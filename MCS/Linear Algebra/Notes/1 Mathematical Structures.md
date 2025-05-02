## Groups 
For something to be a group it must have a set $G$, a binary operation $*$, and some axioms:

- $*$ is closed on $G$ (This means that any use of $*$ on $G$ can only result in an element of $G$)
- $*$ is associative ($\forall a,b,c$ in $G$, $a*(b*c)=(a*b)*c$)
- $*$ has an inverse operator $e$ ($\forall a \in G. \exists b \in G.a*b=b*a=e$)
- There exists a $Neutral$ element ($e \in G \space where \space \forall a \in G.a*e=e*a=a$)

## Examples of Groups / Example Questions
###### Even numbers with addition
- [x] Closure
- [x] Associative
- [x] Inverse
- [x] Neutral
So, yes this does form a group.
###### Odd numbers with addition
- [ ] Closure (This fails because adding 2 odd numbers generates an even number)
So, no this does not form a group.

###### Rational numbers with multiplication
- [x] Closure
- [x] Associative
- [ ] Inverse (This fails because multiplication by 0 cannot be inverted)
So, no this does not form a group.

###### Strings with concatenation
- [x] Closure
- [x] Associative
- [ ] Inverse (This fails because every string must have an inverse $s^{-1}$ such that: $s+s^{-1}=s^{-1}+s=e$, suppose $s=$"hello", what string $t$ would satisfy "hello"+ $t=e$ )
So, no this does not form a group.

## Field Axioms

