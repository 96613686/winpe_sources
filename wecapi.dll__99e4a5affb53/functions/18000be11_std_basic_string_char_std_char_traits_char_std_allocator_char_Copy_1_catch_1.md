# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000be11`
- end: `0x18000be58`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800012d8`
- `0x18000262c`
- `0x18000be11`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  SIZE_T v5; // rcx

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
0x18000be11  mov     [rsp+arg_8], rdx
0x18000be16  push    rbp
0x18000be17  sub     rsp, 20h
0x18000be1b  mov     rbp, rdx
0x18000be1e  mov     rcx, [rbp+58h]
0x18000be22  mov     [rbp+58h], rcx
0x18000be26  xor     eax, eax
0x18000be28  add     rcx, 1; dwBytes
0x18000be2c  jz      short loc_18000BE43
0x18000be2e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000be32  ja      short loc_18000BE3E
0x18000be34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000be39  test    rax, rax
0x18000be3c  jnz     short loc_18000BE43
0x18000be3e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000be43  mov     [rbp+68h], rax
0x18000be47  mov     rax, 0
0x18000be51  add     rsp, 20h
0x18000be55  pop     rbp
0x18000be56  retn
```
