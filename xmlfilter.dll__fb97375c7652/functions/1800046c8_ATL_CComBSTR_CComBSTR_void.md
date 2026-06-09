# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x1800046c8`
- end: `0x1800046d2`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015fe9`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800046cb`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800046c8  mov     rcx, [rcx]
0x1800046cb  jmp     cs:__imp_SysFreeString
```
