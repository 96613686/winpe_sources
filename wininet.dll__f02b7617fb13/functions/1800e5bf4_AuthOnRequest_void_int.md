# AuthOnRequest(void *,int)

- ea: `0x1800e5bf4`
- end: `0x1800e64e6`
- name: `?AuthOnRequest@@YAKPEAXH@Z`
- size: `2290`
- prototype: `unsigned int __fastcall(struct HTTP_REQUEST_HANDLE_OBJECT *, int)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008b070`

## callees

- `0x180019d20`
- `0x18003602c`
- `0x180037684`
- `0x18004b824`
- `0x1800b810c`
- `0x1800e5424`
- `0x1800e5bf4`
- `0x1800e64ec`
- `0x1800e66ec`
- `0x1800e676c`
- `0x1800e6838`
- `0x1800e685c`
- `0x1800e693c`
- `0x1800e6a08`
- `0x1800e6a88`
- `0x1800e6cc4`
- `0x1800e6d64`
- `0x1800e70b4`
- `0x1800e71c0`
- `0x18014a7a0`
- `0x18015762c`
- `0x180157ab4`
- `0x1801ccf34`
- `0x1801d4d04`
- `0x1801e285c`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6345`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5d3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5cf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5cf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e615b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e615b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e5dca`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e5e0a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e600b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e5dca`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e5e0a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800e600b`

## pseudocode

```c
__int64 __fastcall AuthOnRequest(struct HTTP_REQUEST_HANDLE_OBJECT *a1, unsigned int a2)
{
  const char **v4; // rax
  const CHAR *lpString2; // rsi
  const char *v6; // r14
  struct _INTERNET_CREDENTIALS *v7; // r13
  struct AUTHCTX **v9; // rdx
  struct AUTHCTX *v10; // rdx
  int v11; // r8d
  unsigned int v12; // r15d
  PWC *i; // rbx
  __int64 v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  char v18; // cl
  const CHAR *v19; // rsi
  unsigned __int16 v20; // dx
  int v21; // eax
  struct PWC *v22; // rax
  int v23; // r14d
  const char *v24; // rcx
  __int64 v25; // rcx
  unsigned __int16 *k; // rax
  const char *URL; // rax
  unsigned __int16 *v28; // r13
  unsigned __int16 *v29; // rsi
  __int64 v30; // r8
  unsigned __int16 *v31; // rax
  __int64 v32; // r8
  int v33; // ecx
  int v34; // edx
  unsigned __int16 *PassW; // rax
  unsigned __int16 *v36; // rcx
  int v37; // edx
  int v38; // r8d
  int v39; // r14d
  __int64 v40; // rcx
  __int64 v41; // rdx
  unsigned __int16 *j; // rcx
  struct AUTHCTX *AuthCtxFromPwc; // rax
  struct AUTHCTX *v44; // rsi
  int SchemeType; // eax
  int v46; // edx
  int v47; // r8d
  __int64 v48; // rcx
  char *v49; // rax
  char AuthState; // al
  char v51; // r8
  const char *v52; // r10
  int v53; // [rsp+50h] [rbp-68h]
  int v54; // [rsp+54h] [rbp-64h]
  unsigned __int16 *lpMem; // [rsp+58h] [rbp-60h]
  struct _INTERNET_CREDENTIALS *v56; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int16 *v57; // [rsp+68h] [rbp-50h] BYREF
  const CHAR *v58; // [rsp+70h] [rbp-48h] BYREF
  unsigned __int16 *v59; // [rsp+78h] [rbp-40h] BYREF
  unsigned __int16 v60; // [rsp+80h] [rbp-38h] BYREF

  if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
    WPP_SF_qD(1034, 18, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids, a1, a2);
  v4 = (const char **)((char *)a1 + 680);
  lpMem = 0;
  if ( !*((_QWORD *)a1 + 86) )
    v4 = (const char **)((char *)a1 + 672);
  lpString2 = 0;
  v6 = *v4;
  if ( *((_DWORD *)a1 + 216) )
    lpString2 = (const CHAR *)*((_QWORD *)a1 + 107);
  v58 = 0;
  v7 = 0;
  if ( a2 )
  {
    if ( !*((_DWORD *)a1 + 1288) || *((_DWORD *)a1 + 1287) )
      goto LABEL_9;
    v9 = (struct AUTHCTX **)((char *)a1 + 5224);
  }
  else
  {
    if ( (*((_DWORD *)a1 + 1319) & 0x6200) != 0 )
      goto LABEL_9;
    v9 = (struct AUTHCTX **)((char *)a1 + 5232);
  }
  v10 = *v9;
  if ( v10 )
  {
    ContinueAuthOnRequest(a1, v10, a2);
    goto LABEL_9;
  }
  v53 = 0;
  v54 = 1;
  EnterCriticalSection(&g_csAuth);
  if ( a2 )
  {
    v14 = -1;
    v60 = 0;
    LODWORD(v57) = -1;
    i = 0;
    v18 = xmmword_180266B60;
    if ( (xmmword_180266B60 & 2) != 0 )
    {
      WPP_SF_dsdqqq(
        (unsigned int)&v57,
        0,
        v11,
        *((_DWORD *)a1 + 1323),
        *((_QWORD *)a1 + 660),
        *((_WORD *)a1 + 2644),
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&v60);
      v18 = xmmword_180266B60;
    }
    v19 = (const CHAR *)*((_QWORD *)a1 + 660);
    v20 = *((_WORD *)a1 + 2644);
    v21 = *((_DWORD *)a1 + 1323);
    v58 = v19;
    v60 = v20;
    LODWORD(v57) = v21;
    if ( (v18 & 2) != 0 )
    {
      WPP_SF_(1025, 34, WPP_f57f0d52a59033179f5677a89e61f04c_Traceguids);
      v20 = v60;
      v19 = v58;
    }
    v22 = 0;
    if ( !v19 )
      goto LABEL_20;
    i = g_pwcProxy;
    v23 = v20;
    while ( i )
    {
      if ( CompareStringA(0x7Fu, 1u, *((PCNZCH *)i + 2), -1, v19, -1) == 2 && v23 == *((_DWORD *)i + 6) )
      {
        if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
          WPP_SF_s(1034, 44, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids, *((_QWORD *)i + 13));
        goto LABEL_54;
      }
      i = *(PWC **)i;
      v22 = 0;
    }
  }
  else
  {
    v12 = *((unsigned __int16 *)a1 + 466);
    for ( i = g_pwcRealm; i; i = *(PWC **)i )
    {
      if ( (!lpString2 || CompareStringA(0x7Fu, 1u, *((PCNZCH *)i + 2), -1, lpString2, -1) == 2)
        && v12 == *((_DWORD *)i + 6)
        && (!v6 || (unsigned int)TemplateMatch(*((const char **)i + 4), v6)) )
      {
        if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
          WPP_SF_s(1034, 44, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids, *((_QWORD *)i + 13));
LABEL_45:
        v14 = -1;
        goto LABEL_55;
      }
    }
    for ( i = g_pwcOther; ; i = *(PWC **)i )
    {
      if ( !i )
      {
        i = 0;
        v14 = -1;
        goto LABEL_20;
      }
      if ( (!lpString2 || CompareStringA(0x7Fu, 1u, *((PCNZCH *)i + 2), -1, lpString2, -1) == 2)
        && v12 == *((_DWORD *)i + 6)
        && (!v6 || (unsigned int)TemplateMatch(*((const char **)i + 4), v6)) )
      {
        break;
      }
    }
    if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
      WPP_SF_s(1034, 44, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids, *((_QWORD *)i + 13));
    v24 = (const char *)*((_QWORD *)i + 5);
    if ( !v24 )
      goto LABEL_45;
    v22 = AUTHCTX::SearchPwcList(g_pwcRealm, lpString2, v12, 0, v24, *((struct AUTHCTX::SPMData **)i + 1));
    v14 = -1;
  }
  i = v22;
LABEL_54:
  if ( i )
  {
LABEL_55:
    _InterlockedIncrement((volatile signed __int32 *)i + 24);
    if ( *((_DWORD *)a1 + 1432) && *(_DWORD *)(*((_QWORD *)i + 1) + 24LL) > 1u )
    {
      if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
        WPP_SF_(1034, 19, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids);
      LeaveCriticalSection(&g_csAuth);
      goto LABEL_107;
    }
    if ( !a2 && !*((_DWORD *)i + 21) )
      goto LABEL_20;
    v59 = 0;
    v57 = 0;
    v7 = 0;
    v56 = 0;
    if ( !(unsigned int)INTERNET_CONNECT_HANDLE_OBJECT::GetUserAndPassW(a1, a2, &v59, &v57) )
    {
      lpMem = v57;
      goto LABEL_20;
    }
    URL = INTERNET_CONNECT_HANDLE_OBJECT::GetURL(a1);
    v28 = v57;
    v29 = v59;
    lpMem = v57;
    PrepareInternetCredentials(i, URL, v59, v57, &v56);
    v30 = *((_QWORD *)i + 14);
    if ( !v30 )
      goto LABEL_112;
    v31 = v29;
    v32 = v30 - (_QWORD)v29;
    do
    {
      v33 = *(unsigned __int16 *)((char *)v31 + v32);
      v34 = *v31 - v33;
      if ( v34 )
        break;
      ++v31;
    }
    while ( v33 );
    if ( v34 )
    {
LABEL_112:
      v53 = 1;
    }
    else
    {
      PassW = PWC::GetPassW(i);
      if ( PassW )
      {
        v36 = PassW;
        do
        {
          v37 = *(unsigned __int16 *)((char *)v36 + (char *)v28 - (char *)PassW);
          v38 = *v36 - v37;
          if ( v38 )
            break;
          ++v36;
        }
        while ( v37 );
        if ( !v38 )
        {
          v39 = 0;
LABEL_89:
          v40 = -1;
          do
            ++v40;
          while ( PassW[v40] );
          v41 = 2 * v40;
          for ( j = PassW; v41; --v41 )
          {
            *(_BYTE *)j = 0;
            j = (unsigned __int16 *)((char *)j + 1);
          }
          HeapFree(g_hWxProcessHeap, 0, PassW);
          if ( !v39 )
            goto LABEL_94;
          goto LABEL_113;
        }
      }
      v39 = 1;
      v53 = 1;
      if ( PassW )
        goto LABEL_89;
    }
LABEL_113:
    PurgeKeepAlivesAndDuos(2u);
LABEL_94:
    PWC::SetUserW(i, v29);
    PWC::SetPassW(i, v28);
    v7 = v56;
    v54 = 0;
  }
LABEL_20:
  LeaveCriticalSection(&g_csAuth);
  if ( v7 )
    InternetIndicateStatusExtendedCallback(401 - (unsigned int)(a2 != 0), v7, 56, 0);
  if ( !a2 && !v53 )
  {
    v17 = *((_QWORD *)a1 + 150);
    if ( v17 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v17 + 112LL))(
             v17,
             v15,
             v16,
             0) )
      {
        if ( !i )
          goto LABEL_27;
LABEL_107:
        PWC::Dereference(i);
        goto LABEL_27;
      }
    }
  }
  if ( i )
  {
    if ( !a2 && !*((_DWORD *)i + 21) )
      goto LABEL_107;
    AuthCtxFromPwc = AUTHCTX::CreateAuthCtxFromPwc(a1, a2, i);
    v44 = AuthCtxFromPwc;
    if ( !AuthCtxFromPwc )
      goto LABEL_107;
    SchemeType = AUTHCTX::GetSchemeType(AuthCtxFromPwc);
    if ( SchemeType == v46 && v53 )
      v46 = v47;
    if ( a2 )
    {
      if ( (unsigned int)AUTHCTX::GetSchemeType(v44) != 1
        && (unsigned int)AUTHCTX::GetSchemeType(v44)
        && ((*((_DWORD *)a1 + 1319) & 0x10000) == 0 || (unsigned int)AUTHCTX::GetSchemeType(v44) != 2) )
      {
        goto LABEL_121;
      }
    }
    else if ( (*((_DWORD *)a1 + 1319) & 0x1000) != 0
           && ((unsigned int)AUTHCTX::GetSchemeType(v44) == 2 || (unsigned int)AUTHCTX::GetSchemeType(v44) == 4) )
    {
LABEL_121:
      (**(void (__fastcall ***)(struct AUTHCTX *, __int64))v44)(v44, 1);
      goto LABEL_107;
    }
    if ( v46 )
    {
      PopulateRequestCredentials(a1, v44);
      if ( v54 && (Microsoft_Windows_WinINetEnableBits & 0x4000) != 0 )
        McTemplateU0pq_EventWriteTransfer(v48, WININET_AUTH_USING_CACHED_CREDS, *((_QWORD *)a1 + 16), a2);
      v49 = (char *)a1 + 5224;
      if ( !a2 )
        v49 = (char *)a1 + 5232;
      *(_QWORD *)v49 = v44;
      HTTP_REQUEST_HANDLE_OBJECT::SetAuthState(a1, a2, 2u);
      AddAuthorizationHeader(a1, v44);
      goto LABEL_107;
    }
    goto LABEL_121;
  }
LABEL_27:
  if ( lpMem )
  {
    do
      ++v14;
    while ( lpMem[v14] );
    v25 = 2 * v14;
    for ( k = lpMem; v25; --v25 )
    {
      *(_BYTE *)k = 0;
      k = (unsigned __int16 *)((char *)k + 1);
    }
    HeapFree(g_hWxProcessHeap, 0, lpMem);
  }
  if ( v7 )
    FreePreparedCredentials(v7);
LABEL_9:
  if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
  {
    if ( *(_QWORD *)((char *)a1 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 5232) )
      AUTHCTX::GetSchemeType(*(_QWORD *)((char *)a1 + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 5232));
    AuthState = HTTP_REQUEST_HANDLE_OBJECT::GetAuthState(a1);
    v52 = "proxy";
    if ( !a2 )
      v52 = "server";
    WPP_SF_qsll(
      (unsigned int)"server",
      20,
      (unsigned int)WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids,
      (_DWORD)a1,
      (__int64)v52,
      AuthState,
      v51);
    if ( (BYTE1(xmmword_180266B60) & 4) != 0 )
      WPP_SF_(1034, 21, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e5bf4  mov     [rsp+arg_10], rbx
0x1800e5bf9  mov     [rsp+arg_18], rsi
0x1800e5bfe  push    rdi
0x1800e5bff  push    r12
0x1800e5c01  push    r13
0x1800e5c03  push    r14
0x1800e5c05  push    r15
0x1800e5c07  sub     rsp, 90h
0x1800e5c0e  mov     rax, cs:__security_cookie
0x1800e5c15  xor     rax, rsp
0x1800e5c18  mov     [rsp+0B8h+var_30], rax
0x1800e5c20  mov     r12d, edx
0x1800e5c23  mov     rdi, rcx
0x1800e5c26  test    byte ptr cs:xmmword_180266B60+1, 4
0x1800e5c2d  jnz     loc_1800E6256
0x1800e5c33  xor     r9d, r9d
0x1800e5c36  lea     rax, [rdi+2A8h]
0x1800e5c3d  mov     [rsp+0B8h+lpMem], r9
0x1800e5c42  cmp     [rdi+2B0h], r9
0x1800e5c49  jnz     short loc_1800E5C52
0x1800e5c4b  lea     rax, [rdi+2A0h]
0x1800e5c52  mov     rsi, r9
0x1800e5c55  mov     r14, [rax]
0x1800e5c58  cmp     [rdi+360h], r9d
0x1800e5c5f  jz      short loc_1800E5C68
0x1800e5c61  mov     rsi, [rdi+358h]
0x1800e5c68  mov     [rsp+0B8h+var_48], r9
0x1800e5c6d  mov     r13, r9
0x1800e5c70  test    r12d, r12d
0x1800e5c73  jz      short loc_1800E5CBE
0x1800e5c75  cmp     [rdi+1420h], r9d
0x1800e5c7c  jnz     loc_1800E5E27
0x1800e5c82  test    byte ptr cs:xmmword_180266B60+1, 4
0x1800e5c89  jnz     loc_1800E6442
0x1800e5c8f  xor     eax, eax
0x1800e5c91  mov     rcx, [rsp+0B8h+var_30]
0x1800e5c99  xor     rcx, rsp; StackCookie
0x1800e5c9c  call    __security_check_cookie
0x1800e5ca1  lea     r11, [rsp+0B8h+var_28]
0x1800e5ca9  mov     rbx, [r11+40h]
0x1800e5cad  mov     rsi, [r11+48h]
0x1800e5cb1  mov     rsp, r11
0x1800e5cb4  pop     r15
0x1800e5cb6  pop     r14
0x1800e5cb8  pop     r13
0x1800e5cba  pop     r12
0x1800e5cbc  pop     rdi
0x1800e5cbd  retn
0x1800e5cbe  test    dword ptr [rdi+149Ch], 6200h
0x1800e5cc8  jnz     short loc_1800E5C82
0x1800e5cca  lea     rdx, [rdi+1470h]
0x1800e5cd1  mov     rdx, [rdx]; struct AUTHCTX *
0x1800e5cd4  test    rdx, rdx
0x1800e5cd7  jnz     loc_1800E5FDA
0x1800e5cdd  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x1800e5ce4  mov     [rsp+0B8h+var_68], r9d
0x1800e5ce9  mov     [rsp+0B8h+var_64], 1
0x1800e5cf1  call    cs:__imp_EnterCriticalSection
0x1800e5cf7  xor     edx, edx
0x1800e5cf9  test    r12d, r12d
0x1800e5cfc  jnz     loc_1800E5E74
0x1800e5d02  movzx   r15d, word ptr [rdi+3A4h]
0x1800e5d0a  mov     rbx, cs:?g_pwcRealm@@3PEAVPWC@@EA; PWC * g_pwcRealm
0x1800e5d11  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e5d15  test    rbx, rbx
0x1800e5d18  jnz     loc_1800E5DA9
0x1800e5d1e  mov     rbx, cs:?g_pwcOther@@3PEAVPWC@@EA; PWC * g_pwcOther
0x1800e5d25  test    rbx, rbx
0x1800e5d28  jnz     loc_1800E5DE9
0x1800e5d2e  mov     rbx, rdx
0x1800e5d31  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800e5d35  lea     rcx, ?g_csAuth@@3VWxCriticalSection@@A; lpCriticalSection
0x1800e5d3c  call    cs:__imp_LeaveCriticalSection
0x1800e5d42  xor     r9d, r9d
0x1800e5d45  test    r13, r13
0x1800e5d48  jnz     loc_1800E6367
0x1800e5d4e  mov     r14d, [rsp+0B8h+var_68]
0x1800e5d53  test    r12d, r12d
0x1800e5d56  jnz     short loc_1800E5D7C
0x1800e5d58  test    r14d, r14d
0x1800e5d5b  jnz     short loc_1800E5D7C
0x1800e5d5d  mov     rcx, [rdi+4B0h]
0x1800e5d64  test    rcx, rcx
0x1800e5d67  jz      short loc_1800E5D7C
0x1800e5d69  mov     rax, [rcx]
0x1800e5d6c  mov     rax, [rax+70h]
0x1800e5d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5d75  xor     r9d, r9d
0x1800e5d78  test    eax, eax
0x1800e5d7a  jnz     short loc_1800E5DDF
0x1800e5d7c  test    rbx, rbx
0x1800e5d7f  jnz     loc_1800E61A7
0x1800e5d85  mov     rdx, [rsp+0B8h+lpMem]
0x1800e5d8a  test    rdx, rdx
0x1800e5d8d  jnz     loc_1800E6052
0x1800e5d93  test    r13, r13
0x1800e5d96  jz      loc_1800E5C82
0x1800e5d9c  mov     rcx, r13; struct _INTERNET_CREDENTIALS *
0x1800e5d9f  call    ?FreePreparedCredentials@@YAXPEAU_INTERNET_CREDENTIALS@@@Z; FreePreparedCredentials(_INTERNET_CREDENTIALS *)
0x1800e5da4  jmp     loc_1800E5FE5
0x1800e5da9  test    rsi, rsi
0x1800e5dac  jz      loc_1800E5E40
0x1800e5db2  mov     r8, [rbx+10h]; lpString1
0x1800e5db6  mov     edx, 1; dwCmpFlags
0x1800e5dbb  mov     [rsp+0B8h+cchCount2], eax; cchCount2
0x1800e5dbf  mov     r9d, eax; cchCount1
0x1800e5dc2  mov     [rsp+0B8h+lpString2], rsi; lpString2
0x1800e5dc7  lea     ecx, [rdx+7Eh]; Locale
0x1800e5dca  call    cs:__imp_CompareStringA
0x1800e5dd0  xor     edx, edx
0x1800e5dd2  cmp     eax, 2
0x1800e5dd5  jz      short loc_1800E5E40
0x1800e5dd7  mov     rbx, [rbx]
0x1800e5dda  jmp     loc_1800E5D11
0x1800e5ddf  test    rbx, rbx
0x1800e5de2  jz      short loc_1800E5D85
0x1800e5de4  jmp     loc_1800E6246
0x1800e5de9  test    rsi, rsi
0x1800e5dec  jz      loc_1800E5F49
0x1800e5df2  mov     r8, [rbx+10h]; lpString1
0x1800e5df6  mov     edx, 1; dwCmpFlags
0x1800e5dfb  mov     [rsp+0B8h+cchCount2], eax; cchCount2
0x1800e5dff  mov     r9d, eax; cchCount1
0x1800e5e02  mov     [rsp+0B8h+lpString2], rsi; lpString2
0x1800e5e07  lea     ecx, [rdx+7Eh]; Locale
0x1800e5e0a  call    cs:__imp_CompareStringA
0x1800e5e10  xor     edx, edx
0x1800e5e12  cmp     eax, 2
0x1800e5e15  jz      loc_1800E5F49
0x1800e5e1b  mov     rbx, [rbx]
0x1800e5e1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e5e22  jmp     loc_1800E5D25
0x1800e5e27  cmp     [rdi+141Ch], r9d
0x1800e5e2e  jnz     loc_1800E5C82
0x1800e5e34  lea     rdx, [rdi+1468h]
0x1800e5e3b  jmp     loc_1800E5CD1
0x1800e5e40  cmp     r15d, [rbx+18h]
0x1800e5e44  jnz     short loc_1800E5DD7
0x1800e5e46  test    r14, r14
0x1800e5e49  jz      short loc_1800E5E61
0x1800e5e4b  mov     rcx, [rbx+20h]; char *
0x1800e5e4f  mov     rdx, r14; char *
0x1800e5e52  call    ?TemplateMatch@@YAHPEBD0@Z; TemplateMatch(char const *,char const *)
0x1800e5e57  xor     edx, edx
0x1800e5e59  test    eax, eax
0x1800e5e5b  jz      loc_1800E5DD7
0x1800e5e61  test    byte ptr cs:xmmword_180266B60+1, 4
0x1800e5e68  jnz     loc_1800E62F0
0x1800e5e6e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800e5e72  jmp     short loc_1800E5EF2
0x1800e5e74  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800e5e78  mov     [rsp+0B8h+var_38], dx
0x1800e5e80  mov     dword ptr [rsp+0B8h+var_50], r15d
0x1800e5e85  mov     rbx, rdx
0x1800e5e88  mov     cl, byte ptr cs:xmmword_180266B60
0x1800e5e8e  test    cl, 2
0x1800e5e91  jnz     loc_1800E6279
0x1800e5e97  mov     rsi, [rdi+14A0h]
0x1800e5e9e  movzx   edx, word ptr [rdi+14A8h]
0x1800e5ea5  mov     eax, [rdi+14ACh]
0x1800e5eab  mov     [rsp+0B8h+var_48], rsi
0x1800e5eb0  mov     [rsp+0B8h+var_38], dx
0x1800e5eb8  mov     dword ptr [rsp+0B8h+var_50], eax
0x1800e5ebc  test    cl, 2
0x1800e5ebf  jnz     loc_1800E62C8
0x1800e5ec5  xor     eax, eax
0x1800e5ec7  test    rsi, rsi
0x1800e5eca  jz      loc_1800E5D35
0x1800e5ed0  mov     rbx, cs:?g_pwcProxy@@3PEAVPWC@@EA; PWC * g_pwcProxy
0x1800e5ed7  movzx   r14d, dx
0x1800e5edb  test    rbx, rbx
0x1800e5ede  jnz     loc_1800E5FED
0x1800e5ee4  mov     rbx, rax
0x1800e5ee7  xor     edx, edx
0x1800e5ee9  test    rbx, rbx
0x1800e5eec  jz      loc_1800E5D35
0x1800e5ef2  lock inc dword ptr [rbx+60h]
0x1800e5ef6  cmp     [rdi+1660h], edx
0x1800e5efc  jnz     loc_1800E6311
0x1800e5f02  test    r12d, r12d
0x1800e5f05  jz      loc_1800E5FCC
0x1800e5f0b  mov     [rsp+0B8h+var_40], rdx
0x1800e5f10  lea     r9, [rsp+0B8h+var_50]; unsigned __int16 **
0x1800e5f15  mov     [rsp+0B8h+var_50], rdx
0x1800e5f1a  lea     r8, [rsp+0B8h+var_40]; unsigned __int16 **
0x1800e5f1f  mov     r13, rdx
0x1800e5f22  mov     [rsp+0B8h+var_58], rdx
0x1800e5f27  mov     edx, r12d; int
0x1800e5f2a  mov     rcx, rdi; this
0x1800e5f2d  call    ?GetUserAndPassW@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAHHPEAPEAG0@Z; INTERNET_CONNECT_HANDLE_OBJECT::GetUserAndPassW(int,ushort * *,ushort * *)
0x1800e5f32  test    eax, eax
0x1800e5f34  jnz     loc_1800E608E
0x1800e5f3a  mov     rax, [rsp+0B8h+var_50]
0x1800e5f3f  mov     [rsp+0B8h+lpMem], rax
0x1800e5f44  jmp     loc_1800E5D35
0x1800e5f49  cmp     r15d, [rbx+18h]
0x1800e5f4d  jnz     loc_1800E5E1B
0x1800e5f53  test    r14, r14
0x1800e5f56  jz      short loc_1800E5F6E
0x1800e5f58  mov     rcx, [rbx+20h]; char *
0x1800e5f5c  mov     rdx, r14; char *
0x1800e5f5f  call    ?TemplateMatch@@YAHPEBD0@Z; TemplateMatch(char const *,char const *)
0x1800e5f64  xor     edx, edx
0x1800e5f66  test    eax, eax
0x1800e5f68  jz      loc_1800E5E1B
0x1800e5f6e  test    byte ptr cs:xmmword_180266B60+1, 4
0x1800e5f75  jz      short loc_1800E5F93
0x1800e5f77  mov     r9, [rbx+68h]
0x1800e5f7b  lea     r8, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids
0x1800e5f82  mov     edx, 2Ch ; ','
0x1800e5f87  mov     ecx, 40Ah
0x1800e5f8c  call    WPP_SF_s
0x1800e5f91  xor     edx, edx
0x1800e5f93  mov     rcx, [rbx+28h]
0x1800e5f97  test    rcx, rcx
0x1800e5f9a  jz      loc_1800E5E6E
0x1800e5fa0  mov     rax, [rbx+8]
0x1800e5fa4  xor     r9d, r9d; char *
0x1800e5fa7  mov     qword ptr [rsp+0B8h+cchCount2], rax; struct AUTHCTX::SPMData *
0x1800e5fac  mov     r8d, r15d; unsigned int
0x1800e5faf  mov     [rsp+0B8h+lpString2], rcx; char *
0x1800e5fb4  mov     rdx, rsi; char *
0x1800e5fb7  mov     rcx, cs:?g_pwcRealm@@3PEAVPWC@@EA; struct PWC *
0x1800e5fbe  call    ?SearchPwcList@AUTHCTX@@SAPEAVPWC@@PEAV2@PEBDK11PEAVSPMData@1@@Z; AUTHCTX::SearchPwcList(PWC *,char const *,ulong,char const *,char const *,AUTHCTX::SPMData *)
0x1800e5fc3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800e5fc7  jmp     loc_1800E5EE4
0x1800e5fcc  cmp     [rbx+54h], edx
0x1800e5fcf  jnz     loc_1800E5F0B
0x1800e5fd5  jmp     loc_1800E5D35
0x1800e5fda  mov     r8d, r12d; int
0x1800e5fdd  mov     rcx, rdi; struct HTTP_REQUEST_HANDLE_OBJECT *
0x1800e5fe0  call    ?ContinueAuthOnRequest@@YAXPEAVHTTP_REQUEST_HANDLE_OBJECT@@PEAVAUTHCTX@@H@Z; ContinueAuthOnRequest(HTTP_REQUEST_HANDLE_OBJECT *,AUTHCTX *,int)
0x1800e5fe5  xor     r9d, r9d
0x1800e5fe8  jmp     loc_1800E5C82
0x1800e5fed  test    rsi, rsi
0x1800e5ff0  jz      short loc_1800E6020
0x1800e5ff2  mov     r8, [rbx+10h]; lpString1
0x1800e5ff6  mov     edx, 1; dwCmpFlags
0x1800e5ffb  mov     [rsp+0B8h+cchCount2], r15d; cchCount2
0x1800e6000  mov     r9d, r15d; cchCount1
0x1800e6003  mov     [rsp+0B8h+lpString2], rsi; lpString2
0x1800e6008  lea     ecx, [rdx+7Eh]; Locale
0x1800e600b  call    cs:__imp_CompareStringA
0x1800e6011  cmp     eax, 2
0x1800e6014  jz      short loc_1800E6020
0x1800e6016  mov     rbx, [rbx]
0x1800e6019  xor     eax, eax
0x1800e601b  jmp     loc_1800E5EDB
0x1800e6020  cmp     r14d, [rbx+18h]
0x1800e6024  jnz     short loc_1800E6016
0x1800e6026  test    byte ptr cs:xmmword_180266B60+1, 4
0x1800e602d  jz      loc_1800E5EE7
0x1800e6033  mov     r9, [rbx+68h]
0x1800e6037  lea     r8, WPP_238eb0d6eeb4389ab911b3c40e414073_Traceguids
0x1800e603e  mov     edx, 2Ch ; ','
0x1800e6043  mov     ecx, 40Ah
0x1800e6048  call    WPP_SF_s
0x1800e604d  jmp     loc_1800E5EE7
0x1800e6052  inc     r15
0x1800e6055  cmp     [rdx+r15*2], r9w
0x1800e605a  jnz     short loc_1800E6052
0x1800e605c  lea     rcx, [r15+r15]
0x1800e6060  mov     rax, rdx
0x1800e6063  test    rcx, rcx
0x1800e6066  jz      short loc_1800E6074
0x1800e6068  mov     [rax], r9b
0x1800e606b  inc     rax
0x1800e606e  sub     rcx, 1
0x1800e6072  jnz     short loc_1800E6068
0x1800e6074  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800e607b  mov     r8, rdx; lpMem
0x1800e607e  xor     edx, edx; dwFlags
0x1800e6080  call    cs:__imp_HeapFree
0x1800e6086  xor     r9d, r9d
0x1800e6089  jmp     loc_1800E5D93
0x1800e608e  mov     rcx, rdi; this
0x1800e6091  call    ?GetURL@INTERNET_CONNECT_HANDLE_OBJECT@@QEAAPEADXZ; INTERNET_CONNECT_HANDLE_OBJECT::GetURL(void)
0x1800e6096  mov     r13, [rsp+0B8h+var_50]
0x1800e609b  mov     rdx, rax; char *
0x1800e609e  mov     rsi, [rsp+0B8h+var_40]
0x1800e60a3  lea     rax, [rsp+0B8h+var_58]
0x1800e60a8  mov     r9, r13; unsigned __int16 *
0x1800e60ab  mov     [rsp+0B8h+lpString2], rax; struct _INTERNET_CREDENTIALS **
0x1800e60b0  mov     r8, rsi; unsigned __int16 *
0x1800e60b3  mov     [rsp+0B8h+lpMem], r13
0x1800e60b8  mov     rcx, rbx; struct PWC *
0x1800e60bb  call    ?PrepareInternetCredentials@@YAXPEAVPWC@@PEBDPEBG2PEAPEAU_INTERNET_CREDENTIALS@@@Z; PrepareInternetCredentials(PWC *,char const *,ushort const *,ushort const *,_INTERNET_CREDENTIALS * *)
0x1800e60c0  mov     r8, [rbx+70h]
0x1800e60c4  test    r8, r8
0x1800e60c7  jz      loc_1800E6350
0x1800e60cd  mov     rax, rsi
0x1800e60d0  sub     r8, rsi
0x1800e60d3  movzx   edx, word ptr [rax]
0x1800e60d6  movzx   ecx, word ptr [rax+r8]
0x1800e60db  sub     edx, ecx
0x1800e60dd  jnz     short loc_1800E60E7
0x1800e60df  add     rax, 2
0x1800e60e3  test    ecx, ecx
0x1800e60e5  jnz     short loc_1800E60D3
0x1800e60e7  test    edx, edx
  ... truncated ...
```
