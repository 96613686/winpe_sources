# CWiaItem::InitChildItemLHProps(int)

- ea: `0x180063688`
- end: `0x18006499a`
- name: `?InitChildItemLHProps@CWiaItem@@QEAAJH@Z`
- size: `4882`
- prototype: `__int64 __fastcall(CWiaItem *__hidden this, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800552bc`

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
- `0x180018390`
- `0x18001ad9c`
- `0x18001e364`
- `0x18002de18`
- `0x18002def8`
- `0x180033cc0`
- `0x180034658`
- `0x18005ee10`
- `0x18005f520`
- `0x180063688`
- `0x1800659c8`
- `0x180078010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180063fdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18006405f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800640ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800640e6`
- `OLEAUT32!__imp_SysAllocString` at `0x180063fdb`
- `OLEAUT32!__imp_SysAllocString` at `0x18006405f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800640ba`
- `OLEAUT32!__imp_SysAllocString` at `0x1800640e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180064251`
- `OLEAUT32!__imp_SysFreeString` at `0x18006426e`
- `OLEAUT32!__imp_SysFreeString` at `0x180064287`
- `OLEAUT32!__imp_SysFreeString` at `0x180064295`
- `OLEAUT32!__imp_SysFreeString` at `0x180064251`
- `OLEAUT32!__imp_SysFreeString` at `0x18006426e`
- `OLEAUT32!__imp_SysFreeString` at `0x180064287`
- `OLEAUT32!__imp_SysFreeString` at `0x180064295`
- `ole32!CoTaskMemFree` at `0x180063a2e`
- `ole32!CoTaskMemFree` at `0x180063f28`
- `ole32!CoTaskMemFree` at `0x180063a2e`
- `ole32!CoTaskMemFree` at `0x180063f28`
- `ole32!PropVariantClear` at `0x180063bcd`
- `ole32!PropVariantClear` at `0x180063e13`
- `ole32!PropVariantClear` at `0x1800642a2`
- `ole32!PropVariantClear` at `0x1800642af`
- `ole32!PropVariantClear` at `0x1800642bc`
- `ole32!PropVariantClear` at `0x180064663`
- `ole32!PropVariantClear` at `0x180064670`
- `ole32!PropVariantClear` at `0x18006467d`
- `ole32!PropVariantClear` at `0x18006468a`
- `ole32!PropVariantClear` at `0x180064697`
- `ole32!PropVariantClear` at `0x18006486c`
- `ole32!PropVariantClear` at `0x180063bcd`
- `ole32!PropVariantClear` at `0x180063e13`
- `ole32!PropVariantClear` at `0x1800642a2`
- `ole32!PropVariantClear` at `0x1800642af`
- `ole32!PropVariantClear` at `0x1800642bc`
- `ole32!PropVariantClear` at `0x180064663`
- `ole32!PropVariantClear` at `0x180064670`
- `ole32!PropVariantClear` at `0x18006467d`
- `ole32!PropVariantClear` at `0x18006468a`
- `ole32!PropVariantClear` at `0x180064697`
- `ole32!PropVariantClear` at `0x18006486c`
- `ole32!CoTaskMemAlloc` at `0x180064313`
- `ole32!CoTaskMemAlloc` at `0x180064327`
- `ole32!CoTaskMemAlloc` at `0x180064313`
- `ole32!CoTaskMemAlloc` at `0x180064327`

## string_xrefs

- `0x18006372b`: `not in compatibility mode or called on non LH A-AIT root item (0x%X)`
- `0x180063751`: `not in compatibility mode or called on non LH A-AIT root item (0x%X)`
- `0x180063ed1`: `non-translated property copy failed (0x%X)`
- `0x180063ef7`: `non-translated property copy failed (0x%X)`
- `0x18006459b`: `Call to wiasSetItemPropAttribs(additional props) failed (0x%X)`
- `0x1800645c4`: `Call to wiasSetItemPropAttribs(additional props) failed (0x%X)`
- `0x180064620`: `Call to WriteMultiple(additional props) failed (0x%X)`
- `0x180064649`: `Call to WriteMultiple(additional props) failed (0x%X)`
- `0x1800641fa`: `Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_FLAGS) failed (0x%X)`
- `0x180064220`: `Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_FLAGS) failed (0x%X)`
- `0x180064834`: `Call to WriteMultiple(WIA_IPA_FORMAT) failed (0x%X)`
- `0x180064856`: `Call to WriteMultiple(WIA_IPA_FORMAT) failed (0x%X)`
- `0x180064915`: `Call to wiasSetItemPropNames(additional props) failed (0x%X)`
- `0x18006493d`: `Call to wiasSetItemPropNames(additional props) failed (0x%X)`
- `0x1800647bb`: `cannot read current WIA_IPA_FORMAT from the D-AIT (0x%X)`
- `0x1800647dd`: `cannot read current WIA_IPA_FORMAT from the D-AIT (0x%X)`

## pseudocode

```c
__int64 __fastcall CWiaItem::InitChildItemLHProps(CWiaItem *this, int a2)
{
  int v3; // r12d
  struct tagWiaTraceData_Type *v4; // rax
  char *v5; // rdx
  unsigned int v6; // r8d
  __int64 v7; // r14
  int v8; // edi
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  int v21; // r15d
  __int64 v22; // rcx
  int v23; // edx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  char *v29; // rbx
  void *v30; // rdx
  char *v31; // rbx
  void *v32; // rdx
  char *v33; // rbx
  void *v34; // rdx
  int v35; // eax
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rcx
  char *v42; // rbx
  void *v43; // rdx
  void **v44; // rax
  void *v45; // rdx
  __int64 v46; // rcx
  int v47; // r13d
  __int64 v48; // rcx
  int v49; // edx
  CWiaItem *v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  void **v61; // rax
  void *v62; // rdx
  __int64 v63; // rcx
  char *v64; // rbx
  void *v65; // rdx
  char *v66; // rbx
  void *v67; // rdx
  const OLECHAR *v68; // rcx
  OLECHAR *v69; // r15
  BSTR v70; // rax
  OLECHAR *v71; // r12
  OLECHAR *v72; // rax
  OLECHAR *v73; // rax
  char *v74; // rbx
  void *v75; // rdx
  void **v76; // rax
  void *v77; // rdx
  __int64 v78; // rcx
  char *v79; // rbx
  void *v80; // rdx
  GUID v81; // xmm6
  void *v82; // r12
  GUID *v83; // r15
  _OWORD *v84; // rax
  GUID *v85; // rax
  char *v86; // rbx
  void *v87; // rdx
  void **v88; // rax
  void *v89; // rdx
  __int64 v90; // rcx
  char *v91; // rbx
  void *v92; // rdx
  unsigned int *p_pv; // rax
  char *v94; // rbx
  void *v95; // rdx
  void **v96; // rax
  void *v97; // rdx
  __int64 v98; // rcx
  char *v99; // rbx
  void *v100; // rdx
  __int64 v101; // rcx
  char *v102; // rbx
  void *v103; // rdx
  void **v104; // rax
  void *v105; // rdx
  __int64 v106; // rcx
  __int64 v107; // rcx
  char *v108; // rbx
  void *v109; // rdx
  void **v110; // rax
  void *v111; // rdx
  __int64 v112; // rcx
  char *v113; // rbx
  void *v114; // rdx
  char *v115; // rbx
  void *v116; // rdx
  void **v117; // rax
  void *v118; // rdx
  __int64 v119; // rcx
  unsigned int lpMem; // [rsp+28h] [rbp-E0h]
  __int64 v122; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v123; // [rsp+50h] [rbp-B8h] BYREF
  __int64 pv; // [rsp+58h] [rbp-B0h] BYREF
  struct tagSTATPROPSTG pv_8; // [rsp+60h] [rbp-A8h] BYREF
  int v126; // [rsp+70h] [rbp-98h]
  _BYTE v127[80]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v128[38]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v129[38]; // [rsp+1F8h] [rbp+F0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+328h] [rbp+220h] BYREF
  unsigned int v131[4]; // [rsp+338h] [rbp+230h]
  const wchar_t *v132; // [rsp+348h] [rbp+240h]
  unsigned int v133; // [rsp+350h] [rbp+248h] BYREF
  int v134; // [rsp+354h] [rbp+24Ch]
  __int64 v135; // [rsp+358h] [rbp+250h]
  int v136; // [rsp+360h] [rbp+258h]
  BSTR bstrString[2]; // [rsp+368h] [rbp+260h] BYREF
  __int64 v138; // [rsp+378h] [rbp+270h]
  BSTR v139[2]; // [rsp+380h] [rbp+278h] BYREF
  __int64 v140; // [rsp+390h] [rbp+288h]
  PROPVARIANT v141[2]; // [rsp+398h] [rbp+290h] BYREF
  __int64 v142; // [rsp+3A8h] [rbp+2A0h]
  PROPVARIANT v143[2]; // [rsp+3B0h] [rbp+2A8h] BYREF
  __int64 v144; // [rsp+3C0h] [rbp+2B8h]
  PROPVARIANT v145[2]; // [rsp+3C8h] [rbp+2C0h] BYREF
  __int64 v146; // [rsp+3D8h] [rbp+2D0h]
  int v147; // [rsp+3E8h] [rbp+2E0h] BYREF
  int v148; // [rsp+3F0h] [rbp+2E8h] BYREF
  int v149; // [rsp+3F8h] [rbp+2F0h]
  int v150; // [rsp+400h] [rbp+2F8h]
  int v151; // [rsp+408h] [rbp+300h]
  int v152; // [rsp+410h] [rbp+308h]
  int v153; // [rsp+418h] [rbp+310h]
  int v154; // [rsp+420h] [rbp+318h]
  int v155; // [rsp+428h] [rbp+320h]
  int v156; // [rsp+430h] [rbp+328h]
  int v157; // [rsp+438h] [rbp+330h]
  __int16 v158[18]; // [rsp+43Ch] [rbp+334h] BYREF
  int v159; // [rsp+460h] [rbp+358h]
  __int16 v160; // [rsp+464h] [rbp+35Ch]
  int v161; // [rsp+488h] [rbp+380h]
  __int16 v162; // [rsp+48Ch] [rbp+384h]
  int v163; // [rsp+490h] [rbp+388h]
  int v164; // [rsp+494h] [rbp+38Ch]
  unsigned int *v165; // [rsp+498h] [rbp+390h]
  int v166; // [rsp+4B0h] [rbp+3A8h]
  __int16 v167; // [rsp+4B4h] [rbp+3ACh]
  int v168; // [rsp+4D8h] [rbp+3D0h]
  __int16 v169; // [rsp+4DCh] [rbp+3D4h]

  v126 = a2;
  v3 = a2;
  v4 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("CWiaItem::InitChildItemLHProps");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v127, v5, v6, "CWiaItem::InitChildItemLHProps", lpMem, v4);
  v7 = *(_QWORD *)((char *)this + (-(__int64)(v3 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 96);
  if ( *((_QWORD *)this + 8)
    && v7
    && *((_QWORD *)this + 10)
    && *((_DWORD *)this + 26) == 1
    && *((CWiaItem **)this + 26) == this )
  {
    v8 = 0;
  }
  else
  {
    v8 = -2147467261;
    v9 = (char *)WiaTrace_TraceLog("not in compatibility mode or called on non LH A-AIT root item (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = (void **)WiaTrace_Trace("not in compatibility mode or called on non LH A-AIT root item (0x%X)", -2147467261);
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"CWiaItem::InitChildItemLHProps", 1, v11);
  }
  v14 = 0;
  v123 = 0;
  if ( v8 >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 8) + 8LL) + 88LL))(
            *((_QWORD *)this + 8) + 8LL,
            &v123);
    v14 = v123;
    v8 = v15;
    if ( v123 )
    {
      if ( v15 >= 0 )
        goto LABEL_13;
    }
    else
    {
      v8 = -2147024882;
    }
    v16 = (char *)WiaTrace_TraceLog("failed to get property enumerator for root properties to translate (0x%X)");
    WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v18 = (void **)WiaTrace_Trace("failed to get property enumerator for root properties to translate (0x%X)", v8);
    WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"CWiaItem::InitChildItemLHProps", 1, v18);
    v14 = v123;
  }
LABEL_13:
  LODWORD(v122) = 0;
  pv_8 = 0;
  v21 = 6 - (v3 != 0);
  if ( v8 < 0 )
    goto LABEL_38;
  while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct tagSTATPROPSTG *, __int64 *))(*(_QWORD *)v14 + 24LL))(
             v14,
             1,
             &pv_8,
             &v122)
       && (_DWORD)v122 == 1 )
  {
    *(_OWORD *)pvar = 0;
    *(_OWORD *)v131 = 0;
    if ( !(unsigned int)CWiaItem::GetPropCompatCategory(v22, pv_8.propid, 1, 8, pvar) )
      goto LABEL_33;
    if ( LODWORD(pvar[0]) == 2 )
    {
      if ( v21 == v131[1] )
      {
        v8 = CWiaItem::CopyC2PropertyFrom((CWiaItem *)v7, *((struct CWiaItem **)this + 8), &pv_8, v131[0]);
        if ( v8 < 0 )
        {
          v24 = (char *)WiaTrace_TraceLog("C2 property translation failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v24);
          WiaTrcLib::Free((WiaTrcLib *)v24, v25);
          v26 = (void **)WiaTrace_Trace("C2 property translation failed (0x%X)", (unsigned int)v8);
LABEL_32:
          WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"CWiaItem::InitChildItemLHProps", 1, v26);
        }
      }
    }
    else if ( LODWORD(pvar[0]) == 3 && (v21 == v131[1] || v131[1] == 7) )
    {
      if ( v3 && v23 == 3088 )
      {
        v8 = CWiaItem::CopyFlagPropertyFrom((CWiaItem *)v7, *((struct CWiaItem **)this + 8), &pv_8, 0x7Cu, 0x20u, 0, 0);
        if ( v8 >= 0 )
          goto LABEL_33;
        v29 = (char *)WiaTrace_TraceLog("WIA_DPS_DOCUMENT_HANDLING_SELECT translation failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v29);
        WiaTrcLib::Free((WiaTrcLib *)v29, v30);
        v26 = (void **)WiaTrace_Trace("WIA_DPS_DOCUMENT_HANDLING_SELECT translation failed (0x%X)", (unsigned int)v8);
      }
      else
      {
        v8 = CWiaItem::SetLegacyItemContext((CWiaItem *)v7);
        if ( v8 >= 0 )
        {
          v8 = CWiaItem::CopyPropertyFrom((CWiaItem *)v7, *((struct CWiaItem **)this + 8), &pv_8);
          if ( v8 >= 0 )
            goto LABEL_33;
          v33 = (char *)WiaTrace_TraceLog("C3 property translation failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v33);
          WiaTrcLib::Free((WiaTrcLib *)v33, v34);
          v26 = (void **)WiaTrace_Trace("C3 property translation failed (0x%X)", (unsigned int)v8);
        }
        else
        {
          v31 = (char *)WiaTrace_TraceLog("C3 property context change failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v31);
          WiaTrcLib::Free((WiaTrcLib *)v31, v32);
          v26 = (void **)WiaTrace_Trace("C3 property context change failed (0x%X)", (unsigned int)v8);
        }
      }
      goto LABEL_32;
    }
LABEL_33:
    if ( pv_8.lpwstrName )
    {
      CoTaskMemFree(pv_8.lpwstrName);
      pv_8.lpwstrName = 0;
    }
    if ( v8 < 0 )
      break;
    v14 = v123;
    LODWORD(v122) = 0;
  }
  v14 = v123;
LABEL_38:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
    v123 = 0;
  }
  if ( v8 >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v7 + 8) + 72LL))(v7 + 8, 1);
    v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL) + 88LL))(
            *((_QWORD *)this + 10) + 8LL,
            &v123);
    v8 = v35;
    if ( !v123 )
    {
      v8 = -2147024882;
      goto LABEL_44;
    }
    if ( v35 >= 0 )
    {
      v41 = *((_QWORD *)this + 10);
      v133 = 1;
      *(_QWORD *)v131 = 0;
      v135 = 4108;
      *(_OWORD *)pvar = 0;
      LODWORD(pvar[1]) = 2;
      LOWORD(pvar[0]) = 3;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, PROPVARIANT *, int))(*(_QWORD *)(v41 + 8) + 32LL))(
             v41 + 8,
             1,
             &v133,
             pvar,
             4098);
      if ( v8 < 0 )
      {
        v42 = (char *)WiaTrace_TraceLog("TYMED_FILE not supported by legacy driver (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v42);
        WiaTrcLib::Free((WiaTrcLib *)v42, v43);
        v44 = (void **)WiaTrace_Trace("TYMED_FILE not supported by legacy driver (0x%X)", v8);
        WiaTrace_ProcessTrace_Ex(v46, v45, (void *)"CWiaItem::InitChildItemLHProps", 1, v44);
      }
      PropVariantClear(pvar);
    }
    else
    {
LABEL_44:
      v36 = (char *)WiaTrace_TraceLog("failed to get property enumerator for child properties to translate (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v38 = (void **)WiaTrace_Trace("failed to get property enumerator for child properties to translate (0x%X)", v8);
      WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"CWiaItem::InitChildItemLHProps", 1, v38);
    }
    v14 = v123;
  }
  LODWORD(v122) = 0;
  HIDWORD(pv) = 0;
  v47 = 2;
  if ( v8 < 0 )
    goto LABEL_79;
  while ( 2 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct tagSTATPROPSTG *, __int64 *))(*(_QWORD *)v14 + 24LL))(
            v14,
            1,
            &pv_8,
            &v122)
      && (_DWORD)v122 == 1 )
    {
      *(_OWORD *)pvar = 0;
      *(_OWORD *)v131 = 0;
      if ( (unsigned int)CWiaItem::GetPropCompatCategory(v48, pv_8.propid, 1, 8, pvar) )
      {
        if ( (unsigned int)(LODWORD(pvar[0]) - 4) <= 1
          && ((unsigned int)(LODWORD(pvar[1]) - 2) <= 1 && v21 == v131[1] || v131[1] - 7 <= 1) )
        {
          if ( v49 == 4108 )
          {
            v50 = (CWiaItem *)*((_QWORD *)this + 10);
            LODWORD(pv) = 2;
            wiasReadPropLong(v50, 1);
            v47 = pv;
            if ( (_DWORD)pv == 256 )
            {
              pv = 0x100000100LL;
            }
            else
            {
              v133 = 1;
              *(_QWORD *)v131 = 0;
              v135 = 4108;
              *(_OWORD *)pvar = 0;
              LODWORD(pvar[1]) = 256;
              v51 = *((_QWORD *)this + 10) + 8LL;
              LOWORD(pvar[0]) = 3;
              if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, PROPVARIANT *, int))(*(_QWORD *)v51 + 32LL))(
                     v51,
                     1,
                     &v133,
                     pvar,
                     4098) >= 0 )
              {
                v52 = *((_QWORD *)this + 10) + 8LL;
                v47 = 2;
                LODWORD(pvar[1]) = 2;
                if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, PROPVARIANT *))(*(_QWORD *)v52 + 24LL))(
                       v52,
                       1,
                       &v133,
                       pvar) >= 0 )
                  HIDWORD(pv) = LODWORD(pvar[1]) == 256;
                v53 = *((_QWORD *)this + 10) + 8LL;
                LODWORD(pvar[1]) = 2;
                v8 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, PROPVARIANT *, int))(*(_QWORD *)v53 + 32LL))(
                       v53,
                       1,
                       &v133,
                       pvar,
                       4098);
                if ( v8 < 0 )
                {
                  v54 = (char *)WiaTrace_TraceLog("TYMED_FILE not supported by legacy driver (0x%X)");
                  WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v54);
                  WiaTrcLib::Free((WiaTrcLib *)v54, v55);
                  v56 = (void **)WiaTrace_Trace("TYMED_FILE not supported by legacy driver (0x%X)", v8);
                  WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"CWiaItem::InitChildItemLHProps", 1, v56);
                }
              }
              PropVariantClear(pvar);
            }
            goto LABEL_74;
          }
          if ( v49 != 4105 )
          {
            v8 = CWiaItem::SetLegacyItemContext((CWiaItem *)v7);
            if ( v8 < 0 )
            {
              v59 = (char *)WiaTrace_TraceLog("C4-5 property context change failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v59);
              WiaTrcLib::Free((WiaTrcLib *)v59, v60);
              v61 = (void **)WiaTrace_Trace("C4-5 property context change failed (0x%X)", (unsigned int)v8);
              goto LABEL_73;
            }
            v8 = CWiaItem::CopyPropertyFrom((CWiaItem *)v7, *((struct CWiaItem **)this + 10), &pv_8);
            if ( v8 < 0 )
            {
              v64 = (char *)WiaTrace_TraceLog("C4-5 property translation failed (0x%X)");
              WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v64);
              WiaTrcLib::Free((WiaTrcLib *)v64, v65);
              v61 = (void **)WiaTrace_Trace("C4-5 property translation failed (0x%X)", (unsigned int)v8);
              goto LABEL_73;
            }
          }
        }
      }
      else
      {
        v8 = CWiaItem::CopyPropertyFrom((CWiaItem *)v7, *((struct CWiaItem **)this + 10), &pv_8);
        if ( v8 < 0 )
        {
          v66 = (char *)WiaTrace_TraceLog("non-translated property copy failed (0x%X)");
          WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v66);
          WiaTrcLib::Free((WiaTrcLib *)v66, v67);
          v61 = (void **)WiaTrace_Trace("non-translated property copy failed (0x%X)", (unsigned int)v8);
LABEL_73:
          WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"CWiaItem::InitChildItemLHProps", 1, v61);
        }
      }
LABEL_74:
      if ( pv_8.lpwstrName )
      {
        CoTaskMemFree(pv_8.lpwstrName);
        pv_8.lpwstrName = 0;
      }
      if ( v8 < 0 )
        break;
      v14 = v123;
      LODWORD(v122) = 0;
      continue;
    }
    break;
  }
  v14 = v123;
  v3 = v126;
LABEL_79:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v123 = 0;
  }
  if ( v8 >= 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v7 + 8) + 72LL))(v7 + 8, 1);
  v147 = 0;
  memset_0(&v148, 0, 0x48u);
  LOWORD(bstrString[0]) = 0;
  memset_0((char *)bstrString + 2, 0, 0x76u);
  if ( v8 >= 0 )
  {
    v68 = L"Feeder";
    if ( !v3 )
      v68 = L"Flatbed";
    v69 = SysAllocString(v68);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
      v129,
      *(_QWORD *)(*((_QWORD *)this + 8) + 192LL));
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v128, L"\\");
    CSimpleStringBase<unsigned short>::Concat(v129, v128);
    v128[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v128);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v128, v69);
    CSimpleStringBase<unsigned short>::Concat(v129, v128);
    v128[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v128);
    v70 = SysAllocString((const OLECHAR *)v129[33]);
    v147 = 1;
    v71 = v70;
    v138 = 0;
    v140 = 0;
    v142 = 0;
    *(_OWORD *)bstrString = 0;
    LOWORD(bstrString[0]) = 8;
    *(_OWORD *)v139 = 0;
    v148 = 4098;
    *(_OWORD *)v141 = 0;
    v72 = SysAllocString(v69);
    v149 = 1;
    bstrString[1] = v72;
    LOWORD(v139[0]) = 8;
    v150 = 4099;
    v73 = SysAllocString(v71);
    v151 = 1;
    v139[1] = v73;
    v152 = 4101;
    LOWORD(v141[0]) = 3;
    LODWORD(v141[1]) = 532483;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, BSTR *, int))(***(_QWORD ***)(v7 + 216) + 32LL))(
           **(_QWORD **)(v7 + 216),
           3,
           &v147,
           bstrString,
           4098);
    if ( v8 < 0 )
    {
      v74 = (char *)WiaTrace_TraceLog("cannot item info properties (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v74);
      WiaTrcLib::Free((WiaTrcLib *)v74, v75);
      v76 = (void **)WiaTrace_Trace("cannot item info properties (0x%X)", (unsigned int)v8);
      goto LABEL_90;
    }
    v138 = 0;
    LODWORD(pvar[1]) = v141[1];
    HIDWORD(pvar[1]) = v141[1];
    v132 = 0;
    v147 = 1;
    *(_OWORD *)v131 = 0;
    v148 = 4101;
    *(_OWORD *)bstrString = 0;
    pvar[0] = (PROPVARIANT)0x300000041LL;
    v8 = wiasSetItemPropAttribs((CWiaItem *)v7);
    if ( v8 < 0 )
    {
      v79 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_FLAGS) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v79);
      WiaTrcLib::Free((WiaTrcLib *)v79, v80);
      v76 = (void **)WiaTrace_Trace(
                       "Call to wiasSetItemPropAttribs(WIA_IPA_ITEM_FLAGS) failed (0x%X)",
                       (unsigned int)v8);
LABEL_90:
      WiaTrace_ProcessTrace_Ex(v78, v77, (void *)"CWiaItem::InitChildItemLHProps", 1, v76);
    }
    if ( bstrString[1] )
    {
      SysFreeString(bstrString[1]);
      bstrString[1] = 0;
    }
    if ( v139[1] )
    {
      SysFreeString(v139[1]);
      v139[1] = 0;
    }
    if ( v69 )
      SysFreeString(v69);
    if ( v71 )
      SysFreeString(v71);
    PropVariantClear((PROPVARIANT *)bstrString);
    PropVariantClear((PROPVARIANT *)v139);
    PropVariantClear(v141);
    v157 = 0;
    memset_0(v158, 0, 0xC4u);
    if ( v126 )
      v81 = WIA_CATEGORY_FEEDER;
    else
      v81 = WIA_CATEGORY_FLATBED;
    v82 = 0;
    v83 = 0;
    if ( v8 >= 0 )
    {
      v84 = CoTaskMemAlloc(0x10u);
      v82 = v84;
      if ( v84 )
      {
        *v84 = v81;
        v85 = (GUID *)CoTaskMemAlloc(0x10u);
        v83 = v85;
        if ( v85 )
        {
          *v85 = WiaImgFmt_BMP;
          goto LABEL_109;
        }
        v8 = -2147024882;
        v86 = (char *)WiaTrace_TraceLog("cannot allocate memory for preferred format GUID (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v86);
        WiaTrcLib::Free((WiaTrcLib *)v86, v87);
        v88 = (void **)WiaTrace_Trace("cannot allocate memory for preferred format GUID (0x%X)", 2147942414LL);
      }
      else
      {
        v8 = -2147024882;
        v91 = (char *)WiaTrace_TraceLog("cannot allocate memory for item category GUID (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v91);
        WiaTrcLib::Free((WiaTrcLib *)v91, v92);
        v88 = (void **)WiaTrace_Trace("cannot allocate memory for item category GUID (0x%X)", 2147942414LL);
      }
      WiaTrace_ProcessTrace_Ex(v90, v89, (void *)"CWiaItem::InitChildItemLHProps", 1, v88);
    }
LABEL_109:
    memset_0(&v147, 0, 0x50u);
    memset_0(bstrString, 0, 0x78u);
    v148 = 6167;
    v140 = 0;
    v142 = 0;
    LOWORD(bstrString[0]) = 3;
    v143[0] = 0;
    v143[1] = v82;
    LODWORD(bstrString[1]) = 1;
    v147 = 1;
    v133 = 2;
    LODWORD(pv) = 2;
    p_pv = (unsigned int *)&pv;
    if ( HIDWORD(pv) )
      p_pv = &v133;
    v157 = 9;
    v165 = p_pv;
    v158[0] = 3;
    v149 = 1;
    v150 = 6168;
    v159 = 9;
    *(_OWORD *)v139 = 0;
    v163 = (HIDWORD(pv) != 0) + 1;
    LOWORD(v139[0]) = 3;
    LODWORD(v139[1]) = 1;
    v160 = 3;
    v134 = 256;
    v151 = 1;
    v152 = 4108;
    v161 = 35;
    v162 = 3;
    v164 = v47;
    v144 = 0;
    LOWORD(v143[0]) = 72;
    v153 = 1;
    v154 = 4125;
    v166 = 9;
    v167 = 72;
    v146 = 0;
    v155 = 1;
    v156 = 4105;
    v168 = 9;
    v169 = 72;
    *(_OWORD *)v141 = 0;
    LOWORD(v141[0]) = 3;
    LODWORD(v141[1]) = v47;
    v145[0] = (PROPVARIANT)72;
    v145[1] = v83;
    if ( v8 >= 0 )
    {
      v8 = wiasSetItemPropAttribs((CWiaItem *)v7);
      if ( v8 < 0 )
      {
        v94 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropAttribs(additional props) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v94);
        WiaTrcLib::Free((WiaTrcLib *)v94, v95);
        v96 = (void **)WiaTrace_Trace(
                         "Call to wiasSetItemPropAttribs(additional props) failed (0x%X)",
                         (unsigned int)v8);
        goto LABEL_114;
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, BSTR *, int))(***(_QWORD ***)(v7 + 216) + 32LL))(
             **(_QWORD **)(v7 + 216),
             5,
             &v147,
             bstrString,
             4098);
      if ( v8 < 0 )
      {
        v99 = (char *)WiaTrace_TraceLog("Call to WriteMultiple(additional props) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v99);
        WiaTrcLib::Free((WiaTrcLib *)v99, v100);
        v96 = (void **)WiaTrace_Trace("Call to WriteMultiple(additional props) failed (0x%X)", (unsigned int)v8);
LABEL_114:
        WiaTrace_ProcessTrace_Ex(v98, v97, (void *)"CWiaItem::InitChildItemLHProps", 1, v96);
      }
    }
    PropVariantClear((PROPVARIANT *)bstrString);
    PropVariantClear((PROPVARIANT *)v139);
    PropVariantClear(v141);
    PropVariantClear(v143);
    PropVariantClear(v145);
    if ( v8 >= 0 )
    {
      v101 = *((_QWORD *)this + 10);
      v147 = 1;
      v138 = 0;
      v148 = 4108;
      *(_OWORD *)bstrString = 0;
      LOWORD(bstrString[0]) = 3;
      LODWORD(bstrString[1]) = v47;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *, BSTR *, int))(*(_QWORD *)(v101 + 8) + 32LL))(
             v101 + 8,
             1,
             &v147,
             bstrString,
             4098);
      if ( v8 < 0 )
      {
        v102 = (char *)WiaTrace_TraceLog("cannot sync current WIA_IPA_TYMED with the D-AIT (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v102);
        WiaTrcLib::Free((WiaTrcLib *)v102, v103);
        v104 = (void **)WiaTrace_Trace("cannot sync current WIA_IPA_TYMED with the D-AIT (0x%X)", v8);
        WiaTrace_ProcessTrace_Ex(v106, v105, (void *)"CWiaItem::InitChildItemLHProps", 1, v104);
      }
    }
    v129[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v129);
    if ( v8 >= 0 )
    {
      v107 = *((_QWORD *)this + 10) + 8LL;
      v148 = 4106;
      LODWORD(bstrString[1]) = 0;
      LOWORD(bstrString[0]) = 72;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *, BSTR *))(*(_QWORD *)v107 + 24LL))(
             v107,
             1,
             &v147,
             bstrString);
      if ( v8 < 0 )
      {
        v108 = (char *)WiaTrace_TraceLog("cannot read current WIA_IPA_FORMAT from the D-AIT (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v108);
        WiaTrcLib::Free((WiaTrcLib *)v108, v109);
        v110 = (void **)WiaTrace_Trace("cannot read current WIA_IPA_FORMAT from the D-AIT (0x%X)", (unsigned int)v8);
        goto LABEL_123;
      }
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, BSTR *, int))(***(_QWORD ***)(v7 + 216) + 32LL))(
             **(_QWORD **)(v7 + 216),
             1,
             &v147,
             bstrString,
             4098);
      if ( v8 < 0 )
      {
        v113 = (char *)WiaTrace_TraceLog("Call to WriteMultiple(WIA_IPA_FORMAT) failed (0x%X)");
        WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v113);
        WiaTrcLib::Free((WiaTrcLib *)v113, v114);
        v110 = (void **)WiaTrace_Trace("Call to WriteMultiple(WIA_IPA_FORMAT) failed (0x%X)", (unsigned int)v8);
LABEL_123:
        WiaTrace_ProcessTrace_Ex(v112, v111, (void *)"CWiaItem::InitChildItemLHProps", 1, v110);
      }
    }
  }
  PropVariantClear((PROPVARIANT *)bstrString);
  if ( v8 >= 0 )
  {
    v133 = 6167;
    pvar[0] = L"Minimum Horizontal Scan Size";
    v134 = 6168;
    pvar[1] = L"Minimum Vertical Scan Size";
    v135 = 0x10090000100CLL;
    *(_QWORD *)v131 = L"Media Type";
    *(_QWORD *)&v131[2] = L"Preferred Format";
    v136 = 4125;
    v132 = L"Item Category";
    v8 = wiasSetItemPropNames((CWiaItem *)v7, 5, &v133, (unsigned __int16 **)pvar);
    if ( v8 < 0 )
    {
      v115 = (char *)WiaTrace_TraceLog("Call to wiasSetItemPropNames(additional props) failed (0x%X)");
      WriteDbgTraceErrorWI("CWiaItem::InitChildItemLHProps", v115);
      WiaTrcLib::Free((WiaTrcLib *)v115, v116);
      v117 = (void **)WiaTrace_Trace("Call to wiasSetItemPropNames(additional props) failed (0x%X)", v8);
      WiaTrace_ProcessTrace_Ex(v119, v118, (void *)"CWiaItem::InitChildItemLHProps", 1, v117);
    }
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v127);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180063688  mov     rax, rsp
0x18006368b  push    rbp
0x18006368c  push    rbx
0x18006368d  push    rsi
0x18006368e  push    rdi
0x18006368f  push    r12
0x180063691  push    r13
0x180063693  push    r14
0x180063695  push    r15
0x180063697  lea     rbp, [rax-478h]
0x18006369e  sub     rsp, 538h
0x1800636a5  movaps  xmmword ptr [rax-58h], xmm6
0x1800636a9  movaps  xmmword ptr [rax-68h], xmm7
0x1800636ad  mov     rax, cs:__security_cookie
0x1800636b4  xor     rax, rsp
0x1800636b7  mov     [rbp+470h+var_70], rax
0x1800636be  mov     rsi, rcx
0x1800636c1  mov     [rsp+570h+var_508], edx
0x1800636c5  lea     r15, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x1800636cc  mov     r12d, edx
0x1800636cf  mov     rcx, r15
0x1800636d2  call    WiaTrace_Trace
0x1800636d7  mov     r9, r15; char *
0x1800636da  mov     [rsp+570h+var_548], rax; struct tagWiaTraceData_Type *
0x1800636df  lea     rcx, [rsp+570h+var_500]; this
0x1800636e4  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x1800636e9  mov     eax, r12d
0x1800636ec  mov     ebx, 1
0x1800636f1  neg     eax
0x1800636f3  sbb     rcx, rcx
0x1800636f6  xor     r13d, r13d
0x1800636f9  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800636fd  mov     r14, [rcx+rsi+60h]
0x180063702  cmp     [rsi+40h], r13
0x180063706  jz      short loc_180063726
0x180063708  test    r14, r14
0x18006370b  jz      short loc_180063726
0x18006370d  cmp     [rsi+50h], r13
0x180063711  jz      short loc_180063726
0x180063713  cmp     [rsi+68h], ebx
0x180063716  jnz     short loc_180063726
0x180063718  cmp     [rsi+0D0h], rsi
0x18006371f  jnz     short loc_180063726
0x180063721  mov     edi, r13d
0x180063724  jmp     short loc_180063772
0x180063726  mov     edi, 80004003h
0x18006372b  lea     rcx, aNotInCompatibi_0; "not in compatibility mode or called on "...
0x180063732  mov     edx, edi
0x180063734  call    WiaTrace_TraceLog
0x180063739  mov     rdx, rax; char *
0x18006373c  mov     rcx, r15; char *
0x18006373f  mov     rbx, rax
0x180063742  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180063747  mov     rcx, rbx; this
0x18006374a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18006374f  mov     edx, edi
0x180063751  lea     rcx, aNotInCompatibi_0; "not in compatibility mode or called on "...
0x180063758  call    WiaTrace_Trace
0x18006375d  mov     ebx, 1
0x180063762  mov     [rsp+570h+lpMem], rax; lpMem
0x180063767  mov     r9d, ebx; int
0x18006376a  mov     r8, r15; int
0x18006376d  call    WiaTrace_ProcessTrace_Ex
0x180063772  mov     rcx, r13
0x180063775  mov     [rsp+570h+var_528], rcx
0x18006377a  test    edi, edi
0x18006377c  js      short loc_1800637FA
0x18006377e  mov     rcx, [rsi+40h]
0x180063782  lea     rdx, [rsp+570h+var_528]
0x180063787  add     rcx, 8
0x18006378b  mov     rax, [rcx]
0x18006378e  mov     rax, [rax+58h]
0x180063792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063797  mov     rcx, [rsp+570h+var_528]
0x18006379c  mov     edi, eax
0x18006379e  test    rcx, rcx
0x1800637a1  jnz     short loc_1800637AA
0x1800637a3  mov     edi, 8007000Eh
0x1800637a8  jmp     short loc_1800637AE
0x1800637aa  test    eax, eax
0x1800637ac  jns     short loc_1800637FA
0x1800637ae  mov     edx, edi
0x1800637b0  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x1800637b7  call    WiaTrace_TraceLog
0x1800637bc  mov     rdx, rax; char *
0x1800637bf  mov     rcx, r15; char *
0x1800637c2  mov     rbx, rax
0x1800637c5  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800637ca  mov     rcx, rbx; this
0x1800637cd  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800637d2  mov     edx, edi
0x1800637d4  lea     rcx, aFailedToGetPro_4; "failed to get property enumerator for r"...
0x1800637db  call    WiaTrace_Trace
0x1800637e0  mov     ebx, 1
0x1800637e5  mov     [rsp+570h+lpMem], rax; lpMem
0x1800637ea  mov     r9d, ebx; int
0x1800637ed  mov     r8, r15; int
0x1800637f0  call    WiaTrace_ProcessTrace_Ex
0x1800637f5  mov     rcx, [rsp+570h+var_528]
0x1800637fa  mov     eax, r12d
0x1800637fd  mov     dword ptr [rsp+570h+var_530], r13d
0x180063802  neg     eax
0x180063804  xorps   xmm0, xmm0
0x180063807  movups  xmmword ptr [rsp+570h+pv+8], xmm0
0x18006380c  sbb     r15d, r15d
0x18006380f  add     r15d, 6
0x180063813  test    edi, edi
0x180063815  js      loc_180063A51
0x18006381b  mov     rax, [rcx]
0x18006381e  lea     r9, [rsp+570h+var_530]
0x180063823  lea     r8, [rsp+570h+pv+8]
0x180063828  mov     edx, ebx
0x18006382a  mov     rax, [rax+18h]
0x18006382e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063833  test    eax, eax
0x180063835  jnz     loc_180063A4C
0x18006383b  cmp     dword ptr [rsp+570h+var_530], ebx
0x18006383f  jnz     loc_180063A4C
0x180063845  mov     edx, [rsp+570h+var_510]
0x180063849  lea     rax, [rbp+470h+pvar]
0x180063850  xorps   xmm0, xmm0
0x180063853  mov     [rsp+570h+lpMem], rax
0x180063858  mov     r9d, 8
0x18006385e  mov     r8d, ebx
0x180063861  movups  xmmword ptr [rbp+470h+pvar], xmm0
0x180063868  movups  xmmword ptr [rbp+470h+var_240], xmm0
0x18006386f  call    ?GetPropCompatCategory@CWiaItem@@QEAAHKHW4_CL_ITEM@@AEAU_PROP_COMPAT_TABLE@@@Z; CWiaItem::GetPropCompatCategory(ulong,int,_CL_ITEM,_PROP_COMPAT_TABLE &)
0x180063874  test    eax, eax
0x180063876  jz      loc_180063A24
0x18006387c  cmp     dword ptr [rbp+470h+pvar], 2
0x180063883  jnz     short loc_1800638E8
0x180063885  cmp     r15d, [rbp+470h+var_240+4]
0x18006388c  jnz     loc_180063A24
0x180063892  mov     r9d, [rbp+470h+var_240]; unsigned int
0x180063899  lea     r8, [rsp+570h+pv+8]; struct tagSTATPROPSTG *
0x18006389e  mov     rdx, [rsi+40h]; struct CWiaItem *
0x1800638a2  mov     rcx, r14; this
0x1800638a5  call    ?CopyC2PropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@K@Z; CWiaItem::CopyC2PropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong)
0x1800638aa  mov     edi, eax
0x1800638ac  test    eax, eax
0x1800638ae  jns     loc_180063A24
0x1800638b4  mov     edx, eax
0x1800638b6  lea     rcx, aC2PropertyTran; "C2 property translation failed (0x%X)"
0x1800638bd  call    WiaTrace_TraceLog
0x1800638c2  mov     rdx, rax; char *
0x1800638c5  lea     rcx, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x1800638cc  mov     rbx, rax
0x1800638cf  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800638d4  mov     rcx, rbx; this
0x1800638d7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800638dc  lea     rcx, aC2PropertyTran; "C2 property translation failed (0x%X)"
0x1800638e3  jmp     loc_180063A04
0x1800638e8  cmp     dword ptr [rbp+470h+pvar], 3
0x1800638ef  jnz     loc_180063A24
0x1800638f5  cmp     r15d, [rbp+470h+var_240+4]
0x1800638fc  jz      short loc_18006390B
0x1800638fe  cmp     [rbp+470h+var_240+4], 7
0x180063905  jnz     loc_180063A24
0x18006390b  test    r12d, r12d
0x18006390e  jz      short loc_18006397F
0x180063910  cmp     edx, 0C10h
0x180063916  jnz     short loc_18006397F
0x180063918  mov     rdx, [rsi+40h]; struct CWiaItem *
0x18006391c  lea     r8, [rsp+570h+pv+8]; struct tagSTATPROPSTG *
0x180063921  mov     [rsp+570h+var_540], r13d; unsigned int
0x180063926  mov     r9d, 7Ch ; '|'; unsigned int
0x18006392c  mov     dword ptr [rsp+570h+var_548], r13d; unsigned int
0x180063931  mov     rcx, r14; this
0x180063934  mov     dword ptr [rsp+570h+lpMem], 20h ; ' '; unsigned int
0x18006393c  call    ?CopyFlagPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@KKKK@Z; CWiaItem::CopyFlagPropertyFrom(CWiaItem *,tagSTATPROPSTG &,ulong,ulong,ulong,ulong)
0x180063941  mov     edi, eax
0x180063943  test    eax, eax
0x180063945  jns     loc_180063A24
0x18006394b  mov     edx, eax
0x18006394d  lea     rcx, aWiaDpsDocument_2; "WIA_DPS_DOCUMENT_HANDLING_SELECT transl"...
0x180063954  call    WiaTrace_TraceLog
0x180063959  mov     rdx, rax; char *
0x18006395c  lea     rcx, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x180063963  mov     rbx, rax
0x180063966  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18006396b  mov     rcx, rbx; this
0x18006396e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180063973  lea     rcx, aWiaDpsDocument_2; "WIA_DPS_DOCUMENT_HANDLING_SELECT transl"...
0x18006397a  jmp     loc_180063A04
0x18006397f  mov     rcx, r14; this
0x180063982  call    ?SetLegacyItemContext@CWiaItem@@QEAAJXZ; CWiaItem::SetLegacyItemContext(void)
0x180063987  mov     edi, eax
0x180063989  test    eax, eax
0x18006398b  jns     short loc_1800639BE
0x18006398d  mov     edx, eax
0x18006398f  lea     rcx, aC3PropertyCont; "C3 property context change failed (0x%X"...
0x180063996  call    WiaTrace_TraceLog
0x18006399b  mov     rdx, rax; char *
0x18006399e  lea     rcx, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x1800639a5  mov     rbx, rax
0x1800639a8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800639ad  mov     rcx, rbx; this
0x1800639b0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800639b5  lea     rcx, aC3PropertyCont; "C3 property context change failed (0x%X"...
0x1800639bc  jmp     short loc_180063A04
0x1800639be  mov     rdx, [rsi+40h]; struct CWiaItem *
0x1800639c2  lea     r8, [rsp+570h+pv+8]; struct tagSTATPROPSTG *
0x1800639c7  mov     rcx, r14; this
0x1800639ca  call    ?CopyPropertyFrom@CWiaItem@@QEAAJPEAV1@AEAUtagSTATPROPSTG@@@Z; CWiaItem::CopyPropertyFrom(CWiaItem *,tagSTATPROPSTG &)
0x1800639cf  mov     edi, eax
0x1800639d1  test    eax, eax
0x1800639d3  jns     short loc_180063A24
0x1800639d5  mov     edx, eax
0x1800639d7  lea     rcx, aC3PropertyTran; "C3 property translation failed (0x%X)"
0x1800639de  call    WiaTrace_TraceLog
0x1800639e3  mov     rdx, rax; char *
0x1800639e6  lea     rcx, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x1800639ed  mov     rbx, rax
0x1800639f0  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800639f5  mov     rcx, rbx; this
0x1800639f8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800639fd  lea     rcx, aC3PropertyTran; "C3 property translation failed (0x%X)"
0x180063a04  mov     edx, edi
0x180063a06  call    WiaTrace_Trace
0x180063a0b  mov     ebx, 1
0x180063a10  mov     [rsp+570h+lpMem], rax; lpMem
0x180063a15  mov     r9d, ebx; int
0x180063a18  lea     r8, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x180063a1f  call    WiaTrace_ProcessTrace_Ex
0x180063a24  mov     rcx, [rsp+570h+pv+8]; pv
0x180063a29  test    rcx, rcx
0x180063a2c  jz      short loc_180063A39
0x180063a2e  call    cs:__imp_CoTaskMemFree
0x180063a34  mov     [rsp+570h+pv+8], r13
0x180063a39  test    edi, edi
0x180063a3b  js      short loc_180063A4C
0x180063a3d  mov     rcx, [rsp+570h+var_528]
0x180063a42  mov     dword ptr [rsp+570h+var_530], r13d
0x180063a47  jmp     loc_18006381B
0x180063a4c  mov     rcx, [rsp+570h+var_528]
0x180063a51  test    rcx, rcx
0x180063a54  jz      short loc_180063A6A
0x180063a56  mov     rax, [rcx]
0x180063a59  mov     rax, [rax+10h]
0x180063a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a62  mov     rcx, r13
0x180063a65  mov     [rsp+570h+var_528], rcx
0x180063a6a  test    edi, edi
0x180063a6c  js      loc_180063BD8
0x180063a72  lea     rcx, [r14+8]
0x180063a76  mov     edx, ebx
0x180063a78  mov     rax, [rcx]
0x180063a7b  mov     rax, [rax+48h]
0x180063a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a84  mov     rcx, [rsi+50h]
0x180063a88  lea     rdx, [rsp+570h+var_528]
0x180063a8d  add     rcx, 8
0x180063a91  mov     rax, [rcx]
0x180063a94  mov     rax, [rax+58h]
0x180063a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063a9d  mov     edi, eax
0x180063a9f  cmp     [rsp+570h+var_528], r13
0x180063aa4  jnz     short loc_180063AAD
0x180063aa6  mov     edi, 8007000Eh
0x180063aab  jmp     short loc_180063AB1
0x180063aad  test    eax, eax
0x180063aaf  jns     short loc_180063B05
0x180063ab1  mov     edx, edi
0x180063ab3  lea     rcx, aFailedToGetPro_3; "failed to get property enumerator for c"...
0x180063aba  call    WiaTrace_TraceLog
0x180063abf  mov     rdx, rax; char *
0x180063ac2  lea     rcx, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x180063ac9  mov     rbx, rax
0x180063acc  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180063ad1  mov     rcx, rbx; this
0x180063ad4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180063ad9  mov     edx, edi
0x180063adb  lea     rcx, aFailedToGetPro_3; "failed to get property enumerator for c"...
0x180063ae2  call    WiaTrace_Trace
0x180063ae7  mov     ebx, 1
0x180063aec  mov     [rsp+570h+lpMem], rax; lpMem
0x180063af1  mov     r9d, ebx; int
0x180063af4  lea     r8, aCwiaitemInitch_1; "CWiaItem::InitChildItemLHProps"
0x180063afb  call    WiaTrace_ProcessTrace_Ex
0x180063b00  jmp     loc_180063BD3
0x180063b05  mov     rcx, [rsi+50h]
0x180063b09  lea     r9, [rbp+470h+pvar]
0x180063b10  xor     eax, eax
0x180063b12  mov     [rbp+470h+var_228], ebx
0x180063b18  mov     [rbp+470h+var_220], rax
0x180063b1f  lea     r8, [rbp+470h+var_228]
0x180063b26  mov     qword ptr [rbp+470h+var_240], rax
0x180063b2d  add     rcx, 8
0x180063b31  xorps   xmm0, xmm0
0x180063b34  mov     dword ptr [rbp+470h+var_220], 100Ch
0x180063b3e  movups  xmmword ptr [rbp+470h+pvar], xmm0
0x180063b45  mov     eax, 3
0x180063b4a  mov     dword ptr [rbp+470h+pvar+8], 2
0x180063b54  mov     word ptr [rbp+470h+pvar], ax
0x180063b5b  mov     edx, ebx
0x180063b5d  mov     rax, [rcx]
0x180063b60  mov     dword ptr [rsp+570h+lpMem], 1002h
0x180063b68  mov     rax, [rax+20h]
0x180063b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063b71  mov     edi, eax
  ... truncated ...
```
