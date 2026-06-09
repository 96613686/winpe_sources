# _tlgKeywordOn

- ea: `0x140001008`
- end: `0x140001027`
- name: `_tlgKeywordOn`
- size: `31`
- prototype: `bool __fastcall(__int64, __int64)`
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
- `0x140023694`
- `0x140024214`
- `0x140026260`
- `0x140026e30`
- `0x140027f74`
- `0x14002daa4`
- `0x14002eaac`
- `0x140030438`
- `0x140030da4`
- `0x140031940`
- `0x140032550`
- `0x140032928`
- `0x140033fe0`

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
