# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x18000c424`
- end: `0x18000c454`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001aac`
- `0x180003140`
- `0x18000c424`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 32 )
    std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18000c424  mov     [rsp+arg_8], rdx
0x18000c429  push    rbx
0x18000c42a  push    rbp
0x18000c42b  sub     rsp, 28h
0x18000c42f  mov     rbp, rdx
0x18000c432  mov     rbx, [rbp+48h]
0x18000c436  jmp     short loc_18000C444
0x18000c438  mov     rdx, rbx
0x18000c43b  call    ??$destroy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(std::wstring *)
0x18000c440  add     rbx, 20h ; ' '
0x18000c444  cmp     rbx, [rbp+40h]
0x18000c448  jnz     short loc_18000C438
0x18000c44a  xor     edx, edx; pThrowInfo
0x18000c44c  xor     ecx, ecx; pExceptionObject
0x18000c44e  call    _CxxThrowException_0
```
