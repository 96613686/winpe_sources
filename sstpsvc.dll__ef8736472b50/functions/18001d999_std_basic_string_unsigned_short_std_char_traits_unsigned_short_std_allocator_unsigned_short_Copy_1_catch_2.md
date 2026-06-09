# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$2

- ea: `0x18001d999`
- end: `0x18001d9c1`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$2`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000983e`
- `0x1800134bc`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 128), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18001d999  mov     [rsp+arg_8], rdx
0x18001d99e  push    rbp
0x18001d99f  sub     rsp, 20h
0x18001d9a3  mov     rbp, rdx
0x18001d9a6  xor     r8d, r8d
0x18001d9a9  mov     dl, 1
0x18001d9ab  mov     rcx, [rbp+80h]
0x18001d9b2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001d9b7  xor     edx, edx; pThrowInfo
0x18001d9b9  xor     ecx, ecx; pExceptionObject
0x18001d9bb  call    _CxxThrowException_0
```
