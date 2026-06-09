# _CFciPropertiesShellExt::ApplyThreadProc_::_1_::dtor$4

- ea: `0x18001c6a6`
- end: `0x18001c6b2`
- name: `_CFciPropertiesShellExt::ApplyThreadProc_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005044`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::ApplyThreadProc_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 56));
}

```

## disassembly

```asm
0x18001c6a6  lea     rcx, [rdx+38h]; this
0x18001c6ad  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
