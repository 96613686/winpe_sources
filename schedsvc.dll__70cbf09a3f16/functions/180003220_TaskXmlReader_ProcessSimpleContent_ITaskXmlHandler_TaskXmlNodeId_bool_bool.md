# TaskXmlReader::ProcessSimpleContent(ITaskXmlHandler *,TaskXmlNodeId,bool,bool &)

- ea: `0x180003220`
- end: `0x1800054a0`
- name: `?ProcessSimpleContent@TaskXmlReader@@AEAAJPEAUITaskXmlHandler@@W4TaskXmlNodeId@@_NAEA_N@Z`
- size: `8832`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, char, _BYTE *)`
- caller_count: `2`
- callee_count: `38`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800066a0`
- `0x180006af0`

## callees

- `0x18000238c`
- `0x1800023c0`
- `0x180002460`
- `0x180002ae0`
- `0x180002d70`
- `0x180003220`
- `0x1800054b0`
- `0x180006670`
- `0x180012180`
- `0x180015740`
- `0x1800157c4`
- `0x180016160`
- `0x18001a260`
- `0x1800347e0`
- `0x18003a500`
- `0x18003af20`
- `0x18003ba70`
- `0x18004130c`
- `0x180044d04`
- `0x18004544c`
- `0x18004c304`
- `0x18004c384`
- `0x18004e7fc`
- `0x18004e960`
- `0x18004ea00`
- `0x18004ea58`
- `0x180052118`
- `0x1800528f0`
- `0x18005790c`
- `0x18007aaa8`
- `0x18007ab08`
- `0x18007afa4`
- `0x18007b05c`
- `0x18007b0d4`
- `0x18007b158`
- `0x18007b234`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180004c26`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180004c26`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003271`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003271`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003749`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040ce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000351e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000351e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004c0a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000448e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800048a0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000448e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800048a0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004182`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004182`

## string_xrefs

- `0x180004d18`: `InteractiveToken`
- `0x180004d73`: `LeastPrivilege`
- `0x180004d39`: `InteractiveTokenOrPassword`

## pseudocode

```c
__int64 __fastcall TaskXmlReader::ProcessSimpleContent(__int64 a1, __int64 a2, unsigned int a3, char a4, _BYTE *a5)
{
  __int64 v6; // rsi
  int v8; // r8d
  const struct SchemaEntry **v9; // rdx
  int v10; // ecx
  int v11; // ebx
  __int64 *v12; // rdx
  int v13; // edi
  unsigned int *v14; // rsi
  int v15; // ebx
  unsigned __int64 v16; // rdx
  unsigned int v17; // r15d
  unsigned int *v18; // rdi
  unsigned int v19; // eax
  __int64 *v20; // r8
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rsi
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 (*v28)(void); // rax
  struct IErrorInfo *v29; // rdx
  unsigned int v30; // esi
  __int16 *v31; // rbx
  unsigned int v32; // esi
  unsigned __int64 v33; // rdi
  SIZE_T v34; // rax
  _WORD *v35; // rax
  void *v36; // r8
  __int64 v37; // rcx
  _WORD *v38; // rdx
  int v39; // esi
  __int16 v40; // ax
  unsigned __int64 v41; // rdx
  unsigned int *v42; // rdi
  unsigned int v43; // eax
  void *v44; // rsi
  __int64 *v45; // r8
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // eax
  __int64 v51; // rcx
  int Value; // eax
  unsigned int v53; // eax
  __int64 v54; // rsi
  _BYTE *v55; // rdi
  int v57; // ebx
  unsigned __int64 v58; // rdx
  char v59; // cl
  unsigned int *v60; // rdi
  unsigned int v61; // eax
  __int64 *v62; // r8
  int v63; // eax
  __int64 v64; // rcx
  int v65; // eax
  __int64 v66; // rcx
  unsigned int v67; // eax
  __int64 v68; // rcx
  int v69; // eax
  int v70; // r8d
  __int64 *v71; // r8
  int *v72; // rdi
  int v73; // eax
  int v74; // r8d
  __int64 *v75; // r8
  int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // rsi
  int v79; // eax
  bool v80; // sf
  int RawValue; // ebx
  struct IErrorInfo *v82; // rdx
  const unsigned __int64 *v83; // r9
  int v84; // edx
  unsigned __int64 v85; // r8
  const unsigned __int64 near *v86; // r9
  __int64 v87; // r10
  __int64 *v88; // r8
  int v89; // eax
  __int64 v90; // rcx
  int v91; // eax
  __int64 v92; // rcx
  unsigned int v93; // eax
  __int64 v94; // rcx
  int v95; // eax
  int v96; // ebx
  unsigned int v97; // edx
  int v98; // eax
  int v99; // ebx
  unsigned int v100; // eax
  int v101; // eax
  const unsigned __int16 *v102; // r8
  unsigned int v103; // r9d
  int *v104; // rdi
  int v105; // eax
  int v106; // edx
  int lpVtbl; // eax
  __int64 v108; // rcx
  __int64 v109; // rsi
  int v110; // eax
  __int64 v111; // rax
  unsigned int *v112; // rsi
  unsigned int v113; // eax
  unsigned __int64 v114; // rdx
  __int64 *v115; // r8
  int v116; // eax
  __int64 v117; // rcx
  __int64 v118; // rdi
  int v119; // eax
  __int64 v120; // rax
  unsigned int v121; // eax
  __int64 v122; // rcx
  int v123; // eax
  __int64 v124; // rcx
  unsigned int *v125; // rdi
  int v126; // ebx
  __int64 v127; // r8
  unsigned int v128; // r9d
  int v129; // eax
  int v130; // ebx
  __int64 v131; // r8
  int v132; // ebx
  HRESULT v133; // eax
  const unsigned __int16 *v134; // r8
  unsigned int v135; // r9d
  int v136; // ebx
  unsigned __int16 Data1; // r8
  unsigned int v138; // r9d
  __int64 v139; // rdi
  unsigned __int64 v140; // r9
  __int64 v141; // rax
  WCHAR *v142; // r10
  __int16 v143; // r11
  unsigned __int16 v144; // dx
  __int64 v145; // rax
  unsigned __int64 v146; // r9
  const unsigned __int64 near *v147; // r10
  __int64 v148; // r11
  const unsigned __int16 **v149; // r11
  const unsigned __int16 *v150; // r8
  unsigned int v151; // r9d
  __int64 v152; // rax
  unsigned __int64 v153; // r9
  __int64 v154; // rax
  __int64 v155; // r10
  const OLECHAR *NullTerminated; // rax
  __int16 v157; // r10
  unsigned __int16 v158; // dx
  unsigned __int64 v159; // r9
  const unsigned __int64 near *v160; // r10
  const struct SchemaEntry * near **v161; // r11
  unsigned __int64 v162; // r9
  __int64 v163; // rax
  __int64 v164; // r10
  unsigned __int64 v165; // r9
  const unsigned __int64 near *v166; // r10
  __int64 v167; // r11
  unsigned __int64 v168; // r9
  __int64 v169; // rax
  __int64 v170; // r10
  unsigned __int64 v171; // r9
  __int64 v172; // rax
  __int64 v173; // r10
  unsigned int v174; // r9d
  const unsigned __int16 *v175; // r8
  __int64 Entry; // rax
  const unsigned __int16 *v177; // r8
  unsigned int v178; // r9d
  __int64 v179; // rax
  int v180; // ecx
  int v181; // ecx
  int v182; // eax
  int v183; // eax
  bool v184; // sf
  int v185; // eax
  __int64 v186; // rax
  int v187; // eax
  unsigned __int16 *v188; // rax
  int v189; // eax
  int ProcessTokenSidType; // eax
  int Privilege; // eax
  int Week; // eax
  __int64 v193; // rcx
  unsigned int Data1_low; // eax
  __int64 v195; // rdx
  int v196; // eax
  int DayOfMonth; // eax
  int v198; // eax
  unsigned int v199; // eax
  int v200; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  int v203; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v204; // [rsp+44h] [rbp-BCh]
  _BYTE v205[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v207; // [rsp+60h] [rbp-A0h]
  int v208; // [rsp+68h] [rbp-98h]
  __int16 v209; // [rsp+6Ch] [rbp-94h]
  IID rclsid; // [rsp+70h] [rbp-90h] BYREF
  __int64 v211; // [rsp+80h] [rbp-80h]
  LPVOID v212; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v213[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v214[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v215; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned __int16 v216; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v217; // [rsp+B0h] [rbp-50h] BYREF
  int v218; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v219; // [rsp+BCh] [rbp-44h]
  __int64 v220; // [rsp+C0h] [rbp-40h]
  _BYTE *v221; // [rsp+C8h] [rbp-38h]
  OLECHAR sz[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v223; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v224; // [rsp+E0h] [rbp-20h]
  __int64 v225; // [rsp+E8h] [rbp-18h]
  __int64 v226; // [rsp+F0h] [rbp-10h]
  int v227; // [rsp+F8h] [rbp-8h]
  __int64 v228; // [rsp+FCh] [rbp-4h]

  v6 = (int)a3;
  v220 = a2;
  v221 = a5;
  v205[0] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v207 = 0;
  v208 = 0;
  v209 = 0;
  v212 = 0;
  *(_BYTE *)(a1 + 1112) = 1;
  v8 = *(_DWORD *)(a1 + 1116);
  if ( v8 == 65542 )
  {
LABEL_2:
    v9 = &(&Schema::schemaEntries)[(unsigned __int16)v8][16 * v6];
  }
  else
  {
    switch ( v8 )
    {
      case 65536:
      case 65537:
        v83 = 0;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_2;
      default:
        goto LABEL_329;
    }
    while ( v83 < (&Schema::schemaEntriesCount)[(unsigned __int16)v8] )
    {
      v9 = &(&Schema::schemaEntries)[(unsigned __int16)v8][16 * (_QWORD)v83];
      if ( *(_DWORD *)v9 == (_DWORD)v6 )
        goto LABEL_3;
      v83 = (const unsigned __int64 *)((char *)v83 + 1);
    }
LABEL_329:
    v9 = (const struct SchemaEntry **)&qword_18009D560;
  }
LABEL_3:
  v10 = *((_DWORD *)v9 + 7);
  if ( v10 != 26 )
  {
    if ( v10 )
    {
      v180 = v10 - 1;
      if ( v180 )
      {
        v181 = v180 - 8;
        if ( v181 )
        {
          if ( v181 != 2 && a4 )
          {
            if ( (_DWORD)v6 )
            {
              Entry = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
              v174 = *(_DWORD *)(Entry + 16);
              v175 = *(const unsigned __int16 **)(Entry + 8);
            }
            else
            {
              v174 = 0;
              v175 = 0;
            }
            v11 = TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, -2147216616, v175, v174, 0, 0);
            goto LABEL_383;
          }
        }
      }
    }
  }
  v11 = 0;
  if ( v8 == 65542 )
  {
LABEL_5:
    v12 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v8][16 * v6];
  }
  else
  {
    v84 = *(_DWORD *)(a1 + 1116);
    switch ( v8 )
    {
      case 65536:
      case 65537:
        v85 = 0;
        v86 = (&Schema::schemaEntriesCount)[(unsigned __int16)v84];
        v87 = 8LL * (unsigned __int16)v84 + 558752;
        break;
      case 65538:
      case 65539:
      case 65540:
      case 65541:
        goto LABEL_5;
      default:
        goto LABEL_335;
    }
    while ( v85 < (unsigned __int64)v86 )
    {
      v12 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v87) + (v85 << 7));
      if ( *(_DWORD *)v12 == (_DWORD)v6 )
        goto LABEL_6;
      ++v85;
    }
LABEL_335:
    v12 = &qword_18009D560;
  }
LABEL_6:
  v13 = *((_DWORD *)v12 + 7);
  if ( v13 != 7 )
  {
    if ( v13 != 8 )
    {
      if ( v13 == 20 )
      {
        LODWORD(lpMem) = 65542;
        Value = TaskXmlReader::LoadValue((BSTR *)a1, (enum Schema::Version *)&lpMem);
        v11 = Value;
        if ( Value < 0 )
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Value, (unsigned int)v6, a1 + 64);
        v53 = (unsigned int)lpMem;
        *(_DWORD *)(a1 + 1116) = (_DWORD)lpMem;
        rclsid.Data1 = v53;
        v211 = a1 + 64;
        goto LABEL_75;
      }
      switch ( v13 )
      {
        case 0:
          *(_BYTE *)(a1 + 1112) = 0;
          v17 = a3;
          goto LABEL_77;
        case 1:
        case 2:
        case 6:
          goto LABEL_31;
        case 3:
          RawValue = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( RawValue < 0 )
            goto LABEL_187;
          lpMem = 0;
          v203 = 0;
          v204 = 0;
          if ( (int)TSParser::ParseTimePeriod(
                      *(const unsigned __int16 **)(a1 + 72),
                      *(unsigned int *)(a1 + 64),
                      (struct TSTimePeriod *)&lpMem) < 0
            || WORD1(lpMem) + 12 * (unsigned __int16)lpMem )
          {
            goto LABEL_186;
          }
          v82 = (struct IErrorInfo *)(v204
                                    + 60
                                    * (HIWORD(v203)
                                     + 60
                                     * ((unsigned __int16)v203 + 24 * (HIWORD(lpMem) + 7 * (unsigned int)WORD2(lpMem)))));
          if ( (unsigned __int64)(int)v82 > 0xFFFFFFFF )
          {
            rclsid.Data1 = -1;
LABEL_186:
            RawValue = -2147216616;
LABEL_187:
            if ( (_DWORD)v6 )
            {
              v111 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
              v102 = *(const unsigned __int16 **)(v111 + 8);
              v103 = *(_DWORD *)(v111 + 16);
            }
            else
            {
              v102 = 0;
              v103 = 0;
            }
            v11 = TaskXmlReader::SetErrorInfo(
                    (TaskXmlReader *)a1,
                    RawValue,
                    v102,
                    v103,
                    *(const unsigned __int16 **)(a1 + 72),
                    *(_DWORD *)(a1 + 64));
          }
          else
          {
            rclsid.Data1 = v204
                         + 60 * (HIWORD(v203) + 60 * ((unsigned __int16)v203 + 24 * (HIWORD(lpMem) + 7 * WORD2(lpMem))));
            v11 = 0;
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v104 = *(int **)(a1 + 16);
          v105 = v104[38];
          if ( v105 )
          {
            v104[38] = v105 + 1;
            goto LABEL_156;
          }
          v106 = *v104;
          if ( *v104 == 65542 )
          {
LABEL_179:
            v82 = (struct IErrorInfo *)&(&Schema::schemaEntries)[(unsigned __int16)v106][16 * v6];
          }
          else
          {
            switch ( v106 )
            {
              case 65536:
              case 65537:
                v159 = 0;
                v160 = (&Schema::schemaEntriesCount)[(unsigned __int16)v106];
                v161 = &(&Schema::schemaEntries)[(unsigned __int16)v106];
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_179;
              default:
                goto LABEL_353;
            }
            while ( v159 < (unsigned __int64)v160 )
            {
              v82 = (struct IErrorInfo *)&(*v161)[16 * v159];
              lpVtbl = (int)v82->lpVtbl;
              if ( LODWORD(v82->lpVtbl) == (_DWORD)v6 )
              {
LABEL_181:
                if ( lpVtbl )
                {
                  v108 = *((_QWORD *)v104 + 2);
                  if ( !v108 )
                    _com_raise_error(-2147467261, v82);
                  v109 = *(_QWORD *)(a1 + 72);
                  v110 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, struct IErrorInfoVtbl *, unsigned __int16 *const))(*(_QWORD *)v108 + 216LL))(
                           v108,
                           &ChannelPath,
                           v82[1].lpVtbl,
                           Schema::namespaceUri);
                  v11 = v110;
                  if ( v110 < 0 )
                    goto LABEL_79;
                  if ( !v110 && v109 )
                  {
                    v94 = *((_QWORD *)v104 + 2);
                    if ( !v94 )
                      _com_raise_error(-2147467261, v82);
                    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 224LL))(v94, v109);
                    if ( v11 < 0 )
                      goto LABEL_79;
                  }
                }
                else
                {
                  v104[38] = 1;
                }
LABEL_156:
                v95 = v104[38];
                if ( v95 )
                {
                  v104[38] = v95 - 1;
                  v11 = 1;
                  goto LABEL_159;
                }
                v68 = *((_QWORD *)v104 + 2);
                if ( !v68 )
                  _com_raise_error(-2147467261, v82);
                goto LABEL_158;
              }
              ++v159;
            }
LABEL_353:
            v82 = (struct IErrorInfo *)&qword_18009D560;
          }
          lpVtbl = (int)v82->lpVtbl;
          goto LABEL_181;
        case 4:
          v14 = (unsigned int *)(a1 + 64);
          v15 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v15 < 0 )
            goto LABEL_316;
          if ( (int)TSParser::ParseDateTime(*(const unsigned __int16 **)(a1 + 72), *v14, (struct TSTime *)v205) < 0 )
          {
            v15 = -2147216616;
LABEL_316:
            v17 = a3;
            if ( a3 )
            {
              v179 = Schema::GetEntry(a1 + 1116, a3);
              v177 = *(const unsigned __int16 **)(v179 + 8);
              v178 = *(_DWORD *)(v179 + 16);
            }
            else
            {
              v177 = 0;
              v178 = 0;
            }
            v11 = TaskXmlReader::SetErrorInfo(
                    (TaskXmlReader *)a1,
                    v15,
                    v177,
                    v178,
                    *(const unsigned __int16 **)(a1 + 72),
                    *v14);
          }
          else
          {
            v11 = 0;
            v17 = a3;
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_76;
          v18 = *(unsigned int **)(a1 + 16);
          v19 = v18[38];
          if ( v19 )
          {
            v18[38] = v19 + 1;
            goto LABEL_25;
          }
          v16 = *v18;
          if ( (_DWORD)v16 == 65542 )
          {
LABEL_16:
            v20 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v16][16 * (__int64)(int)v17];
          }
          else
          {
            switch ( (int)v16 )
            {
              case 65536:
              case 65537:
                v153 = 0;
                v154 = (unsigned __int16)v16;
                v16 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v16];
                v155 = 8 * v154 + 558752;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_16;
              default:
                goto LABEL_363;
            }
            while ( v153 < v16 )
            {
              v20 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v155) + (v153 << 7));
              v21 = *(_DWORD *)v20;
              if ( *(_DWORD *)v20 == v17 )
              {
LABEL_18:
                if ( v21 )
                {
                  v22 = *((_QWORD *)v18 + 2);
                  if ( !v22 )
                    _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
                  v23 = *(_QWORD *)(a1 + 72);
                  v24 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v22 + 216LL))(
                          v22,
                          &ChannelPath,
                          v20[1],
                          Schema::namespaceUri);
                  v11 = v24;
                  if ( v24 < 0 )
                    goto LABEL_79;
                  if ( !v24 && v23 )
                  {
                    v25 = *((_QWORD *)v18 + 2);
                    if ( !v25 )
                      _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
                    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 224LL))(v25, v23);
                    if ( v11 < 0 )
                      goto LABEL_79;
                  }
                }
                else
                {
                  v18[38] = 1;
                }
LABEL_25:
                v26 = v18[38];
                if ( v26 )
                {
                  v18[38] = v26 - 1;
                  v11 = 1;
                  goto LABEL_29;
                }
                v27 = *((_QWORD *)v18 + 2);
                if ( !v27 )
                  _com_raise_error(-2147467261, (struct IErrorInfo *)v16);
                v28 = *(__int64 (**)(void))(*(_QWORD *)v27 + 120LL);
LABEL_28:
                v11 = v28();
LABEL_29:
                if ( v11 >= 0 )
                {
                  *(_BYTE *)(a1 + 1112) = 0;
                  goto LABEL_77;
                }
                goto LABEL_79;
              }
              ++v153;
            }
LABEL_363:
            v20 = &qword_18009D560;
          }
          v21 = *(_DWORD *)v20;
          goto LABEL_18;
        case 5:
          LOWORD(rclsid.Data1) = 0;
          v136 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v136 < 0 )
            goto LABEL_301;
          Data1 = 0;
          LOWORD(rclsid.Data1) = 0;
          v138 = 0;
          while ( 2 )
          {
            if ( v138 < *(_DWORD *)(a1 + 64) )
            {
              v157 = *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL * (int)v138);
              if ( (unsigned __int16)(v157 - 48) <= 9u )
              {
                v158 = Data1;
                Data1 = v157 + 10 * Data1 - 48;
                LOWORD(rclsid.Data1) = Data1;
                if ( Data1 >= v158 )
                {
                  ++v138;
                  continue;
                }
              }
              v136 = -2147216616;
LABEL_301:
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v136, (unsigned int)v6, a1 + 64);
              Data1 = rclsid.Data1;
            }
            else
            {
              v11 = 0;
            }
            break;
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v139 = *(_QWORD *)(a1 + 16);
          v11 = StringCchPrintfW((unsigned __int16 *)(v139 + 24), 0x40u, L"%d", Data1);
          if ( v11 >= 0 )
          {
            v17 = a3;
            v11 = TaskXmlWriter::Element(v139, a3, v139 + 24);
            if ( v11 >= 0 )
              goto LABEL_223;
          }
          goto LABEL_374;
        case 9:
          if ( a4 )
            goto LABEL_381;
          LODWORD(lpMem) = 0;
          v186 = _com_ptr_t<_com_IIID<IXmlReader,&__s_GUID const _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030>>::operator->(a1 + 56);
          v187 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v186 + 48LL))(v186, &lpMem);
          v11 = v187;
          if ( v187 < 0 )
          {
            v11 = TaskXmlReader::SetErrorInfoXmlLite((TaskXmlReader *)a1, v187);
            operator delete(v212);
            return (unsigned int)v11;
          }
          if ( v187 || (_DWORD)lpMem != 15 )
            v11 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
LABEL_381:
          v211 = 0;
          if ( *(_BYTE *)(a1 + 40) )
          {
            v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, 0);
            if ( v11 < 0 )
              goto LABEL_383;
          }
          goto LABEL_75;
        case 10:
          v132 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v132 < 0
            || (NullTerminated = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
                v132 = CLSIDFromString(NullTerminated, &rclsid),
                v132 < 0)
            && (*XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)) == 123
             || (v188 = XmlParserTempString::GetNullTerminated((XmlParserTempString *)(a1 + 64)),
                 v132 = StringCchPrintfW(sz, 0x28u, L"{%s}", v188),
                 v132 < 0)
             || (v132 = CLSIDFromString(sz, &rclsid), v132 < 0)) )
          {
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v132, (unsigned int)v6, a1 + 64);
          }
          else
          {
            v11 = 0;
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          lpMem = 0;
          v133 = StringFromCLSID(&rclsid, (LPOLESTR *)&lpMem);
          v11 = v133;
          if ( v133 )
          {
            if ( v133 > 0 )
              v11 = (unsigned __int16)v133 | 0x80070000;
            goto LABEL_79;
          }
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, lpMem);
          if ( v11 < 0 )
            goto LABEL_383;
          CoTaskMemFree(lpMem);
          *(_BYTE *)(a1 + 1112) = 0;
          v17 = a3;
          goto LABEL_77;
        case 11:
          if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
            SysFreeString(*(BSTR *)(a1 + 72));
          *(_DWORD *)(a1 + 64) = 0;
          *(_QWORD *)(a1 + 72) = 0;
          *(_BYTE *)(a1 + 1106) &= 0xFCu;
          *(_WORD *)(a1 + 80) = 0;
          if ( a4 )
          {
            v17 = a3;
          }
          else
          {
            v189 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
            v11 = v189;
            v17 = a3;
            if ( v189 < 0 )
              v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v189, a3, a1 + 64);
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_76;
          v112 = *(unsigned int **)(a1 + 16);
          v113 = v112[38];
          if ( v113 )
          {
            v112[38] = v113 + 1;
            goto LABEL_203;
          }
          v114 = *v112;
          if ( (_DWORD)v114 == 65542 )
          {
LABEL_196:
            v115 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v114][16 * (__int64)(int)v17];
            v116 = *(_DWORD *)v115;
            goto LABEL_197;
          }
          switch ( (int)v114 )
          {
            case 65536:
            case 65537:
              v171 = 0;
              v172 = (unsigned __int16)v114;
              v114 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v114];
              v173 = 8 * v172 + 558752;
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_196;
            default:
              goto LABEL_393;
          }
          while ( 2 )
          {
            if ( v171 >= v114 )
            {
LABEL_393:
              v115 = &qword_18009D560;
              v116 = 0;
            }
            else
            {
              v115 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v173) + (v171 << 7));
              v116 = *(_DWORD *)v115;
              if ( *(_DWORD *)v115 != v17 )
              {
                ++v171;
                continue;
              }
            }
            break;
          }
LABEL_197:
          if ( v116 )
          {
            v117 = *((_QWORD *)v112 + 2);
            if ( !v117 )
              _com_raise_error(-2147467261, (struct IErrorInfo *)v114);
            v118 = *(_QWORD *)(a1 + 72);
            v119 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v117 + 216LL))(
                     v117,
                     &ChannelPath,
                     v115[1],
                     Schema::namespaceUri);
            v11 = v119;
            if ( v119 < 0 )
              goto LABEL_79;
            if ( !v119 )
            {
              if ( v118 )
              {
                v120 = _com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v112 + 4);
                v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v120 + 224LL))(v120, v118);
                if ( v11 < 0 )
                  goto LABEL_79;
              }
            }
          }
          else
          {
            v112[38] = 1;
          }
LABEL_203:
          v121 = v112[38];
          if ( !v121 )
          {
            v28 = *(__int64 (**)(void))(*(_QWORD *)_com_ptr_t<_com_IIID<IXmlWriter,&__s_GUID const _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030>>::operator->(v112 + 4)
                                      + 120LL);
            goto LABEL_28;
          }
          v112[38] = v121 - 1;
          v11 = 1;
          goto LABEL_29;
        case 12:
          v125 = (unsigned int *)(a1 + 64);
          v126 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v126 < 0 )
            goto LABEL_261;
          LOWORD(v127) = 0;
          LOWORD(rclsid.Data1) = 0;
          v128 = 0;
          while ( 2 )
          {
            if ( v128 < *v125 )
            {
              v143 = *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL * (int)v128);
              if ( (unsigned __int16)(v143 - 48) <= 9u )
              {
                v144 = v127;
                LOWORD(v127) = v143 + 10 * v127 - 48;
                LOWORD(rclsid.Data1) = v127;
                if ( (unsigned __int16)v127 >= v144 )
                {
                  ++v128;
                  continue;
                }
              }
              v126 = -2147216616;
LABEL_261:
              v149 = (const unsigned __int16 **)(a1 + 72);
              if ( (_DWORD)v6 )
              {
                v152 = Schema::GetEntry(a1 + 1116, (unsigned int)v6);
                v150 = *(const unsigned __int16 **)(v152 + 8);
                v151 = *(_DWORD *)(v152 + 16);
              }
              else
              {
                v150 = 0;
                v151 = 0;
              }
              v129 = TaskXmlReader::SetErrorInfo((TaskXmlReader *)a1, v126, v150, v151, *v149, *v125);
            }
            else
            {
              v11 = 0;
              if ( (unsigned __int16)v127 <= 0xAu )
                goto LABEL_265;
              v129 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
            }
            break;
          }
          LOWORD(v127) = rclsid.Data1;
          v11 = v129;
LABEL_265:
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v127 = (unsigned __int16)v127;
LABEL_267:
          v101 = TaskXmlWriter::ElementInt(*(_QWORD *)(a1 + 16), (unsigned int)v6, v127);
          goto LABEL_373;
        case 13:
          v130 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v130 < 0 )
            goto LABEL_218;
          if ( !*(_DWORD *)(a1 + 64) )
            goto LABEL_407;
          rclsid.Data1 = 0;
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"S4U", 3u) )
          {
            v131 = 0x4000;
LABEL_406:
            rclsid.Data1 = v131;
            v11 = 0;
            goto LABEL_219;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"Password", 8u) )
          {
            v131 = 0x40000;
            goto LABEL_406;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"InteractiveToken", 0x10u) )
          {
            v131 = 0x10000;
            goto LABEL_406;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"InteractiveTokenOrPassword", 0x1Au) )
          {
            v131 = 0x80000;
            goto LABEL_406;
          }
LABEL_407:
          v130 = -2147216616;
LABEL_218:
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v130, (unsigned int)v6, a1 + 64);
          v131 = rclsid.Data1;
LABEL_219:
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v101 = TaskXmlWriter::ElementLogonType(*(_QWORD *)(a1 + 16), (unsigned int)v6, v131);
          goto LABEL_373;
        case 14:
          rclsid.Data1 = 0;
          v99 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v99 < 0 )
            goto LABEL_170;
          if ( !*(_DWORD *)(a1 + 64) )
            goto LABEL_414;
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"LeastPrivilege", 0xEu) )
          {
            v100 = 0;
LABEL_413:
            rclsid.Data1 = v100;
            v11 = 0;
            goto LABEL_171;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"HighestAvailable", 0x10u) )
          {
            v100 = 0x1000000;
            goto LABEL_413;
          }
LABEL_414:
          v99 = -2147216616;
LABEL_170:
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v99, (unsigned int)v6, a1 + 64);
          v100 = rclsid.Data1;
LABEL_171:
          v211 = a1 + 64;
          if ( *(_BYTE *)(a1 + 40) && (v100 & 0x1000000) != 0 )
          {
            v101 = TaskXmlWriter::ElementRunLevel(*(_QWORD *)(a1 + 16), (unsigned int)v6, 1);
LABEL_373:
            v11 = v101;
            if ( v101 < 0 )
            {
LABEL_374:
              operator delete(v212);
              return (unsigned int)v11;
            }
          }
          goto LABEL_75;
        case 15:
          LOWORD(rclsid.Data1) = 0;
          Week = TaskXmlReader::LoadWeek((BSTR *)a1, (unsigned __int16 *)&rclsid);
          v11 = Week;
          if ( Week < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Week, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v193 = *(_QWORD *)(a1 + 16);
          Data1_low = LOWORD(rclsid.Data1);
          v195 = 70;
          if ( LOWORD(rclsid.Data1) != 5 )
            goto LABEL_348;
          v11 = TaskXmlWriter::Element(v193, 70, L"Last");
          if ( v11 >= 0 )
            goto LABEL_75;
          goto LABEL_349;
        case 16:
          rclsid.Data1 = 0;
          v96 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v96 < 0 )
            goto LABEL_304;
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"Parallel", 8u) )
          {
            v97 = 1024;
            goto LABEL_166;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"Queue", 5u) )
          {
            v97 = 4096;
            goto LABEL_166;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"IgnoreNew", 9u) )
          {
            v97 = 0x2000;
LABEL_166:
            rclsid.Data1 = v97;
            v11 = 0;
            goto LABEL_167;
          }
          if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"StopExisting", 0xCu) )
          {
            v97 = 2048;
            goto LABEL_166;
          }
          v96 = -2147216616;
LABEL_304:
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v96, (unsigned int)v6, a1 + 64);
LABEL_167:
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v98 = TaskXmlWriter::ElementMultipleInstancesPolicy(*(_QWORD *)(a1 + 16));
          goto LABEL_347;
        case 17:
          v196 = TaskXmlReader::SkipElement((TaskXmlReader *)a1);
          v11 = v196;
          if ( v196 < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v196, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          goto LABEL_75;
        case 18:
          LOWORD(rclsid.Data1) = 0;
          DayOfMonth = TaskXmlReader::LoadDayOfMonth((BSTR *)a1, (unsigned __int16 *)&rclsid);
          v11 = DayOfMonth;
          if ( DayOfMonth < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)DayOfMonth, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v193 = *(_QWORD *)(a1 + 16);
          Data1_low = LOWORD(rclsid.Data1);
          v195 = 68;
          if ( LOWORD(rclsid.Data1) == 32 )
          {
            v11 = TaskXmlWriter::Element(v193, 68, L"Last");
            if ( v11 >= 0 )
              goto LABEL_75;
          }
          else
          {
LABEL_348:
            v11 = TaskXmlWriter::ElementInt(v193, v195, Data1_low);
          }
LABEL_349:
          v184 = v11 < 0;
          goto LABEL_350;
        case 19:
          rclsid.Data1 = 0;
          v198 = TaskXmlReader::LoadSessionStateChange((TaskXmlReader *)a1, &rclsid.Data1);
          v11 = v198;
          if ( v198 < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v198, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v98 = TaskXmlWriter::ElementSessionStateChange(*(TaskXmlWriter **)(a1 + 16), LOWORD(rclsid.Data1));
          goto LABEL_347;
        case 21:
          ProcessTokenSidType = TaskXmlReader::LoadProcessTokenSidType(
                                  (TaskXmlReader *)a1,
                                  (enum JobFlags::JobFlag *)&rclsid);
          v11 = ProcessTokenSidType;
          if ( ProcessTokenSidType < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)ProcessTokenSidType, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          if ( (rclsid.Data1 & 0x8000000) != 0 )
          {
            v101 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), (unsigned int)v6, 0);
            goto LABEL_373;
          }
          if ( (rclsid.Data1 & 0x10000000) == 0 )
            goto LABEL_75;
          v101 = TaskXmlWriter::ElementProcessTokenSidType(*(_QWORD *)(a1 + 16), (unsigned int)v6, 1);
          goto LABEL_373;
        case 22:
          Privilege = TaskXmlReader::LoadPrivilege((TaskXmlReader *)a1, (unsigned __int64 *)&rclsid.Data1);
          v11 = Privilege;
          if ( Privilege < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)Privilege, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v101 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), 135, *(_QWORD *)(a1 + 72));
          goto LABEL_373;
        case 23:
          v11 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
          if ( v11 < 0 )
            goto LABEL_225;
          v217 = 0;
          v218 = 0;
          v219 = 0;
          if ( (int)TSParser::ParseTimePeriod(
                      *(const unsigned __int16 **)(a1 + 72),
                      *(unsigned int *)(a1 + 64),
                      (struct TSTimePeriod *)&v217) < 0 )
          {
            v11 = -2147216616;
LABEL_225:
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, (unsigned int)v6, a1 + 64);
            goto LABEL_226;
          }
          v214[0] = 0;
          v215 = 0;
          v216 = 0;
          LOWORD(lpMem) = 0;
          v11 = ULongToUShort((unsigned __int16)v217, v214);
          if ( v11 < 0 )
            goto LABEL_225;
          v11 = ULongToUShort(HIWORD(v217), &v215);
          if ( v11 < 0 )
            goto LABEL_225;
          v11 = ULongToUShort((unsigned __int16)v218, &v216);
          if ( v11 < 0 )
            goto LABEL_225;
          v11 = ULongToUShort(v219, (unsigned __int16 *)&lpMem);
          if ( v11 < 0 )
            goto LABEL_225;
          LOWORD(v207) = v214[0];
          *(_DWORD *)((char *)&v207 + 2) = *(_DWORD *)((char *)&v217 + 2);
          HIWORD(v207) = v215;
          LOWORD(v208) = v216;
          HIWORD(v208) = HIWORD(v218);
          v209 = (__int16)lpMem;
LABEL_226:
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v11 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), (unsigned int)v6, *(_QWORD *)(a1 + 72));
          v80 = v11 < 0;
          break;
        case 24:
        case 26:
          v182 = TaskXmlReader::LoadHexString((tsched **)a1, &v212, v213);
          v11 = v182;
          if ( v182 < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v182, (unsigned int)v6, a1 + 64);
          if ( v13 == 24 && *(_DWORD *)(a1 + 64) != 16 )
          {
            v183 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, (unsigned int)v6, a1 + 64);
LABEL_342:
            v11 = v183;
            goto LABEL_75;
          }
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v98 = TaskXmlWriter::ElementHexString(*(_QWORD *)(a1 + 16), (unsigned int)v6, v212, *(unsigned int *)v213);
          goto LABEL_347;
        case 25:
          rclsid.Data1 = 0;
          v185 = TaskXmlReader::LoadValue((BSTR *)a1, &rclsid.Data1);
          v11 = v185;
          if ( v185 < 0 )
            v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v185, (unsigned int)v6, a1 + 64);
          v211 = a1 + 64;
          if ( !*(_BYTE *)(a1 + 40) )
            goto LABEL_75;
          v127 = rclsid.Data1;
          goto LABEL_267;
        default:
          v183 = TaskXmlReader::SetErrorInfo(a1, 2147750678LL);
          goto LABEL_342;
      }
LABEL_121:
      if ( v80 )
        goto LABEL_79;
      goto LABEL_75;
    }
    v57 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
    if ( v57 >= 0 )
    {
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"false", 5u) )
        goto LABEL_128;
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"true", 4u) )
      {
        v59 = 1;
        goto LABEL_92;
      }
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"0", 1u) )
      {
LABEL_128:
        v59 = 0;
        goto LABEL_92;
      }
      if ( XmlParserTempString::IsEqualTo((XmlParserTempString *)(a1 + 64), L"1", 1u) )
      {
        v59 = 1;
LABEL_92:
        LOBYTE(rclsid.Data1) = v59;
        v11 = 0;
        goto LABEL_93;
      }
      v57 = -2147216616;
    }
    v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v57, (unsigned int)v6, a1 + 64);
    v59 = rclsid.Data1;
LABEL_93:
    v211 = a1 + 64;
    if ( *(_BYTE *)(a1 + 40) )
    {
      v60 = *(unsigned int **)(a1 + 16);
      v61 = v60[38];
      if ( v59 )
      {
        if ( v61 )
        {
          v60[38] = v61 + 1;
        }
        else
        {
          v58 = *v60;
          if ( (_DWORD)v58 == 65542 )
          {
LABEL_97:
            v62 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v58][16 * v6];
          }
          else
          {
            switch ( (int)v58 )
            {
              case 65536:
              case 65537:
                v162 = 0;
                v163 = (unsigned __int16)v58;
                v58 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v58];
                v164 = 8 * v163 + 558752;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_97;
              default:
                goto LABEL_451;
            }
            while ( v162 < v58 )
            {
              v62 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v164) + (v162 << 7));
              v63 = *(_DWORD *)v62;
              if ( *(_DWORD *)v62 == (_DWORD)v6 )
                goto LABEL_99;
              ++v162;
            }
LABEL_451:
            v62 = &qword_18009D560;
          }
          v63 = *(_DWORD *)v62;
LABEL_99:
          if ( v63 )
          {
            v64 = *((_QWORD *)v60 + 2);
            if ( !v64 )
              _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
            v65 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v64 + 216LL))(
                    v64,
                    &ChannelPath,
                    v62[1],
                    Schema::namespaceUri);
            v11 = v65;
            if ( v65 < 0 )
              goto LABEL_159;
            if ( !v65 )
            {
              v66 = *((_QWORD *)v60 + 2);
              if ( !v66 )
                _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
              v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v66 + 224LL))(
                      v66,
                      L"true");
              if ( v11 < 0 )
                goto LABEL_159;
            }
          }
          else
          {
            v60[38] = 1;
          }
        }
        v67 = v60[38];
        if ( !v67 )
        {
          v68 = *((_QWORD *)v60 + 2);
          if ( !v68 )
            _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
LABEL_158:
          v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 120LL))(v68);
          goto LABEL_159;
        }
        v60[38] = v67 - 1;
        v11 = 1;
      }
      else
      {
        if ( v61 )
        {
          v60[38] = v61 + 1;
        }
        else
        {
          v58 = *v60;
          if ( (_DWORD)v58 == 65542 )
          {
LABEL_141:
            v88 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v58][16 * v6];
          }
          else
          {
            switch ( (int)v58 )
            {
              case 65536:
              case 65537:
                v168 = 0;
                v169 = (unsigned __int16)v58;
                v58 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v58];
                v170 = 8 * v169 + 558752;
                break;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
                goto LABEL_141;
              default:
                goto LABEL_457;
            }
            while ( v168 < v58 )
            {
              v88 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v170) + (v168 << 7));
              v89 = *(_DWORD *)v88;
              if ( *(_DWORD *)v88 == (_DWORD)v6 )
                goto LABEL_143;
              ++v168;
            }
LABEL_457:
            v88 = &qword_18009D560;
          }
          v89 = *(_DWORD *)v88;
LABEL_143:
          if ( v89 )
          {
            v90 = *((_QWORD *)v60 + 2);
            if ( !v90 )
              _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
            v91 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v90 + 216LL))(
                    v90,
                    &ChannelPath,
                    v88[1],
                    Schema::namespaceUri);
            v11 = v91;
            if ( v91 < 0 )
              goto LABEL_159;
            if ( !v91 )
            {
              v92 = *((_QWORD *)v60 + 2);
              if ( !v92 )
                _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
              v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v92 + 224LL))(
                      v92,
                      L"false");
              if ( v11 < 0 )
                goto LABEL_159;
            }
          }
          else
          {
            v60[38] = 1;
          }
        }
        v93 = v60[38];
        if ( !v93 )
        {
          v68 = *((_QWORD *)v60 + 2);
          if ( !v68 )
            _com_raise_error(-2147467261, (struct IErrorInfo *)v58);
          goto LABEL_158;
        }
        v60[38] = v93 - 1;
        v11 = 1;
      }
LABEL_159:
      if ( v11 >= 0 )
      {
        *(_BYTE *)(a1 + 1112) = 0;
        v17 = a3;
        goto LABEL_77;
      }
      goto LABEL_79;
    }
LABEL_75:
    v17 = a3;
    goto LABEL_76;
  }
LABEL_31:
  if ( (*(_BYTE *)(a1 + 1106) & 1) != 0 )
    SysFreeString(*(BSTR *)(a1 + 72));
  *(_DWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_BYTE *)(a1 + 1106) &= 0xFCu;
  *(_WORD *)(a1 + 80) = 0;
  if ( !a4 )
  {
    v69 = TaskXmlReader::LoadRawValue((TaskXmlReader *)a1, (BSTR *)(a1 + 64));
    v11 = v69;
    if ( v69 < 0 )
    {
      v17 = a3;
      v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v69);
      goto LABEL_76;
    }
  }
  if ( (v13 == 2 || v13 == 7) && !*(_DWORD *)(a1 + 64) )
  {
    v17 = a3;
    v11 = TaskXmlReader::SetErrorInfo(a1, 2147750680LL, a3, a1 + 64);
    goto LABEL_76;
  }
  if ( v13 == 6 && !*(_DWORD *)(a1 + 64) )
  {
    if ( a3 )
    {
      v145 = Schema::GetEntry(a1 + 1116, a3);
      v134 = *(const unsigned __int16 **)(v145 + 8);
      v135 = *(_DWORD *)(v145 + 16);
    }
    else
    {
      v134 = 0;
      v135 = 0;
    }
    v11 = TaskXmlReader::SetErrorInfo(
            (TaskXmlReader *)a1,
            -2147216616,
            v134,
            v135,
            *(const unsigned __int16 **)(a1 + 72),
            0);
    v17 = a3;
LABEL_76:
    *(_BYTE *)(a1 + 1112) = 0;
    if ( v11 >= 0 )
      goto LABEL_77;
    goto LABEL_79;
  }
  v29 = (struct IErrorInfo *)(a1 + 64);
  v211 = a1 + 64;
  if ( !*(_BYTE *)(a1 + 40) )
    goto LABEL_75;
  v30 = a3;
  if ( a3 != 130 )
  {
    switch ( a3 )
    {
      case 6u:
      case 8u:
      case 0xAu:
      case 0xBu:
      case 0x70u:
      case 0x73u:
      case 0x79u:
      case 0x81u:
        goto LABEL_40;
      default:
        v70 = *(_DWORD *)(a1 + 1116);
        if ( v70 == 65542 )
        {
LABEL_112:
          v71 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v70][16 * (__int64)(int)a3];
          goto LABEL_113;
        }
        switch ( v70 )
        {
          case 65536:
          case 65537:
            v146 = 0;
            v147 = (&Schema::schemaEntriesCount)[(unsigned __int16)v70];
            v148 = 8LL * (unsigned __int16)v70 + 558752;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_112;
          default:
            goto LABEL_464;
        }
        break;
    }
    while ( v146 < (unsigned __int64)v147 )
    {
      v71 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v148) + (v146 << 7));
      if ( *(_DWORD *)v71 == a3 )
        goto LABEL_113;
      ++v146;
    }
LABEL_464:
    v71 = &qword_18009D560;
LABEL_113:
    if ( *((_DWORD *)v71 + 6) == 2 )
      goto LABEL_120;
    v72 = *(int **)(a1 + 16);
    v73 = v72[38];
    if ( v73 )
    {
      v72[38] = v73 + 1;
    }
    else
    {
      v74 = *v72;
      if ( *v72 == 65542 )
      {
LABEL_116:
        v75 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v74][16 * (__int64)(int)a3];
        v76 = *(_DWORD *)v75;
      }
      else
      {
        switch ( v74 )
        {
          case 65536:
          case 65537:
            v165 = 0;
            v166 = (&Schema::schemaEntriesCount)[(unsigned __int16)v74];
            v167 = 8LL * (unsigned __int16)v74 + 558752;
            break;
          case 65538:
          case 65539:
          case 65540:
          case 65541:
            goto LABEL_116;
          default:
            goto LABEL_466;
        }
        while ( v165 < (unsigned __int64)v166 )
        {
          v75 = (__int64 *)(*(_QWORD *)((char *)&_ImageBase + v167) + (v165 << 7));
          v76 = *(_DWORD *)v75;
          if ( *(_DWORD *)v75 == a3 )
            goto LABEL_117;
          ++v165;
        }
LABEL_466:
        v75 = &qword_18009D560;
        v76 = 0;
      }
LABEL_117:
      if ( v76 )
      {
        v77 = *((_QWORD *)v72 + 2);
        if ( !v77 )
          _com_raise_error(-2147467261, v29);
        v78 = *(_QWORD *)(a1 + 72);
        v79 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v77 + 216LL))(
                v77,
                &ChannelPath,
                v75[1],
                Schema::namespaceUri);
        v11 = v79;
        if ( v79 < 0 )
          goto LABEL_120;
        if ( !v79 && v78 )
        {
          v122 = *((_QWORD *)v72 + 2);
          if ( !v122 )
            _com_raise_error(-2147467261, v29);
          v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v122 + 224LL))(v122, v78);
          if ( v11 < 0 )
            goto LABEL_120;
        }
      }
      else
      {
        v72[38] = 1;
      }
    }
    v123 = v72[38];
    if ( v123 )
    {
      v72[38] = v123 - 1;
      v11 = 1;
    }
    else
    {
      v124 = *((_QWORD *)v72 + 2);
      if ( !v124 )
        _com_raise_error(-2147467261, v29);
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v124 + 120LL))(v124);
    }
LABEL_120:
    v80 = v11 < 0;
    goto LABEL_121;
  }
LABEL_40:
  v31 = *(__int16 **)(a1 + 72);
  if ( !v31 )
    goto LABEL_346;
  v32 = (unsigned int)v29->lpVtbl;
  if ( !LODWORD(v29->lpVtbl) )
  {
    v30 = a3;
LABEL_346:
    v98 = TaskXmlWriter::Element(*(_QWORD *)(a1 + 16), v30, &ChannelPath);
LABEL_347:
    v11 = v98;
    v184 = v98 < 0;
LABEL_350:
    if ( v184 )
      goto LABEL_383;
    goto LABEL_75;
  }
  v33 = v32 + 1;
  v34 = 2 * v33;
  if ( !is_mul_ok(v33, 2u) )
    v34 = -1;
  v35 = HeapAlloc(g_PrivateHeap, 0, v34);
  v36 = v35;
  if ( !v35 )
  {
    v223 = 0;
    v224 = &qword_1800A4718;
    v225 = 0;
    v226 = 0;
    v227 = 14;
    v228 = -1;
    *(_QWORD *)sz = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)sz;
  }
  lpMem = v35;
  if ( v32 == -1 )
  {
    v39 = -2147024809;
  }
  else if ( v33 > 0x7FFFFFFF )
  {
    v39 = -2147024809;
    *v35 = 0;
  }
  else if ( v32 > 0x7FFFFFFE )
  {
    v39 = -2147024809;
    *v35 = 0;
  }
  else
  {
    v37 = v32;
    v38 = v35;
    v39 = 0;
    while ( v37 )
    {
      v40 = *v31;
      if ( !*v31 )
      {
        if ( !v33 )
        {
LABEL_52:
          --v38;
          v39 = -2147024774;
          break;
        }
        break;
      }
      ++v31;
      *v38++ = v40;
      --v37;
      if ( !--v33 )
        goto LABEL_52;
    }
    *v38 = 0;
    if ( v39 >= 0 )
    {
      v11 = TaskXmlReader::LoadTranslatedString(&lpMem, v38, v36);
      if ( v11 < 0 )
      {
        operator delete(lpMem);
LABEL_383:
        operator delete(v212);
        return (unsigned int)v11;
      }
      v42 = *(unsigned int **)(a1 + 16);
      v43 = v42[38];
      v44 = lpMem;
      if ( v43 )
      {
        v42[38] = v43 + 1;
        v17 = a3;
      }
      else
      {
        v41 = *v42;
        if ( (_DWORD)v41 == 65542 )
        {
LABEL_57:
          v17 = a3;
          v45 = (__int64 *)&(&Schema::schemaEntries)[(unsigned __int16)v41][16 * (__int64)(int)a3];
        }
        else
        {
          switch ( (int)v41 )
          {
            case 65536:
            case 65537:
              v140 = 0;
              v141 = (unsigned __int16)v41;
              v41 = (unsigned __int64)(&Schema::schemaEntriesCount)[(unsigned __int16)v41];
              v142 = &_ImageBase + 4 * v141 + 279376;
              v17 = a3;
              break;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
              goto LABEL_57;
            default:
              v17 = a3;
              goto LABEL_477;
          }
          while ( v140 < v41 )
          {
            v45 = (__int64 *)(*(_QWORD *)v142 + (v140 << 7));
            v46 = *(_DWORD *)v45;
            if ( *(_DWORD *)v45 == a3 )
              goto LABEL_59;
            ++v140;
          }
LABEL_477:
          v45 = &qword_18009D560;
        }
        v46 = *(_DWORD *)v45;
LABEL_59:
        if ( v46 )
        {
          v47 = *((_QWORD *)v42 + 2);
          if ( !v47 )
            _com_raise_error(-2147467261, (struct IErrorInfo *)v41);
          v48 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64, unsigned __int16 *const))(*(_QWORD *)v47 + 216LL))(
                  v47,
                  &ChannelPath,
                  v45[1],
                  Schema::namespaceUri);
          v11 = v48;
          if ( v48 < 0 )
            goto LABEL_70;
          if ( !v48 && v44 )
          {
            v49 = *((_QWORD *)v42 + 2);
            if ( !v49 )
              _com_raise_error(-2147467261, (struct IErrorInfo *)v41);
            v11 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v49 + 224LL))(v49, v44);
            if ( v11 < 0 )
              goto LABEL_70;
          }
        }
        else
        {
          v42[38] = 1;
        }
      }
      v50 = v42[38];
      if ( v50 )
      {
        v42[38] = v50 - 1;
        v11 = 1;
      }
      else
      {
        v51 = *((_QWORD *)v42 + 2);
        if ( !v51 )
          _com_raise_error(-2147467261, (struct IErrorInfo *)v41);
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 120LL))(v51);
      }
      if ( v11 >= 0 )
      {
        if ( v44 )
          HeapFree(g_PrivateHeap, 0, v44);
LABEL_223:
        *(_BYTE *)(a1 + 1112) = 0;
LABEL_77:
        v54 = v220;
        if ( !v220
          || (v55 = v221,
              LOBYTE(v200) = *v221,
              v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _BYTE *, int))(*(_QWORD *)v220 + 8LL))(
                      v220,
                      a1 + 1116,
                      v17,
                      v205,
                      v200),
              *v55 = 1,
              v11 >= 0) )
        {
LABEL_79:
          if ( v212 )
            HeapFree(g_PrivateHeap, 0, v212);
          return (unsigned int)v11;
        }
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v54 + 24LL))(v54) )
        {
          v199 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 24LL))(v54);
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, v199, a1 + 64);
        }
        else
        {
          v11 = TaskXmlReader::SetErrorInfo(a1, (unsigned int)v11, v17, a1 + 64);
        }
        goto LABEL_383;
      }
LABEL_70:
      if ( v44 )
        HeapFree(g_PrivateHeap, 0, v44);
      goto LABEL_79;
    }
  }
  operator delete(v36);
  operator delete(v212);
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x180003220  mov     [rsp-8+arg_18], rbx
0x180003225  push    rbp
0x180003226  push    rsi
0x180003227  push    rdi
0x180003228  push    r12
0x18000322a  push    r13
0x18000322c  push    r14
0x18000322e  push    r15
0x180003230  lea     rbp, [rsp-30h]
0x180003235  sub     rsp, 130h
0x18000323c  mov     rax, cs:__security_cookie
0x180003243  xor     rax, rsp
0x180003246  mov     [rbp+60h+var_40], rax
0x18000324a  movzx   r15d, r9b
0x18000324e  movsxd  rsi, r8d
0x180003251  mov     [rsp+160h+var_130], esi
0x180003255  mov     [rbp+60h+var_A0], rdx
0x180003259  mov     r13, rcx
0x18000325c  mov     rax, [rbp+60h+arg_20]
0x180003263  mov     [rbp+60h+var_98], rax
0x180003267  mov     [rsp+160h+var_110], 0
0x18000326c  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003271  call    cs:__imp_GetSystemTimeAsFileTime
0x180003277  xor     edi, edi
0x180003279  mov     [rsp+160h+var_100], rdi
0x18000327e  mov     [rsp+160h+var_F8], edi
0x180003282  mov     [rsp+160h+var_F4], di
0x180003287  mov     [rbp+60h+var_D8], rdi
0x18000328b  mov     byte ptr [r13+458h], 1
0x180003293  mov     r8d, [r13+45Ch]
0x18000329a  mov     r12, cs:off_1800886D0
0x1800032a1  lea     r11, __ImageBase
0x1800032a8  cmp     r8d, 10006h
0x1800032af  jnz     loc_180003ACE
0x1800032b5  movzx   eax, r8w; jumptable 0000000180003AEB cases 65538-65541
0x1800032b9  mov     rdx, rsi
0x1800032bc  shl     rdx, 7
0x1800032c0  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800032c8  mov     ecx, [rdx+1Ch]
0x1800032cb  cmp     ecx, 1Ah
0x1800032ce  jnz     loc_1800048BD
0x1800032d4  mov     ebx, edi
0x1800032d6  lea     r11, __ImageBase
0x1800032dd  cmp     r8d, 10006h
0x1800032e4  jnz     loc_180003B27
0x1800032ea  movzx   eax, r8w; jumptable 0000000180003B47 cases 65538-65541
0x1800032ee  mov     rdx, rsi
0x1800032f1  shl     rdx, 7
0x1800032f5  add     rdx, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800032fd  movsxd  rdi, dword ptr [rdx+1Ch]
0x180003301  cmp     edi, 7
0x180003304  jz      loc_18000346A; jumptable 0000000180003330 cases 1,2,6
0x18000330a  cmp     edi, 8
0x18000330d  jz      loc_1800037B1
0x180003313  cmp     edi, 14h
0x180003316  jz      loc_1800036B1
0x18000331c  cmp     edi, 1Ah; switch 27 cases
0x18000331f  ja      def_180003330; jumptable 0000000180003330 default case, cases 7,8,20
0x180003325  mov     ecx, ds:(jpt_180003330 - 180000000h)[r11+rdi*4]
0x18000332d  add     rcx, r11
0x180003330  jmp     rcx; switch jump
0x180003332  lea     rsi, [r13+40h]; jumptable 0000000180003330 case 4
0x180003336  mov     rdx, rsi; struct XmlParserTempString *
0x180003339  mov     rcx, r13; this
0x18000333c  call    ?LoadRawValue@TaskXmlReader@@AEAAJAEAUXmlParserTempString@@@Z; TaskXmlReader::LoadRawValue(XmlParserTempString &)
0x180003341  mov     ebx, eax
0x180003343  test    eax, eax
0x180003345  js      loc_180004776
0x18000334b  mov     edx, [rsi]; unsigned __int64
0x18000334d  lea     r8, [rsp+160h+var_110]; struct TSTime *
0x180003352  mov     rcx, [r13+48h]; unsigned __int16 *
0x180003356  call    ?ParseDateTime@TSParser@@SAJPEBG_KAEAVTSTime@@@Z; TSParser::ParseDateTime(ushort const *,unsigned __int64,TSTime &)
0x18000335b  test    eax, eax
0x18000335d  js      loc_180004A31
0x180003363  xor     ebx, ebx
0x180003365  mov     r15d, [rsp+160h+var_130]
0x18000336a  mov     [rbp+60h+var_E0], rsi
0x18000336e  cmp     byte ptr [r13+28h], 0
0x180003373  jz      loc_1800036EC
0x180003379  mov     rdi, [r13+10h]
0x18000337d  mov     eax, [rdi+98h]
0x180003383  test    eax, eax
0x180003385  jnz     loc_180004A3B
0x18000338b  mov     edx, [rdi]; struct IErrorInfo *
0x18000338d  cmp     edx, 10006h
0x180003393  jnz     loc_18000441D
0x180003399  lea     r11, __ImageBase
0x1800033a0  movzx   eax, dx; jumptable 0000000180004440 cases 65538-65541
0x1800033a3  movsxd  rcx, r15d
0x1800033a6  shl     rcx, 7
0x1800033aa  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800033b2  add     r8, rcx
0x1800033b5  mov     eax, [r8]
0x1800033b8  test    eax, eax
0x1800033ba  jz      loc_180004A54
0x1800033c0  mov     rcx, [rdi+10h]
0x1800033c4  test    rcx, rcx
0x1800033c7  jz      loc_180004A63
0x1800033cd  mov     rsi, [rsi+8]
0x1800033d1  mov     rax, [rcx]
0x1800033d4  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x1800033db  mov     r8, [r8+8]
0x1800033df  lea     rdx, ChannelPath
0x1800033e6  mov     rax, [rax+0D8h]
0x1800033ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f2  mov     ebx, eax
0x1800033f4  test    eax, eax
0x1800033f6  js      loc_180003737
0x1800033fc  jnz     short loc_18000342C
0x1800033fe  test    rsi, rsi
0x180003401  jz      short loc_18000342C
0x180003403  mov     rcx, [rdi+10h]
0x180003407  test    rcx, rcx
0x18000340a  jz      loc_180004A6E
0x180003410  mov     rax, [rcx]
0x180003413  mov     rdx, rsi
0x180003416  mov     rax, [rax+0E0h]
0x18000341d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003422  mov     ebx, eax
0x180003424  test    eax, eax
0x180003426  js      loc_180003737
0x18000342c  mov     eax, [rdi+98h]
0x180003432  test    eax, eax
0x180003434  jnz     loc_180004A79
0x18000343a  mov     rcx, [rdi+10h]
0x18000343e  test    rcx, rcx
0x180003441  jz      loc_180004A8B
0x180003447  mov     rax, [rcx]
0x18000344a  mov     rax, [rax+78h]
0x18000344e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003453  mov     ebx, eax
0x180003455  test    ebx, ebx
0x180003457  js      loc_180003737
0x18000345d  mov     byte ptr [r13+458h], 0
0x180003465  jmp     loc_1800036F8
0x18000346a  test    byte ptr [r13+452h], 1; jumptable 0000000180003330 cases 1,2,6
0x180003472  jnz     loc_1800050D3
0x180003478  mov     [r13+40h], ebx
0x18000347c  mov     [r13+48h], rbx
0x180003480  and     byte ptr [r13+452h], 0FCh
0x180003488  xor     eax, eax
0x18000348a  mov     [r13+50h], ax
0x18000348f  test    r15b, r15b
0x180003492  jz      loc_180003936
0x180003498  cmp     edi, 2
0x18000349b  jz      loc_180003778
0x1800034a1  cmp     edi, 7
0x1800034a4  jz      loc_180003778
0x1800034aa  cmp     edi, 6
0x1800034ad  jnz     short loc_1800034BA
0x1800034af  cmp     dword ptr [r13+40h], 0
0x1800034b4  jz      loc_1800041A6
0x1800034ba  lea     rdx, [r13+40h]; struct IErrorInfo *
0x1800034be  mov     [rbp+60h+var_E0], rdx
0x1800034c2  cmp     byte ptr [r13+28h], 0
0x1800034c7  jz      loc_1800036E7
0x1800034cd  movsxd  rsi, [rsp+160h+var_130]
0x1800034d2  cmp     esi, 82h
0x1800034d8  jnz     loc_180003958
0x1800034de  lea     r15, __ImageBase
0x1800034e5  mov     rbx, [rdx+8]; jumptable 000000018000511F cases 6,8,10,11,112,115,121,129
0x1800034e9  test    rbx, rbx
0x1800034ec  jz      loc_180004979
0x1800034f2  mov     esi, [rdx]
0x1800034f4  test    esi, esi
0x1800034f6  jz      loc_180004975
0x1800034fc  lea     edi, [rsi+1]
0x1800034ff  mov     eax, 2
0x180003504  mul     rdi
0x180003507  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000350e  cmovb   rax, r14
0x180003512  mov     r8, rax; dwBytes
0x180003515  xor     edx, edx; dwFlags
0x180003517  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18000351e  call    cs:__imp_HeapAlloc
0x180003524  mov     r8, rax
0x180003527  test    rax, rax
0x18000352a  jz      loc_180005184
0x180003530  mov     [rsp+160h+lpMem], rax
0x180003535  test    rdi, rdi
0x180003538  jz      loc_180005243
0x18000353e  cmp     rdi, 7FFFFFFFh
0x180003545  ja      loc_1800051CA
0x18000354b  cmp     esi, 7FFFFFFEh
0x180003551  ja      loc_1800051D1
0x180003557  mov     ecx, esi
0x180003559  mov     rdx, rax
0x18000355c  xor     esi, esi
0x18000355e  xchg    ax, ax
0x180003560  test    rcx, rcx
0x180003563  jz      short loc_18000358E
0x180003565  movzx   eax, word ptr [rbx]
0x180003568  test    ax, ax
0x18000356b  jz      loc_1800037A3
0x180003571  add     rbx, 2
0x180003575  mov     [rdx], ax
0x180003578  add     rdx, 2
0x18000357c  dec     rcx
0x18000357f  sub     rdi, 1
0x180003583  jnz     short loc_180003560
0x180003585  sub     rdx, 2
0x180003589  mov     esi, 8007007Ah
0x18000358e  xor     eax, eax
0x180003590  mov     [rdx], ax
0x180003593  test    esi, esi
0x180003595  js      loc_180005252
0x18000359b  lea     rcx, [rsp+160h+lpMem]
0x1800035a0  call    ?LoadTranslatedString@TaskXmlReader@@SAJAEAV?$AutoVectorPtr@G@wmi@@@Z; TaskXmlReader::LoadTranslatedString(wmi::AutoVectorPtr<ushort> &)
0x1800035a5  mov     ebx, eax
0x1800035a7  test    eax, eax
0x1800035a9  js      loc_180004404
0x1800035af  mov     rdi, [r13+10h]
0x1800035b3  mov     eax, [rdi+98h]
0x1800035b9  mov     rsi, [rsp+160h+lpMem]
0x1800035be  test    eax, eax
0x1800035c0  jnz     loc_1800051DE
0x1800035c6  mov     edx, [rdi]; struct IErrorInfo *
0x1800035c8  cmp     edx, 10006h
0x1800035ce  jnz     loc_180004265
0x1800035d4  movzx   eax, dx; jumptable 0000000180004281 cases 65538-65541
0x1800035d7  movsxd  r15, [rsp+160h+var_130]
0x1800035dc  mov     rcx, r15
0x1800035df  shl     rcx, 7
0x1800035e3  lea     r11, __ImageBase
0x1800035ea  mov     r8, ds:rva ?schemaEntries@Schema@@0PAPEBUSchemaEntry@@A[r11+rax*8]; SchemaEntry const * near * Schema::schemaEntries ...
0x1800035f2  add     r8, rcx
0x1800035f5  mov     eax, [r8]
0x1800035f8  test    eax, eax
0x1800035fa  jz      loc_180005201
0x180003600  mov     rcx, [rdi+10h]
0x180003604  test    rcx, rcx
0x180003607  jz      loc_180005210
0x18000360d  mov     rax, [rcx]
0x180003610  mov     r9, cs:?namespaceUri@Schema@@0UConstString@@B; ConstString const Schema::namespaceUri
0x180003617  mov     r8, [r8+8]
0x18000361b  lea     rdx, ChannelPath
0x180003622  mov     rax, [rax+0D8h]
0x180003629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000362e  mov     ebx, eax
0x180003630  test    eax, eax
0x180003632  js      short loc_180003691
0x180003634  jnz     short loc_180003660
0x180003636  test    rsi, rsi
0x180003639  jz      short loc_180003660
0x18000363b  mov     rcx, [rdi+10h]
0x18000363f  test    rcx, rcx
0x180003642  jz      loc_18000521B
0x180003648  mov     rax, [rcx]
0x18000364b  mov     rdx, rsi
0x18000364e  mov     rax, [rax+0E0h]
0x180003655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000365a  mov     ebx, eax
0x18000365c  test    eax, eax
0x18000365e  js      short loc_180003691
0x180003660  mov     eax, [rdi+98h]
0x180003666  test    eax, eax
0x180003668  jnz     loc_180005226
0x18000366e  mov     rcx, [rdi+10h]
0x180003672  test    rcx, rcx
0x180003675  jz      loc_180005238
0x18000367b  mov     rax, [rcx]
0x18000367e  mov     rax, [rax+78h]
0x180003682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003687  mov     ebx, eax
0x180003689  test    ebx, ebx
0x18000368b  jns     loc_1800040BD
0x180003691  test    rsi, rsi
0x180003694  jz      loc_180003737
0x18000369a  mov     r8, rsi; lpMem
0x18000369d  xor     edx, edx; dwFlags
0x18000369f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800036a6  call    cs:__imp_HeapFree
0x1800036ac  jmp     loc_180003737
0x1800036b1  mov     dword ptr [rsp+160h+lpMem], 10006h
0x1800036b9  lea     rdx, [rsp+160h+lpMem]; enum Schema::Version *
0x1800036be  mov     rcx, r13; this
0x1800036c1  call    ?LoadValue@TaskXmlReader@@AEAAJAEAW4Version@Schema@@@Z; TaskXmlReader::LoadValue(Schema::Version &)
0x1800036c6  mov     ebx, eax
0x1800036c8  test    eax, eax
0x1800036ca  js      loc_180004FF2
0x1800036d0  mov     eax, dword ptr [rsp+160h+lpMem]
0x1800036d4  mov     [r13+45Ch], eax
0x1800036db  mov     [rsp+160h+rclsid.Data1], eax
0x1800036df  lea     rax, [r13+40h]
0x1800036e3  mov     [rbp+60h+var_E0], rax
0x1800036e7  mov     r15d, [rsp+160h+var_130]
0x1800036ec  mov     byte ptr [r13+458h], 0
0x1800036f4  test    ebx, ebx
0x1800036f6  js      short loc_180003737
0x1800036f8  mov     rsi, [rbp+60h+var_A0]
0x1800036fc  test    rsi, rsi
0x1800036ff  jz      short loc_180003737
0x180003701  mov     rax, [rsi]
0x180003704  lea     rdx, [r13+45Ch]
0x18000370b  mov     rdi, [rbp+60h+var_98]
0x18000370f  movzx   ecx, byte ptr [rdi]
0x180003712  mov     byte ptr [rsp+160h+var_140], cl
0x180003716  lea     r9, [rsp+160h+var_110]
0x18000371b  mov     r8d, r15d
0x18000371e  mov     rcx, rsi
  ... truncated ...
```
