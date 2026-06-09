# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000db76`
- end: `0x18000dbba`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001cf8`
- `0x180001ed8`
- `0x180002038`
- `0x18000db76`

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
  return &loc_180001F61;
}

```

## disassembly

```asm
0x18000db76  mov     [rsp+arg_8], rdx
0x18000db7b  push    rbp
0x18000db7c  sub     rsp, 20h
0x18000db80  mov     rbp, rdx
0x18000db83  mov     rcx, [rbp+68h]
0x18000db87  mov     [rbp+68h], rcx
0x18000db8b  xor     eax, eax
0x18000db8d  add     rcx, 1; Size
0x18000db91  jz      short loc_18000DBA8
0x18000db93  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000db97  ja      short loc_18000DBA3
0x18000db99  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db9e  test    rax, rax
0x18000dba1  jnz     short loc_18000DBA8
0x18000dba3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000dba8  mov     [rbp+78h], rax
0x18000dbac  lea     rax, loc_180001F61
0x18000dbb3  add     rsp, 20h
0x18000dbb7  pop     rbp
0x18000dbb8  retn
```
