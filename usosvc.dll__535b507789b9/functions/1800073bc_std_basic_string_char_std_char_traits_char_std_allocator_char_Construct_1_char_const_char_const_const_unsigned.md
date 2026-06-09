# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x1800073bc`
- end: `0x1800074a6`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800081b0`
- `0x18000a700`
- `0x18000a750`

## callees

- `0x180002adc`
- `0x1800073bc`
- `0x18000a244`
- `0x18000a348`
- `0x18000e454`

## pseudocode

```c
void *__fastcall std::string::_Construct<1,char const *>(_QWORD *a1, const void *a2, size_t a3)
{
  __int64 v3; // rsi
  void *result; // rax
  size_t v8; // rax
  void *v9; // rax
  size_t v10; // rcx
  _QWORD *v11; // rdi

  v3 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( a3 <= 0xF )
  {
    a1[2] = a3;
    a1[3] = 15;
    result = memcpy_0(a1, a2, a3);
    *((_BYTE *)a1 + a3) = 0;
    return result;
  }
  if ( (a3 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = 0x8000000000000027uLL;
LABEL_6:
    v9 = operator new(v8);
    if ( !v9 )
      __fastfail(5u);
    v11 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v11 - 1) = v9;
    goto LABEL_17;
  }
  v3 = a3 | 0xF;
  if ( (a3 | 0xF) < 0x16 )
    v3 = 22;
  v10 = v3 + 1;
  if ( v3 == -1 )
  {
    v11 = 0;
  }
  else
  {
    if ( v10 >= 0x1000 )
    {
      v8 = v3 + 40;
      if ( v3 + 40 < (unsigned __int64)(v3 + 1) )
        __scrt_throw_std_bad_array_new_length();
      goto LABEL_6;
    }
    v11 = operator new(v10);
  }
LABEL_17:
  *a1 = v11;
  a1[2] = a3;
  a1[3] = v3;
  result = memcpy_0(v11, a2, a3);
  *((_BYTE *)v11 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800073bc  push    rbx
0x1800073be  push    rbp
0x1800073bf  push    rsi
0x1800073c0  push    rdi
0x1800073c1  push    r14
0x1800073c3  sub     rsp, 20h
0x1800073c7  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800073d1  mov     rbx, r8
0x1800073d4  mov     rbp, rdx
0x1800073d7  mov     r14, rcx
0x1800073da  cmp     r8, rsi
0x1800073dd  ja      loc_18000749A
0x1800073e3  cmp     rbx, 0Fh
0x1800073e7  ja      short loc_180007404
0x1800073e9  mov     [rcx+10h], rbx
0x1800073ed  mov     qword ptr [rcx+18h], 0Fh
0x1800073f5  call    memcpy_0
0x1800073fa  mov     byte ptr [rbx+r14], 0
0x1800073ff  jmp     loc_18000748F
0x180007404  mov     rax, rbx
0x180007407  or      rax, 0Fh
0x18000740b  cmp     rax, rsi
0x18000740e  jbe     short loc_18000742C
0x180007410  mov     rax, 8000000000000027h
0x18000741a  mov     rcx, rax; Size
0x18000741d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007422  test    rax, rax
0x180007425  jnz     short loc_18000745C
0x180007427  lea     ecx, [rax+5]
0x18000742a  int     29h; Win8: RtlFailFast(ecx)
0x18000742c  mov     ecx, 16h
0x180007431  mov     rsi, rax
0x180007434  cmp     rax, rcx
0x180007437  cmovb   rsi, rcx
0x18000743b  lea     rcx, [rsi+1]; Size
0x18000743f  test    rcx, rcx
0x180007442  jnz     short loc_180007448
0x180007444  xor     edi, edi
0x180007446  jmp     short loc_180007472
0x180007448  cmp     rcx, 1000h
0x18000744f  jb      short loc_18000746A
0x180007451  lea     rax, [rcx+27h]
0x180007455  cmp     rax, rcx
0x180007458  jbe     short loc_1800074A0
0x18000745a  jmp     short loc_18000741A
0x18000745c  lea     rdi, [rax+27h]
0x180007460  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180007464  mov     [rdi-8], rax
0x180007468  jmp     short loc_180007472
0x18000746a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000746f  mov     rdi, rax
0x180007472  mov     r8, rbx; Size
0x180007475  mov     [r14], rdi
0x180007478  mov     rdx, rbp; Src
0x18000747b  mov     [r14+10h], rbx
0x18000747f  mov     rcx, rdi; void *
0x180007482  mov     [r14+18h], rsi
0x180007486  call    memcpy_0
0x18000748b  mov     byte ptr [rdi+rbx], 0
0x18000748f  add     rsp, 20h
0x180007493  pop     r14
0x180007495  pop     rdi
0x180007496  pop     rsi
0x180007497  pop     rbp
0x180007498  pop     rbx
0x180007499  retn
0x18000749a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800074a0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
