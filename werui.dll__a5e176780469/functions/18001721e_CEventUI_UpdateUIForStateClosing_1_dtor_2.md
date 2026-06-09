# _CEventUI::UpdateUIForStateClosing_::_1_::dtor$2

- ea: `0x18001721e`
- end: `0x18001722a`
- name: `_CEventUI::UpdateUIForStateClosing_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall CEventUI::UpdateUIForStateClosing_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 184));
}

```

## disassembly

```asm
0x18001721e  lea     rcx, [rdx+0B8h]; void *
0x180017225  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
