# _CEventUI::UploadDlgUpdateState_::_1_::dtor$0

- ea: `0x180017278`
- end: `0x180017284`
- name: `_CEventUI::UploadDlgUpdateState_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall CEventUI::UploadDlgUpdateState_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 64));
}

```

## disassembly

```asm
0x180017278  lea     rcx, [rdx+40h]; void *
0x18001727f  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
