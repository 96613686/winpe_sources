# _tlgKeywordOn

- ea: `0x18000d6cc`
- end: `0x18000d6fa`
- name: `_tlgKeywordOn`
- size: `46`
- prototype: `bool()`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180002288`
- `0x180009b50`
- `0x180009f14`
- `0x18000c34c`
- `0x18000d080`
- `0x18000d2f4`
- `0x18000f6f4`
- `0x180015e68`
- `0x180015f78`
- `0x1800160e8`

## callees

- `0x18000d6cc`

## pseudocode

```c
bool tlgKeywordOn()
{
  return (qword_1800241A0 & 0x400000000000LL) != 0 && (qword_1800241A8 & 0x400000000000LL) == qword_1800241A8;
}

```

## disassembly

```asm
0x18000d6cc  mov     rcx, cs:qword_1800241A8
0x18000d6d3  mov     rdx, 400000000000h
0x18000d6dd  mov     rax, cs:qword_1800241A0
0x18000d6e4  test    rdx, rax
0x18000d6e7  jz      short loc_18000D6F7
0x18000d6e9  mov     rax, rcx
0x18000d6ec  and     rax, rdx
0x18000d6ef  cmp     rax, rcx
0x18000d6f2  jnz     short loc_18000D6F7
0x18000d6f4  mov     al, 1
0x18000d6f6  retn
0x18000d6f7  xor     al, al
0x18000d6f9  retn
```
