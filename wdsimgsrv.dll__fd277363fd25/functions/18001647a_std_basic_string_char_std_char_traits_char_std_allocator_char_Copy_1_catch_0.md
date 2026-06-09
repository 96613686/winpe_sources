# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18001647a`
- end: `0x18001649f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ea8`
- `0x1800025cc`

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
0x18001647a  mov     [rsp+arg_8], rdx
0x18001647f  push    rbp
0x180016480  sub     rsp, 20h
0x180016484  mov     rbp, rdx
0x180016487  xor     r8d, r8d
0x18001648a  mov     dl, 1
0x18001648c  mov     rcx, [rbp+60h]
0x180016490  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180016495  xor     edx, edx; pThrowInfo
0x180016497  xor     ecx, ecx; pExceptionObject
0x180016499  call    _CxxThrowException_0
```
