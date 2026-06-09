# ATL::CComVariant::~CComVariant(void)

- ea: `0x180005044`
- end: `0x180005054`
- name: `??1CComVariant@ATL@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(VARIANTARG *this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001c682`
- `0x18001c694`
- `0x18001c6a6`
- `0x18001c6ca`
- `0x18001c82a`
- `0x18001c83c`
- `0x18001c84e`
- `0x18001c860`
- `0x18001c884`
- `0x18001d152`
- `0x18001d164`
- `0x18001d19a`
- `0x18001d69d`
- `0x18001df1e`
- `0x18001e0e6`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180005048`
- `OLEAUT32!__imp_VariantClear` at `0x180005048`

## pseudocode

```c
void __fastcall ATL::CComVariant::~CComVariant(VARIANTARG *this)
{
  VariantClear(this);
}

```

## disassembly

```asm
0x180005044  sub     rsp, 28h
0x180005048  call    cs:__imp_VariantClear
0x18000504e  nop
0x18000504f  add     rsp, 28h
0x180005053  retn
```
