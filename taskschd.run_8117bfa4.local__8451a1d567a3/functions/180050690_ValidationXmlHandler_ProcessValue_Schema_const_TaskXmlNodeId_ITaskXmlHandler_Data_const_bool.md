# ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)

- ea: `0x180050690`
- end: `0x180051a0e`
- name: `?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z`
- size: `4990`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b390`
- `0x18004dcb0`

## callees

- `0x180003ea0`
- `0x180007e90`
- `0x1800089e0`
- `0x180009150`
- `0x180009248`
- `0x180016930`
- `0x18001d3f0`
- `0x1800259f0`
- `0x1800287c0`
- `0x180029cd0`
- `0x18002ae20`
- `0x18002b400`
- `0x18002cdf4`
- `0x18002eee0`
- `0x18002fe74`
- `0x180031fa8`
- `0x1800372f0`
- `0x18003b048`
- `0x18003c5ec`
- `0x18003c7c0`
- `0x18003e8a6`
- `0x18004f71c`
- `0x18004f8c8`
- `0x18004fb1c`
- `0x180050690`
- `0x180051af8`
- `0x180052640`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180051271`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800512bf`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180051271`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800512bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ValidationXmlHandler::ProcessValue(__int64 a1, int *a2, int a3, __int64 a4)
{
  __int64 v8; // rax
  const wchar_t *v9; // rdi
  __int64 Entry; // rax
  __int64 v11; // r11
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // r15d
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rcx
  _bstr_t *v22; // rbx
  _bstr_t *v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rdi
  _bstr_t *v26; // rbx
  ATL::CComBSTR *v27; // rbx
  __int64 v28; // rdi
  _bstr_t *v29; // rbx
  unsigned __int16 *v30; // rax
  __int64 v31; // rdi
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // ebx
  unsigned int v36; // eax
  unsigned int v37; // ecx
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // ecx
  unsigned int v41; // eax
  __int64 v42; // rdi
  __int64 v43; // rdi
  __int64 v44; // rdi
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  unsigned int v49; // eax
  _QWORD *v50; // rdx
  JobBucket *v51; // rbx
  int v52; // edi
  char v53; // dl
  __int64 v54; // rcx
  int v55; // eax
  unsigned int v56; // eax
  int v57; // ebx
  int v58; // ebx
  int v59; // ebx
  int v60; // ebx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // r8
  unsigned int v66; // eax
  __int16 v67; // cx
  bool v68; // cc
  __int64 v69; // rcx
  __int64 v70; // rax
  const WCHAR **v71; // rdx
  const WCHAR *v72; // rdx
  __int64 v74; // rax
  const WCHAR ***v75; // rbx
  __int64 v76; // rax
  __int64 v77; // rax
  const WCHAR *v78; // rcx
  const WCHAR *v79; // rcx
  volatile signed __int32 *v80; // rax
  __int64 v81; // rdx
  char v82; // bl
  int v83; // eax
  bool v84; // zf
  int v85; // ecx
  int v86; // ecx
  int v87; // ecx
  unsigned int v88; // ebx
  int v89; // eax
  int v90; // eax
  int v91; // ebx
  int v92; // ebx
  int v93; // ebx
  int v94; // ebx
  __int64 v95; // rdx
  int v96; // eax
  unsigned int v97; // eax
  int v98; // eax
  int v99; // eax
  int v100; // eax
  int v101; // ebx
  int v102; // ebx
  int v103; // ebx
  int v104; // ebx
  int v105; // eax
  int v106; // eax
  int v107; // eax
  int v108; // eax
  int v109; // eax
  JobBucket *v110; // rbx
  int v111; // edi
  int v112; // ebx
  int v113; // ebx
  int v114; // ebx
  int v115; // ebx
  int v116; // eax
  int v117; // eax
  JobBucket *v118; // rbx
  int v119; // edi
  JobBucket *v120; // rbx
  int v121; // edi
  int v122; // eax
  JobBucket *v123; // rbx
  GUID v124; // xmm6
  __int64 v125; // r8
  __int64 v126; // rdi
  int v127; // r14d
  JobBucket *v128; // rbx
  int v129; // edi
  JobBucket *v130; // rbx
  __int64 v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  const unsigned __int16 ***v134; // r12
  unsigned int v135; // eax
  XmlParserTempString *v136; // r13
  unsigned __int64 v137; // r8
  const unsigned __int16 *v138; // rdx
  __int64 v139; // rax
  __int64 v140; // rax
  bool v141; // al
  _DWORD *v142; // rcx
  int v143; // eax
  int v144; // ebx
  int v145; // ebx
  int v146; // ebx
  int v147; // ebx
  int v148; // eax
  _QWORD *v149; // rax
  const WCHAR *v150; // rcx
  int v151; // ebx
  int v152; // ebx
  int v153; // ebx
  int v154; // ebx
  int v155; // eax
  JobBucket *v156; // rbx
  int v157; // edi
  unsigned __int16 *v158; // r8
  JobBucket *v159; // rbx
  __int64 v160; // xmm6_8
  int v161; // edi
  unsigned __int16 v162; // si
  __int64 v163; // rax
  unsigned __int16 *v164; // r8
  JobBucket *v165; // rbx
  __int64 v166; // xmm6_8
  int v167; // edi
  unsigned __int16 v168; // si
  __int64 v169; // rax
  const WCHAR **v170; // rax
  const WCHAR *v171; // rcx
  JobBucket *v172; // rbx
  __int64 v173; // rdi
  int v174; // ebx
  int v175; // ebx
  int v176; // ebx
  JobBucket *v177; // rbx
  const unsigned __int16 ***Copy; // rax
  const unsigned __int16 *v179; // rdx
  __int64 v180; // rbx
  _QWORD *v181; // rax
  __int64 **v182; // rax
  __int64 v183; // rdx
  void *v184; // rax
  _QWORD v185[2]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v186; // [rsp+48h] [rbp-81h] BYREF
  GUID iid; // [rsp+58h] [rbp-71h] BYREF
  OLECHAR sz[40]; // [rsp+68h] [rbp-61h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v8 = *(_QWORD *)(a4 + 48);
    if ( v8 )
      v9 = *(const wchar_t **)(v8 + 8);
    else
      v9 = L"null";
    Entry = Schema::GetEntry(a2, (unsigned int)a3);
    WPP_SF_SS(*(_QWORD *)(v11 + 16), v12, v13, *(_QWORD *)(Entry + 8), (__int64)v9);
  }
  v14 = 0;
  iid = 0;
  if ( a3 > 68 )
  {
    if ( a3 > 101 )
    {
      if ( a3 > 133 )
      {
        if ( a3 > 142 )
        {
          v174 = a3 - 143;
          if ( !v174 )
          {
            v184 = operator new(*(unsigned int *)(a4 + 64));
            *(_QWORD *)(a1 + 352) = v184;
            if ( v184 )
            {
              memcpy_0(v184, *(const void **)(a4 + 56), *(unsigned int *)(a4 + 64));
              *(_DWORD *)(a1 + 344) = *(_DWORD *)(a4 + 64);
            }
            else
            {
              return (unsigned int)-2147024882;
            }
            return v14;
          }
          v175 = v174 - 1;
          if ( !v175 )
          {
            *(_DWORD *)(a1 + 340) = *(_DWORD *)(a4 + 32);
            return v14;
          }
          v176 = v175 - 1;
          if ( v176 )
          {
            if ( v176 != 2 )
              return v14;
            v177 = *(JobBucket **)(a1 + 40);
            Copy = (const unsigned __int16 ***)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
            if ( *Copy )
              v179 = **Copy;
            else
              v179 = 0;
            JobBucket::AddCapability(v177, v179);
            goto LABEL_64;
          }
          v180 = *(_QWORD *)(a1 + 40);
          v181 = *(_QWORD **)(v180 + 176);
          if ( !v181 || !*v181 )
          {
            v182 = (__int64 **)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
            if ( *v182 )
              v183 = **v182;
            else
              v183 = 0;
            _bstr_t::operator=(v180 + 176, v183);
            goto LABEL_64;
          }
          return 2147750678LL;
        }
        if ( a3 == 142 )
        {
          if ( *(_DWORD *)(a4 + 64) == 8 )
          {
            *(_QWORD *)(a1 + 332) = **(_QWORD **)(a4 + 56);
            return v14;
          }
        }
        else
        {
          v151 = a3 - 135;
          if ( !v151 )
          {
            if ( !_bstr_t::length((_bstr_t *)(a1 + 72))
              || ((v170 = *(const WCHAR ***)(a1 + 72)) == 0 ? (v171 = 0) : (v171 = *v170),
                  User::SupportsTaskHardening(v171)) )
            {
              v172 = *(JobBucket **)(a1 + 40);
              v173 = *(_QWORD *)(a4 + 32);
              JobBucket::InitOptionalSettings(v172);
              *(_QWORD *)(*((_QWORD *)v172 + 26) + 48LL) |= v173;
              return v14;
            }
            return 2147750678LL;
          }
          v152 = v151 - 2;
          if ( v152 )
          {
            v153 = v152 - 1;
            if ( v153 )
            {
              v154 = v153 - 1;
              if ( !v154 )
              {
                v156 = *(JobBucket **)(a1 + 40);
                v157 = *(unsigned __int8 *)(a4 + 32);
                JobBucket::InitOptionalSettings(v156);
                *(_DWORD *)(*((_QWORD *)v156 + 26) + 84LL) = v157;
                return v14;
              }
              if ( v154 != 1 )
                return v14;
              v54 = *(_QWORD *)(a1 + 40);
              v155 = *(_DWORD *)(v54 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v56 = v155 | 0x20000000;
              else
                v56 = v155 & 0xDFFFFFFF;
              goto LABEL_185;
            }
            if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)(a4 + 16))
              && (v158[1] + 12LL * *v158
               || *(unsigned __int16 *)(a4 + 28)
                + 60
                * (*(unsigned __int16 *)(a4 + 26)
                 + 60
                 * (*(unsigned __int16 *)(a4 + 24)
                  + 24 * (*(unsigned __int16 *)(a4 + 22) + 7 * (unsigned int)*(unsigned __int16 *)(a4 + 20)))) >= 0x15180) )
            {
              v159 = *(JobBucket **)(a1 + 40);
              v160 = *(_QWORD *)v158;
              v161 = *((_DWORD *)v158 + 2);
              v162 = v158[6];
              JobBucket::InitOptionalSettings(v159);
              v163 = *((_QWORD *)v159 + 26);
              *(_QWORD *)(v163 + 70) = v160;
              *(_DWORD *)(v163 + 78) = v161;
              *(_WORD *)(v163 + 82) = v162;
              return v14;
            }
          }
          else if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)(a4 + 16))
                 && (v164[1] + 12LL * *v164
                  || *(unsigned __int16 *)(a4 + 28)
                   + 60
                   * (*(unsigned __int16 *)(a4 + 26)
                    + 60
                    * (*(unsigned __int16 *)(a4 + 24)
                     + 24 * (*(unsigned __int16 *)(a4 + 22) + 7 * (unsigned int)*(unsigned __int16 *)(a4 + 20)))) >= 0x15180) )
          {
            v165 = *(JobBucket **)(a1 + 40);
            v166 = *(_QWORD *)v164;
            v167 = *((_DWORD *)v164 + 2);
            v168 = v164[6];
            JobBucket::InitOptionalSettings(v165);
            v169 = *((_QWORD *)v165 + 26);
            *(_QWORD *)(v169 + 56) = v166;
            *(_DWORD *)(v169 + 64) = v167;
            *(_WORD *)(v169 + 68) = v168;
            return v14;
          }
        }
        return (unsigned int)-2147216616;
      }
      if ( a3 == 133 )
      {
        if ( _bstr_t::length((_bstr_t *)(a1 + 72)) )
        {
          v149 = *(_QWORD **)(a1 + 72);
          v150 = v149 ? (const WCHAR *)*v149 : 0LL;
          if ( !User::SupportsTaskHardening(v150) )
            return 2147750678LL;
        }
LABEL_181:
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= *(_DWORD *)(a4 + 32);
        return v14;
      }
      if ( a3 > 112 )
      {
        v144 = a3 - 116;
        if ( !v144 )
        {
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 448;
          goto LABEL_62;
        }
        v145 = v144 - 1;
        if ( !v145 )
        {
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 456;
          goto LABEL_62;
        }
        v146 = v145 - 1;
        if ( !v146 )
        {
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 464;
          goto LABEL_62;
        }
        v147 = v146 - 2;
        if ( !v147 )
        {
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 472;
          goto LABEL_62;
        }
        if ( v147 != 12 )
          return v14;
        v54 = *(_QWORD *)(a1 + 40);
        v148 = *(_DWORD *)(v54 + 16);
        if ( *(_BYTE *)(a4 + 32) )
          v56 = v148 | 0x4000000;
        else
          v56 = v148 & 0xFBFFFFFF;
        goto LABEL_185;
      }
      switch ( a3 )
      {
        case 'p':
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 88;
          goto LABEL_62;
        case 'h':
          v142 = *(_DWORD **)(a4 + 48);
          v143 = 0;
          if ( (unsigned int)(*v142 - 1) > 0x103 )
            v143 = -2147216616;
          v14 = v143;
          v38 = XmlParserTempString::GetCopy(v142, v185);
          v39 = a1 + 480;
          goto LABEL_62;
        case 'j':
          if ( (unsigned int)(**(_DWORD **)(a4 + 48) - 1) <= 0x103 )
            return v14;
          return (unsigned int)-2147216616;
        case 'm':
          XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          if ( *(_DWORD *)(a1 + 112) )
            _bstr_t::operator=(a1 + 120, v185);
          v141 = ValidationXmlHandler::CheckId((ValidationXmlHandler *)a1, (const struct _bstr_t *)v185);
          v23 = (_bstr_t *)v185;
          if ( v141 )
            goto LABEL_23;
          goto LABEL_272;
      }
      if ( a3 != 110 )
      {
        if ( a3 != 111 )
          return v14;
        if ( (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) & 0xF4000) == 0 && !_bstr_t::length((_bstr_t *)(a1 + 72)) )
        {
          v131 = *(_QWORD *)(a1 + 40);
          if ( (*(_DWORD *)(v131 + 16) & 0x18000000) == 0 )
          {
            v132 = *(_QWORD *)(v131 + 208);
            if ( !v132 || !*(_QWORD *)(v132 + 48) )
            {
              v133 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
              _bstr_t::operator=(a1 + 72, v133);
              _bstr_t::_Free((_bstr_t *)v185);
              v54 = *(_QWORD *)(a1 + 40);
              v56 = *(_DWORD *)(v54 + 16) & 0xFFF03FFF | 0x8000;
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
          v110 = *(JobBucket **)(a1 + 40);
          v111 = *(unsigned __int16 *)(a4 + 32);
          JobBucket::InitOptionalSettings(v110);
          *(_DWORD *)(*((_QWORD *)v110 + 26) + 16LL) = v111;
          return v14;
        }
        if ( a3 > 76 )
        {
          v101 = a3 - 77;
          if ( v101 )
          {
            v102 = v101 - 1;
            if ( v102 )
            {
              v103 = v102 - 1;
              if ( v103 )
              {
                v104 = v103 - 2;
                if ( v104 )
                {
                  if ( v104 == 1 )
                  {
                    if ( *a2 < 65538 )
                    {
                      v105 = 0;
                      if ( *(_DWORD *)(a4 + 32) )
                        v105 = -2147216616;
                      v14 = v105;
                    }
                    *(_DWORD *)(a1 + 432) = *(_DWORD *)(a4 + 32);
                  }
                  return v14;
                }
                v54 = *(_QWORD *)(a1 + 40);
                v106 = *(_DWORD *)(v54 + 16);
                if ( *(_BYTE *)(a4 + 32) )
                  v56 = v106 | 0x800000;
                else
                  v56 = v106 & 0xFF7FFFFF;
              }
              else
              {
                v54 = *(_QWORD *)(a1 + 40);
                v107 = *(_DWORD *)(v54 + 16);
                if ( *(_BYTE *)(a4 + 32) )
                  v56 = v107 | 0x200;
                else
                  v56 = v107 & 0xFFFFFDFF;
              }
            }
            else
            {
              v54 = *(_QWORD *)(a1 + 40);
              v108 = *(_DWORD *)(v54 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v56 = v108 | 0x80;
              else
                v56 = v108 & 0xFFFFFF7F;
            }
          }
          else
          {
            v54 = *(_QWORD *)(a1 + 40);
            v109 = *(_DWORD *)(v54 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v56 = v109 | 0x40;
            else
              v56 = v109 & 0xFFFFFFBF;
          }
          goto LABEL_185;
        }
        if ( a3 == 76 )
        {
          v54 = *(_QWORD *)(a1 + 40);
          v100 = *(_DWORD *)(v54 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v56 = v100 | 0x40000000;
          else
            v56 = v100 & 0xBFFFFFFF;
          goto LABEL_185;
        }
        v91 = a3 - 70;
        if ( !v91 )
        {
          LOWORD(v83) = *(_WORD *)(a1 + 274) | (1 << ((*(_BYTE *)(a4 + 32) - 1) & 0xF));
          goto LABEL_187;
        }
        v92 = v91 - 2;
        if ( !v92 )
        {
          v54 = *(_QWORD *)(a1 + 40);
          v99 = *(_DWORD *)(v54 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v56 = v99 | 0x100;
          else
            v56 = v99 & 0xFFFFFEFF;
          goto LABEL_185;
        }
        v93 = v92 - 1;
        if ( v93 )
        {
          v94 = v93 - 1;
          if ( v94 )
          {
            if ( v94 == 1 )
            {
              v95 = *(_QWORD *)(a1 + 40);
              v96 = *(_DWORD *)(v95 + 16);
              if ( *(_BYTE *)(a4 + 32) )
                v97 = v96 | 0x20;
              else
                v97 = v96 & 0xFFFFFFDF;
              *(_DWORD *)(v95 + 16) = v97;
            }
            return v14;
          }
          v54 = *(_QWORD *)(a1 + 40);
          v98 = *(_DWORD *)(v54 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v56 = v98 | 0x10;
          else
            v56 = v98 & 0xFFFFFFEF;
          goto LABEL_185;
        }
        *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) &= 0xFFFFC3FF;
        goto LABEL_181;
      }
      if ( a3 <= 92 )
      {
        if ( a3 == 92 )
        {
          v14 = IIDFromString(*(LPCOLESTR *)(*(_QWORD *)(a4 + 48) + 8LL), &iid);
          if ( (v14 & 0x80000000) == 0
            || **(_WORD **)(*(_QWORD *)(a4 + 48) + 8LL) != 123
            && (v14 = StringCchPrintfW(sz, 0x28u, L"{%s}"), (v14 & 0x80000000) == 0)
            && (v14 = IIDFromString(sz, &iid), (v14 & 0x80000000) == 0) )
          {
            v123 = *(JobBucket **)(a1 + 40);
            v124 = iid;
            JobBucket::InitOptionalSettings(v123);
            *(GUID *)(*((_QWORD *)v123 + 26) + 28LL) = v124;
          }
          return v14;
        }
        v112 = a3 - 84;
        if ( v112 )
        {
          v113 = v112 - 2;
          if ( !v113 )
          {
            v120 = *(JobBucket **)(a1 + 40);
            v121 = *(_DWORD *)(a4 + 32);
            JobBucket::InitOptionalSettings(v120);
            **((_DWORD **)v120 + 26) = v121;
            return v14;
          }
          v114 = v113 - 1;
          if ( !v114 )
          {
            v118 = *(JobBucket **)(a1 + 40);
            v119 = *(_DWORD *)(a4 + 32);
            JobBucket::InitOptionalSettings(v118);
            *(_DWORD *)(*((_QWORD *)v118 + 26) + 4LL) = v119;
            return v14;
          }
          v115 = v114 - 1;
          if ( v115 )
          {
            if ( v115 != 1 )
              return v14;
            v54 = *(_QWORD *)(a1 + 40);
            v116 = *(_DWORD *)(v54 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v56 = v116 | 4;
            else
              v56 = v116 & 0xFFFFFFFB;
          }
          else
          {
            v54 = *(_QWORD *)(a1 + 40);
            v117 = *(_DWORD *)(v54 + 16);
            if ( *(_BYTE *)(a4 + 32) )
              v56 = v117 | 8;
            else
              v56 = v117 & 0xFFFFFFF7;
          }
        }
        else
        {
          v54 = *(_QWORD *)(a1 + 40);
          v122 = *(_DWORD *)(v54 + 16);
          if ( *(_BYTE *)(a4 + 32) )
            v56 = v122 | 2;
          else
            v56 = v122 & 0xFFFFFFFD;
        }
        goto LABEL_185;
      }
      switch ( a3 )
      {
        case '^':
          v129 = *(_DWORD *)(a4 + 32);
          if ( (unsigned int)(v129 - 60) <= 0x28DE44 )
          {
            v130 = *(JobBucket **)(a1 + 40);
            JobBucket::InitOptionalSettings(v130);
            *(_DWORD *)(*((_QWORD *)v130 + 26) + 20LL) = v129;
            return v14;
          }
          return 2147750680LL;
        case '_':
          v127 = *(unsigned __int16 *)(a4 + 32);
          if ( (_WORD)v127 )
          {
            v128 = *(JobBucket **)(a1 + 40);
            JobBucket::InitOptionalSettings(v128);
            *(_DWORD *)(*((_QWORD *)v128 + 26) + 24LL) = v127;
            return v14;
          }
          return 2147750680LL;
        case '`':
          if ( *(_BYTE *)(a1 + 105) )
            return v14;
          v126 = *(_QWORD *)(a1 + 40);
          v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v21 = v126 + 168;
          goto LABEL_22;
      }
      if ( a3 != 99 )
      {
        if ( a3 != 100 )
          return v14;
        v125 = *(_QWORD *)(a1 + 40);
        if ( (*(_DWORD *)(v125 + 16) & 0xFC000) == 0
          || (*(_DWORD *)(v125 + 16) & 0xFC000) == (*(_DWORD *)(a4 + 32) & 0xFC000) )
        {
          *(_DWORD *)(v125 + 16) = *(_DWORD *)(a4 + 32) | *(_DWORD *)(v125 + 16) & 0xFFF03FFF;
          return v14;
        }
        return 2147750678LL;
      }
    }
    *(_BYTE *)(a1 + 489) = 1;
    v134 = (const unsigned __int16 ***)(a1 + 80);
    v135 = _bstr_t::length((_bstr_t *)(a1 + 80));
    v136 = *(XmlParserTempString **)(a4 + 48);
    if ( v135 )
    {
      v137 = _bstr_t::length((_bstr_t *)(a1 + 80));
      if ( *v134 )
        v138 = **v134;
      else
        v138 = 0;
      if ( !XmlParserTempString::IsEqualTo(v136, v138, v137) )
      {
        *(_BYTE *)(a1 + 488) = 1;
        v139 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
        _bstr_t::operator=(a1 + 80, v139);
LABEL_272:
        _bstr_t::_Free((_bstr_t *)v185);
        return 2147750680LL;
      }
    }
    else
    {
      v140 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      _bstr_t::operator=(a1 + 80, v140);
      _bstr_t::_Free((_bstr_t *)v185);
    }
    if ( a3 != 99 || ValidationXmlHandler::CheckId((ValidationXmlHandler *)a1, (const struct _bstr_t *)(a1 + 80)) )
      return v14;
    return 2147750680LL;
  }
  if ( a3 == 68 )
  {
    if ( *a2 >= 65538 || *(_WORD *)(a4 + 32) != 32 )
    {
      v90 = *(_DWORD *)(a1 + 272);
      _bittestandset(&v90, *(unsigned __int16 *)(a4 + 32) - 1);
      *(_DWORD *)(a1 + 272) = v90;
      return v14;
    }
    return (unsigned int)-2147216616;
  }
  if ( a3 > 34 )
  {
    if ( a3 > 55 )
    {
      if ( a3 > 61 )
      {
        v84 = a3 == 62;
        v85 = a3 - 62;
      }
      else
      {
        if ( a3 == 61 )
          goto LABEL_156;
        v84 = a3 == 56;
        v85 = a3 - 56;
      }
      if ( !v84 )
      {
        v86 = v85 - 1;
        if ( v86 )
        {
          v87 = v86 - 1;
          if ( v87 )
          {
            if ( (unsigned int)(v87 - 1) > 1 )
              return v14;
          }
        }
      }
    }
    else if ( a3 != 55 )
    {
      if ( a3 > 46 )
      {
        if ( a3 != 47 && a3 != 48 && a3 != 49 && (unsigned int)(a3 - 50) > 1 )
          return v14;
      }
      else if ( a3 != 46 )
      {
        if ( a3 != 36 )
        {
          switch ( a3 )
          {
            case '&':
              *(_DWORD *)(a1 + 328) = *(_DWORD *)(a4 + 32);
              return v14;
            case ')':
              v67 = *(_WORD *)(a4 + 32);
              v68 = (unsigned __int16)(v67 - 1) <= 0x16Cu;
              break;
            case '+':
              v67 = *(_WORD *)(a4 + 32);
              v68 = (unsigned __int16)(v67 - 1) <= 0x33u;
              break;
            case '-':
              goto LABEL_146;
            default:
              return v14;
          }
          if ( v68 )
          {
            *(_WORD *)(a1 + 272) = v67;
            return v14;
          }
          return 2147750680LL;
        }
        v69 = *(_QWORD *)(a4 + 48);
        if ( *(_DWORD *)(a1 + 112) )
        {
          v70 = XmlParserTempString::GetCopy(v69, v185);
          _bstr_t::operator=(a1 + 200, v70);
          _bstr_t::_Free((_bstr_t *)v185);
          v185[0] = 0;
          v71 = *(const WCHAR ***)(a1 + 200);
          if ( v71 )
            v72 = *v71;
          else
            v72 = 0;
          v14 = User::FromUsername((struct User *)v185, v72);
          if ( (v14 & 0x80000000) == 0 )
          {
            if ( User::IsGroupAccount((User *)v185) )
            {
              User::~User((User *)v185);
              return 2147750680LL;
            }
          }
          else if ( (*(_BYTE *)(a1 + 48) & 4) != 0 )
          {
            v14 = 0;
          }
          User::~User((User *)v185);
          return v14;
        }
        v74 = XmlParserTempString::GetCopy(v69, v185);
        v75 = (const WCHAR ***)(a1 + 72);
        _bstr_t::operator=(a1 + 72, v74);
        _bstr_t::_Free((_bstr_t *)v185);
        v76 = *(_QWORD *)(a1 + 40);
        if ( (*(_DWORD *)(v76 + 16) & 0x18000000) == 0
          && ((v77 = *(_QWORD *)(v76 + 208)) == 0 || !*(_QWORD *)(v77 + 48))
          || (!*v75 ? (v78 = 0) : (v78 = **v75), User::SupportsTaskHardening(v78)) )
        {
          if ( *v75 )
            v79 = **v75;
          else
            v79 = 0;
          if ( *v79 != 64 )
            return v14;
          *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x100000u;
          v80 = (volatile signed __int32 *)*v75;
          v185[0] = v80;
          if ( v80 )
          {
            _InterlockedAdd(v80 + 4, 1u);
            v81 = *(_QWORD *)v80;
          }
          else
          {
            v81 = 0;
          }
          _bstr_t::operator=(a1 + 72, v81 + 2);
          goto LABEL_64;
        }
        return 2147750678LL;
      }
LABEL_146:
      v82 = a3 - 45;
      if ( *(_DWORD *)(a1 + 268) != 2 )
      {
        *(_WORD *)(a1 + 272) |= 1 << v82;
        return v14;
      }
      v83 = *(unsigned __int16 *)(a1 + 274) | (1 << v82);
LABEL_187:
      *(_WORD *)(a1 + 274) = v83;
      return v14;
    }
LABEL_156:
    v88 = a3 - 55;
    v89 = *(unsigned __int16 *)(a1 + 276);
    if ( !_bittest(&v89, v88) )
    {
      *(_WORD *)(a1 + 276) = v89 | (1 << v88);
      return v14;
    }
    return 2147750678LL;
  }
  if ( a3 == 34 )
  {
    v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    v39 = a1 + 184;
    goto LABEL_62;
  }
  if ( a3 > 16 )
  {
    if ( a3 > 26 )
    {
      v57 = a3 - 28;
      if ( v57 )
      {
        v58 = v57 - 1;
        if ( !v58 )
        {
          v66 = *(_DWORD *)(a4 + 32);
          if ( v66 >= 0x3C )
          {
            *(_DWORD *)(a1 + 156) = v66;
            return v14;
          }
          return 2147750680LL;
        }
        v59 = v58 - 1;
        if ( !v59 )
        {
          if ( (unsigned __int16)(*(_WORD *)(a4 + 32) - 1) <= 0x1Fu )
          {
            *(_DWORD *)(a1 + 152) = *(unsigned __int16 *)(a4 + 32);
            return v14;
          }
          return 2147750680LL;
        }
        v60 = v59 - 1;
        if ( v60 )
        {
          if ( v60 != 2 )
            return v14;
          v61 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          _bstr_t::operator=(a1 + 192, v61);
          _bstr_t::_Free((_bstr_t *)v185);
          if ( _bstr_t::length((_bstr_t *)(a1 + 192)) && _bstr_t::length((_bstr_t *)(a1 + 184)) )
          {
            v62 = *(_QWORD *)(a1 + 184);
            v185[0] = v62;
            if ( v62 )
              _InterlockedAdd((volatile signed __int32 *)(v62 + 16), 1u);
            v63 = *(_QWORD *)(a1 + 192);
            v185[1] = v63;
            if ( v63 )
              _InterlockedAdd((volatile signed __int32 *)(v63 + 16), 1u);
            v64 = std::_Tree_buy<std::pair<_bstr_t const,_bstr_t>>::_Buynode<std::pair<_bstr_t,_bstr_t>>(a1 + 168, v185);
            std::_Tree<std::_Tmap_traits<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>,0>>::_Insert_nohint<std::pair<_bstr_t const,_bstr_t> &,std::_Tree_node<std::pair<_bstr_t const,_bstr_t>,void *> *>(
              a1 + 168,
              &v186,
              v65,
              v64 + 32,
              v64);
            std::pair<_bstr_t const,_bstr_t>::~pair<_bstr_t const,_bstr_t>((_bstr_t *)v185);
            v185[0] = 0;
            _bstr_t::operator=(a1 + 184, v185);
            _bstr_t::_Free((_bstr_t *)v185);
            v185[0] = 0;
            v50 = v185;
            v39 = a1 + 192;
            goto LABEL_63;
          }
          return 2147750680LL;
        }
        v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
        v39 = a1 + 160;
      }
      else
      {
        v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
        v39 = a1 + 144;
      }
LABEL_62:
      v50 = (_QWORD *)v38;
LABEL_63:
      _bstr_t::operator=(v39, v50);
LABEL_64:
      v23 = (_bstr_t *)v185;
      goto LABEL_23;
    }
    if ( a3 == 26 )
    {
      v49 = *(_DWORD *)(a4 + 32);
      if ( v49 > 0x28DE80 )
        return 2147750680LL;
      goto LABEL_60;
    }
    v45 = a3 - 17;
    if ( !v45 )
    {
      if ( (unsigned __int8)TSTime::operator<(a1 + 312, a4) )
        return 2147750680LL;
      *(_OWORD *)(a1 + 208) = *(_OWORD *)a4;
      *(_OWORD *)(a1 + 296) = *(_OWORD *)a4;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v14;
      v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v39 = a1 + 384;
      goto LABEL_62;
    }
    v46 = v45 - 1;
    if ( !v46 )
    {
      if ( (unsigned __int8)TSTime::operator<(a4, a1 + 296) )
        return 2147750680LL;
      *(_OWORD *)(a1 + 224) = *(_OWORD *)a4;
      *(_OWORD *)(a1 + 312) = *(_OWORD *)a4;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v14;
      v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v39 = a1 + 392;
      goto LABEL_62;
    }
    v47 = v46 - 1;
    if ( v47 )
    {
      v48 = v47 - 1;
      if ( !v48 )
      {
        if ( !*(_DWORD *)(a1 + 112) )
        {
          v51 = *(JobBucket **)(a1 + 40);
          v52 = *(_DWORD *)(a4 + 32);
          JobBucket::InitOptionalSettings(v51);
          *(_DWORD *)(*((_QWORD *)v51 + 26) + 8LL) = v52;
          return v14;
        }
        *(_DWORD *)(a1 + 136) = *(_DWORD *)(a4 + 32);
        if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
          return v14;
        v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
        v39 = a1 + 376;
        goto LABEL_62;
      }
      if ( v48 != 2 )
        return v14;
      v49 = *(_DWORD *)(a4 + 32);
LABEL_60:
      *(_DWORD *)(a1 + 132) = v49;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v14;
      v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v39 = a1 + 368;
      goto LABEL_62;
    }
    v53 = *(_BYTE *)(a4 + 32);
    if ( *(_DWORD *)(a1 + 112) )
    {
      *(_BYTE *)(a1 + 128) = v53;
      *(_BYTE *)(a1 + 281) = *(_BYTE *)(a4 + 32);
      return v14;
    }
    v54 = *(_QWORD *)(a1 + 40);
    v55 = *(_DWORD *)(v54 + 16);
    if ( v53 )
      v56 = v55 | 0x400000;
    else
      v56 = v55 & 0xFFBFFFFF;
LABEL_185:
    *(_DWORD *)(v54 + 16) = v56;
    return v14;
  }
  if ( a3 == 16 )
  {
    *(_BYTE *)(a1 + 280) = *(_BYTE *)(a4 + 32);
    return v14;
  }
  if ( a3 > 8 )
  {
    v32 = a3 - 9;
    if ( !v32 )
    {
      v44 = *(_QWORD *)(a1 + 40);
      v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v21 = v44 + 112;
      goto LABEL_22;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      v43 = *(_QWORD *)(a1 + 40);
      v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v21 = v43 + 144;
      goto LABEL_22;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      v42 = *(_QWORD *)(a1 + 40);
      v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
      v21 = v42 + 152;
      goto LABEL_22;
    }
    v35 = v34 - 3;
    if ( v35 )
    {
      if ( v35 != 1 )
        return v14;
      v36 = *(_DWORD *)(a4 + 32);
      if ( v36 >= 0x3C )
      {
        v37 = *(_DWORD *)(a1 + 256);
        if ( !v37 || v37 <= v36 )
        {
          *(_DWORD *)(a1 + 260) = v36;
          if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
            return v14;
          v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
          v39 = a1 + 408;
          goto LABEL_62;
        }
      }
      return 2147750680LL;
    }
    v40 = *(_DWORD *)(a4 + 32);
    if ( v40 - 60 > 0x28DE44 )
      return 2147750680LL;
    v41 = *(_DWORD *)(a1 + 260);
    if ( v41 )
    {
      if ( v41 < v40 )
        return 2147750680LL;
    }
    *(_DWORD *)(a1 + 256) = v40;
    if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
      return v14;
    v38 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    v39 = a1 + 400;
    goto LABEL_62;
  }
  if ( a3 == 8 )
  {
    v31 = *(_QWORD *)(a1 + 40);
    v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    v21 = v31 + 136;
    goto LABEL_22;
  }
  v15 = a3 - 2;
  if ( !v15 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 96LL) = *(_DWORD *)(a4 + 32);
    if ( *(_DWORD *)(a4 + 32) == 0x10000 || *(_DWORD *)(a4 + 32) == 65537 )
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 16LL) |= 0x200000u;
    return v14;
  }
  v16 = v15 - 2;
  if ( !v16 )
  {
    v28 = *(_QWORD *)(a1 + 40);
    v29 = (_bstr_t *)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    _bstr_t::operator=(v28 + 160, v29);
    _bstr_t::_Free(v29);
    v27 = *(ATL::CComBSTR **)(a1 + 56);
LABEL_27:
    if ( v27 )
    {
      v30 = XmlParserTempString::DetachBstr(*(XmlParserTempString **)(a4 + 48));
      ATL::CComBSTR::Attach(v27, v30);
    }
    return v14;
  }
  v17 = v16 - 1;
  if ( !v17 )
  {
    v25 = *(_QWORD *)(a1 + 40);
    v26 = (_bstr_t *)XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    _bstr_t::operator=(v25 + 120, v26);
    _bstr_t::_Free(v26);
    v27 = *(ATL::CComBSTR **)(a1 + 64);
    goto LABEL_27;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    v24 = *(_QWORD *)(a1 + 40);
    v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    v21 = v24 + 128;
    goto LABEL_22;
  }
  if ( v18 == 1 )
  {
    v19 = *(_QWORD *)(a1 + 40);
    v20 = XmlParserTempString::GetCopy(*(_QWORD *)(a4 + 48), v185);
    v21 = v19 + 104;
LABEL_22:
    v22 = (_bstr_t *)v20;
    _bstr_t::operator=(v21, v20);
    v23 = v22;
LABEL_23:
    _bstr_t::_Free(v23);
  }
  return v14;
}

```

## disassembly

```asm
0x180050690  mov     rax, rsp
0x180050693  push    rbp
0x180050694  push    rbx
0x180050695  push    rsi
0x180050696  push    rdi
0x180050697  push    r12
0x180050699  push    r13
0x18005069b  push    r14
0x18005069d  push    r15
0x18005069f  lea     rbp, [rax-57h]
0x1800506a3  sub     rsp, 0D8h
0x1800506aa  movaps  xmmword ptr [rax-58h], xmm6
0x1800506ae  mov     rax, cs:__security_cookie
0x1800506b5  xor     rax, rsp
0x1800506b8  mov     [rbp+4Fh+var_60], rax
0x1800506bc  mov     r14, r9
0x1800506bf  mov     ebx, r8d
0x1800506c2  mov     r12, rdx
0x1800506c5  mov     rsi, rcx
0x1800506c8  lea     rax, WPP_GLOBAL_Control
0x1800506cf  xor     r13d, r13d
0x1800506d2  mov     r11, cs:WPP_GLOBAL_Control
0x1800506d9  cmp     r11, rax
0x1800506dc  jz      short loc_18005071E
0x1800506de  test    byte ptr [r11+1Ch], 80h
0x1800506e3  jz      short loc_18005071E
0x1800506e5  cmp     byte ptr [r11+19h], 5
0x1800506ea  jb      short loc_18005071E
0x1800506ec  mov     rax, [r9+30h]
0x1800506f0  test    rax, rax
0x1800506f3  jz      short loc_1800506FB
0x1800506f5  mov     rdi, [rax+8]
0x1800506f9  jmp     short loc_180050702
0x1800506fb  lea     rdi, aNull; "null"
0x180050702  mov     edx, ebx
0x180050704  mov     rcx, r12
0x180050707  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x18005070c  mov     [rsp+20h], rdi
0x180050711  mov     r9, [rax+8]
0x180050715  mov     rcx, [r11+10h]
0x180050719  call    WPP_SF_SS
0x18005071e  mov     r15d, r13d
0x180050721  xorps   xmm0, xmm0
0x180050724  movups  xmmword ptr [rbp+4Fh+iid.Data1], xmm0
0x180050728  cmp     ebx, 44h ; 'D'
0x18005072b  jg      loc_180050FC9
0x180050731  jz      loc_180050F94
0x180050737  cmp     ebx, 22h ; '"'
0x18005073a  jg      loc_180050D2D
0x180050740  jz      loc_180050D13
0x180050746  cmp     ebx, 10h
0x180050749  jg      loc_1800509CF
0x18005074f  jz      loc_1800509C0
0x180050755  cmp     ebx, 8
0x180050758  jg      loc_18005089F
0x18005075e  jz      loc_180050881
0x180050764  sub     ebx, 2
0x180050767  jz      loc_180050853
0x18005076d  sub     ebx, 2
0x180050770  jz      loc_180050801
0x180050776  sub     ebx, 1
0x180050779  jz      short loc_1800507D2
0x18005077b  sub     ebx, 1
0x18005077e  jz      short loc_1800507B7
0x180050780  cmp     ebx, 1
0x180050783  jnz     loc_1800519E2
0x180050789  mov     rdi, [rsi+28h]
0x18005078d  lea     rdx, [rsp+110h+var_E0]
0x180050792  mov     rcx, [r14+30h]
0x180050796  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18005079b  lea     rcx, [rdi+68h]
0x18005079f  mov     rbx, rax
0x1800507a2  mov     rdx, rax
0x1800507a5  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800507aa  mov     rcx, rbx; this
0x1800507ad  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800507b2  jmp     loc_1800519E2
0x1800507b7  mov     rdi, [rsi+28h]
0x1800507bb  lea     rdx, [rsp+110h+var_E0]
0x1800507c0  mov     rcx, [r14+30h]
0x1800507c4  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800507c9  lea     rcx, [rdi+80h]
0x1800507d0  jmp     short loc_18005079F
0x1800507d2  mov     rdi, [rsi+28h]
0x1800507d6  lea     rdx, [rsp+110h+var_E0]
0x1800507db  mov     rcx, [r14+30h]
0x1800507df  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800507e4  mov     rbx, rax
0x1800507e7  lea     rcx, [rdi+78h]
0x1800507eb  mov     rdx, rax
0x1800507ee  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x1800507f3  mov     rcx, rbx; this
0x1800507f6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800507fb  mov     rbx, [rsi+40h]
0x1800507ff  jmp     short loc_180050831
0x180050801  mov     rdi, [rsi+28h]
0x180050805  lea     rdx, [rsp+110h+var_E0]
0x18005080a  mov     rcx, [r14+30h]
0x18005080e  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050813  mov     rbx, rax
0x180050816  lea     rcx, [rdi+0A0h]
0x18005081d  mov     rdx, rax
0x180050820  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180050825  mov     rcx, rbx; this
0x180050828  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18005082d  mov     rbx, [rsi+38h]
0x180050831  test    rbx, rbx
0x180050834  jz      loc_1800519E2
0x18005083a  mov     rcx, [r14+30h]; this
0x18005083e  call    ?DetachBstr@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::DetachBstr(void)
0x180050843  mov     rdx, rax; unsigned __int16 *
0x180050846  mov     rcx, rbx; this
0x180050849  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18005084e  jmp     loc_1800519E2
0x180050853  mov     rcx, [rsi+28h]
0x180050857  mov     eax, [r14+20h]
0x18005085b  mov     [rcx+60h], eax
0x18005085e  mov     ecx, [r14+20h]
0x180050862  sub     ecx, 10000h
0x180050868  jz      short loc_180050873
0x18005086a  cmp     ecx, 1
0x18005086d  jnz     loc_1800519E2
0x180050873  mov     rax, [rsi+28h]
0x180050877  bts     dword ptr [rax+10h], 15h
0x18005087c  jmp     loc_1800519E2
0x180050881  mov     rdi, [rsi+28h]
0x180050885  lea     rdx, [rsp+110h+var_E0]
0x18005088a  mov     rcx, [r14+30h]
0x18005088e  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050893  lea     rcx, [rdi+88h]
0x18005089a  jmp     loc_18005079F
0x18005089f  sub     ebx, 9
0x1800508a2  jz      loc_1800509A5
0x1800508a8  sub     ebx, 1
0x1800508ab  jz      loc_180050987
0x1800508b1  sub     ebx, 1
0x1800508b4  jz      loc_180050969
0x1800508ba  sub     ebx, 3
0x1800508bd  jz      short loc_180050916
0x1800508bf  cmp     ebx, 1
0x1800508c2  jnz     loc_1800519E2
0x1800508c8  mov     eax, [r14+20h]
0x1800508cc  cmp     eax, 3Ch ; '<'
0x1800508cf  jb      loc_180050E37
0x1800508d5  mov     ecx, [rsi+100h]
0x1800508db  test    ecx, ecx
0x1800508dd  jz      short loc_1800508E7
0x1800508df  cmp     ecx, eax
0x1800508e1  ja      loc_180050E37
0x1800508e7  mov     [rsi+104h], eax
0x1800508ed  mov     edi, 1
0x1800508f2  test    [rsi+30h], dil
0x1800508f6  jz      loc_1800519E2
0x1800508fc  lea     rdx, [rsp+110h+var_E0]
0x180050901  mov     rcx, [r14+30h]
0x180050905  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18005090a  lea     rcx, [rsi+198h]
0x180050911  jmp     loc_180050A35
0x180050916  mov     ecx, [r14+20h]
0x18005091a  lea     eax, [rcx-3Ch]
0x18005091d  cmp     eax, 28DE44h
0x180050922  ja      loc_180050E37
0x180050928  mov     eax, [rsi+104h]
0x18005092e  test    eax, eax
0x180050930  jz      short loc_18005093A
0x180050932  cmp     eax, ecx
0x180050934  jb      loc_180050E37
0x18005093a  mov     [rsi+100h], ecx
0x180050940  mov     edi, 1
0x180050945  test    [rsi+30h], dil
0x180050949  jz      loc_1800519E2
0x18005094f  lea     rdx, [rsp+110h+var_E0]
0x180050954  mov     rcx, [r14+30h]
0x180050958  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18005095d  lea     rcx, [rsi+190h]
0x180050964  jmp     loc_180050A35
0x180050969  mov     rdi, [rsi+28h]
0x18005096d  lea     rdx, [rsp+110h+var_E0]
0x180050972  mov     rcx, [r14+30h]
0x180050976  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18005097b  lea     rcx, [rdi+98h]
0x180050982  jmp     loc_18005079F
0x180050987  mov     rdi, [rsi+28h]
0x18005098b  lea     rdx, [rsp+110h+var_E0]
0x180050990  mov     rcx, [r14+30h]
0x180050994  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050999  lea     rcx, [rdi+90h]
0x1800509a0  jmp     loc_18005079F
0x1800509a5  mov     rdi, [rsi+28h]
0x1800509a9  lea     rdx, [rsp+110h+var_E0]
0x1800509ae  mov     rcx, [r14+30h]
0x1800509b2  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x1800509b7  lea     rcx, [rdi+70h]
0x1800509bb  jmp     loc_18005079F
0x1800509c0  mov     al, [r14+20h]
0x1800509c4  mov     [rsi+118h], al
0x1800509ca  jmp     loc_1800519E2
0x1800509cf  cmp     ebx, 1Ah
0x1800509d2  jg      loc_180050B9C
0x1800509d8  jz      loc_180050B88
0x1800509de  sub     ebx, 11h
0x1800509e1  jz      loc_180050B30
0x1800509e7  sub     ebx, 1
0x1800509ea  jz      loc_180050AD8
0x1800509f0  sub     ebx, 1
0x1800509f3  jz      loc_180050A9C
0x1800509f9  sub     ebx, 1
0x1800509fc  jz      short loc_180050A47
0x1800509fe  cmp     ebx, 2
0x180050a01  jnz     loc_1800519E2
0x180050a07  mov     eax, [r14+20h]
0x180050a0b  mov     [rsi+84h], eax
0x180050a11  mov     edi, 1
0x180050a16  test    [rsi+30h], dil
0x180050a1a  jz      loc_1800519E2
0x180050a20  lea     rdx, [rsp+110h+var_E0]
0x180050a25  mov     rcx, [r14+30h]
0x180050a29  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050a2e  lea     rcx, [rsi+170h]
0x180050a35  mov     rdx, rax
0x180050a38  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180050a3d  lea     rcx, [rsp+110h+var_E0]
0x180050a42  jmp     loc_1800507AD
0x180050a47  cmp     [rsi+70h], r13d
0x180050a4b  jz      short loc_180050A7D
0x180050a4d  mov     eax, [r14+20h]
0x180050a51  mov     [rsi+88h], eax
0x180050a57  mov     edi, 1
0x180050a5c  test    [rsi+30h], dil
0x180050a60  jz      loc_1800519E2
0x180050a66  lea     rdx, [rsp+110h+var_E0]
0x180050a6b  mov     rcx, [r14+30h]
0x180050a6f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050a74  lea     rcx, [rsi+178h]
0x180050a7b  jmp     short loc_180050A35
0x180050a7d  mov     rbx, [rsi+28h]
0x180050a81  mov     edi, [r14+20h]
0x180050a85  mov     rcx, rbx; this
0x180050a88  call    ?InitOptionalSettings@JobBucket@@IEAAXXZ; JobBucket::InitOptionalSettings(void)
0x180050a8d  mov     rax, [rbx+0D0h]
0x180050a94  mov     [rax+8], edi
0x180050a97  jmp     loc_1800519E2
0x180050a9c  mov     dl, [r14+20h]
0x180050aa0  cmp     [rsi+70h], r13d
0x180050aa4  jz      short loc_180050ABB
0x180050aa6  mov     [rsi+80h], dl
0x180050aac  mov     al, [r14+20h]
0x180050ab0  mov     [rsi+119h], al
0x180050ab6  jmp     loc_1800519E2
0x180050abb  mov     rcx, [rsi+28h]
0x180050abf  mov     eax, [rcx+10h]
0x180050ac2  test    dl, dl
0x180050ac4  jz      short loc_180050ACF
0x180050ac6  bts     eax, 16h
0x180050aca  jmp     loc_180051079
0x180050acf  btr     eax, 16h
0x180050ad3  jmp     loc_180051079
0x180050ad8  lea     rdx, [rsi+128h]
0x180050adf  mov     rcx, r14
0x180050ae2  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180050ae7  test    al, al
0x180050ae9  jnz     loc_180050E37
0x180050aef  movups  xmm0, xmmword ptr [r14]
0x180050af3  movdqu  xmmword ptr [rsi+0E0h], xmm0
0x180050afb  movups  xmm1, xmmword ptr [r14]
0x180050aff  movdqu  xmmword ptr [rsi+138h], xmm1
0x180050b07  mov     edi, 1
0x180050b0c  test    [rsi+30h], dil
0x180050b10  jz      loc_1800519E2
0x180050b16  lea     rdx, [rsp+110h+var_E0]
0x180050b1b  mov     rcx, [r14+30h]
0x180050b1f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050b24  lea     rcx, [rsi+188h]
0x180050b2b  jmp     loc_180050A35
0x180050b30  lea     rcx, [rsi+138h]
0x180050b37  mov     rdx, r14
0x180050b3a  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180050b3f  test    al, al
0x180050b41  jnz     loc_180050E37
0x180050b47  movups  xmm0, xmmword ptr [r14]
0x180050b4b  movdqu  xmmword ptr [rsi+0D0h], xmm0
0x180050b53  movups  xmm1, xmmword ptr [r14]
0x180050b57  movdqu  xmmword ptr [rsi+128h], xmm1
0x180050b5f  mov     edi, 1
0x180050b64  test    [rsi+30h], dil
0x180050b68  jz      loc_1800519E2
0x180050b6e  lea     rdx, [rsp+110h+var_E0]
0x180050b73  mov     rcx, [r14+30h]
0x180050b77  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180050b7c  lea     rcx, [rsi+180h]
0x180050b83  jmp     loc_180050A35
0x180050b88  mov     eax, [r14+20h]
0x180050b8c  cmp     eax, 28DE80h
0x180050b91  ja      loc_180050E37
0x180050b97  jmp     loc_180050A0B
0x180050b9c  sub     ebx, 1Ch
0x180050b9f  jz      loc_180050CF9
0x180050ba5  sub     ebx, 1
0x180050ba8  jz      loc_180050CE1
0x180050bae  sub     ebx, 1
  ... truncated ...
```
