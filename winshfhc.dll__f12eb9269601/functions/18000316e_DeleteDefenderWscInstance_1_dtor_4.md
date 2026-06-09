# _DeleteDefenderWscInstance_::_1_::dtor$4

- ea: `0x18000316e`
- end: `0x18000317a`
- name: `_DeleteDefenderWscInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180001b0c`

## pseudocode

```c
void __fastcall DeleteDefenderWscInstance_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComBSTR::~CComBSTR((BSTR *)(a2 + 104));
}

```

## disassembly

```asm
0x18000316e  lea     rcx, [rdx+68h]; this
0x180003175  jmp     ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
```
