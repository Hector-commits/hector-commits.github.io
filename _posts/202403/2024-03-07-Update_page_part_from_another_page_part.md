---
title: Update a Business Central Page Part from another Page Part
date: 2024-03-07 18:00:00 000
categories: [Business Central]
tags: [Business Central]
published: false
---

## This is quite easy by using an Id Provider
The provider establishes the link between different page parts. In the following example I have a main header, but I'm not interested in updating the content of the second subpage from the main header, I'm interested in updating the content of the Second page part from the first page part. With the Provider we establish the link for the filters, and magically the SecondSubpage will now be able to discover the symbols of the FirstSubpage!

```pascal
    part(FirstSubpage; "First Subpage")

    {
        ApplicationArea = All;
        Caption = 'SubPage';
        SubPageLink = "Entry No." = field("Entry No.");
        UpdatePropagation = SubPart;


    }
    part(SecondSubpage; "Second Subpage")
    {
        ApplicationArea = All;
        UpdatePropagation = SubPart;
        Provider = FirstSubpage;//!! 
        SubPageLink = "Code" = field("Code");
    }
```
{: file='AL'}