# PkpValidatePointer

- ea: `0x140005230`
- end: `0x140005240`
- name: `PkpValidatePointer`
- size: `16`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400037e0`
- `0x140003f40`
- `0x1400042b0`
- `0x140004630`
- `0x140004cc0`
- `0x140005300`
- `0x140005750`
- `0x1400116d8`
- `0x140011890`

## callees

- `0x140005230`

## pseudocode

```c
bool __fastcall PkpValidatePointer(unsigned int a1, unsigned int a2)
{
  return a2 < a1 && (a2 & 7) == 0;
}

```

## disassembly

```asm
0x140005230  cmp     edx, ecx
0x140005232  jb      short loc_140005238
0x140005234  xor     al, al
0x140005236  retn
0x140005238  test    dl, 7
0x14000523b  jnz     short loc_140005234
0x14000523d  mov     al, 1
0x14000523f  retn
```
