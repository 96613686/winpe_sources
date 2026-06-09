# _CEventUI::UpdateUIForStateClosing_::_1_::dtor$1

- ea: `0x18001720c`
- end: `0x180017218`
- name: `_CEventUI::UpdateUIForStateClosing_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall CEventUI::UpdateUIForStateClosing_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 152));
}

```

## disassembly

```asm
0x18001720c  lea     rcx, [rdx+98h]; void *
0x180017213  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
