# ATL::CComVariant::~CComVariant(void)

- ea: `0x180039618`
- end: `0x18003961f`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `7`
- prototype: `HRESULT __stdcall(VARIANTARG *pvarg)`
- caller_count: `9`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800563db`
- `0x1800563ed`
- `0x1800563ff`
- `0x1800564d7`
- `0x18005651f`
- `0x180056b5e`
- `0x180056c6c`
- `0x180056cfd`
- `0x180056e5e`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180039618`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall ATL::CComVariant::~CComVariant(VARIANTARG *pvarg)
{
  return VariantClear(pvarg);
}

```

## disassembly

```asm
0x180039618  jmp     cs:__imp_VariantClear
```
