# FileProvCompressionScheme

- ea: `0x140007a30`
- end: `0x140007a45`
- name: `FileProvCompressionScheme`
- size: `21`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400382b0`
- `0x140038b10`
- `0x140039750`
- `0x14003b0c8`

## pseudocode

```c
__int64 *__fastcall FileProvCompressionScheme(__int64 a1)
{
  return &g_CompressionScheme[104 * *(unsigned int *)(a1 + 4)];
}

```

## disassembly

```asm
0x140007a30  mov     eax, [rcx+4]
0x140007a33  lea     rcx, g_CompressionScheme
0x140007a3a  imul    rax, 340h
0x140007a41  add     rax, rcx
0x140007a44  retn
```
