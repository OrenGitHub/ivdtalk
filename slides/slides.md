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
      AST🎄         AST🎄        AST🎄   ...    AST🎄
       ┊            ┊            ┊              ┊
 ━━━━━━━━━━━━━ CodeGen ━━━━━━━━━━━━   
   ┊        ┊                            ┊      ┊
Callable  Callable         ...       Callable   Callable 
   ┊        ┊                            ┊      ┊
   AI        AI            ...             AI     AI
   ┊        ┊                            ┊      ┊
 ━━━━━━━━━━━  Knowledge Base 🧠 ━━━━━━━

                        ⬆️⬆️⬆️⬆️⬆️
                           Queries
```

# Trade-offs 👠 / 👢 / 👡

- intra-procedural / inter-procedural
  * parallelism 🤹
  * bounded dataflow 
- incremental ? privacy ⚠️
- bitcode: build 🧱 or buy 💶
- chaotic iteration ? simpler !
  * non-converging scenarios
  * better parallelism

# Research 👨‍🔬

- parallel queries
- natural language queries
- fine grained parallelism
  * multi-tenant
