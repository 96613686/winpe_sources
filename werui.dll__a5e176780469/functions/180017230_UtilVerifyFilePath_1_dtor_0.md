# _UtilVerifyFilePath_::_1_::dtor$0

- ea: `0x180017230`
- end: `0x18001723c`
- name: `_UtilVerifyFilePath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005dd0`

## pseudocode

```c
void __fastcall UtilVerifyFilePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::~basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((void *)(a2 + 120));
}

```

## disassembly

```asm
0x180017230  lea     rcx, [rdx+78h]; void *
0x180017237  jmp     ??1?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::~basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
```
