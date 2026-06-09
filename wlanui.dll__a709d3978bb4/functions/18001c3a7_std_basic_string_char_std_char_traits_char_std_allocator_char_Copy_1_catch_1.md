# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001c3a7`
- end: `0x18001c3ee`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011d0`
- `0x180001378`
- `0x18001c3a7`

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
0x18001c3a7  mov     [rsp+arg_8], rdx
0x18001c3ac  push    rbp
0x18001c3ad  sub     rsp, 20h
0x18001c3b1  mov     rbp, rdx
0x18001c3b4  mov     rcx, [rbp+58h]
0x18001c3b8  mov     [rbp+58h], rcx
0x18001c3bc  xor     eax, eax
0x18001c3be  add     rcx, 1; Size
0x18001c3c2  jz      short loc_18001C3D9
0x18001c3c4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c3c8  ja      short loc_18001C3D4
0x18001c3ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c3cf  test    rax, rax
0x18001c3d2  jnz     short loc_18001C3D9
0x18001c3d4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001c3d9  mov     [rbp+68h], rax
0x18001c3dd  mov     rax, 0
0x18001c3e7  add     rsp, 20h
0x18001c3eb  pop     rbp
0x18001c3ec  retn
```
