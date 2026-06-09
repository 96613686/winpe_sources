# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x18001d753`
- end: `0x18001d783`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000983e`
- `0x180010188`
- `0x18001d753`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 40 )
    std::_Dest_val<std::allocator<std::wstring>,std::wstring>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18001d753  mov     [rsp+arg_8], rdx
0x18001d758  push    rbx
0x18001d759  push    rbp
0x18001d75a  sub     rsp, 28h
0x18001d75e  mov     rbp, rdx
0x18001d761  mov     rbx, [rbp+48h]
0x18001d765  jmp     short loc_18001D773
0x18001d767  mov     rdx, rbx
0x18001d76a  call    ??$_Dest_val@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@std@@YAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::_Dest_val<std::allocator<std::wstring>,std::wstring>(std::allocator<std::wstring> &,std::wstring *)
0x18001d76f  add     rbx, 28h ; '('
0x18001d773  cmp     rbx, [rbp+40h]
0x18001d777  jnz     short loc_18001D767
0x18001d779  xor     edx, edx; pThrowInfo
0x18001d77b  xor     ecx, ecx; pExceptionObject
0x18001d77d  call    _CxxThrowException_0
```
