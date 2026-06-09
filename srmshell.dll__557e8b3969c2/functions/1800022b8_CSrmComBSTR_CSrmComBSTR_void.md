# CSrmComBSTR::~CSrmComBSTR(void)

- ea: `0x1800022b8`
- end: `0x1800022cb`
- name: `??1CSrmComBSTR@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `12`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001c6b8`
- `0x18001c6dc`
- `0x18001cf48`
- `0x18001cf5a`
- `0x18001d12e`
- `0x18001d140`
- `0x18001d1be`
- `0x18001d6af`
- `0x18001dcfe`
- `0x18001dd2a`
- `0x18001e152`
- `0x18001f013`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800022bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800022bf`

## pseudocode

```c
void __fastcall CSrmComBSTR::~CSrmComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800022b8  sub     rsp, 28h
0x1800022bc  mov     rcx, [rcx]; bstrString
0x1800022bf  call    cs:__imp_SysFreeString
0x1800022c5  nop
0x1800022c6  add     rsp, 28h
0x1800022ca  retn
```
