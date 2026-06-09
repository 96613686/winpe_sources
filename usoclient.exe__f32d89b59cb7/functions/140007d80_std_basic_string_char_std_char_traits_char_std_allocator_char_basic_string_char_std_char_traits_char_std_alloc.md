# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x140007d80`
- end: `0x140007e85`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008058`
- `0x140008354`

## callees

- `0x1400023ec`
- `0x140007d80`
- `0x14000a1a8`
- `0x14000a2ac`
- `0x14000ac54`

## pseudocode

```c
__int64 __fastcall std::string::string(__int64 a1, __int64 a2)
{
  _OWORD *v3; // r14
  unsigned __int64 v4; // rsi
  __int64 v5; // rdi
  size_t v6; // rax
  void *v7; // rax
  void *v8; // rcx
  size_t v9; // rcx
  _QWORD *v10; // rax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 0xFu )
    v3 = *(_OWORD **)a2;
  v5 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v4 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( v4 > 0xF )
  {
    if ( (v4 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
    {
      v6 = 0x8000000000000027uLL;
LABEL_8:
      v7 = operator new(v6);
      v8 = v7;
      if ( !v7 )
        __fastfail(5u);
      v10 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v10 - 1) = v8;
      goto LABEL_19;
    }
    v5 = v4 | 0xF;
    if ( (v4 | 0xF) < 0x16 )
      v5 = 22;
    v9 = v5 + 1;
    if ( v5 == -1 )
    {
      v10 = 0;
    }
    else
    {
      if ( v9 >= 0x1000 )
      {
        v6 = v5 + 40;
        if ( v5 + 40 < (unsigned __int64)(v5 + 1) )
          __scrt_throw_std_bad_array_new_length();
        goto LABEL_8;
      }
      v10 = operator new(v9);
    }
LABEL_19:
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = v5;
    memcpy_0(v10, v3, v4 + 1);
    return a1;
  }
  *(_QWORD *)(a1 + 16) = v4;
  *(_QWORD *)(a1 + 24) = 15;
  *(_OWORD *)a1 = *v3;
  return a1;
}

```

## disassembly

```asm
0x140007d80  push    rbx
0x140007d82  push    rsi
0x140007d83  push    rdi
0x140007d84  push    r14
0x140007d86  sub     rsp, 28h
0x140007d8a  xorps   xmm0, xmm0
0x140007d8d  mov     rbx, rcx
0x140007d90  movups  xmmword ptr [rcx], xmm0
0x140007d93  mov     qword ptr [rcx+10h], 0
0x140007d9b  mov     r14, rdx
0x140007d9e  mov     qword ptr [rcx+18h], 0
0x140007da6  mov     ecx, 0Fh
0x140007dab  mov     rsi, [rdx+10h]
0x140007daf  cmp     [rdx+18h], rcx
0x140007db3  jbe     short loc_140007DB8
0x140007db5  mov     r14, [rdx]
0x140007db8  mov     rdi, 7FFFFFFFFFFFFFFFh
0x140007dc2  cmp     rsi, rdi
0x140007dc5  ja      loc_140007E79
0x140007dcb  cmp     rsi, rcx
0x140007dce  ja      short loc_140007DE5
0x140007dd0  mov     [rbx+10h], rsi
0x140007dd4  mov     [rbx+18h], rcx
0x140007dd8  movups  xmm0, xmmword ptr [r14]
0x140007ddc  movdqu  xmmword ptr [rbx], xmm0
0x140007de0  jmp     loc_140007E6C
0x140007de5  mov     rax, rsi
0x140007de8  or      rax, rcx
0x140007deb  cmp     rax, rdi
0x140007dee  jbe     short loc_140007E0F
0x140007df0  mov     rax, 8000000000000027h
0x140007dfa  mov     rcx, rax; Size
0x140007dfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007e02  mov     rcx, rax
0x140007e05  test    rax, rax
0x140007e08  jnz     short loc_140007E3F
0x140007e0a  lea     ecx, [rax+5]
0x140007e0d  int     29h; Win8: RtlFailFast(ecx)
0x140007e0f  mov     ecx, 16h
0x140007e14  mov     rdi, rax
0x140007e17  cmp     rax, rcx
0x140007e1a  cmovb   rdi, rcx
0x140007e1e  lea     rcx, [rdi+1]; Size
0x140007e22  test    rcx, rcx
0x140007e25  jnz     short loc_140007E2B
0x140007e27  xor     eax, eax
0x140007e29  jmp     short loc_140007E52
0x140007e2b  cmp     rcx, 1000h
0x140007e32  jb      short loc_140007E4D
0x140007e34  lea     rax, [rcx+27h]
0x140007e38  cmp     rax, rcx
0x140007e3b  jbe     short loc_140007E7F
0x140007e3d  jmp     short loc_140007DFA
0x140007e3f  add     rax, 27h ; '''
0x140007e43  and     rax, 0FFFFFFFFFFFFFFE0h
0x140007e47  mov     [rax-8], rcx
0x140007e4b  jmp     short loc_140007E52
0x140007e4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007e52  lea     r8, [rsi+1]; Size
0x140007e56  mov     [rbx], rax
0x140007e59  mov     rdx, r14; Src
0x140007e5c  mov     [rbx+10h], rsi
0x140007e60  mov     rcx, rax; void *
0x140007e63  mov     [rbx+18h], rdi
0x140007e67  call    memcpy_0
0x140007e6c  mov     rax, rbx
0x140007e6f  add     rsp, 28h
0x140007e73  pop     r14
0x140007e75  pop     rdi
0x140007e76  pop     rsi
0x140007e77  pop     rbx
0x140007e78  retn
0x140007e79  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140007e7f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
