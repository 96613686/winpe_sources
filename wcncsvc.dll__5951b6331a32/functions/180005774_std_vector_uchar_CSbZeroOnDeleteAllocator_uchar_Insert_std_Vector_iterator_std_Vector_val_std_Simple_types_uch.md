# std::vector<uchar,CSbZeroOnDeleteAllocator<uchar>>::_Insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::forward_iterator_tag)

- ea: `0x180005774`
- end: `0x1800058d5`
- name: `??$_Insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@@?$vector@EV?$CSbZeroOnDeleteAllocator@E@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@1Uforward_iterator_tag@1@@Z`
- size: `353`
- prototype: `void __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180005720`
- `0x18000aa8c`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180005774`
- `0x1800058dc`
- `0x180005900`
- `0x180005924`
- `0x180007670`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005877`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005877`

## pseudocode

```c
void __fastcall std::vector<unsigned char,CSbZeroOnDeleteAllocator<unsigned char>>::_Insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v8; // r15
  __int64 v9; // r8
  _BYTE *v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // r10
  size_t v13; // r13
  char *v14; // r12
  __int64 v15; // rcx
  _BYTE *v16; // rcx
  __int64 v17; // r15
  __int64 v18; // rax
  _BYTE *i; // rdx
  char *v20; // [rsp+70h] [rbp+18h]

  v8 = a4 - a3;
  if ( a4 != a3 )
  {
    v9 = a1[1];
    if ( a1[2] - v9 >= v8 )
    {
      std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(
        a3,
        a4);
      std::rotate<unsigned char *>(a2, a1[1], a1[1] + v8);
      a1[1] += v8;
    }
    else
    {
      v10 = (_BYTE *)*a1;
      v11 = v9 - *a1;
      if ( ~v11 < v8 )
        std::vector<CWcnEapSession *>::_Xlen();
      v12 = a1[2] - (_QWORD)v10;
      v13 = 0;
      if ( ~(v12 >> 1) >= v12 )
        v13 = v12 + (v12 >> 1);
      if ( v13 < v11 + v8 )
        v13 = v11 + v8;
      v14 = 0;
      v20 = 0;
      if ( v13 )
      {
        v14 = (char *)operator new(v13);
        v20 = v14;
        if ( !v14 )
          std::_Xbad_alloc();
        v10 = (_BYTE *)*a1;
      }
      try
      {
        std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(v10, a2);
        std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(
          a3,
          a4);
        std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(a2, a1[1]);
      }
      catch ( ... )
      {
        std::_Wrap_alloc<CSbZeroOnDeleteAllocator<unsigned char>>::deallocate(v15, v20, v13);
        throw;
      }
      v16 = (_BYTE *)*a1;
      v17 = a1[1] + v8 - *a1;
      if ( *a1 )
      {
        v18 = a1[2] - (_QWORD)v16;
        for ( i = (_BYTE *)*a1; v18; --v18 )
          *i++ = 0;
        operator delete(v16);
      }
      a1[2] = &v14[v13];
      a1[1] = &v14[v17];
      *a1 = v14;
    }
  }
}

```

## disassembly

```asm
0x180005774  mov     [rsp+arg_0], rbx
0x180005779  mov     [rsp+arg_8], rsi
0x18000577e  push    rdi
0x18000577f  push    r12
0x180005781  push    r13
0x180005783  push    r14
0x180005785  push    r15
0x180005787  sub     rsp, 30h
0x18000578b  mov     rbx, r9
0x18000578e  mov     rdi, r8
0x180005791  mov     rsi, rdx
0x180005794  mov     r14, rcx
0x180005797  mov     r15, r9
0x18000579a  sub     r15, r8
0x18000579d  jz      loc_1800058B1
0x1800057a3  mov     r8, [rcx+8]
0x1800057a7  mov     r10, [rcx+10h]
0x1800057ab  mov     rax, r10
0x1800057ae  sub     rax, r8
0x1800057b1  cmp     rax, r15
0x1800057b4  jnb     loc_180005892
0x1800057ba  mov     r9, [rcx]
0x1800057bd  sub     r8, r9
0x1800057c0  mov     rax, r8
0x1800057c3  not     rax
0x1800057c6  cmp     rax, r15
0x1800057c9  jb      loc_1800058C9
0x1800057cf  lea     rdx, [r8+r15]
0x1800057d3  sub     r10, r9
0x1800057d6  mov     rax, r10
0x1800057d9  shr     rax, 1
0x1800057dc  mov     rcx, rax
0x1800057df  not     rcx
0x1800057e2  add     rax, r10
0x1800057e5  xor     r13d, r13d
0x1800057e8  cmp     rcx, r10
0x1800057eb  cmovnb  r13, rax
0x1800057ef  cmp     r13, rdx
0x1800057f2  cmovb   r13, rdx
0x1800057f6  mov     [rsp+58h+arg_18], r13
0x1800057fb  xor     r12d, r12d
0x1800057fe  mov     [rsp+58h+arg_10], r12
0x180005803  test    r13, r13
0x180005806  jz      short loc_180005824
0x180005808  mov     rcx, r13; Size
0x18000580b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005810  mov     r12, rax
0x180005813  mov     [rsp+58h+arg_10], rax
0x180005818  test    rax, rax
0x18000581b  jz      loc_1800058CF
0x180005821  mov     r9, [r14]
0x180005824  mov     r8, r12
0x180005827  mov     rdx, rsi
0x18000582a  mov     rcx, r9
0x18000582d  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x180005832  mov     r8, rax
0x180005835  mov     rdx, rbx
0x180005838  mov     rcx, rdi
0x18000583b  call    ??$_Uninit_copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@PEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,CSbZeroOnDeleteAllocator<uchar>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x180005840  mov     r8, rax
0x180005843  mov     rdx, [r14+8]
0x180005847  mov     rcx, rsi
0x18000584a  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000584f  nop
0x180005850  mov     rcx, [r14]
0x180005853  sub     r15, rcx
0x180005856  add     r15, [r14+8]
0x18000585a  test    rcx, rcx
0x18000585d  jz      short loc_18000587D
0x18000585f  mov     rax, [r14+10h]
0x180005863  sub     rax, rcx
0x180005866  mov     rdx, rcx
0x180005869  jz      short loc_180005877
0x18000586b  mov     byte ptr [rdx], 0
0x18000586e  inc     rdx
0x180005871  sub     rax, 1
0x180005875  jnz     short loc_18000586B
0x180005877  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000587d  lea     rax, [r12+r13]
0x180005881  mov     [r14+10h], rax
0x180005885  lea     rax, [r12+r15]
0x180005889  mov     [r14+8], rax
0x18000588d  mov     [r14], r12
0x180005890  jmp     short loc_1800058B1
0x180005892  mov     rdx, rbx
0x180005895  mov     rcx, rdi
0x180005898  call    ??$_Uninit_copy@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@PEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@0@0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,CSbZeroOnDeleteAllocator<uchar>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000589d  mov     rdx, [r14+8]
0x1800058a1  lea     r8, [rdx+r15]
0x1800058a5  mov     rcx, rsi
0x1800058a8  call    ??$rotate@PEAE@std@@YAPEAEPEAE00@Z; std::rotate<uchar *>(uchar *,uchar *,uchar *)
0x1800058ad  add     [r14+8], r15
0x1800058b1  mov     rbx, [rsp+58h+arg_0]
0x1800058b6  mov     rsi, [rsp+58h+arg_8]
0x1800058bb  add     rsp, 30h
0x1800058bf  pop     r15
0x1800058c1  pop     r14
0x1800058c3  pop     r13
0x1800058c5  pop     r12
0x1800058c7  pop     rdi
0x1800058c8  retn
0x1800058c9  call    ?_Xlen@?$vector@PEAVCWcnEapSession@@V?$allocator@PEAVCWcnEapSession@@@std@@@std@@IEBAXXZ; std::vector<CWcnEapSession *>::_Xlen(void)
0x1800058cf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
