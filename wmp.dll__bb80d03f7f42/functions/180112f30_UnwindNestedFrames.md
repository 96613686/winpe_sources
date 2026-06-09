# _UnwindNestedFrames

- ea: `0x180112f30`
- end: `0x180114b81`
- name: `_UnwindNestedFrames`
- size: `7249`
- prototype: ``
- caller_count: `1`
- callee_count: `75`
- tags: `file_ops, loader_planting`

## callers

- `0x18069644c`

## callees

- `0x180007b30`
- `0x18000cb40`
- `0x18000ef70`
- `0x180011028`
- `0x180015184`
- `0x1800178b0`
- `0x180027db0`
- `0x18002dea0`
- `0x18003946c`
- `0x18003e3c0`
- `0x180054c60`
- `0x180056de0`
- `0x18005f374`
- `0x180060630`
- `0x1800654d0`
- `0x18006d200`
- `0x18008d3a8`
- `0x18008ebdc`
- `0x18009e600`
- `0x1800a0894`
- `0x1800bd300`
- `0x18010194c`
- `0x180112c24`
- `0x180112f30`
- `0x180114b88`
- `0x180114e48`
- `0x1801152d8`
- `0x180115340`
- `0x180115884`
- `0x180115b74`
- `0x180115c78`
- `0x180119fd8`
- `0x180121ad0`
- `0x1801232bc`
- `0x180159890`
- `0x18018435c`
- `0x180184410`
- `0x180187c64`
- `0x1801ac808`
- `0x1801ba5dc`
- `0x1802ffad4`
- `0x18031682c`
- `0x18032ec7c`
- `0x1805684ac`
- `0x18061ad44`
- `0x180620034`
- `0x1806202f4`
- `0x180622194`
- `0x180622870`
- `0x18062dcf0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180113e88`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180113f19`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180113e88`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180113f19`
- `OLEAUT32!VariantInit` at `0x180113139`
- `OLEAUT32!VariantInit` at `0x180113139`
- `OLEAUT32!VariantClear` at `0x180113283`
- `OLEAUT32!VariantClear` at `0x1801148e6`
- `OLEAUT32!VariantClear` at `0x180113283`
- `OLEAUT32!VariantClear` at `0x1801148e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180113c66`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180113cfe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180113c66`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180113cfe`
- `SHLWAPI!PathFindFileNameW` at `0x180113c46`
- `SHLWAPI!PathFindFileNameW` at `0x180113ce5`
- `SHLWAPI!PathFindFileNameW` at `0x180113c46`
- `SHLWAPI!PathFindFileNameW` at `0x180113ce5`

## string_xrefs

- `0x180113f7e`: `CSyncEngine::TransferFileToDevice - Insert3 copy file`

## pseudocode

```c
__int64 __fastcall UnwindNestedFrames(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int64 a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int16 v13; // r12
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  BSTR v17; // r15
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r9
  char v27; // r14
  __int64 (__fastcall ***v28)(_QWORD, __int64 *, __int64 *); // rsi
  __int64 v29; // r12
  int v30; // edx
  int v31; // r8d
  int v32; // r9d
  __int128 v33; // xmm0
  int v34; // ebx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // r8
  __int128 v38; // xmm0
  __int64 v39; // r8
  int v40; // esi
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int128 v44; // xmm0
  int v45; // eax
  const WCHAR *v46; // rbx
  __int64 v47; // r9
  const WCHAR *v48; // rcx
  const WCHAR *FileNameW; // r12
  const WCHAR *v50; // rcx
  LPWSTR ExtensionW; // rax
  __int64 v52; // rcx
  __int64 v53; // r9
  LPWSTR v54; // rax
  LPWSTR v55; // r15
  const WCHAR *v56; // r13
  __int64 v57; // rbx
  unsigned int v58; // esi
  int v59; // r11d
  char v60; // r12
  int v61; // r14d
  int v62; // r9d
  int v63; // edx
  int v64; // r8d
  __int64 v65; // rbx
  __int64 v66; // rcx
  __int64 v67; // r8
  int v68; // ecx
  __int64 v69; // rax
  PCNZWCH v70; // rbx
  PCNZWCH v71; // r14
  int v72; // eax
  unsigned __int64 v73; // r8
  int v74; // ebx
  __int64 v75; // rcx
  unsigned __int64 v76; // rax
  int v77; // r12d
  const WCHAR *v78; // r15
  __int64 v79; // rbx
  unsigned int v80; // esi
  unsigned __int64 v81; // rsi
  unsigned int v82; // ebx
  __int64 v83; // rax
  const WCHAR *v84; // rbx
  __int64 v85; // rcx
  int v86; // ebx
  char v87; // si
  int v88; // ebx
  unsigned int v89; // ebx
  unsigned int v90; // eax
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // r8
  unsigned int v94; // ebx
  void *v96; // [rsp+20h] [rbp-E0h]
  __int16 v97; // [rsp+30h] [rbp-D0h]
  char v98[8]; // [rsp+38h] [rbp-C8h]
  char v99[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v100; // [rsp+64h] [rbp-9Ch]
  _WORD v101[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v102; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v103; // [rsp+70h] [rbp-90h]
  unsigned __int64 v104; // [rsp+78h] [rbp-88h] BYREF
  __int64 v105; // [rsp+80h] [rbp-80h] BYREF
  PCNZWCH v106; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v107)(_QWORD, __int64 *, _QWORD *); // [rsp+90h] [rbp-70h] BYREF
  unsigned int v108; // [rsp+98h] [rbp-68h]
  __int16 v109; // [rsp+9Ch] [rbp-64h]
  int v110; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall ***v111)(_QWORD, __int64 *, __int64 *); // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v112[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v113; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v114; // [rsp+D0h] [rbp-30h] BYREF
  int v115; // [rsp+D8h] [rbp-28h]
  __int16 v116; // [rsp+DCh] [rbp-24h]
  unsigned int v117; // [rsp+E0h] [rbp-20h]
  int v118; // [rsp+E4h] [rbp-1Ch] BYREF
  int v119[2]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int64 v120; // [rsp+F0h] [rbp-10h] BYREF
  char v121[8]; // [rsp+F8h] [rbp-8h] BYREF
  int v122; // [rsp+100h] [rbp+0h] BYREF
  __int64 v123; // [rsp+108h] [rbp+8h] BYREF
  int v124; // [rsp+110h] [rbp+10h]
  __int16 v125; // [rsp+114h] [rbp+14h]
  __int64 (__fastcall ***v126)(_QWORD, __int64 *, _QWORD *); // [rsp+118h] [rbp+18h] BYREF
  PCNZWCH lpString2; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v128; // [rsp+128h] [rbp+28h]
  __int16 v129; // [rsp+12Ch] [rbp+2Ch]
  __int64 v130; // [rsp+130h] [rbp+30h] BYREF
  int v131; // [rsp+138h] [rbp+38h]
  __int16 v132; // [rsp+13Ch] [rbp+3Ch]
  __int128 v133; // [rsp+140h] [rbp+40h] BYREF
  __int64 v134; // [rsp+150h] [rbp+50h]
  PCNZWCH lpString1; // [rsp+158h] [rbp+58h] BYREF
  int v136; // [rsp+160h] [rbp+60h]
  __int16 v137; // [rsp+164h] [rbp+64h]
  __int64 v138; // [rsp+168h] [rbp+68h] BYREF
  int v139; // [rsp+170h] [rbp+70h]
  __int16 v140; // [rsp+174h] [rbp+74h]
  __int64 v141; // [rsp+178h] [rbp+78h] BYREF
  int v142; // [rsp+180h] [rbp+80h]
  __int16 v143; // [rsp+184h] [rbp+84h]
  int v144; // [rsp+188h] [rbp+88h] BYREF
  __int64 *v145; // [rsp+190h] [rbp+90h]
  __int64 v146; // [rsp+198h] [rbp+98h] BYREF
  __int64 (__fastcall ***v147)(_QWORD, __int64 *, __int64 *); // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v148; // [rsp+1A8h] [rbp+A8h] BYREF
  int v149; // [rsp+1B0h] [rbp+B0h]
  __int16 v150; // [rsp+1B4h] [rbp+B4h]
  LPCWCH lpWideCharStr; // [rsp+1B8h] [rbp+B8h] BYREF
  int v152; // [rsp+1C0h] [rbp+C0h]
  __int16 v153; // [rsp+1C4h] [rbp+C4h]
  LPCWSTR pszPath; // [rsp+1C8h] [rbp+C8h] BYREF
  int v155; // [rsp+1D0h] [rbp+D0h]
  __int16 v156; // [rsp+1D4h] [rbp+D4h]
  _QWORD v157[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  struct _FILETIME v158; // [rsp+1E8h] [rbp+E8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+1F0h] [rbp+F0h] BYREF
  const WCHAR *v160; // [rsp+1F8h] [rbp+F8h] BYREF
  int v161; // [rsp+200h] [rbp+100h]
  __int16 v162; // [rsp+204h] [rbp+104h]
  BSTR v163; // [rsp+208h] [rbp+108h] BYREF
  int v164; // [rsp+210h] [rbp+110h]
  __int16 v165; // [rsp+214h] [rbp+114h]
  VARIANTARG pvarg; // [rsp+218h] [rbp+118h] BYREF
  PCNZWCH v167[2]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v168; // [rsp+240h] [rbp+140h]
  _BYTE v169[144]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v170[144]; // [rsp+2E0h] [rbp+1E0h] BYREF
  GUID Buf2; // [rsp+370h] [rbp+270h] BYREF
  GUID v172; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v173[96]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v174[96]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _BYTE v175[304]; // [rsp+450h] [rbp+350h] BYREF
  __int128 v176; // [rsp+580h] [rbp+480h] BYREF
  __int64 v177; // [rsp+590h] [rbp+490h]

  v117 = a4;
  v103 = a2;
  v145 = a6;
  v11 = a7;
  v12 = a8;
  v108 = 0;
  LODWORD(v111) = 0;
  v13 = 3;
  LOBYTE(a4) = 3;
  sub_18031682C((unsigned int)v174, a2, a3, a4, 1);
  if ( (dword_1808E0D80 & 1) != 0 )
    sub_18018435C(&qword_1808C5BA0, qword_180809C28, v14, 1, &v176);
  sub_18061AD44(L"WMPPERF_PDA_TRANSFER_FILE_START");
  LOBYTE(v15) = 1;
  sub_180187C64(1414681414, qword_180809F18, v16, v15);
  *(_DWORD *)v99 = 0;
  v110 = 0;
  Buf2 = ::Buf2;
  v172 = ::Buf2;
  v126 = 0;
  v147 = 0;
  *(_QWORD *)v119 = 0;
  v146 = 0;
  v105 = 0;
  v112[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v141 = 0;
  v142 = 0;
  v143 = 4;
  v138 = 0;
  v139 = 0;
  v140 = 4;
  v130 = 0;
  v131 = 0;
  v132 = 4;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  lpString1 = 0;
  v136 = 0;
  v137 = 0;
  pszPath = 0;
  v155 = 0;
  v156 = 0;
  lpString2 = 0;
  v128 = 0;
  v129 = 0;
  v123 = 0;
  v124 = 0;
  v125 = 0;
  v17 = 0;
  v163 = 0;
  v164 = 0;
  v165 = 0;
  v118 = 0;
  v122 = 0;
  v101[0] = 0;
  lpWideCharStr = 0;
  v152 = 0;
  v153 = 0;
  SystemTimeAsFileTime = 0;
  v158 = 0;
  sub_180060630(v169);
  sub_180060630(v170);
  v160 = 0;
  v161 = 0;
  v162 = 4;
  *(_DWORD *)(a1 + 1448) = 0;
  VariantInit(&pvarg);
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x400) != 0
    && *((_BYTE *)RequestContext + 25) >= 7u )
  {
    v97 = *(_WORD *)(sub_1802FFAD4(a1 + 912, a2) + 8);
    sub_1806AC280(*((_QWORD *)RequestContext + 2), v18, v19, a2, a5, v145, v97);
  }
  sub_1801152D8(v175, "CSyncEngine::TransferFileToDevice", v99, a1 + 1888);
  sub_180112C24(a1, a2, &Buf2);
  if ( !memcmp(&stru_180801348, &Buf2, 0x10u) )
  {
    v118 = 1;
  }
  else if ( !memcmp(&xmmword_180801338, &Buf2, 0x10u) )
  {
    v122 = 1;
  }
  if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)(a1 + 8) + 32LL))(
         a1 + 8,
         a2,
         264,
         &pvarg) >= 0
    && pvarg.vt == 8
    && pvarg.llVal )
  {
    sub_180007B30(&v163, pvarg.bstrVal, 0xFFFFFFFFLL, v20);
    v17 = v163;
  }
  VariantClear(&pvarg);
  v21 = 5;
  if ( *(int *)v99 < 0 )
    goto LABEL_286;
  *(_DWORD *)v99 = (*(__int64 (__fastcall **)(_QWORD, int *, __int64))(**(_QWORD **)(a1 + 1480) + 136LL))(
                     *(_QWORD *)(a1 + 1480),
                     v119,
                     5);
  if ( *(int *)v99 < 0 )
  {
    v21 = 5;
    goto LABEL_286;
  }
  v113 = (__int128)Buf2;
  sub_1806A3228(a1, v119[0], a2, (int)v17, &v113, (__int64)&v141, (__int64)&v138, (__int64)&v130, v11, v12);
  *(_DWORD *)v99 = 0;
  sub_18003E3C0(&v113, *(_QWORD *)(a1 + 176));
  v22 = *(_DWORD *)(sub_1802FFAD4(a1 + 912, a2) + 8);
  sub_180027DB0(&v113);
  if ( (v22 & 1) != 0 )
  {
    v102 = -1;
    v106 = 0;
    *(_DWORD *)v99 = sub_1806B0844(a1, a2, (unsigned int)&v102, (unsigned int)&v106, 0);
    if ( v106 && v102 != -1 )
    {
      v176 = 0;
      v177 = 0;
      LOWORD(v176) = 0;
      *(_DWORD *)v99 = (*(__int64 (__fastcall **)(PCNZWCH, _QWORD, __int64, __int128 *))(*(_QWORD *)v106 + 32LL))(
                         v106,
                         v102,
                         264,
                         &v176);
      if ( (_WORD)v176 == 8 )
      {
        if ( *((_QWORD *)&v176 + 1) )
        {
          if ( **((_WORD **)&v176 + 1) )
          {
            sub_1806A52C4(a1, *((_QWORD *)&v176 + 1), &v105);
            if ( v105 )
            {
              sub_18003E3C0(&v113, *(_QWORD *)(a1 + 176));
              v23 = sub_1802FFAD4(a1 + 912, a2);
              sub_180056DE0(v23 + 16, v105);
              sub_180027DB0(&v113);
              if ( RequestContext != &RequestContext
                && (*((_DWORD *)RequestContext + 7) & 0x400) != 0
                && *((_BYTE *)RequestContext + 25) >= 4u )
              {
                sub_180121AD0(*((_QWORD *)RequestContext + 2), 47, &stru_180870240, a2);
              }
              v107 = 0;
              *(_DWORD *)v99 = (**(__int64 (__fastcall ***)(__int64, __int64 *, _QWORD *))v105)(
                                 v105,
                                 qword_180867FA0,
                                 &v107);
              if ( *(int *)v99 >= 0 )
              {
                *(_DWORD *)v99 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD *), _QWORD))(*v107)[16])(
                                   v107,
                                   *(_QWORD *)v119);
                sub_18068DC14(v24, L"CSyncEngine::TransferFileToDevice - SetMetadata", *(unsigned int *)v99);
                if ( *(int *)v99 >= 0 )
                {
                  v110 = 6;
                  *(_DWORD *)v99 = 6;
                  if ( v118 && (*(_BYTE *)(a1 + 656) & 2) != 0 )
                  {
                    v120 = 0;
                    *(_QWORD *)v121 = 0;
                    v104 = 0;
                    if ( (**(int (__fastcall ***)(__int64, __int64 *, unsigned __int64 *))v105)(
                           v105,
                           qword_1807FBD78,
                           &v120) >= 0
                      && v120
                      && (*(int (__fastcall **)(unsigned __int64, char *))(*(_QWORD *)v120 + 192LL))(v120, v121) >= 0
                      && *(_QWORD *)v121
                      && (***(int (__fastcall ****)(_QWORD, __int64 *, unsigned __int64 *))v121)(
                           *(_QWORD *)v121,
                           qword_180867FA0,
                           &v104) >= 0
                      && v104 )
                    {
                      sub_1806AB448(a1, a2, v105);
                    }
                    sub_1800654D0(&v104);
                    sub_1800654D0(v121);
                    sub_1800654D0(&v120);
                  }
                  v25 = *(_QWORD *)(a1 + 544);
                  if ( v25 )
                  {
                    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v25 + 56LL))(
                      v25,
                      *((_QWORD *)&v176 + 1),
                      *(_QWORD *)v119);
                    v110 = 6;
                  }
                }
              }
              sub_1800654D0(&v107);
            }
          }
        }
      }
      sub_1800178B0(&v176);
    }
    sub_1800654D0(&v106);
  }
  if ( *(int *)v99 < 0 )
    goto LABEL_282;
  if ( v105 )
    goto LABEL_282;
  *(_DWORD *)v99 = sub_180054C60(a3, 0, &v123);
  if ( *(int *)v99 < 0 || !v17 || !*v17 )
    goto LABEL_282;
  v106 = 0;
  v100 = 0;
  v27 = 0;
  v28 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 1544);
  v107 = v28;
  if ( v28 )
  {
    sub_180007B30((BSTR *)&v114, *(const WCHAR **)(a1 + 552), 0xFFFFFFFFLL, v26);
    if ( *(_WORD *)(v114 + 2) )
    {
      v102 = 92;
      sub_180011028((__int64)&v114, (const WCHAR *)&v102, -1);
    }
    goto LABEL_53;
  }
  v28 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 1480);
  v107 = v28;
  v111 = v28;
  sub_180007B30((BSTR *)&v114, &SubBlock, 0xFFFFFFFFLL, v26);
  if ( (*(_DWORD *)(a1 + 656) & 8) == 0 )
  {
    if ( !memcmp(&stru_180801348, &Buf2, 0x10u) )
    {
      LOBYTE(v32) = 51;
      sub_18031682C((unsigned int)v173, v30, v31, v32, 1);
      v34 = sub_1806A54D0(a1, 1, &v114, 0);
      if ( v34 < 0 )
      {
        v41 = *(unsigned int *)v99;
      }
      else
      {
        if ( (*(_DWORD *)(a1 + 656) & 4) == 0 )
        {
          *(_DWORD *)v99 = sub_18069C5D0(a1, a2, v112);
          if ( *(int *)v99 >= 0 )
          {
            if ( v112[0] )
              sub_18064468C(v112[0], &v141);
          }
        }
        v39 = v141;
        if ( !v141 )
        {
          sub_1800A0894(&v141, 916, 0);
          v39 = v141;
        }
        v40 = sub_1806A2E68(a1, *(_QWORD *)(a1 + 1488), v39, *(unsigned __int16 *)(a1 + 1708), &v126, &v114, 0);
        v41 = (unsigned int)v40;
        *(_DWORD *)v99 = v40;
        if ( v40 < 0 )
        {
          v28 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 1488);
          v107 = v28;
          v101[0] = 1;
        }
        else
        {
          if ( (*(_DWORD *)(a1 + 656) & 4) == 0 )
          {
            v42 = v112[0];
            if ( v112[0] || (*(_DWORD *)v99 = sub_18069C5D0(a1, a2, v112), *(int *)v99 >= 0) && (v42 = v112[0]) != 0 )
              sub_18064453C(v42, &v138);
          }
          v43 = v138;
          if ( !v138 )
          {
            sub_1800A0894(&v138, 917, 0);
            v43 = v138;
          }
          v34 = sub_1806A2E68(a1, v126, v43, *(unsigned __int16 *)(a1 + 1708), &v147, &v114, 0);
          v41 = (unsigned int)v34;
          *(_DWORD *)v99 = v34;
          if ( v34 < 0 )
          {
            v107 = v126;
            v13 = 2;
            v34 = v40;
            v28 = v126;
          }
          else
          {
            v28 = v147;
            v107 = v147;
          }
          v101[0] = v13;
        }
      }
      sub_180115C78(v173, v41);
      sub_180115884(v173);
      goto LABEL_90;
    }
    if ( !memcmp(&xmmword_180801338, &Buf2, 0x10u) )
    {
      v29 = a1 + 8;
      sub_180115340(a1 + 8, a2, 365, &v172);
      if ( memcmp(&xmmword_1808023C8, &v172, 0x10u) || (*(_DWORD *)(a1 + 656) & 0x40000) != 0 )
        v33 = xmmword_180801338;
      else
        v33 = xmmword_1808023C8;
      v113 = v33;
      v34 = sub_180114E48(a1, &v113, 0, &v111, v101, &v114);
      v28 = v111;
      v107 = v111;
LABEL_91:
      if ( v34 )
      {
        if ( v34 == -1072885383 )
          *(_DWORD *)v99 = -1072885383;
      }
      else
      {
        v100 = 1;
      }
      goto LABEL_95;
    }
    v35 = memcmp(&xmmword_180802810, &Buf2, 0x10u);
    v36 = a1;
    if ( v35 )
    {
      v38 = xmmword_1807FF358;
      v37 = 0;
      goto LABEL_66;
    }
    *(_DWORD *)v99 = sub_18069C5D0(a1, a2, v112);
    if ( *(int *)v99 >= 0 )
    {
      v37 = v112[0];
      if ( v112[0] )
      {
        v38 = xmmword_180802810;
        v36 = a1;
LABEL_66:
        v113 = v38;
        v34 = sub_180114E48(v36, &v113, v37, &v111, v101, &v114);
        v28 = v111;
        v107 = v111;
LABEL_90:
        v29 = a1 + 8;
        goto LABEL_91;
      }
    }
  }
LABEL_53:
  v29 = a1 + 8;
LABEL_95:
  if ( *(_DWORD *)v99 == -1072885383 || !v28 )
  {
    v78 = v106;
    goto LABEL_277;
  }
  if ( !v117 && (!memcmp(&xmmword_180802810, &Buf2, 0x10u) || !memcmp(&xmmword_180801338, &Buf2, 0x10u)) )
  {
    if ( !memcmp(&xmmword_180801338, &Buf2, 0x10u) )
    {
      v44 = xmmword_1808033F8;
      v45 = 46;
    }
    else
    {
      v44 = xmmword_1808033E0;
      v45 = 100;
    }
    v176 = v44;
    LODWORD(v177) = v45;
    sub_180114B88(v17);
  }
  *(_OWORD *)v167 = 0;
  v168 = 0;
  LOWORD(v167[0]) = 0;
  v102 = 0;
  sub_18003E3C0(&v113, *(_QWORD *)(a1 + 240));
  v46 = (const WCHAR *)sub_18032EC7C(a1 + 1288, a2);
  sub_180027DB0(&v113);
  if ( v46 )
  {
    v104 = 0;
    if ( (int)sub_18003946C(v169, 0, v46) < 0
      || (int)sub_180622194(v169, &v104) < 0
      || (v46 = 0, (int)sub_180622870(v169) >= 0)
      && (int)sub_1806202F4(v169, v170) >= 0
      && (int)sub_180054C60(v170, 0, &v160) >= 0
      && (int)sub_180620034(v169, &a5) >= 0
      && (v46 = v160) != 0 )
    {
      sub_180007B30((BSTR *)&v123, v46, 0xFFFFFFFFLL, v47);
    }
    sub_1800654D0(&v104);
  }
  *(_DWORD *)v99 = sub_18005F374(v17, &v102);
  if ( *(int *)v99 >= 0 )
  {
    if ( v117 )
    {
      v102 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, int *))(**(_QWORD **)(a1 + 528) + 56LL))(
               *(_QWORD *)(a1 + 528),
               v102,
               &v118,
               &v122);
    }
    else if ( v46 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, __int64, PCNZWCH *))(*(_QWORD *)v29 + 32LL))(v29, a2, 260, v167);
      sub_1806453AC(v167[1]);
    }
    *(_DWORD *)v99 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, unsigned int *, int))(**(_QWORD **)v119 + 24LL))(
                       *(_QWORD *)v119,
                       0,
                       L"WMDM/FormatCode",
                       &v102,
                       4);
  }
  v48 = v17;
  if ( v46 )
    v48 = v46;
  FileNameW = PathFindFileNameW(v48);
  v157[0] = FileNameW;
  v50 = v17;
  if ( v46 )
    v50 = v46;
  ExtensionW = PathFindExtensionW(v50);
  if ( ExtensionW && *ExtensionW )
    sub_180007B30((BSTR *)&lpWideCharStr, ExtensionW + 1, 0xFFFFFFFFLL, v53);
  if ( *(int *)v99 >= 0
    && (v117 && (int)sub_1806A4A68(v52, (_DWORD)v17, v102, v122, (__int64)&pszPath) >= 0
     || v46 && (int)sub_1806A49C8(v52, v17, lpWideCharStr, &pszPath) >= 0) )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v157[0] = FileNameW;
  }
  v54 = PathFindExtensionW(FileNameW);
  v55 = v54;
  if ( v54 )
  {
    if ( *v54 )
    {
      *v54 = 0;
      v55 = v54 + 1;
      v104 = 0;
      if ( (int)sub_1800BD300(v54 + 1, 0x7FFFFFFF, &v104) < 0 || v104 >= 7 )
        v55[6] = 0;
    }
  }
  sub_18009E600(&lpString1, (unsigned int)*(unsigned __int16 *)(a1 + 1710) + 12);
  sub_18008D3A8(&lpString1, L"%.*s.%s", *(unsigned __int16 *)(a1 + 1710), FileNameW, v55);
  v56 = lpString1;
  v106 = lpString1;
  *(_DWORD *)v99 = (**v28)(v28, qword_1808680F8, &v146);
  v57 = 0;
  if ( *(int *)v99 < 0 )
  {
    v78 = v56;
    goto LABEL_258;
  }
  v109 = 1;
  v58 = *(_DWORD *)(a1 + 656);
  v120 = -1;
  v104 = -1;
  *(_QWORD *)v121 = 0;
  sub_180646C20(v56);
  v60 = v59 & ~(unsigned __int8)(v58 >> 9);
  while ( 1 )
  {
    while ( 1 )
    {
      if ( !v60 )
        goto LABEL_182;
      if ( (*(_BYTE *)(a1 + 656) & 4) != 0 )
      {
        v57 = *(_QWORD *)v119;
        *(_QWORD *)&v113 = *(_QWORD *)v119;
        if ( *(_QWORD *)v119 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v119 + 8LL))(*(_QWORD *)v119);
          v59 = 1;
        }
        v61 = v59 | v108;
      }
      else
      {
        v148 = v57;
        v61 = v108 | 2;
      }
      v108 = v61;
      if ( (v61 & 2) != 0 )
      {
        v61 &= ~2u;
        v108 = v61;
        sub_1800654D0(&v148);
        LOBYTE(v59) = 1;
      }
      if ( ((unsigned __int8)v61 & (unsigned __int8)v59) != 0 )
      {
        v108 = v61 & 0xFFFFFFFE;
        sub_1800654D0(&v113);
        LOBYTE(v59) = 1;
      }
      *(_DWORD *)(a1 + 1704) = 0;
      *(_BYTE *)(a1 + 776) = v59;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      LOBYTE(v62) = 5;
      sub_18031682C((unsigned int)v173, v63, v64, v62, 1);
      *(_QWORD *)v98 = v57;
      v65 = v123;
      *(_DWORD *)v99 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, const WCHAR *, _QWORD, __int64, char *, _QWORD, __int64 *))(*(_QWORD *)v146 + 72LL))(
                         v146,
                         2053,
                         0,
                         v123,
                         v56,
                         0,
                         a1 + 16,
                         *(char **)v98,
                         0,
                         &v105);
      sub_180115C78(v173, *(unsigned int *)v99);
      GetSystemTimeAsFileTime(&v158);
      if ( RequestContext == &RequestContext || (*((_DWORD *)RequestContext + 7) & 0x400) == 0 )
        goto LABEL_154;
      v67 = *(unsigned int *)v99;
      v66 = (unsigned int)(*(_DWORD *)v99 >= 0) + 5;
      if ( *((unsigned __int8 *)RequestContext + 25) >= (unsigned int)v66 )
      {
        sub_1801BA5DC(*((_QWORD *)RequestContext + 2), 48, (unsigned int)&stru_180870240, *(_DWORD *)v99, v65);
LABEL_154:
        v67 = *(unsigned int *)v99;
      }
      sub_18068DC14(v66, L"CSyncEngine::TransferFileToDevice - Insert3 copy file", v67);
      v68 = *(_DWORD *)v99;
      if ( !*(_DWORD *)v99 )
      {
        v81 = a5;
        sub_180691EB8(0, v65, a5, SystemTimeAsFileTime.dwLowDateTime, *(_QWORD *)&v158);
        sub_18003E3C0(&v176, *(_QWORD *)(a1 + 176));
        v82 = v103;
        v83 = sub_1802FFAD4(a1 + 912, v103);
        sub_180056DE0(v83 + 16, v105);
        sub_180027DB0(&v176);
        if ( RequestContext != &RequestContext
          && (*((_DWORD *)RequestContext + 7) & 0x400) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180121AD0(*((_QWORD *)RequestContext + 2), 49, &stru_180870240, v82);
        }
        if ( (*(_DWORD *)(a1 + 656) & 0x3000) == 0 )
        {
          sub_18009E600(&lpString2, 260);
          v84 = lpString2;
          *(_DWORD *)v99 = (*(__int64 (__fastcall **)(__int64, PCNZWCH, _QWORD))(*(_QWORD *)v105 + 48LL))(
                             v105,
                             lpString2,
                             v128);
          if ( *(int *)v99 >= 0 )
          {
            *(_DWORD *)(a1 + 656) |= ((unsigned __int8)sub_18002DEA0(v56, v84) + 1) << 12;
            v106 = v84;
          }
          v82 = v103;
        }
        *(_QWORD *)(a1 + 808) -= v81;
        *(_BYTE *)(a1 + 848) = 0;
        v27 = 0;
        v100 = 0;
        v85 = v112[0];
        if ( v112[0] || (sub_18069C5D0(a1, v82, v112), (v85 = v112[0]) != 0) )
        {
          v133 = 0;
          v134 = 0;
          v86 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _DWORD, __int128 *))(*(_QWORD *)v85 + 48LL))(
                  v85,
                  0,
                  349,
                  0,
                  0,
                  &v133);
          v87 = 0;
          if ( v86 >= 0 )
          {
            if ( (_WORD)v133 == 8 )
            {
              v87 = sub_180119FD8(*((_QWORD *)&v133 + 1), 0);
              v86 = 0;
            }
            else
            {
              v86 = -2147418113;
            }
          }
          sub_1800178B0(&v133);
          if ( v86 >= 0 && v87 )
            ++*(_DWORD *)(a1 + 1896);
        }
LABEL_222:
        sub_180115884(v173);
        goto LABEL_223;
      }
      v27 = 1;
      if ( *(_DWORD *)v99 == -2147023729
        || *(_DWORD *)v99 == -2147024775
        || *(_DWORD *)v99 == -2147024875
        || (unsigned int)(*(_DWORD *)v99 + 2147014843) <= 1
        || *(_DWORD *)v99 == -2147201023
        || *(_DWORD *)v99 == -2147023728
        || *(_DWORD *)v99 == -2147024865
        || (unsigned int)(*(_DWORD *)v99 + 2147024894) <= 1
        || *(_DWORD *)v99 == -2147467260
        || *(_DWORD *)v99 == -2144731130 )
      {
        v68 = -1072885383;
        *(_DWORD *)v99 = -1072885383;
        *(_BYTE *)(a1 + 364) = 1;
        *(_BYTE *)(a1 + 1696) = 1;
      }
      v57 = 0;
      if ( *(_BYTE *)(a1 + 364) )
        goto LABEL_222;
      v27 = 0;
      switch ( v68 )
      {
        case -2147024814:
          *(_DWORD *)v99 = -1072885366;
          if ( *(_QWORD *)(a1 + 1544) || (*(_BYTE *)(a1 + 656) & 8) != 0 )
            *(_BYTE *)(a1 + 364) = 1;
          goto LABEL_222;
        case -2147024726:
          *(_DWORD *)v99 = -1072885336;
          goto LABEL_222;
        case 1064:
          v69 = 0x41E48C8F2A11ED91LL - *(_QWORD *)(a1 + 592);
          if ( *(_QWORD *)(a1 + 592) == 0x41E48C8F2A11ED91LL )
            v69 = 0x1C5603E08683D182LL - *(_QWORD *)(a1 + 600);
          if ( !v69 )
          {
            *(_DWORD *)v99 = -1072885183;
            goto LABEL_222;
          }
          break;
      }
      if ( v68 == -2147201007 )
      {
        if ( RequestContext != &RequestContext
          && (*((_DWORD *)RequestContext + 7) & 0x400) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180184410(*((_QWORD *)RequestContext + 2), 50, &stru_180870240);
        }
        LODWORD(v111) = 1;
        v144 = 1;
        sub_18068E1E0(a1, v103, (unsigned int)&v111, (unsigned int)&v144, 0);
        v68 = *(_DWORD *)v99;
      }
      if ( v68 != -2147024816 )
        goto LABEL_222;
      sub_180115884(v173);
LABEL_182:
      if ( (v58 & 0x1000) == 0 )
        break;
      v27 = v57;
      if ( (v58 & 0x2000) != 0 )
        goto LABEL_223;
      v58 |= 0x2000u;
      if ( (v58 & 4) == 0 )
      {
        v58 |= 4u;
        v133 = 0;
        v134 = 0;
        LOWORD(v133) = v57;
        (*(void (__fastcall **)(__int64, _QWORD, __int64, __int128 *))(*(_QWORD *)(a1 + 8) + 32LL))(
          a1 + 8,
          v103,
          308,
          &v133);
        if ( (_WORD)v133 == 8 )
        {
          v57 = *((_QWORD *)&v133 + 1);
          if ( *((_QWORD *)&v133 + 1) )
          {
            sub_18000EF70(&v130);
            v130 = v57;
            v132 = v132 & 0xFF8F | 0x40;
            v57 = 0;
            LOWORD(v133) = 0;
          }
        }
        sub_1800178B0(&v133);
      }
      if ( v130 && *(_WORD *)v130 != (_WORD)v57 )
      {
        sub_18008D3A8(&lpString2, L"%s.%s", v130, v55);
        v71 = lpString2;
        v70 = lpString2;
        goto LABEL_193;
      }
      if ( (*(_DWORD *)(a1 + 656) & 0x1000) == 0 )
      {
        v59 = 1;
        goto LABEL_216;
      }
      v58 &= ~0x1000u;
LABEL_219:
      v59 = 1;
    }
    v58 |= 0x1000u;
    v70 = v56;
    v71 = lpString2;
LABEL_193:
    v106 = v70;
    v72 = (*v107)[12](v107, (__int64 *)v70, &v105);
    *(_DWORD *)v99 = v72;
    if ( v72 == -2147023729
      || v72 == -2147024775
      || v72 == -2147024875
      || (v59 = 1, (unsigned int)(v72 + 2147014843) <= 1)
      || v72 == -2147201023
      || v72 == -2147024865
      || v72 == -2147467260
      || v72 == -2144731130 )
    {
      *(_DWORD *)v99 = -1072885383;
      *(_BYTE *)(a1 + 364) = 1;
      *(_BYTE *)(a1 + 1696) = 1;
      v27 = 0;
LABEL_223:
      if ( *(int *)v99 >= 0 )
      {
        v77 = v110;
        goto LABEL_225;
      }
LABEL_257:
      v78 = v106;
      goto LABEL_258;
    }
    if ( v105 )
      break;
    v57 = 0;
    if ( v60 )
    {
      v27 = 0;
      v78 = v106;
      if ( *(int *)v99 >= 0 )
        *(_DWORD *)v99 = -2147418113;
      goto LABEL_258;
    }
    if ( (v58 & 0x3000) != 0x1000 )
LABEL_216:
      v60 = 1;
  }
  *(_DWORD *)v99 = (*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v105 + 64LL))(v105, v121, &v121[4]);
  if ( *(_DWORD *)v99 )
    goto LABEL_211;
  v73 = v120;
  if ( v120 == -1 )
  {
    sub_18003E3C0(&v176, *(_QWORD *)(a1 + 176));
    v74 = *(_DWORD *)(sub_1802FFAD4(a1 + 912, v103) + 8);
    sub_180027DB0(&v176);
    if ( *(_BYTE *)(a1 + 1848) || (v74 & 0x10) == 0 )
    {
      v76 = a5;
    }
    else
    {
      sub_1801232BC(v75, (const WCHAR *)v123, a5, &v120, &v104);
      v104 = *(unsigned int *)(a1 + 1712)
           + v104
           - 1
           - (*(unsigned int *)(a1 + 1712) + v104 - 1) % *(unsigned int *)(a1 + 1712);
      v76 = v120;
    }
    v73 = v76
        + *(unsigned int *)(a1 + 1712)
        - 1LL
        - (v76 + *(unsigned int *)(a1 + 1712) - 1LL) % *(unsigned int *)(a1 + 1712);
    v120 = v73;
    v70 = v106;
  }
  if ( *(_QWORD *)v121 != v73 && *(_QWORD *)v121 != v104 )
  {
LABEL_211:
    sub_18008EBDC(&v105);
    if ( v70 == v71 )
    {
      *(_DWORD *)v99 = -1072885361;
    }
    else
    {
      if ( (unsigned __int16)v109 < 0x63u )
      {
        LODWORD(v96) = (unsigned __int16)++v109;
        sub_18008D3A8(&lpString1, L"%.*s(%hu).%s", *(unsigned __int16 *)(a1 + 1710), v157[0], v96, v55);
        v56 = lpString1;
        sub_180646C20(lpString1);
        v57 = 0;
        v60 = 0;
        v58 = 0x2000;
        goto LABEL_219;
      }
      *(_DWORD *)v99 = -1072885368;
    }
    v27 = 0;
    goto LABEL_257;
  }
  if ( RequestContext != &RequestContext
    && (*((_DWORD *)RequestContext + 7) & 0x400) != 0
    && *((_BYTE *)RequestContext + 25) >= 4u )
  {
    sub_1805684AC(*((_QWORD *)RequestContext + 2), v114, (__int64)v70, v121[0]);
  }
  *(_DWORD *)v99 = 2;
  v77 = 2;
  v110 = 2;
  v27 = 0;
LABEL_225:
  v148 = 0;
  v149 = 0;
  v150 = 4;
  *(_QWORD *)&v113 = 0;
  DWORD2(v113) = 0;
  WORD6(v113) = 4;
  v78 = v106;
  *(_DWORD *)v99 = sub_1806A4F10(a1, v114, (_DWORD)v106, v105, (__int64)&v148, (__int64)&v113, (__int64)v145);
  v79 = v113;
  if ( *(int *)v99 >= 0 && v77 == 2 )
  {
    sub_180015184(v157, v113);
    v80 = v103;
    *(_DWORD *)v99 = sub_18069EE8C(a1, v157, v103);
    sub_18000EF70(v157);
  }
  else
  {
    v80 = v103;
  }
  if ( *(int *)v99 >= 0 )
  {
    if ( !v77 )
    {
      sub_1806A8C18(a1, v105, v119[0], v148, v79);
      sub_18003E3C0(&v176, *(_QWORD *)(a1 + 176));
      v88 = *(_DWORD *)(sub_1802FFAD4(a1 + 912, v80) + 8);
      sub_180027DB0(&v176);
      v89 = v88 & 0x10;
      v90 = sub_18062DD3C(lpWideCharStr);
      sub_18062DCF0(&off_1808D6480, v90, v89, v117);
      ((void (__fastcall *)(__int64 (__fastcall ***)(), const wchar_t *, __int64))off_1808D6480[9])(
        &off_1808D6480,
        L"SyncFileTransferCount",
        1);
      if ( v89 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(), const wchar_t *, __int64))off_1808D6480[9])(
          &off_1808D6480,
          L"SyncDRMFileTransferCount",
          1);
      ++*(_DWORD *)(a1 + 1036);
      if ( v89 )
        ++*(_DWORD *)(a1 + 1040);
    }
    if ( *(int *)v99 >= 0 && v118 && (*(_BYTE *)(a1 + 656) & 2) != 0 )
      sub_1806AB448(a1, v80, v105);
  }
  *(_DWORD *)(a1 + 1448) = 100;
  sub_18000EF70(&v113);
  sub_18000EF70(&v148);
LABEL_258:
  sub_1800178B0(v167);
LABEL_277:
  VariantClear(&pvarg);
  if ( v27 )
  {
    sub_180011028((__int64)&v114, v78, -1);
    v104 = 0;
    sub_18010194C(&v114, &v104);
    if ( v104 )
    {
      sub_18003E3C0(&v176, *(_QWORD *)(a1 + 352));
      if ( (int)sub_1801AC808(a1 + 1768, &v104) < 0 )
        sub_18000CB40(&v104);
      sub_180027DB0(&v176);
    }
  }
  else if ( v100 )
  {
    sub_1806A0EF0(a1, v114, v91, v101[0]);
  }
LABEL_282:
  v21 = 5;
LABEL_286:
  if ( !*(_DWORD *)v99 )
    *(_DWORD *)v99 = v110;
  if ( RequestContext != &RequestContext && (*((_DWORD *)RequestContext + 7) & 0x400) != 0 )
  {
    if ( *(int *)v99 >= 0 )
      v21 = 7;
    if ( *((unsigned __int8 *)RequestContext + 25) >= (unsigned int)v21 )
      sub_1806AC354(*((_QWORD *)RequestContext + 2), v123, a5, *v145, v99[0], v114);
  }
  if ( (dword_1808E0D80 & 1) != 0 )
    sub_18018435C(&qword_1808C5BA0, qword_180809C18, v21, 1, &v176);
  sub_18061AD44(L"WMPPERF_PDA_TRANSFER_FILE_END");
  LOBYTE(v92) = 2;
  sub_180187C64(1414681414, qword_180809F18, v93, v92);
  sub_180115C78(v174, *(unsigned int *)v99);
  v94 = *(_DWORD *)v99;
  sub_180115B74(v175);
  sub_18000EF70(&v160);
  sub_18006D200(v170);
  sub_18006D200(v169);
  sub_18000EF70(&lpWideCharStr);
  sub_18000EF70(&v163);
  sub_18000EF70(&v123);
  sub_18000EF70(&lpString2);
  sub_18000EF70(&pszPath);
  sub_18000EF70(&lpString1);
  sub_18000EF70(&v114);
  sub_18000EF70(&v130);
  sub_18000EF70(&v138);
  sub_18000EF70(&v141);
  sub_1800654D0(v112);
  sub_1800654D0(&v105);
  sub_1800654D0(&v146);
  sub_1800654D0(v119);
  sub_1800654D0(&v147);
  sub_1800654D0(&v126);
  sub_180115884(v174);
  return v94;
}

```

## disassembly

```asm
0x180112f30  push    rbp
0x180112f32  push    rbx
0x180112f33  push    rsi
0x180112f34  push    rdi
0x180112f35  push    r12
0x180112f37  push    r13
0x180112f39  push    r14
0x180112f3b  push    r15
0x180112f3d  lea     rbp, [rsp-4B8h]
0x180112f45  sub     rsp, 5B8h
0x180112f4c  mov     rax, cs:__security_cookie
0x180112f53  xor     rax, rsp
0x180112f56  mov     [rbp+4F0h+var_50], rax
0x180112f5d  mov     [rbp+4F0h+var_510], r9d
0x180112f61  mov     r14, r8
0x180112f64  mov     r13d, edx
0x180112f67  mov     [rsp+5F0h+var_580], edx
0x180112f6b  mov     rdi, rcx
0x180112f6e  mov     rax, [rbp+4F0h+arg_28]
0x180112f75  mov     [rbp+4F0h+var_460], rax
0x180112f7c  mov     rbx, [rbp+4F0h+arg_30]
0x180112f83  mov     rsi, [rbp+4F0h+arg_38]
0x180112f8a  xor     eax, eax
0x180112f8c  mov     [rbp+4F0h+var_558], eax
0x180112f8f  mov     dword ptr [rbp+4F0h+var_548], eax
0x180112f92  lea     r15d, [rax+1]
0x180112f96  mov     dword ptr [rsp+5F0h+var_5D0], r15d
0x180112f9b  lea     r12d, [rax+3]
0x180112f9f  mov     r9b, r12b
0x180112fa2  lea     rcx, [rbp+4F0h+var_200]
0x180112fa9  call    sub_18031682C
0x180112fae  nop
0x180112faf  test    byte ptr cs:dword_1808E0D80, r15b
0x180112fb6  jz      short loc_180112FDA
0x180112fb8  lea     rax, [rbp+4F0h+var_70]
0x180112fbf  mov     [rsp+5F0h+var_5D0], rax
0x180112fc4  mov     r9d, r15d
0x180112fc7  lea     rdx, qword_180809C28
0x180112fce  lea     rcx, qword_1808C5BA0
0x180112fd5  call    sub_18018435C
0x180112fda  lea     rcx, aWmpperfPdaTran_0
0x180112fe1  call    sub_18061AD44
0x180112fe6  mov     r9b, r15b
0x180112fe9  lea     rdx, qword_180809F18
0x180112ff0  mov     ecx, 54525346h
0x180112ff5  call    sub_180187C64
0x180112ffa  xor     ecx, ecx
0x180112ffc  mov     dword ptr [rsp+5F0h+var_590], ecx
0x180113000  mov     [rbp+4F0h+var_550], ecx
0x180113003  movups  xmm0, xmmword ptr cs:Buf2.Data1
0x18011300a  movdqu  [rbp+4F0h+Buf2], xmm0
0x180113012  movdqu  [rbp+4F0h+var_270], xmm0
0x18011301a  mov     [rbp+4F0h+var_4D8], rcx
0x18011301e  mov     [rbp+4F0h+var_450], rcx
0x180113025  mov     qword ptr [rbp+4F0h+var_508], rcx
0x180113029  mov     [rbp+4F0h+var_458], rcx
0x180113030  mov     [rbp+4F0h+var_570], rcx
0x180113034  mov     [rbp+4F0h+var_540], rcx
0x180113038  xorps   xmm0, xmm0
0x18011303b  xor     eax, eax
0x18011303d  movups  xmmword ptr [rbp+4F0h+pvarg], xmm0
0x180113044  mov     qword ptr [rbp+4F0h+pvarg+10h], rax
0x18011304b  mov     [rbp+4F0h+var_478], rcx
0x18011304f  mov     [rbp+4F0h+var_470], ecx
0x180113055  lea     eax, [rcx+4]
0x180113058  mov     [rbp+4F0h+var_46C], ax
0x18011305f  mov     [rbp+4F0h+var_488], rcx
0x180113063  mov     [rbp+4F0h+var_480], ecx
0x180113066  mov     [rbp+4F0h+var_47C], ax
0x18011306a  mov     [rbp+4F0h+var_4C0], rcx
0x18011306e  mov     [rbp+4F0h+var_4B8], ecx
0x180113071  mov     [rbp+4F0h+var_4B4], ax
0x180113075  mov     [rbp+4F0h+var_520], rcx
0x180113079  mov     [rbp+4F0h+var_518], ecx
0x18011307c  mov     [rbp+4F0h+var_514], cx
0x180113080  mov     [rbp+4F0h+lpString1], rcx
0x180113084  mov     [rbp+4F0h+var_490], ecx
0x180113087  mov     [rbp+4F0h+var_48C], cx
0x18011308b  mov     [rbp+4F0h+pszPath], rcx
0x180113092  mov     [rbp+4F0h+var_420], ecx
0x180113098  mov     [rbp+4F0h+var_41C], cx
0x18011309f  mov     [rbp+4F0h+lpString2], rcx
0x1801130a3  mov     [rbp+4F0h+var_4C8], ecx
0x1801130a6  mov     [rbp+4F0h+var_4C4], cx
0x1801130aa  mov     [rbp+4F0h+var_4E8], rcx
0x1801130ae  mov     [rbp+4F0h+var_4E0], ecx
0x1801130b1  mov     [rbp+4F0h+var_4DC], cx
0x1801130b5  mov     r15d, ecx
0x1801130b8  mov     [rbp+4F0h+var_3E8], rcx
0x1801130bf  mov     [rbp+4F0h+var_3E0], ecx
0x1801130c5  mov     [rbp+4F0h+var_3DC], cx
0x1801130cc  mov     [rbp+4F0h+var_50C], ecx
0x1801130cf  mov     [rbp+4F0h+var_4F0], ecx
0x1801130d2  mov     [rsp+5F0h+var_588], cx
0x1801130d7  mov     [rbp+4F0h+lpWideCharStr], rcx
0x1801130de  mov     [rbp+4F0h+var_430], ecx
0x1801130e4  mov     [rbp+4F0h+var_42C], cx
0x1801130eb  mov     qword ptr [rbp+4F0h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1801130f2  mov     qword ptr [rbp+4F0h+var_408.dwLowDateTime], rcx
0x1801130f9  lea     rcx, [rbp+4F0h+var_3A0]
0x180113100  call    sub_180060630
0x180113105  nop
0x180113106  lea     rcx, [rbp+4F0h+var_310]
0x18011310d  call    sub_180060630
0x180113112  nop
0x180113113  xor     eax, eax
0x180113115  mov     [rbp+4F0h+var_3F8], rax
0x18011311c  mov     [rbp+4F0h+var_3F0], eax
0x180113122  lea     ecx, [rax+4]
0x180113125  mov     [rbp+4F0h+var_3EC], cx
0x18011312c  mov     [rdi+5A8h], eax
0x180113132  lea     rcx, [rbp+4F0h+pvarg]; pvarg
0x180113139  call    cs:VariantInit
0x180113140  nop     dword ptr [rax+rax+00h]
0x180113145  lea     rcx, RequestContext
0x18011314c  mov     rax, cs:RequestContext
0x180113153  cmp     rax, rcx
0x180113156  jz      short loc_1801131AA
0x180113158  test    dword ptr [rax+1Ch], 400h
0x18011315f  jz      short loc_1801131AA
0x180113161  cmp     byte ptr [rax+19h], 7
0x180113165  jb      short loc_1801131AA
0x180113167  lea     rcx, [rdi+390h]
0x18011316e  mov     edx, r13d
0x180113171  call    sub_1802FFAD4
0x180113176  movzx   ecx, word ptr [rax+8]
0x18011317a  mov     word ptr [rsp+5F0h+var_5C0], cx
0x18011317f  mov     rax, [rbp+4F0h+var_460]
0x180113186  mov     qword ptr [rsp+5F0h+var_5C8], rax
0x18011318b  mov     rax, [rbp+4F0h+arg_20]
0x180113192  mov     [rsp+5F0h+var_5D0], rax
0x180113197  mov     r9d, r13d
0x18011319a  mov     rcx, cs:RequestContext
0x1801131a1  mov     rcx, [rcx+10h]
0x1801131a5  call    sub_1806AC280
0x1801131aa  lea     r9, [rdi+760h]
0x1801131b1  lea     r8, [rsp+5F0h+var_590]
0x1801131b6  lea     rdx, aCsyncengineTra_0
0x1801131bd  lea     rcx, [rbp+4F0h+var_1A0]
0x1801131c4  call    sub_1801152D8
0x1801131c9  nop
0x1801131ca  lea     r8, [rbp+4F0h+Buf2]
0x1801131d1  mov     edx, r13d
0x1801131d4  mov     rcx, rdi
0x1801131d7  call    sub_180112C24
0x1801131dc  mov     r8d, 10h; Size
0x1801131e2  lea     rdx, [rbp+4F0h+Buf2]; Buf2
0x1801131e9  lea     rcx, stru_180801348; Buf1
0x1801131f0  call    memcmp
0x1801131f5  test    eax, eax
0x1801131f7  jnz     short loc_180113202
0x1801131f9  mov     [rbp+4F0h+var_50C], 1
0x180113200  jmp     short loc_180113226
0x180113202  mov     r8d, 10h; Size
0x180113208  lea     rdx, [rbp+4F0h+Buf2]; Buf2
0x18011320f  lea     rcx, xmmword_180801338; Buf1
0x180113216  call    memcmp
0x18011321b  test    eax, eax
0x18011321d  jnz     short loc_180113226
0x18011321f  mov     [rbp+4F0h+var_4F0], 1
0x180113226  lea     rcx, [rdi+8]
0x18011322a  mov     rax, [rcx]
0x18011322d  lea     r9, [rbp+4F0h+pvarg]
0x180113234  mov     r8d, 108h
0x18011323a  mov     edx, r13d
0x18011323d  mov     rax, [rax+20h]
0x180113241  call    cs:__guard_dispatch_icall_fptr
0x180113247  mov     edx, 8
0x18011324c  test    eax, eax
0x18011324e  js      short loc_18011327C
0x180113250  cmp     dx, word ptr [rbp+4F0h+pvarg]
0x180113257  jnz     short loc_18011327C
0x180113259  mov     rdx, qword ptr [rbp+4F0h+pvarg+8]
0x180113260  test    rdx, rdx
0x180113263  jz      short loc_18011327C
0x180113265  or      r8d, 0FFFFFFFFh
0x180113269  lea     rcx, [rbp+4F0h+var_3E8]
0x180113270  call    sub_180007B30
0x180113275  mov     r15, [rbp+4F0h+var_3E8]
0x18011327c  lea     rcx, [rbp+4F0h+pvarg]; pvarg
0x180113283  call    cs:VariantClear
0x18011328a  nop     dword ptr [rax+rax+00h]
0x18011328f  mov     r8d, 5
0x180113295  cmp     dword ptr [rsp+5F0h+var_590], 0
0x18011329a  jl      loc_180114989
0x1801132a0  mov     rcx, [rdi+5C8h]
0x1801132a7  mov     rax, [rcx]
0x1801132aa  lea     rdx, [rbp+4F0h+var_508]
0x1801132ae  mov     rax, [rax+88h]
0x1801132b5  call    cs:__guard_dispatch_icall_fptr
0x1801132bb  mov     dword ptr [rsp+5F0h+var_590], eax
0x1801132bf  test    eax, eax
0x1801132c1  js      loc_180114983
0x1801132c7  movaps  xmm0, [rbp+4F0h+Buf2]
0x1801132ce  movdqa  [rbp+4F0h+var_530], xmm0
0x1801132d3  mov     [rsp+5F0h+var_5A8], rsi; __int64
0x1801132d8  mov     [rsp+5F0h+var_5B0], rbx; __int64
0x1801132dd  lea     rax, [rbp+4F0h+var_4C0]
0x1801132e1  mov     qword ptr [rsp+5F0h+var_5B8], rax; __int64
0x1801132e6  lea     rax, [rbp+4F0h+var_488]
0x1801132ea  mov     qword ptr [rsp+5F0h+var_5C0], rax; __int64
0x1801132ef  lea     rax, [rbp+4F0h+var_478]
0x1801132f3  mov     qword ptr [rsp+5F0h+var_5C8], rax; __int64
0x1801132f8  lea     rax, [rbp+4F0h+var_530]
0x1801132fc  mov     [rsp+5F0h+var_5D0], rax; Buf2
0x180113301  mov     r9, r15; int
0x180113304  mov     r8d, r13d; int
0x180113307  mov     rdx, qword ptr [rbp+4F0h+var_508]; int
0x18011330b  mov     rcx, rdi; int
0x18011330e  call    sub_1806A3228
0x180113313  mov     dword ptr [rsp+5F0h+var_590], 0
0x18011331b  mov     rdx, [rdi+0B0h]
0x180113322  lea     rcx, [rbp+4F0h+var_530]
0x180113326  call    sub_18003E3C0
0x18011332b  nop
0x18011332c  lea     rsi, [rdi+390h]
0x180113333  mov     edx, r13d
0x180113336  mov     rcx, rsi
0x180113339  call    sub_1802FFAD4
0x18011333e  mov     ebx, [rax+8]
0x180113341  lea     rcx, [rbp+4F0h+var_530]
0x180113345  call    sub_180027DB0
0x18011334a  test    bl, 1
0x18011334d  jz      loc_1801135EC
0x180113353  mov     [rsp+5F0h+var_584], 0FFFFFFFFh
0x18011335b  xor     ebx, ebx
0x18011335d  mov     [rbp+4F0h+var_568], rbx
0x180113361  mov     dword ptr [rsp+5F0h+var_5D0], ebx
0x180113365  lea     r9, [rbp+4F0h+var_568]
0x180113369  lea     r8, [rsp+5F0h+var_584]
0x18011336e  mov     edx, r13d
0x180113371  mov     rcx, rdi
0x180113374  call    sub_1806B0844
0x180113379  mov     dword ptr [rsp+5F0h+var_590], eax
0x18011337d  mov     rcx, [rbp+4F0h+var_568]
0x180113381  test    rcx, rcx
0x180113384  jz      loc_1801135E3
0x18011338a  mov     edx, [rsp+5F0h+var_584]
0x18011338e  cmp     edx, 0FFFFFFFFh
0x180113391  jz      loc_1801135E3
0x180113397  xorps   xmm0, xmm0
0x18011339a  xor     eax, eax
0x18011339c  movups  [rbp+4F0h+var_70], xmm0
0x1801133a3  mov     [rbp+4F0h+var_60], rax
0x1801133aa  mov     word ptr [rbp+4F0h+var_70], bx
0x1801133b1  mov     rax, [rcx]
0x1801133b4  lea     r9, [rbp+4F0h+var_70]
0x1801133bb  mov     r8d, 108h
0x1801133c1  mov     rax, [rax+20h]
0x1801133c5  call    cs:__guard_dispatch_icall_fptr
0x1801133cb  mov     dword ptr [rsp+5F0h+var_590], eax
0x1801133cf  lea     eax, [rbx+8]
0x1801133d2  cmp     word ptr [rbp+4F0h+var_70], ax
0x1801133d9  jnz     loc_1801135D6
0x1801133df  mov     rdx, qword ptr [rbp+4F0h+var_70+8]
0x1801133e6  test    rdx, rdx
0x1801133e9  jz      loc_1801135D6
0x1801133ef  cmp     [rdx], bx
0x1801133f2  jz      loc_1801135D6
0x1801133f8  lea     r8, [rbp+4F0h+var_570]
0x1801133fc  mov     rcx, rdi
0x1801133ff  call    sub_1806A52C4
0x180113404  cmp     [rbp+4F0h+var_570], rbx
0x180113408  jz      loc_1801135D6
0x18011340e  mov     rdx, [rdi+0B0h]
0x180113415  lea     rcx, [rbp+4F0h+var_530]
0x180113419  call    sub_18003E3C0
0x18011341e  nop
0x18011341f  mov     edx, r13d
0x180113422  mov     rcx, rsi
0x180113425  call    sub_1802FFAD4
0x18011342a  lea     rcx, [rax+10h]
0x18011342e  mov     rdx, [rbp+4F0h+var_570]
0x180113432  call    sub_180056DE0
0x180113437  nop
0x180113438  lea     rcx, [rbp+4F0h+var_530]
0x18011343c  call    sub_180027DB0
0x180113441  mov     rcx, cs:RequestContext
0x180113448  lea     rdx, RequestContext
0x18011344f  cmp     rcx, rdx
0x180113452  jz      short loc_180113479
0x180113454  test    dword ptr [rcx+1Ch], 400h
0x18011345b  jz      short loc_180113479
0x18011345d  cmp     byte ptr [rcx+19h], 4
0x180113461  jb      short loc_180113479
0x180113463  lea     edx, [rbx+2Fh]
0x180113466  mov     r9d, r13d
0x180113469  lea     r8, stru_180870240
0x180113470  mov     rcx, [rcx+10h]
0x180113474  call    sub_180121AD0
0x180113479  xor     esi, esi
0x18011347b  mov     [rbp+4F0h+var_560], rsi
0x18011347f  mov     rcx, [rbp+4F0h+var_570]
0x180113483  mov     rax, [rcx]
0x180113486  lea     r8, [rbp+4F0h+var_560]
0x18011348a  lea     rdx, qword_180867FA0
0x180113491  mov     rax, [rax]
0x180113494  call    cs:__guard_dispatch_icall_fptr
0x18011349a  mov     dword ptr [rsp+5F0h+var_590], eax
0x18011349e  test    eax, eax
  ... truncated ...
```
