# ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)

- ea: `0x140002410`
- end: `0x14000241a`
- name: `??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003070`
- `0x140005ee4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140002413`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::stringdispid::~stringdispid(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140002410  mov     rcx, [rcx]
0x140002413  jmp     cs:__imp_SysFreeString
```
