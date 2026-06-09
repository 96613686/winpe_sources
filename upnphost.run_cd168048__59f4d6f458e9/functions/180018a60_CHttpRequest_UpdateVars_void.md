# CHttpRequest::UpdateVars(void)

- ea: `0x180018a60`
- end: `0x1800194b9`
- name: `?UpdateVars@CHttpRequest@@AEAAHXZ`
- size: `2649`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800175c0`

## callees

- `0x180018a4c`
- `0x180018a60`
- `0x1800194c0`
- `0x18001aea8`
- `0x18001b240`
- `0x18001b2d0`
- `0x180029ae0`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18003cba0`
- `0x1800517fc`
- `0x180051f78`
- `0x180052040`
- `0x1800520d0`
- `0x18005220c`
- `0x180052e78`
- `0x180053264`
- `0x18005327c`
- `0x180057cac`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180018cf7`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180018cf7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019392`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ded`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018ded`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018e16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018fab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019127`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018e16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018fab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800190e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019326`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019476`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018db8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019067`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018db8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019067`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180018ad4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180018b2d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180018ad4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180018b2d`

## pseudocode

```c
__int64 __fastcall CHttpRequest::UpdateVars(CHttpRequest *this)
{
  unsigned int v1; // r14d
  CHttpRequest *v2; // r15
  __int64 v3; // rcx
  char *v4; // rbp
  const WCHAR *v5; // rdi
  int v6; // eax
  int cbMultiByte; // ebx
  void *v8; // rax
  int v9; // edx
  char *v10; // rax
  const char *v11; // rdx
  char *v12; // rsi
  __int64 v13; // rbx
  _BYTE *v15; // rax
  _BYTE *v16; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  char *v20; // rdx
  _BYTE *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  const char *v24; // rax
  __int64 v25; // rsi
  char *v26; // r14
  __int64 v27; // rbp
  int i; // ebx
  __int64 v29; // rdx
  __int64 v30; // rdi
  int v31; // eax
  __int64 v32; // r15
  int v33; // r8d
  __int64 v34; // rdx
  int *v35; // r13
  __int64 v36; // rdi
  char *v37; // rax
  char *v38; // r15
  char *v39; // rbx
  _BYTE *v40; // rbx
  unsigned __int64 v41; // rcx
  struct VROOTINFO *matched; // rdi
  char **v43; // r15
  _BYTE *v44; // rdi
  __int64 v45; // rbx
  _BYTE *v46; // rax
  _BYTE *v47; // rbp
  char v48; // al
  char *v49; // rax
  _BYTE *v50; // rbx
  char *v51; // rax
  char *v52; // r13
  int v53; // ebx
  int v54; // edx
  __int64 v55; // r12
  int j; // r15d
  int v57; // ebx
  __int16 *v58; // r12
  __int64 v59; // rax
  __int16 *v60; // rdi
  int v61; // ebx
  unsigned __int16 v62; // dx
  __int16 v63; // cx
  __int16 *v64; // rax
  const unsigned __int16 *v65; // rax
  int v66; // edx
  unsigned __int16 *v67; // rax
  unsigned int v68; // r8d
  unsigned int v69; // r9d
  __int64 v70; // rdi
  int v71; // ebp
  DWORD LastError; // eax
  __int64 v73; // rdx
  __int64 v74; // rax
  __int64 v75; // rcx
  __int64 v76; // r8
  char v77; // al
  int v78; // edx
  int v79; // r8d
  int lpMultiByteStr; // [rsp+20h] [rbp-298h]
  char *v82; // [rsp+48h] [rbp-270h] BYREF
  __int64 v83; // [rsp+50h] [rbp-268h]
  void *Block; // [rsp+58h] [rbp-260h]
  WCHAR WideCharStr[264]; // [rsp+70h] [rbp-248h] BYREF

  v1 = 0;
  v2 = this;
  v3 = *((_QWORD *)this + 2);
  v82 = (char *)v3;
  v4 = 0;
  *((_DWORD *)v2 + 54) = *(unsigned __int16 *)(v3 + 34) | (*(unsigned __int16 *)(v3 + 32) << 16);
  v5 = *(const WCHAR **)(v3 + 88);
  v6 = WideCharToMultiByte(0, 0x400u, v5, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6
    && (v8 = (void *)svsutil_Alloc((unsigned int)(v6 + 1), g_pvAllocData), Block = v8, (v4 = (char *)v8) != 0)
    && WideCharToMultiByte(0, 0x400u, v5, -1, (LPSTR)v8, cbMultiByte, 0, 0) )
  {
    v10 = strchr(v4, v9);
    v12 = v10;
    if ( !v10 )
    {
LABEL_5:
      if ( *((_DWORD *)g_pVars + 6) )
      {
        v49 = strstr(v4, v11);
        if ( v49 )
        {
          v50 = v49 + 4;
          v51 = MySzDupA(v49 + 4, 0);
          *((_QWORD *)v2 + 18) = v51;
          if ( !v51 )
            goto LABEL_9;
          *v50 = 0;
        }
      }
      v13 = -1;
      while ( v4[++v13] != 0 )
        ;
      v15 = (_BYTE *)svsutil_Alloc((unsigned int)(v13 + 2), g_pvAllocData);
      *((_QWORD *)v2 + 8) = v15;
      v16 = v15;
      if ( !v15 )
        goto LABEL_9;
      v18 = (int)v13 + 1;
      if ( (_DWORD)v13 != -1 )
      {
        if ( (unsigned __int64)((int)v13 + 1) > 0x7FFFFFFF )
        {
          *v15 = 0;
        }
        else
        {
          v19 = 2147483646;
          v20 = v4;
          do
          {
            if ( !v19 )
              break;
            if ( !*v20 )
              break;
            *v16++ = *v20++;
            --v19;
            --v18;
          }
          while ( v18 );
          v21 = v16 - 1;
          if ( v18 )
            v21 = v16;
          *v21 = 0;
        }
      }
      v22 = *((_QWORD *)v2 + 2);
      v23 = *(_DWORD *)(v22 + 36);
      *((_DWORD *)v2 + 55) = v23;
      switch ( v23 )
      {
        case 4:
          v24 = "GET";
          break;
        case 5:
          v24 = "HEAD";
          break;
        case 6:
          v24 = "POST";
          break;
        case 1:
          v24 = *(const char **)(v22 + 48);
          break;
        default:
LABEL_22:
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids,
              *((_QWORD *)v2 + 7));
          }
          v25 = -1;
          v26 = (char *)*((_QWORD *)v2 + 8);
          v27 = *((_QWORD *)g_pVars + 2);
          do
            ++v25;
          while ( v26[v25] );
          EnterCriticalSection(*((LPCRITICAL_SECTION *)g_pVars + 2));
          if ( !*(_QWORD *)(v27 + 48) )
          {
LABEL_68:
            LeaveCriticalSection((LPCRITICAL_SECTION)v27);
            *((_QWORD *)v2 + 16) = 0;
            goto LABEL_69;
          }
          for ( i = 0; i < *(_DWORD *)(v27 + 40); ++i )
          {
            v29 = *(_QWORD *)(v27 + 48);
            v30 = 56LL * i;
            v31 = *(_DWORD *)(v29 + v30);
            if ( *(_DWORD *)(v29 + v30 + 40) && v31 != 1 )
              --v31;
            if ( v31 )
            {
              if ( (int)v25 >= v31 )
              {
                v32 = v31;
                if ( !(unsigned int)_o__memicmp(v26, *(_QWORD *)(v29 + v30 + 8), v31) )
                {
                  v34 = v30 + *(_QWORD *)(v27 + 48);
                  if ( !*(_DWORD *)(v34 + 40) || *(_DWORD *)v34 == 1 || (v48 = v26[v32], v48 == 47) || !v48 )
                  {
                    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                    {
                      WPP_SF_ssSd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v34,
                        v33,
                        (_DWORD)v26,
                        *(_QWORD *)(v34 + 8),
                        *(_QWORD *)(v34 + 24),
                        *(_DWORD *)(v34 + 32));
                    }
                    v35 = (int *)(v30 + *(_QWORD *)(v27 + 48));
                    if ( v35 )
                    {
                      v36 = -1;
                      do
                        ++v36;
                      while ( v26[v36] );
                      v37 = strrchr(v26, v34);
                      v38 = v37;
                      v39 = v37;
                      if ( !v37 )
                      {
                        v43 = (char **)((char *)this + 144);
                        goto LABEL_77;
                      }
                      if ( *v37 != 47 )
                      {
                        do
                        {
                          if ( !*v39 )
                            break;
                          ++v39;
                        }
                        while ( *v39 != 47 );
                      }
                      v40 = v39 + 1;
                      if ( v40 - v37 > 260 )
                      {
                        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                        {
                          WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            17,
                            WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids);
                        }
                      }
                      else
                      {
                        if ( MultiByteToWideChar(0, 0, v37, -1, WideCharStr, (_DWORD)v40 - (_DWORD)v37) )
                        {
                          v41 = v40 - v38;
                          if ( v41 >= 261 )
                            _report_rangecheckfailure();
                          WideCharStr[v41] = 0;
                          EnterCriticalSection((LPCRITICAL_SECTION)v27);
                          matched = CVRoots::MatchVRoot((CVRoots *)v27, v26, v36);
                          if ( matched )
                          {
                            v55 = 0;
                            for ( j = 0; ; ++j )
                            {
                              if ( j >= *((_DWORD *)matched + 11) )
                              {
                                v40 = 0;
                                goto LABEL_76;
                              }
                              if ( j )
                              {
                                v74 = j;
                              }
                              else
                              {
                                v73 = 0;
                                if ( ***((_WORD ***)matched + 6) == 42 )
                                  goto LABEL_138;
                                v74 = 0;
                              }
                              v75 = *((_QWORD *)matched + 6);
                              v83 = v74;
                              if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v75 + 16 * v74), WideCharStr) )
                                break;
                            }
                            v73 = v83;
LABEL_138:
                            v55 = *(_QWORD *)(*((_QWORD *)matched + 6) + 16 * v73 + 8);
LABEL_76:
                            LeaveCriticalSection((LPCRITICAL_SECTION)v27);
                            v43 = (char **)((char *)this + 144);
                            if ( v55 )
                            {
                              if ( this != (CHttpRequest *)-144LL && !*v43 )
                                *v43 = MySzDupA(v26, 0);
                              if ( *v40 )
                              {
                                *v40 = 0;
                                v25 = -1;
                                do
                                  ++v25;
                                while ( v26[v25] );
                              }
                            }
                          }
                          else
                          {
                            LeaveCriticalSection((LPCRITICAL_SECTION)v27);
                            v43 = (char **)((char *)this + 144);
                          }
LABEL_77:
                          v57 = v25 + v35[4] - *v35 + 1;
                          v58 = (__int16 *)svsutil_Alloc((unsigned int)(2 * v57), g_pvAllocData);
                          if ( v58 )
                          {
                            memcpy_0(v58, *((const void **)v35 + 3), 2LL * v35[4]);
                            if ( this != (CHttpRequest *)-164LL )
                              *((_DWORD *)this + 41) = v35[8];
                            if ( this != (CHttpRequest *)-160LL )
                              *((_DWORD *)this + 40) = v35[9];
                            if ( v35[9] )
                            {
                              if ( v43 )
                              {
                                v76 = *v35;
                                if ( v26[v76] )
                                  SetPathInfo(v43, v26, v76);
                              }
                              v58[v35[4]] = 0;
                              LeaveCriticalSection((LPCRITICAL_SECTION)v27);
                              v60 = v58;
                            }
                            else
                            {
                              v59 = v35[4];
                              v60 = v58;
                              v61 = v57 - v59;
                              if ( v61 )
                                MultiByteToWideChar(0, 0, &v26[*v35], -1, (LPWSTR)&v58[v59], v61);
                              else
                                v58[v59] = 0;
                              LeaveCriticalSection((LPCRITICAL_SECTION)v27);
                              v63 = *v58;
                              if ( *v58 )
                              {
                                v64 = v58;
                                do
                                {
                                  if ( v63 == 47 )
                                    *v64 = 92;
                                  v63 = v64[1];
                                  ++v64;
                                }
                                while ( v63 );
                              }
                            }
                            v2 = this;
                            *((_QWORD *)this + 16) = v60;
                            v65 = wcsrchr((unsigned __int16 *)v58, v62);
                            if ( v65 )
                            {
                              v67 = MySzDupW(v65, v66);
                              *((_QWORD *)this + 17) = v67;
                              if ( !v67 )
                              {
LABEL_92:
                                v1 = 0;
                                goto LABEL_9;
                              }
                            }
                          }
                          else
                          {
                            LeaveCriticalSection((LPCRITICAL_SECTION)v27);
                            v2 = this;
                            *((_QWORD *)this + 16) = 0;
                          }
LABEL_69:
                          v52 = v82;
                          v53 = 0;
                          v1 = 1;
                          while ( v53 < 41 )
                          {
                            v54 = *(unsigned __int16 *)&v52[16 * v53 + 152];
                            if ( (_WORD)v54 )
                            {
                              v68 = 0;
                              v82 = *(char **)&v52[16 * v53 + 160];
                              v69 = 0;
                              while ( 1 )
                              {
                                v70 = 3LL * (int)v68;
                                if ( !(&off_18005A040)[v70] || *((_DWORD *)&off_18005A040 + 2 * v70 + 3) == v53 )
                                  break;
                                v69 = ++v68;
                                if ( v68 >= 7 )
                                  goto LABEL_72;
                              }
                              if ( v69 < 7 && (&off_18005A040)[v70 + 2] )
                              {
                                v71 = v54;
                                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                                {
                                  WPP_SF_s(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    12,
                                    WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids,
                                    (&off_18005A040)[v70]);
                                }
                                if ( !(unsigned int)(*(__int64 (__fastcall **)(CHttpRequest *__hidden, char **, int, enum _HTTP_HEADER_ID))((char *)&funcs_18001921E + v70 * 8))(
                                                      v2,
                                                      &v82,
                                                      v71,
                                                      (enum _HTTP_HEADER_ID)*((_DWORD *)&off_18005A040 + 2 * v70 + 3)) )
                                {
                                  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                                  {
                                    WPP_SF_s(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      13,
                                      WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids,
                                      (&off_18005A040)[v70]);
                                  }
                                  goto LABEL_92;
                                }
                              }
                            }
LABEL_72:
                            ++v53;
                          }
                          goto LABEL_9;
                        }
                        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                        {
                          LastError = GetLastError();
                          WPP_SF_d(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            18,
                            WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids,
                            LastError);
                          v43 = (char **)((char *)this + 144);
                          goto LABEL_77;
                        }
                      }
                      v43 = (char **)((char *)this + 144);
                      goto LABEL_77;
                    }
LABEL_67:
                    v2 = this;
                    goto LABEL_68;
                  }
                }
              }
            }
          }
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f28cf248efbf3aa3b14f0d26735e5363_Traceguids, v26);
          }
          goto LABEL_67;
      }
      *((_QWORD *)v2 + 7) = v24;
      goto LABEL_22;
    }
    v44 = v10 + 1;
    if ( v10 == (char *)-1LL )
    {
      *((_QWORD *)v2 + 15) = 0;
      goto LABEL_9;
    }
    v45 = -1;
    do
      ++v45;
    while ( v44[v45] );
    v46 = (_BYTE *)svsutil_Alloc((unsigned int)(v45 + 1), g_pvAllocData);
    v47 = v46;
    if ( v46 )
    {
      memcpy_0(v46, v44, (int)v45);
      v47[(int)v45] = 0;
    }
    *((_QWORD *)v2 + 15) = v47;
    if ( v47 )
    {
      v4 = (char *)Block;
      *v12 = 0;
      goto LABEL_5;
    }
LABEL_9:
    svsutil_Free(Block);
    return v1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      v77 = GetLastError();
      WPP_SF_Sdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v78, v79, (_DWORD)v5, lpMultiByteStr, (char)v4, v77);
    }
    if ( v4 )
      svsutil_Free(v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180018a60  push    rbx
0x180018a62  push    rbp
0x180018a63  push    rdi
0x180018a64  push    r14
0x180018a66  push    r15
0x180018a68  sub     rsp, 290h
0x180018a6f  mov     rax, cs:__security_cookie
0x180018a76  xor     rax, rsp
0x180018a79  mov     [rsp+2B8h+var_38], rax
0x180018a81  xor     r14d, r14d
0x180018a84  mov     [rsp+2B8h+var_278], rcx
0x180018a89  mov     r15, rcx
0x180018a8c  mov     [rsp+2B8h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180018a91  mov     rcx, [rcx+10h]
0x180018a95  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180018a9b  mov     [rsp+2B8h+var_270], rcx
0x180018aa0  mov     ebp, r14d
0x180018aa3  mov     [rsp+2B8h+lpDefaultChar], r14; lpDefaultChar
0x180018aa8  mov     [rsp+2B8h+cbMultiByte], r14d; cbMultiByte
0x180018aad  movzx   edx, word ptr [rcx+20h]
0x180018ab1  movzx   eax, word ptr [rcx+22h]
0x180018ab5  shl     edx, 10h
0x180018ab8  or      edx, eax
0x180018aba  mov     [rsp+2B8h+lpMultiByteStr], r14; lpMultiByteStr
0x180018abf  mov     [r15+0D8h], edx
0x180018ac6  mov     edx, 400h; dwFlags
0x180018acb  mov     rdi, [rcx+58h]
0x180018acf  xor     ecx, ecx; CodePage
0x180018ad1  mov     r8, rdi; lpWideCharStr
0x180018ad4  call    cs:__imp_WideCharToMultiByte
0x180018adb  nop     dword ptr [rax+rax+00h]
0x180018ae0  mov     ebx, eax
0x180018ae2  test    eax, eax
0x180018ae4  jz      loc_18001945A
0x180018aea  mov     rdx, cs:g_pvAllocData
0x180018af1  lea     ecx, [rax+1]
0x180018af4  call    svsutil_Alloc
0x180018af9  mov     [rsp+2B8h+Block], rax
0x180018afe  mov     rbp, rax
0x180018b01  test    rax, rax
0x180018b04  jz      loc_18001945A
0x180018b0a  mov     [rsp+2B8h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180018b0f  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180018b15  mov     [rsp+2B8h+lpDefaultChar], r14; lpDefaultChar
0x180018b1a  mov     r8, rdi; lpWideCharStr
0x180018b1d  mov     [rsp+2B8h+cbMultiByte], ebx; cbMultiByte
0x180018b21  mov     edx, 400h; dwFlags
0x180018b26  xor     ecx, ecx; CodePage
0x180018b28  mov     [rsp+2B8h+lpMultiByteStr], rax; lpMultiByteStr
0x180018b2d  call    cs:__imp_WideCharToMultiByte
0x180018b34  nop     dword ptr [rax+rax+00h]
0x180018b39  test    eax, eax
0x180018b3b  jz      loc_18001945A
0x180018b41  mov     [rsp+2B8h+arg_8], rsi
0x180018b49  mov     rcx, rbp; char *
0x180018b4c  mov     [rsp+2B8h+arg_10], r12
0x180018b54  mov     [rsp+2B8h+arg_18], r13
0x180018b5c  call    ?strchr@@YAPEADQEADH@Z; strchr(char * const,int)
0x180018b61  mov     rsi, rax
0x180018b64  test    rax, rax
0x180018b67  jnz     loc_180018E33
0x180018b6d  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180018b74  cmp     [rax+18h], r14d
0x180018b78  jnz     loc_180018EE6
0x180018b7e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180018b85  cmp     [rbx+rbp+1], r14b
0x180018b8a  lea     rbx, [rbx+1]
0x180018b8e  jnz     short loc_180018B85
0x180018b90  mov     rdx, cs:g_pvAllocData
0x180018b97  lea     ecx, [rbx+2]
0x180018b9a  call    svsutil_Alloc
0x180018b9f  mov     [r15+40h], rax
0x180018ba3  mov     r8, rax
0x180018ba6  test    rax, rax
0x180018ba9  jnz     short loc_180018BF7
0x180018bab  mov     rdx, cs:g_pvFreeData
0x180018bb2  mov     rcx, [rsp+2B8h+Block]; Block
0x180018bb7  call    svsutil_Free
0x180018bbc  mov     r12, [rsp+2B8h+arg_10]
0x180018bc4  mov     eax, r14d
0x180018bc7  mov     r13, [rsp+2B8h+arg_18]
0x180018bcf  mov     rsi, [rsp+2B8h+arg_8]
0x180018bd7  mov     rcx, [rsp+2B8h+var_38]
0x180018bdf  xor     rcx, rsp; StackCookie
0x180018be2  call    __security_check_cookie
0x180018be7  add     rsp, 290h
0x180018bee  pop     r15
0x180018bf0  pop     r14
0x180018bf2  pop     rdi
0x180018bf3  pop     rbp
0x180018bf4  pop     rbx
0x180018bf5  retn
0x180018bf7  lea     eax, [rbx+1]
0x180018bfa  movsxd  r9, eax
0x180018bfd  test    eax, eax
0x180018bff  jz      short loc_180018C42
0x180018c01  cmp     r9, 7FFFFFFFh
0x180018c08  ja      loc_180019282
0x180018c0e  mov     ecx, 7FFFFFFEh
0x180018c13  mov     rdx, rbp
0x180018c16  test    rcx, rcx
0x180018c19  jz      short loc_180018C34
0x180018c1b  movzx   eax, byte ptr [rdx]
0x180018c1e  test    al, al
0x180018c20  jz      short loc_180018C34
0x180018c22  mov     [r8], al
0x180018c25  inc     rdx
0x180018c28  inc     r8
0x180018c2b  dec     rcx
0x180018c2e  sub     r9, 1
0x180018c32  jnz     short loc_180018C16
0x180018c34  test    r9, r9
0x180018c37  lea     rax, [r8-1]
0x180018c3b  cmovnz  rax, r8
0x180018c3f  mov     [rax], r14b
0x180018c42  mov     rcx, [r15+10h]
0x180018c46  mov     eax, [rcx+24h]
0x180018c49  mov     [r15+0DCh], eax
0x180018c50  cmp     eax, 4
0x180018c53  jnz     loc_18001916D
0x180018c59  lea     rax, aGet; "GET"
0x180018c60  mov     [r15+38h], rax
0x180018c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c6b  lea     r12, WPP_GLOBAL_Control
0x180018c72  cmp     rcx, r12
0x180018c75  jnz     loc_180018EBB
0x180018c7b  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180018c82  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180018c89  mov     r14, [r15+40h]
0x180018c8d  mov     rbp, [rax+10h]
0x180018c91  inc     rsi
0x180018c94  cmp     byte ptr [r14+rsi], 0
0x180018c99  jnz     short loc_180018C91
0x180018c9b  mov     rcx, rbp; lpCriticalSection
0x180018c9e  call    cs:__imp_EnterCriticalSection
0x180018ca5  nop     dword ptr [rax+rax+00h]
0x180018caa  cmp     qword ptr [rbp+30h], 0
0x180018caf  jz      loc_180018F3B
0x180018cb5  xor     ebx, ebx
0x180018cb7  cmp     ebx, [rbp+28h]
0x180018cba  jge     loc_180018F1D
0x180018cc0  mov     rdx, [rbp+30h]
0x180018cc4  movsxd  rax, ebx
0x180018cc7  imul    rdi, rax, 38h ; '8'
0x180018ccb  cmp     dword ptr [rdx+rdi+28h], 0
0x180018cd0  mov     eax, [rdx+rdi]
0x180018cd3  jnz     loc_1800192A8
0x180018cd9  test    eax, eax
0x180018cdb  jz      loc_180018EB4
0x180018ce1  cmp     esi, eax
0x180018ce3  jl      loc_180018EB4
0x180018ce9  mov     rdx, [rdx+rdi+8]
0x180018cee  mov     rcx, r14
0x180018cf1  movsxd  r15, eax
0x180018cf4  mov     r8, r15
0x180018cf7  call    cs:__imp__o__memicmp
0x180018cfe  nop     dword ptr [rax+rax+00h]
0x180018d03  test    eax, eax
0x180018d05  jnz     loc_180018EB4
0x180018d0b  mov     rdx, [rbp+30h]
0x180018d0f  add     rdx, rdi; int
0x180018d12  cmp     [rdx+28h], eax
0x180018d15  jnz     loc_180018E96
0x180018d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d22  cmp     rcx, r12
0x180018d25  jz      short loc_180018D34
0x180018d27  test    dword ptr [rcx+1Ch], 1000h
0x180018d2e  jnz     loc_1800192B8
0x180018d34  mov     r13, [rbp+30h]
0x180018d38  add     r13, rdi
0x180018d3b  jz      loc_180018F36
0x180018d41  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018d48  nop     dword ptr [rax+rax+00000000h]
0x180018d50  inc     rdi
0x180018d53  cmp     byte ptr [r14+rdi], 0
0x180018d58  jnz     short loc_180018D50
0x180018d5a  mov     rcx, r14; char *
0x180018d5d  call    ?strrchr@@YAPEADQEADH@Z; strrchr(char * const,int)
0x180018d62  mov     r15, rax
0x180018d65  mov     rbx, rax
0x180018d68  test    rax, rax
0x180018d6b  jz      loc_18001915C
0x180018d71  cmp     byte ptr [rax], 2Fh ; '/'
0x180018d74  jz      short loc_180018D83
0x180018d76  cmp     byte ptr [rbx], 0
0x180018d79  jz      short loc_180018D83
0x180018d7b  inc     rbx
0x180018d7e  cmp     byte ptr [rbx], 2Fh ; '/'
0x180018d81  jnz     short loc_180018D76
0x180018d83  inc     rbx
0x180018d86  mov     rax, rbx
0x180018d89  sub     rax, r15
0x180018d8c  cmp     rax, 104h
0x180018d92  jg      loc_1800192E2
0x180018d98  mov     eax, ebx
0x180018d9a  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180018da0  sub     eax, r15d
0x180018da3  mov     r8, r15; lpMultiByteStr
0x180018da6  mov     [rsp+2B8h+cbMultiByte], eax; cchWideChar
0x180018daa  xor     edx, edx; dwFlags
0x180018dac  lea     rax, [rsp+2B8h+WideCharStr]
0x180018db1  xor     ecx, ecx; CodePage
0x180018db3  mov     [rsp+2B8h+lpMultiByteStr], rax; lpWideCharStr
0x180018db8  call    cs:__imp_MultiByteToWideChar
0x180018dbf  nop     dword ptr [rax+rax+00h]
0x180018dc4  test    eax, eax
0x180018dc6  jz      loc_18001913B
0x180018dcc  mov     rax, rbx
0x180018dcf  sub     rax, r15
0x180018dd2  lea     rcx, [rax+rax]
0x180018dd6  cmp     rcx, 20Ah
0x180018ddd  jnb     loc_18001910A
0x180018de3  xor     eax, eax
0x180018de5  mov     [rsp+rcx+2B8h+WideCharStr], ax
0x180018dea  mov     rcx, rbp; lpCriticalSection
0x180018ded  call    cs:__imp_EnterCriticalSection
0x180018df4  nop     dword ptr [rax+rax+00h]
0x180018df9  mov     r8d, edi; int
0x180018dfc  mov     rdx, r14; char *
0x180018dff  mov     rcx, rbp; this
0x180018e02  call    ?MatchVRoot@CVRoots@@AEAAPEAUVROOTINFO@@PEBDH@Z; CVRoots::MatchVRoot(char const *,int)
0x180018e07  mov     rdi, rax
0x180018e0a  test    rax, rax
0x180018e0d  jnz     loc_180018F95
0x180018e13  mov     rcx, rbp; lpCriticalSection
0x180018e16  call    cs:__imp_LeaveCriticalSection
0x180018e1d  nop     dword ptr [rax+rax+00h]
0x180018e22  mov     r15, [rsp+2B8h+var_278]
0x180018e27  add     r15, 90h
0x180018e2e  jmp     loc_180018FCC
0x180018e33  lea     rdi, [rax+1]
0x180018e37  test    rdi, rdi
0x180018e3a  jz      loc_180019195
0x180018e40  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180018e47  inc     rbx
0x180018e4a  cmp     [rdi+rbx], r14b
0x180018e4e  jnz     short loc_180018E47
0x180018e50  mov     rdx, cs:g_pvAllocData
0x180018e57  lea     ecx, [rbx+1]
0x180018e5a  call    svsutil_Alloc
0x180018e5f  mov     rbp, rax
0x180018e62  test    rax, rax
0x180018e65  jz      short loc_180018E7C
0x180018e67  movsxd  rbx, ebx
0x180018e6a  mov     rdx, rdi; Src
0x180018e6d  mov     r8, rbx; Size
0x180018e70  mov     rcx, rax; void *
0x180018e73  call    memcpy_0
0x180018e78  mov     [rbx+rbp], r14b
0x180018e7c  mov     [r15+78h], rbp
0x180018e80  test    rbp, rbp
0x180018e83  jz      loc_180018BAB
0x180018e89  mov     rbp, [rsp+2B8h+Block]
0x180018e8e  mov     [rsi], r14b
0x180018e91  jmp     loc_180018B6D
0x180018e96  cmp     dword ptr [rdx], 1
0x180018e99  jz      loc_180018D1B
0x180018e9f  movzx   eax, byte ptr [r14+r15]
0x180018ea4  cmp     al, 2Fh ; '/'
0x180018ea6  jz      loc_180018D1B
0x180018eac  test    al, al
0x180018eae  jz      loc_180018D1B
0x180018eb4  inc     ebx
0x180018eb6  jmp     loc_180018CB7
0x180018ebb  test    dword ptr [rcx+1Ch], 1000h
0x180018ec2  jz      loc_180018C7B
0x180018ec8  mov     r9, [r15+38h]
0x180018ecc  lea     r8, WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids
0x180018ed3  mov     rcx, [rcx+10h]
0x180018ed7  mov     edx, 0Bh
0x180018edc  call    WPP_SF_s
0x180018ee1  jmp     loc_180018C7B
0x180018ee6  mov     rcx, rbp; char *
0x180018ee9  call    ?strstr@@YAPEADQEADQEBD@Z; strstr(char * const,char const * const)
0x180018eee  test    rax, rax
0x180018ef1  jz      loc_180018B7E
0x180018ef7  lea     rbx, [rax+4]
0x180018efb  xor     edx, edx; int
0x180018efd  mov     rcx, rbx; Src
0x180018f00  call    ?MySzDupA@@YAPEADPEBDH@Z; MySzDupA(char const *,int)
0x180018f05  mov     [r15+90h], rax
0x180018f0c  test    rax, rax
0x180018f0f  jz      loc_180018BAB
0x180018f15  mov     [rbx], r14b
0x180018f18  jmp     loc_180018B7E
0x180018f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f24  cmp     rcx, r12
0x180018f27  jz      short loc_180018F36
0x180018f29  test    dword ptr [rcx+1Ch], 1000h
0x180018f30  jnz     loc_180019419
0x180018f36  mov     r15, [rsp+2B8h+var_278]
0x180018f3b  mov     rcx, rbp; lpCriticalSection
0x180018f3e  call    cs:__imp_LeaveCriticalSection
0x180018f45  nop     dword ptr [rax+rax+00h]
0x180018f4a  mov     qword ptr [r15+80h], 0
0x180018f55  mov     r13, [rsp+2B8h+var_270]
0x180018f5a  lea     r10, off_18005A040; "Connection:"
0x180018f61  xor     ebx, ebx
0x180018f63  mov     r14d, 1
0x180018f69  nop     dword ptr [rax+00000000h]
  ... truncated ...
```
