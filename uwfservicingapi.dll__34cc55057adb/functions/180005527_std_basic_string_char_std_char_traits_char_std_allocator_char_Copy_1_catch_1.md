# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180005527`
- end: `0x18000556b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001a38`
- `0x180001c18`
- `0x180001d78`
- `0x180005527`

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
  return &loc_180001CA1;
}

```

## disassembly

```asm
0x180005527  mov     [rsp+arg_8], rdx
0x18000552c  push    rbp
0x18000552d  sub     rsp, 20h
0x180005531  mov     rbp, rdx
0x180005534  mov     rcx, [rbp+68h]
0x180005538  mov     [rbp+68h], rcx
0x18000553c  xor     eax, eax
0x18000553e  add     rcx, 1; Size
0x180005542  jz      short loc_180005559
0x180005544  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005548  ja      short loc_180005554
0x18000554a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000554f  test    rax, rax
0x180005552  jnz     short loc_180005559
0x180005554  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005559  mov     [rbp+78h], rax
0x18000555d  lea     rax, loc_180001CA1
0x180005564  add     rsp, 20h
0x180005568  pop     rbp
0x180005569  retn
```
