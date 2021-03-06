# US-letter


US-letter is a simple template to make a letter as US format.

You need to edit these values : 
- About sender:  
  - `\namefrom{Your name HERE}`, to your name
  - `\emailfrom{Your email HERE}`, to your email address
  - `\phonefrom{Your phone HERE}`, to your phone
  - `\addrfrom{Sender address HERE}`, to your postal address
- About recipient : 
  - `\nameto{Recipient name HERE}`, to the recipient name
  - `\addrto{Recipient address HERE}`, to the recipiant address
- The mail subject with changing `\regarding{Subject HERE}`
  

> You can also modify :
> - `\dateset{\today}`, to set the date manually
> - `\greetto{Dear Madam, Dear Sir,}`, to use your favorite greeting
> - `\closeline{Sincerely,}`, to use your own final word

# About options and spacing with *newlfm* LaTex module

This LaTex template come from OverLeaf template, but it's been a little bit modified, to include *newlfm* module.  
This allow to get a better spacing management between different parts of the letter.

> Refer to : https://texblog.org/2013/11/11/latexs-alternative-letter-class-newlfm/  
> Official documentation : http://ctan.math.utah.edu/ctan/tex-archive/macros/latex/contrib/newlfm/newlfm.pdf  
> Also read : https://www.dickimaw-books.com/latex/admin/html/newlfm.shtml

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
```latex
\newlfmP{dateskipbefore=50pt}
\newlfmP{sigsize=50pt}
\newlfmP{sigskipbefore=50pt}
\newlfmP{addrtoskipafter=50pt}
\newlfmP{greettoskipafter=45pt}
```

Refer to the following document : 

![spacing](https://user-images.githubusercontent.com/52102633/68786871-23e4f780-0606-11ea-955b-d5f4632c9839.png)

# Example

> View Example.pdf

```latex
\documentclass[11pt, stdletter, orderfromdateto, addrfromphone, addrfromemail, sigright, dateleft]{newlfm}

\usepackage{etoolbox}
\usepackage{blindtext, xfrac}

%% Patch from https://tex.stackexchange.com/a/395529/226 to address newlfm bug
\makeatletter
\patchcmd{\@zfancyhead}{\fancy@reset}{\f@nch@reset}{}{}
\patchcmd{\@set@em@up}{\f@ncyolh}{\f@nch@olh}{}{}
\patchcmd{\@set@em@up}{\f@ncyolh}{\f@nch@olh}{}{}
\patchcmd{\@set@em@up}{\f@ncyorh}{\f@nch@orh}{}{}
\makeatother

\newlfmP{dateskipbefore=50pt}
\newlfmP{sigsize=50pt}
\newlfmP{sigskipbefore=50pt}
\newlfmP{addrtoskipafter=50pt}
\newlfmP{greettoskipafter=45pt}
\newlfmP{Headlinewd=0pt,Footlinewd=0pt}
 
 
% --------------------------------------------------------------- 

% From informations
\namefrom{John Doe}
\emailfrom{john.doe@everyone.com}
\phonefrom{no phone}
% Sender address
\addrfrom{777, Jackson Avenue\\Oxford MS 38 655}

% Date, can be set manually
\dateset{\today}

% To informations
\nameto{Rick Grimes}
% Recipient address
\addrto{793 Windsor St SW\\Atlanta GA 30315}

% Subject
\regarding{About Alexandria}

% Greet expression
\greetto{Dear Rick}

% Closing expression
\closeline{Sincerely,}
 
% ---------------------------------------------------------------  

\begin{document}
\begin{newlfm}

% Comment \blindtext, used for demo
    \blindtext

% Your text HERE

\end{newlfm}
\end{document}
```

