# _WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$2

- ea: `0x18000c71a`
- end: `0x18000c726`
- name: `_WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000625c`

## pseudocode

```c
__int64 __fastcall WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<unsigned char>::_Tidy(a2 + 40);
}

```

## disassembly

```asm
0x18000c71a  lea     rcx, [rdx+28h]
0x18000c721  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
