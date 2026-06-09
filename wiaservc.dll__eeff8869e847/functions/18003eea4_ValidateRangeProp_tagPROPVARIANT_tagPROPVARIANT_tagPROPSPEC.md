# ValidateRangeProp(tagPROPVARIANT *,tagPROPVARIANT *,tagPROPSPEC *)

- ea: `0x18003eea4`
- end: `0x18003f969`
- name: `?ValidateRangeProp@@YAJPEAUtagPROPVARIANT@@0PEAUtagPROPSPEC@@@Z`
- size: `2757`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPSPEC *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180043ce0`

## callees

- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18001c1e4`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18003eea4`

## string_xrefs

- `0x18003ef55`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003ef79`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f0dd`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f101`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f272`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f296`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f408`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f42c`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f5b6`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f5da`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f7a7`: `wiasValidateItemProperties, invalid RANGE value for : `
- `0x18003f7cb`: `wiasValidateItemProperties, invalid RANGE value for : `

## pseudocode

```c
__int64 __fastcall ValidateRangeProp(struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2, struct tagPROPSPEC *a3)
{
  char ***v6; // rax
  char *v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // edi
  BYTE *v10; // rdx
  unsigned int v11; // r9d
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  const wchar_t *v22; // rax
  int v23; // r9d
  char *v24; // rbx
  void *v25; // rdx
  unsigned __int16 *v26; // r8
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  LONG lVal; // eax
  int v33; // r8d
  unsigned int v34; // edx
  BYTE *v35; // rdx
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  const wchar_t *v46; // rax
  int v47; // r9d
  char *v48; // rbx
  void *v49; // rdx
  unsigned __int16 *v50; // r8
  __int64 v51; // r9
  char *v52; // rbx
  void *v53; // rdx
  BYTE *v54; // rax
  int v55; // ecx
  int v56; // r9d
  int v57; // r8d
  int uiVal; // eax
  int v59; // r8d
  BYTE *v60; // rdx
  char *v61; // rbx
  void *v62; // rdx
  void **v63; // rax
  void *v64; // rdx
  __int64 v65; // rcx
  char *v66; // rbx
  void *v67; // rdx
  void **v68; // rax
  void *v69; // rdx
  __int64 v70; // rcx
  const wchar_t *v71; // rax
  int v72; // r9d
  char *v73; // rbx
  void *v74; // rdx
  unsigned __int16 *v75; // r8
  __int64 v76; // r9
  char *v77; // rbx
  void *v78; // rdx
  BYTE *v79; // rax
  int bVal; // eax
  int v81; // r8d
  double *pElems; // rax
  double dblVal; // xmm1_8
  char *v84; // rbx
  void *v85; // rdx
  void **v86; // rax
  void *v87; // rdx
  __int64 v88; // rcx
  char *v89; // rbx
  void *v90; // rdx
  LPOLESTR lpwstr; // r8
  const char *v92; // rdx
  unsigned __int16 *v93; // rax
  char *v94; // rbx
  void *v95; // rdx
  void **v96; // rax
  void *v97; // rdx
  __int64 v98; // rcx
  char *v99; // rbx
  void *v100; // rdx
  void **v101; // rax
  void *v102; // rdx
  __int64 v103; // rcx
  float *v105; // rax
  float fltVal; // xmm1_4
  char *v107; // rbx
  void *v108; // rdx
  void **v109; // rax
  void *v110; // rdx
  __int64 v111; // rcx
  double v112; // xmm3_8
  char *v113; // rbx
  void *v114; // rdx
  void **v115; // rax
  void *v116; // rdx
  __int64 v117; // rcx
  const wchar_t *v118; // rax
  char *v119; // rbx
  void *v120; // rdx
  double v121; // xmm3_8
  unsigned __int16 *v122; // r8
  char *v123; // rbx
  void *v124; // rdx
  BYTE *v125; // rdx
  int v126; // r9d
  BYTE *pData; // rdx
  char *v128; // rbx
  void *v129; // rdx
  void **v130; // rax
  void *v131; // rdx
  __int64 v132; // rcx
  char *v133; // rbx
  void *v134; // rdx
  void **v135; // rax
  void *v136; // rdx
  __int64 v137; // rcx
  int iVal; // eax
  int v139; // r8d
  const wchar_t *NameFromWiaPropId; // rax
  int v142; // r9d
  char *v143; // rbx
  void *v144; // rdx
  unsigned __int16 *v145; // rax
  __int64 v146; // r9
  char *v147; // rbx
  void *v148; // rdx
  BYTE *v149; // rax
  unsigned int lpMem; // [rsp+20h] [rbp-49h]
  _BYTE v151[144]; // [rsp+30h] [rbp-39h] BYREF

  v6 = (char ***)WiaTrace_Trace("::ValidateRangeProp");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v151, v7, v8, (char **)"ValidateRangeProp", lpMem, v6);
  if ( (a1->vt & 0xEFFF) == 2 )
  {
    pData = a2->bstrblobVal.pData;
    if ( *((_WORD *)pData + 3) || *(_WORD *)pData == *((_WORD *)pData + 2) )
    {
      iVal = a1->iVal;
      v139 = *(__int16 *)pData;
      if ( a1->iVal >= *(_WORD *)pData
        && (__int16)iVal <= *((__int16 *)pData + 2)
        && (*((_WORD *)pData + 3) ? (iVal - v139) % *((__int16 *)pData + 3) == 0 : (_WORD)iVal == (unsigned __int16)v139) )
      {
        goto LABEL_77;
      }
    }
    v128 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
    WriteDbgTraceWarningWI("ValidateRangeProp", v128);
    WiaTrcLib::Free((WiaTrcLib *)v128, v129);
    v130 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
    WiaTrace_ProcessTrace_Ex(v132, v131, (void *)"ValidateRangeProp", 2, v130);
    if ( a3->ulKind )
    {
      NameFromWiaPropId = GetNameFromWiaPropId(a3->propid);
      v143 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", NameFromWiaPropId, v142);
      WriteDbgTraceWarningWI("ValidateRangeProp", v143);
      WiaTrcLib::Free((WiaTrcLib *)v143, v144);
      v145 = GetNameFromWiaPropId(a3->propid);
      v135 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v145, v146);
    }
    else
    {
      v133 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->iVal);
      WriteDbgTraceWarningWI("ValidateRangeProp", v133);
      WiaTrcLib::Free((WiaTrcLib *)v133, v134);
      v135 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, (unsigned int)a1->iVal);
    }
    WiaTrace_ProcessTrace_Ex(v137, v136, (void *)"ValidateRangeProp", 2, v135);
    v147 = (char *)WiaTrace_TraceLogWithSubComp(
                     0,
                     "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d",
                     *a2->cai.pElems,
                     *((__int16 *)a2->bstrblobVal.pData + 2),
                     *((__int16 *)a2->bstrblobVal.pData + 3));
    WriteDbgTraceWarningWI("ValidateRangeProp", v147);
    WiaTrcLib::Free((WiaTrcLib *)v147, v148);
    v149 = a2->bstrblobVal.pData;
    v57 = *(__int16 *)v149;
    v56 = *((__int16 *)v149 + 2);
    v55 = *((__int16 *)v149 + 3);
LABEL_80:
    v29 = (void **)WiaTrace_TraceWithSubComp(0, "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d", v57, v56, v55);
    goto LABEL_81;
  }
  if ( (a1->vt & 0xEFFF) == 3 )
  {
    v125 = a2->bstrblobVal.pData;
    v126 = *((_DWORD *)v125 + 3);
    if ( !v126 && *(_DWORD *)v125 != *((_DWORD *)v125 + 2) )
      goto LABEL_10;
    lVal = a1->lVal;
    v33 = *(_DWORD *)v125;
    if ( lVal < *(_DWORD *)v125 || lVal > *((_DWORD *)v125 + 2) )
      goto LABEL_10;
    if ( v126 )
    {
      v34 = (lVal - v33) % v126;
LABEL_18:
      if ( !v34 )
        goto LABEL_77;
      goto LABEL_10;
    }
    goto LABEL_20;
  }
  if ( (a1->vt & 0xEFFF) != 4 )
  {
    switch ( a1->vt & 0xEFFF )
    {
      case 5:
        pElems = a2->cadbl.pElems;
        dblVal = a1->dblVal;
        if ( *pElems <= dblVal && dblVal <= pElems[2] )
          goto LABEL_77;
        v84 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WriteDbgTraceWarningWI("ValidateRangeProp", v84);
        WiaTrcLib::Free((WiaTrcLib *)v84, v85);
        v86 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WiaTrace_ProcessTrace_Ex(v88, v87, (void *)"ValidateRangeProp", 2, v86);
        if ( a3->ulKind )
        {
          v93 = GetNameFromWiaPropId(a3->propid);
          v94 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %2.3f", v93, a1->hVal.QuadPart);
          WriteDbgTraceWarningWI("ValidateRangeProp", v94);
          WiaTrcLib::Free((WiaTrcLib *)v94, v95);
          lpwstr = GetNameFromWiaPropId(a3->propid);
          v92 = "    (propID) %S, value = %2.3f";
        }
        else
        {
          v89 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %2.3f", a3->lpwstr, a1->hVal.QuadPart);
          WriteDbgTraceWarningWI("ValidateRangeProp", v89);
          WiaTrcLib::Free((WiaTrcLib *)v89, v90);
          lpwstr = a3->lpwstr;
          v92 = "    (Name) %S, value = %2.3f";
        }
        v96 = (void **)WiaTrace_TraceWithSubComp(0, v92, lpwstr, a1->hVal.QuadPart);
        WiaTrace_ProcessTrace_Ex(v98, v97, (void *)"ValidateRangeProp", 2, v96);
        v99 = (char *)WiaTrace_TraceLogWithSubComp(
                        0,
                        "Valid RANGE is: MIN = %2.3f, MAX = %2.3f, STEP = %2.3f",
                        *a2->cabstr.pElems,
                        *((_QWORD *)a2->bstrblobVal.pData + 2),
                        *((_QWORD *)a2->bstrblobVal.pData + 3));
        WriteDbgTraceWarningWI("ValidateRangeProp", v99);
        WiaTrcLib::Free((WiaTrcLib *)v99, v100);
        v101 = (void **)WiaTrace_TraceWithSubComp(
                          0,
                          "Valid RANGE is: MIN = %2.3f, MAX = %2.3f, STEP = %2.3f",
                          *a2->cabstr.pElems,
                          *((_QWORD *)a2->bstrblobVal.pData + 2),
                          *((_QWORD *)a2->bstrblobVal.pData + 3));
        WiaTrace_ProcessTrace_Ex(v103, v102, (void *)"ValidateRangeProp", 2, v101);
        v9 = -2147024809;
        goto LABEL_54;
      case 17:
        v60 = a2->bstrblobVal.pData;
        if ( v60[3] || *v60 == v60[2] )
        {
          bVal = a1->bVal;
          v81 = *v60;
          if ( (unsigned __int8)bVal >= (unsigned __int8)v81 && (unsigned __int8)bVal <= v60[2] )
          {
            if ( v60[3] )
            {
              if ( !((bVal - v81) % v60[3]) )
                goto LABEL_77;
            }
            else if ( (_BYTE)bVal == (_BYTE)v81 )
            {
              goto LABEL_77;
            }
          }
        }
        v61 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WriteDbgTraceWarningWI("ValidateRangeProp", v61);
        WiaTrcLib::Free((WiaTrcLib *)v61, v62);
        v63 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WiaTrace_ProcessTrace_Ex(v65, v64, (void *)"ValidateRangeProp", 2, v63);
        if ( a3->ulKind )
        {
          v71 = GetNameFromWiaPropId(a3->propid);
          v73 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v71, v72);
          WriteDbgTraceWarningWI("ValidateRangeProp", v73);
          WiaTrcLib::Free((WiaTrcLib *)v73, v74);
          v75 = GetNameFromWiaPropId(a3->propid);
          v68 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v75, v76);
        }
        else
        {
          v66 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->bVal);
          WriteDbgTraceWarningWI("ValidateRangeProp", v66);
          WiaTrcLib::Free((WiaTrcLib *)v66, v67);
          v68 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->bVal);
        }
        WiaTrace_ProcessTrace_Ex(v70, v69, (void *)"ValidateRangeProp", 2, v68);
        v77 = (char *)WiaTrace_TraceLogWithSubComp(
                        0,
                        "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d",
                        *a2->bstrblobVal.pData,
                        a2->bstrblobVal.pData[2],
                        a2->bstrblobVal.pData[3]);
        WriteDbgTraceWarningWI("ValidateRangeProp", v77);
        WiaTrcLib::Free((WiaTrcLib *)v77, v78);
        v79 = a2->bstrblobVal.pData;
        v55 = v79[3];
        v56 = v79[2];
        v57 = *v79;
        break;
      case 18:
        v35 = a2->bstrblobVal.pData;
        if ( *((_WORD *)v35 + 3) || *(_WORD *)v35 == *((_WORD *)v35 + 2) )
        {
          uiVal = a1->uiVal;
          v59 = *(unsigned __int16 *)v35;
          if ( (unsigned __int16)uiVal >= (unsigned __int16)v59 && (unsigned __int16)uiVal <= *((_WORD *)v35 + 2) )
          {
            if ( *((_WORD *)v35 + 3) )
            {
              if ( !((uiVal - v59) % *((unsigned __int16 *)v35 + 3)) )
                goto LABEL_77;
            }
            else if ( (_WORD)uiVal == (_WORD)v59 )
            {
              goto LABEL_77;
            }
          }
        }
        v36 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WriteDbgTraceWarningWI("ValidateRangeProp", v36);
        WiaTrcLib::Free((WiaTrcLib *)v36, v37);
        v38 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
        WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"ValidateRangeProp", 2, v38);
        if ( a3->ulKind )
        {
          v46 = GetNameFromWiaPropId(a3->propid);
          v48 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v46, v47);
          WriteDbgTraceWarningWI("ValidateRangeProp", v48);
          WiaTrcLib::Free((WiaTrcLib *)v48, v49);
          v50 = GetNameFromWiaPropId(a3->propid);
          v43 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v50, v51);
        }
        else
        {
          v41 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->uiVal);
          WriteDbgTraceWarningWI("ValidateRangeProp", v41);
          WiaTrcLib::Free((WiaTrcLib *)v41, v42);
          v43 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->uiVal);
        }
        WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"ValidateRangeProp", 2, v43);
        v52 = (char *)WiaTrace_TraceLogWithSubComp(
                        0,
                        "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d",
                        *a2->caui.pElems,
                        *((unsigned __int16 *)a2->bstrblobVal.pData + 2),
                        *((unsigned __int16 *)a2->bstrblobVal.pData + 3));
        WriteDbgTraceWarningWI("ValidateRangeProp", v52);
        WiaTrcLib::Free((WiaTrcLib *)v52, v53);
        v54 = a2->bstrblobVal.pData;
        v55 = *((unsigned __int16 *)v54 + 3);
        v56 = *((unsigned __int16 *)v54 + 2);
        v57 = *(unsigned __int16 *)v54;
        break;
      default:
        v9 = 0;
        if ( (a1->vt & 0xEFFF) == 0x13 )
        {
          v10 = a2->bstrblobVal.pData;
          v11 = *((_DWORD *)v10 + 3);
          if ( !v11 && *(_DWORD *)v10 != *((_DWORD *)v10 + 2) )
            goto LABEL_10;
          lVal = a1->lVal;
          v33 = *(_DWORD *)v10;
          if ( (unsigned int)lVal < *(_DWORD *)v10 || (unsigned int)lVal > *((_DWORD *)v10 + 2) )
            goto LABEL_10;
          if ( v11 )
          {
            v34 = (lVal - v33) % v11;
            goto LABEL_18;
          }
LABEL_20:
          if ( lVal != v33 )
          {
LABEL_10:
            v12 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
            WriteDbgTraceWarningWI("ValidateRangeProp", v12);
            WiaTrcLib::Free((WiaTrcLib *)v12, v13);
            v14 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
            WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"ValidateRangeProp", 2, v14);
            if ( a3->ulKind )
            {
              v22 = GetNameFromWiaPropId(a3->propid);
              v24 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v22, v23);
              WriteDbgTraceWarningWI("ValidateRangeProp", v24);
              WiaTrcLib::Free((WiaTrcLib *)v24, v25);
              v26 = GetNameFromWiaPropId(a3->propid);
              v19 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v26, a1->ulVal);
            }
            else
            {
              v17 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->lVal);
              WriteDbgTraceWarningWI("ValidateRangeProp", v17);
              WiaTrcLib::Free((WiaTrcLib *)v17, v18);
              v19 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->ulVal);
            }
            WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"ValidateRangeProp", 2, v19);
            v27 = (char *)WiaTrace_TraceLogWithSubComp(
                            0,
                            "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d",
                            *a2->cal.pElems,
                            *((_DWORD *)a2->bstrblobVal.pData + 2),
                            *((_DWORD *)a2->bstrblobVal.pData + 3));
            WriteDbgTraceWarningWI("ValidateRangeProp", v27);
            WiaTrcLib::Free((WiaTrcLib *)v27, v28);
            v29 = (void **)WiaTrace_TraceWithSubComp(
                             0,
                             "Valid RANGE is: MIN = %d, MAX = %d, STEP = %d",
                             *a2->cal.pElems,
                             *((_DWORD *)a2->bstrblobVal.pData + 2),
                             *((_DWORD *)a2->bstrblobVal.pData + 3));
            goto LABEL_81;
          }
LABEL_77:
          CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v151);
          return 0;
        }
LABEL_54:
        CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v151);
        return v9;
    }
    goto LABEL_80;
  }
  v105 = a2->caflt.pElems;
  fltVal = a1->fltVal;
  if ( *v105 <= fltVal && fltVal <= v105[2] )
    goto LABEL_77;
  v107 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
  WriteDbgTraceWarningWI("ValidateRangeProp", v107);
  WiaTrcLib::Free((WiaTrcLib *)v107, v108);
  v109 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid RANGE value for : ");
  WiaTrace_ProcessTrace_Ex(v111, v110, (void *)"ValidateRangeProp", 2, v109);
  v112 = a1->fltVal;
  if ( a3->ulKind )
  {
    v118 = GetNameFromWiaPropId(a3->propid);
    v119 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %2.3f", v118, v112);
    WriteDbgTraceWarningWI("ValidateRangeProp", v119);
    WiaTrcLib::Free((WiaTrcLib *)v119, v120);
    v121 = a1->fltVal;
    v122 = GetNameFromWiaPropId(a3->propid);
    v115 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %2.3f", v122, v121);
  }
  else
  {
    v113 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %2.3f", a3->lpwstr, v112);
    WriteDbgTraceWarningWI("ValidateRangeProp", v113);
    WiaTrcLib::Free((WiaTrcLib *)v113, v114);
    v115 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %2.3f", a3->lpwstr, a1->fltVal);
  }
  WiaTrace_ProcessTrace_Ex(v117, v116, (void *)"ValidateRangeProp", 2, v115);
  v123 = (char *)WiaTrace_TraceLogWithSubComp(
                   0,
                   "Valid RANGE is: MIN = %2.3f, MAX = %2.3f, STEP = %2.3f",
                   *a2->caflt.pElems,
                   *((float *)a2->bstrblobVal.pData + 2),
                   *((float *)a2->bstrblobVal.pData + 3));
  WriteDbgTraceWarningWI("ValidateRangeProp", v123);
  WiaTrcLib::Free((WiaTrcLib *)v123, v124);
  v29 = (void **)WiaTrace_TraceWithSubComp(
                   0,
                   "Valid RANGE is: MIN = %2.3f, MAX = %2.3f, STEP = %2.3f",
                   *a2->caflt.pElems,
                   *((float *)a2->bstrblobVal.pData + 2),
                   *((float *)a2->bstrblobVal.pData + 3));
LABEL_81:
  WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"ValidateRangeProp", 2, v29);
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v151);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003eea4  push    rbp
0x18003eea6  push    rbx
0x18003eea7  push    rsi
0x18003eea8  push    rdi
0x18003eea9  push    r12
0x18003eeab  push    r13
0x18003eead  push    r14
0x18003eeaf  push    r15
0x18003eeb1  lea     rbp, [rsp-1Fh]
0x18003eeb6  sub     rsp, 88h
0x18003eebd  mov     r14, rcx
0x18003eec0  mov     rsi, r8
0x18003eec3  lea     rcx, aValidaterangep_0; "::ValidateRangeProp"
0x18003eeca  mov     r15, rdx
0x18003eecd  call    WiaTrace_Trace
0x18003eed2  lea     r12, aValidaterangep; "ValidateRangeProp"
0x18003eed9  mov     [rsp+0C0h+var_98], rax; struct tagWiaTraceData_Type *
0x18003eede  mov     r9, r12; char *
0x18003eee1  lea     rcx, [rbp+57h+var_90]; this
0x18003eee5  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18003eeea  movzx   ecx, word ptr [r14]
0x18003eeee  mov     r13d, 2
0x18003eef4  btr     ecx, 0Ch
0x18003eef8  sub     ecx, r13d
0x18003eefb  jz      loc_18003F78A
0x18003ef01  sub     ecx, 1
0x18003ef04  jz      loc_18003F742
0x18003ef0a  sub     ecx, 1
0x18003ef0d  jz      loc_18003F599
0x18003ef13  sub     ecx, 1
0x18003ef16  jz      loc_18003F3E9
0x18003ef1c  sub     ecx, 0Ch
0x18003ef1f  jz      loc_18003F257
0x18003ef25  sub     ecx, 1
0x18003ef28  jz      loc_18003F0C0
0x18003ef2e  xor     edi, edi
0x18003ef30  cmp     ecx, 1
0x18003ef33  jnz     loc_18003F589
0x18003ef39  mov     rdx, [r15+10h]
0x18003ef3d  mov     r9d, [rdx+0Ch]
0x18003ef41  test    r9d, r9d
0x18003ef44  jnz     loc_18003F07F
0x18003ef4a  mov     eax, [rdx+8]
0x18003ef4d  cmp     [rdx], eax
0x18003ef4f  jz      loc_18003F07F
0x18003ef55  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003ef5c  xor     ecx, ecx
0x18003ef5e  call    WiaTrace_TraceLogWithSubComp
0x18003ef63  mov     rdx, rax; char *
0x18003ef66  mov     rcx, r12; char *
0x18003ef69  mov     rbx, rax
0x18003ef6c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003ef71  mov     rcx, rbx; this
0x18003ef74  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003ef79  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003ef80  xor     ecx, ecx
0x18003ef82  call    WiaTrace_TraceWithSubComp
0x18003ef87  mov     r9d, r13d; int
0x18003ef8a  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003ef8f  mov     r8, r12; int
0x18003ef92  call    WiaTrace_ProcessTrace_Ex
0x18003ef97  mov     r9d, [r14+8]
0x18003ef9b  cmp     [rsi], edi
0x18003ef9d  jnz     short loc_18003EFD4
0x18003ef9f  mov     r8, [rsi+8]
0x18003efa3  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003efaa  xor     ecx, ecx
0x18003efac  call    WiaTrace_TraceLogWithSubComp
0x18003efb1  mov     rdx, rax; char *
0x18003efb4  mov     rcx, r12; char *
0x18003efb7  mov     rbx, rax
0x18003efba  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003efbf  mov     rcx, rbx; this
0x18003efc2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003efc7  mov     r8, [rsi+8]
0x18003efcb  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003efd2  jmp     short loc_18003F015
0x18003efd4  mov     ecx, [rsi+8]; unsigned int
0x18003efd7  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003efdc  mov     r8, rax
0x18003efdf  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003efe6  xor     ecx, ecx
0x18003efe8  call    WiaTrace_TraceLogWithSubComp
0x18003efed  mov     rdx, rax; char *
0x18003eff0  mov     rcx, r12; char *
0x18003eff3  mov     rbx, rax
0x18003eff6  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003effb  mov     rcx, rbx; this
0x18003effe  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f003  mov     ecx, [rsi+8]; unsigned int
0x18003f006  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003f00b  mov     r8, rax
0x18003f00e  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003f015  mov     r9d, [r14+8]
0x18003f019  xor     ecx, ecx
0x18003f01b  call    WiaTrace_TraceWithSubComp
0x18003f020  mov     r9d, r13d; int
0x18003f023  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003f028  mov     r8, r12; int
0x18003f02b  call    WiaTrace_ProcessTrace_Ex
0x18003f030  mov     r8, [r15+10h]
0x18003f034  lea     rdx, aValidRangeIsMi_0; "Valid RANGE is: MIN = %d, MAX = %d, STE"...
0x18003f03b  xor     ecx, ecx
0x18003f03d  mov     eax, [r8+0Ch]
0x18003f041  mov     r9d, [r8+8]
0x18003f045  mov     r8d, [r8]
0x18003f048  mov     dword ptr [rsp+0C0h+lpMem], eax
0x18003f04c  call    WiaTrace_TraceLogWithSubComp
0x18003f051  mov     rdx, rax; char *
0x18003f054  mov     rcx, r12; char *
0x18003f057  mov     rbx, rax
0x18003f05a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f05f  mov     rcx, rbx; this
0x18003f062  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f067  mov     r8, [r15+10h]
0x18003f06b  mov     eax, [r8+0Ch]
0x18003f06f  mov     r9d, [r8+8]
0x18003f073  mov     r8d, [r8]
0x18003f076  mov     dword ptr [rsp+0C0h+lpMem], eax
0x18003f07a  jmp     loc_18003F929
0x18003f07f  mov     eax, [r14+8]
0x18003f083  mov     r8d, [rdx]
0x18003f086  cmp     eax, r8d
0x18003f089  jb      loc_18003EF55
0x18003f08f  cmp     eax, [rdx+8]
0x18003f092  ja      loc_18003EF55
0x18003f098  test    r9d, r9d
0x18003f09b  jz      short loc_18003F0B2
0x18003f09d  sub     eax, r8d
0x18003f0a0  xor     edx, edx
0x18003f0a2  div     r9d
0x18003f0a5  test    edx, edx
0x18003f0a7  jnz     loc_18003EF55
0x18003f0ad  jmp     loc_18003F86E
0x18003f0b2  cmp     eax, r8d
0x18003f0b5  jz      loc_18003F86E
0x18003f0bb  jmp     loc_18003EF55
0x18003f0c0  mov     rdx, [r15+10h]
0x18003f0c4  xor     edi, edi
0x18003f0c6  cmp     [rdx+6], di
0x18003f0ca  jnz     loc_18003F20E
0x18003f0d0  movzx   eax, word ptr [rdx+4]
0x18003f0d4  cmp     [rdx], ax
0x18003f0d7  jz      loc_18003F20E
0x18003f0dd  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003f0e4  xor     ecx, ecx
0x18003f0e6  call    WiaTrace_TraceLogWithSubComp
0x18003f0eb  mov     rdx, rax; char *
0x18003f0ee  mov     rcx, r12; char *
0x18003f0f1  mov     rbx, rax
0x18003f0f4  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f0f9  mov     rcx, rbx; this
0x18003f0fc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f101  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003f108  xor     ecx, ecx
0x18003f10a  call    WiaTrace_TraceWithSubComp
0x18003f10f  mov     r9d, r13d; int
0x18003f112  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003f117  mov     r8, r12; int
0x18003f11a  call    WiaTrace_ProcessTrace_Ex
0x18003f11f  movzx   r9d, word ptr [r14+8]
0x18003f124  cmp     [rsi], edi
0x18003f126  jnz     short loc_18003F162
0x18003f128  mov     r8, [rsi+8]
0x18003f12c  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003f133  xor     ecx, ecx
0x18003f135  call    WiaTrace_TraceLogWithSubComp
0x18003f13a  mov     rdx, rax; char *
0x18003f13d  mov     rcx, r12; char *
0x18003f140  mov     rbx, rax
0x18003f143  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f148  mov     rcx, rbx; this
0x18003f14b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f150  movzx   r9d, word ptr [r14+8]
0x18003f155  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003f15c  mov     r8, [rsi+8]
0x18003f160  jmp     short loc_18003F1A8
0x18003f162  mov     ecx, [rsi+8]; unsigned int
0x18003f165  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003f16a  mov     r8, rax
0x18003f16d  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003f174  xor     ecx, ecx
0x18003f176  call    WiaTrace_TraceLogWithSubComp
0x18003f17b  mov     rdx, rax; char *
0x18003f17e  mov     rcx, r12; char *
0x18003f181  mov     rbx, rax
0x18003f184  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f189  mov     rcx, rbx; this
0x18003f18c  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f191  movzx   r9d, word ptr [r14+8]
0x18003f196  mov     ecx, [rsi+8]; unsigned int
0x18003f199  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003f19e  mov     r8, rax
0x18003f1a1  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003f1a8  xor     ecx, ecx
0x18003f1aa  call    WiaTrace_TraceWithSubComp
0x18003f1af  mov     r9d, r13d; int
0x18003f1b2  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003f1b7  mov     r8, r12; int
0x18003f1ba  call    WiaTrace_ProcessTrace_Ex
0x18003f1bf  mov     rax, [r15+10h]
0x18003f1c3  lea     rdx, aValidRangeIsMi_0; "Valid RANGE is: MIN = %d, MAX = %d, STE"...
0x18003f1ca  movzx   ecx, word ptr [rax+6]
0x18003f1ce  movzx   r9d, word ptr [rax+4]
0x18003f1d3  movzx   r8d, word ptr [rax]
0x18003f1d7  mov     dword ptr [rsp+0C0h+lpMem], ecx
0x18003f1db  xor     ecx, ecx
0x18003f1dd  call    WiaTrace_TraceLogWithSubComp
0x18003f1e2  mov     rdx, rax; char *
0x18003f1e5  mov     rcx, r12; char *
0x18003f1e8  mov     rbx, rax
0x18003f1eb  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f1f0  mov     rcx, rbx; this
0x18003f1f3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f1f8  mov     rax, [r15+10h]
0x18003f1fc  movzx   ecx, word ptr [rax+6]
0x18003f200  movzx   r9d, word ptr [rax+4]
0x18003f205  movzx   r8d, word ptr [rax]
0x18003f209  jmp     loc_18003F925
0x18003f20e  movzx   eax, word ptr [r14+8]
0x18003f213  movzx   r8d, word ptr [rdx]
0x18003f217  cmp     ax, r8w
0x18003f21b  jb      loc_18003F0DD
0x18003f221  cmp     ax, [rdx+4]
0x18003f225  ja      loc_18003F0DD
0x18003f22b  cmp     [rdx+6], di
0x18003f22f  jz      short loc_18003F248
0x18003f231  movzx   ecx, word ptr [rdx+6]
0x18003f235  sub     eax, r8d
0x18003f238  cdq
0x18003f239  idiv    ecx
0x18003f23b  test    edx, edx
0x18003f23d  jnz     loc_18003F0DD
0x18003f243  jmp     loc_18003F86E
0x18003f248  cmp     ax, r8w
0x18003f24c  jz      loc_18003F86E
0x18003f252  jmp     loc_18003F0DD
0x18003f257  mov     rdx, [r15+10h]
0x18003f25b  xor     edi, edi
0x18003f25d  cmp     [rdx+3], dil
0x18003f261  jnz     loc_18003F3A3
0x18003f267  mov     al, [rdx+2]
0x18003f26a  cmp     [rdx], al
0x18003f26c  jz      loc_18003F3A3
0x18003f272  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003f279  xor     ecx, ecx
0x18003f27b  call    WiaTrace_TraceLogWithSubComp
0x18003f280  mov     rdx, rax; char *
0x18003f283  mov     rcx, r12; char *
0x18003f286  mov     rbx, rax
0x18003f289  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f28e  mov     rcx, rbx; this
0x18003f291  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f296  lea     rdx, aWiasvalidateit_4; "wiasValidateItemProperties, invalid RAN"...
0x18003f29d  xor     ecx, ecx
0x18003f29f  call    WiaTrace_TraceWithSubComp
0x18003f2a4  mov     r9d, r13d; int
0x18003f2a7  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003f2ac  mov     r8, r12; int
0x18003f2af  call    WiaTrace_ProcessTrace_Ex
0x18003f2b4  movzx   r9d, byte ptr [r14+8]
0x18003f2b9  cmp     [rsi], edi
0x18003f2bb  jnz     short loc_18003F2F7
0x18003f2bd  mov     r8, [rsi+8]
0x18003f2c1  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003f2c8  xor     ecx, ecx
0x18003f2ca  call    WiaTrace_TraceLogWithSubComp
0x18003f2cf  mov     rdx, rax; char *
0x18003f2d2  mov     rcx, r12; char *
0x18003f2d5  mov     rbx, rax
0x18003f2d8  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f2dd  mov     rcx, rbx; this
0x18003f2e0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f2e5  movzx   r9d, byte ptr [r14+8]
0x18003f2ea  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003f2f1  mov     r8, [rsi+8]
0x18003f2f5  jmp     short loc_18003F33D
0x18003f2f7  mov     ecx, [rsi+8]; unsigned int
0x18003f2fa  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003f2ff  mov     r8, rax
0x18003f302  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003f309  xor     ecx, ecx
0x18003f30b  call    WiaTrace_TraceLogWithSubComp
0x18003f310  mov     rdx, rax; char *
0x18003f313  mov     rcx, r12; char *
0x18003f316  mov     rbx, rax
0x18003f319  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003f31e  mov     rcx, rbx; this
0x18003f321  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003f326  movzx   r9d, byte ptr [r14+8]
0x18003f32b  mov     ecx, [rsi+8]; unsigned int
0x18003f32e  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003f333  mov     r8, rax
0x18003f336  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003f33d  xor     ecx, ecx
0x18003f33f  call    WiaTrace_TraceWithSubComp
0x18003f344  mov     r9d, r13d; int
0x18003f347  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003f34c  mov     r8, r12; int
0x18003f34f  call    WiaTrace_ProcessTrace_Ex
  ... truncated ...
```
