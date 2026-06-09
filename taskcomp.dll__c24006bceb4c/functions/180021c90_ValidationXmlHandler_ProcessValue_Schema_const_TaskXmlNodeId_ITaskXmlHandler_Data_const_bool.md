# ValidationXmlHandler::ProcessValue(Schema const &,TaskXmlNodeId,ITaskXmlHandler::Data const &,bool)

- ea: `0x180021c90`
- end: `0x18002300b`
- name: `?ProcessValue@ValidationXmlHandler@@MEAAJAEBUSchema@@W4TaskXmlNodeId@@AEBUData@ITaskXmlHandler@@_N@Z`
- size: `4987`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d130`

## callees

- `0x180003250`
- `0x180003af0`
- `0x180003dac`
- `0x180003ec0`
- `0x180004e50`
- `0x180004fe4`
- `0x1800050fc`
- `0x18000518c`
- `0x180005f7c`
- `0x1800074d4`
- `0x1800087a6`
- `0x18000a390`
- `0x18000a42c`
- `0x18000c7a0`
- `0x180010360`
- `0x18001a6b8`
- `0x18001ad80`
- `0x18001bc8c`
- `0x18001bd78`
- `0x18001be00`
- `0x18001d4c4`
- `0x180020a78`
- `0x180020d94`
- `0x180021018`
- `0x180021088`
- `0x180021c90`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002287b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800228c3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002287b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800228c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ValidationXmlHandler::ProcessValue(__int64 a1, int *a2, int a3, __int64 a4)
{
  _QWORD *v8; // rdi
  __int64 v9; // rax
  const wchar_t *v10; // r15
  __int64 *Entry; // rax
  unsigned int v12; // r15d
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  __int64 v17; // rdi
  _bstr_t *v18; // rax
  _bstr_t *v19; // rcx
  _bstr_t *v20; // rbx
  _bstr_t *v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // rdi
  _bstr_t *v24; // rbx
  BSTR *v25; // rbx
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
  _bstr_t *v36; // rax
  _bstr_t *v37; // rcx
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
  _bstr_t *v48; // rdx
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
  _bstr_t *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // r8
  unsigned int v64; // eax
  __int16 v65; // cx
  bool v66; // cc
  const OLECHAR **v67; // rcx
  _bstr_t *v68; // rax
  const WCHAR **v69; // rdx
  const WCHAR *v70; // rdx
  _bstr_t *v72; // rax
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
  _bstr_t *v131; // rax
  const unsigned __int16 ***v132; // r12
  unsigned int v133; // eax
  XmlParserTempString *v134; // r13
  unsigned __int64 v135; // r8
  const unsigned __int16 *v136; // rdx
  _bstr_t *v137; // rax
  _bstr_t *v138; // rax
  char v139; // al
  const OLECHAR **v140; // rcx
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
  _bstr_t *Copy; // rax
  const unsigned __int16 *v177; // rdx
  __int64 v178; // rbx
  _QWORD *v179; // rax
  _bstr_t *v180; // rax
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
    Entry = Schema::GetEntry(a2, a3);
    WPP_SF_SS(v8[2], 11, (unsigned int)WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids, Entry[1], (__int64)v10);
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
            Copy = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
            if ( *(_QWORD *)Copy )
              v177 = **(const unsigned __int16 ***)Copy;
            else
              v177 = 0;
            JobBucket::AddCapability(v175, v177);
            goto LABEL_64;
          }
          v178 = *(_QWORD *)(a1 + 40);
          v179 = *(_QWORD **)(v178 + 176);
          if ( !v179 || !*v179 )
          {
            v180 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
            if ( *(_QWORD *)v180 )
              v181 = **(_QWORD **)v180;
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
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 448);
          goto LABEL_62;
        }
        v143 = v142 - 1;
        if ( !v143 )
        {
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 456);
          goto LABEL_62;
        }
        v144 = v143 - 1;
        if ( !v144 )
        {
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 464);
          goto LABEL_62;
        }
        v145 = v144 - 2;
        if ( !v145 )
        {
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 472);
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
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 88);
          goto LABEL_62;
        case 'h':
          v140 = *(const OLECHAR ***)(a4 + 48);
          v141 = 0;
          if ( (unsigned int)(*(_DWORD *)v140 - 1) > 0x103 )
            v141 = -2147216616;
          v12 = v141;
          v36 = XmlParserTempString::GetCopy(v140, (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 480);
          goto LABEL_62;
        case 'j':
          if ( (unsigned int)(**(_DWORD **)(a4 + 48) - 1) <= 0x103 )
            return v12;
          return (unsigned int)-2147216616;
        case 'm':
          XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          if ( *(_DWORD *)(a1 + 112) )
            _bstr_t::operator=((_bstr_t *)(a1 + 120), (__int64)v183);
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
              v131 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
              _bstr_t::operator=((_bstr_t *)(a1 + 72), (__int64)v131);
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
          v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v19 = (_bstr_t *)(v124 + 168);
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
        v137 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
        _bstr_t::operator=((_bstr_t *)(a1 + 80), (__int64)v137);
LABEL_272:
        _bstr_t::~_bstr_t((_bstr_t *)v183);
        return 2147750680LL;
      }
    }
    else
    {
      v138 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      _bstr_t::operator=((_bstr_t *)(a1 + 80), (__int64)v138);
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
        v67 = *(const OLECHAR ***)(a4 + 48);
        if ( *(_DWORD *)(a1 + 112) )
        {
          v68 = XmlParserTempString::GetCopy(v67, (_bstr_t *)v183);
          _bstr_t::operator=((_bstr_t *)(a1 + 200), (__int64)v68);
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
        v72 = XmlParserTempString::GetCopy(v67, (_bstr_t *)v183);
        v73 = (const WCHAR ***)(a1 + 72);
        _bstr_t::operator=((_bstr_t *)(a1 + 72), (__int64)v72);
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
    v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    v37 = (_bstr_t *)(a1 + 184);
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
          v59 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          _bstr_t::operator=((_bstr_t *)(a1 + 192), (__int64)v59);
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
            _bstr_t::operator=((_bstr_t *)(a1 + 184), (__int64)v183);
            _bstr_t::~_bstr_t((_bstr_t *)v183);
            v183[0] = 0;
            v48 = (_bstr_t *)v183;
            v37 = (_bstr_t *)(a1 + 192);
            goto LABEL_63;
          }
          return 2147750680LL;
        }
        v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
        v37 = (_bstr_t *)(a1 + 160);
      }
      else
      {
        v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
        v37 = (_bstr_t *)(a1 + 144);
      }
LABEL_62:
      v48 = v36;
LABEL_63:
      _bstr_t::operator=(v37, (__int64)v48);
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
      v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v37 = (_bstr_t *)(a1 + 384);
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
      v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v37 = (_bstr_t *)(a1 + 392);
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
        v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
        v37 = (_bstr_t *)(a1 + 376);
        goto LABEL_62;
      }
      if ( v46 != 2 )
        return v12;
      v47 = *(_DWORD *)(a4 + 32);
LABEL_60:
      *(_DWORD *)(a1 + 132) = v47;
      if ( (*(_BYTE *)(a1 + 48) & 1) == 0 )
        return v12;
      v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v37 = (_bstr_t *)(a1 + 368);
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
      v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v19 = (_bstr_t *)(v42 + 112);
      goto LABEL_22;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      v41 = *(_QWORD *)(a1 + 40);
      v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v19 = (_bstr_t *)(v41 + 144);
      goto LABEL_22;
    }
    v32 = v31 - 1;
    if ( !v32 )
    {
      v40 = *(_QWORD *)(a1 + 40);
      v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
      v19 = (_bstr_t *)(v40 + 152);
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
          v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
          v37 = (_bstr_t *)(a1 + 408);
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
    v36 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    v37 = (_bstr_t *)(a1 + 400);
    goto LABEL_62;
  }
  if ( a3 == 8 )
  {
    v29 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    v19 = (_bstr_t *)(v29 + 136);
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
    v27 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    _bstr_t::operator=((_bstr_t *)(v26 + 160), (__int64)v27);
    _bstr_t::~_bstr_t(v27);
    v25 = *(BSTR **)(a1 + 56);
LABEL_27:
    if ( v25 )
    {
      v28 = XmlParserTempString::DetachBstr(*(const OLECHAR ***)(a4 + 48));
      ATL::CComBSTR::Attach(v25, v28);
    }
    return v12;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v23 = *(_QWORD *)(a1 + 40);
    v24 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    _bstr_t::operator=((_bstr_t *)(v23 + 120), (__int64)v24);
    _bstr_t::~_bstr_t(v24);
    v25 = *(BSTR **)(a1 + 64);
    goto LABEL_27;
  }
  v16 = v15 - 1;
  if ( !v16 )
  {
    v22 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    v19 = (_bstr_t *)(v22 + 128);
    goto LABEL_22;
  }
  if ( v16 == 1 )
  {
    v17 = *(_QWORD *)(a1 + 40);
    v18 = XmlParserTempString::GetCopy(*(const OLECHAR ***)(a4 + 48), (_bstr_t *)v183);
    v19 = (_bstr_t *)(v17 + 104);
LABEL_22:
    v20 = v18;
    _bstr_t::operator=(v19, (__int64)v18);
    v21 = v20;
LABEL_23:
    _bstr_t::~_bstr_t(v21);
  }
  return v12;
}

```

## disassembly

```asm
0x180021c90  mov     rax, rsp
0x180021c93  push    rbp
0x180021c94  push    rbx
0x180021c95  push    rsi
0x180021c96  push    rdi
0x180021c97  push    r12
0x180021c99  push    r13
0x180021c9b  push    r14
0x180021c9d  push    r15
0x180021c9f  lea     rbp, [rax-57h]
0x180021ca3  sub     rsp, 0D8h
0x180021caa  movaps  xmmword ptr [rax-58h], xmm6
0x180021cae  mov     rax, cs:__security_cookie
0x180021cb5  xor     rax, rsp
0x180021cb8  mov     [rbp+4Fh+var_60], rax
0x180021cbc  mov     r14, r9
0x180021cbf  mov     ebx, r8d
0x180021cc2  mov     r12, rdx
0x180021cc5  mov     rsi, rcx
0x180021cc8  lea     rax, WPP_GLOBAL_Control
0x180021ccf  xor     r13d, r13d
0x180021cd2  mov     rdi, cs:WPP_GLOBAL_Control
0x180021cd9  cmp     rdi, rax
0x180021cdc  jz      short loc_180021D28
0x180021cde  test    byte ptr [rdi+1Ch], 80h
0x180021ce2  jz      short loc_180021D28
0x180021ce4  cmp     byte ptr [rdi+19h], 5
0x180021ce8  jb      short loc_180021D28
0x180021cea  mov     rax, [r9+30h]
0x180021cee  test    rax, rax
0x180021cf1  jz      short loc_180021CF9
0x180021cf3  mov     r15, [rax+8]
0x180021cf7  jmp     short loc_180021D00
0x180021cf9  lea     r15, aNull; "null"
0x180021d00  mov     edx, ebx
0x180021d02  mov     rcx, r12
0x180021d05  call    ?GetEntry@Schema@@AEBAAEBUSchemaEntry@@W4TaskXmlNodeId@@@Z; Schema::GetEntry(TaskXmlNodeId)
0x180021d0a  mov     edx, 0Bh
0x180021d0f  mov     [rsp+20h], r15
0x180021d14  mov     r9, [rax+8]
0x180021d18  lea     r8, WPP_66bc7a8e9c2933fa102678c8dfb90698_Traceguids
0x180021d1f  mov     rcx, [rdi+10h]
0x180021d23  call    WPP_SF_SS
0x180021d28  mov     r15d, r13d
0x180021d2b  xorps   xmm0, xmm0
0x180021d2e  movups  xmmword ptr [rbp+4Fh+iid.Data1], xmm0
0x180021d32  cmp     ebx, 44h ; 'D'
0x180021d35  jg      loc_1800225D3
0x180021d3b  jz      loc_18002259E
0x180021d41  cmp     ebx, 22h ; '"'
0x180021d44  jg      loc_180022337
0x180021d4a  jz      loc_18002231D
0x180021d50  cmp     ebx, 10h
0x180021d53  jg      loc_180021FD9
0x180021d59  jz      loc_180021FCA
0x180021d5f  cmp     ebx, 8
0x180021d62  jg      loc_180021EA9
0x180021d68  jz      loc_180021E8B
0x180021d6e  sub     ebx, 2
0x180021d71  jz      loc_180021E5D
0x180021d77  sub     ebx, 2
0x180021d7a  jz      loc_180021E0B
0x180021d80  sub     ebx, 1
0x180021d83  jz      short loc_180021DDC
0x180021d85  sub     ebx, 1
0x180021d88  jz      short loc_180021DC1
0x180021d8a  cmp     ebx, 1
0x180021d8d  jnz     loc_180022FE0
0x180021d93  mov     rdi, [rsi+28h]
0x180021d97  lea     rdx, [rsp+110h+var_E0]
0x180021d9c  mov     rcx, [r14+30h]
0x180021da0  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021da5  lea     rcx, [rdi+68h]
0x180021da9  mov     rbx, rax
0x180021dac  mov     rdx, rax
0x180021daf  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180021db4  mov     rcx, rbx; this
0x180021db7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180021dbc  jmp     loc_180022FE0
0x180021dc1  mov     rdi, [rsi+28h]
0x180021dc5  lea     rdx, [rsp+110h+var_E0]
0x180021dca  mov     rcx, [r14+30h]
0x180021dce  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021dd3  lea     rcx, [rdi+80h]
0x180021dda  jmp     short loc_180021DA9
0x180021ddc  mov     rdi, [rsi+28h]
0x180021de0  lea     rdx, [rsp+110h+var_E0]
0x180021de5  mov     rcx, [r14+30h]
0x180021de9  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021dee  mov     rbx, rax
0x180021df1  lea     rcx, [rdi+78h]
0x180021df5  mov     rdx, rax
0x180021df8  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180021dfd  mov     rcx, rbx; this
0x180021e00  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180021e05  mov     rbx, [rsi+40h]
0x180021e09  jmp     short loc_180021E3B
0x180021e0b  mov     rdi, [rsi+28h]
0x180021e0f  lea     rdx, [rsp+110h+var_E0]
0x180021e14  mov     rcx, [r14+30h]
0x180021e18  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021e1d  mov     rbx, rax
0x180021e20  lea     rcx, [rdi+0A0h]
0x180021e27  mov     rdx, rax
0x180021e2a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180021e2f  mov     rcx, rbx; this
0x180021e32  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180021e37  mov     rbx, [rsi+38h]
0x180021e3b  test    rbx, rbx
0x180021e3e  jz      loc_180022FE0
0x180021e44  mov     rcx, [r14+30h]; this
0x180021e48  call    ?DetachBstr@XmlParserTempString@@QEAAPEAGXZ; XmlParserTempString::DetachBstr(void)
0x180021e4d  mov     rdx, rax; unsigned __int16 *
0x180021e50  mov     rcx, rbx; this
0x180021e53  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x180021e58  jmp     loc_180022FE0
0x180021e5d  mov     rcx, [rsi+28h]
0x180021e61  mov     eax, [r14+20h]
0x180021e65  mov     [rcx+60h], eax
0x180021e68  mov     ecx, [r14+20h]
0x180021e6c  sub     ecx, 10000h
0x180021e72  jz      short loc_180021E7D
0x180021e74  cmp     ecx, 1
0x180021e77  jnz     loc_180022FE0
0x180021e7d  mov     rax, [rsi+28h]
0x180021e81  bts     dword ptr [rax+10h], 15h
0x180021e86  jmp     loc_180022FE0
0x180021e8b  mov     rdi, [rsi+28h]
0x180021e8f  lea     rdx, [rsp+110h+var_E0]
0x180021e94  mov     rcx, [r14+30h]
0x180021e98  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021e9d  lea     rcx, [rdi+88h]
0x180021ea4  jmp     loc_180021DA9
0x180021ea9  sub     ebx, 9
0x180021eac  jz      loc_180021FAF
0x180021eb2  sub     ebx, 1
0x180021eb5  jz      loc_180021F91
0x180021ebb  sub     ebx, 1
0x180021ebe  jz      loc_180021F73
0x180021ec4  sub     ebx, 3
0x180021ec7  jz      short loc_180021F20
0x180021ec9  cmp     ebx, 1
0x180021ecc  jnz     loc_180022FE0
0x180021ed2  mov     eax, [r14+20h]
0x180021ed6  cmp     eax, 3Ch ; '<'
0x180021ed9  jb      loc_180022441
0x180021edf  mov     ecx, [rsi+100h]
0x180021ee5  test    ecx, ecx
0x180021ee7  jz      short loc_180021EF1
0x180021ee9  cmp     ecx, eax
0x180021eeb  ja      loc_180022441
0x180021ef1  mov     [rsi+104h], eax
0x180021ef7  mov     edi, 1
0x180021efc  test    [rsi+30h], dil
0x180021f00  jz      loc_180022FE0
0x180021f06  lea     rdx, [rsp+110h+var_E0]
0x180021f0b  mov     rcx, [r14+30h]
0x180021f0f  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021f14  lea     rcx, [rsi+198h]
0x180021f1b  jmp     loc_18002203F
0x180021f20  mov     ecx, [r14+20h]
0x180021f24  lea     eax, [rcx-3Ch]
0x180021f27  cmp     eax, 28DE44h
0x180021f2c  ja      loc_180022441
0x180021f32  mov     eax, [rsi+104h]
0x180021f38  test    eax, eax
0x180021f3a  jz      short loc_180021F44
0x180021f3c  cmp     eax, ecx
0x180021f3e  jb      loc_180022441
0x180021f44  mov     [rsi+100h], ecx
0x180021f4a  mov     edi, 1
0x180021f4f  test    [rsi+30h], dil
0x180021f53  jz      loc_180022FE0
0x180021f59  lea     rdx, [rsp+110h+var_E0]
0x180021f5e  mov     rcx, [r14+30h]
0x180021f62  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021f67  lea     rcx, [rsi+190h]
0x180021f6e  jmp     loc_18002203F
0x180021f73  mov     rdi, [rsi+28h]
0x180021f77  lea     rdx, [rsp+110h+var_E0]
0x180021f7c  mov     rcx, [r14+30h]
0x180021f80  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021f85  lea     rcx, [rdi+98h]
0x180021f8c  jmp     loc_180021DA9
0x180021f91  mov     rdi, [rsi+28h]
0x180021f95  lea     rdx, [rsp+110h+var_E0]
0x180021f9a  mov     rcx, [r14+30h]
0x180021f9e  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021fa3  lea     rcx, [rdi+90h]
0x180021faa  jmp     loc_180021DA9
0x180021faf  mov     rdi, [rsi+28h]
0x180021fb3  lea     rdx, [rsp+110h+var_E0]
0x180021fb8  mov     rcx, [r14+30h]
0x180021fbc  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180021fc1  lea     rcx, [rdi+70h]
0x180021fc5  jmp     loc_180021DA9
0x180021fca  mov     al, [r14+20h]
0x180021fce  mov     [rsi+118h], al
0x180021fd4  jmp     loc_180022FE0
0x180021fd9  cmp     ebx, 1Ah
0x180021fdc  jg      loc_1800221A6
0x180021fe2  jz      loc_180022192
0x180021fe8  sub     ebx, 11h
0x180021feb  jz      loc_18002213A
0x180021ff1  sub     ebx, 1
0x180021ff4  jz      loc_1800220E2
0x180021ffa  sub     ebx, 1
0x180021ffd  jz      loc_1800220A6
0x180022003  sub     ebx, 1
0x180022006  jz      short loc_180022051
0x180022008  cmp     ebx, 2
0x18002200b  jnz     loc_180022FE0
0x180022011  mov     eax, [r14+20h]
0x180022015  mov     [rsi+84h], eax
0x18002201b  mov     edi, 1
0x180022020  test    [rsi+30h], dil
0x180022024  jz      loc_180022FE0
0x18002202a  lea     rdx, [rsp+110h+var_E0]
0x18002202f  mov     rcx, [r14+30h]
0x180022033  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180022038  lea     rcx, [rsi+170h]
0x18002203f  mov     rdx, rax
0x180022042  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180022047  lea     rcx, [rsp+110h+var_E0]
0x18002204c  jmp     loc_180021DB7
0x180022051  cmp     [rsi+70h], r13d
0x180022055  jz      short loc_180022087
0x180022057  mov     eax, [r14+20h]
0x18002205b  mov     [rsi+88h], eax
0x180022061  mov     edi, 1
0x180022066  test    [rsi+30h], dil
0x18002206a  jz      loc_180022FE0
0x180022070  lea     rdx, [rsp+110h+var_E0]
0x180022075  mov     rcx, [r14+30h]
0x180022079  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002207e  lea     rcx, [rsi+178h]
0x180022085  jmp     short loc_18002203F
0x180022087  mov     rbx, [rsi+28h]
0x18002208b  mov     edi, [r14+20h]
0x18002208f  mov     rcx, rbx; this
0x180022092  call    ?InitOptionalSettings@JobBucket@@IEAAXXZ; JobBucket::InitOptionalSettings(void)
0x180022097  mov     rax, [rbx+0D0h]
0x18002209e  mov     [rax+8], edi
0x1800220a1  jmp     loc_180022FE0
0x1800220a6  mov     dl, [r14+20h]
0x1800220aa  cmp     [rsi+70h], r13d
0x1800220ae  jz      short loc_1800220C5
0x1800220b0  mov     [rsi+80h], dl
0x1800220b6  mov     al, [r14+20h]
0x1800220ba  mov     [rsi+119h], al
0x1800220c0  jmp     loc_180022FE0
0x1800220c5  mov     rcx, [rsi+28h]
0x1800220c9  mov     eax, [rcx+10h]
0x1800220cc  test    dl, dl
0x1800220ce  jz      short loc_1800220D9
0x1800220d0  bts     eax, 16h
0x1800220d4  jmp     loc_180022683
0x1800220d9  btr     eax, 16h
0x1800220dd  jmp     loc_180022683
0x1800220e2  lea     rdx, [rsi+128h]
0x1800220e9  mov     rcx, r14
0x1800220ec  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x1800220f1  test    al, al
0x1800220f3  jnz     loc_180022441
0x1800220f9  movups  xmm0, xmmword ptr [r14]
0x1800220fd  movdqu  xmmword ptr [rsi+0E0h], xmm0
0x180022105  movups  xmm1, xmmword ptr [r14]
0x180022109  movdqu  xmmword ptr [rsi+138h], xmm1
0x180022111  mov     edi, 1
0x180022116  test    [rsi+30h], dil
0x18002211a  jz      loc_180022FE0
0x180022120  lea     rdx, [rsp+110h+var_E0]
0x180022125  mov     rcx, [r14+30h]
0x180022129  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x18002212e  lea     rcx, [rsi+188h]
0x180022135  jmp     loc_18002203F
0x18002213a  lea     rcx, [rsi+138h]
0x180022141  mov     rdx, r14
0x180022144  call    ??MTSTime@@QEBA_NAEBV0@@Z; TSTime::operator<(TSTime const &)
0x180022149  test    al, al
0x18002214b  jnz     loc_180022441
0x180022151  movups  xmm0, xmmword ptr [r14]
0x180022155  movdqu  xmmword ptr [rsi+0D0h], xmm0
0x18002215d  movups  xmm1, xmmword ptr [r14]
0x180022161  movdqu  xmmword ptr [rsi+128h], xmm1
0x180022169  mov     edi, 1
0x18002216e  test    [rsi+30h], dil
0x180022172  jz      loc_180022FE0
0x180022178  lea     rdx, [rsp+110h+var_E0]
0x18002217d  mov     rcx, [r14+30h]
0x180022181  call    ?GetCopy@XmlParserTempString@@QEAA?AV_bstr_t@@XZ; XmlParserTempString::GetCopy(void)
0x180022186  lea     rcx, [rsi+180h]
0x18002218d  jmp     loc_18002203F
0x180022192  mov     eax, [r14+20h]
0x180022196  cmp     eax, 28DE80h
0x18002219b  ja      loc_180022441
0x1800221a1  jmp     loc_180022015
0x1800221a6  sub     ebx, 1Ch
0x1800221a9  jz      loc_180022303
0x1800221af  sub     ebx, 1
  ... truncated ...
```
