# _tlgKeywordOn

- ea: `0x140001008`
- end: `0x140001027`
- name: `_tlgKeywordOn`
- size: `31`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x140014c90`
- `0x140019c40`
- `0x140019da0`
- `0x14001a20c`
- `0x14001b0bc`
- `0x14001b524`
- `0x14001c244`
- `0x14001c688`
- `0x140023644`
- `0x1400241c4`
- `0x140026210`
- `0x140026de0`
- `0x140027f24`
- `0x14002da54`
- `0x14002ea5c`
- `0x1400303e8`
- `0x140030d54`
- `0x1400318f0`
- `0x140032500`
- `0x1400328d8`
- `0x140033f90`

## callees

- `0x140001008`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (*(_QWORD *)(a1 + 16) & a2) != 0 && (a2 & *(_QWORD *)(a1 + 24)) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x140001008  mov     r8, [rcx+18h]
0x14000100c  mov     rax, [rcx+10h]
0x140001010  test    rdx, rax
0x140001013  jz      short loc_140001024
0x140001015  mov     rax, r8
0x140001018  and     rax, rdx
0x14000101b  cmp     rax, r8
0x14000101e  jnz     short loc_140001024
0x140001020  mov     al, 1
0x140001022  retn
0x140001024  xor     al, al
0x140001026  retn
```
