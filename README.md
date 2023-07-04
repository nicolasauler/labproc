# Questão 1
## Enunciado
Escreva instruções de Máquina A32 para as seguintes pseudo-instruções:

```assembly
nop
incr r0
decr r0
```

## Resposta
No arm não há addi, por exemplo.

```assembly
mov r0, #0
add r0, r0, #1
sub r0, r0, #1
```

# Questão 2
## Enunciado
Escreva instruções de Máquina A32 para as seguintes pseudo-instruções:

```assembly
clr r0 // zera r0
not r0 // inverte r0 bit a bit
neg r0 // faz r0 = -r0
```

## Resposta 
```assembly
and r0, r0, #0 // mov r0, #0
mun r0, r0
rsb r0, r0, #0
```

# Questão 3
## Enunciado
Escreva instruções de Máquina A32 para as seguintes pseudo-instruções:

```assembly
ror r0, #3 // roda r0 tres bits a direita
push r0 // coloca r0 na pilha
dob 40 // duplica o valor de r0
```

## Resposta
Tem de decrementar o stack pointer, por quê?

```assembly
mov r0, r0, ror #3 // ou lsr r0, r0, #3
srt r0, [sp, #-4] // ou stmdb sp!, {r0}
add r0, r0, r0 // ou lsl r0, r0, #1 ou mov r0, r0, lsl #1
```

# Questão 4
## Enunciado
Essas instruções existem no conjunto A32 ou não e por que?

```assembly
mov sp, r0, r1, lsr #8
adds r3, pc, r0, rol #1
```

## Resposta
rol não existe
mov errado pois só pode 2 parametros

```assembly
```

# Questão 5
## Enunciado

## Resposta

# Questão 6
## Enunciado

## Resposta

# Questão 7
## Enunciado

## Resposta

# Questão 8
## Enunciado

## Resposta