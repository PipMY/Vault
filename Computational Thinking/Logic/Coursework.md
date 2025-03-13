1. Answer the following questions about complete sets of logical connectives, in each case justifying your answer.
- (i) Show $\{\neg ,\implies\}$ is a complete set of connectives.
-  We already have $\neg$ in the set so negation can be expressed
- 

| $$p$$ | $$q$$ | $$\neg p$$ | $$\neg q$$ | $$p \implies q$$ | $$p \implies \neg q$$ | $$\neg(p \implies \neg q)$$ | $$\neg(\neg p \implies  q)$$ |
| ----- | ----- | ---------- | ---------- | ---------------- | --------------------- | --------------------------- | ---------------------------- |
| T     | T     | F          | F          | T                | F                     | T                           | T                            |
| T     | F     | F          | T          | F                | T                     | F                           | T                            |
| F     | T     | T          | F          | T                | T                     | F                           | T                            |
| F     | F     | T          | T          | T                | T                     | F                           | F                            |
- $\neg(p \implies \neg q)=p \land q$
- $\neg(\neg p \implies  q)=p \vee q$


- (ii) Show $\{ \implies,0 \}$ is a complete set of connectives (where 0 is the constant false).
- 

| $$p$$ | $$q$$ | $$0$$ | $$p \implies 0$$ | $$q \implies 0$$ |
| ----- | ----- | ----- | ---------------- | ---------------- |
| T     | T     | F     | T                | F                |
| T     | F     | F     | T                | T                |
| F     | T     | F     | F                | F                |
| F     | F     | F     | F                | T                |
- $p \implies 0=\neg p$
- We know that $\neg(p \implies \neg q)=p \land q$ 
