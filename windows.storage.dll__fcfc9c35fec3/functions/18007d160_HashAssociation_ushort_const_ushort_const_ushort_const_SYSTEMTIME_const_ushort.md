# HashAssociation(ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)

- ea: `0x18007d160`
- end: `0x18007dab2`
- name: `?HashAssociation@@YAJPEBG00AEBU_SYSTEMTIME@@PEAPEAG@Z`
- size: `2386`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _SYSTEMTIME *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f909c`
- `0x1805917dc`
- `0x1805941d0`
- `0x180617a14`

## callees

- `0x180038f50`
- `0x180045bd0`
- `0x18007bf50`
- `0x18007d160`
- `0x18007dcf0`
- `0x180083c94`
- `0x18018e720`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18007d833`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18007d833`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007d66c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007d66c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d2b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d74e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d2b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d58a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18007d74e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d2f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d2f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d85f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d89b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d9ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d463`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d85f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d89b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007d9ce`

## pseudocode

```c
__int64 __fastcall HashAssociation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SYSTEMTIME *a4,
        unsigned __int16 **a5)
{
  _WORD *v5; // r12
  unsigned __int64 v6; // r13
  unsigned __int64 v7; // rsi
  const unsigned __int16 *v9; // rbx
  unsigned __int64 v11; // r13
  unsigned __int64 v12; // rdi
  int v13; // r8d
  int v14; // edi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rdi
  __int64 v17; // r8
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  _WORD *v20; // rax
  _WORD *v21; // rax
  int v22; // r12d
  void *v23; // rdi
  unsigned __int64 v24; // rdx
  _WORD *v25; // r8
  unsigned __int64 v26; // rcx
  _WORD *v27; // rcx
  unsigned __int64 v28; // rbx
  unsigned __int64 v29; // r14
  _WORD *v31; // rax
  _WORD *v32; // rcx
  unsigned __int64 v33; // rcx
  _WORD *v34; // rdx
  __int64 v35; // r8
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rcx
  _WORD *v38; // rax
  _WORD *v39; // rax
  unsigned __int64 v40; // rdx
  _WORD *v41; // r8
  unsigned __int64 v42; // rcx
  _WORD *v43; // rcx
  const char *v44; // r9
  int v45; // eax
  int LastError; // ebx
  int v47; // eax
  unsigned __int64 v48; // rbx
  unsigned __int64 v49; // rdx
  _WORD *v50; // rax
  _WORD *v51; // rax
  __int64 v52; // rax
  const wchar_t *v53; // rcx
  __int64 v54; // r9
  _WORD *v55; // r8
  _WORD *v56; // rcx
  unsigned __int64 v57; // rsi
  int v58; // eax
  unsigned int v59; // ebx
  DWORD dwLowDateTime; // [rsp+20h] [rbp-71h]
  LPVOID pv; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v62; // [rsp+38h] [rbp-59h]
  unsigned __int64 v63; // [rsp+40h] [rbp-51h]
  struct _FILETIME FileTime; // [rsp+48h] [rbp-49h] BYREF
  unsigned __int16 **v65; // [rsp+50h] [rbp-41h]
  __int64 v66; // [rsp+58h] [rbp-39h]
  unsigned __int64 v67; // [rsp+60h] [rbp-31h]
  SYSTEMTIME *lpSystemTime; // [rsp+68h] [rbp-29h]
  unsigned __int16 v69[20]; // [rsp+70h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v5 = 0;
  v6 = 0;
  lpSystemTime = a4;
  v7 = 0;
  v65 = a5;
  FileTime = 0;
  *a5 = 0;
  v9 = a2;
  pv = 0;
  v62 = 0;
  v67 = 0;
  v63 = 0;
  if ( !a2 )
  {
LABEL_8:
    v14 = -2147024882;
    LODWORD(v66) = -2147024882;
    if ( !a1 )
      goto LABEL_41;
    v15 = -1;
    do
      ++v15;
    while ( a1[v15] );
    if ( v7 == -1 )
    {
      if ( v5 )
      {
        do
          ++v7;
        while ( v5[v7] );
      }
      else
      {
        v7 = 0;
      }
    }
    v16 = v15 + v7 + 1;
    if ( v16 < v15 + v7 )
      goto LABEL_52;
    if ( v6 != -1 )
    {
LABEL_16:
      if ( v6 )
      {
        if ( v16 <= v6 )
        {
LABEL_30:
          v24 = v15 + 1;
          v25 = &v5[v7];
          if ( v15 != -1 )
          {
            if ( v24 > 0x7FFFFFFF || v15 > 0x7FFFFFFE )
            {
              *v25 = 0;
            }
            else
            {
              v26 = v15;
              do
              {
                if ( !v26 )
                  break;
                if ( !*a1 )
                  break;
                *v25++ = *a1++;
                --v26;
                --v24;
              }
              while ( v24 );
              v27 = v25 - 1;
              if ( v24 )
                v27 = v25;
              *v27 = 0;
            }
          }
          v14 = v66;
          v7 += v15;
          v62 = v7;
LABEL_41:
          if ( !a3 )
            goto LABEL_95;
          v28 = -1;
          do
            ++v28;
          while ( a3[v28] );
          if ( v7 == -1 )
          {
            if ( v5 )
            {
              do
                ++v7;
              while ( v5[v7] );
            }
            else
            {
              v7 = 0;
            }
            v62 = v7;
          }
          v29 = v28 + v7 + 1;
          if ( v29 < v28 + v7 )
            goto LABEL_49;
          if ( v6 != -1 )
          {
LABEL_71:
            if ( v6 )
            {
              if ( v29 > v6 )
              {
                v67 = 0;
                v35 = 2 * v6;
                if ( is_mul_ok(v6, 2u) )
                {
                  v36 = v6;
                  v37 = v6 + 2048;
                  v6 = v29;
                  if ( v36 <= 0x800 )
                    v37 = v35;
                  if ( v29 <= v37 )
                    v6 = v37;
                  v38 = CoTaskMemRealloc(v5, 2 * v6);
                  v5 = v38;
                  if ( !v38 )
                    goto LABEL_50;
                  v63 = v6;
                  pv = v38;
                  goto LABEL_84;
                }
LABEL_49:
                v14 = -2147024362;
LABEL_50:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD2,
                  (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                  (const char *)(unsigned int)v14,
                  dwLowDateTime);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
                return (unsigned int)v14;
              }
            }
            else
            {
              v67 = 0;
              if ( !is_mul_ok(v29, 2u) )
                goto LABEL_49;
              v39 = CoTaskMemAlloc(2 * v29);
              if ( v39 )
              {
                v14 = 0;
                pv = v39;
                v5 = v39;
                v63 = v29;
                v6 = v29;
                *v39 = 0;
              }
              if ( v14 < 0 )
                goto LABEL_50;
            }
LABEL_84:
            v40 = v28 + 1;
            v41 = &v5[v7];
            if ( v28 != -1 )
            {
              if ( v40 > 0x7FFFFFFF || v28 > 0x7FFFFFFE )
              {
                *v41 = 0;
              }
              else
              {
                v42 = v28;
                do
                {
                  if ( !v42 )
                    break;
                  if ( !*a3 )
                    break;
                  *v41++ = *a3++;
                  --v42;
                  --v40;
                }
                while ( v40 );
                v43 = v41 - 1;
                if ( v40 )
                  v43 = v41;
                *v43 = 0;
              }
            }
            v7 += v28;
            v62 = v7;
LABEL_95:
            FileTime = 0;
            if ( SystemTimeToFileTime(lpSystemTime, &FileTime) )
            {
              dwLowDateTime = FileTime.dwLowDateTime;
              v45 = StringCchPrintfW(v69, 0x11u, L"%08x%08x", FileTime.dwHighDateTime);
              LastError = v45;
              if ( v45 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBE,
                  (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                  (const char *)(unsigned int)v45,
                  dwLowDateTime);
                goto LABEL_139;
              }
              v47 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                      &pv,
                      v69);
              LastError = v47;
              if ( v47 < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBF,
                  (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                  (const char *)(unsigned int)v47,
                  dwLowDateTime);
              v6 = v63;
              v7 = v62;
              v5 = pv;
            }
            else
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0xBB,
                            (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                            v44);
            }
            if ( LastError >= 0 )
            {
              if ( v7 == -1 )
              {
                if ( v5 )
                {
                  do
                    ++v7;
                  while ( v5[v7] );
                }
                else
                {
                  v7 = 0;
                }
              }
              v48 = v7 + 83;
              if ( v7 + 83 < v7 + 82 )
                goto LABEL_134;
              if ( v6 != -1 )
              {
LABEL_106:
                if ( v6 )
                {
                  if ( v48 <= v6 )
                    goto LABEL_119;
                  if ( is_mul_ok(v6, 2u) )
                  {
                    v49 = v6 + 2048;
                    if ( v6 <= 0x800 )
                      v49 = 2 * v6;
                    if ( v48 <= v49 )
                      v48 = v49;
                    v50 = CoTaskMemRealloc(v5, 2 * v48);
                    if ( v50 )
                    {
                      v63 = v48;
                      v5 = v50;
                      pv = v50;
LABEL_119:
                      v52 = 82;
                      v53 = L"User Choice set via Windows User Experience {D18B6DD5-6124-4341-9318-804003BAFA0B}";
                      v54 = 83;
                      v55 = &v5[v7];
                      do
                      {
                        if ( !v52 )
                          break;
                        if ( !*v53 )
                          break;
                        *v55++ = *v53++;
                        --v52;
                        --v54;
                      }
                      while ( v54 );
                      v56 = v55 - 1;
                      if ( v54 )
                        v56 = v55;
                      v57 = v7 + 82;
                      v62 = v57;
                      *v56 = 0;
                      if ( v57 == -1 )
                      {
                        if ( v5 )
                        {
                          do
                            ++v57;
                          while ( v5[v57] );
                          v62 = v57;
                        }
                        else
                        {
                          LODWORD(v57) = 0;
                          v62 = 0;
                        }
                      }
                      CharLowerBuffW(v5, v57);
                      v58 = ComputeHashFromString(&pv, v65);
                      v59 = v58;
                      if ( v58 < 0 )
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xD7,
                          (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                          (const char *)(unsigned int)v58,
                          dwLowDateTime);
                      if ( pv )
                        CoTaskMemFree(pv);
                      return v59;
                    }
                    v14 = v66;
LABEL_135:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xD4,
                      (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
                      (const char *)(unsigned int)v14,
                      dwLowDateTime);
                    if ( v5 )
                      CoTaskMemFree(v5);
                    return (unsigned int)v14;
                  }
                }
                else if ( is_mul_ok(v48, 2u) )
                {
                  v51 = CoTaskMemAlloc(2 * v48);
                  if ( v51 )
                  {
                    v14 = 0;
                    v63 = v48;
                    v5 = v51;
                    pv = v51;
                    *v51 = 0;
                  }
                  else
                  {
                    v14 = v66;
                  }
                  if ( v14 >= 0 )
                    goto LABEL_119;
                  goto LABEL_135;
                }
LABEL_134:
                v14 = -2147024362;
                goto LABEL_135;
              }
              if ( v7 == -1 )
              {
                if ( !v5 )
                {
                  v7 = 0;
LABEL_171:
                  v6 = 0;
                  v63 = 0;
                  goto LABEL_106;
                }
                do
                  ++v7;
                while ( v5[v7] );
              }
              if ( v5 )
              {
                v6 = v7 + 1;
                v63 = v7 + 1;
                goto LABEL_106;
              }
              goto LABEL_171;
            }
LABEL_139:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD3,
              (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
              (const char *)(unsigned int)LastError,
              dwLowDateTime);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
            return (unsigned int)LastError;
          }
          if ( v7 == -1 )
          {
            if ( !v5 )
            {
              v7 = 0;
              v62 = 0;
              goto LABEL_169;
            }
            do
              ++v7;
            while ( v5[v7] );
            v62 = v7;
          }
          if ( v5 )
          {
            v6 = v7 + 1;
LABEL_152:
            v63 = v6;
            goto LABEL_71;
          }
LABEL_169:
          v6 = 0;
          goto LABEL_152;
        }
        v67 = 0;
        v17 = 2 * v6;
        if ( is_mul_ok(v6, 2u) )
        {
          v18 = v6;
          v19 = v6 + 2048;
          v6 = v16;
          if ( v18 <= 0x800 )
            v19 = v17;
          if ( v16 <= v19 )
            v6 = v19;
          v20 = CoTaskMemRealloc(v5, 2 * v6);
          if ( v20 )
          {
            v63 = v6;
            v5 = v20;
            pv = v20;
            goto LABEL_30;
          }
          v22 = v66;
          goto LABEL_53;
        }
      }
      else
      {
        v67 = 0;
        if ( is_mul_ok(v16, 2u) )
        {
          v21 = CoTaskMemAlloc(2 * v16);
          if ( v21 )
          {
            v22 = 0;
            v63 = v16;
            v6 = v16;
            FileTime = (struct _FILETIME)v21;
            v23 = v21;
            pv = v21;
            *v21 = 0;
          }
          else
          {
            v22 = v66;
            v23 = (void *)FileTime;
          }
          if ( v22 >= 0 )
          {
            v5 = (_WORD *)FileTime;
            goto LABEL_30;
          }
          goto LABEL_54;
        }
      }
LABEL_52:
      v22 = -2147024362;
LABEL_53:
      v23 = (void *)FileTime;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
        (const char *)(unsigned int)v22,
        dwLowDateTime);
      if ( v23 )
        CoTaskMemFree(v23);
      return (unsigned int)v22;
    }
    if ( v7 == -1 )
    {
      if ( !v5 )
      {
        v7 = 0;
        goto LABEL_167;
      }
      do
        ++v7;
      while ( v5[v7] );
    }
    if ( v5 )
    {
      v6 = v7 + 1;
LABEL_145:
      v63 = v6;
      goto LABEL_16;
    }
LABEL_167:
    v6 = 0;
    goto LABEL_145;
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = v11 + 1;
  if ( v11 + 1 < v11 || (v66 = 0, !is_mul_ok(v12, 2u)) )
  {
    v13 = -2147024362;
    LODWORD(v66) = -2147024362;
    goto LABEL_6;
  }
  v31 = CoTaskMemAlloc(2 * v12);
  v32 = v31;
  if ( !v31 )
  {
    v13 = -2147024882;
    LODWORD(v66) = -2147024882;
    goto LABEL_159;
  }
  FileTime = (struct _FILETIME)v31;
  v13 = 0;
  v67 = v11 + 1;
  v63 = v11 + 1;
  v5 = v31;
  LODWORD(v66) = 0;
  pv = v31;
  *v31 = 0;
  if ( v11 == -1 )
  {
    LODWORD(v66) = 0;
    goto LABEL_69;
  }
  if ( v12 <= 0x7FFFFFFF )
  {
    LODWORD(v66) = 0;
    if ( v11 > 0x7FFFFFFE )
    {
      *v31 = 0;
      goto LABEL_69;
    }
    v33 = v11;
    v34 = v31;
    do
    {
      if ( !v33 )
        break;
      if ( !*v9 )
        break;
      *v34++ = *v9++;
      --v33;
      --v12;
    }
    while ( v12 );
    v32 = v34 - 1;
    if ( v12 )
      v32 = v34;
  }
  *v32 = 0;
LABEL_69:
  v7 = v11;
  v62 = v11;
LABEL_6:
  if ( v13 >= 0 )
  {
    v6 = v67;
    goto LABEL_8;
  }
LABEL_159:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD0,
    (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
    (const char *)(unsigned int)v13,
    dwLowDateTime);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v66;
}

```

## disassembly

```asm
0x18007d160  push    rbp
0x18007d162  push    rbx
0x18007d163  push    rsi
0x18007d164  push    rdi
0x18007d165  push    r12
0x18007d167  push    r13
0x18007d169  push    r14
0x18007d16b  push    r15
0x18007d16d  lea     rbp, [rsp-17h]
0x18007d172  sub     rsp, 0A8h
0x18007d179  mov     rax, cs:__security_cookie
0x18007d180  xor     rax, rsp
0x18007d183  mov     [rbp+4Fh+var_48], rax
0x18007d187  mov     rax, [rbp+4Fh+arg_20]
0x18007d18b  xor     r12d, r12d
0x18007d18e  xor     r13d, r13d
0x18007d191  mov     [rbp+4Fh+lpSystemTime], r9
0x18007d195  xor     esi, esi
0x18007d197  mov     [rbp+4Fh+var_90], rax
0x18007d19b  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], r12
0x18007d19f  mov     r15, r8
0x18007d1a2  mov     qword ptr [rax], 0
0x18007d1a9  mov     rbx, rdx
0x18007d1ac  mov     [rbp+4Fh+pv], r12
0x18007d1b0  mov     r14, rcx
0x18007d1b3  mov     [rbp+4Fh+var_A8], rsi
0x18007d1b7  mov     [rbp+4Fh+var_80], r13
0x18007d1bb  mov     [rbp+4Fh+var_A0], r13
0x18007d1bf  test    rdx, rdx
0x18007d1c2  jz      short loc_18007D1FE
0x18007d1c4  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18007d1cb  nop     dword ptr [rax+rax+00h]
0x18007d1d0  inc     r13
0x18007d1d3  cmp     [rdx+r13*2], si
0x18007d1d8  jnz     short loc_18007D1D0
0x18007d1da  lea     rdi, [r13+1]
0x18007d1de  cmp     rdi, r13
0x18007d1e1  jnb     loc_18007D474
0x18007d1e7  mov     r8d, 80070216h
0x18007d1ed  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18007d1f1  test    r8d, r8d
0x18007d1f4  js      loc_18007D9AE
0x18007d1fa  mov     r13, [rbp+4Fh+var_80]
0x18007d1fe  mov     edi, 8007000Eh
0x18007d203  mov     dword ptr [rbp+4Fh+var_88], edi
0x18007d206  test    r14, r14
0x18007d209  jz      loc_18007D39D
0x18007d20f  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d216  nop     word ptr [rax+rax+00000000h]
0x18007d220  inc     rbx
0x18007d223  cmp     word ptr [r14+rbx*2], 0
0x18007d229  jnz     short loc_18007D220
0x18007d22b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007d22f  jnz     short loc_18007D24B
0x18007d231  test    r12, r12
0x18007d234  jz      loc_18007DA2F
0x18007d23a  nop     word ptr [rax+rax+00h]
0x18007d240  inc     rsi
0x18007d243  cmp     word ptr [r12+rsi*2], 0
0x18007d249  jnz     short loc_18007D240
0x18007d24b  lea     rax, [rbx+rsi]
0x18007d24f  lea     rdi, [rax+1]
0x18007d253  cmp     rdi, rax
0x18007d256  jb      loc_18007D439
0x18007d25c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18007d260  jz      loc_18007D908
0x18007d266  test    r13, r13
0x18007d269  jz      short loc_18007D2DB
0x18007d26b  cmp     rdi, r13
0x18007d26e  jbe     loc_18007D336
0x18007d274  mov     eax, 2
0x18007d279  mov     [rbp+4Fh+var_80], 0
0x18007d281  mul     r13
0x18007d284  mov     r8, rax
0x18007d287  test    rdx, rdx
0x18007d28a  jnz     loc_18007D439
0x18007d290  sub     rax, r13
0x18007d293  lea     rcx, [r13+800h]
0x18007d29a  cmp     rax, 800h
0x18007d2a0  mov     r13, rdi
0x18007d2a3  cmovbe  rcx, r8
0x18007d2a7  cmp     rdi, rcx
0x18007d2aa  cmovbe  r13, rcx
0x18007d2ae  mov     rcx, r12; pv
0x18007d2b1  lea     rdx, ds:0[r13*2]; cb
0x18007d2b9  call    cs:__imp_CoTaskMemRealloc
0x18007d2c0  nop     dword ptr [rax+rax+00h]
0x18007d2c5  test    rax, rax
0x18007d2c8  jz      loc_18007D9F7
0x18007d2ce  mov     [rbp+4Fh+var_A0], r13
0x18007d2d2  mov     r12, rax
0x18007d2d5  mov     [rbp+4Fh+pv], rax
0x18007d2d9  jmp     short loc_18007D336
0x18007d2db  mov     eax, 2
0x18007d2e0  mov     [rbp+4Fh+var_80], 0
0x18007d2e8  mul     rdi
0x18007d2eb  test    rdx, rdx
0x18007d2ee  jnz     loc_18007D439
0x18007d2f4  mov     rcx, rax; cb
0x18007d2f7  call    cs:__imp_CoTaskMemAlloc
0x18007d2fe  nop     dword ptr [rax+rax+00h]
0x18007d303  mov     rcx, rax
0x18007d306  test    rax, rax
0x18007d309  jz      loc_18007D9E2
0x18007d30f  xor     r12d, r12d
0x18007d312  mov     [rbp+4Fh+var_A0], rdi
0x18007d316  mov     r13, rdi
0x18007d319  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], rax
0x18007d31d  mov     rdi, rax
0x18007d320  mov     [rbp+4Fh+pv], rax
0x18007d324  xor     eax, eax
0x18007d326  mov     [rcx], ax
0x18007d329  test    r12d, r12d
0x18007d32c  js      loc_18007D443
0x18007d332  mov     r12, qword ptr [rbp+4Fh+FileTime.dwLowDateTime]
0x18007d336  lea     rdx, [rbx+1]
0x18007d33a  lea     r8, [r12+rsi*2]
0x18007d33e  test    rdx, rdx
0x18007d341  jz      short loc_18007D393
0x18007d343  cmp     rdx, 7FFFFFFFh
0x18007d34a  ja      loc_18007DA62
0x18007d350  cmp     rbx, 7FFFFFFEh
0x18007d357  ja      loc_18007DA62
0x18007d35d  mov     rcx, rbx
0x18007d360  test    rcx, rcx
0x18007d363  jz      short loc_18007D383
0x18007d365  movzx   eax, word ptr [r14]
0x18007d369  test    ax, ax
0x18007d36c  jz      short loc_18007D383
0x18007d36e  mov     [r8], ax
0x18007d372  add     r14, 2
0x18007d376  add     r8, 2
0x18007d37a  dec     rcx
0x18007d37d  sub     rdx, 1
0x18007d381  jnz     short loc_18007D360
0x18007d383  test    rdx, rdx
0x18007d386  lea     rcx, [r8-2]
0x18007d38a  cmovnz  rcx, r8
0x18007d38e  xor     eax, eax
0x18007d390  mov     [rcx], ax
0x18007d393  mov     edi, dword ptr [rbp+4Fh+var_88]
0x18007d396  add     rsi, rbx
0x18007d399  mov     [rbp+4Fh+var_A8], rsi
0x18007d39d  test    r15, r15
0x18007d3a0  jz      loc_18007D65D
0x18007d3a6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18007d3ad  nop     dword ptr [rax]
0x18007d3b0  inc     rbx
0x18007d3b3  cmp     word ptr [r15+rbx*2], 0
0x18007d3b9  jnz     short loc_18007D3B0
0x18007d3bb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18007d3bf  jnz     short loc_18007D3DF
0x18007d3c1  test    r12, r12
0x18007d3c4  jz      loc_18007DA36
0x18007d3ca  nop     word ptr [rax+rax+00h]
0x18007d3d0  inc     rsi
0x18007d3d3  cmp     word ptr [r12+rsi*2], 0
0x18007d3d9  jnz     short loc_18007D3D0
0x18007d3db  mov     [rbp+4Fh+var_A8], rsi
0x18007d3df  lea     rax, [rbx+rsi]
0x18007d3e3  lea     r14, [rax+1]
0x18007d3e7  cmp     r14, rax
0x18007d3ea  jnb     loc_18007D52D
0x18007d3f0  mov     edi, 80070216h
0x18007d3f5  mov     rcx, [rbp+57h]; this
0x18007d3f9  lea     r8, aOnecoreShellLi_4; "onecore\\shell\\lib\\userchoicehelpers"...
0x18007d400  mov     r9d, edi; char *
0x18007d403  mov     edx, 0D2h; void *
0x18007d408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d40d  lea     rcx, [rbp+4Fh+pv]; void *
0x18007d411  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18007d416  mov     eax, edi
0x18007d418  mov     rcx, [rbp+4Fh+var_48]
0x18007d41c  xor     rcx, rsp; StackCookie
0x18007d41f  call    __security_check_cookie
0x18007d424  add     rsp, 0A8h
0x18007d42b  pop     r15
0x18007d42d  pop     r14
0x18007d42f  pop     r13
0x18007d431  pop     r12
0x18007d433  pop     rdi
0x18007d434  pop     rsi
0x18007d435  pop     rbx
0x18007d436  pop     rbp
0x18007d437  retn
0x18007d439  mov     r12d, 80070216h
0x18007d43f  mov     rdi, qword ptr [rbp+4Fh+FileTime.dwLowDateTime]
0x18007d443  mov     rcx, [rbp+57h]; this
0x18007d447  lea     r8, aOnecoreShellLi_4; "onecore\\shell\\lib\\userchoicehelpers"...
0x18007d44e  mov     r9d, r12d; char *
0x18007d451  mov     edx, 0D1h; void *
0x18007d456  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d45b  test    rdi, rdi
0x18007d45e  jz      short loc_18007D46F
0x18007d460  mov     rcx, rdi; pv
0x18007d463  call    cs:__imp_CoTaskMemFree
0x18007d46a  nop     dword ptr [rax+rax+00h]
0x18007d46f  mov     eax, r12d
0x18007d472  jmp     short loc_18007D418
0x18007d474  mov     eax, 2
0x18007d479  mov     [rbp+4Fh+var_88], rsi
0x18007d47d  mul     rdi
0x18007d480  test    rdx, rdx
0x18007d483  jnz     loc_18007D1E7
0x18007d489  mov     rcx, rax; cb
0x18007d48c  call    cs:__imp_CoTaskMemAlloc
0x18007d493  nop     dword ptr [rax+rax+00h]
0x18007d498  mov     rcx, rax
0x18007d49b  test    rax, rax
0x18007d49e  jz      loc_18007D9A4
0x18007d4a4  mov     rax, rdi
0x18007d4a7  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], rcx
0x18007d4ab  xor     r8d, r8d
0x18007d4ae  mov     [rbp+4Fh+var_80], rax
0x18007d4b2  mov     [rbp+4Fh+var_A0], rax
0x18007d4b6  mov     r12, rcx
0x18007d4b9  xor     eax, eax
0x18007d4bb  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18007d4bf  mov     [rbp+4Fh+pv], rcx
0x18007d4c3  mov     [rcx], ax
0x18007d4c6  test    rdi, rdi
0x18007d4c9  jz      loc_18007DA59
0x18007d4cf  cmp     rdi, 7FFFFFFFh
0x18007d4d6  ja      short loc_18007D51E
0x18007d4d8  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18007d4dc  cmp     r13, 7FFFFFFEh
0x18007d4e3  ja      loc_18007DA51
0x18007d4e9  mov     rcx, r13
0x18007d4ec  mov     rdx, r12
0x18007d4ef  nop
0x18007d4f0  test    rcx, rcx
0x18007d4f3  jz      short loc_18007D511
0x18007d4f5  movzx   eax, word ptr [rbx]
0x18007d4f8  test    ax, ax
0x18007d4fb  jz      short loc_18007D511
0x18007d4fd  mov     [rdx], ax
0x18007d500  add     rbx, 2
0x18007d504  add     rdx, 2
0x18007d508  dec     rcx
0x18007d50b  sub     rdi, 1
0x18007d50f  jnz     short loc_18007D4F0
0x18007d511  test    rdi, rdi
0x18007d514  lea     rcx, [rdx-2]
0x18007d518  cmovnz  rcx, rdx
0x18007d51c  xor     eax, eax
0x18007d51e  mov     [rcx], ax
0x18007d521  mov     rsi, r13
0x18007d524  mov     [rbp+4Fh+var_A8], r13
0x18007d528  jmp     loc_18007D1F1
0x18007d52d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18007d531  jz      loc_18007D941
0x18007d537  test    r13, r13
0x18007d53a  jz      short loc_18007D5AC
0x18007d53c  cmp     r14, r13
0x18007d53f  jbe     loc_18007D5F9
0x18007d545  mov     eax, 2
0x18007d54a  mov     [rbp+4Fh+var_80], 0
0x18007d552  mul     r13
0x18007d555  mov     r8, rax
0x18007d558  test    rdx, rdx
0x18007d55b  jnz     loc_18007D3F0
0x18007d561  sub     rax, r13
0x18007d564  lea     rcx, [r13+800h]
0x18007d56b  cmp     rax, 800h
0x18007d571  mov     r13, r14
0x18007d574  cmovbe  rcx, r8
0x18007d578  cmp     r14, rcx
0x18007d57b  cmovbe  r13, rcx
0x18007d57f  mov     rcx, r12; pv
0x18007d582  lea     rdx, ds:0[r13*2]; cb
0x18007d58a  call    cs:__imp_CoTaskMemRealloc
0x18007d591  nop     dword ptr [rax+rax+00h]
0x18007d596  mov     r12, rax
0x18007d599  test    rax, rax
0x18007d59c  jz      loc_18007D3F5
0x18007d5a2  mov     [rbp+4Fh+var_A0], r13
0x18007d5a6  mov     [rbp+4Fh+pv], rax
0x18007d5aa  jmp     short loc_18007D5F9
0x18007d5ac  mov     eax, 2
0x18007d5b1  mov     [rbp+4Fh+var_80], 0
0x18007d5b9  mul     r14
0x18007d5bc  test    rdx, rdx
0x18007d5bf  jnz     loc_18007D3F0
0x18007d5c5  mov     rcx, rax; cb
0x18007d5c8  call    cs:__imp_CoTaskMemAlloc
0x18007d5cf  nop     dword ptr [rax+rax+00h]
0x18007d5d4  mov     rcx, rax
0x18007d5d7  test    rax, rax
0x18007d5da  jz      short loc_18007D5F1
0x18007d5dc  xor     edi, edi
0x18007d5de  mov     [rbp+4Fh+pv], rax
0x18007d5e2  mov     r12, rax
0x18007d5e5  mov     [rbp+4Fh+var_A0], r14
0x18007d5e9  xor     eax, eax
0x18007d5eb  mov     r13, r14
0x18007d5ee  mov     [rcx], ax
0x18007d5f1  test    edi, edi
0x18007d5f3  js      loc_18007D3F5
0x18007d5f9  lea     rdx, [rbx+1]
0x18007d5fd  lea     r8, [r12+rsi*2]
  ... truncated ...
```
