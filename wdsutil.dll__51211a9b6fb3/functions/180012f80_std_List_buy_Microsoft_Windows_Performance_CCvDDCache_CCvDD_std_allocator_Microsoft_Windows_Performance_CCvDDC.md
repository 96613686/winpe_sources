# std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x180012f80`
- end: `0x180013137`
- name: `??$_Buynode@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@?$_List_buy@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@1@PEAU21@0$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
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
- `0x180012f80`
- `0x1800144f0`
- `0x1800182e4`
- `0x18001ccb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall std::_List_buy<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rbx
  unsigned int v8; // r15d
  __int64 *v9; // r12
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 result; // rax
  __int64 v13; // [rsp+60h] [rbp+8h]

  v5 = std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode0(
         a1,
         a2,
         a3);
  v6 = v5;
  v13 = v5;
  v7 = v5 + 16;
  *(_QWORD *)(v5 + 40) = 7;
  v8 = 0;
  *(_QWORD *)(v5 + 32) = 0;
  *(_WORD *)(v5 + 16) = 0;
  try
  {
    std::wstring::assign((void *)(v5 + 16));
    *(_QWORD *)(v7 + 56) = 7;
    *(_QWORD *)(v7 + 48) = 0;
    *(_WORD *)(v7 + 32) = 0;
    std::wstring::assign((void *)(v7 + 32));
    *(_DWORD *)(v7 + 64) = *(_DWORD *)(a4 + 64);
    *(_QWORD *)(v7 + 72) = 0;
    v9 = (__int64 *)(v7 + 80);
    *(_QWORD *)(v7 + 80) = 0;
    *(_QWORD *)(v7 + 88) = 0;
    std::vector<unsigned char>::vector<unsigned char>(v7 + 96, a4 + 96);
    *(_WORD *)(v7 + 120) = *(_WORD *)(a4 + 120);
    *(_WORD *)(v7 + 122) = *(_WORD *)(a4 + 122);
    *(_BYTE *)(v7 + 124) = *(_BYTE *)(a4 + 124);
    *(_DWORD *)(v7 + 128) = *(_DWORD *)(a4 + 128);
    *(_DWORD *)(v7 + 132) = *(_DWORD *)(a4 + 132);
    *(_DWORD *)(v7 + 136) = *(_DWORD *)(a4 + 136);
    if ( *(_DWORD *)(v7 + 64) )
    {
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(v7 + 72, *(unsigned int *)(v7 + 64))
        || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(v7 + 80, *(unsigned int *)(v7 + 64))
        || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(v7 + 88, *(unsigned int *)(v7 + 64)) )
      {
        ATL::AtlThrowImpl(-2147024882);
      }
      if ( *(_DWORD *)(v7 + 64) )
      {
        do
        {
          v11 = *(_QWORD *)(a4 + 80);
          if ( *(_DWORD *)(v11 + 4LL * v8) > 0x628u )
            ATL::AtlThrowImpl(-2147418113);
          memcpy_0(
            (void *)(*(_QWORD *)(v7 + 72) + 1576LL * v8),
            (const void *)(1576LL * v8 + *(_QWORD *)(a4 + 72)),
            *(unsigned int *)(v11 + 4LL * v8));
          *(_QWORD *)(*(_QWORD *)(v7 + 88) + 8LL * v8) = *(_QWORD *)(*(_QWORD *)(a4 + 88) + 8LL * v8);
          v10 = *v9;
          *(_DWORD *)(*v9 + 4LL * v8) = *(_DWORD *)(*(_QWORD *)(a4 + 80) + 4LL * v8);
          ++v8;
        }
        while ( v8 < *(_DWORD *)(v7 + 64) );
      }
    }
    result = v6;
  }
  catch ( ... )
  {
    std::_Tree_buy<unsigned short const *>::_Freenode0(v10, v13);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180012f80  mov     rax, rsp
0x180012f83  mov     [rax+8], rcx
0x180012f87  push    rdi
0x180012f88  push    r12
0x180012f8a  push    r13
0x180012f8c  push    r14
0x180012f8e  push    r15
0x180012f90  sub     rsp, 30h
0x180012f94  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180012f9c  mov     [rax+10h], rbx
0x180012fa0  mov     [rax+18h], rsi
0x180012fa4  mov     rdi, r9
0x180012fa7  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode0(std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *,std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *> *)
0x180012fac  mov     rsi, rax
0x180012faf  mov     [rsp+58h+arg_0], rax
0x180012fb4  lea     rbx, [rax+10h]
0x180012fb8  mov     [rsp+58h+arg_18], rbx
0x180012fbd  mov     r14d, 7
0x180012fc3  mov     [rbx+18h], r14
0x180012fc7  xor     r15d, r15d
0x180012fca  mov     [rbx+10h], r15
0x180012fce  mov     [rbx], r15w
0x180012fd2  or      r12, 0FFFFFFFFFFFFFFFFh
0x180012fd6  mov     r9, r12
0x180012fd9  xor     r8d, r8d
0x180012fdc  mov     rdx, rdi
0x180012fdf  mov     rcx, rbx; void *
0x180012fe2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012fe7  nop
0x180012fe8  lea     rcx, [rbx+20h]; void *
0x180012fec  mov     [rcx+18h], r14
0x180012ff0  mov     [rcx+10h], r15
0x180012ff4  mov     [rcx], r15w
0x180012ff8  lea     rdx, [rdi+20h]
0x180012ffc  mov     r9, r12
0x180012fff  xor     r8d, r8d
0x180013002  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180013007  nop
0x180013008  mov     eax, [rdi+40h]
0x18001300b  mov     [rbx+40h], eax
0x18001300e  mov     [rbx+48h], r15
0x180013012  lea     r12, [rbx+50h]
0x180013016  mov     [r12], r15
0x18001301a  lea     r13, [rbx+58h]
0x18001301e  mov     [r13+0], r15
0x180013022  lea     rdx, [rdi+60h]
0x180013026  lea     rcx, [rbx+60h]
0x18001302a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18001302f  movzx   eax, word ptr [rdi+78h]
0x180013033  mov     [rbx+78h], ax
0x180013037  movzx   eax, word ptr [rdi+7Ah]
0x18001303b  mov     [rbx+7Ah], ax
0x18001303f  mov     al, [rdi+7Ch]
0x180013042  mov     [rbx+7Ch], al
0x180013045  mov     eax, [rdi+80h]
0x18001304b  mov     [rbx+80h], eax
0x180013051  mov     eax, [rdi+84h]
0x180013057  mov     [rbx+84h], eax
0x18001305d  mov     eax, [rdi+88h]
0x180013063  mov     [rbx+88h], eax
0x180013069  cmp     [rbx+40h], r15d
0x18001306d  jz      loc_180013104
0x180013073  mov     edx, [rbx+40h]
0x180013076  lea     rcx, [rbx+48h]
0x18001307a  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x18001307f  test    al, al
0x180013081  jz      loc_180013120
0x180013087  mov     edx, [rbx+40h]
0x18001308a  mov     rcx, r12
0x18001308d  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180013092  test    al, al
0x180013094  jz      loc_180013120
0x18001309a  mov     edx, [rbx+40h]
0x18001309d  mov     rcx, r13
0x1800130a0  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x1800130a5  test    al, al
0x1800130a7  jz      short loc_180013120
0x1800130a9  cmp     [rbx+40h], r15d
0x1800130ad  jbe     short loc_180013104
0x1800130af  mov     r14d, r15d
0x1800130b2  mov     rax, [rdi+50h]
0x1800130b6  cmp     dword ptr [rax+r14*4], 628h
0x1800130be  ja      short loc_18001312B
0x1800130c0  imul    rcx, r14, 628h
0x1800130c7  mov     r8d, [rax+r14*4]; Size
0x1800130cb  mov     rdx, [rdi+48h]
0x1800130cf  add     rdx, rcx; Src
0x1800130d2  add     rcx, [rbx+48h]; void *
0x1800130d6  call    memcpy_0
0x1800130db  mov     rax, [rdi+58h]
0x1800130df  mov     rcx, [r13+0]
0x1800130e3  mov     rax, [rax+r14*8]
0x1800130e7  mov     [rcx+r14*8], rax
0x1800130eb  mov     rax, [rdi+50h]
0x1800130ef  mov     rcx, [r12]
0x1800130f3  mov     eax, [rax+r14*4]
0x1800130f7  mov     [rcx+r14*4], eax
0x1800130fb  inc     r15d
0x1800130fe  cmp     r15d, [rbx+40h]
0x180013102  jb      short loc_1800130AF
0x180013104  mov     rax, rsi
0x180013107  mov     rbx, [rsp+58h+arg_8]
0x18001310c  mov     rsi, [rsp+58h+arg_10]
0x180013111  add     rsp, 30h
0x180013115  pop     r15
0x180013117  pop     r14
0x180013119  pop     r13
0x18001311b  pop     r12
0x18001311d  pop     rdi
0x18001311e  retn
0x180013120  mov     ecx, 8007000Eh; int
0x180013125  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001312b  mov     ecx, 8000FFFFh; int
0x180013130  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
