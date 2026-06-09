# _WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$4

- ea: `0x18000c73e`
- end: `0x18000c74a`
- name: `_WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800033ac`

## pseudocode

```c
__int64 __fastcall WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 240);
}

```

## disassembly

```asm
0x18000c73e  lea     rcx, [rdx+0F0h]
0x18000c745  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
