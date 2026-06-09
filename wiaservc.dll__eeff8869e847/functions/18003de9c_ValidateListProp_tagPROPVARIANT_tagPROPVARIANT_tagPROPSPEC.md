# ValidateListProp(tagPROPVARIANT *,tagPROPVARIANT *,tagPROPSPEC *)

- ea: `0x18003de9c`
- end: `0x18003ee9b`
- name: `?ValidateListProp@@YAJPEAUtagPROPVARIANT@@0PEAUtagPROPSPEC@@@Z`
- size: `4095`
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
- `0x18003de9c`

## import_xrefs

- `RPCRT4!RpcStringFreeA` at `0x18003e0ba`
- `RPCRT4!RpcStringFreeA` at `0x18003e176`
- `RPCRT4!RpcStringFreeA` at `0x18003e0ba`
- `RPCRT4!RpcStringFreeA` at `0x18003e176`
- `RPCRT4!UuidToStringA` at `0x18003df7e`
- `RPCRT4!UuidToStringA` at `0x18003e11e`
- `RPCRT4!UuidToStringA` at `0x18003df7e`
- `RPCRT4!UuidToStringA` at `0x18003e11e`

## string_xrefs

- `0x18003dfd5`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003dff7`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e1ba`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e1de`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e37f`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e3a3`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e549`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e56d`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e739`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e75d`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e902`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003e926`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003eaea`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003eb0e`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003ece8`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003ed0c`: `wiasValidateItemProperties, invalid LIST value for : `
- `0x18003df8a`: `wiasValidateItemProperties, Out of memory`
- `0x18003dfac`: `wiasValidateItemProperties, Out of memory`

## pseudocode

```c
__int64 __fastcall ValidateListProp(struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2, struct tagPROPSPEC *a3)
{
  char ***v6; // rax
  char *v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // r14d
  unsigned int kk; // edx
  BSTR *pbstrVal; // r9
  BYTE *v12; // rcx
  char *v13; // rax
  const UUID *puuid; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  const wchar_t *v30; // rax
  char *v31; // rbx
  void *v32; // rdx
  unsigned __int16 *v33; // r8
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  unsigned int v39; // edi
  char *v40; // rbx
  void *v41; // rdx
  void **v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  unsigned int v45; // r14d
  unsigned int jj; // edx
  char *v47; // rbx
  void *v48; // rdx
  void **v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  char *v52; // rbx
  void *v53; // rdx
  void **v54; // rax
  void *v55; // rdx
  __int64 v56; // rcx
  const wchar_t *v57; // rax
  int v58; // r9d
  char *v59; // rbx
  void *v60; // rdx
  unsigned __int16 *v61; // r8
  char *v62; // rbx
  void *v63; // rdx
  void **v64; // rax
  void *v65; // rdx
  __int64 v66; // rcx
  char *v67; // rbx
  void *v68; // rdx
  void **v69; // rax
  void *v70; // rdx
  __int64 v71; // rcx
  unsigned int v72; // r14d
  unsigned int ii; // edx
  char *v74; // rbx
  void *v75; // rdx
  void **v76; // rax
  void *v77; // rdx
  __int64 v78; // rcx
  char *v79; // rbx
  void *v80; // rdx
  void **v81; // rax
  void *v82; // rdx
  __int64 v83; // rcx
  const wchar_t *v84; // rax
  int v85; // r9d
  char *v86; // rbx
  void *v87; // rdx
  unsigned __int16 *v88; // r8
  __int64 v89; // r9
  char *v90; // rbx
  void *v91; // rdx
  void **v92; // rax
  void *v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // rdi
  char *v96; // rbx
  void *v97; // rdx
  void **v98; // rax
  void *v99; // rdx
  __int64 v100; // rcx
  unsigned int v101; // r14d
  unsigned int n; // edx
  char *v103; // rbx
  void *v104; // rdx
  void **v105; // rax
  void *v106; // rdx
  __int64 v107; // rcx
  char *v108; // rbx
  void *v109; // rdx
  void **v110; // rax
  void *v111; // rdx
  __int64 v112; // rcx
  const wchar_t *v113; // rax
  int v114; // r9d
  char *v115; // rbx
  void *v116; // rdx
  unsigned __int16 *v117; // r8
  __int64 v118; // r9
  char *v119; // rbx
  void *v120; // rdx
  void **v121; // rax
  void *v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rdi
  char *v125; // rbx
  void *v126; // rdx
  void **v127; // rax
  void *v128; // rdx
  __int64 v129; // rcx
  unsigned int v130; // r14d
  unsigned int m; // r8d
  BSTR bstrVal; // rdx
  __int64 v133; // r10
  int v134; // eax
  int v135; // ecx
  char *v136; // rbx
  void *v137; // rdx
  void **v138; // rax
  void *v139; // rdx
  __int64 v140; // rcx
  char *v141; // rbx
  void *v142; // rdx
  void **v143; // rax
  void *v144; // rdx
  __int64 v145; // rcx
  const wchar_t *v146; // rax
  const wchar_t *v147; // r9
  char *v148; // rbx
  void *v149; // rdx
  unsigned __int16 *v150; // r8
  char *v151; // rbx
  void *v152; // rdx
  void **v153; // rax
  void *v154; // rdx
  __int64 v155; // rcx
  char *v156; // rbx
  void *v157; // rdx
  void **v158; // rax
  void *v159; // rdx
  __int64 v160; // rcx
  unsigned int v161; // r14d
  unsigned int k; // edx
  char *v163; // rbx
  void *v164; // rdx
  void **v165; // rax
  void *v166; // rdx
  __int64 v167; // rcx
  char *v168; // rbx
  void *v169; // rdx
  LPOLESTR lpwstr; // r8
  const char *v171; // rdx
  const wchar_t *v172; // rax
  char *v173; // rbx
  void *v174; // rdx
  void **v175; // rax
  void *v176; // rdx
  __int64 v177; // rcx
  char *v178; // rbx
  void *v179; // rdx
  void **v180; // rax
  void *v181; // rdx
  __int64 v182; // rcx
  __int64 v183; // rdi
  char *v184; // rbx
  void *v185; // rdx
  void **v186; // rax
  void *v187; // rdx
  __int64 v188; // rcx
  unsigned int v189; // r14d
  unsigned int j; // edx
  char *v191; // rbx
  void *v192; // rdx
  void **v193; // rax
  void *v194; // rdx
  __int64 v195; // rcx
  float fltVal; // xmm3_4
  char *v197; // rbx
  void *v198; // rdx
  void **v199; // rax
  void *v200; // rdx
  __int64 v201; // rcx
  const wchar_t *v202; // rax
  char *v203; // rbx
  void *v204; // rdx
  double v205; // xmm3_8
  unsigned __int16 *v206; // r8
  char *v207; // rbx
  void *v208; // rdx
  void **v209; // rax
  void *v210; // rdx
  __int64 v211; // rcx
  __int64 v212; // rdi
  char *v213; // rbx
  void *v214; // rdx
  void **v215; // rax
  void *v216; // rdx
  __int64 v217; // rcx
  unsigned int v218; // r14d
  unsigned int i; // edx
  char *v221; // rbx
  void *v222; // rdx
  void **v223; // rax
  void *v224; // rdx
  __int64 v225; // rcx
  char *v226; // rbx
  void *v227; // rdx
  void **v228; // rax
  void *v229; // rdx
  __int64 v230; // rcx
  const wchar_t *NameFromWiaPropId; // rax
  int v232; // r9d
  char *v233; // rbx
  void *v234; // rdx
  unsigned __int16 *v235; // r8
  char *v236; // rbx
  void *v237; // rdx
  void **v238; // rax
  void *v239; // rdx
  __int64 v240; // rcx
  char *v241; // rbx
  void *v242; // rdx
  void **v243; // rax
  void *v244; // rdx
  __int64 v245; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-49h]
  _BYTE v247[144]; // [rsp+30h] [rbp-39h] BYREF
  RPC_CSTR StringUuid; // [rsp+D0h] [rbp+67h] BYREF

  v6 = (char ***)WiaTrace_Trace("::ValidateListProp");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v247, v7, v8, (char **)"ValidateListProp", lpMem, v6);
  switch ( a1->vt & 0xEFFF )
  {
    case 3:
      v218 = 0;
      for ( i = 0; i < a2->lVal - 2; ++i )
      {
        if ( a1->lVal == *(_DWORD *)&a2->bstrblobVal.pData[4 * i + 8] )
          goto LABEL_93;
      }
      v221 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v221);
      WiaTrcLib::Free((WiaTrcLib *)v221, v222);
      v223 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v225, v224, (void *)"ValidateListProp", 2, v223);
      if ( a3->ulKind )
      {
        NameFromWiaPropId = GetNameFromWiaPropId(a3->propid);
        v233 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", NameFromWiaPropId, v232);
        WriteDbgTraceWarningWI("ValidateListProp", v233);
        WiaTrcLib::Free((WiaTrcLib *)v233, v234);
        v235 = GetNameFromWiaPropId(a3->propid);
        v228 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v235, a1->ulVal);
      }
      else
      {
        v226 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->lVal);
        WriteDbgTraceWarningWI("ValidateListProp", v226);
        WiaTrcLib::Free((WiaTrcLib *)v226, v227);
        v228 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->ulVal);
      }
      WiaTrace_ProcessTrace_Ex(v230, v229, (void *)"ValidateListProp", 2, v228);
      v236 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v236);
      WiaTrcLib::Free((WiaTrcLib *)v236, v237);
      v238 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v240, v239, (void *)"ValidateListProp", 2, v238);
      if ( a2->lVal != 2 )
      {
        do
        {
          v241 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v218 + 8]);
          WriteDbgTraceWarningWI("ValidateListProp", v241);
          WiaTrcLib::Free((WiaTrcLib *)v241, v242);
          v243 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v218 + 8]);
          WiaTrace_ProcessTrace_Ex(v245, v244, (void *)"ValidateListProp", 2, v243);
          ++v218;
        }
        while ( v218 < a2->lVal - 2 );
      }
      goto LABEL_99;
    case 4:
      v189 = 0;
      for ( j = 0; j < a2->lVal - 2; ++j )
      {
        if ( a1->fltVal == *(float *)&a2->bstrblobVal.pData[4 * j + 8] )
          goto LABEL_93;
      }
      v191 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v191);
      WiaTrcLib::Free((WiaTrcLib *)v191, v192);
      v193 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v195, v194, (void *)"ValidateListProp", 2, v193);
      fltVal = a1->fltVal;
      if ( a3->ulKind )
      {
        v202 = GetNameFromWiaPropId(a3->propid);
        v203 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v202, fltVal);
        WriteDbgTraceWarningWI("ValidateListProp", v203);
        WiaTrcLib::Free((WiaTrcLib *)v203, v204);
        v205 = a1->fltVal;
        v206 = GetNameFromWiaPropId(a3->propid);
        v199 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v206, v205);
      }
      else
      {
        v197 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, fltVal);
        WriteDbgTraceWarningWI("ValidateListProp", v197);
        WiaTrcLib::Free((WiaTrcLib *)v197, v198);
        v199 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->fltVal);
      }
      WiaTrace_ProcessTrace_Ex(v201, v200, (void *)"ValidateListProp", 2, v199);
      v207 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v207);
      WiaTrcLib::Free((WiaTrcLib *)v207, v208);
      v209 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v211, v210, (void *)"ValidateListProp", 2, v209);
      if ( a2->lVal != 2 )
      {
        do
        {
          v212 = v189 + 2;
          v213 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v212]);
          WriteDbgTraceWarningWI("ValidateListProp", v213);
          WiaTrcLib::Free((WiaTrcLib *)v213, v214);
          v215 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v212]);
          WiaTrace_ProcessTrace_Ex(v217, v216, (void *)"ValidateListProp", 2, v215);
          ++v189;
        }
        while ( v189 < a2->lVal - 2 );
      }
      goto LABEL_99;
    case 5:
      v161 = 0;
      for ( k = 0; k < a2->lVal - 2; ++k )
      {
        if ( a1->dblVal == *(double *)&a2->bstrblobVal.pData[8 * k + 16] )
          goto LABEL_93;
      }
      v163 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v163);
      WiaTrcLib::Free((WiaTrcLib *)v163, v164);
      v165 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v167, v166, (void *)"ValidateListProp", 2, v165);
      if ( a3->ulKind )
      {
        v172 = GetNameFromWiaPropId(a3->propid);
        v173 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v172, a1->hVal.QuadPart);
        WriteDbgTraceWarningWI("ValidateListProp", v173);
        WiaTrcLib::Free((WiaTrcLib *)v173, v174);
        lpwstr = GetNameFromWiaPropId(a3->propid);
        v171 = "    (propID) %S, value = %d";
      }
      else
      {
        v168 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->hVal.QuadPart);
        WriteDbgTraceWarningWI("ValidateListProp", v168);
        WiaTrcLib::Free((WiaTrcLib *)v168, v169);
        lpwstr = a3->lpwstr;
        v171 = "    (Name) %S, value = %d";
      }
      v175 = (void **)WiaTrace_TraceWithSubComp(0, v171, lpwstr, a1->hVal.QuadPart);
      WiaTrace_ProcessTrace_Ex(v177, v176, (void *)"ValidateListProp", 2, v175);
      v178 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v178);
      WiaTrcLib::Free((WiaTrcLib *)v178, v179);
      v180 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v182, v181, (void *)"ValidateListProp", 2, v180);
      if ( a2->lVal != 2 )
      {
        do
        {
          v183 = v161 + 2;
          v184 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", *(_QWORD *)&a2->bstrblobVal.pData[8 * v183]);
          WriteDbgTraceWarningWI("ValidateListProp", v184);
          WiaTrcLib::Free((WiaTrcLib *)v184, v185);
          v186 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", *(_QWORD *)&a2->bstrblobVal.pData[8 * v183]);
          WiaTrace_ProcessTrace_Ex(v188, v187, (void *)"ValidateListProp", 2, v186);
          ++v161;
        }
        while ( v161 < a2->lVal - 2 );
      }
      goto LABEL_99;
    case 8:
      v130 = 0;
      if ( a1->hVal.QuadPart )
      {
        for ( m = 0; m < a2->lVal - 2; ++m )
        {
          bstrVal = a1->bstrVal;
          v133 = *(_QWORD *)&a2->bstrblobVal.pData[8 * m + 16] - (_QWORD)bstrVal;
          do
          {
            v134 = *(BSTR)((char *)bstrVal + v133);
            v135 = *bstrVal - v134;
            if ( v135 )
              break;
            ++bstrVal;
          }
          while ( v134 );
          if ( !v135 )
            goto LABEL_93;
        }
        v136 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
        WriteDbgTraceWarningWI("ValidateListProp", v136);
        WiaTrcLib::Free((WiaTrcLib *)v136, v137);
        v138 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
        WiaTrace_ProcessTrace_Ex(v140, v139, (void *)"ValidateListProp", 2, v138);
        if ( a3->ulKind )
        {
          v146 = GetNameFromWiaPropId(a3->propid);
          v148 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %S", v146, v147);
          WriteDbgTraceWarningWI("ValidateListProp", v148);
          WiaTrcLib::Free((WiaTrcLib *)v148, v149);
          v150 = GetNameFromWiaPropId(a3->propid);
          v143 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %S", v150, a1->hVal.QuadPart);
        }
        else
        {
          v141 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %S", a3->lpwstr, a1->bstrVal);
          WriteDbgTraceWarningWI("ValidateListProp", v141);
          WiaTrcLib::Free((WiaTrcLib *)v141, v142);
          v143 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %S", a3->lpwstr, a1->hVal.QuadPart);
        }
        WiaTrace_ProcessTrace_Ex(v145, v144, (void *)"ValidateListProp", 2, v143);
        v151 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
        WriteDbgTraceWarningWI("ValidateListProp", v151);
        WiaTrcLib::Free((WiaTrcLib *)v151, v152);
        v153 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
        WiaTrace_ProcessTrace_Ex(v155, v154, (void *)"ValidateListProp", 2, v153);
        if ( a2->lVal != 2 )
        {
          do
          {
            v156 = (char *)WiaTrace_TraceLogWithSubComp(
                             0,
                             "    %S",
                             *(const wchar_t **)&a2->bstrblobVal.pData[8 * v130 + 16]);
            WriteDbgTraceWarningWI("ValidateListProp", v156);
            WiaTrcLib::Free((WiaTrcLib *)v156, v157);
            v158 = (void **)WiaTrace_TraceWithSubComp(
                              0,
                              "    %S",
                              *(const wchar_t **)&a2->bstrblobVal.pData[8 * v130 + 16]);
            WiaTrace_ProcessTrace_Ex(v160, v159, (void *)"ValidateListProp", 2, v158);
            ++v130;
          }
          while ( v130 < a2->lVal - 2 );
        }
        goto LABEL_99;
      }
      goto LABEL_93;
    case 17:
      v101 = 0;
      for ( n = 0; n < a2->lVal - 2; ++n )
      {
        if ( a1->cVal == a2->bstrblobVal.pData[n + 2] )
          goto LABEL_93;
      }
      v103 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v103);
      WiaTrcLib::Free((WiaTrcLib *)v103, v104);
      v105 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v107, v106, (void *)"ValidateListProp", 2, v105);
      if ( a3->ulKind )
      {
        v113 = GetNameFromWiaPropId(a3->propid);
        v115 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v113, v114);
        WriteDbgTraceWarningWI("ValidateListProp", v115);
        WiaTrcLib::Free((WiaTrcLib *)v115, v116);
        v117 = GetNameFromWiaPropId(a3->propid);
        v110 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v117, v118);
      }
      else
      {
        v108 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->bVal);
        WriteDbgTraceWarningWI("ValidateListProp", v108);
        WiaTrcLib::Free((WiaTrcLib *)v108, v109);
        v110 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->bVal);
      }
      WiaTrace_ProcessTrace_Ex(v112, v111, (void *)"ValidateListProp", 2, v110);
      v119 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v119);
      WiaTrcLib::Free((WiaTrcLib *)v119, v120);
      v121 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v123, v122, (void *)"ValidateListProp", 2, v121);
      if ( a2->lVal != 2 )
      {
        do
        {
          v124 = v101 + 2;
          v125 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", a2->bstrblobVal.pData[v124]);
          WriteDbgTraceWarningWI("ValidateListProp", v125);
          WiaTrcLib::Free((WiaTrcLib *)v125, v126);
          v127 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", a2->bstrblobVal.pData[v124]);
          WiaTrace_ProcessTrace_Ex(v129, v128, (void *)"ValidateListProp", 2, v127);
          ++v101;
        }
        while ( v101 < a2->lVal - 2 );
      }
      goto LABEL_99;
    case 18:
      v72 = 0;
      for ( ii = 0; ii < a2->lVal - 2; ++ii )
      {
        if ( a1->iVal == *(_WORD *)&a2->bstrblobVal.pData[2 * ii + 4] )
          goto LABEL_93;
      }
      v74 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v74);
      WiaTrcLib::Free((WiaTrcLib *)v74, v75);
      v76 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v78, v77, (void *)"ValidateListProp", 2, v76);
      if ( a3->ulKind )
      {
        v84 = GetNameFromWiaPropId(a3->propid);
        v86 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v84, v85);
        WriteDbgTraceWarningWI("ValidateListProp", v86);
        WiaTrcLib::Free((WiaTrcLib *)v86, v87);
        v88 = GetNameFromWiaPropId(a3->propid);
        v81 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v88, v89);
      }
      else
      {
        v79 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->iVal);
        WriteDbgTraceWarningWI("ValidateListProp", v79);
        WiaTrcLib::Free((WiaTrcLib *)v79, v80);
        v81 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, (unsigned int)a1->iVal);
      }
      WiaTrace_ProcessTrace_Ex(v83, v82, (void *)"ValidateListProp", 2, v81);
      v90 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v90);
      WiaTrcLib::Free((WiaTrcLib *)v90, v91);
      v92 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v94, v93, (void *)"ValidateListProp", 2, v92);
      if ( a2->lVal != 2 )
      {
        do
        {
          v95 = v72 + 2;
          v96 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", *(__int16 *)&a2->bstrblobVal.pData[2 * v95]);
          WriteDbgTraceWarningWI("ValidateListProp", v96);
          WiaTrcLib::Free((WiaTrcLib *)v96, v97);
          v98 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", *(__int16 *)&a2->bstrblobVal.pData[2 * v95]);
          WiaTrace_ProcessTrace_Ex(v100, v99, (void *)"ValidateListProp", 2, v98);
          ++v72;
        }
        while ( v72 < a2->lVal - 2 );
      }
      goto LABEL_99;
    case 19:
      v45 = 0;
      for ( jj = 0; jj < a2->lVal - 2; ++jj )
      {
        if ( a1->lVal == *(_DWORD *)&a2->bstrblobVal.pData[4 * jj + 8] )
          goto LABEL_93;
      }
      v47 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WriteDbgTraceWarningWI("ValidateListProp", v47);
      WiaTrcLib::Free((WiaTrcLib *)v47, v48);
      v49 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
      WiaTrace_ProcessTrace_Ex(v51, v50, (void *)"ValidateListProp", 2, v49);
      if ( a3->ulKind )
      {
        v57 = GetNameFromWiaPropId(a3->propid);
        v59 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %d", v57, v58);
        WriteDbgTraceWarningWI("ValidateListProp", v59);
        WiaTrcLib::Free((WiaTrcLib *)v59, v60);
        v61 = GetNameFromWiaPropId(a3->propid);
        v54 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %d", v61, a1->ulVal);
      }
      else
      {
        v52 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->lVal);
        WriteDbgTraceWarningWI("ValidateListProp", v52);
        WiaTrcLib::Free((WiaTrcLib *)v52, v53);
        v54 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %S, value = %d", a3->lpwstr, a1->ulVal);
      }
      WiaTrace_ProcessTrace_Ex(v56, v55, (void *)"ValidateListProp", 2, v54);
      v62 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
      WriteDbgTraceWarningWI("ValidateListProp", v62);
      WiaTrcLib::Free((WiaTrcLib *)v62, v63);
      v64 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
      WiaTrace_ProcessTrace_Ex(v66, v65, (void *)"ValidateListProp", 2, v64);
      if ( a2->lVal != 2 )
      {
        do
        {
          v67 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v45 + 8]);
          WriteDbgTraceWarningWI("ValidateListProp", v67);
          WiaTrcLib::Free((WiaTrcLib *)v67, v68);
          v69 = (void **)WiaTrace_TraceWithSubComp(0, "    %d", *(_DWORD *)&a2->bstrblobVal.pData[4 * v45 + 8]);
          WiaTrace_ProcessTrace_Ex(v71, v70, (void *)"ValidateListProp", 2, v69);
          ++v45;
        }
        while ( v45 < a2->lVal - 2 );
      }
      goto LABEL_99;
  }
  if ( (a1->vt & 0xEFFF) != 0x48 )
  {
LABEL_93:
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v247);
    return 0;
  }
  v9 = 0;
  for ( kk = 0; kk < a2->lVal - 2; ++kk )
  {
    pbstrVal = a1->pbstrVal;
    v12 = &a2->bstrblobVal.pData[16 * kk + 32];
    v13 = (char *)*pbstrVal - *(_QWORD *)v12;
    if ( *pbstrVal == *(BSTR *)v12 )
      v13 = (char *)pbstrVal[1] - *((_QWORD *)v12 + 1);
    if ( !v13 )
      goto LABEL_100;
  }
  puuid = a1->puuid;
  StringUuid = 0;
  if ( !UuidToStringA(puuid, &StringUuid) )
  {
    v20 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
    WriteDbgTraceWarningWI("ValidateListProp", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v22 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, invalid LIST value for : ");
    WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"ValidateListProp", 2, v22);
    if ( a3->ulKind )
    {
      v30 = GetNameFromWiaPropId(a3->propid);
      v31 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (propID) %S, value = %s", v30, (const char *)StringUuid);
      WriteDbgTraceWarningWI("ValidateListProp", v31);
      WiaTrcLib::Free((WiaTrcLib *)v31, v32);
      v33 = GetNameFromWiaPropId(a3->propid);
      v27 = (void **)WiaTrace_TraceWithSubComp(0, "    (propID) %S, value = %s", v33, StringUuid);
    }
    else
    {
      v25 = (char *)WiaTrace_TraceLogWithSubComp(0, "    (Name) %d, value = %s", a3->lpwstr, (const char *)StringUuid);
      WriteDbgTraceWarningWI("ValidateListProp", v25);
      WiaTrcLib::Free((WiaTrcLib *)v25, v26);
      v27 = (void **)WiaTrace_TraceWithSubComp(0, "    (Name) %d, value = %s", a3->lpwstr, StringUuid);
    }
    WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"ValidateListProp", 2, v27);
    RpcStringFreeA(&StringUuid);
    v34 = (char *)WiaTrace_TraceLogWithSubComp(0, "Valid values are:");
    WriteDbgTraceWarningWI("ValidateListProp", v34);
    WiaTrcLib::Free((WiaTrcLib *)v34, v35);
    v36 = (void **)WiaTrace_TraceWithSubComp(0, "Valid values are:");
    WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"ValidateListProp", 2, v36);
    v39 = 0;
    if ( a2->lVal != 2 )
    {
      do
      {
        if ( !UuidToStringA((const UUID *)&a2->bstrblobVal.pData[16 * v39 + 32], &StringUuid) )
        {
          v40 = (char *)WiaTrace_TraceLogWithSubComp(0, "    %s", (const char *)StringUuid);
          WriteDbgTraceWarningWI("ValidateListProp", v40);
          WiaTrcLib::Free((WiaTrcLib *)v40, v41);
          v42 = (void **)WiaTrace_TraceWithSubComp(0, "    %s", (const char *)StringUuid);
          WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"ValidateListProp", 2, v42);
          RpcStringFreeA(&StringUuid);
        }
        ++v39;
      }
      while ( v39 < a2->lVal - 2 );
    }
LABEL_99:
    v9 = -2147024809;
    goto LABEL_100;
  }
  v15 = (char *)WiaTrace_TraceLogWithSubComp(0, "wiasValidateItemProperties, Out of memory");
  WriteDbgTraceWarningWI("ValidateListProp", v15);
  WiaTrcLib::Free((WiaTrcLib *)v15, v16);
  v17 = (void **)WiaTrace_TraceWithSubComp(0, "wiasValidateItemProperties, Out of memory");
  WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"ValidateListProp", 2, v17);
  v9 = -2147024882;
LABEL_100:
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v247);
  return v9;
}

```

## disassembly

```asm
0x18003de9c  push    rbp
0x18003de9e  push    rbx
0x18003de9f  push    rsi
0x18003dea0  push    rdi
0x18003dea1  push    r12
0x18003dea3  push    r13
0x18003dea5  push    r14
0x18003dea7  push    r15
0x18003dea9  lea     rbp, [rsp-1Fh]
0x18003deae  sub     rsp, 88h
0x18003deb5  mov     rdi, rcx
0x18003deb8  mov     r13, r8
0x18003debb  lea     rcx, aValidatelistpr_0; "::ValidateListProp"
0x18003dec2  mov     r15, rdx
0x18003dec5  call    WiaTrace_Trace
0x18003deca  lea     r12, aValidatelistpr; "ValidateListProp"
0x18003ded1  mov     [rsp+0C0h+var_98], rax; struct tagWiaTraceData_Type *
0x18003ded6  mov     r9, r12; char *
0x18003ded9  lea     rcx, [rbp+57h+var_90]; this
0x18003dedd  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18003dee2  movzx   eax, word ptr [rdi]
0x18003dee5  btr     eax, 0Ch
0x18003dee9  sub     eax, 3
0x18003deec  jz      loc_18003ECAF
0x18003def2  sub     eax, 1
0x18003def5  jz      loc_18003EAB8
0x18003defb  sub     eax, 1
0x18003defe  jz      loc_18003E8CF
0x18003df04  sub     eax, 3
0x18003df07  jz      loc_18003E6E6
0x18003df0d  sub     eax, 9
0x18003df10  jz      loc_18003E51C
0x18003df16  sub     eax, 1
0x18003df19  jz      loc_18003E350
0x18003df1f  sub     eax, 1
0x18003df22  jz      loc_18003E18D
0x18003df28  cmp     eax, 35h ; '5'
0x18003df2b  jnz     loc_18003ECD8
0x18003df31  mov     r8d, [r15+8]
0x18003df35  lea     esi, [rax-33h]
0x18003df38  xor     r14d, r14d
0x18003df3b  mov     edx, r14d
0x18003df3e  sub     r8d, esi
0x18003df41  cmp     edx, r8d
0x18003df44  jnb     short loc_18003DF72
0x18003df46  mov     r9, [rdi+8]
0x18003df4a  lea     ecx, [rdx+2]
0x18003df4d  shl     rcx, 4
0x18003df51  add     rcx, [r15+10h]
0x18003df55  mov     rax, [r9]
0x18003df58  sub     rax, [rcx]
0x18003df5b  jnz     short loc_18003DF65
0x18003df5d  mov     rax, [r9+8]
0x18003df61  sub     rax, [rcx+8]
0x18003df65  test    rax, rax
0x18003df68  jz      loc_18003EE7B
0x18003df6e  inc     edx
0x18003df70  jmp     short loc_18003DF41
0x18003df72  mov     rcx, [rdi+8]; Uuid
0x18003df76  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18003df7a  mov     [rbp+57h+StringUuid], r14
0x18003df7e  call    cs:__imp_UuidToStringA
0x18003df84  xor     ecx, ecx
0x18003df86  test    eax, eax
0x18003df88  jz      short loc_18003DFD5
0x18003df8a  lea     rdx, aWiasvalidateit_0; "wiasValidateItemProperties, Out of memo"...
0x18003df91  call    WiaTrace_TraceLogWithSubComp
0x18003df96  mov     rdx, rax; char *
0x18003df99  mov     rcx, r12; char *
0x18003df9c  mov     rbx, rax
0x18003df9f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003dfa4  mov     rcx, rbx; this
0x18003dfa7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003dfac  lea     rdx, aWiasvalidateit_0; "wiasValidateItemProperties, Out of memo"...
0x18003dfb3  xor     ecx, ecx
0x18003dfb5  call    WiaTrace_TraceWithSubComp
0x18003dfba  mov     r9d, esi; int
0x18003dfbd  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003dfc2  mov     r8, r12; int
0x18003dfc5  call    WiaTrace_ProcessTrace_Ex
0x18003dfca  mov     r14d, 8007000Eh
0x18003dfd0  jmp     loc_18003EE7B
0x18003dfd5  lea     rdx, aWiasvalidateit_6; "wiasValidateItemProperties, invalid LIS"...
0x18003dfdc  call    WiaTrace_TraceLogWithSubComp
0x18003dfe1  mov     rdx, rax; char *
0x18003dfe4  mov     rcx, r12; char *
0x18003dfe7  mov     rbx, rax
0x18003dfea  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003dfef  mov     rcx, rbx; this
0x18003dff2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003dff7  lea     rdx, aWiasvalidateit_6; "wiasValidateItemProperties, invalid LIS"...
0x18003dffe  xor     ecx, ecx
0x18003e000  call    WiaTrace_TraceWithSubComp
0x18003e005  mov     r9d, esi; int
0x18003e008  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e00d  mov     r8, r12; int
0x18003e010  call    WiaTrace_ProcessTrace_Ex
0x18003e015  cmp     [r13+0], r14d
0x18003e019  jnz     short loc_18003E054
0x18003e01b  mov     r9, [rbp+57h+StringUuid]
0x18003e01f  lea     rdx, aNameDValueS; "    (Name) %d, value = %s"
0x18003e026  mov     r8, [r13+8]
0x18003e02a  xor     ecx, ecx
0x18003e02c  call    WiaTrace_TraceLogWithSubComp
0x18003e031  mov     rdx, rax; char *
0x18003e034  mov     rcx, r12; char *
0x18003e037  mov     rbx, rax
0x18003e03a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e03f  mov     rcx, rbx; this
0x18003e042  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e047  mov     r8, [r13+8]
0x18003e04b  lea     rdx, aNameDValueS; "    (Name) %d, value = %s"
0x18003e052  jmp     short loc_18003E09B
0x18003e054  mov     ecx, [r13+8]; unsigned int
0x18003e058  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003e05d  mov     r9, [rbp+57h+StringUuid]
0x18003e061  lea     rdx, aPropidSValueS; "    (propID) %S, value = %s"
0x18003e068  mov     r8, rax
0x18003e06b  xor     ecx, ecx
0x18003e06d  call    WiaTrace_TraceLogWithSubComp
0x18003e072  mov     rdx, rax; char *
0x18003e075  mov     rcx, r12; char *
0x18003e078  mov     rbx, rax
0x18003e07b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e080  mov     rcx, rbx; this
0x18003e083  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e088  mov     ecx, [r13+8]; unsigned int
0x18003e08c  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003e091  mov     r8, rax
0x18003e094  lea     rdx, aPropidSValueS; "    (propID) %S, value = %s"
0x18003e09b  mov     r9, [rbp+57h+StringUuid]
0x18003e09f  xor     ecx, ecx
0x18003e0a1  call    WiaTrace_TraceWithSubComp
0x18003e0a6  mov     r9d, esi; int
0x18003e0a9  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e0ae  mov     r8, r12; int
0x18003e0b1  call    WiaTrace_ProcessTrace_Ex
0x18003e0b6  lea     rcx, [rbp+57h+StringUuid]; String
0x18003e0ba  call    cs:__imp_RpcStringFreeA
0x18003e0c0  lea     rdx, aValidValuesAre; "Valid values are:"
0x18003e0c7  xor     ecx, ecx
0x18003e0c9  call    WiaTrace_TraceLogWithSubComp
0x18003e0ce  mov     rdx, rax; char *
0x18003e0d1  mov     rcx, r12; char *
0x18003e0d4  mov     rbx, rax
0x18003e0d7  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e0dc  mov     rcx, rbx; this
0x18003e0df  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e0e4  lea     rdx, aValidValuesAre; "Valid values are:"
0x18003e0eb  xor     ecx, ecx
0x18003e0ed  call    WiaTrace_TraceWithSubComp
0x18003e0f2  mov     r9d, esi; int
0x18003e0f5  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e0fa  mov     r8, r12; int
0x18003e0fd  call    WiaTrace_ProcessTrace_Ex
0x18003e102  mov     edi, r14d
0x18003e105  cmp     [r15+8], esi
0x18003e109  jz      loc_18003EE75
0x18003e10f  lea     ecx, [rdi+2]
0x18003e112  shl     rcx, 4
0x18003e116  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18003e11a  add     rcx, [r15+10h]; Uuid
0x18003e11e  call    cs:__imp_UuidToStringA
0x18003e124  test    eax, eax
0x18003e126  jnz     short loc_18003E17C
0x18003e128  mov     r8, [rbp+57h+StringUuid]
0x18003e12c  lea     rdx, aS_0; "    %s"
0x18003e133  xor     ecx, ecx
0x18003e135  call    WiaTrace_TraceLogWithSubComp
0x18003e13a  mov     rdx, rax; char *
0x18003e13d  mov     rcx, r12; char *
0x18003e140  mov     rbx, rax
0x18003e143  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e148  mov     rcx, rbx; this
0x18003e14b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e150  mov     r8, [rbp+57h+StringUuid]
0x18003e154  lea     rdx, aS_0; "    %s"
0x18003e15b  xor     ecx, ecx
0x18003e15d  call    WiaTrace_TraceWithSubComp
0x18003e162  mov     r9d, esi; int
0x18003e165  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e16a  mov     r8, r12; int
0x18003e16d  call    WiaTrace_ProcessTrace_Ex
0x18003e172  lea     rcx, [rbp+57h+StringUuid]; String
0x18003e176  call    cs:__imp_RpcStringFreeA
0x18003e17c  mov     eax, [r15+8]
0x18003e180  inc     edi
0x18003e182  sub     eax, esi
0x18003e184  cmp     edi, eax
0x18003e186  jb      short loc_18003E10F
0x18003e188  jmp     loc_18003EE75
0x18003e18d  mov     r8d, [r15+8]
0x18003e191  xor     r14d, r14d
0x18003e194  mov     edx, r14d
0x18003e197  lea     esi, [r14+2]
0x18003e19b  sub     r8d, esi
0x18003e19e  cmp     edx, r8d
0x18003e1a1  jnb     short loc_18003E1BA
0x18003e1a3  mov     rax, [r15+10h]
0x18003e1a7  lea     ecx, [rdx+2]
0x18003e1aa  mov     ecx, [rax+rcx*4]
0x18003e1ad  cmp     [rdi+8], ecx
0x18003e1b0  jz      loc_18003ECD8
0x18003e1b6  inc     edx
0x18003e1b8  jmp     short loc_18003E19E
0x18003e1ba  lea     rdx, aWiasvalidateit_6; "wiasValidateItemProperties, invalid LIS"...
0x18003e1c1  xor     ecx, ecx
0x18003e1c3  call    WiaTrace_TraceLogWithSubComp
0x18003e1c8  mov     rdx, rax; char *
0x18003e1cb  mov     rcx, r12; char *
0x18003e1ce  mov     rbx, rax
0x18003e1d1  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e1d6  mov     rcx, rbx; this
0x18003e1d9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e1de  lea     rdx, aWiasvalidateit_6; "wiasValidateItemProperties, invalid LIS"...
0x18003e1e5  xor     ecx, ecx
0x18003e1e7  call    WiaTrace_TraceWithSubComp
0x18003e1ec  mov     r9d, esi; int
0x18003e1ef  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e1f4  mov     r8, r12; int
0x18003e1f7  call    WiaTrace_ProcessTrace_Ex
0x18003e1fc  mov     r9d, [rdi+8]
0x18003e200  cmp     [r13+0], r14d
0x18003e204  jnz     short loc_18003E23B
0x18003e206  mov     r8, [r13+8]
0x18003e20a  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003e211  xor     ecx, ecx
0x18003e213  call    WiaTrace_TraceLogWithSubComp
0x18003e218  mov     rdx, rax; char *
0x18003e21b  mov     rcx, r12; char *
0x18003e21e  mov     rbx, rax
0x18003e221  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e226  mov     rcx, rbx; this
0x18003e229  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e22e  mov     r8, [r13+8]
0x18003e232  lea     rdx, aNameSValueD; "    (Name) %S, value = %d"
0x18003e239  jmp     short loc_18003E27E
0x18003e23b  mov     ecx, [r13+8]; unsigned int
0x18003e23f  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003e244  mov     r8, rax
0x18003e247  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003e24e  xor     ecx, ecx
0x18003e250  call    WiaTrace_TraceLogWithSubComp
0x18003e255  mov     rdx, rax; char *
0x18003e258  mov     rcx, r12; char *
0x18003e25b  mov     rbx, rax
0x18003e25e  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e263  mov     rcx, rbx; this
0x18003e266  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e26b  mov     ecx, [r13+8]; unsigned int
0x18003e26f  call    ?GetNameFromWiaPropId@@YAPEAGK@Z; GetNameFromWiaPropId(ulong)
0x18003e274  mov     r8, rax
0x18003e277  lea     rdx, aPropidSValueD; "    (propID) %S, value = %d"
0x18003e27e  mov     r9d, [rdi+8]
0x18003e282  xor     ecx, ecx
0x18003e284  call    WiaTrace_TraceWithSubComp
0x18003e289  mov     r9d, esi; int
0x18003e28c  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e291  mov     r8, r12; int
0x18003e294  call    WiaTrace_ProcessTrace_Ex
0x18003e299  lea     rdx, aValidValuesAre; "Valid values are:"
0x18003e2a0  xor     ecx, ecx
0x18003e2a2  call    WiaTrace_TraceLogWithSubComp
0x18003e2a7  mov     rdx, rax; char *
0x18003e2aa  mov     rcx, r12; char *
0x18003e2ad  mov     rbx, rax
0x18003e2b0  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e2b5  mov     rcx, rbx; this
0x18003e2b8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e2bd  lea     rdx, aValidValuesAre; "Valid values are:"
0x18003e2c4  xor     ecx, ecx
0x18003e2c6  call    WiaTrace_TraceWithSubComp
0x18003e2cb  mov     r9d, esi; int
0x18003e2ce  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e2d3  mov     r8, r12; int
0x18003e2d6  call    WiaTrace_ProcessTrace_Ex
0x18003e2db  cmp     [r15+8], esi
0x18003e2df  jz      loc_18003EE75
0x18003e2e5  mov     r8, [r15+10h]
0x18003e2e9  lea     eax, [r14+2]
0x18003e2ed  lea     rdx, aD_1; "    %d"
0x18003e2f4  mov     edi, eax
0x18003e2f6  xor     ecx, ecx
0x18003e2f8  mov     r8d, [r8+rax*4]
0x18003e2fc  call    WiaTrace_TraceLogWithSubComp
0x18003e301  mov     rdx, rax; char *
0x18003e304  mov     rcx, r12; char *
0x18003e307  mov     rbx, rax
0x18003e30a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18003e30f  mov     rcx, rbx; this
0x18003e312  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003e317  mov     r8, [r15+10h]
0x18003e31b  lea     rdx, aD_1; "    %d"
0x18003e322  xor     ecx, ecx
0x18003e324  mov     r8d, [r8+rdi*4]
0x18003e328  call    WiaTrace_TraceWithSubComp
0x18003e32d  mov     r9d, esi; int
0x18003e330  mov     [rsp+0C0h+lpMem], rax; lpMem
0x18003e335  mov     r8, r12; int
0x18003e338  call    WiaTrace_ProcessTrace_Ex
  ... truncated ...
```
