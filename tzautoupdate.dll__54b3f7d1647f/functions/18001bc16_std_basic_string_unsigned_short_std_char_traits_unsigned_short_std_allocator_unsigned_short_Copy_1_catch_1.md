# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18001bc16`
- end: `0x18001bc69`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002050`
- `0x1800021f8`
- `0x18001bc16`

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
0x18001bc16  mov     [rsp+arg_8], rdx
0x18001bc1b  push    rbp
0x18001bc1c  sub     rsp, 20h
0x18001bc20  mov     rbp, rdx
0x18001bc23  mov     rcx, [rbp+58h]
0x18001bc27  mov     [rbp+58h], rcx
0x18001bc2b  xor     eax, eax
0x18001bc2d  add     rcx, 1
0x18001bc31  jz      short loc_18001BC54
0x18001bc33  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001bc3d  cmp     rcx, rax
0x18001bc40  ja      short loc_18001BC4F
0x18001bc42  add     rcx, rcx; Size
0x18001bc45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bc4a  test    rax, rax
0x18001bc4d  jnz     short loc_18001BC54
0x18001bc4f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001bc54  mov     [rbp+68h], rax
0x18001bc58  mov     rax, 0
0x18001bc62  add     rsp, 20h
0x18001bc66  pop     rbp
0x18001bc67  retn
```
