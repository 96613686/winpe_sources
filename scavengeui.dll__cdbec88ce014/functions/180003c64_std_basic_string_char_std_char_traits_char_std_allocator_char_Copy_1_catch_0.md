# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x180003c64`
- end: `0x180003c89`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001338`
- `0x18000200c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::string::_Tidy(*(void ***)(a2 + 96), 1, 0);
  throw;
}

```

## disassembly

```asm
0x180003c64  mov     [rsp+arg_8], rdx
0x180003c69  push    rbp
0x180003c6a  sub     rsp, 20h
0x180003c6e  mov     rbp, rdx
0x180003c71  xor     r8d, r8d
0x180003c74  mov     dl, 1
0x180003c76  mov     rcx, [rbp+60h]
0x180003c7a  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180003c7f  xor     edx, edx; pThrowInfo
0x180003c81  xor     ecx, ecx; pExceptionObject
0x180003c83  call    _CxxThrowException_0
```
