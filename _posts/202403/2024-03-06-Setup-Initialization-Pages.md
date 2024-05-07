---
title: Always initialize the record on the Setup Pages in Business Central
date: 2024-03-06 12:30:00 000
categories: [Business Central]
tags: [Business Central, Setup]
published: false
---
## It's always a good practice to initialize the Rec on the Setup pages
This is for the typical tables which have the field "Primary Key" on Business Central. With this little code we avoid having to use the + button to generate the record.

```pascal
//remember to use the property InsertAllowed = false;
InsertAllowed = false;

//Also, unless required otherwise use the field "Primary Key" as Code[10]

trigger OnOpenPage()
begin
    Rec.Reset();
    if not Rec.Get() then begin
        Rec.Init();
        Rec.Insert();
    end;
end;
```
{: file='AL'}

