# CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)

- ea: `0x18001f968`
- end: `0x18001ff3b`
- name: `?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z`
- size: `1491`
- prototype: `__int64 __fastcall(CAutoImpersonateClient *__hidden this, struct ATL::CAccessToken *)`
- caller_count: `86`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010290`
- `0x18001f190`
- `0x1800216f8`
- `0x180021df0`
- `0x18002a57c`
- `0x18003100c`
- `0x18003b550`
- `0x18003e73c`
- `0x180040084`
- `0x180044a10`
- `0x18004a4b8`
- `0x18004d77c`
- `0x18004e874`
- `0x180052a40`
- `0x1800563d0`
- `0x18005ddb0`
- `0x180062a4c`
- `0x180067f4c`
- `0x18006ccc8`
- `0x18007b260`
- `0x180081648`
- `0x1800834d8`
- `0x18008a794`
- `0x18008be88`
- `0x18008c938`
- `0x18008cf4c`
- `0x18008e0b0`
- `0x18008e3ac`
- `0x18008e644`
- `0x18008f2cc`
- `0x18008fb60`
- `0x180090afc`
- `0x18009132c`
- `0x180091e98`
- `0x1800921bc`
- `0x1800927b0`
- `0x180092c78`
- `0x1800931e4`
- `0x18009362c`
- `0x180093e30`
- `0x180094f84`
- `0x1800957f4`
- `0x180095b34`
- `0x180095f9c`
- `0x180096d84`
- `0x180096ff0`
- `0x180098310`
- `0x1800989a8`
- `0x1800990c0`
- `0x18009939c`

## callees

- `0x18001a9c0`
- `0x18001b760`
- `0x18001f968`
- `0x18001ff44`
- `0x1800204ac`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f9f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fc1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fcba`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fd17`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fd74`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fdd1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fe2e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f9f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fc1b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fcba`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fd17`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fd74`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fdd1`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001fe2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fefc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fefc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fa74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001face`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001fa74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001face`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fb63`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fb63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fa92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fae1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fa92`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001fae1`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18001fb57`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18001fb57`
- `RPCRT4!RpcRevertToSelf` at `0x18001faef`
- `RPCRT4!RpcRevertToSelf` at `0x18001fe85`
- `RPCRT4!RpcRevertToSelf` at `0x18001faef`
- `RPCRT4!RpcRevertToSelf` at `0x18001fe85`
- `RPCRT4!RpcImpersonateClient` at `0x18001fabe`
- `RPCRT4!RpcImpersonateClient` at `0x18001fabe`

## string_xrefs

- `0x18001f9e9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fc11`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fcb0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fd08`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fd65`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fdc2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001fe1f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001f997`: `CAutoImpersonateClient::ImpersonateClient`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CAutoImpersonateClient::ImpersonateClient(
        CAutoImpersonateClient *this,
        struct ATL::CAccessToken *a2)
{
  const char *v4; // rbx
  char *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // eax
  __int64 *v10; // rdx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  bool v13; // cc
  HANDLE v14; // rax
  void *v15; // rcx
  void *v16; // rcx
  unsigned int v17; // ebx
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
  signed int v31; // eax
  int v32; // [rsp+30h] [rbp-89h] BYREF
  int UserTokenFromAppContainerContext; // [rsp+38h] [rbp-81h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+48h] [rbp-71h] BYREF
  void *v36; // [rsp+50h] [rbp-69h] BYREF
  __int64 v37; // [rsp+58h] [rbp-61h]
  __int64 v38; // [rsp+60h] [rbp-59h]
  _QWORD v39[5]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v40[16]; // [rsp+90h] [rbp-29h] BYREF
  const char *v41; // [rsp+A0h] [rbp-19h]
  int v42; // [rsp+A8h] [rbp-11h]
  int v43; // [rsp+ACh] [rbp-Dh]
  const char *v44; // [rsp+B0h] [rbp-9h]
  __int64 v45; // [rsp+B8h] [rbp-1h]
  int *v46; // [rsp+C0h] [rbp+7h]
  __int64 v47; // [rsp+C8h] [rbp+Fh]
  const wchar_t *v48; // [rsp+D0h] [rbp+17h]
  __int64 v49; // [rsp+D8h] [rbp+1Fh]

  TokenHandle = 0;
  UserTokenFromAppContainerContext = 0;
  TokenInformation = 0;
  v39[0] = "CAutoImpersonateClient::ImpersonateClient";
  v39[1] = &UserTokenFromAppContainerContext;
  v39[2] = 0;
  v39[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) == 0 )
        break;
      v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v5 = strrchr(
             "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
             dword_1801C3ABC - 4 + 92);
      if ( v5 )
        v4 = v5 + 1;
      v32 = 151;
      if ( v4 )
      {
        v8 = -1;
        do
          ++v8;
        while ( v4[v8] );
        v9 = v8 + 1;
      }
      else
      {
        v4 = "NULL";
        v9 = 5;
      }
      v10 = WlidSvc_TraceFunction_Enter;
      goto LABEL_10;
    case 5:
      if ( byte_1801C36C5 < 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v29 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v29 )
          v4 = v29 + 1;
        v32 = 151;
        if ( v4 )
        {
          v30 = -1;
          do
            ++v30;
          while ( v4[v30] );
          v9 = v30 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = WlidModern_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 6:
      if ( (byte_1801C36C7 & 8) != 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v27 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v27 )
          v4 = v27 + 1;
        v32 = 151;
        if ( v4 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v4[v28] );
          v9 = v28 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = WlidCli_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 7:
      if ( (byte_1801C36C8 & 8) != 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v25 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v25 )
          v4 = v25 + 1;
        v32 = 151;
        if ( v4 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v4[v26] );
          v9 = v26 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = WlidProv_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 8:
      if ( (byte_1801C36C9 & 0x10) != 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v23 )
          v4 = v23 + 1;
        v32 = 151;
        if ( v4 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v4[v24] );
          v9 = v24 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = WlidBho_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 9:
      if ( (byte_1801C36CA & 0x10) != 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v19 )
          v4 = v19 + 1;
        v32 = 151;
        if ( v4 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v4[v20] );
          v9 = v20 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = TokenProvider_TraceFunction_Enter;
LABEL_10:
        v42 = v9;
        v46 = &v32;
        v48 = L"NULL";
        v41 = v4;
        v43 = 0;
        v44 = "CAutoImpersonateClient::ImpersonateClient";
        v45 = 42;
        v47 = 4;
        v49 = 10;
        McGenEventWrite_EventWriteTransfer(v6, v10, v7, 5, v40);
      }
      break;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v4 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v21 )
          v4 = v21 + 1;
        v32 = 151;
        if ( v4 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v4[v22] );
          v9 = v22 + 1;
        }
        else
        {
          v4 = "NULL";
          v9 = 5;
        }
        v10 = Extension_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    *((_DWORD *)this + 1) = 1;
    goto LABEL_23;
  }
  if ( GetLastError() == 1008 )
  {
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      UserTokenFromAppContainerContext = -2147418113;
      goto LABEL_23;
    }
    LastError = RpcImpersonateClient(0);
    v13 = LastError <= 0;
    if ( LastError )
    {
LABEL_45:
      if ( !v13 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      UserTokenFromAppContainerContext = LastError;
      goto LABEL_23;
    }
    *(_DWORD *)this = 1;
    v14 = GetCurrentThread();
    if ( OpenThreadToken(v14, 0xF01FFu, 1, &TokenHandle) )
    {
      LastError = RpcRevertToSelf();
      v13 = LastError <= 0;
      if ( !LastError )
      {
        v15 = TokenHandle;
        *(_DWORD *)this = 0;
        v32 = 0;
        v36 = 0;
        v38 = 0;
        v37 = 0;
        UserTokenFromAppContainerContext = GetUserTokenFromAppContainerContext(v15, &v36, &v32);
        if ( UserTokenFromAppContainerContext < 0 )
        {
          Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(&v36);
          goto LABEL_23;
        }
        if ( v32 )
        {
          CloseHandle(TokenHandle);
          TokenHandle = v36;
          v36 = 0;
          v37 = 0;
        }
        Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(&v36);
        TokenInformation = 0;
        SetTokenInformation(TokenHandle, TokenMandatoryPolicy, &TokenInformation, 4u);
        if ( SetThreadToken(0, TokenHandle) )
        {
          *(_DWORD *)this = 1;
          goto LABEL_23;
        }
        LastError = GetLastError();
        v13 = LastError <= 0;
      }
      goto LABEL_45;
    }
    v31 = GetLastError();
    if ( v31 > 0 )
      v31 = (unsigned __int16)v31 | 0x80070000;
    UserTokenFromAppContainerContext = v31;
    RpcRevertToSelf();
    *(_DWORD *)this = 0;
  }
LABEL_23:
  if ( a2 && UserTokenFromAppContainerContext >= 0 )
  {
    if ( !TokenHandle )
      goto LABEL_27;
    v16 = 0;
    *((_QWORD *)a2 + 1) = TokenHandle;
    TokenHandle = 0;
  }
  else
  {
    v16 = TokenHandle;
  }
  if ( v16 )
    CloseHandle(v16);
LABEL_27:
  v17 = UserTokenFromAppContainerContext;
  CTraceFuncW<long>::~CTraceFuncW<long>(v39);
  return v17;
}

```

## disassembly

```asm
0x18001f968  mov     [rsp-8+arg_10], rbx
0x18001f96d  mov     [rsp-8+arg_18], rsi
0x18001f972  push    rbp
0x18001f973  push    rdi
0x18001f974  push    r12
0x18001f976  push    r14
0x18001f978  push    r15
0x18001f97a  lea     rbp, [rsp-37h]
0x18001f97f  sub     rsp, 0F0h
0x18001f986  mov     rax, cs:__security_cookie
0x18001f98d  xor     rax, rsp
0x18001f990  mov     [rbp+57h+var_30], rax
0x18001f994  xor     r14d, r14d
0x18001f997  lea     r15, aCautoimpersona_5; "CAutoImpersonateClient::ImpersonateClie"...
0x18001f99e  mov     rdi, rcx
0x18001f9a1  mov     [rbp+57h+TokenHandle], r14
0x18001f9a5  mov     ecx, cs:dword_1801C3ABC
0x18001f9ab  lea     rax, [rsp+110h+var_D8]
0x18001f9b0  mov     rsi, rdx
0x18001f9b3  mov     [rsp+110h+var_D8], r14d
0x18001f9b8  lea     r12d, [r14+4]
0x18001f9bc  mov     [rbp+57h+TokenInformation], r14d
0x18001f9c0  mov     [rbp+57h+var_A8], r15
0x18001f9c4  mov     [rbp+57h+var_A0], rax
0x18001f9c8  mov     [rbp+57h+var_98], r14
0x18001f9cc  mov     [rbp+57h+var_90], r14
0x18001f9d0  sub     ecx, r12d
0x18001f9d3  jnz     loc_18001FBD4
0x18001f9d9  test    cs:byte_1801C36C4, r12b
0x18001f9e0  jz      loc_18001FA74
0x18001f9e6  lea     edx, [rcx+5Ch]; Ch
0x18001f9e9  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001f9f0  mov     rcx, rbx; Str
0x18001f9f3  call    cs:__imp_strrchr
0x18001f9f9  test    rax, rax
0x18001f9fc  jz      short loc_18001FA02
0x18001f9fe  lea     rbx, [rax+1]
0x18001fa02  mov     [rsp+110h+var_E0], 97h
0x18001fa0a  mov     r9d, 5
0x18001fa10  test    rbx, rbx
0x18001fa13  jz      loc_18001FEED
0x18001fa19  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fa1d  inc     rax
0x18001fa20  cmp     [rbx+rax], r14b
0x18001fa24  jnz     short loc_18001FA1D
0x18001fa26  inc     eax
0x18001fa28  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001fa2f  mov     [rbp+57h+var_68], eax
0x18001fa32  lea     rax, [rsp+110h+var_E0]
0x18001fa37  mov     [rbp+57h+var_50], rax
0x18001fa3b  lea     rax, aNull_2; "NULL"
0x18001fa42  mov     [rbp+57h+var_40], rax
0x18001fa46  lea     rax, [rbp+57h+var_80]
0x18001fa4a  mov     [rsp+110h+var_F0], rax
0x18001fa4f  mov     [rbp+57h+var_70], rbx
0x18001fa53  mov     [rbp+57h+var_64], r14d
0x18001fa57  mov     [rbp+57h+var_60], r15
0x18001fa5b  mov     [rbp+57h+var_58], 2Ah ; '*'
0x18001fa63  mov     [rbp+57h+var_48], r12
0x18001fa67  mov     [rbp+57h+var_38], 0Ah
0x18001fa6f  call    McGenEventWrite_EventWriteTransfer
0x18001fa74  call    cs:__imp_GetCurrentThread
0x18001fa7a  mov     ebx, 1
0x18001fa7f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001fa83  mov     r15d, 0F01FFh
0x18001fa89  mov     rcx, rax; ThreadHandle
0x18001fa8c  mov     r8d, ebx; OpenAsSelf
0x18001fa8f  mov     edx, r15d; DesiredAccess
0x18001fa92  call    cs:__imp_OpenThreadToken
0x18001fa98  test    eax, eax
0x18001fa9a  jnz     loc_18001FB75
0x18001faa0  call    cs:__imp_GetLastError
0x18001faa6  cmp     eax, 3F0h
0x18001faab  jnz     loc_18001FB78
0x18001fab1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001fab5  test    rcx, rcx
0x18001fab8  jnz     loc_18001FEFC
0x18001fabe  call    cs:__imp_RpcImpersonateClient
0x18001fac4  test    eax, eax
0x18001fac6  jnz     loc_18001FC84
0x18001facc  mov     [rdi], ebx
0x18001face  call    cs:__imp_GetCurrentThread
0x18001fad4  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001fad8  mov     r8d, ebx; OpenAsSelf
0x18001fadb  mov     rcx, rax; ThreadHandle
0x18001fade  mov     edx, r15d; DesiredAccess
0x18001fae1  call    cs:__imp_OpenThreadToken
0x18001fae7  test    eax, eax
0x18001fae9  jz      loc_18001FE6F
0x18001faef  call    cs:__imp_RpcRevertToSelf
0x18001faf5  test    eax, eax
0x18001faf7  jnz     loc_18001FC84
0x18001fafd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001fb01  lea     r8, [rsp+110h+var_E0]; int *
0x18001fb06  lea     rdx, [rbp+57h+var_C0]; void **
0x18001fb0a  mov     [rdi], r14d
0x18001fb0d  mov     [rsp+110h+var_E0], r14d
0x18001fb12  mov     [rbp+57h+var_C0], r14
0x18001fb16  mov     [rbp+57h+var_B0], r14
0x18001fb1a  mov     [rbp+57h+var_B8], r14
0x18001fb1e  call    ?GetUserTokenFromAppContainerContext@@YAJPEAXPEAPEAXAEAH@Z; GetUserTokenFromAppContainerContext(void *,void * *,int &)
0x18001fb23  mov     [rsp+110h+var_D8], eax
0x18001fb27  test    eax, eax
0x18001fb29  js      loc_18001FBC9
0x18001fb2f  cmp     [rsp+110h+var_E0], r14d
0x18001fb34  jnz     loc_18001FF0F
0x18001fb3a  lea     rcx, [rbp+57h+var_C0]
0x18001fb3e  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x18001fb43  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001fb47  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001fb4b  mov     r9d, r12d; TokenInformationLength
0x18001fb4e  mov     [rbp+57h+TokenInformation], r14d
0x18001fb52  mov     edx, 1Bh; TokenInformationClass
0x18001fb57  call    cs:__imp_SetTokenInformation
0x18001fb5d  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18001fb61  xor     ecx, ecx; Thread
0x18001fb63  call    cs:__imp_SetThreadToken
0x18001fb69  test    eax, eax
0x18001fb6b  jz      loc_18001FF2E
0x18001fb71  mov     [rdi], ebx
0x18001fb73  jmp     short loc_18001FB78
0x18001fb75  mov     [rdi+4], ebx
0x18001fb78  test    rsi, rsi
0x18001fb7b  jnz     loc_18001FC5C
0x18001fb81  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001fb85  test    rcx, rcx
0x18001fb88  jnz     short loc_18001FBC1
0x18001fb8a  mov     ebx, [rsp+110h+var_D8]
0x18001fb8e  lea     rcx, [rbp+57h+var_A8]
0x18001fb92  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001fb97  mov     eax, ebx
0x18001fb99  mov     rcx, [rbp+57h+var_30]
0x18001fb9d  xor     rcx, rsp; StackCookie
0x18001fba0  call    __security_check_cookie
0x18001fba5  lea     r11, [rsp+110h+var_20]
0x18001fbad  mov     rbx, [r11+40h]
0x18001fbb1  mov     rsi, [r11+48h]
0x18001fbb5  mov     rsp, r11
0x18001fbb8  pop     r15
0x18001fbba  pop     r14
0x18001fbbc  pop     r12
0x18001fbbe  pop     rdi
0x18001fbbf  pop     rbp
0x18001fbc0  retn
0x18001fbc1  call    cs:__imp_CloseHandle
0x18001fbc7  jmp     short loc_18001FB8A
0x18001fbc9  lea     rcx, [rbp+57h+var_C0]
0x18001fbcd  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x18001fbd2  jmp     short loc_18001FB78
0x18001fbd4  sub     ecx, 1
0x18001fbd7  jz      loc_18001FE12
0x18001fbdd  sub     ecx, 1
0x18001fbe0  jz      loc_18001FDB5
0x18001fbe6  sub     ecx, 1
0x18001fbe9  jz      loc_18001FD58
0x18001fbef  sub     ecx, 1
0x18001fbf2  jz      loc_18001FCFB
0x18001fbf8  sub     ecx, 1
0x18001fbfb  jnz     loc_18001FC97
0x18001fc01  test    cs:byte_1801C36CA, 10h
0x18001fc08  jz      loc_18001FA74
0x18001fc0e  lea     edx, [rcx+5Ch]; Ch
0x18001fc11  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fc18  mov     rcx, rbx; Str
0x18001fc1b  call    cs:__imp_strrchr
0x18001fc21  test    rax, rax
0x18001fc24  jz      short loc_18001FC2A
0x18001fc26  lea     rbx, [rax+1]
0x18001fc2a  mov     [rsp+110h+var_E0], 97h
0x18001fc32  mov     r9d, 5
0x18001fc38  test    rbx, rbx
0x18001fc3b  jz      loc_18001FEA2
0x18001fc41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fc45  inc     rax
0x18001fc48  cmp     [rbx+rax], r14b
0x18001fc4c  jnz     short loc_18001FC45
0x18001fc4e  inc     eax
0x18001fc50  lea     rdx, TokenProvider_TraceFunction_Enter
0x18001fc57  jmp     loc_18001FA2F
0x18001fc5c  cmp     [rsp+110h+var_D8], r14d
0x18001fc61  jl      loc_18001FB81
0x18001fc67  mov     rax, [rbp+57h+TokenHandle]
0x18001fc6b  test    rax, rax
0x18001fc6e  jz      loc_18001FB8A
0x18001fc74  mov     rcx, r14
0x18001fc77  mov     [rsi+8], rax
0x18001fc7b  mov     [rbp+57h+TokenHandle], rcx
0x18001fc7f  jmp     loc_18001FB85
0x18001fc84  jle     short loc_18001FC8E
0x18001fc86  movzx   eax, ax
0x18001fc89  or      eax, 80070000h
0x18001fc8e  mov     [rsp+110h+var_D8], eax
0x18001fc92  jmp     loc_18001FB78
0x18001fc97  cmp     ecx, 1
0x18001fc9a  jnz     loc_18001FA74
0x18001fca0  test    cs:byte_1801C36CB, 10h
0x18001fca7  jz      loc_18001FA74
0x18001fcad  lea     edx, [rcx+5Bh]; Ch
0x18001fcb0  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fcb7  mov     rcx, rbx; Str
0x18001fcba  call    cs:__imp_strrchr
0x18001fcc0  test    rax, rax
0x18001fcc3  jz      short loc_18001FCC9
0x18001fcc5  lea     rbx, [rax+1]
0x18001fcc9  mov     [rsp+110h+var_E0], 97h
0x18001fcd1  mov     r9d, 5
0x18001fcd7  test    rbx, rbx
0x18001fcda  jz      loc_18001FE93
0x18001fce0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fce4  inc     rax
0x18001fce7  cmp     [rbx+rax], r14b
0x18001fceb  jnz     short loc_18001FCE4
0x18001fced  inc     eax
0x18001fcef  lea     rdx, Extension_TraceFunction_Enter
0x18001fcf6  jmp     loc_18001FA2F
0x18001fcfb  test    cs:byte_1801C36C9, 10h
0x18001fd02  jz      loc_18001FA74
0x18001fd08  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fd0f  mov     edx, 5Ch ; '\'; Ch
0x18001fd14  mov     rcx, rbx; Str
0x18001fd17  call    cs:__imp_strrchr
0x18001fd1d  test    rax, rax
0x18001fd20  jz      short loc_18001FD26
0x18001fd22  lea     rbx, [rax+1]
0x18001fd26  mov     [rsp+110h+var_E0], 97h
0x18001fd2e  mov     r9d, 5
0x18001fd34  test    rbx, rbx
0x18001fd37  jz      loc_18001FEB1
0x18001fd3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fd41  inc     rax
0x18001fd44  cmp     [rbx+rax], r14b
0x18001fd48  jnz     short loc_18001FD41
0x18001fd4a  inc     eax
0x18001fd4c  lea     rdx, WlidBho_TraceFunction_Enter
0x18001fd53  jmp     loc_18001FA2F
0x18001fd58  test    cs:byte_1801C36C8, 8
0x18001fd5f  jz      loc_18001FA74
0x18001fd65  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fd6c  mov     edx, 5Ch ; '\'; Ch
0x18001fd71  mov     rcx, rbx; Str
0x18001fd74  call    cs:__imp_strrchr
0x18001fd7a  test    rax, rax
0x18001fd7d  jz      short loc_18001FD83
0x18001fd7f  lea     rbx, [rax+1]
0x18001fd83  mov     [rsp+110h+var_E0], 97h
0x18001fd8b  mov     r9d, 5
0x18001fd91  test    rbx, rbx
0x18001fd94  jz      loc_18001FEC0
0x18001fd9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fd9e  inc     rax
0x18001fda1  cmp     [rbx+rax], r14b
0x18001fda5  jnz     short loc_18001FD9E
0x18001fda7  inc     eax
0x18001fda9  lea     rdx, WlidProv_TraceFunction_Enter
0x18001fdb0  jmp     loc_18001FA2F
0x18001fdb5  test    cs:byte_1801C36C7, 8
0x18001fdbc  jz      loc_18001FA74
0x18001fdc2  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fdc9  mov     edx, 5Ch ; '\'; Ch
0x18001fdce  mov     rcx, rbx; Str
0x18001fdd1  call    cs:__imp_strrchr
0x18001fdd7  test    rax, rax
0x18001fdda  jz      short loc_18001FDE0
0x18001fddc  lea     rbx, [rax+1]
0x18001fde0  mov     [rsp+110h+var_E0], 97h
0x18001fde8  mov     r9d, 5
0x18001fdee  test    rbx, rbx
0x18001fdf1  jz      loc_18001FECF
0x18001fdf7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fdfb  inc     rax
0x18001fdfe  cmp     [rbx+rax], r14b
0x18001fe02  jnz     short loc_18001FDFB
0x18001fe04  inc     eax
0x18001fe06  lea     rdx, WlidCli_TraceFunction_Enter
0x18001fe0d  jmp     loc_18001FA2F
0x18001fe12  cmp     cs:byte_1801C36C5, r14b
0x18001fe19  jge     loc_18001FA74
0x18001fe1f  lea     rbx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001fe26  mov     edx, 5Ch ; '\'; Ch
0x18001fe2b  mov     rcx, rbx; Str
0x18001fe2e  call    cs:__imp_strrchr
0x18001fe34  test    rax, rax
0x18001fe37  jz      short loc_18001FE3D
0x18001fe39  lea     rbx, [rax+1]
0x18001fe3d  mov     [rsp+110h+var_E0], 97h
0x18001fe45  mov     r9d, 5
0x18001fe4b  test    rbx, rbx
0x18001fe4e  jz      loc_18001FEDE
0x18001fe54  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fe58  inc     rax
0x18001fe5b  cmp     [rbx+rax], r14b
0x18001fe5f  jnz     short loc_18001FE58
0x18001fe61  inc     eax
0x18001fe63  lea     rdx, WlidModern_TraceFunction_Enter
0x18001fe6a  jmp     loc_18001FA2F
0x18001fe6f  call    cs:__imp_GetLastError
0x18001fe75  test    eax, eax
0x18001fe77  jle     short loc_18001FE81
0x18001fe79  movzx   eax, ax
0x18001fe7c  or      eax, 80070000h
  ... truncated ...
```
