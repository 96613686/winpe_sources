# CHttpRequest::UpdateVars(void)

- ea: `0x180003dc0`
- end: `0x1800047c6`
- name: `?UpdateVars@CHttpRequest@@AEAAHXZ`
- size: `2566`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002b40`

## callees

- `0x180003dc0`
- `0x1800047d0`
- `0x180006168`
- `0x1800062a8`
- `0x1800065f0`
- `0x180006680`
- `0x180028840`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18003a5a0`
- `0x18004e30c`
- `0x18004ea2c`
- `0x18004eaec`
- `0x18004eb70`
- `0x18004ec9c`
- `0x18004f898`
- `0x18004fc58`
- `0x18004fc6c`
- `0x18005430c`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180004050`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x180004050`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800046ab`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800046ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004137`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ffd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004137`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000415a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000427c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000439b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004441`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000415a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000427c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800042dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000439b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004789`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004108`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004392`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004108`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004392`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e34`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e87`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e34`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180003e87`

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
                                if ( !(&off_180056000)[v70] || *((_DWORD *)&off_180056000 + 2 * v70 + 3) == v53 )
                                  break;
                                v69 = ++v68;
                                if ( v68 >= 7 )
                                  goto LABEL_72;
                              }
                              if ( v69 < 7 && (&off_180056000)[v70 + 2] )
                              {
                                v71 = v54;
                                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                                {
                                  WPP_SF_s(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    12,
                                    WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids,
                                    (&off_180056000)[v70]);
                                }
                                if ( !(unsigned int)(*(__int64 (__fastcall **)(CHttpRequest *__hidden, char **, int, enum _HTTP_HEADER_ID))((char *)&funcs_18000453D + v70 * 8))(
                                                      v2,
                                                      &v82,
                                                      v71,
                                                      (enum _HTTP_HEADER_ID)*((_DWORD *)&off_180056000 + 2 * v70 + 3)) )
                                {
                                  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                                  {
                                    WPP_SF_s(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      13,
                                      WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids,
                                      (&off_180056000)[v70]);
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
0x180003dc0  push    rbx
0x180003dc2  push    rbp
0x180003dc3  push    rdi
0x180003dc4  push    r14
0x180003dc6  push    r15
0x180003dc8  sub     rsp, 290h
0x180003dcf  mov     rax, cs:__security_cookie
0x180003dd6  xor     rax, rsp
0x180003dd9  mov     [rsp+2B8h+var_38], rax
0x180003de1  xor     r14d, r14d
0x180003de4  mov     [rsp+2B8h+var_278], rcx
0x180003de9  mov     r15, rcx
0x180003dec  mov     [rsp+2B8h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180003df1  mov     rcx, [rcx+10h]
0x180003df5  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180003dfb  mov     [rsp+2B8h+var_270], rcx
0x180003e00  mov     ebp, r14d
0x180003e03  mov     [rsp+2B8h+lpDefaultChar], r14; lpDefaultChar
0x180003e08  mov     [rsp+2B8h+cbMultiByte], r14d; cbMultiByte
0x180003e0d  movzx   edx, word ptr [rcx+20h]
0x180003e11  movzx   eax, word ptr [rcx+22h]
0x180003e15  shl     edx, 10h
0x180003e18  or      edx, eax
0x180003e1a  mov     [rsp+2B8h+lpMultiByteStr], r14; lpMultiByteStr
0x180003e1f  mov     [r15+0D8h], edx
0x180003e26  mov     edx, 400h; dwFlags
0x180003e2b  mov     rdi, [rcx+58h]
0x180003e2f  xor     ecx, ecx; CodePage
0x180003e31  mov     r8, rdi; lpWideCharStr
0x180003e34  call    cs:__imp_WideCharToMultiByte
0x180003e3a  mov     ebx, eax
0x180003e3c  test    eax, eax
0x180003e3e  jz      loc_18000476D
0x180003e44  mov     rdx, cs:g_pvAllocData
0x180003e4b  lea     ecx, [rax+1]
0x180003e4e  call    svsutil_Alloc
0x180003e53  mov     [rsp+2B8h+Block], rax
0x180003e58  mov     rbp, rax
0x180003e5b  test    rax, rax
0x180003e5e  jz      loc_18000476D
0x180003e64  mov     [rsp+2B8h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180003e69  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180003e6f  mov     [rsp+2B8h+lpDefaultChar], r14; lpDefaultChar
0x180003e74  mov     r8, rdi; lpWideCharStr
0x180003e77  mov     [rsp+2B8h+cbMultiByte], ebx; cbMultiByte
0x180003e7b  mov     edx, 400h; dwFlags
0x180003e80  xor     ecx, ecx; CodePage
0x180003e82  mov     [rsp+2B8h+lpMultiByteStr], rax; lpMultiByteStr
0x180003e87  call    cs:__imp_WideCharToMultiByte
0x180003e8d  test    eax, eax
0x180003e8f  jz      loc_18000476D
0x180003e95  mov     [rsp+2B8h+arg_8], rsi
0x180003e9d  mov     rcx, rbp; char *
0x180003ea0  mov     [rsp+2B8h+arg_10], r12
0x180003ea8  mov     [rsp+2B8h+arg_18], r13
0x180003eb0  call    ?strchr@@YAPEADQEADH@Z; strchr(char * const,int)
0x180003eb5  mov     rsi, rax
0x180003eb8  test    rax, rax
0x180003ebb  jnz     loc_180004171
0x180003ec1  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180003ec8  cmp     [rax+18h], r14d
0x180003ecc  jnz     loc_180004224
0x180003ed2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003ed9  nop     dword ptr [rax+00000000h]
0x180003ee0  cmp     [rbx+rbp+1], r14b
0x180003ee5  lea     rbx, [rbx+1]
0x180003ee9  jnz     short loc_180003EE0
0x180003eeb  mov     rdx, cs:g_pvAllocData
0x180003ef2  lea     ecx, [rbx+2]
0x180003ef5  call    svsutil_Alloc
0x180003efa  mov     [r15+40h], rax
0x180003efe  mov     r8, rax
0x180003f01  test    rax, rax
0x180003f04  jnz     short loc_180003F51
0x180003f06  mov     rdx, cs:g_pvFreeData
0x180003f0d  mov     rcx, [rsp+2B8h+Block]; Block
0x180003f12  call    svsutil_Free
0x180003f17  mov     r12, [rsp+2B8h+arg_10]
0x180003f1f  mov     eax, r14d
0x180003f22  mov     r13, [rsp+2B8h+arg_18]
0x180003f2a  mov     rsi, [rsp+2B8h+arg_8]
0x180003f32  mov     rcx, [rsp+2B8h+var_38]
0x180003f3a  xor     rcx, rsp; StackCookie
0x180003f3d  call    __security_check_cookie
0x180003f42  add     rsp, 290h
0x180003f49  pop     r15
0x180003f4b  pop     r14
0x180003f4d  pop     rdi
0x180003f4e  pop     rbp
0x180003f4f  pop     rbx
0x180003f50  retn
0x180003f51  lea     eax, [rbx+1]
0x180003f54  movsxd  r9, eax
0x180003f57  test    eax, eax
0x180003f59  jz      short loc_180003F9C
0x180003f5b  cmp     r9, 7FFFFFFFh
0x180003f62  ja      loc_1800045A1
0x180003f68  mov     ecx, 7FFFFFFEh
0x180003f6d  mov     rdx, rbp
0x180003f70  test    rcx, rcx
0x180003f73  jz      short loc_180003F8E
0x180003f75  movzx   eax, byte ptr [rdx]
0x180003f78  test    al, al
0x180003f7a  jz      short loc_180003F8E
0x180003f7c  mov     [r8], al
0x180003f7f  inc     rdx
0x180003f82  inc     r8
0x180003f85  dec     rcx
0x180003f88  sub     r9, 1
0x180003f8c  jnz     short loc_180003F70
0x180003f8e  test    r9, r9
0x180003f91  lea     rax, [r8-1]
0x180003f95  cmovnz  rax, r8
0x180003f99  mov     [rax], r14b
0x180003f9c  mov     rcx, [r15+10h]
0x180003fa0  mov     eax, [rcx+24h]
0x180003fa3  mov     [r15+0DCh], eax
0x180003faa  cmp     eax, 4
0x180003fad  jnz     loc_180004481
0x180003fb3  lea     rax, aGet; "GET"
0x180003fba  mov     [r15+38h], rax
0x180003fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fc5  lea     r12, WPP_GLOBAL_Control
0x180003fcc  cmp     rcx, r12
0x180003fcf  jnz     loc_1800041F9
0x180003fd5  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180003fdc  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180003fe3  mov     r14, [r15+40h]
0x180003fe7  mov     rbp, [rax+10h]
0x180003feb  nop     dword ptr [rax+rax+00h]
0x180003ff0  inc     rsi
0x180003ff3  cmp     byte ptr [r14+rsi], 0
0x180003ff8  jnz     short loc_180003FF0
0x180003ffa  mov     rcx, rbp; lpCriticalSection
0x180003ffd  call    cs:__imp_EnterCriticalSection
0x180004003  cmp     qword ptr [rbp+30h], 0
0x180004008  jz      loc_180004279
0x18000400e  xor     ebx, ebx
0x180004010  cmp     ebx, [rbp+28h]
0x180004013  jge     loc_18000425B
0x180004019  mov     rdx, [rbp+30h]
0x18000401d  movsxd  rax, ebx
0x180004020  imul    rdi, rax, 38h ; '8'
0x180004024  cmp     dword ptr [rdx+rdi+28h], 0
0x180004029  mov     eax, [rdx+rdi]
0x18000402c  jnz     loc_1800045C7
0x180004032  test    eax, eax
0x180004034  jz      loc_1800041F2
0x18000403a  cmp     esi, eax
0x18000403c  jl      loc_1800041F2
0x180004042  mov     rdx, [rdx+rdi+8]
0x180004047  mov     rcx, r14
0x18000404a  movsxd  r15, eax
0x18000404d  mov     r8, r15
0x180004050  call    cs:__imp__o__memicmp
0x180004056  test    eax, eax
0x180004058  jnz     loc_1800041F2
0x18000405e  mov     rdx, [rbp+30h]
0x180004062  add     rdx, rdi; int
0x180004065  cmp     [rdx+28h], eax
0x180004068  jnz     loc_1800041D4
0x18000406e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004075  cmp     rcx, r12
0x180004078  jz      short loc_180004087
0x18000407a  test    dword ptr [rcx+1Ch], 1000h
0x180004081  jnz     loc_1800045D7
0x180004087  mov     r13, [rbp+30h]
0x18000408b  add     r13, rdi
0x18000408e  jz      loc_180004274
0x180004094  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000409b  nop     dword ptr [rax+rax+00h]
0x1800040a0  inc     rdi
0x1800040a3  cmp     byte ptr [r14+rdi], 0
0x1800040a8  jnz     short loc_1800040A0
0x1800040aa  mov     rcx, r14; char *
0x1800040ad  call    ?strrchr@@YAPEADQEADH@Z; strrchr(char * const,int)
0x1800040b2  mov     r15, rax
0x1800040b5  mov     rbx, rax
0x1800040b8  test    rax, rax
0x1800040bb  jz      loc_180004470
0x1800040c1  cmp     byte ptr [rax], 2Fh ; '/'
0x1800040c4  jz      short loc_1800040D3
0x1800040c6  cmp     byte ptr [rbx], 0
0x1800040c9  jz      short loc_1800040D3
0x1800040cb  inc     rbx
0x1800040ce  cmp     byte ptr [rbx], 2Fh ; '/'
0x1800040d1  jnz     short loc_1800040C6
0x1800040d3  inc     rbx
0x1800040d6  mov     rax, rbx
0x1800040d9  sub     rax, r15
0x1800040dc  cmp     rax, 104h
0x1800040e2  jg      loc_180004601
0x1800040e8  mov     eax, ebx
0x1800040ea  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800040f0  sub     eax, r15d
0x1800040f3  mov     r8, r15; lpMultiByteStr
0x1800040f6  mov     [rsp+2B8h+cbMultiByte], eax; cchWideChar
0x1800040fa  xor     edx, edx; dwFlags
0x1800040fc  lea     rax, [rsp+2B8h+WideCharStr]
0x180004101  xor     ecx, ecx; CodePage
0x180004103  mov     [rsp+2B8h+lpMultiByteStr], rax; lpWideCharStr
0x180004108  call    cs:__imp_MultiByteToWideChar
0x18000410e  test    eax, eax
0x180004110  jz      loc_18000444F
0x180004116  mov     rax, rbx
0x180004119  sub     rax, r15
0x18000411c  lea     rcx, [rax+rax]
0x180004120  cmp     rcx, 20Ah
0x180004127  jnb     loc_180004424
0x18000412d  xor     eax, eax
0x18000412f  mov     [rsp+rcx+2B8h+WideCharStr], ax
0x180004134  mov     rcx, rbp; lpCriticalSection
0x180004137  call    cs:__imp_EnterCriticalSection
0x18000413d  mov     r8d, edi; int
0x180004140  mov     rdx, r14; char *
0x180004143  mov     rcx, rbp; this
0x180004146  call    ?MatchVRoot@CVRoots@@AEAAPEAUVROOTINFO@@PEBDH@Z; CVRoots::MatchVRoot(char const *,int)
0x18000414b  mov     rdi, rax
0x18000414e  test    rax, rax
0x180004151  jnz     loc_1800042C6
0x180004157  mov     rcx, rbp; lpCriticalSection
0x18000415a  call    cs:__imp_LeaveCriticalSection
0x180004160  mov     r15, [rsp+2B8h+var_278]
0x180004165  add     r15, 90h
0x18000416c  jmp     loc_1800042F7
0x180004171  lea     rdi, [rax+1]
0x180004175  test    rdi, rdi
0x180004178  jz      loc_1800044A9
0x18000417e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180004185  inc     rbx
0x180004188  cmp     [rdi+rbx], r14b
0x18000418c  jnz     short loc_180004185
0x18000418e  mov     rdx, cs:g_pvAllocData
0x180004195  lea     ecx, [rbx+1]
0x180004198  call    svsutil_Alloc
0x18000419d  mov     rbp, rax
0x1800041a0  test    rax, rax
0x1800041a3  jz      short loc_1800041BA
0x1800041a5  movsxd  rbx, ebx
0x1800041a8  mov     rdx, rdi; Src
0x1800041ab  mov     r8, rbx; Size
0x1800041ae  mov     rcx, rax; void *
0x1800041b1  call    memcpy_0
0x1800041b6  mov     [rbx+rbp], r14b
0x1800041ba  mov     [r15+78h], rbp
0x1800041be  test    rbp, rbp
0x1800041c1  jz      loc_180003F06
0x1800041c7  mov     rbp, [rsp+2B8h+Block]
0x1800041cc  mov     [rsi], r14b
0x1800041cf  jmp     loc_180003EC1
0x1800041d4  cmp     dword ptr [rdx], 1
0x1800041d7  jz      loc_18000406E
0x1800041dd  movzx   eax, byte ptr [r14+r15]
0x1800041e2  cmp     al, 2Fh ; '/'
0x1800041e4  jz      loc_18000406E
0x1800041ea  test    al, al
0x1800041ec  jz      loc_18000406E
0x1800041f2  inc     ebx
0x1800041f4  jmp     loc_180004010
0x1800041f9  test    dword ptr [rcx+1Ch], 1000h
0x180004200  jz      loc_180003FD5
0x180004206  mov     r9, [r15+38h]
0x18000420a  lea     r8, WPP_f08ef8a88f173f3f14f74f015bbda39e_Traceguids
0x180004211  mov     rcx, [rcx+10h]
0x180004215  mov     edx, 0Bh
0x18000421a  call    WPP_SF_s
0x18000421f  jmp     loc_180003FD5
0x180004224  mov     rcx, rbp; char *
0x180004227  call    ?strstr@@YAPEADQEADQEBD@Z; strstr(char * const,char const * const)
0x18000422c  test    rax, rax
0x18000422f  jz      loc_180003ED2
0x180004235  lea     rbx, [rax+4]
0x180004239  xor     edx, edx; int
0x18000423b  mov     rcx, rbx; Src
0x18000423e  call    ?MySzDupA@@YAPEADPEBDH@Z; MySzDupA(char const *,int)
0x180004243  mov     [r15+90h], rax
0x18000424a  test    rax, rax
0x18000424d  jz      loc_180003F06
0x180004253  mov     [rbx], r14b
0x180004256  jmp     loc_180003ED2
0x18000425b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004262  cmp     rcx, r12
0x180004265  jz      short loc_180004274
0x180004267  test    dword ptr [rcx+1Ch], 1000h
0x18000426e  jnz     loc_18000472C
0x180004274  mov     r15, [rsp+2B8h+var_278]
0x180004279  mov     rcx, rbp; lpCriticalSection
0x18000427c  call    cs:__imp_LeaveCriticalSection
0x180004282  mov     qword ptr [r15+80h], 0
0x18000428d  mov     r13, [rsp+2B8h+var_270]
0x180004292  lea     r10, off_180056000; "Connection:"
0x180004299  xor     ebx, ebx
0x18000429b  mov     r14d, 1
0x1800042a1  cmp     ebx, 29h ; ')'
0x1800042a4  jge     loc_180003F06
0x1800042aa  movsxd  rax, ebx
0x1800042ad  add     rax, rax
0x1800042b0  movzx   edx, word ptr [r13+rax*8+98h]
0x1800042b9  test    dx, dx
0x1800042bc  jnz     loc_1800044B2
  ... truncated ...
```
