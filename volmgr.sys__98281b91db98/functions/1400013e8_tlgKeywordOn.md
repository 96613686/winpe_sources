# _tlgKeywordOn

- ea: `0x1400013e8`
- end: `0x140001417`
- name: `_tlgKeywordOn`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010d7c`
- `0x14001171c`

## callees

- `0x1400013e8`

## pseudocode

```c
bool tlgKeywordOn()
{
  return (qword_14000A058 & 0x400000000000LL) != 0 && (qword_14000A060 & 0x400000000000LL) == qword_14000A060;
}

```

## disassembly

```asm
0x1400013e8  mov     rcx, cs:qword_14000A060
0x1400013ef  mov     rdx, 400000000000h
0x1400013f9  mov     rax, cs:qword_14000A058
0x140001400  test    rdx, rax
0x140001403  jz      short loc_140001414
0x140001405  mov     rax, rcx
0x140001408  and     rax, rdx
0x14000140b  cmp     rax, rcx
0x14000140e  jnz     short loc_140001414
0x140001410  mov     al, 1
0x140001412  retn
0x140001414  xor     al, al
0x140001416  retn
```
