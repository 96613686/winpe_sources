# ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)

- ea: `0x1800232b0`
- end: `0x180024638`
- name: `?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z`
- size: `5000`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d9b0`

## callees

- `0x1800033d0`
- `0x180003c9c`
- `0x180003f7c`
- `0x180004090`
- `0x1800050d0`
- `0x180005284`
- `0x1800053bc`
- `0x1800053e8`
- `0x180006314`
- `0x180007994`
- `0x180008c66`
- `0x18000a960`
- `0x18000aa0c`
- `0x18000cfc4`
- `0x180010d4c`
- `0x18001ba20`
- `0x18001c21c`
- `0x18001d1ac`
- `0x18001d298`
- `0x18001d320`
- `0x18001ea5c`
- `0x18002209c`
- `0x1800223bc`
- `0x180022640`
- `0x1800226b0`
- `0x1800232b0`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180023e9b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180023ee9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180023e9b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180023ee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ValidationXmlHandler::ProcessValue(__int64 a1, int *a2, int a3, __int64 a4)
{
  _QWORD *v8; // rdi
  __int64 v9; // rax
  const wchar_t *v10; // r15
  __int64 Entry; // rax
  unsigned int v12; // r15d
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rcx
  _bstr_t *v20; // rbx
  _bstr_t *v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // rdi
  _bstr_t *v24; // rbx
  ATL::CComBSTR *v25; // rbx
  __int64 v26; // rdi
  _bstr_t *v27; // rbx
  unsigned __int16 *v28; // rax
  __int64 v29; // rdi
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  unsigned int v34; // eax
  unsigned int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // ecx
  unsigned int v39; // eax
  __int64 v40; // rdi
  __int64 v41; // rdi
  __int64 v42; // rdi
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  unsigned int v47; // eax
  _QWORD *v48; // rdx
  JobBucket *v49; // rbx
  int v50; // edi
  char v51; // dl
  __int64 v52; // rcx
  int v53; // eax
  unsigned int v54; // eax
  int v55; // ebx
  int v56; // ebx
  int v57; // ebx
  int v58; // ebx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // r8
  unsigned int v64; // eax
  __int16 v65; // cx
  bool v66; // cc
  __int64 v67; // rcx
  __int64 v68; // rax
  const WCHAR **v69; // rdx
  const WCHAR *v70; // rdx
  __int64 v72; // rax
  const WCHAR ***v73; // rbx
  __int64 v74; // rax
  __int64 v75; // rax
  const WCHAR *v76; // rcx
  const WCHAR *v77; // rcx
  volatile signed __int32 *v78; // rax
  __int64 v79; // rdx
  char v80; // bl
  int v81; // eax
  bool v82; // zf
  int v83; // ecx
  int v84; // ecx
  int v85; // ecx
  unsigned int v86; // ebx
  int v87; // eax
  int v88; // eax
  int v89; // ebx
  int v90; // ebx
  int v91; // ebx
  int v92; // ebx
  __int64 v93; // rdx
  int v94; // eax
  unsigned int v95; // eax
  int v96; // eax
  int v97; // eax
  int v98; // eax
  int v99; // ebx
  int v100; // ebx
  int v101; // ebx
  int v102; // ebx
  int v103; // eax
  int v104; // eax
  int v105; // eax
  int v106; // eax
  int v107; // eax
  JobBucket *v108; // rbx
  int v109; // edi
  int v110; // ebx
  int v111; // ebx
  int v112; // ebx
  int v113; // ebx
  int v114; // eax
  int v115; // eax
  JobBucket *v116; // rbx
  int v117; // edi
  JobBucket *v118; // rbx
  int v119; // edi
  int v120; // eax
  JobBucket *v121; // rbx
  GUID v122; // xmm6
  __int64 v123; // r8
  __int64 v124; // rdi
  int v125; // r14d
  JobBucket *v126; // rbx
  int v127; // edi
  JobBucket *v128; // rbx
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 v131; // rax
  const unsigned __int16 ***v132; // r12
  unsigned int v133; // eax
  XmlParserTempString *v134; // r13
  unsigned __int64 v135; // r8
  const unsigned __int16 *v136; // rdx
  __int64 v137; // rax
  __int64 v138; // rax
  bool v139; // al
  _DWORD *v140; // rcx
  int v141; // eax
  int v142; // ebx
  int v143; // ebx
  int v144; // ebx
  int v145; // ebx
  int v146; // eax
  _QWORD *v147; // rax
  const WCHAR *v148; // rcx
  int v149; // ebx
  int v150; // ebx
  int v151; // ebx
  int v152; // ebx
  int v153; // eax
  JobBucket *v154; // rbx
  int v155; // edi
  unsigned __int16 *v156; // r8
  JobBucket *v157; // rbx
  __int64 v158; // xmm6_8
  int v159; // edi
  unsigned __int16 v160; // si
  __int64 v161; // rax
  unsigned __int16 *v162; // r8
  JobBucket *v163; // rbx
  __int64 v164; // xmm6_8
  int v165; // edi
  unsigned __int16 v166; // si
  __int64 v167; // rax
  const WCHAR **v168; // rax
  const WCHAR *v169; // rcx
  JobBucket *v170; // rbx
  __int64 v171; // rdi
  int v172; // ebx
  int v173; // ebx
  int v174; // ebx
  JobBucket *v175; // rbx
  const unsigned __int16 ***Copy; // rax
  const unsigned __int16 *v177; // rdx
  __int64 v178; // rbx
  _QWORD *v179; // rax
  __int64 **v180; // rax
  __int64 v181; // rdx
  void *v182; // rax
  _QWORD v183[2]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v184; // [rsp+48h] [rbp-81h] BYREF
  GUID iid; // [rsp+58h] [rbp-71h] BYREF
  OLECHAR sz[40]; // [rsp+68h] [rbp-61h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v9 = *(_QWORD *)(a4 + 48);
    if ( v9 )
      v10 = *(const wchar_t **)(v9 + 8);
    else
      v10 = L"null";
    Entry = Schema::GetEntry(a2, (unsigned int)a3);
    WPP_SF_SS(
      v8[2],
      11,
      (unsigned int)WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids,
      *(_QWORD *)(Entry + 8),
      (__int64)v10);
  }
  v12 = 0;
  iid = 0;
  if ( a3 > 68 )
  {
    if ( a3 > 101 )
    {
      if ( a3 > 133 )
      {
        if ( a3 > 142 )
        {
          v172 = a3 - 143;
          if ( !v172 )
          {
            v182 = operator new[](*(unsigned int *)(a4 + 64));
            *(_QWORD *)(a1 + 352) = v182;
            if ( v182 )
            {
              memcpy_0(v182, *(const void **)(a4 + 56), *(unsigned int *)(a4 + 64));
              *(_DWORD *)(a1 + 344) = *(_DWORD *)(a4 + 64);
            }
            else
            {
              return (unsigned int)-2147024882;
            }
            return v12;
          }
          v173 = v172 - 1;
          if ( !v173 )
          {
            *(_DWORD *)(a1 + 340) = *(_DWORD *)(a4 + 32);
            return v12;
          }
          v174 = v173 - 1;
          if ( v174 )
          {
            if ( v174 != 2 )
              return v12;
            v175 = *(JobBucket **)(a1 + 40);
            Copy = (const unsigned __int16 ***)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
            if ( *Copy )
              v177 = **Copy;
            else
              v177 = 0;
            JobBucket::AddCapability(v175, v177);
            goto LABEL_64;
          }
          v178 = *(_QWORD *)(a1 + 40);
          v179 = *(_QWORD **)(v178 + 176);
          if ( !v179 || !*v179 )
          {
            v180 = (__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
            if ( *v180 )
              v181 = **v180;
            else
              v181 = 0;
            _bstr_t::operator=(v178 + 176, v181);
            goto LABEL_64;
          }
          return 2147750678LL;
        }
        if ( a3 == 142 )
        {
          if ( *(_DWORD *)(a4 + 64) == 8 )
          {
            *(_QWORD *)(a1 + 332) = **(_QWORD **)(a4 + 56);
            return v12;
          }
        }
        else
        {
          v149 = a3 - 135;
          if ( !v149 )
          {
            if ( !_bstr_t::length((_bstr_t *)(a1 + 72))
              || ((v168 = *(const WCHAR ***)(a1 + 72)) == 0 ? (v169 = 0) : (v169 = *v168),
                  User::SupportsTaskHardening(v169)) )
            {
              v170 = *(JobBucket **)(a1 + 40);
              v171 = *(_QWORD *)(a4 + 32);
              JobBucket::InitOptionalSettings(v170);
              *(_QWORD *)(*((_QWORD *)v170 + 26) + 48LL) |= v171;
              return v12;
            }
            return 2147750678LL;
          }
          v150 = v149 - 2;
          if ( v150 )
          {
            v151 = v150 - 1;
            if ( v151 )
            {
              v152 = v151 - 1;
              if ( !v152 )
              {
                v154 = *(JobBucket **)(a1 + 40);
                v155 = *(unsigned __int8 *)(a4 + 32);
                JobBucket::InitOptionalSettings(v154);
                *(_DWORD *)(*((_QWORD *)v154 + 26) + 84LL) = v155;
                return v12;
              }
              if ( v152 != 1 )
                return v12;
              v52 = *(_QWORD *)(a1 + 40);
              v153 = *(_DWORD *)(v52 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v54 = v153 | 0x20000000;
              else
                v54 = v153 & 0xDFFFFFFF;
              goto LABEL_185;
            }
            if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)(a4 + 16))
              && (v156[1] + 12LL * *v156
               || *(unsigned __int16 *)(a4 + 28)
                + 60
                * (*(unsigned __int16 *)(a4 + 26)
                 + 60
                 * (*(unsigned __int16 *)(a4 + 24)
                  + 24 * (*(unsigned __int16 *)(a4 + 22) + 7 * (unsigned int)*(unsigned __int16 *)(a4 + 20)))) >= 0x15180) )
            {
              v157 = *(JobBucket **)(a1 + 40);
              v158 = *(_QWORD *)v156;
              v159 = *((_DWORD *)v156 + 2);
              v160 = v156[6];
              JobBucket::InitOptionalSettings(v157);
              v161 = *((_QWORD *)v157 + 26);
              *(_QWORD *)(v161 + 70) = v158;
              *(_DWORD *)(v161 + 78) = v159;
              *(_WORD *)(v161 + 82) = v160;
              return v12;
            }
          }
          else if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)(a4 + 16))
                 && (v162[1] + 12LL * *v162
                  || *(unsigned __int16 *)(a4 + 28)
                   + 60
                   * (*(unsigned __int16 *)(a4 + 26)
                    + 60
                    * (*(unsigned __int16 *)(a4 + 24)
                     + 24 * (*(unsigned __int16 *)(a4 + 22) + 7 * (unsigned int)*(unsigned __int16 *)(a4 + 20)))) >= 0x15180) )
          {
            v163 = *(JobBucket **)(a1 + 40);
            v164 = *(_QWORD *)v162;
            v165 = *((_DWORD *)v162 + 2);
            v166 = v162[6];
            JobBucket::InitOptionalSettings(v163);
            v167 = *((_QWORD *)v163 + 26);
            *(_QWORD *)(v167 + 56) = v164;
            *(_DWORD *)(v167 + 64) = v165;
            *(_WORD *)(v167 + 68) = v166;
            return v12;
          }
        }
        return (unsigned int)-2147216616;
      }
      if ( a3 == 133 )
      {
        if ( _bstr_t::length((_bstr_t *)(a1 + 72)) )
        {
          v147 = *(_QWORD **)(a1 + 72);
          v148 = v147 ? (const WCHAR *)*v147 : 0LL;
          if ( !User::SupportsTaskHardening(v148) )
            return 2147750678LL;
        }
LABEL_181:
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= *(_DWORD *)(a4 + 32);
        return v12;
      }
      if ( a3 > 112 )
      {
        v142 = a3 - 116;
        if ( !v142 )
        {
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 448;
          goto LABEL_62;
        }
        v143 = v142 - 1;
        if ( !v143 )
        {
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 456;
          goto LABEL_62;
        }
        v144 = v143 - 1;
        if ( !v144 )
        {
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 464;
          goto LABEL_62;
        }
        v145 = v144 - 2;
        if ( !v145 )
        {
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 472;
          goto LABEL_62;
        }
        if ( v145 != 12 )
          return v12;
        v52 = *(_QWORD *)(a1 + 40);
        v146 = *(_DWORD *)(v52 + 16);
        if ( *(_BYTE *)(a4 + 32) )
          v54 = v146 | 0x4000000;
        else
          v54 = v146 & 0xFBFFFFFF;
        goto LABEL_185;
      }
      switch ( a3 )
      {
        case 'p':
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 88;
          goto LABEL_62;
        case 'h':
          v140 = *(_DWORD **)(a4 + 48);
          v141 = 0;
          if ( (unsigned int)(*v140 - 1) > 0x103 )
            v141 = -2147216616;
          v12 = v141;
          v36 = XmlParserTempString::GetCopy(v140, v183);
          v37 = a1 + 480;
          goto LABEL_62;
        case 'j':
          if ( (unsigned int)(**(_DWORD **)(a4 + 48) - 1) <= 0x103 )
            return v12;
          return (unsigned int)-2147216616;
        case 'm':
          XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          if ( *(_DWORD *)(a1 + 112) )
            _bstr_t::operator=(a1 + 120, v183);
          v139 = ValidationXmlHandler::CheckId((ValidationXmlHandler *)a1, (const struct _bstr_t *)v183);
          v21 = (_bstr_t *)v183;
          if ( v139 )
            goto LABEL_23;
          goto LABEL_272;
      }
      if ( a3 != 110 )
      {
        if ( a3 != 111 )
          return v12;
        if ( (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) & 0xF4000) == 0 && !_bstr_t::length((_bstr_t *)(a1 + 72)) )
        {
          v129 = *(_QWORD *)(a1 + 40);
          if ( (*(_DWORD *)(v129 + 16) & 0x18000000) == 0 )
          {
            v130 = *(_QWORD *)(v129 + 208);
            if ( !v130 || !*(_QWORD *)(v130 + 48) )
            {
              v131 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
              _bstr_t::operator=(a1 + 72, v131);
              _bstr_t::~_bstr_t((_bstr_t *)v183);
              v52 = *(_QWORD *)(a1 + 40);
              v54 = *(_DWORD *)(v52 + 16) & 0xFFF03FFF | 0x8000;
              goto LABEL_185;
            }
          }
        }
        return 2147750678LL;
      }
    }
    else
    {
      if ( a3 == 101 )
        goto LABEL_181;
      if ( a3 <= 83 )
      {
        if ( a3 == 83 )
        {
          v108 = *(JobBucket **)(a1 + 40);
          v109 = *(unsigned __int16 *)(a4 + 32);
          JobBucket::InitOptionalSettings(v108);
          *(_DWORD *)(*((_QWORD *)v108 + 26) + 16LL) = v109;
          return v12;
        }
        if ( a3 > 76 )
        {
          v99 = a3 - 77;
          if ( v99 )
          {
            v100 = v99 - 1;
            if ( v100 )
            {
              v101 = v100 - 1;
              if ( v101 )
              {
                v102 = v101 - 2;
                if ( v102 )
                {
                  if ( v102 == 1 )
                  {
                    if ( *a2 < 65538 )
                    {
                      v103 = 0;
                      if ( *(_DWORD *)(a4 + 32) )
                        v103 = -2147216616;
                      v12 = v103;
                    }
                    *(_DWORD *)(a1 + 432) = *(_DWORD *)(a4 + 32);
                  }
                  return v12;
                }
                v52 = *(_QWORD *)(a1 + 40);
                v104 = *(_DWORD *)(v52 + 16);
                if ( *(_BYTE *)(a4 + 32) )
                  v54 = v104 | 0x800000;
                else
                  v54 = v104 & 0xFF7FFFFF;
              }
              else
              {
                v52 = *(_QWORD *)(a1 + 40);
                v105 = *(_DWORD *)(v52 + 16);
                if ( *(_BYTE *)(a4 + 32) )
                  v54 = v105 | 0x200;
                else
                  v54 = v105 & 0xFFFFFDFF;
              }
            }
            else
            {
              v52 = *(_QWORD *)(a1 + 40);
              v106 = *(_DWORD *)(v52 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v54 = v106 | 0x80;
              else
                v54 = v106 & 0xFFFFFF7F;
            }
          }
          else
          {
            v52 = *(_QWORD *)(a1 + 40);
            v107 = *(_DWORD *)(v52 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v54 = v107 | 0x40;
            else
              v54 = v107 & 0xFFFFFFBF;
          }
          goto LABEL_185;
        }
        if ( a3 == 76 )
        {
          v52 = *(_QWORD *)(a1 + 40);
          v98 = *(_DWORD *)(v52 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v54 = v98 | 0x40000000;
          else
            v54 = v98 & 0xBFFFFFFF;
          goto LABEL_185;
        }
        v89 = a3 - 70;
        if ( !v89 )
        {
          LOWORD(v81) = *(_WORD *)(a1 + 274) | (1 << ((*(_BYTE *)(a4 + 32) - 1) & 0xF));
          goto LABEL_187;
        }
        v90 = v89 - 2;
        if ( !v90 )
        {
          v52 = *(_QWORD *)(a1 + 40);
          v97 = *(_DWORD *)(v52 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v54 = v97 | 0x100;
          else
            v54 = v97 & 0xFFFFFEFF;
          goto LABEL_185;
        }
        v91 = v90 - 1;
        if ( v91 )
        {
          v92 = v91 - 1;
          if ( v92 )
          {
            if ( v92 == 1 )
            {
              v93 = *(_QWORD *)(a1 + 40);
              v94 = *(_DWORD *)(v93 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v95 = v94 | 0x20;
              else
                v95 = v94 & 0xFFFFFFDF;
              *(_DWORD *)(v93 + 16) = v95;
            }
            return v12;
          }
          v52 = *(_QWORD *)(a1 + 40);
          v96 = *(_DWORD *)(v52 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v54 = v96 | 0x10;
          else
            v54 = v96 & 0xFFFFFFEF;
          goto LABEL_185;
        }
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) &= 0xFFFFC3FF;
        goto LABEL_181;
      }
      if ( a3 <= 92 )
      {
        if ( a3 == 92 )
        {
          v12 = IIDFromString(*(LPCOLESTR *)(*(_QWORD *)(a4 + 48) + 8LL), &iid);
          if ( (v12 & 0x80000000) == 0
            || **(_WORD **)(*(_QWORD *)(a4 + 48) + 8LL) != 123
            && (v12 = StringCchPrintfW(sz, 0x28u, L"{%s}"), (v12 & 0x80000000) == 0)
            && (v12 = IIDFromString(sz, &iid), (v12 & 0x80000000) == 0) )
          {
            v121 = *(JobBucket **)(a1 + 40);
            v122 = iid;
            JobBucket::InitOptionalSettings(v121);
            *(GUID *)(*((_QWORD *)v121 + 26) + 28LL) = v122;
          }
          return v12;
        }
        v110 = a3 - 84;
        if ( v110 )
        {
          v111 = v110 - 2;
          if ( !v111 )
          {
            v118 = *(JobBucket **)(a1 + 40);
            v119 = *(_DWORD *)(a4 + 32);
            JobBucket::InitOptionalSettings(v118);
            **((_DWORD **)v118 + 26) = v119;
            return v12;
          }
          v112 = v111 - 1;
          if ( !v112 )
          {
            v116 = *(JobBucket **)(a1 + 40);
            v117 = *(_DWORD *)(a4 + 32);
            JobBucket::InitOptionalSettings(v116);
            *(_DWORD *)(*((_QWORD *)v116 + 26) + 4LL) = v117;
            return v12;
          }
          v113 = v112 - 1;
          if ( v113 )
          {
            if ( v113 != 1 )
              return v12;
            v52 = *(_QWORD *)(a1 + 40);
            v114 = *(_DWORD *)(v52 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v54 = v114 | 4;
            else
              v54 = v114 & 0xFFFFFFFB;
          }
          else
          {
            v52 = *(_QWORD *)(a1 + 40);
            v115 = *(_DWORD *)(v52 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v54 = v115 | 8;
            else
              v54 = v115 & 0xFFFFFFF7;
          }
        }
        else
        {
          v52 = *(_QWORD *)(a1 + 40);
          v120 = *(_DWORD *)(v52 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v54 = v120 | 2;
          else
            v54 = v120 & 0xFFFFFFFD;
        }
        goto LABEL_185;
      }
      switch ( a3 )
      {
        case '^':
          v127 = *(_DWORD *)(a4 + 32);
          if ( (unsigned int)(v127 - 60) <= 0x28DE44 )
          {
            v128 = *(JobBucket **)(a1 + 40);
            JobBucket::InitOptionalSettings(v128);
            *(_DWORD *)(*((_QWORD *)v128 + 26) + 20LL) = v127;
            return v12;
          }
          return 2147750680LL;
        case '_':
          v125 = *(unsigned __int16 *)(a4 + 32);
          if ( (_WORD)v125 )
          {
            v126 = *(JobBucket **)(a1 + 40);
            JobBucket::InitOptionalSettings(v126);
            *(_DWORD *)(*((_QWORD *)v126 + 26) + 24LL) = v125;
            return v12;
          }
          return 2147750680LL;
        case '`':
          if ( *(_BYTE *)(a1 + 105) )
            return v12;
          v124 = *(_QWORD *)(a1 + 40);
          v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v19 = v124 + 168;
          goto LABEL_22;
      }
      if ( a3 != 99 )
      {
        if ( a3 != 100 )
          return v12;
        v123 = *(_QWORD *)(a1 + 40);
        if ( (*(_DWORD *)(v123 + 16) & 0xFC000) == 0
          || (*(_DWORD *)(v123 + 16) & 0xFC000) == (*(_DWORD *)(a4 + 32) & 0xFC000) )
        {
          *(_DWORD *)(v123 + 16) = *(_DWORD *)(a4 + 32) | *(_DWORD *)(v123 + 16) & 0xFFF03FFF;
          return v12;
        }
        return 2147750678LL;
      }
    }
    *(_BYTE *)(a1 + 489) = 1;
    v132 = (const unsigned __int16 ***)(a1 + 80);
    v133 = _bstr_t::length((_bstr_t *)(a1 + 80));
    v134 = *(XmlParserTempString **)(a4 + 48);
    if ( v133 )
    {
      v135 = _bstr_t::length((_bstr_t *)(a1 + 80));
      if ( *v132 )
        v136 = **v132;
      else
        v136 = 0;
      if ( !XmlParserTempString::IsEqualTo(v134, v136, v135) )
      {
        *(_BYTE *)(a1 + 488) = 1;
        v137 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
        _bstr_t::operator=(a1 + 80, v137);
LABEL_272:
        _bstr_t::~_bstr_t((_bstr_t *)v183);
        return 2147750680LL;
      }
    }
    else
    {
      v138 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      _bstr_t::operator=(a1 + 80, v138);
      _bstr_t::~_bstr_t((_bstr_t *)v183);
    }
    if ( a3 != 99 || ValidationXmlHandler::CheckId((ValidationXmlHandler *)a1, (const struct _bstr_t *)(a1 + 80)) )
      return v12;
    return 2147750680LL;
  }
  if ( a3 == 68 )
  {
    if ( *a2 >= 65538 || *(_WORD *)(a4 + 32) != 32 )
    {
      v88 = *(_DWORD *)(a1 + 272);
      _bittestandset(&v88, *(unsigned __int16 *)(a4 + 32) - 1);
      *(_DWORD *)(a1 + 272) = v88;
      return v12;
    }
    return (unsigned int)-2147216616;
  }
  if ( a3 > 34 )
  {
    if ( a3 > 55 )
    {
      if ( a3 > 61 )
      {
        v82 = a3 == 62;
        v83 = a3 - 62;
      }
      else
      {
        if ( a3 == 61 )
          goto LABEL_156;
        v82 = a3 == 56;
        v83 = a3 - 56;
      }
      if ( !v82 )
      {
        v84 = v83 - 1;
        if ( v84 )
        {
          v85 = v84 - 1;
          if ( v85 )
          {
            if ( (unsigned int)(v85 - 1) > 1 )
              return v12;
          }
        }
      }
    }
    else if ( a3 != 55 )
    {
      if ( a3 > 46 )
      {
        if ( a3 != 47 && a3 != 48 && a3 != 49 && (unsigned int)(a3 - 50) > 1 )
          return v12;
      }
      else if ( a3 != 46 )
      {
        if ( a3 != 36 )
        {
          switch ( a3 )
          {
            case '&':
              *(_DWORD *)(a1 + 328) = *(_DWORD *)(a4 + 32);
              return v12;
            case ')':
              v65 = *(_WORD *)(a4 + 32);
              v66 = (unsigned __int16)(v65 - 1) <= 0x16Cu;
              break;
            case '+':
              v65 = *(_WORD *)(a4 + 32);
              v66 = (unsigned __int16)(v65 - 1) <= 0x33u;
              break;
            case '-':
              goto LABEL_146;
            default:
              return v12;
          }
          if ( v66 )
          {
            *(_WORD *)(a1 + 272) = v65;
            return v12;
          }
          return 2147750680LL;
        }
        v67 = *(_QWORD *)(a4 + 48);
        if ( *(_DWORD *)(a1 + 112) )
        {
          v68 = XmlParserTempString::GetCopy(v67, v183);
          _bstr_t::operator=(a1 + 200, v68);
          _bstr_t::~_bstr_t((_bstr_t *)v183);
          v183[0] = 0;
          v69 = *(const WCHAR ***)(a1 + 200);
          if ( v69 )
            v70 = *v69;
          else
            v70 = 0;
          v12 = User::FromUsername((struct User *)v183, v70);
          if ( (v12 & 0x80000000) == 0 )
          {
            if ( User::IsGroupAccount((User *)v183) )
            {
              wmi::AutoRef<User::UserEntry>::Release(v183);
              return 2147750680LL;
            }
          }
          else if ( (*(_BYTE *)(a1 + 48) & 4) != 0 )
          {
            v12 = 0;
          }
          wmi::AutoRef<User::UserEntry>::Release(v183);
          return v12;
        }
        v72 = XmlParserTempString::GetCopy(v67, v183);
        v73 = (const WCHAR ***)(a1 + 72);
        _bstr_t::operator=(a1 + 72, v72);
        _bstr_t::~_bstr_t((_bstr_t *)v183);
        v74 = *(_QWORD *)(a1 + 40);
        if ( (*(_DWORD *)(v74 + 16) & 0x18000000) == 0
          && ((v75 = *(_QWORD *)(v74 + 208)) == 0 || !*(_QWORD *)(v75 + 48))
          || (!*v73 ? (v76 = 0) : (v76 = **v73), User::SupportsTaskHardening(v76)) )
        {
          if ( *v73 )
            v77 = **v73;
          else
            v77 = 0;
          if ( *v77 != 64 )
            return v12;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x100000u;
          v78 = (volatile signed __int32 *)*v73;
          v183[0] = v78;
          if ( v78 )
          {
            _InterlockedAdd(v78 + 4, 1u);
            v79 = *(_QWORD *)v78;
          }
          else
          {
            v79 = 0;
          }
          _bstr_t::operator=(a1 + 72, v79 + 2);
          goto LABEL_64;
        }
        return 2147750678LL;
      }
LABEL_146:
      v80 = a3 - 45;
      if ( *(_DWORD *)(a1 + 268) != 2 )
      {
        *(_WORD *)(a1 + 272) |= 1 << v80;
        return v12;
      }
      v81 = *(unsigned __int16 *)(a1 + 274) | (1 << v80);
LABEL_187:
      *(_WORD *)(a1 + 274) = v81;
      return v12;
    }
LABEL_156:
    v86 = a3 - 55;
    v87 = *(unsigned __int16 *)(a1 + 276);
    if ( !_bittest(&v87, v86) )
    {
      *(_WORD *)(a1 + 276) = v87 | (1 << v86);
      return v12;
    }
    return 2147750678LL;
  }
  if ( a3 == 34 )
  {
    v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    v37 = a1 + 184;
    goto LABEL_62;
  }
  if ( a3 > 16 )
  {
    if ( a3 > 26 )
    {
      v55 = a3 - 28;
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( !v56 )
        {
          v64 = *(_DWORD *)(a4 + 32);
          if ( v64 >= 0x3C )
          {
            *(_DWORD *)(a1 + 156) = v64;
            return v12;
          }
          return 2147750680LL;
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          if ( (unsigned __int16)(*(_WORD *)(a4 + 32) - 1) <= 0x1Fu )
          {
            *(_DWORD *)(a1 + 152) = *(unsigned __int16 *)(a4 + 32);
            return v12;
          }
          return 2147750680LL;
        }
        v58 = v57 - 1;
        if ( v58 )
        {
          if ( v58 != 2 )
            return v12;
          v59 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          _bstr_t::operator=(a1 + 192, v59);
          _bstr_t::~_bstr_t((_bstr_t *)v183);
          if ( _bstr_t::length((_bstr_t *)(a1 + 192)) && _bstr_t::length((_bstr_t *)(a1 + 184)) )
          {
            v60 = *(_QWORD *)(a1 + 184);
            v183[0] = v60;
            if ( v60 )
              _InterlockedAdd((volatile signed __int32 *)(v60 + 16), 1u);
            v61 = *(_QWORD *)(a1 + 192);
            v183[1] = v61;
            if ( v61 )
              _InterlockedAdd((volatile signed __int32 *)(v61 + 16), 1u);
            v62 = std::_Tree_buy<std::pair<_bstr_t const,_bstr_t>>::_Buynode<std::pair<_bstr_t,_bstr_t>>(a1 + 168, v183);
            std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::_Insert_nohint<std::pair<_bstr_t const,_bstr_t> &,std::_Tree_node<std::pair<_bstr_t const,_bstr_t>,void *> *>(
              a1 + 168,
              &v184,
              v63,
              v62 + 32,
              v62);
            std::pair<_bstr_t const,_bstr_t>::~pair<_bstr_t const,_bstr_t>((_bstr_t *)v183);
            v183[0] = 0;
            _bstr_t::operator=(a1 + 184, v183);
            _bstr_t::~_bstr_t((_bstr_t *)v183);
            v183[0] = 0;
            v48 = v183;
            v37 = a1 + 192;
            goto LABEL_63;
          }
          return 2147750680LL;
        }
        v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
        v37 = a1 + 160;
      }
      else
      {
        v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
        v37 = a1 + 144;
      }
LABEL_62:
      v48 = (_QWORD *)v36;
LABEL_63:
      _bstr_t::operator=(v37, v48);
LABEL_64:
      v21 = (_bstr_t *)v183;
      goto LABEL_23;
    }
    if ( a3 == 26 )
    {
      v47 = *(_DWORD *)(a4 + 32);
      if ( v47 > 0x28DE80 )
        return 2147750680LL;
      goto LABEL_60;
    }
    v43 = a3 - 17;
    if ( !v43 )
    {
      if ( (unsigned __int8)TSTime::operator<(a1 + 312, a4) )
        return 2147750680LL;
      *(_OWORD *)(a1 + 208) = *(_OWORD *)a4;
      *(_OWORD *)(a1 + 296) = *(_OWORD *)a4;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v12;
      v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v37 = a1 + 384;
      goto LABEL_62;
    }
    v44 = v43 - 1;
    if ( !v44 )
    {
      if ( (unsigned __int8)TSTime::operator<(a4, a1 + 296) )
        return 2147750680LL;
      *(_OWORD *)(a1 + 224) = *(_OWORD *)a4;
      *(_OWORD *)(a1 + 312) = *(_OWORD *)a4;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v12;
      v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v37 = a1 + 392;
      goto LABEL_62;
    }
    v45 = v44 - 1;
    if ( v45 )
    {
      v46 = v45 - 1;
      if ( !v46 )
      {
        if ( !*(_DWORD *)(a1 + 112) )
        {
          v49 = *(JobBucket **)(a1 + 40);
          v50 = *(_DWORD *)(a4 + 32);
          JobBucket::InitOptionalSettings(v49);
          *(_DWORD *)(*((_QWORD *)v49 + 26) + 8LL) = v50;
          return v12;
        }
        *(_DWORD *)(a1 + 136) = *(_DWORD *)(a4 + 32);
        if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
          return v12;
        v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
        v37 = a1 + 376;
        goto LABEL_62;
      }
      if ( v46 != 2 )
        return v12;
      v47 = *(_DWORD *)(a4 + 32);
LABEL_60:
      *(_DWORD *)(a1 + 132) = v47;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v12;
      v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v37 = a1 + 368;
      goto LABEL_62;
    }
    v51 = *(_BYTE *)(a4 + 32);
    if ( *(_DWORD *)(a1 + 112) )
    {
      *(_BYTE *)(a1 + 128) = v51;
      *(_BYTE *)(a1 + 281) = *(_BYTE *)(a4 + 32);
      return v12;
    }
    v52 = *(_QWORD *)(a1 + 40);
    v53 = *(_DWORD *)(v52 + 16);
    if ( v51 )
      v54 = v53 | 0x400000;
    else
      v54 = v53 & 0xFFBFFFFF;
LABEL_185:
    *(_DWORD *)(v52 + 16) = v54;
    return v12;
  }
  if ( a3 == 16 )
  {
    *(_BYTE *)(a1 + 280) = *(_BYTE *)(a4 + 32);
    return v12;
  }
  if ( a3 > 8 )
  {
    v30 = a3 - 9;
    if ( !v30 )
    {
      v42 = *(_QWORD *)(a1 + 40);
      v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v19 = v42 + 112;
      goto LABEL_22;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      v41 = *(_QWORD *)(a1 + 40);
      v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v19 = v41 + 144;
      goto LABEL_22;
    }
    v32 = v31 - 1;
    if ( !v32 )
    {
      v40 = *(_QWORD *)(a1 + 40);
      v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
      v19 = v40 + 152;
      goto LABEL_22;
    }
    v33 = v32 - 3;
    if ( v33 )
    {
      if ( v33 != 1 )
        return v12;
      v34 = *(_DWORD *)(a4 + 32);
      if ( v34 >= 0x3C )
      {
        v35 = *(_DWORD *)(a1 + 256);
        if ( !v35 || v35 <= v34 )
        {
          *(_DWORD *)(a1 + 260) = v34;
          if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
            return v12;
          v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
          v37 = a1 + 408;
          goto LABEL_62;
        }
      }
      return 2147750680LL;
    }
    v38 = *(_DWORD *)(a4 + 32);
    if ( v38 - 60 > 0x28DE44 )
      return 2147750680LL;
    v39 = *(_DWORD *)(a1 + 260);
    if ( v39 )
    {
      if ( v39 < v38 )
        return 2147750680LL;
    }
    *(_DWORD *)(a1 + 256) = v38;
    if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
      return v12;
    v36 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    v37 = a1 + 400;
    goto LABEL_62;
  }
  if ( a3 == 8 )
  {
    v29 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    v19 = v29 + 136;
    goto LABEL_22;
  }
  v13 = a3 - 2;
  if ( !v13 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 96LL) = *(_DWORD *)(a4 + 32);
    if ( *(_DWORD *)(a4 + 32) == 0x10000 || *(_DWORD *)(a4 + 32) == 65537 )
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x200000u;
    return v12;
  }
  v14 = v13 - 2;
  if ( !v14 )
  {
    v26 = *(_QWORD *)(a1 + 40);
    v27 = (_bstr_t *)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    _bstr_t::operator=(v26 + 160, v27);
    _bstr_t::~_bstr_t(v27);
    v25 = *(ATL::CComBSTR **)(a1 + 56);
LABEL_27:
    if ( v25 )
    {
      v28 = XmlParserTempString::DetachBstr(*(XmlParserTempString **)(a4 + 48));
      ATL::CComBSTR::Attach(v25, v28);
    }
    return v12;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v23 = *(_QWORD *)(a1 + 40);
    v24 = (_bstr_t *)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    _bstr_t::operator=(v23 + 120, v24);
    _bstr_t::~_bstr_t(v24);
    v25 = *(ATL::CComBSTR **)(a1 + 64);
    goto LABEL_27;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v22 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    v19 = v22 + 128;
    goto LABEL_22;
  }
  if ( v16 == 1 )
  {
    v17 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v183);
    v19 = v17 + 104;
LABEL_22:
    v20 = (_bstr_t *)v18;
    _bstr_t::operator=(v19, v18);
    v21 = v20;
LABEL_23:
    _bstr_t::~_bstr_t(v21);
  }
  return v12;
}

```

## disassembly

```asm
0x1800232b0  mov     rax, rsp
0x1800232b3  push    rbp
0x1800232b4  push    rbx
0x1800232b5  push    rsi
0x1800232b6  push    rdi
0x1800232b7  push    r12
0x1800232b9  push    r13
0x1800232bb  push    r14
0x1800232bd  push    r15
0x1800232bf  lea     rbp, [rax-57h]
0x1800232c3  sub     rsp, 0D8h
0x1800232ca  movaps  xmmword ptr [rax-58h], xmm6
0x1800232ce  mov     rax, cs:__security_cookie
0x1800232d5  xor     rax, rsp
0x1800232d8  mov     [rbp+4Fh+var_60], rax
0x1800232dc  mov     r14, r9
0x1800232df  mov     ebx, r8d
0x1800232e2  mov     r12, rdx
0x1800232e5  mov     rsi, rcx
0x1800232e8  lea     rax, WPP_GLOBAL_Control
0x1800232ef  xor     r13d, r13d
0x1800232f2  mov     rdi, cs:WPP_GLOBAL_Control
0x1800232f9  cmp     rdi, rax
0x1800232fc  jz      short loc_180023348
0x1800232fe  test    byte ptr [rdi+1Ch], 80h
0x180023302  jz      short loc_180023348
0x180023304  cmp     byte ptr [rdi+19h], 5
0x180023308  jb      short loc_180023348
0x18002330a  mov     rax, [r9+30h]
0x18002330e  test    rax, rax
0x180023311  jz      short loc_180023319
0x180023313  mov     r15, [rax+8]
0x180023317  jmp     short loc_180023320
0x180023319  lea     r15, aNull; "null"
0x180023320  mov     edx, ebx
0x180023322  mov     rcx, r12
0x180023325  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18002332a  mov     edx, 0Bh
0x18002332f  mov     [rsp+20h], r15
0x180023334  mov     r9, [rax+8]
0x180023338  lea     r8, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids
0x18002333f  mov     rcx, [rdi+10h]
0x180023343  call    WPP_SF_SS
0x180023348  mov     r15d, r13d
0x18002334b  xorps   xmm0, xmm0
0x18002334e  movups  xmmword ptr [rbp+4Fh+iid.Data1], xmm0
0x180023352  cmp     ebx, 44h ; 'D'
0x180023355  jg      loc_180023BF3
0x18002335b  jz      loc_180023BBE
0x180023361  cmp     ebx, 22h ; '"'
0x180023364  jg      loc_180023957
0x18002336a  jz      loc_18002393D
0x180023370  cmp     ebx, 10h
0x180023373  jg      loc_1800235F9
0x180023379  jz      loc_1800235EA
0x18002337f  cmp     ebx, 8
0x180023382  jg      loc_1800234C9
0x180023388  jz      loc_1800234AB
0x18002338e  sub     ebx, 2
0x180023391  jz      loc_18002347D
0x180023397  sub     ebx, 2
0x18002339a  jz      loc_18002342B
0x1800233a0  sub     ebx, 1
0x1800233a3  jz      short loc_1800233FC
0x1800233a5  sub     ebx, 1
0x1800233a8  jz      short loc_1800233E1
0x1800233aa  cmp     ebx, 1
0x1800233ad  jnz     loc_18002460C
0x1800233b3  mov     rdi, [rsi+28h]
0x1800233b7  lea     rdx, [rsp+110h+var_E0]
0x1800233bc  mov     rcx, [r14+30h]
0x1800233c0  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800233c5  lea     rcx, [rdi+68h]
0x1800233c9  mov     rbx, rax
0x1800233cc  mov     rdx, rax
0x1800233cf  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800233d4  mov     rcx, rbx; this
0x1800233d7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800233dc  jmp     loc_18002460C
0x1800233e1  mov     rdi, [rsi+28h]
0x1800233e5  lea     rdx, [rsp+110h+var_E0]
0x1800233ea  mov     rcx, [r14+30h]
0x1800233ee  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800233f3  lea     rcx, [rdi+80h]
0x1800233fa  jmp     short loc_1800233C9
0x1800233fc  mov     rdi, [rsi+28h]
0x180023400  lea     rdx, [rsp+110h+var_E0]
0x180023405  mov     rcx, [r14+30h]
0x180023409  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002340e  mov     rbx, rax
0x180023411  lea     rcx, [rdi+78h]
0x180023415  mov     rdx, rax
0x180023418  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18002341d  mov     rcx, rbx; this
0x180023420  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023425  mov     rbx, [rsi+40h]
0x180023429  jmp     short loc_18002345B
0x18002342b  mov     rdi, [rsi+28h]
0x18002342f  lea     rdx, [rsp+110h+var_E0]
0x180023434  mov     rcx, [r14+30h]
0x180023438  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002343d  mov     rbx, rax
0x180023440  lea     rcx, [rdi+0A0h]
0x180023447  mov     rdx, rax
0x18002344a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18002344f  mov     rcx, rbx; this
0x180023452  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023457  mov     rbx, [rsi+38h]
0x18002345b  test    rbx, rbx
0x18002345e  jz      loc_18002460C
0x180023464  mov     rcx, [r14+30h]; this
0x180023468  call    ?DetachBstr@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::DetachBstr(void)
0x18002346d  mov     rdx, rax; unsigned __int16 *
0x180023470  mov     rcx, rbx; this
0x180023473  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180023478  jmp     loc_18002460C
0x18002347d  mov     rcx, [rsi+28h]
0x180023481  mov     eax, [r14+20h]
0x180023485  mov     [rcx+60h], eax
0x180023488  mov     ecx, [r14+20h]
0x18002348c  sub     ecx, 10000h
0x180023492  jz      short loc_18002349D
0x180023494  cmp     ecx, 1
0x180023497  jnz     loc_18002460C
0x18002349d  mov     rax, [rsi+28h]
0x1800234a1  bts     dword ptr [rax+10h], 15h
0x1800234a6  jmp     loc_18002460C
0x1800234ab  mov     rdi, [rsi+28h]
0x1800234af  lea     rdx, [rsp+110h+var_E0]
0x1800234b4  mov     rcx, [r14+30h]
0x1800234b8  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800234bd  lea     rcx, [rdi+88h]
0x1800234c4  jmp     loc_1800233C9
0x1800234c9  sub     ebx, 9
0x1800234cc  jz      loc_1800235CF
0x1800234d2  sub     ebx, 1
0x1800234d5  jz      loc_1800235B1
0x1800234db  sub     ebx, 1
0x1800234de  jz      loc_180023593
0x1800234e4  sub     ebx, 3
0x1800234e7  jz      short loc_180023540
0x1800234e9  cmp     ebx, 1
0x1800234ec  jnz     loc_18002460C
0x1800234f2  mov     eax, [r14+20h]
0x1800234f6  cmp     eax, 3Ch ; '<'
0x1800234f9  jb      loc_180023A61
0x1800234ff  mov     ecx, [rsi+100h]
0x180023505  test    ecx, ecx
0x180023507  jz      short loc_180023511
0x180023509  cmp     ecx, eax
0x18002350b  ja      loc_180023A61
0x180023511  mov     [rsi+104h], eax
0x180023517  mov     edi, 1
0x18002351c  test    [rsi+30h], dil
0x180023520  jz      loc_18002460C
0x180023526  lea     rdx, [rsp+110h+var_E0]
0x18002352b  mov     rcx, [r14+30h]
0x18002352f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180023534  lea     rcx, [rsi+198h]
0x18002353b  jmp     loc_18002365F
0x180023540  mov     ecx, [r14+20h]
0x180023544  lea     eax, [rcx-3Ch]
0x180023547  cmp     eax, 28DE44h
0x18002354c  ja      loc_180023A61
0x180023552  mov     eax, [rsi+104h]
0x180023558  test    eax, eax
0x18002355a  jz      short loc_180023564
0x18002355c  cmp     eax, ecx
0x18002355e  jb      loc_180023A61
0x180023564  mov     [rsi+100h], ecx
0x18002356a  mov     edi, 1
0x18002356f  test    [rsi+30h], dil
0x180023573  jz      loc_18002460C
0x180023579  lea     rdx, [rsp+110h+var_E0]
0x18002357e  mov     rcx, [r14+30h]
0x180023582  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180023587  lea     rcx, [rsi+190h]
0x18002358e  jmp     loc_18002365F
0x180023593  mov     rdi, [rsi+28h]
0x180023597  lea     rdx, [rsp+110h+var_E0]
0x18002359c  mov     rcx, [r14+30h]
0x1800235a0  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800235a5  lea     rcx, [rdi+98h]
0x1800235ac  jmp     loc_1800233C9
0x1800235b1  mov     rdi, [rsi+28h]
0x1800235b5  lea     rdx, [rsp+110h+var_E0]
0x1800235ba  mov     rcx, [r14+30h]
0x1800235be  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800235c3  lea     rcx, [rdi+90h]
0x1800235ca  jmp     loc_1800233C9
0x1800235cf  mov     rdi, [rsi+28h]
0x1800235d3  lea     rdx, [rsp+110h+var_E0]
0x1800235d8  mov     rcx, [r14+30h]
0x1800235dc  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800235e1  lea     rcx, [rdi+70h]
0x1800235e5  jmp     loc_1800233C9
0x1800235ea  mov     al, [r14+20h]
0x1800235ee  mov     [rsi+118h], al
0x1800235f4  jmp     loc_18002460C
0x1800235f9  cmp     ebx, 1Ah
0x1800235fc  jg      loc_1800237C6
0x180023602  jz      loc_1800237B2
0x180023608  sub     ebx, 11h
0x18002360b  jz      loc_18002375A
0x180023611  sub     ebx, 1
0x180023614  jz      loc_180023702
0x18002361a  sub     ebx, 1
0x18002361d  jz      loc_1800236C6
0x180023623  sub     ebx, 1
0x180023626  jz      short loc_180023671
0x180023628  cmp     ebx, 2
0x18002362b  jnz     loc_18002460C
0x180023631  mov     eax, [r14+20h]
0x180023635  mov     [rsi+84h], eax
0x18002363b  mov     edi, 1
0x180023640  test    [rsi+30h], dil
0x180023644  jz      loc_18002460C
0x18002364a  lea     rdx, [rsp+110h+var_E0]
0x18002364f  mov     rcx, [r14+30h]
0x180023653  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180023658  lea     rcx, [rsi+170h]
0x18002365f  mov     rdx, rax
0x180023662  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180023667  lea     rcx, [rsp+110h+var_E0]
0x18002366c  jmp     loc_1800233D7
0x180023671  cmp     [rsi+70h], r13d
0x180023675  jz      short loc_1800236A7
0x180023677  mov     eax, [r14+20h]
0x18002367b  mov     [rsi+88h], eax
0x180023681  mov     edi, 1
0x180023686  test    [rsi+30h], dil
0x18002368a  jz      loc_18002460C
0x180023690  lea     rdx, [rsp+110h+var_E0]
0x180023695  mov     rcx, [r14+30h]
0x180023699  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002369e  lea     rcx, [rsi+178h]
0x1800236a5  jmp     short loc_18002365F
0x1800236a7  mov     rbx, [rsi+28h]
0x1800236ab  mov     edi, [r14+20h]
0x1800236af  mov     rcx, rbx; this
0x1800236b2  call    ?InitOptionalSettings@JobBucket@@IEAAXXZ; JobBucket::InitOptionalSettings(void)
0x1800236b7  mov     rax, [rbx+0D0h]
0x1800236be  mov     [rax+8], edi
0x1800236c1  jmp     loc_18002460C
0x1800236c6  mov     dl, [r14+20h]
0x1800236ca  cmp     [rsi+70h], r13d
0x1800236ce  jz      short loc_1800236E5
0x1800236d0  mov     [rsi+80h], dl
0x1800236d6  mov     al, [r14+20h]
0x1800236da  mov     [rsi+119h], al
0x1800236e0  jmp     loc_18002460C
0x1800236e5  mov     rcx, [rsi+28h]
0x1800236e9  mov     eax, [rcx+10h]
0x1800236ec  test    dl, dl
0x1800236ee  jz      short loc_1800236F9
0x1800236f0  bts     eax, 16h
0x1800236f4  jmp     loc_180023CA3
0x1800236f9  btr     eax, 16h
0x1800236fd  jmp     loc_180023CA3
0x180023702  lea     rdx, [rsi+128h]
0x180023709  mov     rcx, r14
0x18002370c  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180023711  test    al, al
0x180023713  jnz     loc_180023A61
0x180023719  movups  xmm0, xmmword ptr [r14]
0x18002371d  movdqu  xmmword ptr [rsi+0E0h], xmm0
0x180023725  movups  xmm1, xmmword ptr [r14]
0x180023729  movdqu  xmmword ptr [rsi+138h], xmm1
0x180023731  mov     edi, 1
0x180023736  test    [rsi+30h], dil
0x18002373a  jz      loc_18002460C
0x180023740  lea     rdx, [rsp+110h+var_E0]
0x180023745  mov     rcx, [r14+30h]
0x180023749  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002374e  lea     rcx, [rsi+188h]
0x180023755  jmp     loc_18002365F
0x18002375a  lea     rcx, [rsi+138h]
0x180023761  mov     rdx, r14
0x180023764  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180023769  test    al, al
0x18002376b  jnz     loc_180023A61
0x180023771  movups  xmm0, xmmword ptr [r14]
0x180023775  movdqu  xmmword ptr [rsi+0D0h], xmm0
0x18002377d  movups  xmm1, xmmword ptr [r14]
0x180023781  movdqu  xmmword ptr [rsi+128h], xmm1
0x180023789  mov     edi, 1
0x18002378e  test    [rsi+30h], dil
0x180023792  jz      loc_18002460C
0x180023798  lea     rdx, [rsp+110h+var_E0]
0x18002379d  mov     rcx, [r14+30h]
0x1800237a1  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800237a6  lea     rcx, [rsi+180h]
0x1800237ad  jmp     loc_18002365F
0x1800237b2  mov     eax, [r14+20h]
0x1800237b6  cmp     eax, 28DE80h
0x1800237bb  ja      loc_180023A61
0x1800237c1  jmp     loc_180023635
0x1800237c6  sub     ebx, 1Ch
0x1800237c9  jz      loc_180023923
0x1800237cf  sub     ebx, 1
  ... truncated ...
```
