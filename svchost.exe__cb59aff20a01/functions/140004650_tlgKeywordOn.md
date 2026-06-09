# _tlgKeywordOn

- ea: `0x140004650`
- end: `0x140004679`
- name: `_tlgKeywordOn`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a40`
- `0x140008124`

## callees

- `0x140004650`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return !a2 || (qword_14000F010 & a2) != 0 && (a2 & qword_14000F018) == qword_14000F018;
}

```

## disassembly

```asm
0x140004650  test    rdx, rdx
0x140004653  jz      short loc_140004673
0x140004655  mov     rcx, cs:qword_14000F018
0x14000465c  mov     rax, cs:qword_14000F010
0x140004663  test    rdx, rax
0x140004666  jz      short loc_140004676
0x140004668  mov     rax, rcx
0x14000466b  and     rax, rdx
0x14000466e  cmp     rax, rcx
0x140004671  jnz     short loc_140004676
0x140004673  mov     al, 1
0x140004675  retn
0x140004676  xor     al, al
0x140004678  retn
```
