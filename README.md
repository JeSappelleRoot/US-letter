# US-letter


US-letter is a simple template to make a letter as US format.

You need to edit these values : 
- `\namefrom{Your name HERE}`, to your name
- `\addrfrom{Sender address HERE}`, to your postal address
- `\addrto{Recipient address HERE}`, to the recipiant address

> You can also modify :
> - `\greetto{Dear Madam, Dear Sir,}`, to use your favorite greeting
> - `\closeline{Sincerely,}`, to use your own final word

# About options and spacing with *newlfm* LaTex module

This LaTex template come from OverLeaf template, but it's been a little bit modified, to include *newlfm* module.  
This allow to get a better spacing management between different parts of the letter.

> Refer to : https://texblog.org/2013/11/11/latexs-alternative-letter-class-newlfm/

## Options


In preambule, you can declare *newlfm* module with options like `\documentclass[12pt,stdletter,orderfromdateto,sigright,dateleft]{newlfm}` : 
- `12pt` set the font size
- `stdletter` set the LaTex document structure as a letter
- `orderfromdateto` define the order of each part (From section, Date section and To section)
- `sigright` to set the signature to the right (bottom of document)
- `dateleft` to set the date to the left (top of document)

You can add or remove options easily with the following documentation :  

![options](https://user-images.githubusercontent.com/52102633/68786870-23e4f780-0606-11ea-81a9-17fe648abbdb.png)


## Vertical spacing

Most of *newlfm* commands have options to set spacing, before of after.  

Use spacing options like : 
```
\newlfmP{dateskipbefore=50pt}
\newlfmP{sigsize=50pt}
\newlfmP{sigskipbefore=50pt}
\newlfmP{addrtoskipafter=50pt}
\newlfmP{greettoskipafter=45pt}
```

Refer to the following document : 

![spacing](https://user-images.githubusercontent.com/52102633/68786871-23e4f780-0606-11ea-955b-d5f4632c9839.png)

