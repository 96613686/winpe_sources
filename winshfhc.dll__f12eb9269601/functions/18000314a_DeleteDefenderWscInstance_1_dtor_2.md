# _DeleteDefenderWscInstance_::_1_::dtor$2

- ea: `0x18000314a`
- end: `0x180003156`
- name: `_DeleteDefenderWscInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b0c`

## pseudocode

```c
void __fastcall DeleteDefenderWscInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 216));
}

```

## disassembly

```asm
0x18000314a  lea     rcx, [rdx+0D8h]; this
0x180003151  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
