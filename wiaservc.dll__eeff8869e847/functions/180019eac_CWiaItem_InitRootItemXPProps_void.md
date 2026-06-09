# CWiaItem::InitRootItemXPProps(void)

- ea: `0x180019eac`
- end: `0x18001ad95`
- name: `?InitRootItemXPProps@CWiaItem@@QEAAJXZ`
- size: `3817`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800552bc`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x180017740`
- `0x180017e90`
- `0x180019eac`
- `0x18001ad9c`
- `0x18001e364`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x18005ee10`
- `0x18005f520`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001a265`
- `ole32!CoTaskMemFree` at `0x18001a566`
- `ole32!CoTaskMemFree` at `0x18001a924`
- `ole32!CoTaskMemFree` at `0x18001a265`
- `ole32!CoTaskMemFree` at `0x18001a566`
- `ole32!CoTaskMemFree` at `0x18001a924`
- `ole32!PropVariantClear` at `0x18001a683`
- `ole32!PropVariantClear` at `0x18001aa82`
- `ole32!PropVariantClear` at `0x18001ac06`
- `ole32!PropVariantClear` at `0x18001ad4e`
- `ole32!PropVariantClear` at `0x18001a683`
- `ole32!PropVariantClear` at `0x18001aa82`
- `ole32!PropVariantClear` at `0x18001ac06`
- `ole32!PropVariantClear` at `0x18001ad4e`

## string_xrefs

- `0x180019fbb`: `not in compatibility mode or called on non XP A-AIT root item (0x%X)`
- `0x180019fe1`: `not in compatibility mode or called on non XP A-AIT root item (0x%X)`
- `0x18001a216`: `C1 property copy failed (0x%X)`
- `0x18001a238`: `C1 property copy failed (0x%X)`
- `0x18001aab9`: `Call to wiasSetItemPropNames(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001aadf`: `Call to wiasSetItemPropNames(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001ab56`: `Call to wiasSetItemPropAttribs(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`
- `0x18001ab7c`: `Call to wiasSetItemPropAttribs(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`
- `0x18001a9d2`: `wiasSetItemPropAttribs(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001a9f8`: `wiasSetItemPropAttribs(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001aa30`: `Call to WriteMultiple(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001aa56`: `Call to WriteMultiple(WIA_DPS_PAGES) failed (0x%X)`
- `0x18001acfc`: `cannot update document handling select (0x%X)`
- `0x18001ad24`: `cannot update document handling select (0x%X)`
- `0x18001abb4`: `Call to WriteMultiple(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`
- `0x18001abda`: `Call to WriteMultiple(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`
- `0x18001ac3d`: `Call to wiasSetItemPropNames(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`
- `0x18001ac63`: `Call to wiasSetItemPropNames(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitRootItemXPProps(CWiaItem *this)
{
  char ***v2; // rax
  char *v3; // rdx
  __int64 v4; // r8
  _QWORD *v5; // rcx
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // edi
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  int v20; // r13d
  __int64 v21; // rax
  int v22; // r14d
  unsigned int i; // ecx
  __int64 v24; // rax
  __m128i v25; // xmm0
  unsigned int v26; // edx
  unsigned int v27; // eax
  int v28; // r9d
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  int v41; // r12d
  struct CWiaItem *v42; // r15
  int v43; // eax
  __int64 v44; // rcx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  struct CWiaItem *v50; // r14
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // edx
  int v55; // r9d
  char *v56; // rbx
  void *v57; // rdx
  void **v58; // rax
  void *v59; // rdx
  __int64 v60; // rcx
  int v61; // r14d
  char *v62; // rbx
  void *v63; // rdx
  void **v64; // rax
  void *v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  unsigned int k; // edx
  __int64 v69; // rax
  char *v70; // rbx
  void *v71; // rdx
  void **v72; // rax
  void *v73; // rdx
  __int64 v74; // rcx
  bool v75; // zf
  char *v76; // rbx
  void *v77; // rdx
  char *v78; // rbx
  void *v79; // rdx
  void **v80; // rax
  void *v81; // rdx
  __int64 v82; // rcx
  unsigned int m; // edx
  __int64 v84; // rcx
  __m128i v85; // xmm1
  __m128i v86; // xmm0
  __int64 v87; // rcx
  char *v88; // rbx
  void *v89; // rdx
  void **v90; // rax
  void *v91; // rdx
  __int64 v92; // rcx
  char *v93; // rbx
  void *v94; // rdx
  char *v95; // rbx
  void *v96; // rdx
  void **v97; // rax
  void *v98; // rdx
  __int64 v99; // rcx
  char *v100; // rbx
  void *v101; // rdx
  char *v102; // rbx
  void *v103; // rdx
  void **v104; // rax
  void *v105; // rdx
  __int64 v106; // rcx
  char *v107; // rbx
  void *v108; // rdx
  void **v109; // rax
  void *v110; // rdx
  __int64 v111; // rcx
  char *v112; // rbx
  void *v113; // rdx
  char *v114; // rbx
  void *v115; // rdx
  _QWORD *v116; // rax
  char *v117; // rbx
  void *v118; // rdx
  void **v119; // rax
  void *v120; // rdx
  __int64 v121; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  int j; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v125; // [rsp+48h] [rbp-B8h] BYREF
  int v126; // [rsp+50h] [rbp-B0h]
  LPVOID pv[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v128; // [rsp+68h] [rbp-98h] BYREF
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v130; // [rsp+88h] [rbp-78h]
  unsigned int v131; // [rsp+90h] [rbp-70h] BYREF
  int v132; // [rsp+94h] [rbp-6Ch]
  unsigned __int16 *v133; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v134[80]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v135[36]; // [rsp+F0h] [rbp-10h] BYREF
  int v136; // [rsp+114h] [rbp+14h]

  v2 = (char ***)WiaTrace_Trace("CWiaItem::InitRootItemXPProps");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v134, v3, v4, (char **)"CWiaItem::InitRootItemXPProps", lpMem, v2);
  v5 = (_QWORD *)*((_QWORD *)this + 8);
  v6 = 1;
  if ( v5 && *((_DWORD *)this + 26) == 2 && *((CWiaItem **)this + 26) == this && (v5[11] || v5[12]) )
  {
    v125 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v5[1] + 88LL))(v5 + 1, &v125);
    v8 = v125;
    v9 = v7;
    if ( v125 )
    {
      if ( v7 >= 0 )
        goto LABEL_11;
    }
    else
    {
      v9 = -2147024882;
    }
    v10 = (char *)WiaTrace_TraceLog("failed to get property enumerator for root properties to translate (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    v12 = (void **)WiaTrace_Trace("failed to get property enumerator for root properties to translate (0x%X)", v9);
    v6 = 1;
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"CWiaItem::InitRootItemXPProps", 1, v12);
    v8 = v125;
  }
  else
  {
    v9 = -2147467261;
    v15 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non XP A-AIT root item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v17 = (void **)WiaTrace_Trace("not in compatibility mode or called on non XP A-AIT root item (0x%X)", -2147467261);
    v6 = 1;
    WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::InitRootItemXPProps", 1, v17);
    v8 = 0;
    v125 = 0;
  }
LABEL_11:
  v20 = 0;
  j = 0;
  v132 = 0;
  *(_OWORD *)pv = 0;
  if ( v9 < 0 )
  {
    v22 = 0;
    v126 = 0;
  }
  else
  {
    v21 = *((_QWORD *)this + 8);
    LOBYTE(v20) = *(_QWORD *)(v21 + 88) != 0;
    if ( *(_QWORD *)(v21 + 96) )
    {
      v22 = 1;
      v126 = 1;
    }
    else
    {
      v22 = 0;
      v126 = 0;
    }
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v8 + 24LL))(v8, 1, pv, &j)
         && j == 1 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= 0x35 )
        {
          v9 = CWiaItem::CopyPropertyFrom(
                 *((CWiaItem **)this + 26),
                 *((struct CWiaItem **)this + 8),
                 (struct tagSTATPROPSTG *)pv);
          if ( v9 >= 0 )
            goto LABEL_40;
          v39 = (char *)WiaTrace_TraceLog("C1 property copy failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v39);
          WiaTrcLib::Free((WiaTrcLib *)v39, v40);
          v31 = (void **)WiaTrace_Trace("C1 property copy failed (0x%X)", (unsigned int)v9);
          goto LABEL_39;
        }
        v24 = 4LL * i;
        if ( HIDWORD(qword_180082160[v24]) == LODWORD(pv[1]) )
          break;
      }
      v25 = *(__m128i *)&qword_180082160[v24];
      if ( _mm_cvtsi128_si32(v25) == 4
        && ((_mm_cvtsi128_si32(_mm_srli_si128(v25, 8)) - 1) & 0xFFFFFFFD) == 0
        && ((HIDWORD(qword_180082160[v24 + 2]) - 4) & 0xFFFFFFFB) == 0 )
      {
        if ( LODWORD(pv[1]) == 3086 )
        {
          v26 = v20 != 0;
          if ( v22 )
            v26 = 2;
          v27 = (v20 != 0) | 2;
          if ( !v22 )
            v27 = v20 != 0;
          v28 = (v20 != 0 ? 0x35 : 0) | 0xA;
          if ( !v22 )
            v28 = v20 != 0 ? 0x35 : 0;
          v9 = CWiaItem::CopyFlagPropertyFrom(
                 *((CWiaItem **)this + 26),
                 *((struct CWiaItem **)this + 8),
                 (struct tagSTATPROPSTG *)pv,
                 v28,
                 v26,
                 v27,
                 v26);
          if ( v9 < 0 )
          {
            v29 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES translation failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v29);
            WiaTrcLib::Free((WiaTrcLib *)v29, v30);
            v31 = (void **)WiaTrace_Trace(
                             "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES translation failed (0x%X)",
                             (unsigned int)v9);
LABEL_39:
            v6 = 1;
            WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"CWiaItem::InitRootItemXPProps", 1, v31);
          }
        }
        else
        {
          v9 = CWiaItem::CopyPropertyFrom(
                 *((CWiaItem **)this + 26),
                 *((struct CWiaItem **)this + 8),
                 (struct tagSTATPROPSTG *)pv);
          if ( v9 < 0 )
          {
            v34 = (char *)WiaTrace_TraceLog("C4 property translation failed (0x%X)");
            WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v34);
            WiaTrcLib::Free((WiaTrcLib *)v34, v35);
            v36 = (void **)WiaTrace_Trace("C4 property translation failed (0x%X)", v9);
            v6 = 1;
            WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"CWiaItem::InitRootItemXPProps", 1, v36);
          }
          if ( LODWORD(pv[1]) == 3095 )
            v132 = 1;
        }
      }
LABEL_40:
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
      if ( v9 < 0 )
        break;
      v8 = v125;
      j = 0;
    }
    v8 = v125;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v125 = 0;
  }
  if ( v9 >= 0 )
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, 1);
  v41 = 0;
  v42 = *(struct CWiaItem **)(*((_QWORD *)this + 8) + 88LL);
  if ( v42 && v9 >= 0 )
  {
    v43 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*((_QWORD *)v42 + 1) + 88LL))((_QWORD *)v42 + 1, &v125);
    v44 = v125;
    v9 = v43;
    if ( !v125 )
    {
      v9 = -2147024882;
      goto LABEL_55;
    }
    if ( v43 < 0 )
    {
LABEL_55:
      v45 = (char *)WiaTrace_TraceLog("failed to get property enumerator for ADF D-AIT properties to translate (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_Trace(
                       "failed to get property enumerator for ADF D-AIT properties to translate (0x%X)",
                       v9);
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"CWiaItem::InitRootItemXPProps", 1, v47);
LABEL_56:
      if ( v125 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
        v125 = 0;
      }
      if ( v9 >= 0 )
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, 1);
      goto LABEL_60;
    }
    for ( j = 0; ; j = 0 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v44 + 24LL))(v44, 1, pv, &j)
        || j != 1 )
      {
        goto LABEL_56;
      }
      memset(v135, 0, 32);
      if ( (unsigned int)CWiaItem::GetPropCompatCategory(v53, LODWORD(pv[1]), 0, 5, v135) )
      {
        if ( *(_DWORD *)v135 == 2 )
        {
          if ( *(_DWORD *)&v135[8] == 1 && *(_DWORD *)&v135[20] == v55 )
          {
            v9 = CWiaItem::CopyC2PropertyFrom(
                   *((CWiaItem **)this + 26),
                   v42,
                   (struct tagSTATPROPSTG *)pv,
                   *(unsigned int *)&v135[4]);
            if ( v9 < 0 )
            {
              v56 = (char *)WiaTrace_TraceLog("C2 property translation failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v56);
              WiaTrcLib::Free((WiaTrcLib *)v56, v57);
              v58 = (void **)WiaTrace_Trace("C2 property translation failed (0x%X)", (unsigned int)v9);
LABEL_96:
              v6 = 1;
              WiaTrace_ProcessTrace_Ex(v60, v59, (void *)"CWiaItem::InitRootItemXPProps", 1, v58);
            }
          }
        }
        else if ( *(_DWORD *)v135 == 3 && ((*(_DWORD *)&v135[20] - 5) & 0xFFFFFFFD) == 0 )
        {
          if ( v54 == 3088 )
          {
            v61 = CWiaItem::CopyFlagPropertyFrom(
                    *((CWiaItem **)this + 26),
                    v42,
                    (struct tagSTATPROPSTG *)pv,
                    2 * v22 + 125,
                    1u,
                    2 * v22 + 1,
                    1u);
            if ( v61 < 0 )
            {
              v62 = (char *)WiaTrace_TraceLog("WIA_IPS_DOCUMENT_HANDLING_SELECT translation failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v62);
              WiaTrcLib::Free((WiaTrcLib *)v62, v63);
              v64 = (void **)WiaTrace_Trace("WIA_IPS_DOCUMENT_HANDLING_SELECT translation failed (0x%X)", v61);
              v6 = 1;
              WiaTrace_ProcessTrace_Ex(v66, v65, (void *)"CWiaItem::InitRootItemXPProps", 1, v64);
            }
            v22 = v126;
          }
          else
          {
            if ( v54 != 3097 )
              goto LABEL_94;
            v130 = 0;
            v67 = *((_QWORD *)v42 + 27);
            v128 = 0;
            LODWORD(v128) = 1;
            DWORD2(v128) = 3097;
            *(_OWORD *)pvar = 0;
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *))(**(_QWORD **)(v67 + 8) + 24LL))(
                   *(_QWORD *)(v67 + 8),
                   1,
                   &v128,
                   pvar);
            if ( v9 < 0 )
              goto LABEL_94;
            if ( LOWORD(pvar[0]) == 4099 )
            {
              for ( k = 0; k < LODWORD(pvar[1]) - 2; ++k )
              {
                v69 = k + 2;
                if ( *(_DWORD *)(v130 + 4 * v69) == 100 || *(_DWORD *)(v130 + 4 * v69) == 0x8000 )
                {
                  v70 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                                  0,
                                  0,
                                  "LH only page size value found, WIA_IPS_PAGE_SIZE will not be translated",
                                  v130);
                  WriteDbgTraceInfoWI("CWiaItem::InitRootItemXPProps", v70);
                  WiaTrcLib::Free((WiaTrcLib *)v70, v71);
                  v72 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                                   0,
                                   0,
                                   "LH only page size value found, WIA_IPS_PAGE_SIZE will not be translated");
                  WiaTrace_ProcessTrace_Ex(v74, v73, (void *)"CWiaItem::InitRootItemXPProps", 4, v72);
                  v6 = 0;
                  goto LABEL_93;
                }
              }
              v6 = 1;
            }
LABEL_93:
            PropVariantClear(pvar);
            v75 = v6 == 0;
            v6 = 1;
            if ( !v75 )
            {
LABEL_94:
              v9 = CWiaItem::CopyPropertyFrom(*((CWiaItem **)this + 26), v42, (struct tagSTATPROPSTG *)pv);
              if ( v9 < 0 )
              {
                v76 = (char *)WiaTrace_TraceLog("C3 property translation failed (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v76);
                WiaTrcLib::Free((WiaTrcLib *)v76, v77);
                v58 = (void **)WiaTrace_Trace("C3 property translation failed (0x%X)", (unsigned int)v9);
                goto LABEL_96;
              }
              if ( *(_DWORD *)&v135[4] == 3096 )
                v41 = 1;
            }
          }
        }
      }
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
      if ( v9 < 0 )
        goto LABEL_56;
      v44 = v125;
    }
  }
LABEL_60:
  v50 = *(struct CWiaItem **)(*((_QWORD *)this + 8) + 96LL);
  if ( !v50 )
  {
    if ( v9 < 0 )
      goto LABEL_155;
LABEL_128:
    if ( v41 || !v20 )
      goto LABEL_138;
    LODWORD(v128) = 1;
    *(_OWORD *)pvar = 0;
    *(_OWORD *)&v135[20] = 0;
    LOWORD(pvar[0]) = 3;
    LODWORD(pvar[1]) = 1;
    *((_QWORD *)&v128 + 1) = 3096;
    *(_DWORD *)&v135[4] = 3;
    *(_DWORD *)&v135[8] = 0;
    *(_QWORD *)&v135[16] = 0x100000001LL;
    *(_DWORD *)&v135[12] = 1;
    v136 = 0;
    v130 = 0;
    *(_DWORD *)v135 = 19;
    v9 = wiasSetItemPropAttribs(this);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(***((_QWORD ***)this + 27) + 32LL))(
             **((_QWORD **)this + 27),
             1,
             &v128,
             pvar,
             3074);
      if ( v9 >= 0 )
      {
LABEL_135:
        PropVariantClear(pvar);
        if ( v9 < 0 )
          goto LABEL_155;
        v131 = 3096;
        v133 = L"Pages";
        v9 = wiasSetItemPropNames(this, 1, &v131, &v133);
        if ( v9 < 0 )
        {
          v102 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropNames(WIA_DPS_PAGES) failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v102);
          WiaTrcLib::Free((WiaTrcLib *)v102, v103);
          v104 = (void **)WiaTrace_Trace("Call to wiasSetItemPropNames(WIA_DPS_PAGES) failed (0x%X)", (unsigned int)v9);
LABEL_147:
          WiaTrace_ProcessTrace_Ex(v106, v105, (void *)"CWiaItem::InitRootItemXPProps", 1, v104);
          goto LABEL_155;
        }
LABEL_138:
        if ( v132 )
        {
LABEL_148:
          if ( !v20 )
            goto LABEL_154;
          if ( v126 )
          {
            LODWORD(v128) = 1;
            *((_QWORD *)&v128 + 1) = 0;
            v130 = 0;
            v116 = (_QWORD *)*((_QWORD *)this + 27);
            *(_OWORD *)pvar = 0;
            DWORD2(v128) = 3088;
            LOWORD(pvar[0]) = 3;
            LODWORD(pvar[1]) = 2;
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(*(_QWORD *)*v116 + 32LL))(
                   *v116,
                   1,
                   &v128,
                   pvar,
                   3074);
            if ( v9 < 0 )
            {
              v117 = (char *)WiaTrace_TraceLog("cannot update document handling select (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v117);
              WiaTrcLib::Free((WiaTrcLib *)v117, v118);
              v119 = (void **)WiaTrace_Trace("cannot update document handling select (0x%X)", v9);
              WiaTrace_ProcessTrace_Ex(v121, v120, (void *)"CWiaItem::InitRootItemXPProps", 1, v119);
            }
            PropVariantClear(pvar);
          }
          if ( v9 >= 0 )
LABEL_154:
            (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, 1);
          goto LABEL_155;
        }
        LODWORD(v128) = 1;
        *(_DWORD *)v135 = 9;
        *(_OWORD *)pvar = 0;
        memset(&v135[4], 0, 32);
        LOWORD(pvar[0]) = 3;
        LODWORD(pvar[1]) = 3600000;
        *((_QWORD *)&v128 + 1) = 3095;
        *(_WORD *)&v135[4] = 3;
        v136 = 0;
        v130 = 0;
        v9 = wiasSetItemPropAttribs(this);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, PROPVARIANT *, int))(***((_QWORD ***)this + 27)
                                                                                          + 32LL))(
                 **((_QWORD **)this + 27),
                 1,
                 &v128,
                 pvar,
                 3074);
          if ( v9 >= 0 )
          {
LABEL_144:
            PropVariantClear(pvar);
            if ( v9 < 0 )
              goto LABEL_155;
            v131 = 3095;
            v133 = L"Max Scan Time";
            v9 = wiasSetItemPropNames(this, 1, &v131, &v133);
            if ( v9 < 0 )
            {
              v114 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropNames(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v114);
              WiaTrcLib::Free((WiaTrcLib *)v114, v115);
              v104 = (void **)WiaTrace_Trace(
                                "Call to wiasSetItemPropNames(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)",
                                (unsigned int)v9);
              goto LABEL_147;
            }
            goto LABEL_148;
          }
          v112 = (char *)WiaTrace_TraceLog("Call to WriteMultiple(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v112);
          WiaTrcLib::Free((WiaTrcLib *)v112, v113);
          v109 = (void **)WiaTrace_Trace("Call to WriteMultiple(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)", (unsigned int)v9);
        }
        else
        {
          v107 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropAttribs(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v107);
          WiaTrcLib::Free((WiaTrcLib *)v107, v108);
          v109 = (void **)WiaTrace_Trace(
                            "Call to wiasSetItemPropAttribs(WIA_DPS_MAX_SCAN_TIME) failed (0x%X)",
                            (unsigned int)v9);
        }
        WiaTrace_ProcessTrace_Ex(v111, v110, (void *)"CWiaItem::InitRootItemXPProps", 1, v109);
        goto LABEL_144;
      }
      v100 = (char *)WiaTrace_TraceLog("Call to WriteMultiple(WIA_DPS_PAGES) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v100);
      WiaTrcLib::Free((WiaTrcLib *)v100, v101);
      v97 = (void **)WiaTrace_Trace("Call to WriteMultiple(WIA_DPS_PAGES) failed (0x%X)", (unsigned int)v9);
    }
    else
    {
      v95 = (char *)WiaTrace_TraceLog("wiasSetItemPropAttribs(WIA_DPS_PAGES) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v95);
      WiaTrcLib::Free((WiaTrcLib *)v95, v96);
      v97 = (void **)WiaTrace_Trace("wiasSetItemPropAttribs(WIA_DPS_PAGES) failed (0x%X)", (unsigned int)v9);
    }
    WiaTrace_ProcessTrace_Ex(v99, v98, (void *)"CWiaItem::InitRootItemXPProps", 1, v97);
    goto LABEL_135;
  }
  if ( v9 >= 0 )
  {
    v51 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*((_QWORD *)v50 + 1) + 88LL))((_QWORD *)v50 + 1, &v125);
    v52 = v125;
    v9 = v51;
    if ( v125 )
    {
      if ( v51 >= 0 )
      {
        while ( 1 )
        {
          j = 0;
          if ( (*(unsigned int (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v52 + 24LL))(
                 v52,
                 1,
                 pv,
                 &j)
            || j != 1 )
          {
            goto LABEL_102;
          }
          for ( m = 0; ; ++m )
          {
            if ( m >= 0x35 )
              goto LABEL_123;
            v84 = 4LL * m;
            if ( LODWORD(qword_180082160[v84 + 2]) == LODWORD(pv[1])
              && (unsigned int)(HIDWORD(qword_180082160[v84 + 2]) - 6) <= 2 )
            {
              break;
            }
          }
          v85 = *(__m128i *)&qword_180082160[v84];
          v86 = *(__m128i *)&qword_180082160[v84 + 2];
          v87 = qword_180082160[v84];
          if ( (_DWORD)v87 == 2 )
          {
            if ( _mm_cvtsi128_si32(_mm_srli_si128(v85, 8)) == 1 && v86.m128i_i32[1] == 6 )
            {
              v9 = CWiaItem::CopyC2PropertyFrom(
                     *((CWiaItem **)this + 26),
                     v50,
                     (struct tagSTATPROPSTG *)pv,
                     HIDWORD(v87));
              if ( v9 < 0 )
              {
                v88 = (char *)WiaTrace_TraceLog("C2 property translation failed (0x%X)");
                WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v88);
                WiaTrcLib::Free((WiaTrcLib *)v88, v89);
                v90 = (void **)WiaTrace_Trace("C2 property translation failed (0x%X)", (unsigned int)v9);
LABEL_122:
                WiaTrace_ProcessTrace_Ex(v92, v91, (void *)"CWiaItem::InitRootItemXPProps", 1, v90);
              }
            }
          }
          else if ( (_DWORD)v87 == 3 && (unsigned int)(_mm_cvtsi128_si32(_mm_srli_si128(v86, 4)) - 6) <= 1 )
          {
            v9 = CWiaItem::CopyPropertyFrom(*((CWiaItem **)this + 26), v50, (struct tagSTATPROPSTG *)pv);
            if ( v9 < 0 )
            {
              v93 = (char *)WiaTrace_TraceLog("C3 property translation failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v93);
              WiaTrcLib::Free((WiaTrcLib *)v93, v94);
              v90 = (void **)WiaTrace_Trace("C3 property translation failed (0x%X)", (unsigned int)v9);
              goto LABEL_122;
            }
          }
LABEL_123:
          if ( pv[0] )
          {
            CoTaskMemFree(pv[0]);
            pv[0] = 0;
          }
          if ( v9 < 0 )
            goto LABEL_102;
          v52 = v125;
        }
      }
    }
    else
    {
      v9 = -2147024882;
    }
    v78 = (char *)WiaTrace_TraceLog("failed to get property enumerator for FB D-AIT properties to translate (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitRootItemXPProps", v78);
    WiaTrcLib::Free((WiaTrcLib *)v78, v79);
    v80 = (void **)WiaTrace_Trace("failed to get property enumerator for FB D-AIT properties to translate (0x%X)", v9);
    WiaTrace_ProcessTrace_Ex(v82, v81, (void *)"CWiaItem::InitRootItemXPProps", 1, v80);
LABEL_102:
    if ( v125 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
      v125 = 0;
    }
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 1) + 72LL))((char *)this + 8, 1);
      goto LABEL_128;
    }
  }
LABEL_155:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v134);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180019eac  push    rbp
0x180019eae  push    rbx
0x180019eaf  push    rsi
0x180019eb0  push    rdi
0x180019eb1  push    r12
0x180019eb3  push    r13
0x180019eb5  push    r14
0x180019eb7  push    r15
0x180019eb9  lea     rbp, [rsp-28h]
0x180019ebe  sub     rsp, 128h
0x180019ec5  mov     rax, cs:__security_cookie
0x180019ecc  xor     rax, rsp
0x180019ecf  mov     [rbp+60h+var_48], rax
0x180019ed3  mov     rsi, rcx
0x180019ed6  lea     r15, aCwiaitemInitro; "CWiaItem::InitRootItemXPProps"
0x180019edd  mov     rcx, r15
0x180019ee0  call    WiaTrace_Trace
0x180019ee5  mov     r9, r15; char *
0x180019ee8  mov     [rsp+160h+var_138], rax; struct tagWiaTraceData_Type *
0x180019eed  lea     rcx, [rbp+60h+var_C0]; this
0x180019ef1  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180019ef6  mov     rcx, [rsi+40h]
0x180019efa  mov     ebx, 1
0x180019eff  test    rcx, rcx
0x180019f02  jz      loc_180019FB6
0x180019f08  cmp     dword ptr [rsi+68h], 2
0x180019f0c  jnz     loc_180019FB6
0x180019f12  cmp     [rsi+0D0h], rsi
0x180019f19  jnz     loc_180019FB6
0x180019f1f  cmp     qword ptr [rcx+58h], 0
0x180019f24  jnz     short loc_180019F31
0x180019f26  cmp     qword ptr [rcx+60h], 0
0x180019f2b  jz      loc_180019FB6
0x180019f31  xor     eax, eax
0x180019f33  lea     rdx, [rsp+160h+var_118]
0x180019f38  mov     [rsp+160h+var_118], rax
0x180019f3d  add     rcx, 8
0x180019f41  mov     rax, [rcx]
0x180019f44  mov     rax, [rax+58h]
0x180019f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f4d  mov     rcx, [rsp+160h+var_118]
0x180019f52  mov     edi, eax
0x180019f54  test    rcx, rcx
0x180019f57  jnz     short loc_180019F60
0x180019f59  mov     edi, 8007000Eh
0x180019f5e  jmp     short loc_180019F68
0x180019f60  test    eax, eax
0x180019f62  jns     loc_18001A009
0x180019f68  mov     edx, edi
0x180019f6a  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x180019f71  call    WiaTrace_TraceLog
0x180019f76  mov     rdx, rax; char *
0x180019f79  mov     rcx, r15; char *
0x180019f7c  mov     rbx, rax
0x180019f7f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180019f84  mov     rcx, rbx; this
0x180019f87  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180019f8c  mov     edx, edi
0x180019f8e  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x180019f95  call    WiaTrace_Trace
0x180019f9a  mov     ebx, 1
0x180019f9f  mov     [rsp+160h+lpMem], rax; lpMem
0x180019fa4  mov     r9d, ebx; int
0x180019fa7  mov     r8, r15; int
0x180019faa  call    WiaTrace_ProcessTrace_Ex
0x180019faf  mov     rcx, [rsp+160h+var_118]
0x180019fb4  jmp     short loc_18001A009
0x180019fb6  mov     edi, 80004003h
0x180019fbb  lea     rcx, aNotInCompatibi; "not in compatibility mode or called on "...
0x180019fc2  mov     edx, edi
0x180019fc4  call    WiaTrace_TraceLog
0x180019fc9  mov     rdx, rax; char *
0x180019fcc  mov     rcx, r15; char *
0x180019fcf  mov     rbx, rax
0x180019fd2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180019fd7  mov     rcx, rbx; this
0x180019fda  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180019fdf  mov     edx, edi
0x180019fe1  lea     rcx, aNotInCompatibi; "not in compatibility mode or called on "...
0x180019fe8  call    WiaTrace_Trace
0x180019fed  mov     ebx, 1
0x180019ff2  mov     [rsp+160h+lpMem], rax; lpMem
0x180019ff7  mov     r9d, ebx; int
0x180019ffa  mov     r8, r15; int
0x180019ffd  call    WiaTrace_ProcessTrace_Ex
0x18001a002  xor     ecx, ecx
0x18001a004  mov     [rsp+160h+var_118], rcx
0x18001a009  xor     r13d, r13d
0x18001a00c  mov     [rsp+160h+var_120], 0
0x18001a014  mov     [rbp+60h+var_CC], 0
0x18001a01b  xorps   xmm0, xmm0
0x18001a01e  lea     r12, qword_180082160
0x18001a025  movups  xmmword ptr [rsp+160h+pv], xmm0
0x18001a02a  test    edi, edi
0x18001a02c  js      loc_18001A291
0x18001a032  mov     rax, [rsi+40h]
0x18001a036  cmp     [rax+58h], r13
0x18001a03a  setnz   r13b
0x18001a03e  cmp     qword ptr [rax+60h], 0
0x18001a043  jz      short loc_18001A04E
0x18001a045  mov     r14d, ebx
0x18001a048  mov     [rsp+160h+var_110], ebx
0x18001a04c  jmp     short loc_18001A056
0x18001a04e  xor     r14d, r14d
0x18001a051  mov     [rsp+160h+var_110], r14d
0x18001a056  mov     rax, [rcx]
0x18001a059  lea     r9, [rsp+160h+var_120]
0x18001a05e  lea     r8, [rsp+160h+pv]
0x18001a063  mov     edx, ebx
0x18001a065  mov     rax, [rax+18h]
0x18001a069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a06e  test    eax, eax
0x18001a070  jnz     loc_18001A28A
0x18001a076  cmp     [rsp+160h+var_120], ebx
0x18001a07a  jnz     loc_18001A28A
0x18001a080  mov     edx, dword ptr [rsp+160h+pv+8]
0x18001a084  xor     ecx, ecx
0x18001a086  cmp     ecx, 35h ; '5'
0x18001a089  jnb     loc_18001A1F9
0x18001a08f  mov     eax, ecx
0x18001a091  shl     rax, 5
0x18001a095  cmp     [rax+r12+4], edx
0x18001a09a  jz      short loc_18001A0A0
0x18001a09c  add     ecx, ebx
0x18001a09e  jmp     short loc_18001A086
0x18001a0a0  movups  xmm0, xmmword ptr [rax+r12]
0x18001a0a5  movups  xmm1, xmmword ptr [rax+r12+10h]
0x18001a0ab  movd    eax, xmm0
0x18001a0af  cmp     eax, 4
0x18001a0b2  jnz     loc_18001A25B
0x18001a0b8  psrldq  xmm0, 8
0x18001a0bd  movd    eax, xmm0
0x18001a0c1  dec     eax
0x18001a0c3  test    eax, 0FFFFFFFDh
0x18001a0c8  jnz     loc_18001A25B
0x18001a0ce  movq    rax, xmm1
0x18001a0d3  shr     rax, 20h
0x18001a0d7  sub     eax, 4
0x18001a0da  test    eax, 0FFFFFFFBh
0x18001a0df  jnz     loc_18001A25B
0x18001a0e5  cmp     edx, 0C0Eh
0x18001a0eb  jnz     loc_18001A188
0x18001a0f1  xor     ecx, ecx
0x18001a0f3  mov     r9d, 2
0x18001a0f9  test    r13d, r13d
0x18001a0fc  mov     eax, r13d
0x18001a0ff  setnz   cl
0x18001a102  neg     eax
0x18001a104  mov     edx, ecx
0x18001a106  mov     eax, ecx
0x18001a108  sbb     r8d, r8d
0x18001a10b  and     r8d, 35h
0x18001a10f  test    r14d, r14d
0x18001a112  cmovnz  edx, r9d
0x18001a116  or      eax, r9d
0x18001a119  mov     [rsp+160h+var_130], edx; unsigned int
0x18001a11d  mov     r9d, r8d
0x18001a120  test    r14d, r14d
0x18001a123  cmovz   eax, ecx
0x18001a126  mov     rcx, [rsi+0D0h]; this
0x18001a12d  or      r9d, 0Ah
0x18001a131  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x18001a135  mov     dword ptr [rsp+160h+lpMem], edx; unsigned int
0x18001a139  test    r14d, r14d
0x18001a13c  mov     rdx, [rsi+40h]; struct CWiaItem *
0x18001a140  cmovz   r9d, r8d; unsigned int
0x18001a144  lea     r8, [rsp+160h+pv]; struct tagSTATPROPSTG *
0x18001a149  call    ?CopyFlagPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@KKKK@Z; CWiaItem::CopyFlagPropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong,ulong,ulong,ulong)
0x18001a14e  mov     edi, eax
0x18001a150  test    eax, eax
0x18001a152  jns     loc_18001A25B
0x18001a158  mov     edx, eax
0x18001a15a  lea     rcx, aWiaDpsDocument_0; "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES "...
0x18001a161  call    WiaTrace_TraceLog
0x18001a166  mov     rdx, rax; char *
0x18001a169  mov     rcx, r15; char *
0x18001a16c  mov     rbx, rax
0x18001a16f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001a174  mov     rcx, rbx; this
0x18001a177  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001a17c  lea     rcx, aWiaDpsDocument_0; "WIA_DPS_DOCUMENT_HANDLING_CAPABILITIES "...
0x18001a183  jmp     loc_18001A23F
0x18001a188  mov     rdx, [rsi+40h]; struct CWiaItem *
0x18001a18c  lea     r8, [rsp+160h+pv]; struct tagSTATPROPSTG *
0x18001a191  mov     rcx, [rsi+0D0h]; this
0x18001a198  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x18001a19d  mov     edi, eax
0x18001a19f  test    eax, eax
0x18001a1a1  jns     short loc_18001A1EA
0x18001a1a3  mov     edx, eax
0x18001a1a5  lea     rcx, aC4PropertyTran; "C4 property translation failed (0x%X)"
0x18001a1ac  call    WiaTrace_TraceLog
0x18001a1b1  mov     rdx, rax; char *
0x18001a1b4  mov     rcx, r15; char *
0x18001a1b7  mov     rbx, rax
0x18001a1ba  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001a1bf  mov     rcx, rbx; this
0x18001a1c2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001a1c7  mov     edx, edi
0x18001a1c9  lea     rcx, aC4PropertyTran; "C4 property translation failed (0x%X)"
0x18001a1d0  call    WiaTrace_Trace
0x18001a1d5  mov     ebx, 1
0x18001a1da  mov     [rsp+160h+lpMem], rax; lpMem
0x18001a1df  mov     r9d, ebx; int
0x18001a1e2  mov     r8, r15; int
0x18001a1e5  call    WiaTrace_ProcessTrace_Ex
0x18001a1ea  cmp     dword ptr [rsp+160h+pv+8], 0C17h
0x18001a1f2  jnz     short loc_18001A25B
0x18001a1f4  mov     [rbp+60h+var_CC], ebx
0x18001a1f7  jmp     short loc_18001A25B
0x18001a1f9  mov     rdx, [rsi+40h]; struct CWiaItem *
0x18001a1fd  lea     r8, [rsp+160h+pv]; struct tagSTATPROPSTG *
0x18001a202  mov     rcx, [rsi+0D0h]; this
0x18001a209  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x18001a20e  mov     edi, eax
0x18001a210  test    eax, eax
0x18001a212  jns     short loc_18001A25B
0x18001a214  mov     edx, eax
0x18001a216  lea     rcx, aC1PropertyCopy; "C1 property copy failed (0x%X)"
0x18001a21d  call    WiaTrace_TraceLog
0x18001a222  mov     rdx, rax; char *
0x18001a225  mov     rcx, r15; char *
0x18001a228  mov     rbx, rax
0x18001a22b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001a230  mov     rcx, rbx; this
0x18001a233  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001a238  lea     rcx, aC1PropertyCopy; "C1 property copy failed (0x%X)"
0x18001a23f  mov     edx, edi
0x18001a241  call    WiaTrace_Trace
0x18001a246  mov     ebx, 1
0x18001a24b  mov     [rsp+160h+lpMem], rax; lpMem
0x18001a250  mov     r9d, ebx; int
0x18001a253  mov     r8, r15; int
0x18001a256  call    WiaTrace_ProcessTrace_Ex
0x18001a25b  mov     rcx, [rsp+160h+pv]; pv
0x18001a260  test    rcx, rcx
0x18001a263  jz      short loc_18001A274
0x18001a265  call    cs:__imp_CoTaskMemFree
0x18001a26b  mov     [rsp+160h+pv], 0
0x18001a274  test    edi, edi
0x18001a276  js      short loc_18001A28A
0x18001a278  mov     rcx, [rsp+160h+var_118]
0x18001a27d  mov     [rsp+160h+var_120], 0
0x18001a285  jmp     loc_18001A056
0x18001a28a  mov     rcx, [rsp+160h+var_118]
0x18001a28f  jmp     short loc_18001A299
0x18001a291  xor     r14d, r14d
0x18001a294  mov     [rsp+160h+var_110], r14d
0x18001a299  test    rcx, rcx
0x18001a29c  jz      short loc_18001A2B3
0x18001a29e  mov     rax, [rcx]
0x18001a2a1  mov     rax, [rax+10h]
0x18001a2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2aa  mov     [rsp+160h+var_118], 0
0x18001a2b3  test    edi, edi
0x18001a2b5  js      short loc_18001A2C9
0x18001a2b7  lea     rcx, [rsi+8]
0x18001a2bb  mov     edx, ebx
0x18001a2bd  mov     rax, [rcx]
0x18001a2c0  mov     rax, [rax+48h]
0x18001a2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2c9  mov     rax, [rsi+40h]
0x18001a2cd  xor     r12d, r12d
0x18001a2d0  mov     r15, [rax+58h]
0x18001a2d4  test    r15, r15
0x18001a2d7  jz      loc_18001A399
0x18001a2dd  test    edi, edi
0x18001a2df  js      loc_18001A399
0x18001a2e5  lea     rcx, [r15+8]
0x18001a2e9  mov     rax, [rcx]
0x18001a2ec  lea     rdx, [rsp+160h+var_118]
0x18001a2f1  mov     rax, [rax+58h]
0x18001a2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2fa  mov     rcx, [rsp+160h+var_118]
0x18001a2ff  mov     edi, eax
0x18001a301  test    rcx, rcx
0x18001a304  jnz     short loc_18001A30D
0x18001a306  mov     edi, 8007000Eh
0x18001a30b  jmp     short loc_18001A315
0x18001a30d  test    eax, eax
0x18001a30f  jns     loc_18001A3E1
0x18001a315  mov     edx, edi
0x18001a317  lea     rcx, aFailedToGetPro_2; "failed to get property enumerator for A"...
0x18001a31e  call    WiaTrace_TraceLog
0x18001a323  mov     rdx, rax; char *
0x18001a326  lea     rcx, aCwiaitemInitro; "CWiaItem::InitRootItemXPProps"
0x18001a32d  mov     rbx, rax
0x18001a330  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001a335  mov     rcx, rbx; this
0x18001a338  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001a33d  mov     edx, edi
0x18001a33f  lea     rcx, aFailedToGetPro_2; "failed to get property enumerator for A"...
0x18001a346  call    WiaTrace_Trace
0x18001a34b  mov     ebx, 1
0x18001a350  mov     [rsp+160h+lpMem], rax; lpMem
0x18001a355  mov     r9d, ebx; int
0x18001a358  lea     r8, aCwiaitemInitro; "CWiaItem::InitRootItemXPProps"
0x18001a35f  call    WiaTrace_ProcessTrace_Ex
0x18001a364  mov     rcx, [rsp+160h+var_118]
0x18001a369  test    rcx, rcx
  ... truncated ...
```
