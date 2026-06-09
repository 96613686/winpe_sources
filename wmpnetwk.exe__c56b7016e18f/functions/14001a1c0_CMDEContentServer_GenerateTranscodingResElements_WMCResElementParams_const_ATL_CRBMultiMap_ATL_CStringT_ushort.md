# CMDEContentServer::GenerateTranscodingResElements(_WMCResElementParams const *,ATL::CRBMultiMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>> const *,MDEProfile const *,ushort const * const,ushort const * const,ushort const * const,ushort const * const,ATL::CAtlList<_WMCResElement *,ATL::CElementTraits<_WMCResElement *>> *)

- ea: `0x14001a1c0`
- end: `0x14001b54e`
- name: `?GenerateTranscodingResElements@CMDEContentServer@@AEAAJPEBU_WMCResElementParams@@PEBV?$CRBMultiMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@PEBUMDEProfile@@QEBG333PEAV?$CAtlList@PEAU_WMCResElement@@V?$CElementTraits@PEAU_WMCResElement@@@ATL@@@4@@Z`
- size: `5006`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x14001c430`

## callees

- `0x1400029f0`
- `0x1400030e8`
- `0x140004fe0`
- `0x1400065e0`
- `0x140007020`
- `0x14000b3f0`
- `0x14000c920`
- `0x140013a20`
- `0x140014f90`
- `0x140017450`
- `0x140018df0`
- `0x140019590`
- `0x14001a1c0`
- `0x14001b560`
- `0x14001b620`
- `0x1400312d8`
- `0x1400395c0`
- `0x1400396dc`
- `0x14003b2b8`
- `0x140045f20`
- `0x140046c32`
- `0x140046d00`
- `0x140047798`
- `0x14005480c`
- `0x140091618`
- `0x14009a55c`
- `0x14009ad04`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14001a6a2`
- `KERNEL32!CompareStringW` at `0x14001a6d0`
- `KERNEL32!CompareStringW` at `0x14001a705`
- `KERNEL32!CompareStringW` at `0x14001a736`
- `KERNEL32!CompareStringW` at `0x14001a86b`
- `KERNEL32!CompareStringW` at `0x14001a8d5`
- `KERNEL32!CompareStringW` at `0x14001aa23`
- `KERNEL32!CompareStringW` at `0x14001aa51`
- `KERNEL32!CompareStringW` at `0x14001ae0c`
- `KERNEL32!CompareStringW` at `0x14001b452`
- `KERNEL32!CompareStringW` at `0x14001b47c`
- `KERNEL32!CompareStringW` at `0x14001b4b2`
- `KERNEL32!CompareStringW` at `0x14001a6a2`
- `KERNEL32!CompareStringW` at `0x14001a6d0`
- `KERNEL32!CompareStringW` at `0x14001a705`
- `KERNEL32!CompareStringW` at `0x14001a736`
- `KERNEL32!CompareStringW` at `0x14001a86b`
- `KERNEL32!CompareStringW` at `0x14001a8d5`
- `KERNEL32!CompareStringW` at `0x14001aa23`
- `KERNEL32!CompareStringW` at `0x14001aa51`
- `KERNEL32!CompareStringW` at `0x14001ae0c`
- `KERNEL32!CompareStringW` at `0x14001b452`
- `KERNEL32!CompareStringW` at `0x14001b47c`
- `KERNEL32!CompareStringW` at `0x14001b4b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001b32e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14001b32e`
- `USER32!CharUpperW` at `0x14001a4f3`
- `USER32!CharUpperW` at `0x14001a4f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CMDEContentServer::GenerateTranscodingResElements(
        __int64 a1,
        __int64 a2,
        ATL::CStringData *a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  char v10; // al
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r10
  char v16; // r11
  __int64 v17; // r15
  _WORD *v18; // rcx
  bool v19; // r14
  __int64 v20; // rdi
  __int64 v21; // r8
  PVOID *v22; // rcx
  int v23; // ebx
  __int64 v24; // r9
  volatile signed __int32 *v25; // rdi
  __int64 v26; // rsi
  int *v27; // rsi
  __int64 v28; // r9
  volatile signed __int32 *v29; // rdi
  __int64 v30; // r14
  int v31; // edx
  __int64 v32; // rdi
  const WCHAR *v33; // r14
  unsigned int v34; // esi
  WCHAR v35; // ax
  const WCHAR *v36; // rbx
  __int64 i; // rbx
  __int64 v38; // rdx
  _QWORD *v39; // rcx
  volatile signed __int32 *v40; // rbx
  __int64 v41; // rdi
  char *v42; // rbx
  __int64 v43; // r8
  volatile signed __int32 *v44; // rsi
  volatile signed __int32 *v45; // r14
  __int64 (__fastcall ***v46)(_QWORD, _QWORD, __int64); // rax
  char *v47; // r15
  int v48; // esi
  unsigned int WMCResElement; // r14d
  char v50; // di
  int v51; // eax
  struct _WMCResElementParams *v52; // rsi
  __int64 v53; // rcx
  __int64 v54; // rdi
  unsigned int v55; // ebx
  PVOID v56; // rcx
  _QWORD *v57; // rdx
  _QWORD *v58; // rdx
  _QWORD *v59; // rdx
  _QWORD *v60; // rdx
  int v62; // r14d
  __int64 v63; // rsi
  unsigned int v64; // ecx
  unsigned int v65; // edx
  GUID v66; // xmm0
  GUID v67; // xmm0
  char *v68; // rdi
  ATL::CStringData *v69; // rbx
  unsigned int v70; // eax
  __int64 v71; // r8
  __int64 j; // r14
  __int64 v73; // rdx
  _QWORD *v74; // rcx
  int *v75; // r14
  __int64 v76; // rbx
  __int64 v77; // r14
  __int64 v78; // r8
  _QWORD *v79; // rcx
  int *v80; // rax
  __int64 v81; // rdi
  _QWORD *v82; // rdx
  __int64 v83; // rdx
  _QWORD *v84; // rcx
  volatile signed __int32 *v85; // rbx
  __int64 v86; // r14
  int v87; // r9d
  ATL::CStringData *v88; // rbx
  __int64 v89; // rcx
  unsigned int v90; // ecx
  unsigned int v91; // edx
  _QWORD *v92; // rax
  __int64 v93; // rcx
  int v94; // eax
  struct _WMCResElementParams *v95; // r14
  int v96; // r9d
  int v97; // ebx
  int v98; // edi
  ATL::CStringData *v99; // rbx
  void *v100; // r10
  size_t v101; // r8
  void *v102; // rcx
  __int64 v103; // r8
  __int64 v104; // rax
  __int64 v105; // rdx
  unsigned int v106; // ecx
  unsigned int v107; // eax
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2[2]; // [rsp+28h] [rbp-D8h]
  char v110[8]; // [rsp+30h] [rbp-D0h]
  void *Src; // [rsp+38h] [rbp-C8h]
  char v112[8]; // [rsp+40h] [rbp-C0h]
  char v113[8]; // [rsp+48h] [rbp-B8h]
  ATL::CStringData *v114; // [rsp+60h] [rbp-A0h] BYREF
  char v115[8]; // [rsp+68h] [rbp-98h]
  char *v116; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v117[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _WMCResElementParams *v118; // [rsp+80h] [rbp-80h]
  PCNZWCH v119; // [rsp+88h] [rbp-78h] BYREF
  __int64 v120[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v121; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v122; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v123; // [rsp+B0h] [rbp-50h]
  __int64 v124; // [rsp+B8h] [rbp-48h] BYREF
  int v125; // [rsp+C0h] [rbp-40h]
  int v126; // [rsp+C4h] [rbp-3Ch]
  __int64 v127; // [rsp+C8h] [rbp-38h]
  __int64 v128; // [rsp+D0h] [rbp-30h]
  int v129; // [rsp+D8h] [rbp-28h]
  __int64 v130; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v131; // [rsp+E8h] [rbp-18h]
  __int64 v132; // [rsp+F0h] [rbp-10h]
  __int64 v133; // [rsp+F8h] [rbp-8h]
  __int64 v134; // [rsp+100h] [rbp+0h]
  char *v135; // [rsp+108h] [rbp+8h] BYREF
  int v136[4]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v137; // [rsp+120h] [rbp+20h]
  __int128 v138; // [rsp+130h] [rbp+30h]
  __int128 v139; // [rsp+140h] [rbp+40h]
  unsigned int v140[4]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v141; // [rsp+160h] [rbp+60h]
  GUID Buf1; // [rsp+170h] [rbp+70h] BYREF
  GUID v143; // [rsp+180h] [rbp+80h] BYREF
  __int128 v144; // [rsp+190h] [rbp+90h]

  v10 = (char)a3;
  v114 = a3;
  v118 = (struct _WMCResElementParams *)a2;
  v12 = a5;
  v134 = a5;
  v13 = a6;
  v133 = a6;
  v14 = a7;
  v132 = a7;
  v15 = a8;
  v131 = a8;
  v16 = a9;
  *(_QWORD *)v115 = a9;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x80u) != 0 )
  {
    if ( a9 )
      v103 = *(unsigned int *)(a9 + 16);
    else
      v103 = 0xFFFFFFFFLL;
    McTemplateU0qq_EventWriteTransfer(a1, MDE_Generate_Trans_Res_Element_Start, v103, 0);
    v10 = (char)v114;
    v12 = v134;
    v13 = v133;
    v14 = v132;
    v15 = v131;
    v16 = v115[0];
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqqSSSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, (char)a4, v12, v13, v14, v15, v16);
  }
  v117[0] = *(_DWORD *)(a2 + 128);
  v120[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v17 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v130 = v17;
  v18 = *(_WORD **)(a2 + 48);
  v19 = !v18 || !*v18;
  v121 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v20 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v122 = v20;
  v123 = 0;
  v124 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v125 = 0;
  v127 = 0;
  v128 = 1065353216;
  v129 = 0;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qll(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v21, a4, v19, 0);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  v23 = 0x100000;
  v126 = 0x100000;
  if ( *((_DWORD *)a4 + 14) == 1 )
  {
    HIDWORD(v127) = 1;
    LODWORD(v128) = 1084227584;
    v23 = -2096103424;
    v126 = -2096103424;
    v27 = (int *)(a4 + 23);
  }
  else
  {
    LODWORD(v127) = 1;
    v24 = a4[4];
    v25 = (volatile signed __int32 *)(v20 - 24);
    if ( (volatile signed __int32 *)(v24 - 24) != v25 )
    {
      if ( *((int *)v25 + 4) >= 0 && *(_QWORD *)(v24 - 24) == *(_QWORD *)v25 )
      {
        v26 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v24 - 24);
        if ( _InterlockedExchangeAdd(v25 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25, v25);
        v122 = v26 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v122, a4[4], *(unsigned int *)(v24 - 16));
        v23 = v126;
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    v27 = (int *)(a4 + 23);
    if ( *((_DWORD *)a4 + 46) >= 2u || (v23 |= 0x400000u, v126 = v23, !*((_DWORD *)a4 + 19)) )
    {
      v23 |= 0x1000000u;
      v126 = v23;
    }
    if ( *((_DWORD *)a4 + 17) )
      HIDWORD(v123) = 1;
  }
  if ( v19 )
  {
    LODWORD(v123) = 0;
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v124);
  }
  else
  {
    LODWORD(v123) = *((_DWORD *)a4 + 18);
    v28 = a4[10];
    v29 = (volatile signed __int32 *)(v124 - 24);
    if ( v28 - 24 == v124 - 24 )
      goto LABEL_29;
    if ( *((int *)v29 + 4) >= 0 && *(_QWORD *)(v28 - 24) == *(_QWORD *)v29 )
    {
      v30 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v28 - 24);
      if ( _InterlockedExchangeAdd(v29 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v29 + 8LL))(*(_QWORD *)v29, v29);
      v124 = v30 + 24;
      goto LABEL_28;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v124, a4[10], *(unsigned int *)(v28 - 16));
  }
  v23 = v126;
LABEL_28:
  v22 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
  v125 = *((_DWORD *)a4 + 5);
  v31 = *v27;
  if ( (unsigned int)(*v27 - 3) <= 1 )
  {
    v126 = v23 | 0x10000;
    if ( v31 == 3 )
    {
      HIDWORD(v128) = 1;
    }
    else
    {
      HIDWORD(v128) = 0;
      v129 = 1;
      if ( v31 == 4 )
        goto LABEL_30;
    }
    v129 = 0;
  }
LABEL_30:
  if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
    WPP_SF_(v22[2], 11, &WPP_319832924108377660623741120c2e9b_Traceguids);
  v32 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v116 = (char *)v32;
  v33 = *(const WCHAR **)v118;
  if ( !*(_QWORD *)v118 )
    ATL::AtlThrowImpl(-2147467259);
  v34 = 0;
  v35 = *v33;
  if ( *v33 )
  {
    v36 = *(const WCHAR **)v118;
    do
    {
      v34 = (unsigned __int16)CharUpperW((LPWSTR)v35) + 33 * v34;
      v35 = *++v36;
    }
    while ( *v36 );
  }
  if ( CShellProvider::s_mapMIMETypeToFileTypes )
  {
    for ( i = *(_QWORD *)(CShellProvider::s_mapMIMETypeToFileTypes + 8LL * (v34 % dword_1400BF590));
          ;
          i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
        goto LABEL_60;
      if ( *(_DWORD *)(i + 24) == v34 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, v33, -1) == 2 )
        break;
    }
    v38 = *(_QWORD *)(i + 8);
    v39 = (_QWORD *)(v38 - 24);
    v40 = (volatile signed __int32 *)(v32 - 24);
    if ( v38 - 24 != v32 - 24 )
    {
      if ( *((int *)v40 + 4) >= 0 && *v39 == *(_QWORD *)v40 )
      {
        v41 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v39);
        if ( _InterlockedExchangeAdd(v40 + 4, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v40 + 8LL))(*(_QWORD *)v40, v40);
        v32 = v41 + 24;
        v116 = (char *)v32;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v116, v38, *(unsigned int *)(v38 - 16));
        v32 = (__int64)v116;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
      &v116,
      &v135,
      L",");
    v42 = v135;
    v43 = *((unsigned int *)v135 - 4);
    if ( (_DWORD)v43 )
    {
      v44 = (volatile signed __int32 *)(v135 - 24);
      v45 = (volatile signed __int32 *)(v17 - 24);
      if ( v135 - 24 != (char *)(v17 - 24) )
      {
        if ( *((int *)v45 + 4) >= 0 && *(_QWORD *)v44 == *(_QWORD *)v45 )
        {
          v46 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 32LL))(*(_QWORD *)v44);
          if ( *((int *)v44 + 4) >= 0 && v46 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v44 )
          {
            v47 = v42 - 24;
            _InterlockedIncrement(v44 + 4);
LABEL_55:
            if ( _InterlockedExchangeAdd(v45 + 4, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v45 + 8LL))(*(_QWORD *)v45, v45);
            v17 = (__int64)(v47 + 24);
            v130 = v17;
            goto LABEL_58;
          }
          v104 = (**v46)(v46, *((unsigned int *)v44 + 2), 2);
          v47 = (char *)v104;
          if ( !v104 )
            ATL::CSimpleStringT<char,0>::ThrowMemoryException();
          *(_DWORD *)(v104 + 8) = *((_DWORD *)v44 + 2);
          v101 = 2LL * (*((_DWORD *)v44 + 2) + 1);
          if ( !v101 )
            goto LABEL_55;
          v102 = (void *)(v104 + 24);
          if ( v104 != -24 )
          {
            if ( v42 )
            {
              memcpy_0(v102, v42, v101);
              goto LABEL_55;
            }
            memset_0(v102, 0, v101);
          }
          *(_DWORD *)_o__errno(v102, v105, v101) = 22;
          invalid_parameter_noinfo();
          goto LABEL_55;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v130, v135, v43);
        v17 = v130;
      }
    }
LABEL_58:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v42 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v42 - 3) + 8LL))(*((_QWORD *)v42 - 3));
  }
LABEL_60:
  v48 = v117[0] & 8;
  LODWORD(v119) = v48;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v32 - 24) + 8LL))(*(_QWORD *)(v32 - 24));
  WMCResElement = 0;
  v50 = 1;
  if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"image/x-ycbcr-yuv420", -1) == 2
    && (int)CMDEContentServer::IsImageValid(v118) >= 0 )
  {
    v94 = *((_DWORD *)a4 + 26);
    if ( v94 == 136 )
    {
      if ( *((_DWORD *)a4 + 27) == 90 )
        goto LABEL_153;
    }
    else if ( v94 == 684 && *((_DWORD *)a4 + 27) == 456 )
    {
      goto LABEL_153;
    }
    if ( (unsigned int)CMDEContentServer::IsSuitableMDEProfile(v93, v118, v114, a4) )
    {
LABEL_153:
      v95 = v118;
      *(_OWORD *)v136 = *(_OWORD *)v118;
      v137 = *((_OWORD *)v118 + 1);
      v138 = *((_OWORD *)v118 + 2);
      v139 = *((_OWORD *)v118 + 3);
      *(_OWORD *)v140 = *((_OWORD *)v118 + 4);
      v141 = *((_OWORD *)v118 + 5);
      v144 = *((_OWORD *)v118 + 8);
      *(_QWORD *)v136 = a4[4];
      *(_QWORD *)&v139 = 0;
      v140[2] = *((_DWORD *)a4 + 26);
      v140[3] = *((_DWORD *)a4 + 27);
      *((_QWORD *)&v139 + 1) = -1;
      v140[0] = -1;
      *(_QWORD *)&v141 = -1;
      DWORD2(v141) = -1;
      Buf1 = GUID_NULL;
      v143 = GUID_NULL;
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v121, a4 + 5);
      v96 = *((_DWORD *)v95 + 32) >> 2;
      LOBYTE(v96) = (*((_DWORD *)v95 + 32) & 4) != 0;
      CDlnaContentFeaturesWriter::ToString(
        (unsigned int)&v121,
        (unsigned int)v120,
        0,
        v96,
        (*((_DWORD *)v95 + 32) & 8) != 0);
      v97 = *((_DWORD *)a4 + 28);
      v98 = *((_DWORD *)a4 + 29);
      if ( *((_DWORD *)a4 + 26) == -1 && *((_DWORD *)a4 + 27) == -1 )
      {
        v106 = *((_DWORD *)v95 + 18);
        if ( v106 > 0x800 || (v107 = *((_DWORD *)v95 + 19), v107 > 0x800) )
        {
          if ( (int)GetInscribedRectangle(v106, *((_DWORD *)v95 + 19), 0x800u, 0x800u, &v140[2], &v140[3]) >= 0 )
          {
            v97 = 1;
            v98 = 1;
          }
        }
        else
        {
          v140[2] = *((_DWORD *)v95 + 18);
          v140[3] = v107;
        }
      }
      v114 = (ATL::CStringData *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
      *(_DWORD *)v113 = *((unsigned __int8 *)a4 + 138);
      *(_DWORD *)v112 = *((unsigned __int8 *)a4 + 137);
      LODWORD(Src) = *((unsigned __int8 *)a4 + 136);
      *(_DWORD *)v110 = v98;
      cchCount2[0] = v97;
      LODWORD(lpString2) = v140[3];
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
        &v114,
        L"formatID=%u,width=%u,height=%u,thumbnail=false,aspectRatio=%u:%u,rFill=%u,gFill=%u,bFill=%u",
        *(unsigned int *)a4,
        v140[2],
        lpString2,
        *(_QWORD *)cchCount2,
        *(_QWORD *)v110,
        Src,
        *(_QWORD *)v112,
        *(_QWORD *)v113);
      v99 = v114;
      v100 = (void *)v17;
      if ( !v48 )
        v100 = 0;
      v54 = *(_QWORD *)v115;
      WMCResElement = CMDEContentServer::GenerateWMCResElement(
                        (int)v136,
                        v134,
                        v133,
                        v132,
                        v100,
                        v131,
                        v120[0],
                        v114,
                        0,
                        -1,
                        *(__int64 *)v115);
      ATL::CStringData::Release((ATL::CStringData *)((char *)v99 - 24));
      goto LABEL_67;
    }
LABEL_66:
    v54 = *(_QWORD *)v115;
LABEL_67:
    v55 = -1;
    goto LABEL_68;
  }
  v51 = CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"image/jpeg", -1);
  v52 = v118;
  if ( v51 != 2 || (int)CMDEContentServer::IsImageValid(v118) < 0 )
  {
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], 6, L"audio/", -1) != 2
      && CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], 6, L"video/", -1) != 2
      || !(unsigned int)CMDEContentServer::IsSuitableMDEProfile(v53, v52, v114, a4) )
    {
      goto LABEL_66;
    }
    v62 = CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], 9, L"audio/L16", -1);
    *(_OWORD *)v136 = *(_OWORD *)v52;
    v137 = *((_OWORD *)v52 + 1);
    v138 = *((_OWORD *)v52 + 2);
    v139 = *((_OWORD *)v52 + 3);
    *(_OWORD *)v140 = *((_OWORD *)v52 + 4);
    v141 = *((_OWORD *)v52 + 5);
    Buf1 = (GUID)*((_OWORD *)v52 + 6);
    v143 = (GUID)*((_OWORD *)v52 + 7);
    v144 = *((_OWORD *)v52 + 8);
    v63 = ATL::CSimpleStringT<unsigned short,0>::CloneData(a4[4] - 24) + 24;
    v135 = (char *)v63;
    if ( v62 == 2 && (v117[0] & 0x10) != 0 )
    {
      v92 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
                        a4 + 4,
                        &v114,
                        L";");
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v135, v92);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v114);
      v63 = (__int64)v135;
    }
    *(_QWORD *)v136 = v63;
    *((_QWORD *)&v139 + 1) = -1;
    v64 = *((_DWORD *)a4 + 24);
    v140[0] = v64;
    v65 = *((_DWORD *)a4 + 32);
    if ( v65 != -1 )
    {
      if ( v64 == -1 )
        v64 = 0;
      v140[0] = (v65 >> 3) + v64;
    }
    v140[2] = *((_DWORD *)a4 + 30);
    v140[3] = *((_DWORD *)a4 + 31);
    *(_QWORD *)&v141 = a4[11];
    DWORD2(v141) = *((_DWORD *)a4 + 25);
    HIDWORD(v141) = -1;
    if ( !*((_DWORD *)a4 + 43) )
    {
      if ( !memcmp_0(&GUID_NULL, (char *)a4 + 140, 0x10u) )
      {
        if ( v62 == 2 || CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], 8, L"audio/L8", -1) == 2 )
        {
          v66 = MFAudioFormat_PCM;
        }
        else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"audio/x-ms-wma", -1) == 2 )
        {
          v66 = MFAudioFormat_WMAudioV8;
        }
        else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"audio/mpeg", -1) == 2 )
        {
          v66 = MFAudioFormat_MP3;
        }
        else
        {
          v66 = GUID_NULL;
        }
      }
      else
      {
        v66 = *(GUID *)((char *)a4 + 140);
      }
      Buf1 = v66;
    }
    if ( !*((_DWORD *)a4 + 44) )
    {
      if ( !memcmp_0(&GUID_NULL, (char *)a4 + 156, 0x10u) )
      {
        if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"video/mpeg", -1) == 2 )
        {
          v67 = MFVideoFormat_MPEG2;
        }
        else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a4[4], -1, L"video/x-ms-wmv", -1) == 2 )
        {
          v67 = MFVideoFormat_WMV3;
        }
        else
        {
          v67 = GUID_NULL;
        }
      }
      else
      {
        v67 = *(GUID *)((char *)a4 + 156);
      }
      v143 = v67;
    }
    v68 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v116 = v68;
    if ( (_DWORD)v119 )
    {
      ATL::CSimpleStringT<unsigned short,0>::operator=(&v116, &v130);
      if ( !memcmp_0(&Buf1, &MFAudioFormat_PCM, 0x10u) && !memcmp_0(&v143, &GUID_NULL, 0x10u) )
      {
        v68 = v116;
LABEL_123:
        v114 = (ATL::CStringData *)(((__int64 (__fastcall *)(void ***, _QWORD *, __int64))ATL::g_strmgr[3])(
                                      &ATL::g_strmgr,
                                      v82,
                                      v71)
                                  + 24);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
          &v114,
          L"formatID=%u",
          *(unsigned int *)a4);
        v83 = a4[5];
        v84 = (_QWORD *)(v83 - 24);
        v85 = (volatile signed __int32 *)(v121 - 24);
        if ( v83 - 24 != v121 - 24 )
        {
          if ( *((int *)v85 + 4) >= 0 && *v84 == *(_QWORD *)v85 )
          {
            v86 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v84);
            if ( _InterlockedExchangeAdd(v85 + 4, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v85 + 8LL))(*(_QWORD *)v85, v85);
            v121 = v86 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(&v121, v83, *(unsigned int *)(v83 - 16));
          }
        }
        v87 = *((_DWORD *)v118 + 32) >> 2;
        LOBYTE(v87) = (*((_DWORD *)v118 + 32) & 4) != 0;
        CDlnaContentFeaturesWriter::ToString(
          (unsigned int)&v121,
          (unsigned int)v120,
          0,
          v87,
          (*((_DWORD *)v118 + 32) & 8) != 0);
        v88 = v114;
        WMCResElement = CMDEContentServer::GenerateWMCResElement(
                          (int)v136,
                          v134,
                          v133,
                          v132,
                          v68,
                          v131,
                          v120[0],
                          v114,
                          0,
                          -1,
                          *(__int64 *)v115);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v88 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v88 - 3) + 8LL))(*((_QWORD *)v88 - 3));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v68 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v68 - 3) + 8LL))(*((_QWORD *)v68 - 3));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v63 - 24 + 16), 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v63 - 24) + 8LL))(*(_QWORD *)(v63 - 24));
        goto LABEL_66;
      }
      v68 = v116;
    }
    v69 = (ATL::CStringData *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v114 = v69;
    v119 = *(PCNZWCH *)v136;
    v70 = CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>::Hash(*(_QWORD *)v136);
    v71 = v70;
    v117[0] = v70;
    if ( CShellProvider::s_mapMIMETypeToFileTypes )
    {
      for ( j = *(_QWORD *)(CShellProvider::s_mapMIMETypeToFileTypes + 8LL * (v70 % dword_1400BF590));
            j;
            j = *(_QWORD *)(j + 16) )
      {
        if ( *(_DWORD *)(j + 24) == (_DWORD)v71 )
        {
          if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)j, -1, v119, -1) == 2 )
          {
            v73 = *(_QWORD *)(j + 8);
            v74 = (_QWORD *)(v73 - 24);
            v75 = (int *)((char *)v69 - 24);
            if ( (ATL::CStringData *)(v73 - 24) != (ATL::CStringData *)((char *)v69 - 24) )
            {
              if ( v75[4] >= 0 && *v74 == *(_QWORD *)v75 )
              {
                v76 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v74);
                ATL::CStringData::Release((ATL::CStringData *)v75);
                v69 = (ATL::CStringData *)(v76 + 24);
                v114 = v69;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(&v114, v73, *(unsigned int *)(v73 - 16));
                v69 = v114;
              }
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::SpanExcluding(
              &v114,
              v117,
              L",");
            v77 = *(_QWORD *)v117;
            v78 = *(unsigned int *)(*(_QWORD *)v117 - 16LL);
            if ( (_DWORD)v78 )
            {
              v79 = (_QWORD *)(*(_QWORD *)v117 - 24LL);
              v80 = (int *)(v68 - 24);
              v114 = (ATL::CStringData *)(v68 - 24);
              if ( (char *)(*(_QWORD *)v117 - 24LL) != v68 - 24 )
              {
                if ( v80[4] >= 0 && *v79 == *(_QWORD *)v80 )
                {
                  v81 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v79);
                  ATL::CStringData::Release(v114);
                  v68 = (char *)(v81 + 24);
                  v116 = v68;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&v116, *(_QWORD *)v117, v78);
                  v68 = v116;
                }
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(v77 - 24));
            break;
          }
          v71 = v117[0];
        }
      }
    }
    v82 = (_QWORD *)((char *)v69 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v69 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v82 + 8LL))(*v82);
    goto LABEL_123;
  }
  if ( *((_DWORD *)a4 + 26) != 160 || *((_DWORD *)a4 + 27) != 160 )
  {
    v50 = 0;
    if ( !(unsigned int)CMDEContentServer::IsSuitableMDEProfile(v89, v52, v114, a4) )
      goto LABEL_66;
  }
  v90 = *((_DWORD *)a4 + 26);
  LODWORD(v119) = v90;
  v91 = *((_DWORD *)a4 + 27);
  v117[0] = v91;
  v55 = -1;
  if ( v90 == -1 && v91 == -1 )
  {
    v90 = *((_DWORD *)v52 + 18);
    if ( v90 > 0x800 || (v91 = *((_DWORD *)v52 + 19), v91 > 0x800) )
    {
      GetInscribedRectangle(v90, *((_DWORD *)v52 + 19), 0x800u, 0x800u, (unsigned int *)&v119, v117);
      LOBYTE(v90) = (_BYTE)v119;
      LOBYTE(v91) = v117[0];
    }
  }
  WMCResElement = CMDEContentServer::GenerateImageTranscodingResElement(
                    v52,
                    (struct MDEProfile *)a4,
                    v134,
                    v133,
                    v132,
                    v131,
                    0,
                    v50,
                    v90,
                    v91,
                    a4[5],
                    v115[0]);
  v54 = *(_QWORD *)v115;
LABEL_68:
  v56 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (((int)WMCResElement >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      &WPP_cd74448a81a83594d0e550344f93f664_Traceguids,
      WMCResElement,
      *(_QWORD *)(v54 + 16));
  }
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x80u) != 0 )
  {
    if ( v54 )
      v55 = *(_DWORD *)(v54 + 16);
    McTemplateU0qq_EventWriteTransfer(v56, MDE_Generate_Trans_Res_Element_Stop, v55, WMCResElement);
  }
  v57 = (_QWORD *)(v124 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v124 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v57 + 8LL))(*v57);
  v58 = (_QWORD *)(v122 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v122 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v58 + 8LL))(*v58);
  v59 = (_QWORD *)(v121 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v121 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v59 + 8LL))(*v59);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v17 - 24) + 8LL))(*(_QWORD *)(v17 - 24));
  v60 = (_QWORD *)(v120[0] - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v120[0] - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v60 + 8LL))(*v60);
  return WMCResElement;
}

```

## disassembly

```asm
0x14001a1c0  mov     [rsp-8+arg_0], rbx
0x14001a1c5  push    rbp
0x14001a1c6  push    rsi
0x14001a1c7  push    rdi
0x14001a1c8  push    r12
0x14001a1ca  push    r13
0x14001a1cc  push    r14
0x14001a1ce  push    r15
0x14001a1d0  lea     rbp, [rsp-0B0h]
0x14001a1d8  sub     rsp, 1B0h
0x14001a1df  mov     rax, cs:__security_cookie
0x14001a1e6  xor     rax, rsp
0x14001a1e9  mov     [rbp+0E0h+var_40], rax
0x14001a1f0  mov     r13, r9
0x14001a1f3  mov     rax, r8
0x14001a1f6  mov     [rsp+1E0h+var_180], rax
0x14001a1fb  mov     rbx, rdx
0x14001a1fe  mov     [rbp+0E0h+var_160], rdx
0x14001a202  mov     rdx, [rbp+0E0h+arg_20]
0x14001a209  mov     [rbp+0E0h+var_E0], rdx
0x14001a20d  mov     r8, [rbp+0E0h+arg_28]
0x14001a214  mov     [rbp+0E0h+var_E8], r8
0x14001a218  mov     r9, [rbp+0E0h+arg_30]
0x14001a21f  mov     [rbp+0E0h+var_F0], r9
0x14001a223  mov     r10, [rbp+0E0h+arg_38]
0x14001a22a  mov     [rbp+0E0h+var_F8], r10
0x14001a22e  mov     r11, qword ptr [rbp+0E0h+arg_40]
0x14001a235  mov     qword ptr [rsp+1E0h+var_178], r11
0x14001a23a  cmp     byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 0
0x14001a241  jl      loc_14001B1FA
0x14001a247  lea     rsi, WPP_GLOBAL_Control
0x14001a24e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a255  cmp     rcx, rsi
0x14001a258  jnz     loc_14001AB04
0x14001a25e  mov     eax, [rbx+80h]
0x14001a264  mov     [rsp+1E0h+var_168], eax
0x14001a268  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a26f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a276  mov     rax, [rax+18h]
0x14001a27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a27f  add     rax, 18h
0x14001a283  mov     [rbp+0E0h+var_150], rax
0x14001a287  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a28e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a295  mov     rax, [rax+18h]
0x14001a299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a29e  lea     r15, [rax+18h]
0x14001a2a2  mov     [rbp+0E0h+var_100], r15
0x14001a2a6  mov     rcx, [rbx+30h]
0x14001a2aa  xor     ebx, ebx
0x14001a2ac  test    rcx, rcx
0x14001a2af  jnz     loc_14001A88A
0x14001a2b5  mov     r14b, 1
0x14001a2b8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a2bf  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a2c6  mov     rax, [rax+18h]
0x14001a2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a2cf  add     rax, 18h
0x14001a2d3  mov     [rbp+0E0h+var_140], rax
0x14001a2d7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a2de  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a2e5  mov     rax, [rax+18h]
0x14001a2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a2ee  lea     rdi, [rax+18h]
0x14001a2f2  mov     [rbp+0E0h+var_138], rdi
0x14001a2f6  mov     [rbp+0E0h+var_130], rbx
0x14001a2fa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a301  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a308  mov     rax, [rax+18h]
0x14001a30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a311  add     rax, 18h
0x14001a315  mov     [rbp+0E0h+var_128], rax
0x14001a319  mov     [rbp+0E0h+var_120], ebx
0x14001a31c  mov     [rbp+0E0h+var_118], rbx
0x14001a320  mov     [rbp+0E0h+var_110], 3F800000h
0x14001a328  mov     [rbp+0E0h+var_108], ebx
0x14001a32b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a332  cmp     rcx, rsi
0x14001a335  jz      short loc_14001A341
0x14001a337  test    byte ptr [rcx+1Ch], 2
0x14001a33b  jnz     loc_14001B239
0x14001a341  mov     ebx, 100000h
0x14001a346  mov     [rbp+0E0h+var_11C], ebx
0x14001a349  mov     r12, 0FFFFFFFFFFFFFFFFh
0x14001a350  cmp     dword ptr [r13+38h], 1
0x14001a355  jz      loc_14001A3F5
0x14001a35b  mov     eax, 1
0x14001a360  mov     dword ptr [rbp+0E0h+var_118], eax
0x14001a363  mov     r9, [r13+20h]
0x14001a367  lea     rdx, [r9-18h]
0x14001a36b  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14001a36f  cmp     rdx, rdi
0x14001a372  jz      short loc_14001A3C8
0x14001a374  cmp     dword ptr [rdi+10h], 0
0x14001a378  jl      loc_14001B26C
0x14001a37e  mov     rax, [rdi]
0x14001a381  cmp     [rdx], rax
0x14001a384  jnz     loc_14001B26C
0x14001a38a  mov     rcx, rdx
0x14001a38d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001a392  mov     rsi, rax
0x14001a395  mov     ecx, r12d
0x14001a398  lock xadd [rdi+10h], ecx
0x14001a39d  sub     ecx, 1
0x14001a3a0  jg      short loc_14001A3B4
0x14001a3a2  mov     rcx, [rdi]
0x14001a3a5  mov     rdx, [rcx]
0x14001a3a8  mov     rax, [rdx+8]
0x14001a3ac  mov     rdx, rdi
0x14001a3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3b4  lea     rax, [rsi+18h]
0x14001a3b8  mov     [rbp+0E0h+var_138], rax
0x14001a3bc  mov     eax, 1
0x14001a3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3c8  lea     rsi, [r13+0B8h]
0x14001a3cf  cmp     dword ptr [rsi], 2
0x14001a3d2  jnb     short loc_14001A3E2
0x14001a3d4  bts     ebx, 16h
0x14001a3d8  mov     [rbp+0E0h+var_11C], ebx
0x14001a3db  cmp     dword ptr [r13+4Ch], 0
0x14001a3e0  jnz     short loc_14001A3E9
0x14001a3e2  bts     ebx, 18h
0x14001a3e6  mov     [rbp+0E0h+var_11C], ebx
0x14001a3e9  cmp     dword ptr [r13+44h], 0
0x14001a3ee  jz      short loc_14001A412
0x14001a3f0  mov     dword ptr [rbp+0E0h+var_130+4], eax
0x14001a3f3  jmp     short loc_14001A412
0x14001a3f5  mov     dword ptr [rbp+0E0h+var_118+4], 1
0x14001a3fc  mov     dword ptr [rbp+0E0h+var_110], 40A00000h
0x14001a403  mov     ebx, 83100000h
0x14001a408  mov     [rbp+0E0h+var_11C], ebx
0x14001a40b  lea     rsi, [r13+0B8h]
0x14001a412  test    r14b, r14b
0x14001a415  jnz     loc_14001AE25
0x14001a41b  mov     eax, [r13+48h]
0x14001a41f  mov     dword ptr [rbp+0E0h+var_130], eax
0x14001a422  mov     r9, [r13+50h]
0x14001a426  lea     rdx, [r9-18h]
0x14001a42a  mov     rdi, [rbp+0E0h+var_128]
0x14001a42e  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14001a432  cmp     rdx, rdi
0x14001a435  jz      short loc_14001A486
0x14001a437  cmp     dword ptr [rdi+10h], 0
0x14001a43b  jl      loc_14001B284
0x14001a441  mov     rax, [rdi]
0x14001a444  cmp     [rdx], rax
0x14001a447  jnz     loc_14001B284
0x14001a44d  mov     rcx, rdx
0x14001a450  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001a455  mov     r14, rax
0x14001a458  mov     ecx, r12d
0x14001a45b  lock xadd [rdi+10h], ecx
0x14001a460  sub     ecx, 1
0x14001a463  jg      short loc_14001A477
0x14001a465  mov     rcx, [rdi]
0x14001a468  mov     rdx, [rcx]
0x14001a46b  mov     rax, [rdx+8]
0x14001a46f  mov     rdx, rdi
0x14001a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a477  lea     rax, [r14+18h]
0x14001a47b  mov     [rbp+0E0h+var_128], rax
0x14001a47f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a486  mov     eax, [r13+14h]
0x14001a48a  mov     [rbp+0E0h+var_120], eax
0x14001a48d  mov     edx, [rsi]
0x14001a48f  lea     eax, [rdx-3]
0x14001a492  cmp     eax, 1
0x14001a495  jbe     loc_14001B299
0x14001a49b  lea     rax, WPP_GLOBAL_Control
0x14001a4a2  cmp     rcx, rax
0x14001a4a5  jz      short loc_14001A4B1
0x14001a4a7  test    byte ptr [rcx+1Ch], 2
0x14001a4ab  jnz     loc_14001B2D1
0x14001a4b1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a4b8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14001a4bf  mov     rax, [rax+18h]
0x14001a4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a4c8  lea     rdi, [rax+18h]
0x14001a4cc  mov     [rsp+1E0h+var_170], rdi
0x14001a4d1  mov     r14, [rbp+0E0h+var_160]
0x14001a4d5  mov     r14, [r14]
0x14001a4d8  test    r14, r14
0x14001a4db  jz      loc_14001A87F
0x14001a4e1  xor     esi, esi
0x14001a4e3  movzx   eax, word ptr [r14]
0x14001a4e7  test    ax, ax
0x14001a4ea  jz      short loc_14001A50D
0x14001a4ec  mov     rbx, r14
0x14001a4ef  nop
0x14001a4f0  movzx   ecx, ax; lpsz
0x14001a4f3  call    cs:__imp_CharUpperW
0x14001a4f9  movzx   ecx, ax
0x14001a4fc  imul    esi, 21h ; '!'
0x14001a4ff  add     esi, ecx
0x14001a501  lea     rbx, [rbx+2]
0x14001a505  movzx   eax, word ptr [rbx]
0x14001a508  test    ax, ax
0x14001a50b  jnz     short loc_14001A4F0
0x14001a50d  mov     rbx, cs:?s_mapMIMETypeToFileTypes@CShellProvider@@2V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@A; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> CShellProvider::s_mapMIMETypeToFileTypes
0x14001a514  test    rbx, rbx
0x14001a517  jz      loc_14001A651
0x14001a51d  xor     edx, edx
0x14001a51f  mov     eax, esi
0x14001a521  div     cs:dword_1400BF590
0x14001a527  mov     rbx, [rbx+rdx*8]
0x14001a52b  test    rbx, rbx
0x14001a52e  jz      loc_14001A651
0x14001a534  cmp     [rbx+18h], esi
0x14001a537  jz      loc_14001A851
0x14001a53d  mov     rbx, [rbx+10h]
0x14001a541  jmp     short loc_14001A52B
0x14001a543  mov     rdx, [rbx+8]
0x14001a547  lea     rcx, [rdx-18h]
0x14001a54b  lea     rbx, [rdi-18h]
0x14001a54f  cmp     rcx, rbx
0x14001a552  jz      short loc_14001A59A
0x14001a554  cmp     dword ptr [rbx+10h], 0
0x14001a558  jl      loc_14001B2EB
0x14001a55e  mov     rax, [rbx]
0x14001a561  cmp     [rcx], rax
0x14001a564  jnz     loc_14001B2EB
0x14001a56a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001a56f  mov     rdi, rax
0x14001a572  mov     ecx, r12d
0x14001a575  lock xadd [rbx+10h], ecx
0x14001a57a  sub     ecx, 1
0x14001a57d  jg      short loc_14001A591
0x14001a57f  mov     rcx, [rbx]
0x14001a582  mov     rdx, [rcx]
0x14001a585  mov     rax, [rdx+8]
0x14001a589  mov     rdx, rbx
0x14001a58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a591  add     rdi, 18h
0x14001a595  mov     [rsp+1E0h+var_170], rdi
0x14001a59a  lea     r8, asc_1400A3E98; ","
0x14001a5a1  lea     rdx, [rbp+0E0h+var_D8]
0x14001a5a5  lea     rcx, [rsp+1E0h+var_170]
0x14001a5aa  call    ?SpanExcluding@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEBA?AV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::SpanExcluding(ushort const *)
0x14001a5af  mov     rbx, [rbp+0E0h+var_D8]
0x14001a5b3  mov     r8d, [rbx-10h]
0x14001a5b7  test    r8d, r8d
0x14001a5ba  jz      short loc_14001A631
0x14001a5bc  lea     rsi, [rbx-18h]
0x14001a5c0  lea     r14, [r15-18h]
0x14001a5c4  cmp     rsi, r14
0x14001a5c7  jz      short loc_14001A631
0x14001a5c9  cmp     dword ptr [r14+10h], 0
0x14001a5ce  jl      loc_14001B344
0x14001a5d4  mov     rcx, [rsi]
0x14001a5d7  cmp     rcx, [r14]
0x14001a5da  jnz     loc_14001B344
0x14001a5e0  mov     rax, [rcx]
0x14001a5e3  mov     rax, [rax+20h]
0x14001a5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a5ec  mov     rcx, rax
0x14001a5ef  cmp     dword ptr [rsi+10h], 0
0x14001a5f3  jl      loc_14001B303
0x14001a5f9  cmp     rax, [rsi]
0x14001a5fc  jnz     loc_14001B303
0x14001a602  mov     r15, rsi
0x14001a605  lock inc dword ptr [rsi+10h]
0x14001a609  mov     eax, r12d
0x14001a60c  lock xadd [r14+10h], eax
0x14001a612  sub     eax, 1
0x14001a615  jg      short loc_14001A629
0x14001a617  mov     rcx, [r14]
0x14001a61a  mov     rax, [rcx]
0x14001a61d  mov     rdx, r14
0x14001a620  mov     rax, [rax+8]
0x14001a624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a629  add     r15, 18h
0x14001a62d  mov     [rbp+0E0h+var_100], r15
0x14001a631  lea     rdx, [rbx-18h]
0x14001a635  mov     eax, r12d
0x14001a638  lock xadd [rdx+10h], eax
0x14001a63d  sub     eax, 1
0x14001a640  jg      short loc_14001A651
0x14001a642  mov     rcx, [rdx]
0x14001a645  mov     rax, [rcx]
0x14001a648  mov     rax, [rax+8]
0x14001a64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a651  mov     esi, [rsp+1E0h+var_168]
0x14001a655  and     esi, 8
0x14001a658  mov     dword ptr [rbp+0E0h+var_158], esi
0x14001a65b  lea     rdx, [rdi-18h]
0x14001a65f  mov     eax, r12d
0x14001a662  lock xadd [rdx+10h], eax
0x14001a667  sub     eax, 1
0x14001a66a  jg      short loc_14001A67B
0x14001a66c  mov     rcx, [rdx]
0x14001a66f  mov     rax, [rcx]
0x14001a672  mov     rax, [rax+8]
0x14001a676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a67b  xor     r14d, r14d
0x14001a67e  mov     [rsp+1E0h+cchCount2], r12d; cchCount2
0x14001a683  lea     rax, aImageXYcbcrYuv; "image/x-ycbcr-yuv420"
0x14001a68a  mov     [rsp+1E0h+lpString2], rax; lpString2
0x14001a68f  mov     r9d, r12d; cchCount1
0x14001a692  mov     r8, [r13+20h]; lpString1
0x14001a696  mov     edi, 1
  ... truncated ...
```
