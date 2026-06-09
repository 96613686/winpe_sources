# CMDEContentServer::GenerateWMCResElement(_WMCResElementParams const *,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,int,ulong,ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>> *)

- ea: `0x140017450`
- end: `0x14001813c`
- name: `?GenerateWMCResElement@CMDEContentServer@@CAJPEBU_WMCResElementParams@@QEBG111111HKPEAV?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@ATL@@@Z`
- size: `3308`
- prototype: `__int64 __fastcall(int, int, int, int, void *, __int64, __int64, void *Src, int, int, __int64)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400030e8`
- `0x140005b38`
- `0x14001a1c0`

## callees

- `0x1400065e0`
- `0x14000b3f0`
- `0x1400105a0`
- `0x140015230`
- `0x140016170`
- `0x140017450`
- `0x140018144`
- `0x140018df0`
- `0x140019590`
- `0x14001b620`
- `0x1400215f0`
- `0x14002c50c`
- `0x1400396dc`
- `0x140046020`
- `0x140046358`
- `0x140046c32`
- `0x140046d00`
- `0x140054490`
- `0x14005480c`
- `0x140090a24`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140017e00`
- `KERNEL32!CompareStringW` at `0x140017ea0`
- `KERNEL32!CompareStringW` at `0x140017e00`
- `KERNEL32!CompareStringW` at `0x140017ea0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140017932`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018002`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018025`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018098`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400180be`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400180e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140017932`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018002`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018025`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018098`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400180be`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400180e2`
- `OLEAUT32!__imp_SysAllocString` at `0x140017549`
- `OLEAUT32!__imp_SysAllocString` at `0x140017837`
- `OLEAUT32!__imp_SysAllocString` at `0x140017bc1`
- `OLEAUT32!__imp_SysAllocString` at `0x140017c40`
- `OLEAUT32!__imp_SysAllocString` at `0x140017549`
- `OLEAUT32!__imp_SysAllocString` at `0x140017837`
- `OLEAUT32!__imp_SysAllocString` at `0x140017bc1`
- `OLEAUT32!__imp_SysAllocString` at `0x140017c40`
- `OLEAUT32!__imp_SysFreeString` at `0x140017582`
- `OLEAUT32!__imp_SysFreeString` at `0x14001758c`
- `OLEAUT32!__imp_SysFreeString` at `0x140017596`
- `OLEAUT32!__imp_SysFreeString` at `0x14001759f`
- `OLEAUT32!__imp_SysFreeString` at `0x140017582`
- `OLEAUT32!__imp_SysFreeString` at `0x14001758c`
- `OLEAUT32!__imp_SysFreeString` at `0x140017596`
- `OLEAUT32!__imp_SysFreeString` at `0x14001759f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMDEContentServer::GenerateWMCResElement(
        PCNZWCH *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        OLECHAR *a5,
        OLECHAR *a6,
        OLECHAR *a7,
        OLECHAR *Src,
        int a9,
        int a10,
        __int64 **a11)
{
  OLECHAR *v14; // rsi
  OLECHAR *v15; // r13
  char *v16; // rdi
  int v17; // ebx
  BSTR v18; // r8
  OLECHAR *v19; // rdx
  const wchar_t *v21; // r8
  const wchar_t *v22; // rdx
  OLECHAR *v23; // rbx
  OLECHAR *v24; // rax
  __int64 v25; // r14
  int v26; // ebx
  __int64 v27; // rbx
  OLECHAR *v28; // rdx
  unsigned __int64 v29; // r15
  unsigned __int64 v30; // r12
  int v31; // r14d
  size_t v32; // r8
  OLECHAR *v33; // rcx
  BSTR v34; // r8
  __int64 v35; // rax
  OLECHAR *v36; // rsi
  __int64 v37; // rbx
  OLECHAR *v38; // rdx
  unsigned __int64 v39; // r15
  unsigned __int64 v40; // r13
  int v41; // r14d
  size_t v42; // r8
  OLECHAR *v43; // rcx
  const wchar_t *v44; // r14
  unsigned __int64 v45; // r15
  unsigned __int64 v46; // r13
  int v47; // ebx
  OLECHAR *v48; // rcx
  PCNZWCH v49; // r14
  __int64 v50; // rbx
  unsigned __int64 v51; // r13
  int v52; // r15d
  size_t v53; // r8
  OLECHAR *v54; // rcx
  __int64 v55; // r14
  int v56; // ebx
  __int64 v57; // rbx
  OLECHAR *v58; // rdx
  unsigned __int64 v59; // r15
  unsigned __int64 v60; // r13
  int v61; // r14d
  size_t v62; // r8
  OLECHAR *v63; // rcx
  OLECHAR *v64; // rbx
  BSTR v65; // r8
  int v66; // r9d
  const OLECHAR *v67; // rcx
  __int64 v68; // rax
  BSTR v69; // r8
  const OLECHAR *v70; // rcx
  __int64 v71; // rax
  _OWORD *v72; // rcx
  char *v73; // rax
  int v74; // ecx
  __int64 *v75; // rbx
  __int64 *v76; // rcx
  __int64 *v77; // rax
  __int64 **v78; // rax
  const WCHAR *lpString2; // r13
  unsigned int v80; // eax
  unsigned int v81; // r15d
  __int64 i; // r14
  char *v83; // rbx
  OLECHAR *v84; // rax
  __int64 v85; // r14
  int v86; // ebx
  int v87; // eax
  OLECHAR *v88; // r8
  unsigned __int64 v89; // r14
  unsigned __int64 v90; // r15
  int v91; // ebx
  int v92; // ecx
  __int64 v93; // rdx
  size_t v94; // rax
  OLECHAR *v95; // rcx
  int v96; // [rsp+70h] [rbp-21h]
  int v97; // [rsp+70h] [rbp-21h]
  int v98; // [rsp+70h] [rbp-21h]
  void *v99; // [rsp+78h] [rbp-19h] BYREF
  OLECHAR *psz; // [rsp+80h] [rbp-11h] BYREF
  OLECHAR *v101[9]; // [rsp+88h] [rbp-9h] BYREF

  v14 = Src;
  v15 = a5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v21 = Src;
    if ( !Src )
      v21 = L"<NULL>";
    v22 = a5;
    if ( !a5 )
      v22 = L"<NULL>";
    WPP_SF_qSSSSSSSdqI(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v22,
      (_DWORD)a6,
      (_DWORD)a1,
      a2,
      a3,
      a4,
      (__int64)v22,
      (__int64)a6,
      (__int64)a7,
      (__int64)v21,
      a10,
      (char)a11,
      (char)a11[2]);
  }
  psz = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v16 = (char *)operator new(0x60u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_cd74448a81a83594d0e550344f93f664_Traceguids, 0, v16);
  }
  *(_OWORD *)v16 = 0;
  *((_OWORD *)v16 + 1) = 0;
  *((_OWORD *)v16 + 2) = 0;
  *((_OWORD *)v16 + 3) = 0;
  *((_OWORD *)v16 + 4) = 0;
  *((_OWORD *)v16 + 5) = 0;
  v17 = CMDEContentServer::GenerateURI(a2, a1[2], a3, a4, a1[3], a10, &psz);
  v96 = v17;
  if ( v17 < 0 )
    goto LABEL_10;
  if ( !a5 || !*a5 )
  {
    v23 = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v101[0] = v23;
    lpString2 = *a1;
    v80 = CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>::Hash(*a1);
    v81 = v80;
    if ( CShellProvider::s_mapMIMETypeToFileTypes )
    {
      for ( i = *(_QWORD *)(CShellProvider::s_mapMIMETypeToFileTypes + 8LL * (v80 % dword_1400BF590));
            i;
            i = *(_QWORD *)(i + 16) )
      {
        if ( *(_DWORD *)(i + 24) == v81 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, lpString2, -1) == 2 )
        {
          ATL::CSimpleStringT<unsigned short,0>::operator=(v101, (_QWORD *)(i + 8));
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
            v101,
            &v99,
            L",");
          v83 = (char *)v99;
          if ( *((_DWORD *)v99 - 4) )
          {
            ATL::CSimpleStringT<unsigned short,0>::AppendChar(&psz, 46);
            ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)&psz, (const void **)&v99);
          }
          ATL::CStringData::Release((ATL::CStringData *)(v83 - 24));
          v23 = v101[0];
          break;
        }
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
    goto LABEL_31;
  }
  v84 = psz;
  v85 = *((unsigned int *)psz - 4);
  v86 = v85 + 1;
  if ( (int)((*((_DWORD *)psz - 3) - (v85 + 1)) | (1 - *((_DWORD *)psz - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&psz, (unsigned int)v86);
    v84 = psz;
  }
  v84[v85] = 46;
  if ( v86 < 0 || v86 > *((_DWORD *)psz - 3) )
    goto LABEL_190;
  *((_DWORD *)psz - 4) = v86;
  psz[v86] = 0;
  v87 = ATL::CSimpleStringT<unsigned short,0>::StringLength(a5);
  LODWORD(v99) = v87;
  v88 = psz;
  v89 = a5 - psz;
  v90 = *((unsigned int *)psz - 4);
  v91 = v90 + v87;
  v92 = *((_DWORD *)psz - 3) - (v90 + v87);
  v93 = v92 | (unsigned int)(1 - *((_DWORD *)psz - 2));
  if ( (v92 | (1 - *((_DWORD *)psz - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&psz, (unsigned int)v91);
    v88 = psz;
    v87 = (int)v99;
  }
  if ( v89 <= v90 )
    v15 = &v88[v89];
  v94 = 2LL * v87;
  if ( v94 )
  {
    v95 = &v88[v90];
    if ( v95 )
    {
      if ( v15 )
      {
        memcpy_0(v95, v15, v94);
LABEL_171:
        v88 = psz;
        goto LABEL_172;
      }
      memset_0(v95, 0, v94);
    }
    *(_DWORD *)_o__errno(v95, v93, v88) = 22;
    invalid_parameter_noinfo();
    goto LABEL_171;
  }
LABEL_172:
  if ( v91 < 0 || v91 > *((_DWORD *)v88 - 3) )
    goto LABEL_190;
  *((_DWORD *)v88 - 4) = v91;
  psz[v91] = 0;
LABEL_31:
  if ( !Src )
    goto LABEL_50;
  v24 = psz;
  v25 = *((unsigned int *)psz - 4);
  v26 = v25 + 1;
  if ( (int)((*((_DWORD *)psz - 3) - (v25 + 1)) | (1 - *((_DWORD *)psz - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&psz, (unsigned int)v26);
    v24 = psz;
  }
  v24[v25] = 63;
  if ( v26 < 0 || v26 > *((_DWORD *)psz - 3) )
LABEL_190:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)psz - 4) = v26;
  psz[v26] = 0;
  v27 = -1;
  do
    ++v27;
  while ( Src[v27] );
  v28 = psz;
  v29 = Src - psz;
  v30 = *((unsigned int *)psz - 4);
  v31 = v30 + v27;
  if ( (((*((_DWORD *)psz - 3) - (v30 + v27)) | (1 - *((_DWORD *)psz - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&psz, (unsigned int)v31);
    v28 = psz;
  }
  if ( v29 <= v30 )
    v14 = &v28[v29];
  v32 = 2LL * (int)v27;
  if ( !v32 )
    goto LABEL_47;
  v33 = &v28[v30];
  if ( !v33 )
    goto LABEL_178;
  if ( !v14 )
  {
    memset_0(v33, 0, v32);
LABEL_178:
    *(_DWORD *)_o__errno(v33, v28, v32) = 22;
    invalid_parameter_noinfo();
    goto LABEL_46;
  }
  memcpy_0(v33, v14, v32);
LABEL_46:
  v28 = psz;
LABEL_47:
  if ( v31 < 0 || v31 > *((_DWORD *)v28 - 3) )
    goto LABEL_190;
  *((_DWORD *)v28 - 4) = v31;
  psz[v31] = 0;
LABEL_50:
  v34 = SysAllocString(psz);
  *(_QWORD *)v16 = v34;
  v17 = v96;
  if ( !v34 )
    v17 = -2147024882;
  v98 = v17;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v17 >> 31) & 0xFFFFFFFD) + 5) )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      v17,
      (__int64)v34);
  }
  if ( v17 < 0 )
    goto LABEL_10;
  v35 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v36 = (OLECHAR *)(v35 + 24);
  v101[0] = (OLECHAR *)(v35 + 24);
  if ( ((*(_DWORD *)(v35 + 12) - 128) | (1 - *(_DWORD *)(v35 + 16))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, 128);
    v36 = v101[0];
  }
  if ( a6 )
  {
    v37 = -1;
    do
      ++v37;
    while ( a6[v37] );
  }
  else
  {
    LODWORD(v37) = 0;
  }
  v38 = a6;
  v99 = a6;
  v39 = a6 - v36;
  v40 = *((unsigned int *)v36 - 4);
  v41 = v37 + v40;
  if ( (((*((_DWORD *)v36 - 3) - (v37 + v40)) | (1 - *((_DWORD *)v36 - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, (unsigned int)v41);
    v36 = v101[0];
    v38 = (OLECHAR *)v99;
  }
  if ( v39 <= v40 )
    v38 = &v36[v39];
  v42 = 2LL * (int)v37;
  if ( v42 )
  {
    v43 = &v36[v40];
    if ( v43 )
    {
      if ( v38 )
      {
        memcpy_0(v43, v38, v42);
        goto LABEL_69;
      }
      memset_0(v43, 0, v42);
    }
    *(_DWORD *)_o__errno(v43, v38, v42) = 22;
    invalid_parameter_noinfo();
  }
LABEL_69:
  if ( v41 < 0 || v41 > *((_DWORD *)v36 - 3) )
    goto LABEL_190;
  *((_DWORD *)v36 - 4) = v41;
  v36[v41] = 0;
  v44 = L":*:";
  v45 = L":*:" - v36;
  v46 = *((unsigned int *)v36 - 4);
  v47 = v46 + 3;
  if ( (((*((_DWORD *)v36 - 3) - (v46 + 3)) | (1 - *((_DWORD *)v36 - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, (unsigned int)v47);
    v36 = v101[0];
  }
  if ( v45 <= v46 )
    v44 = &v36[v45];
  v48 = &v36[v46];
  if ( !v48 )
    goto LABEL_183;
  if ( !v44 )
  {
    *(_DWORD *)v48 = 0;
    v48[2] = 0;
LABEL_183:
    *(_DWORD *)_o__errno(v48, v38, v42) = 22;
    invalid_parameter_noinfo();
    goto LABEL_78;
  }
  *(_DWORD *)v48 = *(_DWORD *)v44;
  v48[2] = v44[2];
LABEL_78:
  if ( v47 < 0 || v47 > *((_DWORD *)v36 - 3) )
    goto LABEL_190;
  *((_DWORD *)v36 - 4) = v47;
  v36[v47] = 0;
  v49 = *a1;
  if ( *a1 )
  {
    v50 = -1;
    do
      ++v50;
    while ( v49[v50] );
  }
  else
  {
    LODWORD(v50) = 0;
  }
  v51 = v49 - v36;
  LODWORD(v99) = *((_DWORD *)v36 - 4);
  v52 = v50 + (_DWORD)v99;
  if ( (int)((*((_DWORD *)v36 - 3) - (v50 + (_DWORD)v99)) | (1 - *((_DWORD *)v36 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, (unsigned int)v52);
    v36 = v101[0];
  }
  if ( v51 <= (unsigned int)v99 )
    v49 = &v36[v51];
  v53 = 2LL * (int)v50;
  if ( v53 )
  {
    v54 = &v36[(unsigned int)v99];
    if ( v54 )
    {
      if ( v49 )
      {
        memcpy_0(v54, v49, v53);
        goto LABEL_91;
      }
      memset_0(v54, 0, v53);
    }
    *(_DWORD *)_o__errno(v54, v38, v53) = 22;
    invalid_parameter_noinfo();
  }
LABEL_91:
  if ( v52 < 0 || v52 > *((_DWORD *)v36 - 3) )
    goto LABEL_190;
  *((_DWORD *)v36 - 4) = v52;
  v36[v52] = 0;
  v55 = *((unsigned int *)v36 - 4);
  v56 = v55 + 1;
  if ( (int)((*((_DWORD *)v36 - 3) - (v55 + 1)) | (1 - *((_DWORD *)v36 - 2))) < 0 )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, (unsigned int)v56);
    v36 = v101[0];
  }
  v36[v55] = 58;
  if ( v56 < 0 || v56 > *((_DWORD *)v36 - 3) )
    goto LABEL_190;
  *((_DWORD *)v36 - 4) = v56;
  v36[v56] = 0;
  if ( a7 )
  {
    v57 = -1;
    do
      ++v57;
    while ( a7[v57] );
  }
  else
  {
    LODWORD(v57) = 0;
  }
  v58 = a7;
  v99 = a7;
  v59 = a7 - v36;
  v60 = *((unsigned int *)v36 - 4);
  v61 = v57 + v60;
  if ( (((*((_DWORD *)v36 - 3) - (v57 + v60)) | (1 - *((_DWORD *)v36 - 2))) & 0x80000000) != 0LL )
  {
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v101, (unsigned int)v61);
    v36 = v101[0];
    v58 = (OLECHAR *)v99;
  }
  if ( v59 <= v60 )
    v58 = &v36[v59];
  v62 = 2LL * (int)v57;
  if ( v62 )
  {
    v63 = &v36[v60];
    if ( v63 )
    {
      if ( v58 )
      {
        memcpy_0(v63, v58, v62);
        goto LABEL_108;
      }
      memset_0(v63, 0, v62);
    }
    *(_DWORD *)_o__errno(v63, v58, v62) = 22;
    invalid_parameter_noinfo();
  }
LABEL_108:
  if ( v61 < 0 || v61 > *((_DWORD *)v36 - 3) )
    goto LABEL_190;
  *((_DWORD *)v36 - 4) = v61;
  v36[v61] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
    v101,
    L"%ls:*:%ls:%ls",
    a6,
    *a1,
    a7);
  v64 = v101[0];
  v65 = SysAllocString(v101[0]);
  *((_QWORD *)v16 + 5) = v65;
  v66 = v98;
  if ( !v65 )
    v66 = -2147024882;
  v97 = v66;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v66 >> 31) & 0xFFFFFFFD) + 5) )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      v66,
      (__int64)v65);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v64 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v64 - 3) + 8LL))(*((_QWORD *)v64 - 3));
  v17 = v97;
  if ( v97 < 0 )
    goto LABEL_10;
  v67 = a1[4];
  if ( v67 )
  {
    v68 = -1;
    do
      ++v68;
    while ( v67[v68] );
    if ( v68 )
    {
      v69 = SysAllocString(v67);
      *((_QWORD *)v16 + 6) = v69;
      if ( !v69 )
        v17 = -2147024882;
      v97 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v17 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          v17,
          (__int64)v69);
      }
      if ( v17 < 0 )
        goto LABEL_10;
    }
  }
  v70 = a1[6];
  if ( v70 )
  {
    v71 = -1;
    do
      ++v71;
    while ( v70[v71] );
    if ( v71 )
    {
      v18 = SysAllocString(v70);
      *((_QWORD *)v16 + 2) = v18;
      if ( !v18 )
        v17 = -2147024882;
      v97 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v17 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)&WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
          v17,
          (__int64)v18);
      }
      if ( v17 < 0 )
      {
LABEL_10:
        SysFreeString(*((BSTR *)v16 + 6));
        SysFreeString(*((BSTR *)v16 + 5));
        SysFreeString(*((BSTR *)v16 + 2));
        SysFreeString(*(BSTR *)v16);
        operator delete(v16);
        goto LABEL_11;
      }
    }
  }
  *((_QWORD *)v16 + 1) = a1[7];
  *((_DWORD *)v16 + 6) = *((_DWORD *)a1 + 16);
  *((_DWORD *)v16 + 7) = *((_DWORD *)a1 + 18);
  *((_DWORD *)v16 + 8) = *((_DWORD *)a1 + 19);
  *((_DWORD *)v16 + 14) = *((_DWORD *)a1 + 20);
  *((_DWORD *)v16 + 15) = *((_DWORD *)a1 + 21);
  *((_DWORD *)v16 + 16) = *((_DWORD *)a1 + 22);
  *((_DWORD *)v16 + 17) = *((_DWORD *)a1 + 23);
  v72 = a1 + 14;
  v73 = (char *)a1[14] - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v73 )
    v73 = (char *)a1[15] - *(_QWORD *)GUID_NULL.Data4;
  if ( !v73 )
    v72 = a1 + 12;
  *(_OWORD *)(v16 + 72) = *v72;
  *((_DWORD *)v16 + 22) = a9;
  if ( a9 && CompareStringW(0x7Fu, 1u, *a1, -1, L"video/mpeg", -1) == 2 )
    v74 = *((_DWORD *)a1 + 34);
  else
    v74 = 0;
  *((_DWORD *)v16 + 23) = v74;
  v75 = a11[1];
  ATL::CAtlList<_WMCResElement const *,ATL::CElementTraits<_WMCResElement const *>>::GetFreeNode(a11);
  v76 = a11[4];
  v77 = (__int64 *)*v76;
  v76[2] = (__int64)v16;
  a11[4] = v77;
  v76[1] = (__int64)v75;
  *v76 = 0;
  a11[2] = (__int64 *)((char *)a11[2] + 1);
  v78 = (__int64 **)a11[1];
  if ( v78 )
    *v78 = v76;
  else
    *a11 = v76;
  a11[1] = v76;
  v17 = v97;
LABEL_11:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v17 >> 31) & 0xFFFFFFFD) + 5) )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      (unsigned int)v17,
      a11[2]);
  }
  v19 = psz - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)psz - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140017450  mov     [rsp-8+arg_0], rcx
0x140017455  push    rbp
0x140017456  push    rbx
0x140017457  push    rsi
0x140017458  push    rdi
0x140017459  push    r12
0x14001745b  push    r13
0x14001745d  push    r14
0x14001745f  push    r15
0x140017461  lea     rbp, [rsp-7]
0x140017466  sub     rsp, 98h
0x14001746d  mov     rbx, r9
0x140017470  mov     r14, r8
0x140017473  mov     r15, rdx
0x140017476  mov     r10, rcx
0x140017479  lea     rax, WPP_GLOBAL_Control
0x140017480  mov     r12d, [rbp+3Fh+arg_48]
0x140017487  mov     rsi, [rbp+3Fh+Src]
0x14001748e  mov     r13, [rbp+3Fh+arg_20]
0x140017492  mov     rcx, cs:WPP_GLOBAL_Control
0x140017499  cmp     rcx, rax
0x14001749c  jnz     loc_1400175FB
0x1400174a2  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400174a9  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400174b0  mov     rax, [rax+18h]
0x1400174b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400174b9  add     rax, 18h
0x1400174bd  mov     [rbp+3Fh+psz], rax
0x1400174c1  mov     ecx, 60h ; '`'; Size
0x1400174c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400174cb  mov     rdi, rax
0x1400174ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400174d5  lea     rax, WPP_GLOBAL_Control
0x1400174dc  cmp     rcx, rax
0x1400174df  jnz     loc_140017680
0x1400174e5  xorps   xmm0, xmm0
0x1400174e8  movups  xmmword ptr [rdi], xmm0
0x1400174eb  movups  xmmword ptr [rdi+10h], xmm0
0x1400174ef  movups  xmmword ptr [rdi+20h], xmm0
0x1400174f3  movups  xmmword ptr [rdi+30h], xmm0
0x1400174f7  movups  xmmword ptr [rdi+40h], xmm0
0x1400174fb  movups  xmmword ptr [rdi+50h], xmm0
0x1400174ff  lea     rax, [rbp+3Fh+psz]
0x140017503  mov     [rsp+0D0h+var_A0], rax
0x140017508  mov     [rsp+0D0h+cchCount2], r12d
0x14001750d  mov     rcx, [rbp+3Fh+arg_0]
0x140017511  mov     rax, [rcx+18h]
0x140017515  mov     [rsp+0D0h+lpString2], rax
0x14001751a  mov     r9, rbx
0x14001751d  mov     r8, r14
0x140017520  mov     rdx, [rcx+10h]
0x140017524  mov     rcx, r15
0x140017527  call    ?GenerateURI@CMDEContentServer@@CAJQEBG0000KAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CMDEContentServer::GenerateURI(ushort const * const,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14001752c  mov     ebx, eax
0x14001752e  mov     [rbp+3Fh+var_60], eax
0x140017531  mov     r12, 0FFFFFFFFFFFFFFFFh
0x140017538  test    eax, eax
0x14001753a  jns     loc_140017E1A
0x140017540  lea     r13, WPP_GLOBAL_Control
0x140017547  jmp     short loc_14001757E
0x140017549  call    cs:__imp_SysAllocString
0x14001754f  mov     r8, rax
0x140017552  mov     [rdi+10h], rax
0x140017556  test    rax, rax
0x140017559  cmovz   ebx, r14d
0x14001755d  mov     [rbp+3Fh+var_60], ebx
0x140017560  mov     rcx, cs:WPP_GLOBAL_Control
0x140017567  cmp     rcx, r13
0x14001756a  jz      short loc_140017576
0x14001756c  test    byte ptr [rcx+1Ch], 2
0x140017570  jnz     loc_1400180F8
0x140017576  test    ebx, ebx
0x140017578  jns     loc_140017CC3
0x14001757e  mov     rcx, [rdi+30h]; bstrString
0x140017582  call    cs:__imp_SysFreeString
0x140017588  mov     rcx, [rdi+28h]; bstrString
0x14001758c  call    cs:__imp_SysFreeString
0x140017592  mov     rcx, [rdi+10h]; bstrString
0x140017596  call    cs:__imp_SysFreeString
0x14001759c  mov     rcx, [rdi]; bstrString
0x14001759f  call    cs:__imp_SysFreeString
0x1400175a5  mov     edx, 60h ; '`'
0x1400175aa  mov     rcx, rdi; Block
0x1400175ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400175b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175b9  cmp     rcx, r13
0x1400175bc  jnz     loc_1400176B6
0x1400175c2  mov     rdx, [rbp+3Fh+psz]
0x1400175c6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400175ca  lock xadd [rdx+10h], r12d
0x1400175d0  sub     r12d, 1
0x1400175d4  jg      short loc_1400175E5
0x1400175d6  mov     rcx, [rdx]
0x1400175d9  mov     rax, [rcx]
0x1400175dc  mov     rax, [rax+8]
0x1400175e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400175e5  mov     eax, ebx
0x1400175e7  add     rsp, 98h
0x1400175ee  pop     r15
0x1400175f0  pop     r14
0x1400175f2  pop     r13
0x1400175f4  pop     r12
0x1400175f6  pop     rdi
0x1400175f7  pop     rsi
0x1400175f8  pop     rbx
0x1400175f9  pop     rbp
0x1400175fa  retn
0x1400175fb  test    byte ptr [rcx+1Ch], 1
0x1400175ff  jz      loc_1400174A2
0x140017605  cmp     byte ptr [rcx+19h], 5
0x140017609  jb      loc_1400174A2
0x14001760f  lea     rax, aNull_1; "<NULL>"
0x140017616  mov     r8, rsi
0x140017619  test    rsi, rsi
0x14001761c  cmovz   r8, rax
0x140017620  mov     rdx, r13
0x140017623  test    r13, r13
0x140017626  cmovz   rdx, rax
0x14001762a  mov     r9, [rbp+3Fh+arg_50]
0x140017631  mov     rax, [r9+10h]
0x140017635  mov     [rsp+0D0h+var_68], rax
0x14001763a  mov     [rsp+0D0h+var_70], r9
0x14001763f  mov     [rsp+0D0h+var_78], r12d
0x140017644  mov     [rsp+0D0h+var_80], r8
0x140017649  mov     rax, [rbp+3Fh+arg_30]
0x14001764d  mov     [rsp+0D0h+var_88], rax
0x140017652  mov     r8, [rbp+3Fh+arg_28]
0x140017656  mov     [rsp+0D0h+var_90], r8
0x14001765b  mov     [rsp+0D0h+var_98], rdx
0x140017660  mov     [rsp+0D0h+var_A0], rbx
0x140017665  mov     qword ptr [rsp+0D0h+cchCount2], r14
0x14001766a  mov     [rsp+0D0h+lpString2], r15
0x14001766f  mov     r9, r10
0x140017672  mov     rcx, [rcx+10h]
0x140017676  call    WPP_SF_qSSSSSSSdqI
0x14001767b  jmp     loc_1400174A2
0x140017680  test    byte ptr [rcx+1Ch], 2
0x140017684  jz      loc_1400174E5
0x14001768a  cmp     byte ptr [rcx+19h], 5
0x14001768e  jb      loc_1400174E5
0x140017694  mov     edx, 3Fh ; '?'
0x140017699  mov     [rsp+0D0h+lpString2], rdi
0x14001769e  xor     r9d, r9d
0x1400176a1  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x1400176a8  mov     rcx, [rcx+10h]
0x1400176ac  call    WPP_SF_dq
0x1400176b1  jmp     loc_1400174E5
0x1400176b6  test    byte ptr [rcx+1Ch], 1
0x1400176ba  jz      loc_1400175C2
0x1400176c0  mov     edx, ebx
0x1400176c2  sar     edx, 1Fh
0x1400176c5  and     edx, 0FFFFFFFDh
0x1400176c8  add     edx, 5
0x1400176cb  movzx   eax, byte ptr [rcx+19h]
0x1400176cf  cmp     eax, edx
0x1400176d1  jl      loc_1400175C2
0x1400176d7  mov     edx, 44h ; 'D'
0x1400176dc  mov     rax, [rbp+3Fh+arg_50]
0x1400176e3  mov     rax, [rax+10h]
0x1400176e7  mov     [rsp+0D0h+lpString2], rax
0x1400176ec  mov     r9d, ebx
0x1400176ef  lea     r8, WPP_cd74448a81a83594d0e550344f93f664_Traceguids
0x1400176f6  mov     rcx, [rcx+10h]
0x1400176fa  call    WPP_SF_dq
0x1400176ff  jmp     loc_1400175C2
0x140017704  lea     rcx, [rbx-18h]; this
0x140017708  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001770d  mov     rbx, [rbp+3Fh+var_48]
0x140017711  lea     rdx, [rbx-18h]
0x140017715  mov     eax, r12d
0x140017718  lock xadd [rdx+10h], eax
0x14001771d  sub     eax, 1
0x140017720  jg      short loc_140017731
0x140017722  mov     rcx, [rdx]
0x140017725  mov     rax, [rcx]
0x140017728  mov     rax, [rax+8]
0x14001772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017731  test    rsi, rsi
0x140017734  jz      loc_140017833
0x14001773a  mov     rax, [rbp+3Fh+psz]
0x14001773e  mov     r14d, [rax-10h]
0x140017742  lea     ebx, [r14+1]
0x140017746  mov     edx, 1
0x14001774b  sub     edx, [rax-8]
0x14001774e  mov     ecx, [rax-0Ch]
0x140017751  sub     ecx, ebx
0x140017753  or      edx, ecx
0x140017755  jge     short loc_140017766
0x140017757  mov     edx, ebx
0x140017759  lea     rcx, [rbp+3Fh+psz]
0x14001775d  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140017762  mov     rax, [rbp+3Fh+psz]
0x140017766  mov     word ptr [rax+r14*2], 3Fh ; '?'
0x14001776d  test    ebx, ebx
0x14001776f  js      loc_140018131
0x140017775  mov     rax, [rbp+3Fh+psz]
0x140017779  cmp     ebx, [rax-0Ch]
0x14001777c  jg      loc_140018131
0x140017782  mov     [rax-10h], ebx
0x140017785  movsxd  rdx, ebx
0x140017788  xor     ecx, ecx
0x14001778a  mov     rax, [rbp+3Fh+psz]
0x14001778e  mov     [rax+rdx*2], cx
0x140017792  mov     rbx, r12
0x140017795  inc     rbx
0x140017798  cmp     [rsi+rbx*2], cx
0x14001779c  jnz     short loc_140017795
0x14001779e  mov     r15, rsi
0x1400177a1  mov     rdx, [rbp+3Fh+psz]
0x1400177a5  sub     r15, rdx
0x1400177a8  sar     r15, 1
0x1400177ab  mov     r12d, [rdx-10h]
0x1400177af  lea     r14d, [r12+rbx]
0x1400177b3  mov     ecx, 1
0x1400177b8  sub     ecx, [rdx-8]
0x1400177bb  mov     eax, [rdx-0Ch]
0x1400177be  sub     eax, r14d
0x1400177c1  or      ecx, eax
0x1400177c3  jge     short loc_1400177D5
0x1400177c5  mov     edx, r14d
0x1400177c8  lea     rcx, [rbp+3Fh+psz]
0x1400177cc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400177d1  mov     rdx, [rbp+3Fh+psz]
0x1400177d5  cmp     r15, r12
0x1400177d8  jbe     loc_140018015
0x1400177de  movsxd  r8, ebx
0x1400177e1  add     r8, r8; Size
0x1400177e4  jz      short loc_140017808
0x1400177e6  lea     rcx, [rdx+r12*2]; void *
0x1400177ea  test    rcx, rcx
0x1400177ed  jz      loc_140018025
0x1400177f3  test    rsi, rsi
0x1400177f6  jz      loc_14001801E
0x1400177fc  mov     rdx, rsi; Src
0x1400177ff  call    memcpy_0
0x140017804  mov     rdx, [rbp+3Fh+psz]
0x140017808  test    r14d, r14d
0x14001780b  js      loc_140018131
0x140017811  cmp     r14d, [rdx-0Ch]
0x140017815  jg      loc_140018131
0x14001781b  mov     [rdx-10h], r14d
0x14001781f  movsxd  rdx, r14d
0x140017822  xor     ecx, ecx
0x140017824  mov     rax, [rbp+3Fh+psz]
0x140017828  mov     [rax+rdx*2], cx
0x14001782c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x140017833  mov     rcx, [rbp+3Fh+psz]; psz
0x140017837  call    cs:__imp_SysAllocString
0x14001783d  mov     r8, rax
0x140017840  mov     [rdi], rax
0x140017843  mov     ebx, [rbp+3Fh+var_60]
0x140017846  mov     eax, 8007000Eh
0x14001784b  test    r8, r8
0x14001784e  cmovz   ebx, eax
0x140017851  mov     [rbp+3Fh+var_60], ebx
0x140017854  mov     rcx, cs:WPP_GLOBAL_Control
0x14001785b  lea     r13, WPP_GLOBAL_Control
0x140017862  cmp     rcx, r13
0x140017865  jz      short loc_140017871
0x140017867  test    byte ptr [rcx+1Ch], 2
0x14001786b  jnz     loc_14001803B
0x140017871  test    ebx, ebx
0x140017873  js      loc_14001757E
0x140017879  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017880  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140017887  mov     rax, [rax+18h]
0x14001788b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017890  lea     rsi, [rax+18h]
0x140017894  mov     [rbp+3Fh+var_48], rsi
0x140017898  mov     ecx, 1
0x14001789d  sub     ecx, [rsi-8]
0x1400178a0  mov     eax, [rsi-0Ch]
0x1400178a3  add     eax, 0FFFFFF80h
0x1400178a6  or      ecx, eax
0x1400178a8  jge     short loc_1400178BC
0x1400178aa  mov     edx, 80h
0x1400178af  lea     rcx, [rbp+3Fh+var_48]
0x1400178b3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400178b8  mov     rsi, [rbp+3Fh+var_48]
0x1400178bc  mov     rax, [rbp+3Fh+arg_28]
0x1400178c0  test    rax, rax
0x1400178c3  jz      loc_140017DC5
0x1400178c9  mov     rbx, r12
0x1400178cc  nop     dword ptr [rax+00h]
0x1400178d0  inc     rbx
0x1400178d3  cmp     word ptr [rax+rbx*2], 0
0x1400178d8  jnz     short loc_1400178D0
0x1400178da  mov     rdx, rax
0x1400178dd  mov     [rbp+3Fh+var_58], rax
0x1400178e1  mov     r15, rax
0x1400178e4  sub     r15, rsi
0x1400178e7  sar     r15, 1
0x1400178ea  mov     r13d, [rsi-10h]
0x1400178ee  lea     r14d, [rbx+r13]
0x1400178f2  mov     ecx, 1
0x1400178f7  sub     ecx, [rsi-8]
0x1400178fa  mov     eax, [rsi-0Ch]
0x1400178fd  sub     eax, r14d
0x140017900  or      ecx, eax
0x140017902  jge     short loc_140017918
  ... truncated ...
```
