# _CEventUI::UpdateUIForStateClosing_::_1_::dtor$0

- ea: `0x1800171fa`
- end: `0x180017206`
- name: `_CEventUI::UpdateUIForStateClosing_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall CEventUI::UpdateUIForStateClosing_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 216));
}

```

## disassembly

```asm
0x1800171fa  lea     rcx, [rdx+0D8h]; void *
0x180017201  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
