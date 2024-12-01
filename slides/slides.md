% *CI/CD SAST engines*
% The art 🎨 and misery 😖 of writing real-life abstract interpertation
% Oren Ish Shalom

# Setting

- CI/CD
- limited time ⌛ ( minutes )
- limited space
  * docker(s) size(s) 🐳
  * memory consumption 💾
- code size

# Design

```
      SRC           SRC           SRC
       ┊            ┊            ┊
   AST(py)🌴     AST(rb)🌳    AST(php)🌵
       │             │             │
      AST🎄        AST🎄         AST🎄

                 CodeGen

    AbsInt        AbsInt         AbsInt

               Knowledge Base

                 Queries      
```