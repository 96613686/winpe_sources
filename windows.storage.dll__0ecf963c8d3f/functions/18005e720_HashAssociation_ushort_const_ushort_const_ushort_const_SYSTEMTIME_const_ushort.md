# HashAssociation(ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)

- ea: `0x18005e720`
- end: `0x18005f028`
- name: `?HashAssociation@@YAJPEBG00AEBU_SYSTEMTIME@@PEAPEAG@Z`
- size: `2312`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _SYSTEMTIME *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801fbeb0`
- `0x18038bddc`
- `0x1805774b4`
- `0x1805f7a48`

## callees

- `0x1800432f0`
- `0x18005e720`
- `0x18005f240`
- `0x18005f6c0`
- `0x180060a10`
- `0x180094c70`
- `0x18018c670`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18005edc3`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18005edc3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005ec09`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005ec09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005e879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005eb2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005ecea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005e879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005eb2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005ecea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e8b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ea35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005eb64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ed1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005e8b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ea35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005eb64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005ed1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ea12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ede9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ee1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ef4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ea12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ede9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ee1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005ef4a`

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
0x18005e720  push    rbp
0x18005e722  push    rbx
0x18005e723  push    rsi
0x18005e724  push    rdi
0x18005e725  push    r12
0x18005e727  push    r13
0x18005e729  push    r14
0x18005e72b  push    r15
0x18005e72d  lea     rbp, [rsp-17h]
0x18005e732  sub     rsp, 0A8h
0x18005e739  mov     rax, cs:__security_cookie
0x18005e740  xor     rax, rsp
0x18005e743  mov     [rbp+4Fh+var_48], rax
0x18005e747  mov     rax, [rbp+4Fh+arg_20]
0x18005e74b  xor     r12d, r12d
0x18005e74e  xor     r13d, r13d
0x18005e751  mov     [rbp+4Fh+lpSystemTime], r9
0x18005e755  xor     esi, esi
0x18005e757  mov     [rbp+4Fh+var_90], rax
0x18005e75b  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], r12
0x18005e75f  mov     r15, r8
0x18005e762  mov     qword ptr [rax], 0
0x18005e769  mov     rbx, rdx
0x18005e76c  mov     [rbp+4Fh+pv], r12
0x18005e770  mov     r14, rcx
0x18005e773  mov     [rbp+4Fh+var_A8], rsi
0x18005e777  mov     [rbp+4Fh+var_80], r13
0x18005e77b  mov     [rbp+4Fh+var_A0], r13
0x18005e77f  test    rdx, rdx
0x18005e782  jz      short loc_18005E7BE
0x18005e784  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18005e78b  nop     dword ptr [rax+rax+00h]
0x18005e790  inc     r13
0x18005e793  cmp     [rdx+r13*2], si
0x18005e798  jnz     short loc_18005E790
0x18005e79a  lea     rdi, [r13+1]
0x18005e79e  cmp     rdi, r13
0x18005e7a1  jnb     loc_18005EA1D
0x18005e7a7  mov     r8d, 80070216h
0x18005e7ad  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18005e7b1  test    r8d, r8d
0x18005e7b4  js      loc_18005EF2A
0x18005e7ba  mov     r13, [rbp+4Fh+var_80]
0x18005e7be  mov     edi, 8007000Eh
0x18005e7c3  mov     dword ptr [rbp+4Fh+var_88], edi
0x18005e7c6  test    r14, r14
0x18005e7c9  jz      loc_18005E951
0x18005e7cf  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18005e7d6  nop     word ptr [rax+rax+00000000h]
0x18005e7e0  inc     rbx
0x18005e7e3  cmp     word ptr [r14+rbx*2], 0
0x18005e7e9  jnz     short loc_18005E7E0
0x18005e7eb  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005e7ef  jnz     short loc_18005E80B
0x18005e7f1  test    r12, r12
0x18005e7f4  jz      loc_18005EFA5
0x18005e7fa  nop     word ptr [rax+rax+00h]
0x18005e800  inc     rsi
0x18005e803  cmp     word ptr [r12+rsi*2], 0
0x18005e809  jnz     short loc_18005E800
0x18005e80b  lea     rax, [rbx+rsi]
0x18005e80f  lea     rdi, [rax+1]
0x18005e813  cmp     rdi, rax
0x18005e816  jb      loc_18005E9E8
0x18005e81c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18005e820  jz      loc_18005EE86
0x18005e826  test    r13, r13
0x18005e829  jz      short loc_18005E895
0x18005e82b  cmp     rdi, r13
0x18005e82e  jbe     loc_18005E8EA
0x18005e834  mov     eax, 2
0x18005e839  mov     [rbp+4Fh+var_80], 0
0x18005e841  mul     r13
0x18005e844  mov     r8, rax
0x18005e847  test    rdx, rdx
0x18005e84a  jnz     loc_18005E9E8
0x18005e850  sub     rax, r13
0x18005e853  lea     rcx, [r13+800h]
0x18005e85a  cmp     rax, 800h
0x18005e860  mov     r13, rdi
0x18005e863  cmovbe  rcx, r8
0x18005e867  cmp     rdi, rcx
0x18005e86a  cmovbe  r13, rcx
0x18005e86e  mov     rcx, r12; pv
0x18005e871  lea     rdx, ds:0[r13*2]; cb
0x18005e879  call    cs:__imp_CoTaskMemRealloc
0x18005e87f  test    rax, rax
0x18005e882  jz      loc_18005EF6D
0x18005e888  mov     [rbp+4Fh+var_A0], r13
0x18005e88c  mov     r12, rax
0x18005e88f  mov     [rbp+4Fh+pv], rax
0x18005e893  jmp     short loc_18005E8EA
0x18005e895  mov     eax, 2
0x18005e89a  mov     [rbp+4Fh+var_80], 0
0x18005e8a2  mul     rdi
0x18005e8a5  test    rdx, rdx
0x18005e8a8  jnz     loc_18005E9E8
0x18005e8ae  mov     rcx, rax; cb
0x18005e8b1  call    cs:__imp_CoTaskMemAlloc
0x18005e8b7  mov     rcx, rax
0x18005e8ba  test    rax, rax
0x18005e8bd  jz      loc_18005EF58
0x18005e8c3  xor     r12d, r12d
0x18005e8c6  mov     [rbp+4Fh+var_A0], rdi
0x18005e8ca  mov     r13, rdi
0x18005e8cd  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], rax
0x18005e8d1  mov     rdi, rax
0x18005e8d4  mov     [rbp+4Fh+pv], rax
0x18005e8d8  xor     eax, eax
0x18005e8da  mov     [rcx], ax
0x18005e8dd  test    r12d, r12d
0x18005e8e0  js      loc_18005E9F2
0x18005e8e6  mov     r12, qword ptr [rbp+4Fh+FileTime.dwLowDateTime]
0x18005e8ea  lea     rdx, [rbx+1]
0x18005e8ee  lea     r8, [r12+rsi*2]
0x18005e8f2  test    rdx, rdx
0x18005e8f5  jz      short loc_18005E947
0x18005e8f7  cmp     rdx, 7FFFFFFFh
0x18005e8fe  ja      loc_18005EFD8
0x18005e904  cmp     rbx, 7FFFFFFEh
0x18005e90b  ja      loc_18005EFD8
0x18005e911  mov     rcx, rbx
0x18005e914  test    rcx, rcx
0x18005e917  jz      short loc_18005E937
0x18005e919  movzx   eax, word ptr [r14]
0x18005e91d  test    ax, ax
0x18005e920  jz      short loc_18005E937
0x18005e922  mov     [r8], ax
0x18005e926  add     r14, 2
0x18005e92a  add     r8, 2
0x18005e92e  dec     rcx
0x18005e931  sub     rdx, 1
0x18005e935  jnz     short loc_18005E914
0x18005e937  test    rdx, rdx
0x18005e93a  lea     rcx, [r8-2]
0x18005e93e  cmovnz  rcx, r8
0x18005e942  xor     eax, eax
0x18005e944  mov     [rcx], ax
0x18005e947  mov     edi, dword ptr [rbp+4Fh+var_88]
0x18005e94a  add     rsi, rbx
0x18005e94d  mov     [rbp+4Fh+var_A8], rsi
0x18005e951  test    r15, r15
0x18005e954  jz      loc_18005EBFA
0x18005e95a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18005e961  inc     rbx
0x18005e964  cmp     word ptr [r15+rbx*2], 0
0x18005e96a  jnz     short loc_18005E961
0x18005e96c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005e970  jnz     short loc_18005E98F
0x18005e972  test    r12, r12
0x18005e975  jz      loc_18005EFAC
0x18005e97b  nop     dword ptr [rax+rax+00h]
0x18005e980  inc     rsi
0x18005e983  cmp     word ptr [r12+rsi*2], 0
0x18005e989  jnz     short loc_18005E980
0x18005e98b  mov     [rbp+4Fh+var_A8], rsi
0x18005e98f  lea     rax, [rbx+rsi]
0x18005e993  lea     r14, [rax+1]
0x18005e997  cmp     r14, rax
0x18005e99a  jnb     loc_18005EACF
0x18005e9a0  mov     edi, 80070216h
0x18005e9a5  mov     rcx, [rbp+57h]; this
0x18005e9a9  lea     r8, aOnecoreShellLi_4; "onecore\\shell\\lib\\userchoicehelpers"...
0x18005e9b0  mov     r9d, edi; char *
0x18005e9b3  mov     edx, 0D2h; void *
0x18005e9b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e9bd  lea     rcx, [rbp+4Fh+pv]; void *
0x18005e9c1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005e9c6  mov     eax, edi
0x18005e9c8  mov     rcx, [rbp+4Fh+var_48]
0x18005e9cc  xor     rcx, rsp; StackCookie
0x18005e9cf  call    __security_check_cookie
0x18005e9d4  add     rsp, 0A8h
0x18005e9db  pop     r15
0x18005e9dd  pop     r14
0x18005e9df  pop     r13
0x18005e9e1  pop     r12
0x18005e9e3  pop     rdi
0x18005e9e4  pop     rsi
0x18005e9e5  pop     rbx
0x18005e9e6  pop     rbp
0x18005e9e7  retn
0x18005e9e8  mov     r12d, 80070216h
0x18005e9ee  mov     rdi, qword ptr [rbp+4Fh+FileTime.dwLowDateTime]
0x18005e9f2  mov     rcx, [rbp+57h]; this
0x18005e9f6  lea     r8, aOnecoreShellLi_4; "onecore\\shell\\lib\\userchoicehelpers"...
0x18005e9fd  mov     r9d, r12d; char *
0x18005ea00  mov     edx, 0D1h; void *
0x18005ea05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ea0a  test    rdi, rdi
0x18005ea0d  jz      short loc_18005EA18
0x18005ea0f  mov     rcx, rdi; pv
0x18005ea12  call    cs:__imp_CoTaskMemFree
0x18005ea18  mov     eax, r12d
0x18005ea1b  jmp     short loc_18005E9C8
0x18005ea1d  mov     eax, 2
0x18005ea22  mov     [rbp+4Fh+var_88], rsi
0x18005ea26  mul     rdi
0x18005ea29  test    rdx, rdx
0x18005ea2c  jnz     loc_18005E7A7
0x18005ea32  mov     rcx, rax; cb
0x18005ea35  call    cs:__imp_CoTaskMemAlloc
0x18005ea3b  mov     rcx, rax
0x18005ea3e  test    rax, rax
0x18005ea41  jz      loc_18005EF20
0x18005ea47  mov     rax, rdi
0x18005ea4a  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], rcx
0x18005ea4e  xor     r8d, r8d
0x18005ea51  mov     [rbp+4Fh+var_80], rax
0x18005ea55  mov     [rbp+4Fh+var_A0], rax
0x18005ea59  mov     r12, rcx
0x18005ea5c  xor     eax, eax
0x18005ea5e  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18005ea62  mov     [rbp+4Fh+pv], rcx
0x18005ea66  mov     [rcx], ax
0x18005ea69  test    rdi, rdi
0x18005ea6c  jz      loc_18005EFCF
0x18005ea72  cmp     rdi, 7FFFFFFFh
0x18005ea79  ja      short loc_18005EAC0
0x18005ea7b  mov     dword ptr [rbp+4Fh+var_88], r8d
0x18005ea7f  cmp     r13, 7FFFFFFEh
0x18005ea86  ja      loc_18005EFC7
0x18005ea8c  mov     rcx, r13
0x18005ea8f  mov     rdx, r12
0x18005ea92  test    rcx, rcx
0x18005ea95  jz      short loc_18005EAB3
0x18005ea97  movzx   eax, word ptr [rbx]
0x18005ea9a  test    ax, ax
0x18005ea9d  jz      short loc_18005EAB3
0x18005ea9f  mov     [rdx], ax
0x18005eaa2  add     rbx, 2
0x18005eaa6  add     rdx, 2
0x18005eaaa  dec     rcx
0x18005eaad  sub     rdi, 1
0x18005eab1  jnz     short loc_18005EA92
0x18005eab3  test    rdi, rdi
0x18005eab6  lea     rcx, [rdx-2]
0x18005eaba  cmovnz  rcx, rdx
0x18005eabe  xor     eax, eax
0x18005eac0  mov     [rcx], ax
0x18005eac3  mov     rsi, r13
0x18005eac6  mov     [rbp+4Fh+var_A8], r13
0x18005eaca  jmp     loc_18005E7B1
0x18005eacf  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18005ead3  jz      loc_18005EEB6
0x18005ead9  test    r13, r13
0x18005eadc  jz      short loc_18005EB48
0x18005eade  cmp     r14, r13
0x18005eae1  jbe     loc_18005EB8F
0x18005eae7  mov     eax, 2
0x18005eaec  mov     [rbp+4Fh+var_80], 0
0x18005eaf4  mul     r13
0x18005eaf7  mov     r8, rax
0x18005eafa  test    rdx, rdx
0x18005eafd  jnz     loc_18005E9A0
0x18005eb03  sub     rax, r13
0x18005eb06  lea     rcx, [r13+800h]
0x18005eb0d  cmp     rax, 800h
0x18005eb13  mov     r13, r14
0x18005eb16  cmovbe  rcx, r8
0x18005eb1a  cmp     r14, rcx
0x18005eb1d  cmovbe  r13, rcx
0x18005eb21  mov     rcx, r12; pv
0x18005eb24  lea     rdx, ds:0[r13*2]; cb
0x18005eb2c  call    cs:__imp_CoTaskMemRealloc
0x18005eb32  mov     r12, rax
0x18005eb35  test    rax, rax
0x18005eb38  jz      loc_18005E9A5
0x18005eb3e  mov     [rbp+4Fh+var_A0], r13
0x18005eb42  mov     [rbp+4Fh+pv], rax
0x18005eb46  jmp     short loc_18005EB8F
0x18005eb48  mov     eax, 2
0x18005eb4d  mov     [rbp+4Fh+var_80], 0
0x18005eb55  mul     r14
0x18005eb58  test    rdx, rdx
0x18005eb5b  jnz     loc_18005E9A0
0x18005eb61  mov     rcx, rax; cb
0x18005eb64  call    cs:__imp_CoTaskMemAlloc
0x18005eb6a  mov     rcx, rax
0x18005eb6d  test    rax, rax
0x18005eb70  jz      short loc_18005EB87
0x18005eb72  xor     edi, edi
0x18005eb74  mov     [rbp+4Fh+pv], rax
0x18005eb78  mov     r12, rax
0x18005eb7b  mov     [rbp+4Fh+var_A0], r14
0x18005eb7f  xor     eax, eax
0x18005eb81  mov     r13, r14
0x18005eb84  mov     [rcx], ax
0x18005eb87  test    edi, edi
0x18005eb89  js      loc_18005E9A5
0x18005eb8f  lea     rdx, [rbx+1]
0x18005eb93  lea     r8, [r12+rsi*2]
0x18005eb97  test    rdx, rdx
0x18005eb9a  jz      short loc_18005EBF3
0x18005eb9c  cmp     rdx, 7FFFFFFFh
0x18005eba3  ja      loc_18005EFE3
0x18005eba9  cmp     rbx, 7FFFFFFEh
0x18005ebb0  ja      loc_18005EFE3
0x18005ebb6  mov     rcx, rbx
0x18005ebb9  nop     dword ptr [rax+00000000h]
  ... truncated ...
```
