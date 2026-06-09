# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18001c474`
- end: `0x18001c4c7`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800011d0`
- `0x180001378`
- `0x18001c474`

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
0x18001c474  mov     [rsp+arg_8], rdx
0x18001c479  push    rbp
0x18001c47a  sub     rsp, 20h
0x18001c47e  mov     rbp, rdx
0x18001c481  mov     rcx, [rbp+58h]
0x18001c485  mov     [rbp+58h], rcx
0x18001c489  xor     eax, eax
0x18001c48b  add     rcx, 1
0x18001c48f  jz      short loc_18001C4B2
0x18001c491  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001c49b  cmp     rcx, rax
0x18001c49e  ja      short loc_18001C4AD
0x18001c4a0  add     rcx, rcx; Size
0x18001c4a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c4a8  test    rax, rax
0x18001c4ab  jnz     short loc_18001C4B2
0x18001c4ad  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001c4b2  mov     [rbp+68h], rax
0x18001c4b6  mov     rax, 0
0x18001c4c0  add     rsp, 20h
0x18001c4c4  pop     rbp
0x18001c4c5  retn
```
