# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180029db7`
- end: `0x180029dfe`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001264`
- `0x180001488`
- `0x180029db7`

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
0x180029db7  mov     [rsp+arg_8], rdx
0x180029dbc  push    rbp
0x180029dbd  sub     rsp, 20h
0x180029dc1  mov     rbp, rdx
0x180029dc4  mov     rcx, [rbp+58h]
0x180029dc8  mov     [rbp+58h], rcx
0x180029dcc  xor     eax, eax
0x180029dce  add     rcx, 1; Size
0x180029dd2  jz      short loc_180029DE9
0x180029dd4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029dd8  ja      short loc_180029DE4
0x180029dda  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029ddf  test    rax, rax
0x180029de2  jnz     short loc_180029DE9
0x180029de4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180029de9  mov     [rbp+68h], rax
0x180029ded  mov     rax, 0
0x180029df7  add     rsp, 20h
0x180029dfb  pop     rbp
0x180029dfc  retn
```
