# _tlgKeywordOn

- ea: `0x180001234`
- end: `0x180001258`
- name: `_tlgKeywordOn`
- size: `36`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090f8`
- `0x1800091b0`
- `0x1800115c4`
- `0x1800118a8`
- `0x180011af0`
- `0x18001275c`
- `0x180012d68`

## callees

- `0x180001234`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  return (qword_180022010 & a2) != 0 && (a2 & qword_180022018) == qword_180022018;
}

```

## disassembly

```asm
0x180001234  mov     rcx, cs:qword_180022018
0x18000123b  mov     rax, cs:qword_180022010
0x180001242  test    rdx, rax
0x180001245  jz      short loc_180001255
0x180001247  mov     rax, rcx
0x18000124a  and     rax, rdx
0x18000124d  cmp     rax, rcx
0x180001250  jnz     short loc_180001255
0x180001252  mov     al, 1
0x180001254  retn
0x180001255  xor     al, al
0x180001257  retn
```
