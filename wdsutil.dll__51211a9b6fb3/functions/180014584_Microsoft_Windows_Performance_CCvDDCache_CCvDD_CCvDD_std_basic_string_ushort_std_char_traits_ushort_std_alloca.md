# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x180014584`
- end: `0x1800147ce`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015e34`
- `0x180016248`

## callees

- `0x180001d66`
- `0x1800085b8`
- `0x18000a89c`
- `0x18000aadc`
- `0x180012b44`
- `0x180014584`
- `0x1800182e4`
- `0x18001cf14`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        const void **a11,
        char a12)
{
  _QWORD *v14; // r15
  void **v15; // rdi
  __int64 i; // r14
  char *v17; // rcx
  char *v18; // r8
  char *v19; // rax
  unsigned __int64 v20; // r9
  char *v21; // rax
  __int64 result; // rax
  char v23[8]; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign((void *)a1);
  *(_QWORD *)(a1 + 56) = 7;
  *(_QWORD *)(a1 + 48) = 0;
  *(_WORD *)(a1 + 32) = 0;
  std::wstring::assign((void *)(a1 + 32));
  try
  {
    *(_DWORD *)(a1 + 64) = a4;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    v14 = (_QWORD *)(a1 + 88);
    *(_QWORD *)(a1 + 88) = 0;
    v15 = (void **)(a1 + 96);
    *(_QWORD *)(a1 + 96) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_BYTE *)(a1 + 124) = a12;
    *(_DWORD *)(a1 + 128) = a8;
    *(_DWORD *)(a1 + 132) = a9;
    *(_DWORD *)(a1 + 136) = a10;
    if ( *(_DWORD *)(a1 + 64) )
    {
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(a1 + 72, *(unsigned int *)(a1 + 64))
        || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(a1 + 80, *(unsigned int *)(a1 + 64))
        || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(a1 + 88, *(unsigned int *)(a1 + 64)) )
      {
        ATL::AtlThrowImpl(-2147024882);
      }
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 64); i = (unsigned int)(i + 1) )
      {
        if ( *(_DWORD *)(a6 + 4 * i) > 0x628u )
          ATL::AtlThrowImpl(-2147418113);
        memcpy_0(
          (void *)(*(_QWORD *)(a1 + 72) + 1576LL * (unsigned int)i),
          (const void *)(1576LL * (unsigned int)i + a5),
          *(unsigned int *)(a6 + 4 * i));
        if ( a7 )
          *(_QWORD *)(*v14 + 8 * i) = *(_QWORD *)(a7 + 8 * i);
        else
          *(_QWORD *)(*v14 + 8 * i) = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 80) + 4 * i) = *(_DWORD *)(a6 + 4 * i);
      }
    }
    if ( a11 && *(_DWORD *)a11 && a11[1] )
    {
      a12 = 0;
      v17 = (char *)*v15;
      v18 = *(char **)(a1 + 104);
      v19 = &v18[-*(_QWORD *)(a1 + 96)];
      v20 = *(unsigned int *)a11;
      if ( v20 >= (unsigned __int64)v19 )
      {
        if ( v20 > (unsigned __int64)v19 )
          std::vector<unsigned char>::_Insert_n(a1 + 96, v23, v18, v20 - (_QWORD)v19, &a12);
      }
      else
      {
        v21 = &v17[v20];
        if ( &v17[v20] == v17 )
        {
          *(_QWORD *)(a1 + 104) = v17;
        }
        else if ( v21 != v18 )
        {
          *(_QWORD *)(a1 + 104) = v21;
        }
      }
      memcpy_0(*v15, a11[1], *(unsigned int *)a11);
      *(_WORD *)(a1 + 122) = *((_WORD *)a11 + 8);
      *(_WORD *)(a1 + 120) = *((_WORD *)a11 + 9);
    }
    result = a1;
  }
  catch ( std::bad_alloc )
  {
    ATL::AtlThrowImpl(-2147024882);
  }
  return result;
}

```

## disassembly

```asm
0x180014584  mov     rax, rsp
0x180014587  mov     [rax+8], rcx
0x18001458b  push    rdi
0x18001458c  push    r12
0x18001458e  push    r13
0x180014590  push    r14
0x180014592  push    r15
0x180014594  sub     rsp, 40h
0x180014598  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800145a0  mov     [rax+10h], rbx
0x1800145a4  mov     [rax+18h], rsi
0x1800145a8  mov     edi, r9d
0x1800145ab  mov     rbx, r8
0x1800145ae  mov     rsi, rcx
0x1800145b1  mov     r15d, 7
0x1800145b7  mov     [rcx+18h], r15
0x1800145bb  xor     r12d, r12d
0x1800145be  mov     [rcx+10h], r12
0x1800145c2  mov     [rcx], r12w
0x1800145c6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800145ca  mov     r9, r14
0x1800145cd  xor     r8d, r8d
0x1800145d0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800145d5  nop
0x1800145d6  lea     rcx, [rsi+20h]; void *
0x1800145da  mov     [rcx+18h], r15
0x1800145de  mov     [rcx+10h], r12
0x1800145e2  mov     [rcx], r12w
0x1800145e6  mov     r9, r14
0x1800145e9  xor     r8d, r8d
0x1800145ec  mov     rdx, rbx
0x1800145ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800145f4  nop
0x1800145f5  mov     [rsi+40h], edi
0x1800145f8  lea     rcx, [rsi+48h]
0x1800145fc  mov     [rcx], r12
0x1800145ff  mov     [rsi+50h], r12
0x180014603  lea     r15, [rsi+58h]
0x180014607  mov     [r15], r12
0x18001460a  lea     rdi, [rsi+60h]
0x18001460e  mov     [rdi], r12
0x180014611  mov     [rdi+8], r12
0x180014615  mov     [rdi+10h], r12
0x180014619  mov     al, [rsp+68h+arg_58]
0x180014620  mov     [rsi+7Ch], al
0x180014623  mov     eax, [rsp+68h+arg_38]
0x18001462a  mov     [rsi+80h], eax
0x180014630  mov     eax, [rsp+68h+arg_40]
0x180014637  mov     [rsi+84h], eax
0x18001463d  mov     eax, [rsp+68h+arg_48]
0x180014644  mov     [rsi+88h], eax
0x18001464a  cmp     [rsi+40h], r12d
0x18001464e  jz      loc_180014708
0x180014654  mov     edx, [rsi+40h]
0x180014657  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001465c  test    al, al
0x18001465e  jz      loc_1800147C3
0x180014664  mov     edx, [rsi+40h]
0x180014667  lea     rcx, [rsi+50h]
0x18001466b  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180014670  test    al, al
0x180014672  jz      loc_1800147C3
0x180014678  mov     edx, [rsi+40h]
0x18001467b  mov     rcx, r15
0x18001467e  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180014683  test    al, al
0x180014685  jz      loc_1800147C3
0x18001468b  mov     r13, [rsp+68h+arg_30]
0x180014693  mov     r12, [rsp+68h+arg_28]
0x18001469b  xor     r14d, r14d
0x18001469e  cmp     [rsi+40h], r14d
0x1800146a2  jbe     short loc_180014705
0x1800146a4  mov     ebx, r14d
0x1800146a7  cmp     dword ptr [r12+r14*4], 628h
0x1800146af  ja      loc_1800147B8
0x1800146b5  imul    rcx, rbx, 628h
0x1800146bc  mov     r8d, [r12+r14*4]; Size
0x1800146c0  mov     rdx, [rsp+68h+arg_20]
0x1800146c8  add     rdx, rcx; Src
0x1800146cb  add     rcx, [rsi+48h]; void *
0x1800146cf  call    memcpy_0
0x1800146d4  test    r13, r13
0x1800146d7  jz      short loc_1800146E7
0x1800146d9  mov     rcx, [r15]
0x1800146dc  mov     rax, [r13+r14*8+0]
0x1800146e1  mov     [rcx+r14*8], rax
0x1800146e5  jmp     short loc_1800146F0
0x1800146e7  mov     rax, [r15]
0x1800146ea  xor     ecx, ecx
0x1800146ec  mov     [rax+r14*8], rcx
0x1800146f0  mov     rcx, [rsi+50h]
0x1800146f4  mov     eax, [r12+r14*4]
0x1800146f8  mov     [rcx+r14*4], eax
0x1800146fc  inc     r14d
0x1800146ff  cmp     r14d, [rsi+40h]
0x180014703  jb      short loc_1800146A4
0x180014705  xor     r12d, r12d
0x180014708  mov     rbx, [rsp+68h+arg_50]
0x180014710  test    rbx, rbx
0x180014713  jz      loc_18001479A
0x180014719  cmp     [rbx], r12d
0x18001471c  jz      short loc_18001479A
0x18001471e  cmp     [rbx+8], r12
0x180014722  jz      short loc_18001479A
0x180014724  mov     [rsp+68h+arg_58], r12b
0x18001472c  mov     rcx, [rdi]
0x18001472f  mov     r8, [rdi+8]
0x180014733  mov     rax, r8
0x180014736  sub     rax, rcx
0x180014739  mov     r9d, [rbx]
0x18001473c  cmp     r9, rax
0x18001473f  jnb     short loc_18001475B
0x180014741  lea     rax, [r9+rcx]
0x180014745  cmp     rax, rcx
0x180014748  jnz     short loc_180014750
0x18001474a  mov     [rdi+8], rcx
0x18001474e  jmp     short loc_18001477A
0x180014750  cmp     rax, r8
0x180014753  jz      short loc_18001477A
0x180014755  mov     [rdi+8], rax
0x180014759  jmp     short loc_18001477A
0x18001475b  jbe     short loc_18001477A
0x18001475d  sub     r9, rax
0x180014760  lea     rax, [rsp+68h+arg_58]
0x180014768  mov     [rsp+68h+var_48], rax
0x18001476d  lea     rdx, [rsp+68h+var_30]
0x180014772  mov     rcx, rdi
0x180014775  call    ?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@2@_KAEBE@Z; std::vector<uchar>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,unsigned __int64,uchar const &)
0x18001477a  mov     r8d, [rbx]; Size
0x18001477d  mov     rdx, [rbx+8]; Src
0x180014781  mov     rcx, [rdi]; void *
0x180014784  call    memcpy_0
0x180014789  nop
0x18001478a  movzx   eax, word ptr [rbx+10h]
0x18001478e  mov     [rsi+7Ah], ax
0x180014792  movzx   eax, word ptr [rbx+12h]
0x180014796  mov     [rsi+78h], ax
0x18001479a  mov     rax, rsi
0x18001479d  lea     r11, [rsp+68h+var_28]
0x1800147a2  mov     rbx, [r11+38h]
0x1800147a6  mov     rsi, [r11+40h]
0x1800147aa  mov     rsp, r11
0x1800147ad  pop     r15
0x1800147af  pop     r14
0x1800147b1  pop     r13
0x1800147b3  pop     r12
0x1800147b5  pop     rdi
0x1800147b6  retn
0x1800147b8  mov     ecx, 8000FFFFh; int
0x1800147bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800147c3  mov     ecx, 8007000Eh; int
0x1800147c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
