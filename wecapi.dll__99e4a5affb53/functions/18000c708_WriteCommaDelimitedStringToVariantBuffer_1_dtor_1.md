# _WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$1

- ea: `0x18000c708`
- end: `0x18000c714`
- name: `_WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a380`

## pseudocode

```c
void __fastcall WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  StringTokenizer::~StringTokenizer((void **)(a2 + 240));
}

```

## disassembly

```asm
0x18000c708  lea     rcx, [rdx+0F0h]; this
0x18000c70f  jmp     ??1StringTokenizer@@QEAA@XZ; StringTokenizer::~StringTokenizer(void)
```
