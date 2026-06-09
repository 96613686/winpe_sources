# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x1800204bc`
- end: `0x1800204ec`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000195c`
- `0x180003dec`
- `0x1800204bc`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 32 )
    std::wstring::`scalar deleting destructor'(i);
  throw;
}

```

## disassembly

```asm
0x1800204bc  mov     [rsp+arg_8], rdx
0x1800204c1  push    rbx
0x1800204c2  push    rbp
0x1800204c3  sub     rsp, 28h
0x1800204c7  mov     rbp, rdx
0x1800204ca  mov     rbx, [rbp+48h]
0x1800204ce  jmp     short loc_1800204DC
0x1800204d0  mov     rcx, rbx
0x1800204d3  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x1800204d8  add     rbx, 20h ; ' '
0x1800204dc  cmp     rbx, [rbp+40h]
0x1800204e0  jnz     short loc_1800204D0
0x1800204e2  xor     edx, edx; pThrowInfo
0x1800204e4  xor     ecx, ecx; pExceptionObject
0x1800204e6  call    _CxxThrowException_0
```
