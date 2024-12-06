% *CI/CD SAST engines*
% The art 🎨 and misery 😖 of writing real-life abstract interpertation
% Oren Ish Shalom

# Setting

- CI/CD
- limited time ⌛ ( minutes )
- limited space
  * docker(s) size(s) 🐳
  * memory consumption 💾
- input size
  * files → 10<sup>3</sup>
  * callables → 10<sup>4</sup>

# Design

```
      SRC           SRC           SRC             SRC
       ┊            ┊            ┊              ┊
   AST(py)🌴     AST(rb)🌳    AST(php)🌵  ...  AST(js)🌱
       ┊            ┊            ┊              ┊
      AST🎄         AST🎄        AST🎄          AST🎄
       ┊            ┊            ┊              ┊
        ━━━━━━━━━ CodeGen ━━━━━━━━━━   
       ┊    ┊        ┊                 ┊      ┊
Callable  Callable  Callable ......  Callable  Callable 
       ┊    ┊        ┊                 ┊      ┊
  AbsInt  AbsInt    AbsInt  ......     AbsInt  AbsInt
       ┊    ┊        ┊                 ┊      ┊
        ━━━━━━━  Knowledge Base 🧠 ━━━━━
                        ⬆️⬆️⬆️⬆️⬆️
                           Queries
```