# PkpValidatePointer

- ea: `0x1400155c8`
- end: `0x1400155d8`
- name: `PkpValidatePointer`
- size: `16`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001560`
- `0x1400021f0`
- `0x140015034`
- `0x1400150a0`
- `0x14001539c`
- `0x140015508`

## callees

- `0x1400155c8`

## pseudocode

```c
bool __fastcall PkpValidatePointer(unsigned int a1, unsigned int a2)
{
  return a2 < a1 && (a2 & 7) == 0;
}

```

## disassembly

```asm
0x1400155c8  cmp     edx, ecx
0x1400155ca  jnb     short loc_1400155D5
0x1400155cc  test    dl, 7
0x1400155cf  jnz     short loc_1400155D5
0x1400155d1  mov     al, 1
0x1400155d3  retn
0x1400155d5  xor     al, al
0x1400155d7  retn
```
