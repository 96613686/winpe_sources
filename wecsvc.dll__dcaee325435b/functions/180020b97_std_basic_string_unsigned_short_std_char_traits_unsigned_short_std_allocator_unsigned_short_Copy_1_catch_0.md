# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x180020b97`
- end: `0x180020bbc`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000195c`
- `0x1800062d4`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::wstring::_Tidy(*(_QWORD **)(a2 + 80), 1, 0);
  throw;
}

```

## disassembly

```asm
0x180020b97  mov     [rsp+arg_8], rdx
0x180020b9c  push    rbp
0x180020b9d  sub     rsp, 20h
0x180020ba1  mov     rbp, rdx
0x180020ba4  xor     r8d, r8d
0x180020ba7  mov     dl, 1
0x180020ba9  mov     rcx, [rbp+50h]
0x180020bad  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020bb2  xor     edx, edx; pThrowInfo
0x180020bb4  xor     ecx, ecx; pExceptionObject
0x180020bb6  call    _CxxThrowException_0
```
