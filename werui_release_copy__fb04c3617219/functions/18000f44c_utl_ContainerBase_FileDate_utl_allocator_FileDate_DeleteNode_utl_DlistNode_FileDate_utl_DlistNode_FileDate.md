# utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>(utl::_DlistNode<FileDate> *)

- ea: `0x18000f44c`
- end: `0x18000f472`
- name: `??$_DeleteNode@U?$_DlistNode@VFileDate@@@utl@@@?$_ContainerBase@VFileDate@@V?$allocator@VFileDate@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@VFileDate@@@1@@Z`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f654`
- `0x180010df0`

## callees

- `0x180003038`
- `0x180009580`

## pseudocode

```c
void __fastcall utl::_ContainerBase<FileDate,utl::allocator<FileDate>>::_DeleteNode<utl::_DlistNode<FileDate>>(
        __int64 a1,
        char *a2)
{
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(a2 + 16);
  operator delete(a2);
}

```

## disassembly

```asm
0x18000f44c  push    rbx
0x18000f44e  sub     rsp, 20h
0x18000f452  lea     rcx, [rdx+10h]
0x18000f456  mov     rbx, rdx
0x18000f459  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18000f45e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000f465  mov     rcx, rbx; Block
0x18000f468  add     rsp, 20h
0x18000f46c  pop     rbx
0x18000f46d  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
