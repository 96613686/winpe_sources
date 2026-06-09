# _tlgKeywordOn

- ea: `0x180007da0`
- end: `0x180007dc8`
- name: `_tlgKeywordOn`
- size: `40`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055d0`
- `0x1800097c4`

## callees

- `0x180007da0`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1)
{
  return (*(_QWORD *)(a1 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(a1 + 24) & 0x400000000000LL) == *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x180007da0  mov     rdx, [rcx+18h]
0x180007da4  mov     rax, [rcx+10h]
0x180007da8  mov     rcx, 400000000000h
0x180007db2  test    rcx, rax
0x180007db5  jz      short loc_180007DC5
0x180007db7  mov     rax, rdx
0x180007dba  and     rax, rcx
0x180007dbd  cmp     rax, rdx
0x180007dc0  jnz     short loc_180007DC5
0x180007dc2  mov     al, 1
0x180007dc4  retn
0x180007dc5  xor     al, al
0x180007dc7  retn
```
