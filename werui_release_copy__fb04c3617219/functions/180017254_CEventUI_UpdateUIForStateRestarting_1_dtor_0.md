# _CEventUI::UpdateUIForStateRestarting_::_1_::dtor$0

- ea: `0x180017254`
- end: `0x180017260`
- name: `_CEventUI::UpdateUIForStateRestarting_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall CEventUI::UpdateUIForStateRestarting_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 128));
}

```

## disassembly

```asm
0x180017254  lea     rcx, [rdx+80h]; void *
0x18001725b  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
