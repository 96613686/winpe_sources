# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x140007d60`
- end: `0x140007e65`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008038`
- `0x140008334`

## callees

- `0x1400023fc`
- `0x140007d60`
- `0x14000a1d8`
- `0x14000a2dc`
- `0x14000ac74`

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
0x140007d60  push    rbx
0x140007d62  push    rsi
0x140007d63  push    rdi
0x140007d64  push    r14
0x140007d66  sub     rsp, 28h
0x140007d6a  xorps   xmm0, xmm0
0x140007d6d  mov     rbx, rcx
0x140007d70  movups  xmmword ptr [rcx], xmm0
0x140007d73  mov     qword ptr [rcx+10h], 0
0x140007d7b  mov     r14, rdx
0x140007d7e  mov     qword ptr [rcx+18h], 0
0x140007d86  mov     ecx, 0Fh
0x140007d8b  mov     rsi, [rdx+10h]
0x140007d8f  cmp     [rdx+18h], rcx
0x140007d93  jbe     short loc_140007D98
0x140007d95  mov     r14, [rdx]
0x140007d98  mov     rdi, 7FFFFFFFFFFFFFFFh
0x140007da2  cmp     rsi, rdi
0x140007da5  ja      loc_140007E59
0x140007dab  cmp     rsi, rcx
0x140007dae  ja      short loc_140007DC5
0x140007db0  mov     [rbx+10h], rsi
0x140007db4  mov     [rbx+18h], rcx
0x140007db8  movups  xmm0, xmmword ptr [r14]
0x140007dbc  movdqu  xmmword ptr [rbx], xmm0
0x140007dc0  jmp     loc_140007E4C
0x140007dc5  mov     rax, rsi
0x140007dc8  or      rax, rcx
0x140007dcb  cmp     rax, rdi
0x140007dce  jbe     short loc_140007DEF
0x140007dd0  mov     rax, 8000000000000027h
0x140007dda  mov     rcx, rax; Size
0x140007ddd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007de2  mov     rcx, rax
0x140007de5  test    rax, rax
0x140007de8  jnz     short loc_140007E1F
0x140007dea  lea     ecx, [rax+5]
0x140007ded  int     29h; Win8: RtlFailFast(ecx)
0x140007def  mov     ecx, 16h
0x140007df4  mov     rdi, rax
0x140007df7  cmp     rax, rcx
0x140007dfa  cmovb   rdi, rcx
0x140007dfe  lea     rcx, [rdi+1]; Size
0x140007e02  test    rcx, rcx
0x140007e05  jnz     short loc_140007E0B
0x140007e07  xor     eax, eax
0x140007e09  jmp     short loc_140007E32
0x140007e0b  cmp     rcx, 1000h
0x140007e12  jb      short loc_140007E2D
0x140007e14  lea     rax, [rcx+27h]
0x140007e18  cmp     rax, rcx
0x140007e1b  jbe     short loc_140007E5F
0x140007e1d  jmp     short loc_140007DDA
0x140007e1f  add     rax, 27h ; '''
0x140007e23  and     rax, 0FFFFFFFFFFFFFFE0h
0x140007e27  mov     [rax-8], rcx
0x140007e2b  jmp     short loc_140007E32
0x140007e2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007e32  lea     r8, [rsi+1]; Size
0x140007e36  mov     [rbx], rax
0x140007e39  mov     rdx, r14; Src
0x140007e3c  mov     [rbx+10h], rsi
0x140007e40  mov     rcx, rax; void *
0x140007e43  mov     [rbx+18h], rdi
0x140007e47  call    memcpy_0
0x140007e4c  mov     rax, rbx
0x140007e4f  add     rsp, 28h
0x140007e53  pop     r14
0x140007e55  pop     rdi
0x140007e56  pop     rsi
0x140007e57  pop     rbx
0x140007e58  retn
0x140007e59  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140007e5f  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
