# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x180013337`
- end: `0x18001335c`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001dc8`
- `0x180002b4c`

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
0x180013337  mov     [rsp+arg_8], rdx
0x18001333c  push    rbp
0x18001333d  sub     rsp, 20h
0x180013341  mov     rbp, rdx
0x180013344  xor     r8d, r8d
0x180013347  mov     dl, 1
0x180013349  mov     rcx, [rbp+60h]
0x18001334d  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180013352  xor     edx, edx; pThrowInfo
0x180013354  xor     ecx, ecx; pExceptionObject
0x180013356  call    _CxxThrowException_0
```
