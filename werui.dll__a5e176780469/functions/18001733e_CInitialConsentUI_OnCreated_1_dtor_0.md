# _CInitialConsentUI::OnCreated_::_1_::dtor$0

- ea: `0x18001733e`
- end: `0x18001734a`
- name: `_CInitialConsentUI::OnCreated_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003fc4`

## pseudocode

```c
__int64 __fastcall CInitialConsentUI::OnCreated_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(a2 + 152);
}

```

## disassembly

```asm
0x18001733e  lea     rcx, [rdx+98h]
0x180017345  jmp     ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
```
