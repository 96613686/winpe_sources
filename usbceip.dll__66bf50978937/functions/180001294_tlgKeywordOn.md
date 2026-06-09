# _tlgKeywordOn

- ea: `0x180001294`
- end: `0x1800012bc`
- name: `_tlgKeywordOn`
- size: `40`
- prototype: `bool __fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180003dc4`
- `0x180003f8c`
- `0x1800045d0`
- `0x180004d74`
- `0x1800053e4`
- `0x180005784`
- `0x180005b1c`
- `0x180005e94`
- `0x1800066a8`
- `0x180006f18`
- `0x180007134`
- `0x1800074fc`
- `0x1800075e4`
- `0x180007754`
- `0x1800078e0`
- `0x1800079c0`
- `0x180007b44`
- `0x180007f70`

## callees

- `0x180001294`

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
0x180001294  mov     rdx, [rcx+18h]
0x180001298  mov     rax, [rcx+10h]
0x18000129c  mov     rcx, 400000000000h
0x1800012a6  test    rcx, rax
0x1800012a9  jz      short loc_1800012B9
0x1800012ab  mov     rax, rdx
0x1800012ae  and     rax, rcx
0x1800012b1  cmp     rax, rdx
0x1800012b4  jnz     short loc_1800012B9
0x1800012b6  mov     al, 1
0x1800012b8  retn
0x1800012b9  xor     al, al
0x1800012bb  retn
```
