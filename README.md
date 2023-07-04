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
mov errado pois só pode 2 parametros (e tem 3)
rol não existe

```assembly
naosei
adds r3, pc, r0, ror #31
```

Se usasse registrador na segunda instrução:
```assembly
rsb r3, r2, #32
mov r1, r1, ror r3
```

# Questão 5
## Enunciado
Essas instruções existem no conjunto A32 ou não e por que?

```assembly
muls r8, [r3, #4]!
blne r10
```

## Resposta
Não, pois muls não pode acessar vetorial, além disso,
muls necessita de 3 params.

No caso de blne, não funciona com registrador,
e, sim, com label ou offset de pc.

# Questão 6
## Enunciado
Essas instruções existem no conjunto A32 ou não e por que?

```assembly
rsb r4, r9 #0x1ff
strb r5, [sp]!, #4
```

## Resposta
Na primeira instrução, não existe rsb com imediato.

Quanto a segunda instrução:
! significa pré-indexado e strb é store byte

Quando há pré-indexado, sp é atualizado:
```assembly
strb r5, [sp, #4]! // r5 é salvo em sp + 4, sp vira sp + 4
```

Quando não tem !, sp não é atualizado
```assembly
strb r5, [sp, #4] // r5 é salvo em sp + 4
```

Quando [sp], #4 -> pós indexado, r5 é guardado em sp, e depois sp é atualizado
```assembly
strb r5, [sp], #4 // r5 é salvo em sp, sp vira sp + 4
```

# Questão 7
## Enunciado
Essas instruções existem no conjunto A32 ou não e por que?

```assembly
ldrle r0, [r8, r2, #-4]
ldr r3, [r1], r2, lsl #4
```

## Resposta

# Questão 8
## Enunciado

## Resposta
