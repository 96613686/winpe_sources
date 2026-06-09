# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800167d0`
- end: `0x1800167da`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001ac93`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800167d3`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800167d0  mov     rcx, [rcx]
0x1800167d3  jmp     cs:__imp_SysFreeString
```
