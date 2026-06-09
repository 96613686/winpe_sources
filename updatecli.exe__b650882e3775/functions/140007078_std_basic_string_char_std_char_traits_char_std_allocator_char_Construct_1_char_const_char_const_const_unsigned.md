# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x140007078`
- end: `0x140007162`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007e6c`
- `0x14000a570`
- `0x14000a5c0`

## callees

- `0x1400023fc`
- `0x140007078`
- `0x14000a1d8`
- `0x14000a2dc`
- `0x14000ac74`

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
0x140007078  push    rbx
0x14000707a  push    rbp
0x14000707b  push    rsi
0x14000707c  push    rdi
0x14000707d  push    r14
0x14000707f  sub     rsp, 20h
0x140007083  mov     rsi, 7FFFFFFFFFFFFFFFh
0x14000708d  mov     rbx, r8
0x140007090  mov     rbp, rdx
0x140007093  mov     r14, rcx
0x140007096  cmp     r8, rsi
0x140007099  ja      loc_140007156
0x14000709f  cmp     rbx, 0Fh
0x1400070a3  ja      short loc_1400070C0
0x1400070a5  mov     [rcx+10h], rbx
0x1400070a9  mov     qword ptr [rcx+18h], 0Fh
0x1400070b1  call    memcpy_0
0x1400070b6  mov     byte ptr [rbx+r14], 0
0x1400070bb  jmp     loc_14000714B
0x1400070c0  mov     rax, rbx
0x1400070c3  or      rax, 0Fh
0x1400070c7  cmp     rax, rsi
0x1400070ca  jbe     short loc_1400070E8
0x1400070cc  mov     rax, 8000000000000027h
0x1400070d6  mov     rcx, rax; Size
0x1400070d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400070de  test    rax, rax
0x1400070e1  jnz     short loc_140007118
0x1400070e3  lea     ecx, [rax+5]
0x1400070e6  int     29h; Win8: RtlFailFast(ecx)
0x1400070e8  mov     ecx, 16h
0x1400070ed  mov     rsi, rax
0x1400070f0  cmp     rax, rcx
0x1400070f3  cmovb   rsi, rcx
0x1400070f7  lea     rcx, [rsi+1]; Size
0x1400070fb  test    rcx, rcx
0x1400070fe  jnz     short loc_140007104
0x140007100  xor     edi, edi
0x140007102  jmp     short loc_14000712E
0x140007104  cmp     rcx, 1000h
0x14000710b  jb      short loc_140007126
0x14000710d  lea     rax, [rcx+27h]
0x140007111  cmp     rax, rcx
0x140007114  jbe     short loc_14000715C
0x140007116  jmp     short loc_1400070D6
0x140007118  lea     rdi, [rax+27h]
0x14000711c  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140007120  mov     [rdi-8], rax
0x140007124  jmp     short loc_14000712E
0x140007126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000712b  mov     rdi, rax
0x14000712e  mov     r8, rbx; Size
0x140007131  mov     [r14], rdi
0x140007134  mov     rdx, rbp; Src
0x140007137  mov     [r14+10h], rbx
0x14000713b  mov     rcx, rdi; void *
0x14000713e  mov     [r14+18h], rsi
0x140007142  call    memcpy_0
0x140007147  mov     byte ptr [rdi+rbx], 0
0x14000714b  add     rsp, 20h
0x14000714f  pop     r14
0x140007151  pop     rdi
0x140007152  pop     rsi
0x140007153  pop     rbp
0x140007154  pop     rbx
0x140007155  retn
0x140007156  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000715c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
