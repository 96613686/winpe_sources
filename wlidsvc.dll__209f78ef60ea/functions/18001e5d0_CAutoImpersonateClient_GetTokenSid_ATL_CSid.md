# CAutoImpersonateClient::GetTokenSid(ATL::CSid &)

- ea: `0x18001e5d0`
- end: `0x18001eae2`
- name: `?GetTokenSid@CAutoImpersonateClient@@QEAAJAEAVCSid@ATL@@@Z`
- size: `1298`
- prototype: `int(CAutoImpersonateClient *__hidden this, struct ATL::CSid *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001dfec`
- `0x180021df0`
- `0x1800be590`

## callees

- `0x18000a354`
- `0x18001a9c0`
- `0x18001b760`
- `0x18001db3c`
- `0x18001e5d0`
- `0x1800204ac`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e672`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e859`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e8b6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e913`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e970`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e9cd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001ea2a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e672`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e859`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e8b6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e913`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e970`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001e9cd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001ea2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e77c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e77c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e76b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e703`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e71c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e71c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e746`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e746`

## string_xrefs

- `0x18001e668`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e84f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e8ac`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e909`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e966`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e9c3`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001ea20`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001e629`: `CAutoImpersonateClient::GetTokenSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAutoImpersonateClient::GetTokenSid(CAutoImpersonateClient *this, struct ATL::CSid *a2)
{
  const struct _SID **v4; // rdi
  const char *v5; // rbx
  char *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  int v10; // eax
  __int64 *v11; // rdx
  HANDLE CurrentThread; // rax
  char v13; // bl
  const unsigned __int16 *v14; // r8
  const struct _SID **v15; // rbx
  unsigned int v16; // ebx
  signed int LastError; // eax
  char *v19; // rax
  __int64 v20; // rax
  char *v21; // rax
  __int64 v22; // rax
  char *v23; // rax
  __int64 v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  char *v27; // rax
  __int64 v28; // rax
  char *v29; // rax
  __int64 v30; // rax
  int v31; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v32; // [rsp+38h] [rbp-A1h] BYREF
  DWORD TokenInformationLength; // [rsp+3Ch] [rbp-9Dh] BYREF
  const struct _SID **v34; // [rsp+40h] [rbp-99h] BYREF
  __int64 v35; // [rsp+48h] [rbp-91h]
  __int64 v36; // [rsp+50h] [rbp-89h]
  void *TokenHandle[3]; // [rsp+58h] [rbp-81h] BYREF
  _QWORD v38[4]; // [rsp+70h] [rbp-69h] BYREF
  _BYTE v39[16]; // [rsp+90h] [rbp-49h] BYREF
  const char *v40; // [rsp+A0h] [rbp-39h]
  int v41; // [rsp+A8h] [rbp-31h]
  int v42; // [rsp+ACh] [rbp-2Dh]
  const char *v43; // [rsp+B0h] [rbp-29h]
  __int64 v44; // [rsp+B8h] [rbp-21h]
  int *v45; // [rsp+C0h] [rbp-19h]
  __int64 v46; // [rsp+C8h] [rbp-11h]
  const wchar_t *v47; // [rsp+D0h] [rbp-9h]
  __int64 v48; // [rsp+D8h] [rbp-1h]

  memset(TokenHandle, 0, sizeof(TokenHandle));
  v32 = 0;
  TokenInformationLength = 0;
  v4 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  v38[0] = "CAutoImpersonateClient::GetTokenSid";
  v38[1] = &v32;
  v38[2] = 0;
  v38[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v6 = strrchr(
               "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
               dword_1801C3ABC - 4 + 92);
        if ( v6 )
          v5 = v6 + 1;
        v31 = 364;
        if ( v5 )
        {
          v9 = -1;
          do
            ++v9;
          while ( v5[v9] );
          v10 = v9 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = WlidSvc_TraceFunction_Enter;
LABEL_10:
        v41 = v10;
        v45 = &v31;
        v47 = L"NULL";
        v40 = v5;
        v42 = 0;
        v43 = "CAutoImpersonateClient::GetTokenSid";
        v44 = 36;
        v46 = 4;
        v48 = 10;
        McGenEventWrite_EventWriteTransfer(v7, v11, v8, 5, v39);
      }
      break;
    case 5:
      if ( byte_1801C36C5 >= 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v29 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v29 )
        v5 = v29 + 1;
      v31 = 364;
      if ( v5 )
      {
        v30 = -1;
        do
          ++v30;
        while ( v5[v30] );
        v10 = v30 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = WlidModern_TraceFunction_Enter;
      goto LABEL_10;
    case 6:
      if ( (byte_1801C36C7 & 8) == 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v27 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v27 )
        v5 = v27 + 1;
      v31 = 364;
      if ( v5 )
      {
        v28 = -1;
        do
          ++v28;
        while ( v5[v28] );
        v10 = v28 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = WlidCli_TraceFunction_Enter;
      goto LABEL_10;
    case 7:
      if ( (byte_1801C36C8 & 8) == 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v25 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v25 )
        v5 = v25 + 1;
      v31 = 364;
      if ( v5 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v5[v26] );
        v10 = v26 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = WlidProv_TraceFunction_Enter;
      goto LABEL_10;
    case 8:
      if ( (byte_1801C36C9 & 0x10) == 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v23 )
        v5 = v23 + 1;
      v31 = 364;
      if ( v5 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v5[v24] );
        v10 = v24 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = WlidBho_TraceFunction_Enter;
      goto LABEL_10;
    case 9:
      if ( (byte_1801C36CA & 0x10) == 0 )
        break;
      v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v21 )
        v5 = v21 + 1;
      v31 = 364;
      if ( v5 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v5[v22] );
        v10 = v22 + 1;
      }
      else
      {
        v5 = "NULL";
        v10 = 5;
      }
      v11 = TokenProvider_TraceFunction_Enter;
      goto LABEL_10;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v5 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v19 )
          v5 = v19 + 1;
        v31 = 364;
        if ( v5 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v5[v20] );
          v10 = v20 + 1;
        }
        else
        {
          v5 = "NULL";
          v10 = 5;
        }
        v11 = Extension_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
  }
  if ( !*(_DWORD *)this && !*((_DWORD *)this + 1) )
  {
    v16 = -2147024891;
LABEL_27:
    v32 = v16;
    goto LABEL_24;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
LABEL_25:
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_27;
  }
  v13 = 0;
  while ( !GetTokenInformation(TokenHandle[0], TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
  {
    if ( v13 || !TokenInformationLength )
      goto LABEL_25;
    v15 = (const struct _SID **)LocalAlloc(0x40u, TokenInformationLength);
    if ( v4 )
    {
      LocalFree(v4);
      v35 = 0;
    }
    v4 = v15;
    v34 = v15;
    if ( !v15 )
    {
      v16 = -2147024882;
      goto LABEL_27;
    }
    v13 = 1;
  }
  if ( !ATL::CSid::LoadAccount(a2, *v4, v14) )
    goto LABEL_25;
  v16 = v32;
LABEL_24:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v38);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v34);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(TokenHandle);
  return v16;
}

```

## disassembly

```asm
0x18001e5d0  push    rbp
0x18001e5d2  push    rbx
0x18001e5d3  push    rsi
0x18001e5d4  push    rdi
0x18001e5d5  push    r12
0x18001e5d7  push    r13
0x18001e5d9  push    r14
0x18001e5db  push    r15
0x18001e5dd  lea     rbp, [rsp-1Fh]
0x18001e5e2  sub     rsp, 0F8h
0x18001e5e9  mov     rax, cs:__security_cookie
0x18001e5f0  xor     rax, rsp
0x18001e5f3  mov     [rbp+57h+var_50], rax
0x18001e5f7  mov     r14, rdx
0x18001e5fa  mov     rsi, rcx
0x18001e5fd  xor     r15d, r15d
0x18001e600  mov     [rsp+130h+TokenHandle], r15
0x18001e605  mov     [rbp+57h+var_C8], r15
0x18001e609  mov     [rbp+57h+var_D0], r15
0x18001e60d  mov     [rsp+130h+var_F8], r15d
0x18001e612  mov     [rsp+130h+TokenInformationLength], r15d
0x18001e617  mov     edi, r15d
0x18001e61a  mov     [rsp+130h+var_F0], r15
0x18001e61f  mov     [rsp+130h+var_E0], r15
0x18001e624  mov     [rsp+130h+var_E8], r15
0x18001e629  lea     r13, aCautoimpersona_0; "CAutoImpersonateClient::GetTokenSid"
0x18001e630  mov     [rbp+57h+var_C0], r13
0x18001e634  lea     rax, [rsp+130h+var_F8]
0x18001e639  mov     [rbp+57h+var_B8], rax
0x18001e63d  mov     [rbp+57h+var_B0], r15
0x18001e641  mov     [rbp+57h+var_A8], r15
0x18001e645  mov     ecx, cs:dword_1801C3ABC
0x18001e64b  lea     r12d, [r15+4]
0x18001e64f  sub     ecx, r12d
0x18001e652  jnz     loc_18001E80D
0x18001e658  test    cs:byte_1801C36C4, r12b
0x18001e65f  jz      loc_18001E6F4
0x18001e665  lea     edx, [rcx+5Ch]; Ch
0x18001e668  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e66f  mov     rcx, rbx; Str
0x18001e672  call    cs:__imp_strrchr
0x18001e678  test    rax, rax
0x18001e67b  jz      short loc_18001E681
0x18001e67d  lea     rbx, [rax+1]
0x18001e681  mov     [rsp+130h+var_100], 16Ch
0x18001e689  mov     r9d, 5
0x18001e68f  test    rbx, rbx
0x18001e692  jz      loc_18001EABE
0x18001e698  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e69c  inc     rax
0x18001e69f  cmp     [rbx+rax], r15b
0x18001e6a3  jnz     short loc_18001E69C
0x18001e6a5  inc     eax
0x18001e6a7  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001e6ae  mov     [rbp+57h+var_88], eax
0x18001e6b1  lea     rax, [rsp+130h+var_100]
0x18001e6b6  mov     [rbp+57h+var_70], rax
0x18001e6ba  lea     rax, aNull_2; "NULL"
0x18001e6c1  mov     [rbp+57h+var_60], rax
0x18001e6c5  lea     rax, [rbp+57h+var_A0]
0x18001e6c9  mov     [rsp+130h+ReturnLength], rax
0x18001e6ce  mov     [rbp+57h+var_90], rbx
0x18001e6d2  mov     [rbp+57h+var_84], r15d
0x18001e6d6  mov     [rbp+57h+var_80], r13
0x18001e6da  mov     [rbp+57h+var_78], 24h ; '$'
0x18001e6e2  mov     [rbp+57h+var_68], r12
0x18001e6e6  mov     [rbp+57h+var_58], 0Ah
0x18001e6ee  call    McGenEventWrite_EventWriteTransfer
0x18001e6f3  nop
0x18001e6f4  cmp     [rsi], r15d
0x18001e6f7  jnz     short loc_18001E703
0x18001e6f9  cmp     [rsi+4], r15d
0x18001e6fd  jz      loc_18001EACD
0x18001e703  call    cs:__imp_GetCurrentThread
0x18001e709  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x18001e70e  mov     esi, 1
0x18001e713  mov     r8d, esi; OpenAsSelf
0x18001e716  lea     edx, [rsi+7]; DesiredAccess
0x18001e719  mov     rcx, rax; ThreadHandle
0x18001e71c  call    cs:__imp_OpenThreadToken
0x18001e722  test    eax, eax
0x18001e724  jz      loc_18001E7F1
0x18001e72a  mov     bl, r15b
0x18001e72d  lea     rax, [rsp+130h+TokenInformationLength]
0x18001e732  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18001e737  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x18001e73c  mov     r8, rdi; TokenInformation
0x18001e73f  mov     edx, esi; TokenInformationClass
0x18001e741  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x18001e746  call    cs:__imp_GetTokenInformation
0x18001e74c  test    eax, eax
0x18001e74e  jnz     short loc_18001E79D
0x18001e750  test    bl, bl
0x18001e752  jnz     loc_18001E7F1
0x18001e758  mov     eax, [rsp+130h+TokenInformationLength]
0x18001e75c  test    eax, eax
0x18001e75e  jz      loc_18001E7F1
0x18001e764  mov     edx, eax; uBytes
0x18001e766  mov     ecx, 40h ; '@'; uFlags
0x18001e76b  call    cs:__imp_LocalAlloc
0x18001e771  mov     rbx, rax
0x18001e774  test    rdi, rdi
0x18001e777  jz      short loc_18001E787
0x18001e779  mov     rcx, rdi; hMem
0x18001e77c  call    cs:__imp_LocalFree
0x18001e782  mov     [rsp+130h+var_E8], r15
0x18001e787  mov     rdi, rbx
0x18001e78a  mov     [rsp+130h+var_F0], rbx
0x18001e78f  test    rbx, rbx
0x18001e792  jz      loc_18001EAD7
0x18001e798  mov     bl, sil
0x18001e79b  jmp     short loc_18001E72D
0x18001e79d  mov     rdx, [rdi]; struct _SID *
0x18001e7a0  mov     rcx, r14; this
0x18001e7a3  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x18001e7a8  test    al, al
0x18001e7aa  jz      short loc_18001E7F1
0x18001e7ac  mov     ebx, [rsp+130h+var_F8]
0x18001e7b0  lea     rcx, [rbp+57h+var_C0]
0x18001e7b4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001e7b9  nop
0x18001e7ba  lea     rcx, [rsp+130h+var_F0]
0x18001e7bf  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18001e7c4  nop
0x18001e7c5  lea     rcx, [rsp+130h+TokenHandle]
0x18001e7ca  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x18001e7cf  mov     eax, ebx
0x18001e7d1  mov     rcx, [rbp+57h+var_50]
0x18001e7d5  xor     rcx, rsp; StackCookie
0x18001e7d8  call    __security_check_cookie
0x18001e7dd  add     rsp, 0F8h
0x18001e7e4  pop     r15
0x18001e7e6  pop     r14
0x18001e7e8  pop     r13
0x18001e7ea  pop     r12
0x18001e7ec  pop     rdi
0x18001e7ed  pop     rsi
0x18001e7ee  pop     rbx
0x18001e7ef  pop     rbp
0x18001e7f0  retn
0x18001e7f1  call    cs:__imp_GetLastError
0x18001e7f7  nop
0x18001e7f8  mov     ebx, eax
0x18001e7fa  test    eax, eax
0x18001e7fc  jle     short loc_18001E807
0x18001e7fe  movzx   ebx, ax
0x18001e801  or      ebx, 80070000h
0x18001e807  mov     [rsp+130h+var_F8], ebx
0x18001e80b  jmp     short loc_18001E7B0
0x18001e80d  sub     ecx, 1
0x18001e810  jz      loc_18001EA0E
0x18001e816  sub     ecx, 1
0x18001e819  jz      loc_18001E9B1
0x18001e81f  sub     ecx, 1
0x18001e822  jz      loc_18001E954
0x18001e828  sub     ecx, 1
0x18001e82b  jz      loc_18001E8F7
0x18001e831  sub     ecx, 1
0x18001e834  jz      short loc_18001E89A
0x18001e836  cmp     ecx, 1
0x18001e839  jnz     loc_18001E6F4
0x18001e83f  test    cs:byte_1801C36CB, 10h
0x18001e846  jz      loc_18001E6F4
0x18001e84c  lea     edx, [rcx+5Bh]; Ch
0x18001e84f  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e856  mov     rcx, rbx; Str
0x18001e859  call    cs:__imp_strrchr
0x18001e85f  test    rax, rax
0x18001e862  jz      short loc_18001E868
0x18001e864  lea     rbx, [rax+1]
0x18001e868  mov     [rsp+130h+var_100], 16Ch
0x18001e870  mov     r9d, 5
0x18001e876  test    rbx, rbx
0x18001e879  jz      loc_18001EA67
0x18001e87f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e883  inc     rax
0x18001e886  cmp     [rbx+rax], r15b
0x18001e88a  jnz     short loc_18001E883
0x18001e88c  inc     eax
0x18001e88e  lea     rdx, Extension_TraceFunction_Enter
0x18001e895  jmp     loc_18001E6AE
0x18001e89a  test    cs:byte_1801C36CA, 10h
0x18001e8a1  jz      loc_18001E6F4
0x18001e8a7  mov     edx, 5Ch ; '\'; Ch
0x18001e8ac  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e8b3  mov     rcx, rbx; Str
0x18001e8b6  call    cs:__imp_strrchr
0x18001e8bc  test    rax, rax
0x18001e8bf  jz      short loc_18001E8C5
0x18001e8c1  lea     rbx, [rax+1]
0x18001e8c5  mov     [rsp+130h+var_100], 16Ch
0x18001e8cd  mov     r9d, 5
0x18001e8d3  test    rbx, rbx
0x18001e8d6  jz      loc_18001EA76
0x18001e8dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e8e0  inc     rax
0x18001e8e3  cmp     [rbx+rax], r15b
0x18001e8e7  jnz     short loc_18001E8E0
0x18001e8e9  inc     eax
0x18001e8eb  lea     rdx, TokenProvider_TraceFunction_Enter
0x18001e8f2  jmp     loc_18001E6AE
0x18001e8f7  test    cs:byte_1801C36C9, 10h
0x18001e8fe  jz      loc_18001E6F4
0x18001e904  mov     edx, 5Ch ; '\'; Ch
0x18001e909  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e910  mov     rcx, rbx; Str
0x18001e913  call    cs:__imp_strrchr
0x18001e919  test    rax, rax
0x18001e91c  jz      short loc_18001E922
0x18001e91e  lea     rbx, [rax+1]
0x18001e922  mov     [rsp+130h+var_100], 16Ch
0x18001e92a  mov     r9d, 5
0x18001e930  test    rbx, rbx
0x18001e933  jz      loc_18001EA85
0x18001e939  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e93d  inc     rax
0x18001e940  cmp     [rbx+rax], r15b
0x18001e944  jnz     short loc_18001E93D
0x18001e946  inc     eax
0x18001e948  lea     rdx, WlidBho_TraceFunction_Enter
0x18001e94f  jmp     loc_18001E6AE
0x18001e954  test    cs:byte_1801C36C8, 8
0x18001e95b  jz      loc_18001E6F4
0x18001e961  mov     edx, 5Ch ; '\'; Ch
0x18001e966  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e96d  mov     rcx, rbx; Str
0x18001e970  call    cs:__imp_strrchr
0x18001e976  test    rax, rax
0x18001e979  jz      short loc_18001E97F
0x18001e97b  lea     rbx, [rax+1]
0x18001e97f  mov     [rsp+130h+var_100], 16Ch
0x18001e987  mov     r9d, 5
0x18001e98d  test    rbx, rbx
0x18001e990  jz      loc_18001EA94
0x18001e996  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e99a  inc     rax
0x18001e99d  cmp     [rbx+rax], r15b
0x18001e9a1  jnz     short loc_18001E99A
0x18001e9a3  inc     eax
0x18001e9a5  lea     rdx, WlidProv_TraceFunction_Enter
0x18001e9ac  jmp     loc_18001E6AE
0x18001e9b1  test    cs:byte_1801C36C7, 8
0x18001e9b8  jz      loc_18001E6F4
0x18001e9be  mov     edx, 5Ch ; '\'; Ch
0x18001e9c3  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001e9ca  mov     rcx, rbx; Str
0x18001e9cd  call    cs:__imp_strrchr
0x18001e9d3  test    rax, rax
0x18001e9d6  jz      short loc_18001E9DC
0x18001e9d8  lea     rbx, [rax+1]
0x18001e9dc  mov     [rsp+130h+var_100], 16Ch
0x18001e9e4  mov     r9d, 5
0x18001e9ea  test    rbx, rbx
0x18001e9ed  jz      loc_18001EAA3
0x18001e9f3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e9f7  inc     rax
0x18001e9fa  cmp     [rbx+rax], r15b
0x18001e9fe  jnz     short loc_18001E9F7
0x18001ea00  inc     eax
0x18001ea02  lea     rdx, WlidCli_TraceFunction_Enter
0x18001ea09  jmp     loc_18001E6AE
0x18001ea0e  cmp     cs:byte_1801C36C5, r15b
0x18001ea15  jge     loc_18001E6F4
0x18001ea1b  mov     edx, 5Ch ; '\'; Ch
0x18001ea20  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001ea27  mov     rcx, rbx; Str
0x18001ea2a  call    cs:__imp_strrchr
0x18001ea30  test    rax, rax
0x18001ea33  jz      short loc_18001EA39
0x18001ea35  lea     rbx, [rax+1]
0x18001ea39  mov     [rsp+130h+var_100], 16Ch
0x18001ea41  mov     r9d, 5
0x18001ea47  test    rbx, rbx
0x18001ea4a  jz      short loc_18001EAB2
0x18001ea4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ea50  inc     rax
0x18001ea53  cmp     [rbx+rax], r15b
0x18001ea57  jnz     short loc_18001EA50
0x18001ea59  inc     eax
0x18001ea5b  lea     rdx, WlidModern_TraceFunction_Enter
0x18001ea62  jmp     loc_18001E6AE
0x18001ea67  lea     rbx, aNull_0; "NULL"
0x18001ea6e  mov     eax, r9d
0x18001ea71  jmp     loc_18001E88E
0x18001ea76  lea     rbx, aNull_0; "NULL"
0x18001ea7d  mov     eax, r9d
0x18001ea80  jmp     loc_18001E8EB
0x18001ea85  lea     rbx, aNull_0; "NULL"
0x18001ea8c  mov     eax, r9d
0x18001ea8f  jmp     loc_18001E948
0x18001ea94  lea     rbx, aNull_0; "NULL"
0x18001ea9b  mov     eax, r9d
0x18001ea9e  jmp     loc_18001E9A5
0x18001eaa3  lea     rbx, aNull_0; "NULL"
0x18001eaaa  mov     eax, r9d
0x18001eaad  jmp     loc_18001EA02
0x18001eab2  lea     rbx, aNull_0; "NULL"
0x18001eab9  mov     eax, r9d
0x18001eabc  jmp     short loc_18001EA5B
0x18001eabe  lea     rbx, aNull_0; "NULL"
  ... truncated ...
```
