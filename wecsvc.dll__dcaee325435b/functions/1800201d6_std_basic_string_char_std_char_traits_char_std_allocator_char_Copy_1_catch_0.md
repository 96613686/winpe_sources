# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x1800201d6`
- end: `0x1800201fb`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000195c`
- `0x180001fec`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x1800201d6  mov     [rsp+arg_8], rdx
0x1800201db  push    rbp
0x1800201dc  sub     rsp, 20h
0x1800201e0  mov     rbp, rdx
0x1800201e3  xor     r8d, r8d
0x1800201e6  mov     dl, 1
0x1800201e8  mov     rcx, [rbp+50h]
0x1800201ec  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x1800201f1  xor     edx, edx; pThrowInfo
0x1800201f3  xor     ecx, ecx; pExceptionObject
0x1800201f5  call    _CxxThrowException_0
```
