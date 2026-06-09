# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1

- ea: `0x18000f1f7`
- end: `0x18000f24a`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x18000f1f7`

## pseudocode

```c
__int64 __fastcall std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___::_Copy_::_1_::catch_1(
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
0x18000f1f7  mov     [rsp+arg_8], rdx
0x18000f1fc  push    rbp
0x18000f1fd  sub     rsp, 20h
0x18000f201  mov     rbp, rdx
0x18000f204  mov     rcx, [rbp+58h]
0x18000f208  mov     [rbp+58h], rcx
0x18000f20c  xor     eax, eax
0x18000f20e  add     rcx, 1
0x18000f212  jz      short loc_18000F235
0x18000f214  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000f21e  cmp     rcx, rax
0x18000f221  ja      short loc_18000F230
0x18000f223  add     rcx, rcx; Size
0x18000f226  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f22b  test    rax, rax
0x18000f22e  jnz     short loc_18000F235
0x18000f230  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000f235  mov     [rbp+68h], rax
0x18000f239  mov     rax, 0
0x18000f243  add     rsp, 20h
0x18000f247  pop     rbp
0x18000f248  retn
```
