# _CXmlStreamDocument::GetParsed_::_1_::dtor$0

- ea: `0x180014ee5`
- end: `0x180014ef1`
- name: `_CXmlStreamDocument::GetParsed_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180004e2c`

## pseudocode

```c
HRESULT __fastcall CXmlStreamDocument::GetParsed_::_1_::dtor_0(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 2);
}

```

## disassembly

```asm
0x180014ee5  lea     rcx, [rdx+30h]; pvarg
0x180014eec  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
