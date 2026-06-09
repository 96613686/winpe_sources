# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18001a367`
- end: `0x18001a38c`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002f38`
- `0x180003f4c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 96), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18001a367  mov     [rsp+arg_8], rdx
0x18001a36c  push    rbp
0x18001a36d  sub     rsp, 20h
0x18001a371  mov     rbp, rdx
0x18001a374  xor     r8d, r8d
0x18001a377  mov     dl, 1
0x18001a379  mov     rcx, [rbp+60h]
0x18001a37d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18001a382  xor     edx, edx; pThrowInfo
0x18001a384  xor     ecx, ecx; pExceptionObject
0x18001a386  call    _CxxThrowException_0
```
