# _DeleteDefenderWscInstance_::_1_::dtor$3

- ea: `0x18000315c`
- end: `0x180003168`
- name: `_DeleteDefenderWscInstance_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b0c`

## pseudocode

```c
void __fastcall DeleteDefenderWscInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 96));
}

```

## disassembly

```asm
0x18000315c  lea     rcx, [rdx+60h]; this
0x180003163  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
