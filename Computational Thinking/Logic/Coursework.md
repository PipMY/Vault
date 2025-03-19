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

| $$p \implies (q \implies 0)$$ | $$(p \implies (q \implies 0)) \implies 0$$ | $$((p \implies 0) \implies q) \implies 0$$ |
| ----------------------------- | ------------------------------------------ | ------------------------------------------ |
| F                             | T                                          | T                                          |
| T                             | F                                          | T                                          |
| T                             | F                                          | T                                          |
| T                             | F                                          | F                                          |
- $(p \implies (q \implies 0)) \implies 0=p \land q$
- $((p \implies 0) \implies q) \implies 0=p \vee q$



- (iii) Is $\{\text{NAND},\wedge\}$ a complete set of connectives?
- We already have $\wedge$ in the set so conjunction can be expressed
- 

| $$p$$ | $$q$$ | $$p \land p$$ | $$p\text{ NAND }p$$ | $$q\text{ NAND }q$$ | $$(p\text{ NAND }p)\text{ NAND }(q\text{ NAND }q)$$ |
| ----- | ----- | ------------- | ------------------- | ------------------- | --------------------------------------------------- |
| T     | T     | T             | F                   | F                   | T                                                   |
| T     | F     | T             | F                   | T                   | T                                                   |
| F     | T     | F             | T                   | F                   | T                                                   |
| F     | F     | F             | T                   | T                   | F                                                   |
- $p\text{ NAND }p=\neg p$
- $(p\text{ NAND }p)\text{ NAND }(q\text{ NAND }q)=p \vee q$
- Therefore $\{\text{NAND},\land\}$


- (iv) Is $\{\land,\vee\}$ a complete set of connectives?
- We already have $\land$ and $\vee$ in the set so conjunction and disjunction can be expressed

| $$p$$ | $$p \land p$$ | $$p\vee p$$ |
| ----- | ------------- | ----------- |
| T     | T             | T           |
| F     | F             | F           |

- $\neg p$ cannot be formed because



2. Convert $(((p \implies q)\implies r)\implies(s \implies t))$ to
- (i) Conjunctive Normal Form (CNF)
- $((\neg p \vee q)\implies r)\implies(s \implies t)$
- $(\neg(\neg p\vee q)\vee r)\implies(s \implies t)$
- $\neg(\neg(\neg p\vee q)\vee r)\vee(s \implies t)$
- $\neg(\neg(\neg p\vee q)\vee r)\vee(\neg s\vee t)$
- $(\neg \neg(\neg p\vee q)\land \neg r)\vee(\neg s\vee t)$
- $((\neg p\vee q)\land \neg r)\vee (\neg s\vee t)$
- $((\neg p\vee q)\land \neg r)\vee (\neg s\vee t)$
- $(\neg s\vee t\vee \neg p\vee q)\land(\neg s\vee t\vee \neg r)$

- (ii) Disjunctive Normal Form (DNF)
- $((\neg p \vee q)\implies r)\implies(s \implies t)$
- $(\neg(\neg p\vee q)\vee r)\implies(s \implies t)$
- $\neg(\neg(\neg p\vee q)\vee r)\vee(s \implies t)$
- $\neg(\neg(\neg p\vee q)\vee r)\vee(\neg s\vee t)$
- $(\neg \neg(\neg p\vee q)\land \neg r)\vee(\neg s\vee t)$
- $((\neg p\vee q)\land \neg r)\vee (\neg s\vee t)$
- $((\neg p\vee q)\land \neg r)\vee (\neg s\vee t)$
- $(\neg p\land \neg r)\vee(q\land \neg r)\vee (\neg s\vee t)$
- $(\neg p\land \neg r)\vee(q\land \neg r)\vee\neg s\vee t$

3. What is the purpose of Tseitin's Algorithm? Apply Tseitin's Algorithm to turn propositional formula $(((x_{1}\land x_{2}\land x_{3})\implies(y_{1}\land y_{2}\land y_{3}))\vee z)\text{ to CNF.}$ Tseitin's Algorithm is used to covert propositional formulae into CNF 

4. State with justification if each of the following sentences of predicate logic is logically valid.

- (i) $(\forall x \exists y\forall z\text{ } E(x,y)\land E(y,z))\implies(\forall x\forall z\exists y\text{ }E(x,y)\land E(y,z))$ 
- The left hand side (LHS) states that for all x, there exists a y, such that for all z, $E(x,y)\text{ and }E(y,z)$ hold (the z value essentially doesn't matter).
- The right hand side (RHS) states that for every x and every z, there exists a y where $E(x,y)\text{ and }E(y,z)$ hold.
- In the RHS the y value is allowed to vary depending on the z value.
- This means that the LHS does imply the RHS because the LHS implies there is a single y for every x that works for every z, but the RHS allows y to change depending on z.
- Therefore the implication is logically valid.

- (ii) $(\forall x\exists y\exists u\forall v\text{ }E(x,y)\land E(u,v))\implies(\exists u\forall v\forall x\exists y\text{ }E(x,y)\land E(u,v))$ 
- The left-hand side (LHS) states that for every $x$, there exist $y$ and $u$ such that for all $v$, both $E(x,y)$ and $E(u,v)$ hold.
- The right-hand side (RHS) requires that there exists a **single** $u$ that works for **all** $x$ and $v$, while allowing $y$ to vary with $x$.
- In the LHS, $u$ is chosen **after** $x$, meaning that $u$ can depend on $x$ (i.e., different $x$ values could have different $u$).
- However, in the RHS, a single $u$ must work for **all** $x$, which is a stronger condition.
- Since the existence of $u$ in the LHS does not guarantee a single universal $u$ in the RHS, the implication is **not logically valid** in general.

- (iii) $(\forall x\exists y\forall z\text{ }R(x,y,z))\implies(\exists x\forall y\exists z\text{ }R(x,y,z))$ 
- The LHS states that for all x, there exists a y such that for all z, $R(x,y,z)$ holds (the z value doesn't matter essentially)
- The RHS states that for there exists an x, such that for every y, there is a z such that $R(x,y,z)$ holds.
- According to the LHS, for each x, there is a single y that works for all z that satisfies the condition $R(x,y,z)$, however the RHS states that for each value x, there is a different z for every y which is a stronger condition. This means the LHS doesn't always imply the RHS.
- Therefore the implication isn't logically valid

- (iv) $(\forall x\forall y\exists z\text{ }(E(x,y)\land E(y,z)))\implies(\forall x\forall y\forall z\text{ }(E(x,y)\vee E(y,z)))$
- The LHS states that for every x and y, there exists a z where $(E(x,y)\land E(y,z))$ holds.
- The RHS states that for every x, y, and z, $(E(x,y)\vee E(y,z))$ holds.
- According to the LHS, for any x and any y, there exists a specific z where both $(E(x,y)\land E(y,z))$ hold. 
- The RHS states that for any x, y or z, $(E(x,y) \vee E(y,z))$ holds. Meaning at least one of the conditions hold.
- This is logically valid because according to the LHS, for every x and y, the condition $E(x,y)$ holds  and there exists a value z where $(E(x,y)\land E(y,z))$ holds. On the RHS the only difference is that there is every z and that at least one condition is true. Since x and y are the same as before the first condition $E(x,y)$ will always still be true and the second condition will sometimes be true as described.
- Therefore the implication is logically valid

5. Evaluate the given sentence on the respective relation E over domain $\{ 0,1,2 \}$ with relation $E:=\{ (0,1),(1,0),(1,2),(2,1),(2,0),(0,2) \}$
- (i)$\forall x\forall y\forall z\exists w(E(x,w)\land(E(y,w)\land E(z,w)))$
- For all x, y and z there exists a singular w, where $(E(x,w)\land(E(y,w)\land E(z,w)))$ holds. 
- When x=0, y=0 and z=0, w has to be either 1 or 2
- When x=1, y=1 and z=2, w has to be either 0 or 2
- When x=2, y=2 and z=2, w has to be either 0 or 1
- Since there is no singular w value that satisfies all three functions, then there isn't a w value that satisfies all x, y and z and therefore the statement is false.

- (ii) $\exists x\forall y\forall z\exists w(E(x,w)\land E(y,w)\land E(z,w))$
- There exists x, for all y and z, such that there exists a z, where $(E(x,w)\land E(y,w)\land E(z,w))$ holds.
- When w=0, $E(y,w)=E(0,0)$ is false
- When w=1, $E(y,w)=E(1,1)$ is false
- When w=2, $E(y,w)=E(2,2)$ is false
- Therefore a w doesn't exists such that for all y $(E(x,w)\land E(y,w)\land E(z,w))$ holds.
- Therefore the statement is false

- (iii) $\forall y\exists x\forall z\exists w(E(x,w)\land E(y,w)\land E(z,w))$
- For all y there exists an x, such that for all z there exists a w where $(E(x,w)\land E(y,w)\land E(z,w))$ holds
- For each y, we choose x=y, ensuring that for all z, there exists a valid w that satisfies the relation. 
- As x is always equal to y, and z can be anything, w can always be a unique value that is not equal to x, y or z.
- Since for each y, we can always find an x, and for each z, we can always find a w that satisfies the relation, the statement holds universally over the domain. Thus, the statement is true.

- (iv) $\exists x\exists y\exists z\forall w(E(x,w)\land E(y,w)\land E(z,w))$
- There exists an x, y and z such that for all w, $(E(x,w)\land E(y,w)\land E(z,w))$ must hold.
- Intuitively this statement seems false however this is not enough, so we must check for every value of z under every value of y under every value of x
- 

- (v) 
- $\forall x_{1}\exists x_{2}\forall y_{1}\exists y_{2}\forall z_{1}\exists z_{2}\forall z\exists w$$E(x_{1},x_{2})\land E(x_{2},w)\land E(y_{1},y_{2})\land E(y_{2},w)\land E(z_{1},z_{2})\land E(z_{2},w)\land E(z,w)$ 
- 

- (vi) 
- $\forall x_{1}\exists x_{2}\forall y_{1}\exists y_{2}\forall z_{1}\forall z\exists z_{2}\exists y$ 
- $E(x_{1},x_{2})\land E(x_{2},w)\land E(y_{1},y_{2})\land E(y_{2},w)\land E(z_{1},z_{2})\land E(z_{2},w)\land E(z,w)$
