# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180002750`
- end: `0x18000275a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComBSTR *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ddf8`
- `0x18002e127`
- `0x18002ee0e`
- `0x18002ef59`
- `0x18002ef6b`
- `0x18002ef8f`
- `0x18002f166`
- `0x18002f18a`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180002753`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180002750  mov     rcx, [rcx]
0x180002753  jmp     cs:__imp_SysFreeString
```
