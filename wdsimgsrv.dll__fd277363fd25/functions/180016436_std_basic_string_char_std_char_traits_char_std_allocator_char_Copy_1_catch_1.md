# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180016436`
- end: `0x18001647a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001bc8`
- `0x180001da8`
- `0x180001f08`
- `0x180016436`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_180001E31;
}

```

## disassembly

```asm
0x180016436  mov     [rsp+arg_8], rdx
0x18001643b  push    rbp
0x18001643c  sub     rsp, 20h
0x180016440  mov     rbp, rdx
0x180016443  mov     rcx, [rbp+68h]
0x180016447  mov     [rbp+68h], rcx
0x18001644b  xor     eax, eax
0x18001644d  add     rcx, 1; Size
0x180016451  jz      short loc_180016468
0x180016453  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016457  ja      short loc_180016463
0x180016459  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001645e  test    rax, rax
0x180016461  jnz     short loc_180016468
0x180016463  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180016468  mov     [rbp+78h], rax
0x18001646c  lea     rax, loc_180001E31
0x180016473  add     rsp, 20h
0x180016477  pop     rbp
0x180016478  retn
```
