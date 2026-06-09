# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000f73c`
- end: `0x18000f783`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x18000f73c`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x18000f73c  mov     [rsp+arg_8], rdx
0x18000f741  push    rbp
0x18000f742  sub     rsp, 20h
0x18000f746  mov     rbp, rdx
0x18000f749  mov     rcx, [rbp+58h]
0x18000f74d  mov     [rbp+58h], rcx
0x18000f751  xor     eax, eax
0x18000f753  add     rcx, 1; Size
0x18000f757  jz      short loc_18000F76E
0x18000f759  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f75d  ja      short loc_18000F769
0x18000f75f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f764  test    rax, rax
0x18000f767  jnz     short loc_18000F76E
0x18000f769  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000f76e  mov     [rbp+68h], rax
0x18000f772  mov     rax, 0
0x18000f77c  add     rsp, 20h
0x18000f780  pop     rbp
0x18000f781  retn
```
