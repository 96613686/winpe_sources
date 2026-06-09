# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001a323`
- end: `0x18001a367`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002c54`
- `0x180002e38`
- `0x180002f98`
- `0x18001a323`

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
  return &loc_180002EC1;
}

```

## disassembly

```asm
0x18001a323  mov     [rsp+arg_8], rdx
0x18001a328  push    rbp
0x18001a329  sub     rsp, 20h
0x18001a32d  mov     rbp, rdx
0x18001a330  mov     rcx, [rbp+68h]
0x18001a334  mov     [rbp+68h], rcx
0x18001a338  xor     eax, eax
0x18001a33a  add     rcx, 1; Size
0x18001a33e  jz      short loc_18001A355
0x18001a340  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a344  ja      short loc_18001A350
0x18001a346  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a34b  test    rax, rax
0x18001a34e  jnz     short loc_18001A355
0x18001a350  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001a355  mov     [rbp+78h], rax
0x18001a359  lea     rax, loc_180002EC1
0x18001a360  add     rsp, 20h
0x18001a364  pop     rbp
0x18001a365  retn
```
