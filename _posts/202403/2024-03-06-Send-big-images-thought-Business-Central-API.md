---
title: Sending big images through Business Central APIs
date: 2024-03-06 9:45:00 000
categories: [Business Central]
tags: [Postman, Business Central, API]
published: false
---
## The key thing here is to use a variable to store the image:
I dind't know that, but it seems that the variables of type Text (without defining the lenght of the variable) support A LOT of characters.
I've tried using Blobs directly, medialinks and so on, but in the end, what works best for me is to decode the image to <b>Base 64</b>, upload straight ahead to a Text variable, and the use the OnValidate trigger of the API variable to bulk it to a Blob. It works perfect, even with very big images.
Here´s my page example
```javascript
page 59999 "Picture API"
{
    PageType = API;
    Caption = 'pictureAPI';
    APIPublisher = 'hp';
    APIGroup = 'pictures';
    APIVersion = 'v1.0';
    EntityName = 'picture';
    EntitySetName = 'picture';
    SourceTable = Item;
    DelayedInsert = true;
    InsertAllowed = false;
    DeleteAllowed = false;
    layout
    {
        area(Content)
        {
            repeater(GroupName)
            {
                field(no; Rec."No.") { }
                field(largeText; largeText)
                {
                    trigger OnValidate()
                    begin
                        ImportPictureFromiEncodedText();
                    end;
                }
            }
        }
    }
    var
        largeText: Text;

    procedure ImportPictureFromiEncodedText()
    var
        TempBlob: Codeunit "Temp Blob";
        Base64Convert: Codeunit "Base64 Convert";
        FileName: Text;
        InStr: InStream;
        OutStr: OutStream;
    begin
        FileName := Rec.Description + '.png';
        TempBlob.CreateOutStream(OutStr);
        Base64Convert.FromBase64(largeText, OutStr);
        TempBlob.CreateInStream(InStr);
        Clear(Rec.Picture);
        Rec.Picture.ImportStream(InStr, FileName);
    end;
}
```
