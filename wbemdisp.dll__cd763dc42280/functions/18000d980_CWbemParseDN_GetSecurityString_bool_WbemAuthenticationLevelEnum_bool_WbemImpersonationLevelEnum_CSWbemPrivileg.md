# CWbemParseDN::GetSecurityString(bool,WbemAuthenticationLevelEnum,bool,WbemImpersonationLevelEnum,CSWbemPrivilegeSet &,ushort * &)

- ea: `0x18000d980`
- end: `0x18000e8b0`
- name: `?GetSecurityString@CWbemParseDN@@SAPEAG_NW4WbemAuthenticationLevelEnum@@0W4WbemImpersonationLevelEnum@@AEAVCSWbemPrivilegeSet@@AEAPEAG@Z`
- size: `3888`
- prototype: `unsigned __int16 *__fastcall(bool, enum WbemAuthenticationLevelEnum, bool, enum WbemImpersonationLevelEnum, struct CSWbemPrivilegeSet *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d3f0`
- `0x18002e7a0`

## callees

- `0x18000d2c0`
- `0x18000d980`
- `0x18000e8b8`
- `0x18000f780`
- `0x18000fa40`
- `0x180013920`
- `0x1800196b4`
- `0x18001bed4`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000da48`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000da48`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000df43`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000dfcb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000df43`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000dfcb`

## string_xrefs

- `0x18000dd22`: `impersonationLevel`
- `0x18000de32`: `impersonate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int16 *__fastcall CWbemParseDN::GetSecurityString(
        char a1,
        enum WbemAuthenticationLevelEnum a2,
        char a3,
        enum WbemImpersonationLevelEnum a4,
        struct CSWbemPrivilegeSet *a5,
        const unsigned __int16 **a6)
{
  CSWbemPrivilegeSet *v10; // rbx
  __int64 NumberOfDisabledElements; // rdi
  const unsigned __int16 *v12; // r8
  __int64 v13; // r11
  char v14; // r9
  __int64 v15; // r10
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rax
  unsigned __int16 *v18; // rax
  __int64 j; // r8
  wchar_t *k; // r9
  unsigned __int16 *v21; // r11
  __int64 v22; // r14
  __int64 v23; // rdx
  unsigned __int16 v24; // cx
  unsigned __int16 *v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned __int64 v28; // rax
  __int64 v29; // rcx
  const wchar_t *v30; // rdx
  unsigned __int16 *v31; // r9
  wchar_t v32; // ax
  unsigned __int16 *v33; // rcx
  wchar_t *v34; // rcx
  unsigned __int16 *v35; // rax
  signed __int64 v36; // rax
  __int64 v37; // rcx
  const wchar_t *v38; // rdx
  wchar_t v39; // ax
  _WORD *v40; // rcx
  unsigned __int64 v41; // rcx
  unsigned __int16 *v42; // rax
  unsigned __int64 v43; // rax
  __int64 v44; // rcx
  const wchar_t *v45; // rdx
  wchar_t v46; // ax
  wchar_t *v47; // rcx
  char v48; // bl
  unsigned __int64 v49; // rcx
  unsigned __int16 *v50; // rax
  unsigned __int64 v51; // rax
  __int64 v52; // rcx
  const wchar_t *v53; // rdx
  wchar_t v54; // ax
  wchar_t *v55; // rcx
  unsigned __int64 v56; // rcx
  unsigned __int16 *v57; // rax
  unsigned __int64 v58; // rax
  __int64 v59; // rcx
  const wchar_t *v60; // rdx
  unsigned __int64 v61; // r8
  wchar_t v62; // ax
  wchar_t *v63; // rcx
  __int64 v64; // rcx
  unsigned __int16 *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  const wchar_t *v68; // rdx
  wchar_t v69; // ax
  wchar_t *v70; // rcx
  unsigned __int64 v71; // rcx
  unsigned __int16 *v72; // rax
  unsigned __int64 v73; // rax
  __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  wchar_t v76; // ax
  wchar_t *v77; // rcx
  bool v78; // zf
  unsigned __int64 v79; // rcx
  unsigned __int16 *v80; // rax
  unsigned __int64 v81; // rax
  const wchar_t *v82; // rcx
  unsigned __int64 v83; // rdi
  unsigned __int16 *n; // rax
  wchar_t v85; // dx
  unsigned __int16 *v86; // rcx
  int v88; // r13d
  int v89; // r13d
  __int64 v90; // rax
  __int64 v91; // rax
  unsigned __int64 v92; // rax
  unsigned __int16 *v93; // rcx
  unsigned __int64 v94; // rcx
  unsigned __int64 v95; // rax
  unsigned __int16 *v96; // rdx
  wchar_t v97; // cx
  unsigned __int64 v98; // rax
  unsigned __int16 *v99; // rcx
  unsigned __int64 v100; // rcx
  wchar_t v101; // cx
  unsigned __int64 v102; // rax
  unsigned __int16 *v103; // rcx
  unsigned __int64 v104; // rcx
  wchar_t v105; // cx
  unsigned __int64 v106; // rax
  unsigned __int16 *v107; // rcx
  unsigned __int64 v108; // rcx
  wchar_t v109; // cx
  unsigned __int64 v110; // rax
  unsigned __int16 *v111; // rcx
  unsigned __int64 v112; // rcx
  wchar_t v113; // cx
  unsigned __int64 v114; // rax
  unsigned __int16 *v115; // rcx
  unsigned __int64 v116; // rcx
  unsigned __int64 v117; // rax
  unsigned __int16 *v118; // rdx
  wchar_t v119; // cx
  unsigned __int64 v120; // rax
  unsigned __int16 *v121; // rcx
  unsigned __int64 v122; // rcx
  wchar_t v123; // cx
  unsigned __int64 v124; // rax
  unsigned __int16 *v125; // rcx
  unsigned __int64 v126; // rcx
  wchar_t v127; // cx
  unsigned __int64 v128; // rax
  unsigned __int16 *v129; // rcx
  unsigned __int64 v130; // rcx
  __int64 v131; // r9
  const wchar_t *v132; // r10
  unsigned __int64 v133; // rax
  unsigned __int16 *v134; // rdx
  wchar_t v135; // cx
  unsigned __int16 *v136; // rcx
  unsigned __int16 *v137; // r15
  __int64 v138; // rdx
  _QWORD *v139; // r8
  const unsigned __int16 *v140; // rax
  __int64 v141; // rbx
  __int64 v142; // rcx
  unsigned __int16 *MonikerNameFromId; // rax
  __int64 v144; // rcx
  __int64 i; // rax
  char v146; // si
  unsigned __int16 *v147; // r15
  __int64 v148; // rcx
  __int64 m; // rax
  int v150; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v151; // [rsp+28h] [rbp-20h]
  _QWORD *v152; // [rsp+30h] [rbp-18h] BYREF
  __int64 v153; // [rsp+38h] [rbp-10h]
  __int16 v154; // [rsp+90h] [rbp+48h] BYREF

  v150 = 0;
  v10 = a5;
  (*(void (__fastcall **)(struct CSWbemPrivilegeSet *, int *))(*(_QWORD *)a5 + 72LL))(a5, &v150);
  NumberOfDisabledElements = CSWbemPrivilegeSet::GetNumberOfDisabledElements(v10);
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>(
    &v152,
    (char *)v10 + 112);
  v12 = *a6;
  v13 = -1;
  if ( !*a6 )
    goto LABEL_2;
  v142 = -1;
  do
    ++v142;
  while ( v12[v142] );
  if ( v142 )
    v14 = 1;
  else
LABEL_2:
    v14 = 0;
  LOBYTE(v154) = v14;
  if ( a1 || a3 || v150 )
  {
    v15 = 2;
    if ( a1 )
    {
      if ( a2 )
      {
        switch ( a2 )
        {
          case wbemAuthenticationLevelNone:
          case wbemAuthenticationLevelCall:
            v15 = 26;
            goto LABEL_164;
          case wbemAuthenticationLevelConnect:
            break;
          case wbemAuthenticationLevelPkt:
            v15 = 25;
            goto LABEL_164;
          case wbemAuthenticationLevelPktIntegrity:
            v15 = 34;
            goto LABEL_164;
          case wbemAuthenticationLevelPktPrivacy:
            v15 = 32;
            goto LABEL_164;
          default:
            goto LABEL_320;
        }
      }
      v15 = 29;
LABEL_164:
      a5 = (struct CSWbemPrivilegeSet *)v15;
      if ( !a3 && !v14 )
      {
LABEL_7:
        if ( v150 > 0 )
        {
          if ( a1 || a3 || v14 )
            ++v15;
          if ( v150 <= 1 )
            v15 += 2;
          else
            v15 += 2LL + v150 - 1;
          if ( (_DWORD)NumberOfDisabledElements )
            v15 += NumberOfDisabledElements;
          v139 = v152;
          v138 = *v152;
          while ( (_QWORD *)v138 != v139 )
          {
            MonikerNameFromId = CSWbemPrivilege::GetMonikerNameFromId((enum WbemPrivilegeEnum)*(_DWORD *)(v138 + 32));
            if ( MonikerNameFromId )
            {
              v144 = v13;
              do
                ++v144;
              while ( MonikerNameFromId[v144] );
              v15 += v144;
            }
            if ( !*(_BYTE *)(v138 + 25) )
            {
              if ( *(_BYTE *)(*(_QWORD *)(v138 + 16) + 25LL) )
              {
                for ( i = *(_QWORD *)(v138 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
                {
                  if ( v138 != *(_QWORD *)(i + 16) )
                    break;
                  v138 = i;
                }
                v138 = i;
              }
              else
              {
                v138 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
              }
            }
          }
          a5 = (struct CSWbemPrivilegeSet *)v15;
        }
        v16 = v15 + 1;
        v17 = 2 * (v15 + 1);
        if ( !is_mul_ok(v15 + 1, 2u) )
          v17 = v13;
        v18 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v17);
        v21 = v18;
        v151 = v18;
        if ( !v18 )
        {
LABEL_147:
          std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
            &v152,
            v152[1],
            j,
            k);
          v152[1] = v152;
          *v152 = v152;
          v152[2] = v152;
          v153 = 0;
          CWin32DefaultArena::WbemMemFree(v152);
          return v151;
        }
        v22 = 2147483646;
        if ( v16 )
        {
          if ( v16 > 0x7FFFFFFF )
          {
            *v18 = 0;
          }
          else
          {
            v23 = 2147483646;
            j = (__int64)L"{";
            k = (wchar_t *)v16;
            do
            {
              if ( !v23 )
                break;
              v24 = *(_WORD *)j;
              if ( !*(_WORD *)j )
                break;
              j += 2;
              *v18++ = v24;
              --v23;
              k = (wchar_t *)((char *)k - 1);
            }
            while ( k );
            v25 = v18 - 1;
            if ( k )
              v25 = v18;
            *v25 = 0;
          }
        }
        if ( !a1 )
        {
          v48 = v154;
          goto LABEL_82;
        }
        if ( v16 )
        {
          if ( v16 <= 0x7FFFFFFF )
          {
            v26 = v16;
            v27 = v21;
            while ( *v27 )
            {
              ++v27;
              if ( !--v26 )
              {
                v28 = 0;
                goto LABEL_28;
              }
            }
            v28 = v16 - v26;
LABEL_28:
            if ( v26 )
            {
              v29 = 2147483646;
              v30 = L"authenticationLevel";
              j = v16 - v28;
              v31 = &v21[v28];
              if ( v16 != v28 )
              {
                do
                {
                  if ( !v29 )
                    break;
                  v32 = *v30;
                  if ( !*v30 )
                    break;
                  ++v30;
                  *v31++ = v32;
                  --v29;
                  --j;
                }
                while ( j );
              }
              v33 = v31 - 1;
              if ( j )
                v33 = v31;
              *v33 = 0;
              k = (wchar_t *)v16;
              goto LABEL_37;
            }
          }
          k = (wchar_t *)v16;
          if ( v16 <= 0x7FFFFFFF )
          {
LABEL_37:
            v34 = k;
            v35 = v21;
            do
            {
              if ( !*v35 )
                break;
              ++v35;
              v34 = (wchar_t *)((char *)v34 - 1);
            }
            while ( v34 );
            if ( v34 )
              v36 = (char *)k - (char *)v34;
            else
              v36 = 0;
            if ( v34 )
            {
              v37 = 2147483646;
              v38 = L"=";
              k = (wchar_t *)((char *)k - v36);
              for ( j = (__int64)&v21[v36]; k; k = (wchar_t *)((char *)k - 1) )
              {
                if ( !v37 )
                  break;
                v39 = *v38;
                if ( !*v38 )
                  break;
                ++v38;
                *(_WORD *)j = v39;
                j += 2;
                --v37;
              }
              v40 = (_WORD *)(j - 2);
              if ( k )
                v40 = (_WORD *)j;
              *v40 = 0;
            }
          }
        }
        if ( a2 == wbemAuthenticationLevelPktPrivacy )
        {
          if ( v16 && v16 <= 0x7FFFFFFF )
          {
            v41 = v16;
            v42 = v21;
            while ( *v42 )
            {
              ++v42;
              if ( !--v41 )
              {
                v43 = 0;
                goto LABEL_58;
              }
            }
            v43 = v16 - v41;
LABEL_58:
            if ( v41 )
            {
              v44 = 2147483646;
              v45 = L"pktPrivacy";
              j = v16 - v43;
              k = &v21[v43];
              if ( v16 != v43 )
              {
                do
                {
                  if ( !v44 )
                    break;
                  v46 = *v45;
                  if ( !*v45 )
                    break;
                  ++v45;
                  *k++ = v46;
                  --v44;
                  --j;
                }
                while ( j );
              }
              v47 = k - 1;
              if ( j )
                v47 = k;
LABEL_65:
              *v47 = 0;
            }
          }
        }
        else
        {
          switch ( a2 )
          {
            case wbemAuthenticationLevelDefault:
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v92 = v16;
                v93 = v21;
                do
                {
                  if ( !*v93 )
                  {
                    v94 = v16 - v92;
                    goto LABEL_174;
                  }
                  ++v93;
                  --v92;
                }
                while ( v92 );
                v94 = 0;
LABEL_174:
                if ( v92 )
                {
                  j = 2147483646;
                  k = (wchar_t *)L"default";
                  v95 = v16 - v94;
                  v96 = &v21[v94];
                  if ( v16 != v94 )
                  {
                    do
                    {
                      if ( !j )
                        break;
                      v97 = *k;
                      if ( !*k )
                        break;
                      ++k;
                      *v96++ = v97;
                      --j;
                      --v95;
                    }
                    while ( v95 );
                  }
                  goto LABEL_179;
                }
              }
              break;
            case wbemAuthenticationLevelNone:
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v98 = v16;
                v99 = v21;
                do
                {
                  if ( !*v99 )
                  {
                    v100 = v16 - v98;
                    goto LABEL_189;
                  }
                  ++v99;
                  --v98;
                }
                while ( v98 );
                v100 = 0;
LABEL_189:
                if ( v98 )
                {
                  j = 2147483646;
                  k = (wchar_t *)L"none";
                  v95 = v16 - v100;
                  v96 = &v21[v100];
                  if ( v16 == v100 )
                    goto LABEL_179;
                  while ( j )
                  {
                    v101 = *k;
                    if ( !*k )
                      break;
                    ++k;
                    *v96++ = v101;
                    --j;
                    if ( !--v95 )
                    {
                      v47 = v96 - 1;
                      goto LABEL_65;
                    }
                  }
                  goto LABEL_179;
                }
              }
              break;
            case wbemAuthenticationLevelConnect:
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v102 = v16;
                v103 = v21;
                do
                {
                  if ( !*v103 )
                  {
                    v104 = v16 - v102;
                    goto LABEL_202;
                  }
                  ++v103;
                  --v102;
                }
                while ( v102 );
                v104 = 0;
LABEL_202:
                if ( v102 )
                {
                  j = 2147483646;
                  k = (wchar_t *)L"connect";
                  v95 = v16 - v104;
                  v96 = &v21[v104];
                  if ( v16 == v104 )
                    goto LABEL_179;
                  while ( j )
                  {
                    v105 = *k;
                    if ( !*k )
                      break;
                    ++k;
                    *v96++ = v105;
                    --j;
                    if ( !--v95 )
                    {
                      v47 = v96 - 1;
                      goto LABEL_65;
                    }
                  }
                  goto LABEL_179;
                }
              }
              break;
            case wbemAuthenticationLevelCall:
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v106 = v16;
                v107 = v21;
                do
                {
                  if ( !*v107 )
                  {
                    v108 = v16 - v106;
                    goto LABEL_215;
                  }
                  ++v107;
                  --v106;
                }
                while ( v106 );
                v108 = 0;
LABEL_215:
                if ( v106 )
                {
                  j = 2147483646;
                  k = (wchar_t *)L"call";
                  v95 = v16 - v108;
                  v96 = &v21[v108];
                  if ( v16 == v108 )
                    goto LABEL_179;
                  while ( j )
                  {
                    v109 = *k;
                    if ( !*k )
                      break;
                    ++k;
                    *v96++ = v109;
                    --j;
                    if ( !--v95 )
                    {
                      v47 = v96 - 1;
                      goto LABEL_65;
                    }
                  }
                  goto LABEL_179;
                }
              }
              break;
            case wbemAuthenticationLevelPkt:
              StringCchCatW(v21, v16, L"pkt");
              v21 = v151;
              break;
            case wbemAuthenticationLevelPktIntegrity:
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v110 = v16;
                v111 = v21;
                do
                {
                  if ( !*v111 )
                  {
                    v112 = v16 - v110;
                    goto LABEL_228;
                  }
                  ++v111;
                  --v110;
                }
                while ( v110 );
                v112 = 0;
LABEL_228:
                if ( v110 )
                {
                  j = 2147483646;
                  k = (wchar_t *)L"pktIntegrity";
                  v95 = v16 - v112;
                  v96 = &v21[v112];
                  if ( v16 != v112 )
                  {
                    while ( j )
                    {
                      v113 = *k;
                      if ( !*k )
                        break;
                      ++k;
                      *v96++ = v113;
                      --j;
                      if ( !--v95 )
                      {
                        v47 = v96 - 1;
                        goto LABEL_65;
                      }
                    }
                  }
LABEL_179:
                  v47 = v96 - 1;
                  if ( v95 )
                    v47 = v96;
                  goto LABEL_65;
                }
              }
              break;
            default:
              break;
          }
        }
        v48 = v154;
        if ( !a3 && !(_BYTE)v154 )
        {
          v78 = v150 == 0;
          if ( v150 <= 0 )
            goto LABEL_130;
        }
        if ( v16 && v16 <= 0x7FFFFFFF )
        {
          v49 = v16;
          v50 = v21;
          while ( *v50 )
          {
            ++v50;
            if ( !--v49 )
            {
              v51 = 0;
              goto LABEL_74;
            }
          }
          v51 = v16 - v49;
LABEL_74:
          if ( v49 )
          {
            v52 = 2147483646;
            v53 = L",";
            j = v16 - v51;
            k = &v21[v51];
            if ( v16 != v51 )
            {
              do
              {
                if ( !v52 )
                  break;
                v54 = *v53;
                if ( !*v53 )
                  break;
                ++v53;
                *k++ = v54;
                --v52;
                --j;
              }
              while ( j );
            }
            v55 = k - 1;
            if ( j )
              v55 = k;
            *v55 = 0;
          }
        }
LABEL_82:
        if ( !a3 )
          goto LABEL_149;
        if ( v16 )
        {
          if ( v16 > 0x7FFFFFFF )
            goto LABEL_98;
          v56 = v16;
          v57 = v21;
          while ( *v57 )
          {
            ++v57;
            if ( !--v56 )
            {
              v58 = 0;
              goto LABEL_90;
            }
          }
          v58 = v16 - v56;
LABEL_90:
          if ( v56 )
          {
            v59 = 2147483646;
            v60 = L"impersonationLevel";
            v61 = v16 - v58;
            k = &v21[v58];
            if ( v16 != v58 )
            {
              do
              {
                if ( !v59 )
                  break;
                v62 = *v60;
                if ( !*v60 )
                  break;
                ++v60;
                *k++ = v62;
                --v59;
                --v61;
              }
              while ( v61 );
            }
            v63 = k - 1;
            if ( v61 )
              v63 = k;
            *v63 = 0;
            j = v16;
          }
          else
          {
LABEL_98:
            j = v16;
            if ( v16 > 0x7FFFFFFF )
              goto LABEL_112;
          }
          v64 = j;
          v65 = v21;
          do
          {
            if ( !*v65 )
              break;
            ++v65;
            --v64;
          }
          while ( v64 );
          if ( v64 )
            v66 = j - v64;
          else
            v66 = 0;
          if ( v64 )
          {
            v67 = 2147483646;
            v68 = L"=";
            j -= v66;
            for ( k = &v21[v66]; j; --j )
            {
              if ( !v67 )
                break;
              v69 = *v68;
              if ( !*v68 )
                break;
              ++v68;
              *k++ = v69;
              --v67;
            }
            v70 = k - 1;
            if ( j )
              v70 = k;
            *v70 = 0;
          }
        }
LABEL_112:
        if ( a4 == wbemImpersonationLevelImpersonate )
        {
          if ( !v16 || v16 > 0x7FFFFFFF )
            goto LABEL_128;
          v71 = v16;
          v72 = v21;
          while ( *v72 )
          {
            ++v72;
            if ( !--v71 )
            {
              v73 = 0;
              goto LABEL_120;
            }
          }
          v73 = v16 - v71;
LABEL_120:
          if ( !v71 )
            goto LABEL_128;
          v74 = 2147483646;
          j = (__int64)L"impersonate";
          v75 = v16 - v73;
          k = &v21[v73];
          if ( v16 != v73 )
          {
            do
            {
              if ( !v74 )
                break;
              v76 = *(_WORD *)j;
              if ( !*(_WORD *)j )
                break;
              j += 2;
              *k++ = v76;
              --v74;
              --v75;
            }
            while ( v75 );
          }
          v77 = k - 1;
          if ( v75 )
            v77 = k;
LABEL_127:
          *v77 = 0;
LABEL_128:
          if ( !v48 )
          {
            v78 = v150 == 0;
            if ( v150 <= 0 )
            {
LABEL_130:
              if ( !v78 )
              {
                StringCchCatW(v21, v16, L"(");
                v141 = *v152;
                v146 = 1;
                v147 = v151;
                while ( (_QWORD *)v141 != v152 )
                {
                  if ( !v146 )
                    StringCchCatW(v147, v16, L",");
                  v146 = 0;
                  v148 = *(_QWORD *)(v141 + 40);
                  v154 = 0;
                  if ( (*(int (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v148 + 56LL))(v148, &v154) >= 0 && !v154 )
                    StringCchCatW(v147, v16, L"!");
                  v140 = CSWbemPrivilege::GetMonikerNameFromId((enum WbemPrivilegeEnum)*(_DWORD *)(v141 + 32));
                  StringCchCatW(v147, v16, v140);
                  if ( !*(_BYTE *)(v141 + 25) )
                  {
                    if ( *(_BYTE *)(*(_QWORD *)(v141 + 16) + 25LL) )
                    {
                      for ( m = *(_QWORD *)(v141 + 8); !*(_BYTE *)(m + 25); m = *(_QWORD *)(m + 8) )
                      {
                        if ( v141 != *(_QWORD *)(m + 16) )
                          break;
                        v141 = m;
                      }
                      v141 = m;
                    }
                    else
                    {
                      v141 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum WbemPrivilegeEnum const,CSWbemPrivilege *>>>::_Min();
                    }
                  }
                }
                StringCchCatW(v147, v16, L")");
                v21 = v147;
              }
              if ( v16 && v16 <= 0x7FFFFFFF )
              {
                v79 = v16;
                v80 = v21;
                while ( *v80 )
                {
                  ++v80;
                  if ( !--v79 )
                  {
                    v81 = 0;
                    goto LABEL_138;
                  }
                }
                v81 = v16 - v79;
LABEL_138:
                if ( v79 )
                {
                  v82 = L"}";
                  v83 = v16 - v81;
                  for ( n = &v21[v81]; v83; --v83 )
                  {
                    if ( !v22 )
                      break;
                    v85 = *v82;
                    if ( !*v82 )
                      break;
                    ++v82;
                    *n++ = v85;
                    --v22;
                  }
                  v86 = n - 1;
                  if ( v83 )
                    v86 = n;
                  *v86 = 0;
                }
              }
              v21[(_QWORD)a5] = 0;
              goto LABEL_147;
            }
          }
          StringCchCatW(v21, v16, L",");
          v21 = v151;
LABEL_149:
          if ( v48 )
          {
            if ( v16 && v16 <= 0x7FFFFFFF )
            {
              v128 = v16;
              v129 = v21;
              do
              {
                if ( !*v129 )
                {
                  v130 = v16 - v128;
                  goto LABEL_282;
                }
                ++v129;
                --v128;
              }
              while ( v128 );
              v130 = 0;
LABEL_282:
              if ( v128 )
              {
                v131 = 2147483646;
                v132 = L"authority";
                v133 = v16 - v130;
                v134 = &v21[v130];
                if ( v16 != v130 )
                {
                  do
                  {
                    if ( !v131 )
                      break;
                    v135 = *v132;
                    if ( !*v132 )
                      break;
                    ++v132;
                    *v134++ = v135;
                    --v131;
                    --v133;
                  }
                  while ( v133 );
                }
                v136 = v134 - 1;
                if ( v133 )
                  v136 = v134;
                *v136 = 0;
              }
            }
            StringCchCatW(v21, v16, L"=");
            v137 = v151;
            StringCchCatW(v151, v16, *a6);
            if ( v150 > 0 )
              StringCchCatW(v137, v16, L",");
            v21 = v137;
          }
          v78 = v150 == 0;
          goto LABEL_130;
        }
        v88 = a4 - 1;
        if ( v88 )
        {
          v89 = v88 - 1;
          if ( v89 )
          {
            if ( v89 != 2 )
            {
              std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Erase(
                &v152,
                v152[1],
                j,
                k);
              v152[1] = v152;
              *v152 = v152;
              v152[2] = v152;
              v153 = 0;
              CWin32DefaultArena::WbemMemFree(v152);
              return 0;
            }
            if ( !v16 || v16 > 0x7FFFFFFF )
              goto LABEL_128;
            v114 = v16;
            v115 = v21;
            do
            {
              if ( !*v115 )
              {
                v116 = v16 - v114;
                goto LABEL_241;
              }
              ++v115;
              --v114;
            }
            while ( v114 );
            v116 = 0;
LABEL_241:
            if ( !v114 )
              goto LABEL_128;
            j = 2147483646;
            k = (wchar_t *)L"delegate";
            v117 = v16 - v116;
            v118 = &v21[v116];
            if ( v16 != v116 )
            {
              do
              {
                if ( !j )
                  break;
                v119 = *k;
                if ( !*k )
                  break;
                ++k;
                *v118++ = v119;
                --j;
                --v117;
              }
              while ( v117 );
            }
          }
          else
          {
            if ( !v16 || v16 > 0x7FFFFFFF )
              goto LABEL_128;
            v120 = v16;
            v121 = v21;
            do
            {
              if ( !*v121 )
              {
                v122 = v16 - v120;
                goto LABEL_256;
              }
              ++v121;
              --v120;
            }
            while ( v120 );
            v122 = 0;
LABEL_256:
            if ( !v120 )
              goto LABEL_128;
            j = 2147483646;
            k = (wchar_t *)L"identify";
            v117 = v16 - v122;
            v118 = &v21[v122];
            if ( v16 != v122 )
            {
              while ( j )
              {
                v123 = *k;
                if ( !*k )
                  break;
                ++k;
                *v118++ = v123;
                --j;
                if ( !--v117 )
                {
                  v77 = v118 - 1;
                  goto LABEL_127;
                }
              }
            }
          }
        }
        else
        {
          if ( !v16 || v16 > 0x7FFFFFFF )
            goto LABEL_128;
          v124 = v16;
          v125 = v21;
          do
          {
            if ( !*v125 )
            {
              v126 = v16 - v124;
              goto LABEL_269;
            }
            ++v125;
            --v124;
          }
          while ( v124 );
          v126 = 0;
LABEL_269:
          if ( !v124 )
            goto LABEL_128;
          j = 2147483646;
          k = (wchar_t *)L"anonymous";
          v117 = v16 - v126;
          v118 = &v21[v126];
          if ( v16 != v126 )
          {
            while ( j )
            {
              v127 = *k;
              if ( !*k )
                break;
              ++k;
              *v118++ = v127;
              --j;
              if ( !--v117 )
              {
                v77 = v118 - 1;
                goto LABEL_127;
              }
            }
          }
        }
        v77 = v118 - 1;
        if ( v117 )
          v77 = v118;
        goto LABEL_127;
      }
      ++v15;
    }
    if ( !a3 )
    {
      a5 = (struct CSWbemPrivilegeSet *)v15;
      if ( !v14 )
        goto LABEL_7;
      goto LABEL_159;
    }
    switch ( a4 )
    {
      case wbemImpersonationLevelImpersonate:
        v90 = 30;
        break;
      case wbemImpersonationLevelAnonymous:
        v90 = 28;
        break;
      case wbemImpersonationLevelIdentify:
      case wbemImpersonationLevelDelegate:
        v90 = 27;
        break;
      default:
        goto LABEL_320;
    }
    v15 += v90;
    a5 = (struct CSWbemPrivilegeSet *)v15;
    if ( !v14 )
      goto LABEL_7;
    ++v15;
    goto LABEL_159;
  }
  if ( v14 )
  {
    v15 = 2;
LABEL_159:
    v91 = -1;
    do
      ++v91;
    while ( v12[v91] );
    v15 += v91 + 10;
    a5 = (struct CSWbemPrivilegeSet *)v15;
    goto LABEL_7;
  }
LABEL_320:
  std::_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::~_Tree<std::_Tmap_traits<enum WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>(&v152);
  return 0;
}

```

## disassembly

```asm
0x18000d980  push    rbp
0x18000d982  push    rbx
0x18000d983  push    rsi
0x18000d984  push    rdi
0x18000d985  push    r12
0x18000d987  push    r13
0x18000d989  push    r14
0x18000d98b  push    r15
0x18000d98d  mov     rbp, rsp
0x18000d990  sub     rsp, 48h
0x18000d994  mov     r13d, r9d
0x18000d997  movzx   r12d, r8b
0x18000d99b  movsxd  r15, edx
0x18000d99e  movzx   esi, cl
0x18000d9a1  mov     [rbp+var_28], 0
0x18000d9a8  mov     rbx, [rbp+arg_20]
0x18000d9ac  mov     rax, [rbx]
0x18000d9af  lea     rdx, [rbp+var_28]
0x18000d9b3  mov     rcx, rbx
0x18000d9b6  mov     rax, [rax+48h]
0x18000d9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9bf  mov     rcx, rbx; this
0x18000d9c2  call    ?GetNumberOfDisabledElements@CSWbemPrivilegeSet@@QEAAKXZ; CSWbemPrivilegeSet::GetNumberOfDisabledElements(void)
0x18000d9c7  mov     edi, eax
0x18000d9c9  lea     rdx, [rbx+70h]
0x18000d9cd  lea     rcx, [rbp+var_18]
0x18000d9d1  call    ??0?$_Tree@V?$_Tmap_traits@W4WbemPrivilegeEnum@@PEAVCSWbemPrivilege@@U?$less@H@std@@V?$CWbemAllocator@PEAVCSWbemPrivilege@@@@$0A@@std@@@std@@QEAA@AEBV01@AEBV?$CWbemAllocator@PEAVCSWbemPrivilege@@@@@Z; std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>>(std::_Tree<std::_Tmap_traits<WbemPrivilegeEnum,CSWbemPrivilege *,std::less<int>,CWbemAllocator<CSWbemPrivilege *>,0>> const &,CWbemAllocator<CSWbemPrivilege *> const &)
0x18000d9d6  nop
0x18000d9d7  mov     r8, [rbp+arg_28]
0x18000d9db  mov     r8, [r8]
0x18000d9de  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18000d9e5  test    r8, r8
0x18000d9e8  jnz     loc_18000E610
0x18000d9ee  xor     r9b, r9b
0x18000d9f1  mov     byte ptr [rbp+arg_0], r9b
0x18000d9f5  mov     edx, [rbp+var_28]
0x18000d9f8  test    sil, sil
0x18000d9fb  jz      loc_18000E62F
0x18000da01  mov     r10d, 2
0x18000da07  lea     rbx, __ImageBase
0x18000da0e  test    sil, sil
0x18000da11  jnz     loc_18000E019
0x18000da17  test    r12b, r12b
0x18000da1a  jnz     loc_18000DFD9
0x18000da20  mov     [rbp+arg_20], r10
0x18000da24  test    r9b, r9b
0x18000da27  jnz     loc_18000DFFB
0x18000da2d  test    edx, edx
0x18000da2f  jg      loc_18000E6D0
0x18000da35  lea     rdi, [r10+1]
0x18000da39  mov     eax, 2
0x18000da3e  mul     rdi
0x18000da41  cmovb   rax, r11
0x18000da45  mov     rcx, rax
0x18000da48  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000da4e  mov     r11, rax
0x18000da51  mov     [rbp+var_20], rax
0x18000da55  test    rax, rax
0x18000da58  jz      loc_18000DF0F
0x18000da5e  mov     r14d, 7FFFFFFEh
0x18000da64  test    rdi, rdi
0x18000da67  jz      short loc_18000DAB5
0x18000da69  cmp     rdi, 7FFFFFFFh
0x18000da70  ja      loc_18000E757
0x18000da76  mov     edx, r14d
0x18000da79  lea     r8, asc_18003AEF0; "{"
0x18000da80  mov     r9, rdi
0x18000da83  test    rdx, rdx
0x18000da86  jz      short loc_18000DAA5
0x18000da88  movzx   ecx, word ptr [r8]
0x18000da8c  test    cx, cx
0x18000da8f  jz      short loc_18000DAA5
0x18000da91  add     r8, 2
0x18000da95  mov     [rax], cx
0x18000da98  add     rax, 2
0x18000da9c  dec     rdx
0x18000da9f  sub     r9, 1
0x18000daa3  jnz     short loc_18000DA83
0x18000daa5  lea     rcx, [rax-2]
0x18000daa9  test    r9, r9
0x18000daac  cmovnz  rcx, rax
0x18000dab0  xor     eax, eax
0x18000dab2  mov     [rcx], ax
0x18000dab5  test    sil, sil
0x18000dab8  jz      loc_18000DF5F
0x18000dabe  test    rdi, rdi
0x18000dac1  jz      loc_18000DBC9
0x18000dac7  cmp     rdi, 7FFFFFFFh
0x18000dace  ja      short loc_18000DB4C
0x18000dad0  mov     rcx, rdi
0x18000dad3  mov     rax, r11
0x18000dad6  cmp     word ptr [rax], 0
0x18000dada  jz      short loc_18000DAEA
0x18000dadc  add     rax, 2
0x18000dae0  sub     rcx, 1
0x18000dae4  jnz     short loc_18000DAD6
0x18000dae6  xor     eax, eax
0x18000dae8  jmp     short loc_18000DAF0
0x18000daea  mov     rax, rdi
0x18000daed  sub     rax, rcx
0x18000daf0  test    rcx, rcx
0x18000daf3  jz      short loc_18000DB47
0x18000daf5  mov     rcx, r14
0x18000daf8  lea     rdx, aAuthentication; "authenticationLevel"
0x18000daff  mov     r8, rdi
0x18000db02  sub     r8, rax
0x18000db05  lea     r9, [r11+rax*2]
0x18000db09  jz      short loc_18000DB32
0x18000db0b  nop     dword ptr [rax+rax+00h]
0x18000db10  test    rcx, rcx
0x18000db13  jz      short loc_18000DB32
0x18000db15  movzx   eax, word ptr [rdx]
0x18000db18  test    ax, ax
0x18000db1b  jz      short loc_18000DB32
0x18000db1d  add     rdx, 2
0x18000db21  mov     [r9], ax
0x18000db25  add     r9, 2
0x18000db29  dec     rcx
0x18000db2c  sub     r8, 1
0x18000db30  jnz     short loc_18000DB10
0x18000db32  lea     rcx, [r9-2]
0x18000db36  test    r8, r8
0x18000db39  cmovnz  rcx, r9
0x18000db3d  xor     eax, eax
0x18000db3f  mov     [rcx], ax
0x18000db42  mov     r9, rdi
0x18000db45  jmp     short loc_18000DB58
0x18000db47  test    rdi, rdi
0x18000db4a  jz      short loc_18000DBC9
0x18000db4c  mov     r9, rdi
0x18000db4f  cmp     rdi, 7FFFFFFFh
0x18000db56  ja      short loc_18000DBC9
0x18000db58  mov     rcx, r9
0x18000db5b  mov     rax, r11
0x18000db5e  xchg    ax, ax
0x18000db60  cmp     word ptr [rax], 0
0x18000db64  jz      short loc_18000DB70
0x18000db66  add     rax, 2
0x18000db6a  sub     rcx, 1
0x18000db6e  jnz     short loc_18000DB60
0x18000db70  test    rcx, rcx
0x18000db73  jz      loc_18000E762
0x18000db79  mov     rax, r9
0x18000db7c  sub     rax, rcx
0x18000db7f  test    rcx, rcx
0x18000db82  jz      short loc_18000DBC9
0x18000db84  mov     rcx, r14
0x18000db87  lea     rdx, asc_18003AEEC; "="
0x18000db8e  sub     r9, rax
0x18000db91  lea     r8, [r11+rax*2]
0x18000db95  jz      short loc_18000DBB9
0x18000db97  test    rcx, rcx
0x18000db9a  jz      short loc_18000DBB9
0x18000db9c  movzx   eax, word ptr [rdx]
0x18000db9f  test    ax, ax
0x18000dba2  jz      short loc_18000DBB9
0x18000dba4  add     rdx, 2
0x18000dba8  mov     [r8], ax
0x18000dbac  add     r8, 2
0x18000dbb0  dec     rcx
0x18000dbb3  sub     r9, 1
0x18000dbb7  jnz     short loc_18000DB97
0x18000dbb9  lea     rcx, [r8-2]
0x18000dbbd  test    r9, r9
0x18000dbc0  cmovnz  rcx, r8
0x18000dbc4  xor     eax, eax
0x18000dbc6  mov     [rcx], ax
0x18000dbc9  cmp     r15d, 6
0x18000dbcd  jnz     loc_18000E769
0x18000dbd3  test    rdi, rdi
0x18000dbd6  jz      short def_18000E77E; jumptable 000000018000E77E default case
0x18000dbd8  cmp     rdi, 7FFFFFFFh
0x18000dbdf  ja      short def_18000E77E; jumptable 000000018000E77E default case
0x18000dbe1  mov     rcx, rdi
0x18000dbe4  mov     rax, r11
0x18000dbe7  cmp     word ptr [rax], 0
0x18000dbeb  jz      short loc_18000DBFB
0x18000dbed  add     rax, 2
0x18000dbf1  sub     rcx, 1
0x18000dbf5  jnz     short loc_18000DBE7
0x18000dbf7  xor     eax, eax
0x18000dbf9  jmp     short loc_18000DC01
0x18000dbfb  mov     rax, rdi
0x18000dbfe  sub     rax, rcx
0x18000dc01  test    rcx, rcx
0x18000dc04  jz      short def_18000E77E; jumptable 000000018000E77E default case
0x18000dc06  mov     rcx, r14
0x18000dc09  lea     rdx, aPktprivacy; "pktPrivacy"
0x18000dc10  mov     r8, rdi
0x18000dc13  sub     r8, rax
0x18000dc16  lea     r9, [r11+rax*2]
0x18000dc1a  jz      short loc_18000DC42
0x18000dc1c  nop     dword ptr [rax+00h]
0x18000dc20  test    rcx, rcx
0x18000dc23  jz      short loc_18000DC42
0x18000dc25  movzx   eax, word ptr [rdx]
0x18000dc28  test    ax, ax
0x18000dc2b  jz      short loc_18000DC42
0x18000dc2d  add     rdx, 2
0x18000dc31  mov     [r9], ax
0x18000dc35  add     r9, 2
0x18000dc39  dec     rcx
0x18000dc3c  sub     r8, 1
0x18000dc40  jnz     short loc_18000DC20
0x18000dc42  lea     rcx, [r9-2]
0x18000dc46  test    r8, r8
0x18000dc49  cmovnz  rcx, r9
0x18000dc4d  xor     eax, eax
0x18000dc4f  mov     [rcx], ax
0x18000dc52  movzx   ebx, byte ptr [rbp+arg_0]; jumptable 000000018000E77E default case
0x18000dc56  test    r12b, r12b
0x18000dc59  jz      loc_18000E79B
0x18000dc5f  test    rdi, rdi
0x18000dc62  jz      short loc_18000DCDA
0x18000dc64  cmp     rdi, 7FFFFFFFh
0x18000dc6b  ja      short loc_18000DCDA
0x18000dc6d  mov     rcx, rdi
0x18000dc70  mov     rax, r11
0x18000dc73  cmp     word ptr [rax], 0
0x18000dc77  jz      short loc_18000DC87
0x18000dc79  add     rax, 2
0x18000dc7d  sub     rcx, 1
0x18000dc81  jnz     short loc_18000DC73
0x18000dc83  xor     eax, eax
0x18000dc85  jmp     short loc_18000DC8D
0x18000dc87  mov     rax, rdi
0x18000dc8a  sub     rax, rcx
0x18000dc8d  test    rcx, rcx
0x18000dc90  jz      short loc_18000DCDA
0x18000dc92  mov     rcx, r14
0x18000dc95  lea     rdx, asc_18003AFB8; ","
0x18000dc9c  mov     r8, rdi
0x18000dc9f  sub     r8, rax
0x18000dca2  lea     r9, [r11+rax*2]
0x18000dca6  jz      short loc_18000DCCA
0x18000dca8  test    rcx, rcx
0x18000dcab  jz      short loc_18000DCCA
0x18000dcad  movzx   eax, word ptr [rdx]
0x18000dcb0  test    ax, ax
0x18000dcb3  jz      short loc_18000DCCA
0x18000dcb5  add     rdx, 2
0x18000dcb9  mov     [r9], ax
0x18000dcbd  add     r9, 2
0x18000dcc1  dec     rcx
0x18000dcc4  sub     r8, 1
0x18000dcc8  jnz     short loc_18000DCA8
0x18000dcca  lea     rcx, [r9-2]
0x18000dcce  test    r8, r8
0x18000dcd1  cmovnz  rcx, r9
0x18000dcd5  xor     eax, eax
0x18000dcd7  mov     [rcx], ax
0x18000dcda  test    r12b, r12b
0x18000dcdd  jz      loc_18000DF68
0x18000dce3  test    rdi, rdi
0x18000dce6  jz      loc_18000DDF2
0x18000dcec  cmp     rdi, 7FFFFFFFh
0x18000dcf3  ja      loc_18000DD75
0x18000dcf9  mov     rcx, rdi
0x18000dcfc  mov     rax, r11
0x18000dcff  nop
0x18000dd00  cmp     word ptr [rax], 0
0x18000dd04  jz      short loc_18000DD14
0x18000dd06  add     rax, 2
0x18000dd0a  sub     rcx, 1
0x18000dd0e  jnz     short loc_18000DD00
0x18000dd10  xor     eax, eax
0x18000dd12  jmp     short loc_18000DD1A
0x18000dd14  mov     rax, rdi
0x18000dd17  sub     rax, rcx
0x18000dd1a  test    rcx, rcx
0x18000dd1d  jz      short loc_18000DD6C
0x18000dd1f  mov     rcx, r14
0x18000dd22  lea     rdx, aImpersonationl; "impersonationLevel"
0x18000dd29  mov     r8, rdi
0x18000dd2c  sub     r8, rax
0x18000dd2f  lea     r9, [r11+rax*2]
0x18000dd33  jz      short loc_18000DD57
0x18000dd35  test    rcx, rcx
0x18000dd38  jz      short loc_18000DD57
0x18000dd3a  movzx   eax, word ptr [rdx]
0x18000dd3d  test    ax, ax
0x18000dd40  jz      short loc_18000DD57
0x18000dd42  add     rdx, 2
0x18000dd46  mov     [r9], ax
0x18000dd4a  add     r9, 2
0x18000dd4e  dec     rcx
0x18000dd51  sub     r8, 1
0x18000dd55  jnz     short loc_18000DD35
0x18000dd57  lea     rcx, [r9-2]
0x18000dd5b  test    r8, r8
0x18000dd5e  cmovnz  rcx, r9
0x18000dd62  xor     eax, eax
0x18000dd64  mov     [rcx], ax
0x18000dd67  mov     r8, rdi
0x18000dd6a  jmp     short loc_18000DD81
0x18000dd6c  test    rdi, rdi
0x18000dd6f  jz      loc_18000DDF2
0x18000dd75  mov     r8, rdi
0x18000dd78  cmp     rdi, 7FFFFFFFh
0x18000dd7f  ja      short loc_18000DDF2
  ... truncated ...
```
