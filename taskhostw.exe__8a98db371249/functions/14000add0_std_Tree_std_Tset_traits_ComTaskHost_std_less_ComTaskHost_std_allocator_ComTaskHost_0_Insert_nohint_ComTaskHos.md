# _std::_Tree_std::_Tset_traits_ComTaskHost___std::less_ComTaskHost____std::allocator_ComTaskHost____0___::_Insert_nohint_ComTaskHost___const_&_std::_Nil__::_1_::catch$0

- ea: `0x14000add0`
- end: `0x14000ade7`
- name: `_std::_Tree_std::_Tset_traits_ComTaskHost___std::less_ComTaskHost____std::allocator_ComTaskHost____0___::_Insert_nohint_ComTaskHost___const_&_std::_Nil__::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000894c`

## pseudocode

```c
void __noreturn std::_Tree_std::_Tset_traits_ComTaskHost___std::less_ComTaskHost____std::allocator_ComTaskHost____0___::_Insert_nohint_ComTaskHost___const___std::_Nil__::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x14000add0  mov     [rsp+arg_8], rdx
0x14000add5  push    rbp
0x14000add6  sub     rsp, 30h
0x14000adda  mov     rbp, rdx
0x14000addd  xor     edx, edx; pThrowInfo
0x14000addf  xor     ecx, ecx; pExceptionObject
0x14000ade1  call    _CxxThrowException_0
```
