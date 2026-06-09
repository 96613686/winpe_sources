# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000c607`
- end: `0x18000c65a`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800012d8`
- `0x18000262c`
- `0x18000c607`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000c607  mov     [rsp+arg_8], rdx
0x18000c60c  push    rbp
0x18000c60d  sub     rsp, 20h
0x18000c611  mov     rbp, rdx
0x18000c614  mov     rcx, [rbp+58h]
0x18000c618  mov     [rbp+58h], rcx
0x18000c61c  xor     eax, eax
0x18000c61e  add     rcx, 1
0x18000c622  jz      short loc_18000C645
0x18000c624  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c62e  cmp     rcx, rax
0x18000c631  ja      short loc_18000C640
0x18000c633  add     rcx, rcx; dwBytes
0x18000c636  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c63b  test    rax, rax
0x18000c63e  jnz     short loc_18000C645
0x18000c640  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c645  mov     [rbp+68h], rax
0x18000c649  mov     rax, 0
0x18000c653  add     rsp, 20h
0x18000c657  pop     rbp
0x18000c658  retn
```
