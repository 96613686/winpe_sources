# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000556b`
- end: `0x180005590`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d18`
- `0x1800024dc`

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
0x18000556b  mov     [rsp+arg_8], rdx
0x180005570  push    rbp
0x180005571  sub     rsp, 20h
0x180005575  mov     rbp, rdx
0x180005578  xor     r8d, r8d
0x18000557b  mov     dl, 1
0x18000557d  mov     rcx, [rbp+60h]
0x180005581  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180005586  xor     edx, edx; pThrowInfo
0x180005588  xor     ecx, ecx; pExceptionObject
0x18000558a  call    _CxxThrowException_0
```
