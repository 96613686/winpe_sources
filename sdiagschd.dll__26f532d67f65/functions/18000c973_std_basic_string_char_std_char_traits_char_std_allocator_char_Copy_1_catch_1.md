# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000c973`
- end: `0x18000c9b7`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001174`
- `0x180001358`
- `0x1800014b8`
- `0x18000c973`

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
  return &loc_1800013E1;
}

```

## disassembly

```asm
0x18000c973  mov     [rsp+arg_8], rdx
0x18000c978  push    rbp
0x18000c979  sub     rsp, 20h
0x18000c97d  mov     rbp, rdx
0x18000c980  mov     rcx, [rbp+68h]
0x18000c984  mov     [rbp+68h], rcx
0x18000c988  xor     eax, eax
0x18000c98a  add     rcx, 1; Size
0x18000c98e  jz      short loc_18000C9A5
0x18000c990  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000c994  ja      short loc_18000C9A0
0x18000c996  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c99b  test    rax, rax
0x18000c99e  jnz     short loc_18000C9A5
0x18000c9a0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c9a5  mov     [rbp+78h], rax
0x18000c9a9  lea     rax, loc_1800013E1
0x18000c9b0  add     rsp, 20h
0x18000c9b4  pop     rbp
0x18000c9b5  retn
```
