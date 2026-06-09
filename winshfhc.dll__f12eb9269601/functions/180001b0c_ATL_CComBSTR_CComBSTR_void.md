# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180001b0c`
- end: `0x180001b16`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000314a`
- `0x18000315c`
- `0x18000316e`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001b0f`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180001b0c  mov     rcx, [rcx]
0x180001b0f  jmp     cs:__imp_SysFreeString
```
