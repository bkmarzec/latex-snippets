# latex-snippets

# Circuits

## 2-to-4 decoder

![alt text](https://github.com/bkmarzec/latex-snippets/blob/master/circuits/2-zu-4-decoder.png "2-to-4 decoder")

```tex
\begin{tikzpicture}[circuit logic US, every circuit symbol/.style={logic gate IEC symbol color=black,fill=black!5,draw=black}]
% UND-Gatter
\node at (4,2)  (g1) [and gate, inputs={nnnn}] {};
\node at (4,1)  (g2) [and gate, inputs={nnnn}] {};
\node at (4,0)  (g3) [and gate, inputs={nnnn}] {};
\node at (4,-1) (g4) [and gate, inputs={nnnn}] {};

% Eingaenge
\node[left = 3 of g2.input 1] (label1) {$E_0$};
\node[left = 3 of g3.input 2] (label2) {$E_1$};

% NOT-Gatter
\node at ($(label1)+(.85,-.5)$) (g5) [not gate, scale=.5] {};
\node at ($(label2)+(.85,-.5)$) (g6) [not gate, scale=.5] {};

% Verbindungen
\draw (label1.east) -- ++ (right:1cm) |- (g1.input 4);
\draw (label1.east) -- ++ (right:1cm) |- (g3.input 1);
\fill ($(label1.east)+(1cm,0)$) circle (2pt);

\draw (label1.east) -- ++ (right:2mm) |- (g5.input);
\draw (g5.output) -- ++ (right:.65cm) |- (g2.input 4);
\draw (g5.output) -- ++ (right:.65cm) |- (g4.input 1);
\fill ($(g5.output)+(.65cm,0)$) circle (2pt);

\draw (label2.east) -- ++ (right:2cm) |- (g1.input 1);
\draw (label2.east) -- ++ (right:2cm) |- (g2.input 1);

\draw (label2.east) -- ++ (right:2mm) |- (g6.input);
\draw (g6.output) -- ++ (right:1.65cm) |- (g3.input 4);
\draw (g6.output) -- ++ (right:1.65cm) |- (g4.input 4);
\fill ($(g6.output)+(1.65cm,0)$) circle (2pt);

\fill ($(g2.input 1)-(1cm,0)$) circle (2pt);

% Ausgaenge
\node [right = 0.5 of g1.output] (label3) {$F_0$}; \draw (g1.output) -- (label3);
\node [right = 0.5 of g2.output] (label4) {$F_1$}; \draw (g2.output) -- (label4);
\node [right = 0.5 of g3.output] (label5) {$F_2$}; \draw (g3.output) -- (label5);
\node [right = 0.5 of g4.output] (label6) {$F_3$}; \draw (g4.output) -- (label6);
\end{tikzpicture}
```
