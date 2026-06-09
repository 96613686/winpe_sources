# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180012913`
- end: `0x180012957`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011dc`
- `0x1800013c8`
- `0x180001528`
- `0x180012913`

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
  return &loc_180001451;
}

```

## disassembly

```asm
0x180012913  mov     [rsp+arg_8], rdx
0x180012918  push    rbp
0x180012919  sub     rsp, 20h
0x18001291d  mov     rbp, rdx
0x180012920  mov     rcx, [rbp+68h]
0x180012924  mov     [rbp+68h], rcx
0x180012928  xor     eax, eax
0x18001292a  add     rcx, 1; Size
0x18001292e  jz      short loc_180012945
0x180012930  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012934  ja      short loc_180012940
0x180012936  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001293b  test    rax, rax
0x18001293e  jnz     short loc_180012945
0x180012940  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180012945  mov     [rbp+78h], rax
0x180012949  lea     rax, loc_180001451
0x180012950  add     rsp, 20h
0x180012954  pop     rbp
0x180012955  retn
```
