% *CI/CD SAST engines*
% The art 🎨 and misery 😖 of writing real-life abstract interpertation
% Oren Ish Shalom

# Setting

- CI/CD
- limited time ⌛ ( minutes )
- limited space
  <ul class="no-increment">
    <li>docker(s) size(s) 🐳</li>
    <li>memory consumption 💾</li>
  </ul>
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
- bitcode
  <ul class="no-increment">
    <li>"build or buy"</li>
    <li>zend, v8, yarv, dex, ...</li>
  </ul>
- chaotic iteration ?
  <ul class="no-increment">
    <li>simpler !</li>
    <li>non-converging scenarios</li>
  </ul>

# Results 📊

- hard to evaluate
- false negatives
  * dismissed as bugs 🪲
  * wrong queries ➡️ 🧠
- false positives
  <ul class="no-increment">
    <li>no benchmarks</li>
    <li>very few breakthroughs 😶</li>
  </ul>
- usability
  <ul class="no-increment">
    <li>running time</li>
    <li>memory consumption</li>
  </ul>
