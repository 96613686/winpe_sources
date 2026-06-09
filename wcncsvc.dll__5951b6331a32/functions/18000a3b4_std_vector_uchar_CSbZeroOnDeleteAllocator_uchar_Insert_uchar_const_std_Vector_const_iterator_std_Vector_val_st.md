# std::vector<uchar,CSbZeroOnDeleteAllocator<uchar>>::_Insert<uchar const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,uchar const *,std::forward_iterator_tag)

- ea: `0x18000a3b4`
- end: `0x18000a515`
- name: `??$_Insert@PEBE@?$vector@EV?$CSbZeroOnDeleteAllocator@E@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE1Uforward_iterator_tag@1@@Z`
- size: `353`
- prototype: `void __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000a994`
- `0x180044dd8`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180005900`
- `0x180005924`
- `0x180007670`
- `0x18000a3b4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4b7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a4b7`

## pseudocode

```c
void __fastcall std::vector<unsigned char,CSbZeroOnDeleteAllocator<unsigned char>>::_Insert<unsigned char const *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v8; // rsi
  __int64 v9; // r8
  _BYTE *v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // r10
  size_t v13; // r13
  char *v14; // r14
  _BYTE *v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rax
  _BYTE *i; // rdx

  v8 = a4 - a3;
  if ( a4 != a3 )
  {
    v9 = a1[1];
    if ( a1[2] - v9 >= v8 )
    {
      std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(a3, a4);
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
      if ( v13 )
      {
        v14 = (char *)operator new(v13);
        if ( !v14 )
          std::_Xbad_alloc();
        v10 = (_BYTE *)*a1;
      }
      std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(v10, a2);
      std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(a3, a4);
      std::_Uninit_copy<unsigned char const *,unsigned char *,CSbZeroOnDeleteAllocator<unsigned char>>(a2, a1[1]);
      v15 = (_BYTE *)*a1;
      v16 = a1[1] + v8 - *a1;
      if ( *a1 )
      {
        v17 = a1[2] - (_QWORD)v15;
        for ( i = (_BYTE *)*a1; v17; --v17 )
          *i++ = 0;
        operator delete(v15);
      }
      a1[2] = &v14[v13];
      a1[1] = &v14[v16];
      *a1 = v14;
    }
  }
}

```

## disassembly

```asm
0x18000a3b4  mov     [rsp+arg_0], rbx
0x18000a3b9  mov     [rsp+arg_8], rsi
0x18000a3be  push    rdi
0x18000a3bf  push    r12
0x18000a3c1  push    r13
0x18000a3c3  push    r14
0x18000a3c5  push    r15
0x18000a3c7  sub     rsp, 30h
0x18000a3cb  mov     r15, r9
0x18000a3ce  mov     r12, r8
0x18000a3d1  mov     rbx, rdx
0x18000a3d4  mov     rdi, rcx
0x18000a3d7  mov     rsi, r9
0x18000a3da  sub     rsi, r8
0x18000a3dd  jz      loc_18000A4F1
0x18000a3e3  mov     r8, [rcx+8]
0x18000a3e7  mov     r10, [rcx+10h]
0x18000a3eb  mov     rax, r10
0x18000a3ee  sub     rax, r8
0x18000a3f1  cmp     rax, rsi
0x18000a3f4  jnb     loc_18000A4D2
0x18000a3fa  mov     r9, [rcx]
0x18000a3fd  sub     r8, r9
0x18000a400  mov     rax, r8
0x18000a403  not     rax
0x18000a406  cmp     rax, rsi
0x18000a409  jb      loc_18000A509
0x18000a40f  lea     rdx, [r8+rsi]
0x18000a413  sub     r10, r9
0x18000a416  mov     rax, r10
0x18000a419  shr     rax, 1
0x18000a41c  mov     rcx, rax
0x18000a41f  not     rcx
0x18000a422  add     rax, r10
0x18000a425  xor     r13d, r13d
0x18000a428  cmp     rcx, r10
0x18000a42b  cmovnb  r13, rax
0x18000a42f  cmp     r13, rdx
0x18000a432  cmovb   r13, rdx
0x18000a436  mov     [rsp+58h+arg_18], r13
0x18000a43b  xor     r14d, r14d
0x18000a43e  mov     [rsp+58h+arg_10], r14
0x18000a443  test    r13, r13
0x18000a446  jz      short loc_18000A464
0x18000a448  mov     rcx, r13; Size
0x18000a44b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a450  mov     r14, rax
0x18000a453  mov     [rsp+58h+arg_10], rax
0x18000a458  test    rax, rax
0x18000a45b  jz      loc_18000A50F
0x18000a461  mov     r9, [rdi]
0x18000a464  mov     r8, r14
0x18000a467  mov     rdx, rbx
0x18000a46a  mov     rcx, r9
0x18000a46d  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000a472  mov     r8, rax
0x18000a475  mov     rdx, r15
0x18000a478  mov     rcx, r12
0x18000a47b  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000a480  mov     r8, rax
0x18000a483  mov     rdx, [rdi+8]
0x18000a487  mov     rcx, rbx
0x18000a48a  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000a48f  nop
0x18000a490  mov     rcx, [rdi]
0x18000a493  sub     rsi, rcx
0x18000a496  add     rsi, [rdi+8]
0x18000a49a  test    rcx, rcx
0x18000a49d  jz      short loc_18000A4BD
0x18000a49f  mov     rax, [rdi+10h]
0x18000a4a3  sub     rax, rcx
0x18000a4a6  mov     rdx, rcx
0x18000a4a9  jz      short loc_18000A4B7
0x18000a4ab  mov     byte ptr [rdx], 0
0x18000a4ae  inc     rdx
0x18000a4b1  sub     rax, 1
0x18000a4b5  jnz     short loc_18000A4AB
0x18000a4b7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a4bd  lea     rax, [r14+r13]
0x18000a4c1  mov     [rdi+10h], rax
0x18000a4c5  lea     rax, [r14+rsi]
0x18000a4c9  mov     [rdi+8], rax
0x18000a4cd  mov     [rdi], r14
0x18000a4d0  jmp     short loc_18000A4F1
0x18000a4d2  mov     rdx, r15
0x18000a4d5  mov     rcx, r12
0x18000a4d8  call    ??$_Uninit_copy@PEBEPEAEV?$CSbZeroOnDeleteAllocator@E@@@std@@YAPEAEPEBE0PEAEAEAU?$_Wrap_alloc@V?$CSbZeroOnDeleteAllocator@E@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<uchar const *,uchar *,CSbZeroOnDeleteAllocator<uchar>>(uchar const *,uchar const *,uchar *,std::_Wrap_alloc<CSbZeroOnDeleteAllocator<uchar>> &,std::_Nonscalar_ptr_iterator_tag)
0x18000a4dd  mov     rdx, [rdi+8]
0x18000a4e1  lea     r8, [rdx+rsi]
0x18000a4e5  mov     rcx, rbx
0x18000a4e8  call    ??$rotate@PEAE@std@@YAPEAEPEAE00@Z; std::rotate<uchar *>(uchar *,uchar *,uchar *)
0x18000a4ed  add     [rdi+8], rsi
0x18000a4f1  mov     rbx, [rsp+58h+arg_0]
0x18000a4f6  mov     rsi, [rsp+58h+arg_8]
0x18000a4fb  add     rsp, 30h
0x18000a4ff  pop     r15
0x18000a501  pop     r14
0x18000a503  pop     r13
0x18000a505  pop     r12
0x18000a507  pop     rdi
0x18000a508  retn
0x18000a509  call    ?_Xlen@?$vector@PEAVCWcnEapSession@@V?$allocator@PEAVCWcnEapSession@@@std@@@std@@IEBAXXZ; std::vector<CWcnEapSession *>::_Xlen(void)
0x18000a50f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
