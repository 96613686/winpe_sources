# CWiaItem::InitChildItemXPProps(int)

- ea: `0x18001901c`
- end: `0x180019ea6`
- name: `?InitChildItemXPProps@CWiaItem@@QEAAJH@Z`
- size: `3722`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800552bc`
- `0x18006b040`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x180011a94`
- `0x180013bfc`
- `0x180017740`
- `0x180017e90`
- `0x18001901c`
- `0x18001ad9c`
- `0x18001d584`
- `0x18002bf9c`
- `0x18002de18`
- `0x18002def8`
- `0x180032520`
- `0x180033878`
- `0x180033cc0`
- `0x180034558`
- `0x180034658`
- `0x18005d87c`
- `0x180062bfc`
- `0x18007268c`
- `0x180072a80`
- `0x180072b30`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180019473`
- `OLEAUT32!__imp_SysAllocString` at `0x180019506`
- `OLEAUT32!__imp_SysAllocString` at `0x180019553`
- `OLEAUT32!__imp_SysAllocString` at `0x18001957d`
- `OLEAUT32!__imp_SysAllocString` at `0x180019473`
- `OLEAUT32!__imp_SysAllocString` at `0x180019506`
- `OLEAUT32!__imp_SysAllocString` at `0x180019553`
- `OLEAUT32!__imp_SysAllocString` at `0x18001957d`
- `OLEAUT32!__imp_SysFreeString` at `0x180019616`
- `OLEAUT32!__imp_SysFreeString` at `0x18001962f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001965e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001966c`
- `OLEAUT32!__imp_SysFreeString` at `0x180019616`
- `OLEAUT32!__imp_SysFreeString` at `0x18001962f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001965e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001966c`
- `ole32!CoTaskMemFree` at `0x180019415`
- `ole32!CoTaskMemFree` at `0x180019415`
- `ole32!PropVariantClear` at `0x180019643`
- `ole32!PropVariantClear` at `0x180019650`
- `ole32!PropVariantClear` at `0x180019d19`
- `ole32!PropVariantClear` at `0x180019643`
- `ole32!PropVariantClear` at `0x180019650`
- `ole32!PropVariantClear` at `0x180019d19`
- `ole32!CoTaskMemAlloc` at `0x1800198dd`
- `ole32!CoTaskMemAlloc` at `0x1800198dd`

## string_xrefs

- `0x1800190cb`: `not in compatibility mode or called on non XP A-AIT root item (0x%X)`
- `0x1800190f1`: `not in compatibility mode or called on non XP A-AIT root item (0x%X)`
- `0x1800195c5`: `cannot update item name (0x%X)`
- `0x1800195e9`: `cannot update item name (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitChildItemXPProps(CWiaItem *this, int a2)
{
  unsigned int v2; // ebx
  struct tagWiaTraceData_Type *v5; // rax
  char *v6; // rdx
  unsigned int v7; // r8d
  int DocumentHandling; // edi
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  CWiaPropStg *v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rcx
  unsigned int i; // edx
  __int64 v23; // rcx
  CWiaItem *v24; // rcx
  __int64 v25; // rsi
  int v26; // eax
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  __m128i v32; // xmm0
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  OLECHAR *v38; // r12
  BSTR v39; // rax
  OLECHAR *v40; // r13
  OLECHAR *v41; // rax
  __int64 v42; // rcx
  char *v43; // rbx
  void *v44; // rdx
  void **v45; // rax
  void *v46; // rdx
  __int64 v47; // rcx
  _DWORD *v48; // r12
  _QWORD *v49; // r13
  unsigned __int64 v50; // rdi
  int v51; // r10d
  __int64 j; // rcx
  unsigned int Data1; // r11d
  int v54; // r9d
  __int64 v55; // r8
  unsigned int k; // edx
  __int64 v57; // rax
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rbx
  GUID *v62; // rax
  unsigned __int64 v63; // rdx
  unsigned int v64; // ebx
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  int v69; // r10d
  int v70; // r12d
  int v71; // r11d
  __int64 v72; // rax
  signed int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // r9
  __int64 v79; // r8
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rcx
  __int64 m; // rsi
  CWiaItem *v88; // rcx
  char *v89; // rbx
  void *v90; // rdx
  void **v91; // rax
  void *v92; // rdx
  __int64 v93; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  unsigned int v96; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v97; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v98; // [rsp+40h] [rbp-C8h]
  int v99; // [rsp+44h] [rbp-C4h]
  __int64 v100; // [rsp+48h] [rbp-C0h]
  __int64 v101; // [rsp+50h] [rbp-B8h] BYREF
  int v102; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v103; // [rsp+5Ch] [rbp-ACh] BYREF
  int v104; // [rsp+60h] [rbp-A8h]
  unsigned int v105; // [rsp+64h] [rbp-A4h]
  int pv; // [rsp+68h] [rbp-A0h]
  struct tagSTATPROPSTG pv_8; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v108; // [rsp+80h] [rbp-88h]
  _BYTE v109[96]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v110; // [rsp+E8h] [rbp-20h] BYREF
  _QWORD v111[7]; // [rsp+F8h] [rbp-10h]
  __int128 v112; // [rsp+130h] [rbp+28h]
  __int64 v113; // [rsp+140h] [rbp+38h]
  OLECHAR *psz; // [rsp+1F0h] [rbp+E8h]
  _WIA_FORMAT_INFO v115; // [rsp+218h] [rbp+110h] BYREF
  int v116; // [rsp+22Ch] [rbp+124h]
  int v117; // [rsp+230h] [rbp+128h]
  int v118; // [rsp+234h] [rbp+12Ch]
  BSTR bstrString[2]; // [rsp+238h] [rbp+130h] BYREF
  const wchar_t *v120; // [rsp+248h] [rbp+140h]
  BSTR v121[2]; // [rsp+250h] [rbp+148h] BYREF
  const wchar_t *v122; // [rsp+260h] [rbp+158h]
  const wchar_t *v123; // [rsp+268h] [rbp+160h]
  const wchar_t *v124; // [rsp+270h] [rbp+168h]
  int v125; // [rsp+278h] [rbp+170h] BYREF
  _DWORD v126[30]; // [rsp+280h] [rbp+178h] BYREF
  __int16 v127; // [rsp+2F8h] [rbp+1F0h] BYREF
  int v128; // [rsp+300h] [rbp+1F8h]
  __int16 v129; // [rsp+310h] [rbp+208h]
  int v130; // [rsp+318h] [rbp+210h]
  __int16 v131; // [rsp+328h] [rbp+220h]
  signed int v132; // [rsp+330h] [rbp+228h]
  const unsigned __int64 *v133; // [rsp+348h] [rbp+240h] BYREF
  unsigned int v134; // [rsp+350h] [rbp+248h]
  int v135; // [rsp+354h] [rbp+24Ch]
  _DWORD *v136; // [rsp+358h] [rbp+250h]
  int v137; // [rsp+370h] [rbp+268h]
  __int16 v138; // [rsp+374h] [rbp+26Ch]
  int v139; // [rsp+398h] [rbp+290h]
  __int16 v140; // [rsp+39Ch] [rbp+294h]
  unsigned int v141; // [rsp+3A0h] [rbp+298h]
  GUID v142; // [rsp+3A4h] [rbp+29Ch]
  _QWORD *v143; // [rsp+3B8h] [rbp+2B0h]
  int v144; // [rsp+3C0h] [rbp+2B8h]
  __int16 v145; // [rsp+3C4h] [rbp+2BCh]

  v2 = 0;
  if ( a2 )
    v5 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::InitChildItemXPProps - refresh");
  else
    v5 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::InitChildItemXPProps");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)&v127, v6, v7, "CWiaItem::InitChildItemXPProps", lpMem, v5);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)&v127);
  if ( *((_QWORD *)this + 8)
    && *((_QWORD *)this + 10)
    && (*((_QWORD *)this + 11) || *((_QWORD *)this + 12))
    && *((_DWORD *)this + 26) == 2 )
  {
    DocumentHandling = 0;
  }
  else
  {
    DocumentHandling = -2147467261;
    v9 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non XP A-AIT root item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void **)WiaTrace_Trace("not in compatibility mode or called on non XP A-AIT root item (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"CWiaItem::InitChildItemXPProps", 1, v11);
    v2 = 0;
  }
  if ( !a2 )
  {
LABEL_27:
    if ( DocumentHandling < 0 )
      goto LABEL_18;
    goto LABEL_28;
  }
  if ( DocumentHandling < 0 )
  {
LABEL_18:
    v20 = 0;
    v101 = 0;
    v21 = 0;
    goto LABEL_19;
  }
  v14 = *(CWiaPropStg **)(*((_QWORD *)this + 10) + 216LL);
  if ( *(_QWORD *)v14 && *((_QWORD *)v14 + 1) && *((_QWORD *)v14 + 2) )
  {
    DocumentHandling = CWiaPropStg::ReleaseBackups(v14);
    if ( DocumentHandling < 0 )
    {
      v15 = (char *)WiaTrace_TraceLog("failed to release property storage backups for the XP A-AIT child item (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v17 = (void **)WiaTrace_Trace(
                       "failed to release property storage backups for the XP A-AIT child item (0x%X)",
                       DocumentHandling);
      WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"CWiaItem::InitChildItemXPProps", 1, v17);
      v2 = 0;
      goto LABEL_18;
    }
    goto LABEL_27;
  }
LABEL_28:
  v24 = (CWiaItem *)*((_QWORD *)this + 26);
  v97 = 0;
  DocumentHandling = CWiaItem::GetDocumentHandling(v24, &v97, 1);
  if ( DocumentHandling < 0 )
    goto LABEL_18;
  v25 = *((_QWORD *)this + 8);
  if ( (v97 & 1) != 0 )
    v20 = *(_QWORD *)(v25 + 88);
  else
    v20 = *(_QWORD *)(v25 + 96);
  v101 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v20 + 8) + 88LL))(v20 + 8, &v101);
  v21 = v101;
  DocumentHandling = v26;
  if ( v101 )
  {
    if ( v26 >= 0 )
      goto LABEL_19;
  }
  else
  {
    DocumentHandling = -2147024882;
  }
  v27 = (char *)WiaTrace_TraceLog("failed to get property enumerator for root properties to translate (0x%X)");
  WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v27);
  WiaTrcLib::Free((WiaTrcLib *)v27, v28);
  v29 = (void **)WiaTrace_Trace(
                   "failed to get property enumerator for root properties to translate (0x%X)",
                   DocumentHandling);
  WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"CWiaItem::InitChildItemXPProps", 1, v29);
  v21 = v101;
  v2 = 0;
LABEL_19:
  v102 = 0;
  pv = 0;
  v99 = 0;
  v97 = 0;
  v100 = 0;
  pv_8 = 0;
  if ( DocumentHandling >= 0 )
  {
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct tagSTATPROPSTG *, int *))(*(_QWORD *)v21 + 24LL))(
               v21,
               1,
               &pv_8,
               &v102)
         && v102 == 1 )
    {
      for ( i = 0; i < 0x35; ++i )
      {
        v23 = 4LL * i;
        if ( LODWORD(qword_180082160[v23 + 2]) == pv_8.propid
          && (unsigned int)(HIDWORD(qword_180082160[v23 + 2]) - 7) <= 1 )
        {
          v32 = *(__m128i *)&qword_180082160[v23];
          if ( (unsigned int)(_mm_cvtsi128_si32(v32) - 4) <= 1
            && (unsigned int)(_mm_cvtsi128_si32(_mm_srli_si128(v32, 8)) - 2) <= 1
            && (unsigned int)(HIDWORD(qword_180082160[v23 + 2]) - 7) <= 1
            && (((pv_8.propid - 4105) & 0xFFFFFFFC) != 0 || pv_8.propid == 4107) )
          {
            DocumentHandling = CWiaItem::CopyPropertyFrom(*((CWiaItem **)this + 10), (struct CWiaItem *)v20, &pv_8);
            if ( DocumentHandling >= 0 )
            {
              switch ( pv_8.propid )
              {
                case 0x1016u:
                  pv = 1;
                  break;
                case 0x100Fu:
                  v99 = 1;
                  break;
                case 0x1010u:
                  v97 = 1;
                  *(_DWORD *)(v20 + 236) = 0;
                  break;
                case 0x1012u:
                  HIDWORD(v100) = 1;
                  *(_DWORD *)(v20 + 244) = 0;
                  break;
                case 0x1011u:
                  LODWORD(v100) = 1;
                  *(_DWORD *)(v20 + 240) = 0;
                  break;
              }
            }
            else
            {
              v33 = (char *)WiaTrace_TraceLog("C4 property translation failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v33);
              WiaTrcLib::Free((WiaTrcLib *)v33, v34);
              v35 = (void **)WiaTrace_Trace("C4 property translation failed (0x%X)", DocumentHandling);
              WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"CWiaItem::InitChildItemXPProps", 1, v35);
              v2 = 0;
            }
          }
          break;
        }
      }
      if ( pv_8.lpwstrName )
      {
        CoTaskMemFree(pv_8.lpwstrName);
        pv_8.lpwstrName = 0;
      }
      if ( DocumentHandling < 0 )
        break;
      v21 = v101;
      v102 = 0;
    }
    v21 = v101;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v101 = 0;
  }
  if ( DocumentHandling >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL) + 72LL))(
      *((_QWORD *)this + 10) + 8LL,
      1);
    v38 = SysAllocString(L"Scan");
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
      &v110,
      *(_QWORD *)(*((_QWORD *)this + 8) + 192LL));
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v133, L"\\");
    CSimpleStringBase<unsigned short>::Concat(&v110, &v133);
    v133 = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(&v133);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v133, v38);
    CSimpleStringBase<unsigned short>::Concat(&v110, &v133);
    v133 = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(&v133);
    v39 = SysAllocString(psz);
    *(_DWORD *)v115.guidFormatID.Data4 = 4098;
    v40 = v39;
    v120 = 0;
    v122 = 0;
    *(_OWORD *)bstrString = 0;
    v115.guidFormatID.Data1 = 1;
    LOWORD(bstrString[0]) = 8;
    *(_OWORD *)v121 = 0;
    v41 = SysAllocString(v38);
    v115.lTymed = 1;
    bstrString[1] = v41;
    LOWORD(v121[0]) = 8;
    v117 = 4099;
    v121[1] = SysAllocString(v40);
    v42 = **(_QWORD **)(*((_QWORD *)this + 10) + 216LL);
    DocumentHandling = (*(__int64 (__fastcall **)(__int64, __int64, _WIA_FORMAT_INFO *, BSTR *, int))(*(_QWORD *)v42 + 32LL))(
                         v42,
                         2,
                         &v115,
                         bstrString,
                         4098);
    if ( DocumentHandling < 0 )
    {
      v43 = (char *)WiaTrace_TraceLog("cannot update item name (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v43);
      WiaTrcLib::Free((WiaTrcLib *)v43, v44);
      v45 = (void **)WiaTrace_Trace("cannot update item name (0x%X)", DocumentHandling);
      WiaTrace_ProcessTrace_Ex(v47, v46, (void *)"CWiaItem::InitChildItemXPProps", 1, v45);
      v2 = 0;
    }
    if ( bstrString[1] )
    {
      SysFreeString(bstrString[1]);
      bstrString[1] = 0;
    }
    if ( v121[1] )
    {
      SysFreeString(v121[1]);
      v121[1] = 0;
    }
    PropVariantClear((PROPVARIANT *)bstrString);
    PropVariantClear((PROPVARIANT *)v121);
    if ( v38 )
      SysFreeString(v38);
    if ( v40 )
      SysFreeString(v40);
    *(_QWORD *)&v110 = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(&v110);
    if ( DocumentHandling >= 0 )
    {
      CEnumWiaFormatInfo::CEnumWiaFormatInfo((CEnumWiaFormatInfo *)v109);
      v96 = 0;
      memset(&v115, 0, sizeof(v115));
      v108 = 0;
      v105 = 0;
      v48 = 0;
      v98 = 0;
      v49 = 0;
      if ( CEnumWiaFormatInfo::Initialize((CEnumWiaFormatInfo *)v109, (struct CWiaItem *)v20, 0) < 0 )
        goto LABEL_101;
      if ( (int)CEnumWiaFormatInfo::GetCount((CEnumWiaFormatInfo *)v109, &v96) < 0 )
        goto LABEL_101;
      v50 = v96;
      v108 = operator new[](saturated_mul(v96, 4u));
      v48 = v108;
      if ( !v108 )
        goto LABEL_101;
      v49 = operator new[](saturated_mul(v50, 0x10u));
      if ( !v49 )
        goto LABEL_101;
      v103 = 0;
      CEnumWiaFormatInfo::Reset((CEnumWiaFormatInfo *)v109);
      v104 = 0;
      if ( !v96 )
        goto LABEL_101;
      while ( 1 )
      {
        DocumentHandling = CEnumWiaFormatInfo::Next((CEnumWiaFormatInfo *)v109, 1u, &v115, &v103);
        if ( DocumentHandling < 0 )
          break;
        if ( v103 != 1 )
        {
          DocumentHandling = -2147418113;
          break;
        }
        v51 = 0;
        for ( j = 0; (unsigned int)j < v2; j = (unsigned int)(j + 1) )
        {
          if ( v48[j] == v115.lTymed )
          {
            v51 = 1;
            break;
          }
        }
        Data1 = v115.guidFormatID.Data1;
        v54 = 0;
        v55 = v98;
        for ( k = 0; k < v98; ++k )
        {
          v57 = v49[2 * k] - *(_QWORD *)&v115.guidFormatID.Data1;
          if ( !v57 )
            v57 = v49[2 * k + 1] - *(_QWORD *)v115.guidFormatID.Data4;
          if ( !v57 )
          {
            v54 = 1;
            break;
          }
        }
        if ( !v51 )
        {
          v58 = v2++;
          v105 = v2;
          v48[v58] = v115.lTymed;
        }
        if ( !v54 )
        {
          v59 = *(_DWORD *)&v115.guidFormatID.Data4[4];
          v60 = 2 * v55;
          LODWORD(v55) = v55 + 1;
          v98 = v55;
          *(_QWORD *)((char *)&v49[v60] + 4) = *(_QWORD *)&v115.guidFormatID.Data2;
          HIDWORD(v49[v60 + 1]) = v59;
          LODWORD(v49[v60]) = Data1;
        }
        if ( ++v104 >= v96 )
          goto LABEL_99;
      }
      LODWORD(v55) = v98;
LABEL_99:
      if ( !v2 || !(_DWORD)v55 )
LABEL_101:
        DocumentHandling = -2147418113;
      LOWORD(v110) = 0;
      memset_0((char *)&v110 + 2, 0, 0xBEu);
      v125 = 0;
      memset_0(v126, 0, sizeof(v126));
      LODWORD(v133) = 0;
      memset_0((char *)&v133 + 4, 0, 0x13Cu);
      v61 = 0;
      v115.guidFormatID = 0;
      while ( (unsigned int)v61 < 2 )
      {
        v62 = (GUID *)CoTaskMemAlloc(0x10u);
        *((_QWORD *)&v115.guidFormatID.Data1 + v61) = v62;
        if ( !v62 )
        {
          DocumentHandling = -2147024882;
          break;
        }
        *v62 = WiaImgFmt_BMP;
        v61 = (unsigned int)(v61 + 1);
      }
      v126[0] = 4108;
      v111[0] = 0;
      v110 = 0;
      v136 = v48;
      v126[4] = 4105;
      LOWORD(v110) = 3;
      v63 = 35;
      DWORD2(v110) = 2;
      v135 = 2;
      v134 = v105;
      v125 = 1;
      v111[3] = 0;
      v64 = 3;
      v111[1] = 72;
      v111[2] = *(_QWORD *)&v115.guidFormatID.Data1;
      v111[6] = 0;
      v111[5] = *(_QWORD *)v115.guidFormatID.Data4;
      v141 = v98;
      LODWORD(v133) = 35;
      WORD2(v133) = 3;
      v126[2] = 1;
      v137 = 9;
      v138 = 72;
      v111[4] = 72;
      v126[6] = 1;
      v126[8] = 4106;
      v139 = 35;
      v140 = 72;
      v143 = v49;
      v142 = WiaImgFmt_BMP;
      if ( !pv )
      {
        v112 = 0;
        LOWORD(v112) = 3;
        v113 = 0;
        v64 = 4;
        DWORD2(v112) = 0x10000;
        v126[10] = 1;
        v126[12] = 4118;
        v144 = 9;
        v145 = 3;
      }
      if ( !v99 )
      {
        v65 = v64;
        v63 = 0;
        v66 = 3LL * v64;
        *(_OWORD *)&v111[v66 - 2] = 0;
        v111[v66] = 0;
        LOWORD(v111[v66 - 2]) = 3;
        LODWORD(v111[v66 - 1]) = 0;
        v67 = 2LL * v64++;
        v126[2 * v67] = 1;
        v126[2 * v67] = 4111;
        v68 = 5 * v65;
        LODWORD((&v133)[v68]) = 9;
        WORD2((&v133)[v68]) = 3;
      }
      v69 = 0;
      v70 = 0;
      v99 = 0;
      v96 = 0;
      if ( !v97 || (v71 = HIDWORD(v100)) == 0 || !(_DWORD)v100 )
      {
        v72 = *((_QWORD *)this + 10);
        LODWORD(bstrString[0]) = 1;
        LODWORD(v120) = 1;
        LODWORD(v121[1]) = 1;
        LODWORD(bstrString[1]) = 6151;
        LODWORD(v121[0]) = 6152;
        LODWORD(v122) = 4104;
        if ( (*(int (__fastcall **)(_QWORD, __int64, BSTR *, __int16 *))(***(_QWORD ***)(v72 + 216) + 24LL))(
               **(_QWORD **)(v72 + 216),
               3,
               bstrString,
               &v127) < 0 )
        {
          v69 = 0;
          v73 = 0;
        }
        else
        {
          v73 = v96;
          if ( v127 == 3 )
            v70 = v128;
          v69 = v99;
          if ( v129 == 3 )
            v69 = v130;
          if ( v131 == 3 )
            v73 = v132;
          v96 = v73;
        }
        v71 = HIDWORD(v100);
        if ( !v97 )
        {
          v74 = v64;
          v63 = 0;
          *(_DWORD *)(v20 + 236) = 1;
          v75 = 3LL * v64;
          *(_OWORD *)&v111[v75 - 2] = 0;
          v111[v75] = 0;
          LOWORD(v111[v75 - 2]) = 3;
          LODWORD(v111[v75 - 1]) = v70;
          v76 = 2LL * v64++;
          v126[2 * v76] = 1;
          v126[2 * v76] = 4112;
          v77 = 5 * v74;
          LODWORD((&v133)[v77]) = 9;
          WORD2((&v133)[v77]) = 3;
          v73 = v96;
        }
        if ( !(_DWORD)v100 )
        {
          v78 = v64;
          v79 = 3LL * v64;
          *(_OWORD *)&v111[v79 - 2] = 0;
          v111[v79] = 0;
          LOWORD(v111[v79 - 2]) = 3;
          v63 = (v70 * (__int64)v73 + 31) % 32;
          LODWORD(v111[v79 - 1]) = 4 * ((v70 * (__int64)v73 + 31) / 32);
          v80 = 2LL * v64;
          *(_DWORD *)(v20 + 240) = 1;
          ++v64;
          v126[2 * v80] = 1;
          v126[2 * v80] = 4113;
          v81 = 5 * v78;
          LODWORD((&v133)[v81]) = 9;
          WORD2((&v133)[v81]) = 3;
        }
      }
      if ( !v71 )
      {
        v82 = v64;
        v63 = 0;
        *(_DWORD *)(v20 + 244) = 1;
        v83 = 3LL * v64;
        *(_OWORD *)&v111[v83 - 2] = 0;
        v111[v83] = 0;
        LOWORD(v111[v83 - 2]) = 3;
        LODWORD(v111[v83 - 1]) = v69;
        v84 = 2LL * v64++;
        v126[2 * v84] = 1;
        v126[2 * v84] = 4114;
        v85 = 5 * v82;
        LODWORD((&v133)[v85]) = 9;
        WORD2((&v133)[v85]) = 3;
      }
      if ( DocumentHandling >= 0 )
      {
        DocumentHandling = wiasSetItemPropAttribs(*((CWiaItem **)this + 10));
        if ( DocumentHandling >= 0 )
        {
          v86 = **(_QWORD **)(*((_QWORD *)this + 10) + 216LL);
          DocumentHandling = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int128 *, int))(*(_QWORD *)v86 + 32LL))(
                               v86,
                               v64,
                               &v125,
                               &v110,
                               4098);
        }
      }
      for ( m = 0; (unsigned int)m < v64; m = (unsigned int)(m + 1) )
        PropVariantClear((PROPVARIANT *)&v111[3 * m - 2]);
      if ( DocumentHandling >= 0 )
      {
        v88 = (CWiaItem *)*((_QWORD *)this + 10);
        bstrString[0] = L"Media Type";
        v115.guidFormatID.Data1 = 4108;
        bstrString[1] = L"Preferred Format";
        *(_DWORD *)&v115.guidFormatID.Data2 = 4105;
        v120 = L"Format";
        *(_DWORD *)v115.guidFormatID.Data4 = 4106;
        v121[0] = L"Buffer Size";
        v121[1] = L"Planar";
        v122 = L"Pixels Per Line";
        v123 = L"Number of Lines";
        v124 = L"Bytes Per Line";
        *(_DWORD *)&v115.guidFormatID.Data4[4] = 4118;
        v115.lTymed = 4111;
        v116 = 4112;
        v117 = 4114;
        v118 = 4113;
        DocumentHandling = wiasSetItemPropNames(v88, 8, &v115.guidFormatID.Data1, bstrString);
      }
      if ( v108 )
        operator delete(v108, v63);
      if ( v49 )
        operator delete(v49, v63);
      if ( DocumentHandling < 0 )
      {
        v89 = (char *)WiaTrace_TraceLog("translation for additional properties (tymed, format) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemXPProps", v89);
        WiaTrcLib::Free((WiaTrcLib *)v89, v90);
        v91 = (void **)WiaTrace_Trace(
                         "translation for additional properties (tymed, format) failed (0x%X)",
                         DocumentHandling);
        WiaTrace_ProcessTrace_Ex(v93, v92, (void *)"CWiaItem::InitChildItemXPProps", 1, v91);
      }
      CEnumWiaFormatInfo::~CEnumWiaFormatInfo((CEnumWiaFormatInfo *)v109);
    }
  }
  return (unsigned int)DocumentHandling;
}

```

## disassembly

```asm
0x18001901c  mov     rax, rsp
0x18001901f  push    rbp
0x180019020  push    rbx
0x180019021  push    rsi
0x180019022  push    rdi
0x180019023  push    r12
0x180019025  push    r13
0x180019027  push    r14
0x180019029  push    r15
0x18001902b  lea     rbp, [rax-3E8h]
0x180019032  sub     rsp, 4A8h
0x180019039  movaps  xmmword ptr [rax-58h], xmm6
0x18001903d  mov     rax, cs:__security_cookie
0x180019044  xor     rax, rsp
0x180019047  mov     [rbp+3E0h+var_60], rax
0x18001904e  xor     ebx, ebx
0x180019050  mov     esi, edx
0x180019052  mov     r15, rcx
0x180019055  test    edx, edx
0x180019057  jz      short loc_18001906E
0x180019059  lea     rcx, aCwiaitemInitch_0; "CWiaItem::InitChildItemXPProps - refres"...
0x180019060  call    WiaTrace_Trace
0x180019065  lea     r14, aCwiaitemInitch; "CWiaItem::InitChildItemXPProps"
0x18001906c  jmp     short loc_18001907D
0x18001906e  lea     r14, aCwiaitemInitch; "CWiaItem::InitChildItemXPProps"
0x180019075  mov     rcx, r14
0x180019078  call    WiaTrace_Trace
0x18001907d  mov     r9, r14; char *
0x180019080  mov     [rsp+4E0h+var_4B8], rax; struct tagWiaTraceData_Type *
0x180019085  lea     rcx, [rbp+3E0h+var_1F0]; this
0x18001908c  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x180019091  lea     rcx, [rbp+3E0h+var_1F0]; this
0x180019098  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18001909d  mov     r12d, 1
0x1800190a3  cmp     [r15+40h], rbx
0x1800190a7  jz      short loc_1800190C6
0x1800190a9  cmp     [r15+50h], rbx
0x1800190ad  jz      short loc_1800190C6
0x1800190af  cmp     [r15+58h], rbx
0x1800190b3  jnz     short loc_1800190BB
0x1800190b5  cmp     [r15+60h], rbx
0x1800190b9  jz      short loc_1800190C6
0x1800190bb  cmp     dword ptr [r15+68h], 2
0x1800190c0  jnz     short loc_1800190C6
0x1800190c2  mov     edi, ebx
0x1800190c4  jmp     short loc_18001910F
0x1800190c6  mov     edi, 80004003h
0x1800190cb  lea     rcx, aNotInCompatibi; "not in compatibility mode or called on "...
0x1800190d2  mov     edx, edi
0x1800190d4  call    WiaTrace_TraceLog
0x1800190d9  mov     rdx, rax; char *
0x1800190dc  mov     rcx, r14; char *
0x1800190df  mov     rbx, rax
0x1800190e2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800190e7  mov     rcx, rbx; this
0x1800190ea  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800190ef  mov     edx, edi
0x1800190f1  lea     rcx, aNotInCompatibi; "not in compatibility mode or called on "...
0x1800190f8  call    WiaTrace_Trace
0x1800190fd  mov     r9d, r12d; int
0x180019100  mov     [rsp+4E0h+lpMem], rax; lpMem
0x180019105  mov     r8, r14; int
0x180019108  call    WiaTrace_ProcessTrace_Ex
0x18001910d  xor     ebx, ebx
0x18001910f  test    esi, esi
0x180019111  jz      loc_18001922F
0x180019117  test    edi, edi
0x180019119  js      short loc_180019196
0x18001911b  mov     rax, [r15+50h]
0x18001911f  mov     rcx, [rax+0D8h]; this
0x180019126  cmp     [rcx], rbx
0x180019129  jz      loc_180019237
0x18001912f  cmp     [rcx+8], rbx
0x180019133  jz      loc_180019237
0x180019139  cmp     [rcx+10h], rbx
0x18001913d  jz      loc_180019237
0x180019143  call    ?ReleaseBackups@CWiaPropStg@@QEAAJXZ; CWiaPropStg::ReleaseBackups(void)
0x180019148  mov     edi, eax
0x18001914a  test    eax, eax
0x18001914c  jns     loc_18001922F
0x180019152  mov     edx, eax
0x180019154  lea     rcx, aFailedToReleas; "failed to release property storage back"...
0x18001915b  call    WiaTrace_TraceLog
0x180019160  mov     rdx, rax; char *
0x180019163  mov     rcx, r14; char *
0x180019166  mov     rbx, rax
0x180019169  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001916e  mov     rcx, rbx; this
0x180019171  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180019176  mov     edx, edi
0x180019178  lea     rcx, aFailedToReleas; "failed to release property storage back"...
0x18001917f  call    WiaTrace_Trace
0x180019184  mov     r9d, r12d; int
0x180019187  mov     [rsp+4E0h+lpMem], rax; lpMem
0x18001918c  mov     r8, r14; int
0x18001918f  call    WiaTrace_ProcessTrace_Ex
0x180019194  xor     ebx, ebx
0x180019196  mov     rsi, rbx
0x180019199  mov     qword ptr [rsp+4E0h+var_498], rbx
0x18001919e  mov     rcx, rbx
0x1800191a1  mov     [rsp+4E0h+var_490], ebx
0x1800191a5  xorps   xmm0, xmm0
0x1800191a8  mov     dword ptr [rsp+4E0h+pv], ebx
0x1800191ac  mov     [rsp+4E0h+var_4A4], ebx
0x1800191b0  mov     [rsp+4E0h+var_4AC], ebx
0x1800191b4  mov     dword ptr [rsp+4E0h+var_4A0+4], ebx
0x1800191b8  mov     dword ptr [rsp+4E0h+var_4A0], ebx
0x1800191bc  movups  xmmword ptr [rsp+4E0h+pv+8], xmm0
0x1800191c1  test    edi, edi
0x1800191c3  js      loc_180019437
0x1800191c9  lea     r13, qword_180082160
0x1800191d0  mov     rax, [rcx]
0x1800191d3  lea     r9, [rsp+4E0h+var_490]
0x1800191d8  lea     r8, [rsp+4E0h+pv+8]
0x1800191dd  mov     edx, r12d
0x1800191e0  mov     rax, [rax+18h]
0x1800191e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191e9  test    eax, eax
0x1800191eb  jnz     loc_180019432
0x1800191f1  cmp     [rsp+4E0h+var_490], r12d
0x1800191f6  jnz     loc_180019432
0x1800191fc  mov     r8d, dword ptr [rsp+4E0h+var_470]
0x180019201  mov     edx, ebx
0x180019203  cmp     edx, 35h ; '5'
0x180019206  jnb     loc_18001940B
0x18001920c  mov     ecx, edx
0x18001920e  shl     rcx, 5
0x180019212  cmp     [rcx+r13+10h], r8d
0x180019217  jnz     short loc_18001922A
0x180019219  mov     eax, [rcx+r13+14h]
0x18001921e  sub     eax, 7
0x180019221  cmp     eax, r12d
0x180019224  jbe     loc_1800192F4
0x18001922a  add     edx, r12d
0x18001922d  jmp     short loc_180019203
0x18001922f  test    edi, edi
0x180019231  js      loc_180019196
0x180019237  mov     rcx, [r15+0D0h]; this
0x18001923e  lea     rdx, [rsp+4E0h+var_4AC]; unsigned int *
0x180019243  mov     r8d, r12d; int
0x180019246  mov     [rsp+4E0h+var_4AC], ebx
0x18001924a  call    ?GetDocumentHandling@CWiaItem@@QEAAJAEAKH@Z; CWiaItem::GetDocumentHandling(ulong &,int)
0x18001924f  mov     edi, eax
0x180019251  test    eax, eax
0x180019253  js      loc_180019196
0x180019259  mov     rax, rbx
0x18001925c  mov     rsi, [r15+40h]
0x180019260  test    byte ptr [rsp+4E0h+var_4AC], r12b
0x180019265  jz      short loc_18001926D
0x180019267  mov     rsi, [rsi+58h]
0x18001926b  jmp     short loc_180019271
0x18001926d  mov     rsi, [rsi+60h]
0x180019271  mov     qword ptr [rsp+4E0h+var_498], rax
0x180019276  lea     rcx, [rsi+8]
0x18001927a  mov     rax, [rcx]
0x18001927d  lea     rdx, [rsp+4E0h+var_498]
0x180019282  mov     rax, [rax+58h]
0x180019286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928b  mov     rcx, qword ptr [rsp+4E0h+var_498]
0x180019290  mov     edi, eax
0x180019292  test    rcx, rcx
0x180019295  jnz     short loc_18001929E
0x180019297  mov     edi, 8007000Eh
0x18001929c  jmp     short loc_1800192A6
0x18001929e  test    eax, eax
0x1800192a0  jns     loc_1800191A1
0x1800192a6  mov     edx, edi
0x1800192a8  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x1800192af  call    WiaTrace_TraceLog
0x1800192b4  mov     rdx, rax; char *
0x1800192b7  mov     rcx, r14; char *
0x1800192ba  mov     rbx, rax
0x1800192bd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800192c2  mov     rcx, rbx; this
0x1800192c5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800192ca  mov     edx, edi
0x1800192cc  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x1800192d3  call    WiaTrace_Trace
0x1800192d8  mov     r9d, r12d; int
0x1800192db  mov     [rsp+4E0h+lpMem], rax; lpMem
0x1800192e0  mov     r8, r14; int
0x1800192e3  call    WiaTrace_ProcessTrace_Ex
0x1800192e8  mov     rcx, qword ptr [rsp+4E0h+var_498]
0x1800192ed  xor     ebx, ebx
0x1800192ef  jmp     loc_1800191A1
0x1800192f4  movups  xmm0, xmmword ptr [rcx+r13]
0x1800192f9  movups  xmm1, xmmword ptr [rcx+r13+10h]
0x1800192ff  movd    eax, xmm0
0x180019303  add     eax, 0FFFFFFFCh
0x180019306  cmp     eax, r12d
0x180019309  ja      loc_18001940B
0x18001930f  psrldq  xmm0, 8
0x180019314  movd    eax, xmm0
0x180019318  add     eax, 0FFFFFFFEh
0x18001931b  cmp     eax, r12d
0x18001931e  ja      loc_18001940B
0x180019324  movq    rax, xmm1
0x180019329  shr     rax, 20h
0x18001932d  sub     eax, 7
0x180019330  cmp     eax, r12d
0x180019333  ja      loc_18001940B
0x180019339  lea     eax, [r8-1009h]
0x180019340  test    eax, 0FFFFFFFCh
0x180019345  jnz     short loc_180019354
0x180019347  cmp     r8d, 100Bh
0x18001934e  jnz     loc_18001940B
0x180019354  mov     rcx, [r15+50h]; this
0x180019358  lea     r8, [rsp+4E0h+pv+8]; struct tagSTATPROPSTG *
0x18001935d  mov     rdx, rsi; struct CWiaItem *
0x180019360  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x180019365  mov     edi, eax
0x180019367  test    eax, eax
0x180019369  jns     short loc_1800193B1
0x18001936b  mov     edx, eax
0x18001936d  lea     rcx, aC4PropertyTran; "C4 property translation failed (0x%X)"
0x180019374  call    WiaTrace_TraceLog
0x180019379  mov     rdx, rax; char *
0x18001937c  mov     rcx, r14; char *
0x18001937f  mov     rbx, rax
0x180019382  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180019387  mov     rcx, rbx; this
0x18001938a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001938f  mov     edx, edi
0x180019391  lea     rcx, aC4PropertyTran; "C4 property translation failed (0x%X)"
0x180019398  call    WiaTrace_Trace
0x18001939d  mov     r9d, r12d; int
0x1800193a0  mov     [rsp+4E0h+lpMem], rax; lpMem
0x1800193a5  mov     r8, r14; int
0x1800193a8  call    WiaTrace_ProcessTrace_Ex
0x1800193ad  xor     ebx, ebx
0x1800193af  jmp     short loc_18001940B
0x1800193b1  mov     eax, dword ptr [rsp+4E0h+var_470]
0x1800193b5  cmp     eax, 1016h
0x1800193ba  jnz     short loc_1800193C3
0x1800193bc  mov     dword ptr [rsp+4E0h+pv], r12d
0x1800193c1  jmp     short loc_18001940B
0x1800193c3  cmp     eax, 100Fh
0x1800193c8  jnz     short loc_1800193D1
0x1800193ca  mov     [rsp+4E0h+var_4A4], r12d
0x1800193cf  jmp     short loc_18001940B
0x1800193d1  cmp     eax, 1010h
0x1800193d6  jnz     short loc_1800193E5
0x1800193d8  mov     [rsp+4E0h+var_4AC], r12d
0x1800193dd  mov     [rsi+0ECh], ebx
0x1800193e3  jmp     short loc_18001940B
0x1800193e5  cmp     eax, 1012h
0x1800193ea  jnz     short loc_1800193F9
0x1800193ec  mov     dword ptr [rsp+4E0h+var_4A0+4], r12d
0x1800193f1  mov     [rsi+0F4h], ebx
0x1800193f7  jmp     short loc_18001940B
0x1800193f9  cmp     eax, 1011h
0x1800193fe  jnz     short loc_18001940B
0x180019400  mov     dword ptr [rsp+4E0h+var_4A0], r12d
0x180019405  mov     [rsi+0F0h], ebx
0x18001940b  mov     rcx, [rsp+4E0h+pv+8]; pv
0x180019410  test    rcx, rcx
0x180019413  jz      short loc_180019420
0x180019415  call    cs:__imp_CoTaskMemFree
0x18001941b  mov     [rsp+4E0h+pv+8], rbx
0x180019420  test    edi, edi
0x180019422  js      short loc_180019432
0x180019424  mov     rcx, qword ptr [rsp+4E0h+var_498]
0x180019429  mov     [rsp+4E0h+var_490], ebx
0x18001942d  jmp     loc_1800191D0
0x180019432  mov     rcx, qword ptr [rsp+4E0h+var_498]
0x180019437  test    rcx, rcx
0x18001943a  jz      short loc_18001944D
0x18001943c  mov     rax, [rcx]
0x18001943f  mov     rax, [rax+10h]
0x180019443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019448  mov     qword ptr [rsp+4E0h+var_498], rbx
0x18001944d  test    edi, edi
0x18001944f  js      loc_180019E79
0x180019455  mov     rcx, [r15+50h]
0x180019459  mov     edx, r12d
0x18001945c  add     rcx, 8
0x180019460  mov     rax, [rcx]
0x180019463  mov     rax, [rax+48h]
0x180019467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001946c  lea     rcx, aScan; "Scan"
0x180019473  call    cs:__imp_SysAllocString
0x180019479  mov     rdx, [r15+40h]
0x18001947d  lea     rcx, [rbp+3E0h+var_400]
0x180019481  mov     r12, rax
0x180019484  mov     rdx, [rdx+0C0h]
0x18001948b  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180019490  lea     rdx, SubBlock; "\\"
0x180019497  lea     rcx, [rbp+3E0h+var_1A0]
0x18001949e  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800194a3  lea     rdx, [rbp+3E0h+var_1A0]
0x1800194aa  lea     rcx, [rbp+3E0h+var_400]
0x1800194ae  call    ?Concat@?$CSimpleStringBase@G@@QEAAXAEBV1@@Z; CSimpleStringBase<ushort>::Concat(CSimpleStringBase<ushort> const &)
0x1800194b3  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800194ba  lea     rcx, [rbp+3E0h+var_1A0]
0x1800194c1  mov     [rbp+3E0h+var_1A0], rdi
0x1800194c8  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800194cd  mov     rdx, r12
0x1800194d0  lea     rcx, [rbp+3E0h+var_1A0]
0x1800194d7  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800194dc  lea     rdx, [rbp+3E0h+var_1A0]
  ... truncated ...
```
