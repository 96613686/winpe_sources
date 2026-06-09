# _tlgKeywordOn

- ea: `0x1400049f0`
- end: `0x140004a1a`
- name: `_tlgKeywordOn`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002cb0`
- `0x1400086f8`

## callees

- `0x1400049f0`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return !a2 || (qword_14000F010 & a2) != 0 && (a2 & qword_14000F018) == qword_14000F018;
}

```

## disassembly

```asm
0x1400049f0  test    rdx, rdx
0x1400049f3  jz      short loc_140004A13
0x1400049f5  mov     rcx, cs:qword_14000F018
0x1400049fc  mov     rax, cs:qword_14000F010
0x140004a03  test    rdx, rax
0x140004a06  jz      short loc_140004A17
0x140004a08  mov     rax, rcx
0x140004a0b  and     rax, rdx
0x140004a0e  cmp     rax, rcx
0x140004a11  jnz     short loc_140004A17
0x140004a13  mov     al, 1
0x140004a15  retn
0x140004a17  xor     al, al
0x140004a19  retn
```
