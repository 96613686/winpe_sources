# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x18000da10`
- end: `0x18000da1a`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `15`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002e890`
- `0x18002e8b0`
- `0x18002e8d0`
- `0x18002ea80`
- `0x18002eaa0`
- `0x18002eb00`
- `0x18002eb20`
- `0x18002ebd0`
- `0x18002ebf0`
- `0x18002ec14`
- `0x18002ec80`
- `0x18002eca0`
- `0x18002ecc0`
- `0x180030250`
- `0x180030352`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000da13`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x18000da10  mov     rcx, [rcx]
0x18000da13  jmp     cs:__imp_SysFreeString
```
