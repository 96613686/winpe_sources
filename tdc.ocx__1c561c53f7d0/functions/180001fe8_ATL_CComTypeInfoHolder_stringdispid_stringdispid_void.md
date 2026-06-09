# ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)

- ea: `0x180001fe8`
- end: `0x180001ff2`
- name: `??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180001feb`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::stringdispid::~stringdispid(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180001fe8  mov     rcx, [rcx]
0x180001feb  jmp     cs:__imp_SysFreeString
```
