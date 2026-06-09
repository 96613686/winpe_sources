# _WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$0

- ea: `0x18000c6f6`
- end: `0x18000c702`
- name: `_WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800033ac`

## pseudocode

```c
__int64 __fastcall WriteCommaDelimitedStringToVariantBuffer_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 120);
}

```

## disassembly

```asm
0x18000c6f6  lea     rcx, [rdx+78h]
0x18000c6fd  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
