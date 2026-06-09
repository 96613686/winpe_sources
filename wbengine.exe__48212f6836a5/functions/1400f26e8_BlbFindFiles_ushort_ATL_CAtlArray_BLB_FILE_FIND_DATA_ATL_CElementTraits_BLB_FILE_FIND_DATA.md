# BlbFindFiles(ushort *,ATL::CAtlArray<_BLB_FILE_FIND_DATA *,ATL::CElementTraits<_BLB_FILE_FIND_DATA *>> &)

- ea: `0x1400f26e8`
- end: `0x1400f2a1f`
- name: `?BlbFindFiles@@YAJPEAGAEAV?$CAtlArray@PEAU_BLB_FILE_FIND_DATA@@V?$CElementTraits@PEAU_BLB_FILE_FIND_DATA@@@ATL@@@ATL@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400f1efc`
- `0x1400f2c3c`
- `0x140103bd4`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000bfd8`
- `0x140014260`
- `0x14003c54c`
- `0x1400f26e8`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x1400f45c4`
- `0x1400f46dc`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1400f280f`
- `KERNEL32!CompareFileTime` at `0x1400f280f`
- `KERNEL32!FindClose` at `0x1400f29db`
- `KERNEL32!FindClose` at `0x1400f29db`
- `ole32!CoTaskMemAlloc` at `0x1400f2845`
- `ole32!CoTaskMemAlloc` at `0x1400f2845`
- `ole32!CoTaskMemFree` at `0x1400f2887`
- `ole32!CoTaskMemFree` at `0x1400f295b`
- `ole32!CoTaskMemFree` at `0x1400f2974`
- `ole32!CoTaskMemFree` at `0x1400f29a3`
- `ole32!CoTaskMemFree` at `0x1400f29b8`
- `ole32!CoTaskMemFree` at `0x1400f2887`
- `ole32!CoTaskMemFree` at `0x1400f295b`
- `ole32!CoTaskMemFree` at `0x1400f2974`
- `ole32!CoTaskMemFree` at `0x1400f29a3`
- `ole32!CoTaskMemFree` at `0x1400f29b8`

## string_xrefs

- `0x1400f2751`: `wszFileSearchPath`

## pseudocode

```c
__int64 __fastcall BlbFindFiles(unsigned __int16 *a1, __int64 a2)
{
  int FirstFile; // eax
  int NextFile; // esi
  PVOID *v6; // rcx
  _DWORD *v7; // rbx
  unsigned __int16 *v8; // rdi
  unsigned __int64 v9; // rsi
  bool v10; // cc
  __int64 v11; // rax
  const FILETIME **v12; // rax
  unsigned __int16 *v13; // rax
  void *v14; // rdi
  unsigned int v15; // r14d
  void ***v16; // rax
  void **v17; // rdi
  void *v18; // rcx
  unsigned __int16 *v20; // [rsp+70h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+50h] BYREF
  HANDLE hFindFile; // [rsp+88h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
  }
  v20 = 0;
  hFindFile = (HANDLE)-1LL;
  pv = 0;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x466u, "wszFileSearchPath");
  ATL::CAtlArray<_BLB_FILE_FIND_DATA *,ATL::CElementTraits<_BLB_FILE_FIND_DATA *>>::SetCount(a2, 0);
  FirstFile = BlbFindFirstFile(a1, (LPVOID *)&v20, &hFindFile, (struct _WIN32_FIND_DATAW **)&pv);
  NextFile = FirstFile;
  if ( FirstFile >= 0 )
  {
    while ( 1 )
    {
      v7 = (_DWORD *)(a2 + 8);
      v8 = v20;
      if ( !v20 )
        break;
      v9 = 0;
      v7 = (_DWORD *)(a2 + 8);
      v10 = 1;
      if ( *(_QWORD *)(a2 + 8) )
      {
        v11 = 0;
        do
        {
          v12 = (const FILETIME **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                     a2,
                                     v11);
          if ( CompareFileTime(*v12 + 1, (const FILETIME *)((char *)pv + 4)) == 1 )
            break;
          v9 = (unsigned int)(v9 + 1);
          v11 = (unsigned int)v9;
        }
        while ( (unsigned __int64)(unsigned int)v9 < *(_QWORD *)v7 );
        v10 = v9 <= *(_QWORD *)v7;
      }
      if ( !v10 )
        BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x47Eu, "dwPos <= arrFiles.GetCount()");
      v13 = (unsigned __int16 *)CoTaskMemAlloc(0x10u);
      v20 = v13;
      if ( !v13 )
      {
        NextFile = -2147024882;
LABEL_33:
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_34;
      }
      *(_OWORD *)v13 = 0;
      *(_QWORD *)v13 = v8;
      v14 = pv;
      *((_QWORD *)v13 + 1) = *(_QWORD *)((char *)pv + 4);
      ATL::CAtlArray<_BLB_FILE_FIND_DATA *,ATL::CElementTraits<_BLB_FILE_FIND_DATA *>>::InsertAt(a2, v9, &v20);
      v20 = 0;
      CoTaskMemFree(v14);
      pv = 0;
      NextFile = BlbFindNextFile(a1, hFindFile, (LPVOID *)&v20, (struct _WIN32_FIND_DATAW **)&pv);
      if ( NextFile < 0 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_13;
      }
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
        *v7,
        (__int64)a1);
      goto LABEL_33;
    }
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
        (_DWORD)a1,
        FirstFile);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = (_DWORD *)(a2 + 8);
LABEL_13:
    v8 = v20;
LABEL_34:
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( NextFile < 0 )
  {
    v15 = 0;
    if ( *(_QWORD *)v7 )
    {
      do
      {
        v16 = (void ***)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                          a2,
                          v15);
        v17 = *v16;
        v18 = **v16;
        if ( v18 )
        {
          CoTaskMemFree(v18);
          *v17 = 0;
        }
        if ( v17 )
          CoTaskMemFree(v17);
        ++v15;
      }
      while ( (unsigned __int64)v15 < *(_QWORD *)v7 );
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( hFindFile != (HANDLE)-1LL )
  {
    FindClose(hFindFile);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 57, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
  return (unsigned int)NextFile;
}

```

## disassembly

```asm
0x1400f26e8  push    rbp
0x1400f26ea  push    rbx
0x1400f26eb  push    rsi
0x1400f26ec  push    rdi
0x1400f26ed  push    r12
0x1400f26ef  push    r14
0x1400f26f1  push    r15
0x1400f26f3  mov     rbp, rsp
0x1400f26f6  sub     rsp, 30h
0x1400f26fa  mov     r15, rdx
0x1400f26fd  mov     r14, rcx
0x1400f2700  lea     r12, WPP_GLOBAL_Control
0x1400f2707  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f270e  cmp     rcx, r12
0x1400f2711  jz      short loc_1400F2734
0x1400f2713  test    byte ptr [rcx+1Ch], 1
0x1400f2717  jz      short loc_1400F2734
0x1400f2719  cmp     byte ptr [rcx+19h], 4
0x1400f271d  jb      short loc_1400F2734
0x1400f271f  mov     edx, 35h ; '5'
0x1400f2724  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f272b  mov     rcx, [rcx+10h]
0x1400f272f  call    WPP_SF_
0x1400f2734  mov     [rbp+arg_0], 0
0x1400f273c  mov     [rbp+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1400f2744  mov     [rbp+pv], 0
0x1400f274c  test    r14, r14
0x1400f274f  jnz     short loc_1400F276A
0x1400f2751  lea     r8, aWszfilesearchp; "wszFileSearchPath"
0x1400f2758  mov     edx, 466h; unsigned int
0x1400f275d  lea     rcx, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f2764  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f2769  nop
0x1400f276a  xor     edx, edx
0x1400f276c  mov     rcx, r15
0x1400f276f  call    ?SetCount@?$CAtlArray@PEAU_BLB_FILE_FIND_DATA@@V?$CElementTraits@PEAU_BLB_FILE_FIND_DATA@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<_BLB_FILE_FIND_DATA *,ATL::CElementTraits<_BLB_FILE_FIND_DATA *>>::SetCount(unsigned __int64,int)
0x1400f2774  nop
0x1400f2775  lea     r9, [rbp+pv]; struct _WIN32_FIND_DATAW **
0x1400f2779  lea     r8, [rbp+hFindFile]; void **
0x1400f277d  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x1400f2781  mov     rcx, r14; unsigned __int16 *
0x1400f2784  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x1400f2789  mov     esi, eax
0x1400f278b  test    eax, eax
0x1400f278d  jns     short loc_1400F27D7
0x1400f278f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f2796  cmp     rcx, r12
0x1400f2799  jz      short loc_1400F27CA
0x1400f279b  test    byte ptr [rcx+1Ch], 1
0x1400f279f  jz      short loc_1400F27CA
0x1400f27a1  cmp     byte ptr [rcx+19h], 2
0x1400f27a5  jb      short loc_1400F27CA
0x1400f27a7  mov     edx, 36h ; '6'
0x1400f27ac  mov     dword ptr [rsp+30h+var_10], eax
0x1400f27b0  mov     r9, r14
0x1400f27b3  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f27ba  mov     rcx, [rcx+10h]
0x1400f27be  call    WPP_SF_Sd
0x1400f27c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f27ca  lea     rbx, [r15+8]
0x1400f27ce  mov     rdi, [rbp+arg_0]
0x1400f27d2  jmp     loc_1400F2953
0x1400f27d7  lea     rbx, [r15+8]
0x1400f27db  mov     rdi, [rbp+arg_0]
0x1400f27df  test    rdi, rdi
0x1400f27e2  jz      loc_1400F2910
0x1400f27e8  xor     esi, esi
0x1400f27ea  lea     rbx, [r15+8]
0x1400f27ee  cmp     rsi, [rbx]
0x1400f27f1  jnb     short loc_1400F2826
0x1400f27f3  xor     eax, eax
0x1400f27f5  mov     rdx, rax
0x1400f27f8  mov     rcx, r15
0x1400f27fb  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400f2800  mov     rdx, [rbp+pv]
0x1400f2804  add     rdx, 4; lpFileTime2
0x1400f2808  mov     rcx, [rax]
0x1400f280b  add     rcx, 8; lpFileTime1
0x1400f280f  call    cs:__imp_CompareFileTime
0x1400f2815  cmp     eax, 1
0x1400f2818  jz      short loc_1400F2823
0x1400f281a  inc     esi
0x1400f281c  mov     eax, esi
0x1400f281e  cmp     rax, [rbx]
0x1400f2821  jb      short loc_1400F27F5
0x1400f2823  cmp     rsi, [rbx]
0x1400f2826  jbe     short loc_1400F2840
0x1400f2828  lea     r8, aDwposArrfilesG; "dwPos <= arrFiles.GetCount()"
0x1400f282f  mov     edx, 47Eh; unsigned int
0x1400f2834  lea     rcx, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f283b  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f2840  mov     ecx, 10h; cb
0x1400f2845  call    cs:__imp_CoTaskMemAlloc
0x1400f284b  mov     [rbp+arg_0], rax
0x1400f284f  test    rax, rax
0x1400f2852  jz      loc_1400F2902
0x1400f2858  xorps   xmm0, xmm0
0x1400f285b  movups  xmmword ptr [rax], xmm0
0x1400f285e  mov     [rax], rdi
0x1400f2861  mov     rdi, [rbp+pv]
0x1400f2865  mov     r8, [rdi+4]
0x1400f2869  mov     [rax+8], r8
0x1400f286d  lea     r8, [rbp+arg_0]
0x1400f2871  mov     rdx, rsi
0x1400f2874  mov     rcx, r15
0x1400f2877  call    ?InsertAt@?$CAtlArray@PEAU_BLB_FILE_FIND_DATA@@V?$CElementTraits@PEAU_BLB_FILE_FIND_DATA@@@ATL@@@ATL@@QEAAX_KAEBQEAU_BLB_FILE_FIND_DATA@@0@Z; ATL::CAtlArray<_BLB_FILE_FIND_DATA *,ATL::CElementTraits<_BLB_FILE_FIND_DATA *>>::InsertAt(unsigned __int64,_BLB_FILE_FIND_DATA * const &,unsigned __int64)
0x1400f287c  mov     [rbp+arg_0], 0
0x1400f2884  mov     rcx, rdi; pv
0x1400f2887  call    cs:__imp_CoTaskMemFree
0x1400f288d  mov     [rbp+pv], 0
0x1400f2895  lea     r9, [rbp+pv]; struct _WIN32_FIND_DATAW **
0x1400f2899  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x1400f289d  mov     rdx, [rbp+hFindFile]; hFindFile
0x1400f28a1  mov     rcx, r14; unsigned __int16 *
0x1400f28a4  call    ?BlbFindNextFile@@YAJPEAGPEAXPEAPEAGPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindNextFile(ushort *,void *,ushort * *,_WIN32_FIND_DATAW * *)
0x1400f28a9  mov     esi, eax
0x1400f28ab  test    eax, eax
0x1400f28ad  jns     loc_1400F27D7
0x1400f28b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f28ba  lea     r12, WPP_GLOBAL_Control
0x1400f28c1  cmp     rcx, r12
0x1400f28c4  jz      loc_1400F27CE
0x1400f28ca  test    byte ptr [rcx+1Ch], 1
0x1400f28ce  jz      loc_1400F27CE
0x1400f28d4  cmp     byte ptr [rcx+19h], 2
0x1400f28d8  jb      loc_1400F27CE
0x1400f28de  mov     edx, 37h ; '7'
0x1400f28e3  mov     r9d, eax
0x1400f28e6  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f28ed  mov     rcx, [rcx+10h]
0x1400f28f1  call    WPP_SF_d
0x1400f28f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f28fd  jmp     loc_1400F27CE
0x1400f2902  mov     esi, 8007000Eh
0x1400f2907  lea     r12, WPP_GLOBAL_Control
0x1400f290e  jmp     short loc_1400F294C
0x1400f2910  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f2917  lea     r12, WPP_GLOBAL_Control
0x1400f291e  cmp     rcx, r12
0x1400f2921  jz      short loc_1400F2968
0x1400f2923  test    byte ptr [rcx+1Ch], 1
0x1400f2927  jz      short loc_1400F2968
0x1400f2929  cmp     byte ptr [rcx+19h], 4
0x1400f292d  jb      short loc_1400F2968
0x1400f292f  mov     edx, 38h ; '8'
0x1400f2934  mov     [rsp+30h+var_10], r14
0x1400f2939  mov     r9d, [rbx]
0x1400f293c  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f2943  mov     rcx, [rcx+10h]
0x1400f2947  call    WPP_SF_dS
0x1400f294c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f2953  test    rdi, rdi
0x1400f2956  jz      short loc_1400F2968
0x1400f2958  mov     rcx, rdi; pv
0x1400f295b  call    cs:__imp_CoTaskMemFree
0x1400f2961  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f2968  mov     rdi, [rbp+pv]
0x1400f296c  test    rdi, rdi
0x1400f296f  jz      short loc_1400F2981
0x1400f2971  mov     rcx, rdi; pv
0x1400f2974  call    cs:__imp_CoTaskMemFree
0x1400f297a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f2981  test    esi, esi
0x1400f2983  jns     short loc_1400F29D0
0x1400f2985  xor     r14d, r14d
0x1400f2988  cmp     [rbx], r14
0x1400f298b  jbe     short loc_1400F29D0
0x1400f298d  mov     edx, r14d
0x1400f2990  mov     rcx, r15
0x1400f2993  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400f2998  mov     rdi, [rax]
0x1400f299b  mov     rcx, [rdi]; pv
0x1400f299e  test    rcx, rcx
0x1400f29a1  jz      short loc_1400F29B0
0x1400f29a3  call    cs:__imp_CoTaskMemFree
0x1400f29a9  mov     qword ptr [rdi], 0
0x1400f29b0  test    rdi, rdi
0x1400f29b3  jz      short loc_1400F29BE
0x1400f29b5  mov     rcx, rdi; pv
0x1400f29b8  call    cs:__imp_CoTaskMemFree
0x1400f29be  inc     r14d
0x1400f29c1  mov     eax, r14d
0x1400f29c4  cmp     rax, [rbx]
0x1400f29c7  jb      short loc_1400F298D
0x1400f29c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f29d0  cmp     [rbp+hFindFile], 0FFFFFFFFFFFFFFFFh
0x1400f29d5  jz      short loc_1400F29E8
0x1400f29d7  mov     rcx, [rbp+hFindFile]; hFindFile
0x1400f29db  call    cs:__imp_FindClose
0x1400f29e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f29e8  cmp     rcx, r12
0x1400f29eb  jz      short loc_1400F2A0E
0x1400f29ed  test    byte ptr [rcx+1Ch], 1
0x1400f29f1  jz      short loc_1400F2A0E
0x1400f29f3  cmp     byte ptr [rcx+19h], 4
0x1400f29f7  jb      short loc_1400F2A0E
0x1400f29f9  mov     edx, 39h ; '9'
0x1400f29fe  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f2a05  mov     rcx, [rcx+10h]
0x1400f2a09  call    WPP_SF_
0x1400f2a0e  mov     eax, esi
0x1400f2a10  add     rsp, 30h
0x1400f2a14  pop     r15
0x1400f2a16  pop     r14
0x1400f2a18  pop     r12
0x1400f2a1a  pop     rdi
0x1400f2a1b  pop     rsi
0x1400f2a1c  pop     rbx
0x1400f2a1d  pop     rbp
0x1400f2a1e  retn
```
