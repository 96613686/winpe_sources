# dquantBits

- ea: `0x18003e798`
- end: `0x18003e7b8`
- name: `dquantBits`
- size: `32`
- prototype: `char __fastcall(unsigned __int8)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18003146c`
- `0x180032eb4`
- `0x18003fa68`
- `0x180042878`
- `0x180042a84`

## callees

- `0x18003e798`

## pseudocode

```c
char __fastcall dquantBits(unsigned __int8 a1)
{
  char result; // al

  result = 2;
  if ( a1 < 2u )
    return 0;
  if ( a1 < 4u )
    return 1;
  if ( a1 >= 6u )
    return 4 - (a1 < 0xAu);
  return result;
}

```

## disassembly

```asm
0x18003e798  mov     al, 2
0x18003e79a  cmp     cl, al
0x18003e79c  jnb     short loc_18003E7A2
0x18003e79e  xor     al, al
0x18003e7a0  retn
0x18003e7a2  cmp     cl, 4
0x18003e7a5  jnb     short loc_18003E7AB
0x18003e7a7  mov     al, 1
0x18003e7a9  retn
0x18003e7ab  cmp     cl, 6
0x18003e7ae  jb      short locret_18003E7B7
0x18003e7b0  cmp     cl, 0Ah
0x18003e7b3  sbb     al, al
0x18003e7b5  add     al, 4
0x18003e7b7  retn
```
