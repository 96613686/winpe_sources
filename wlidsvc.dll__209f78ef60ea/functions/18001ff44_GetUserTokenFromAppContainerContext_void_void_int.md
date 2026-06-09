# GetUserTokenFromAppContainerContext(void *,void * *,int &)

- ea: `0x18001ff44`
- end: `0x1800204a3`
- name: `?GetUserTokenFromAppContainerContext@@YAJPEAXPEAPEAXAEAH@Z`
- size: `1375`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f968`

## callees

- `0x18000c050`
- `0x18001a9c0`
- `0x18001b760`
- `0x18001ff44`
- `0x1800204ac`
- `0x1800204c4`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001ffe8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020128`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020181`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800201da`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020233`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002028c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800202e5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001ffe8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020128`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020181`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800201da`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020233`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002028c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800202e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020352`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020490`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020490`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002042c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18002042c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180020452`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180020452`

## string_xrefs

- `0x18001ffa6`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18001ff71`: `GetUserTokenFromAppContainerContext`
- `0x1800203f0`: `hr = IsTokenAppContainer(hThreadToken, isTokenAppContainer)`
- `0x18002043a`: `hr = UMgrQueryUserContext(hThreadToken, &userContext)`
- `0x180020460`: `hr = UMgrQueryUserToken(userContext, &hUserTokenLocal)`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromAppContainerContext(HANDLE TokenHandle, void **a2, int *a3)
{
  char *v6; // rax
  __int64 v7; // r8
  const char *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *v11; // rdx
  signed int UserToken; // eax
  unsigned int v13; // ebx
  char *v15; // rax
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // rcx
  char *v19; // rax
  __int64 v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  char *v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  __int64 v26; // rcx
  const char *v27; // rcx
  unsigned int v28; // r8d
  int v29; // [rsp+30h] [rbp-A9h] BYREF
  signed int v30; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v31; // [rsp+40h] [rbp-99h] BYREF
  void *phNewToken; // [rsp+48h] [rbp-91h] BYREF
  __int64 v33; // [rsp+50h] [rbp-89h]
  __int64 v34; // [rsp+58h] [rbp-81h]
  HANDLE hExistingToken[3]; // [rsp+60h] [rbp-79h] BYREF
  _QWORD v36[5]; // [rsp+78h] [rbp-61h] BYREF
  char v37[16]; // [rsp+A0h] [rbp-39h] BYREF
  const char *v38; // [rsp+B0h] [rbp-29h]
  int v39; // [rsp+B8h] [rbp-21h]
  int v40; // [rsp+BCh] [rbp-1Dh]
  const char *v41; // [rsp+C0h] [rbp-19h]
  __int64 v42; // [rsp+C8h] [rbp-11h]
  int *v43; // [rsp+D0h] [rbp-9h]
  __int64 v44; // [rsp+D8h] [rbp-1h]
  const wchar_t *v45; // [rsp+E0h] [rbp+7h]
  __int64 v46; // [rsp+E8h] [rbp+Fh]

  v30 = 0;
  memset(hExistingToken, 0, sizeof(hExistingToken));
  v31 = 0;
  phNewToken = 0;
  v34 = 0;
  v33 = 0;
  v36[0] = "GetUserTokenFromAppContainerContext";
  v36[1] = &v30;
  v36[2] = 0;
  v36[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) == 0 )
        break;
      v6 = strrchr(
             "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
             dword_1801C3ABC - 4 + 92);
      if ( v6 )
        v8 = v6 + 1;
      else
        v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
      v29 = 11521;
      if ( v8 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v8[v9] );
        v10 = (unsigned int)(v9 + 1);
      }
      else
      {
        v8 = "NULL";
        v10 = 5;
      }
      v11 = WlidSvc_TraceFunction_Enter;
      goto LABEL_10;
    case 5:
      if ( byte_1801C36C5 < 0 )
      {
        v25 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v25 )
          v8 = v25 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v8[v26] );
          v10 = (unsigned int)(v26 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = WlidModern_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 6:
      if ( (byte_1801C36C7 & 8) != 0 )
      {
        v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v23 )
          v8 = v23 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v8[v24] );
          v10 = (unsigned int)(v24 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = WlidCli_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 7:
      if ( (byte_1801C36C8 & 8) != 0 )
      {
        v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v21 )
          v8 = v21 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v8[v22] );
          v10 = (unsigned int)(v22 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = WlidProv_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 8:
      if ( (byte_1801C36C9 & 0x10) != 0 )
      {
        v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v19 )
          v8 = v19 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v8[v20] );
          v10 = (unsigned int)(v20 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = WlidBho_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 9:
      if ( (byte_1801C36CA & 0x10) != 0 )
      {
        v17 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v17 )
          v8 = v17 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v8[v18] );
          v10 = (unsigned int)(v18 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = TokenProvider_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v15 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v15 )
          v8 = v15 + 1;
        else
          v8 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v29 = 11521;
        if ( v8 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v8[v16] );
          v10 = (unsigned int)(v16 + 1);
        }
        else
        {
          v8 = "NULL";
          v10 = 5;
        }
        v11 = Extension_TraceFunction_Enter;
LABEL_10:
        v38 = v8;
        v43 = &v29;
        v45 = L"NULL";
        v39 = v10;
        v40 = 0;
        v41 = "GetUserTokenFromAppContainerContext";
        v42 = 36;
        v44 = 4;
        v46 = 10;
        McGenEventWrite_EventWriteTransfer(v10, v11, v7, 5, v37);
      }
      break;
  }
  *a2 = 0;
  *a3 = 0;
  UserToken = IsTokenAppContainer(TokenHandle, a3);
  v30 = UserToken;
  if ( UserToken < 0 )
  {
    v27 = "hr = IsTokenAppContainer(hThreadToken, isTokenAppContainer)";
    v28 = 11531;
    goto LABEL_88;
  }
  if ( *a3 )
  {
    UserToken = UMgrQueryUserContext(TokenHandle, &v31);
    v30 = UserToken;
    if ( UserToken >= 0 )
    {
      UserToken = UMgrQueryUserToken(v31, hExistingToken);
      v30 = UserToken;
      if ( UserToken >= 0 )
      {
        if ( DuplicateTokenEx(hExistingToken[0], 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
          goto LABEL_78;
        UserToken = GetLastError();
        if ( UserToken > 0 )
          UserToken = (unsigned __int16)UserToken | 0x80070000;
        v30 = UserToken;
        if ( UserToken >= 0 )
        {
LABEL_78:
          *a2 = phNewToken;
          phNewToken = 0;
          v33 = 0;
          goto LABEL_13;
        }
        v27 = "hr = HRESULT_FROM_WIN32(GetLastError())";
        v28 = 11540;
      }
      else
      {
        v27 = "hr = UMgrQueryUserToken(userContext, &hUserTokenLocal)";
        v28 = 11536;
      }
    }
    else
    {
      v27 = "hr = UMgrQueryUserContext(hThreadToken, &userContext)";
      v28 = 11535;
    }
LABEL_88:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "GetUserTokenFromAppContainerContext",
      v28,
      UserToken,
      v27);
  }
LABEL_13:
  v13 = v30;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v36);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(&phNewToken);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(hExistingToken);
  return v13;
}

```

## disassembly

```asm
0x18001ff44  mov     [rsp-8+arg_18], rbx
0x18001ff49  push    rbp
0x18001ff4a  push    rsi
0x18001ff4b  push    rdi
0x18001ff4c  push    r12
0x18001ff4e  push    r13
0x18001ff50  push    r14
0x18001ff52  push    r15
0x18001ff54  lea     rbp, [rsp-27h]
0x18001ff59  sub     rsp, 100h
0x18001ff60  mov     rax, cs:__security_cookie
0x18001ff67  xor     rax, rsp
0x18001ff6a  mov     [rbp+57h+var_40], rax
0x18001ff6e  xor     r14d, r14d
0x18001ff71  lea     r12, aGetusertokenfr; "GetUserTokenFromAppContainerContext"
0x18001ff78  mov     rdi, rcx
0x18001ff7b  mov     [rsp+130h+var_F8], r14d
0x18001ff80  mov     ecx, cs:dword_1801C3ABC
0x18001ff86  lea     rax, [rsp+130h+var_F8]
0x18001ff8b  mov     rbx, r8
0x18001ff8e  mov     [rbp+57h+hExistingToken], r14
0x18001ff92  lea     r13d, [r14+4]
0x18001ff96  mov     [rbp+57h+var_C0], r14
0x18001ff9a  mov     [rbp+57h+var_C8], r14
0x18001ff9e  mov     rsi, rdx
0x18001ffa1  mov     [rsp+130h+var_F0], r14
0x18001ffa6  lea     r15, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001ffad  mov     [rsp+130h+var_E8], r14
0x18001ffb2  mov     [rsp+130h+var_D8], r14
0x18001ffb7  mov     [rsp+130h+var_E0], r14
0x18001ffbc  mov     [rbp+57h+var_B8], r12
0x18001ffc0  mov     [rbp+57h+var_B0], rax
0x18001ffc4  mov     [rbp+57h+var_A8], r14
0x18001ffc8  mov     [rbp+57h+var_A0], r14
0x18001ffcc  sub     ecx, r13d
0x18001ffcf  jnz     loc_1800200E3
0x18001ffd5  test    cs:byte_1801C36C4, r13b
0x18001ffdc  jz      loc_18002006C
0x18001ffe2  lea     edx, [rcx+5Ch]; Ch
0x18001ffe5  mov     rcx, r15; Str
0x18001ffe8  call    cs:__imp_strrchr
0x18001ffee  test    rax, rax
0x18001fff1  jz      loc_1800200DB
0x18001fff7  inc     rax
0x18001fffa  mov     [rsp+130h+var_100], 2D01h
0x180020002  mov     r9d, 5
0x180020008  test    rax, rax
0x18002000b  jz      loc_1800203E1
0x180020011  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020015  inc     rcx
0x180020018  cmp     [rax+rcx], r14b
0x18002001c  jnz     short loc_180020015
0x18002001e  inc     ecx
0x180020020  lea     rdx, WlidSvc_TraceFunction_Enter
0x180020027  mov     [rbp+57h+var_80], rax
0x18002002b  lea     rax, [rsp+130h+var_100]
0x180020030  mov     [rbp+57h+var_60], rax
0x180020034  lea     rax, aNull_2; "NULL"
0x18002003b  mov     [rbp+57h+var_50], rax
0x18002003f  lea     rax, [rbp+57h+var_90]
0x180020043  mov     qword ptr [rsp+130h+TokenType], rax
0x180020048  mov     [rbp+57h+var_78], ecx
0x18002004b  mov     [rbp+57h+var_74], r14d
0x18002004f  mov     [rbp+57h+var_70], r12
0x180020053  mov     [rbp+57h+var_68], 24h ; '$'
0x18002005b  mov     [rbp+57h+var_58], r13
0x18002005f  mov     [rbp+57h+var_48], 0Ah
0x180020067  call    McGenEventWrite_EventWriteTransfer
0x18002006c  mov     [rsi], r14
0x18002006f  mov     rdx, rbx; int *
0x180020072  mov     rcx, rdi; TokenHandle
0x180020075  mov     [rbx], r14d
0x180020078  call    ?IsTokenAppContainer@@YAJPEAXAEAH@Z; IsTokenAppContainer(void *,int &)
0x18002007d  mov     [rsp+130h+var_F8], eax
0x180020081  test    eax, eax
0x180020083  js      loc_1800203F0
0x180020089  cmp     [rbx], r14d
0x18002008c  jnz     loc_180020424
0x180020092  mov     ebx, [rsp+130h+var_F8]
0x180020096  lea     rcx, [rbp+57h+var_B8]
0x18002009a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18002009f  lea     rcx, [rsp+130h+var_E8]
0x1800200a4  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x1800200a9  lea     rcx, [rbp+57h+hExistingToken]
0x1800200ad  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x1800200b2  mov     eax, ebx
0x1800200b4  mov     rcx, [rbp+57h+var_40]
0x1800200b8  xor     rcx, rsp; StackCookie
0x1800200bb  call    __security_check_cookie
0x1800200c0  mov     rbx, [rsp+130h+arg_18]
0x1800200c8  add     rsp, 100h
0x1800200cf  pop     r15
0x1800200d1  pop     r14
0x1800200d3  pop     r13
0x1800200d5  pop     r12
0x1800200d7  pop     rdi
0x1800200d8  pop     rsi
0x1800200d9  pop     rbp
0x1800200da  retn
0x1800200db  mov     rax, r15
0x1800200de  jmp     loc_18001FFFA
0x1800200e3  sub     ecx, 1
0x1800200e6  jz      loc_1800202D0
0x1800200ec  sub     ecx, 1
0x1800200ef  jz      loc_180020277
0x1800200f5  sub     ecx, 1
0x1800200f8  jz      loc_18002021E
0x1800200fe  sub     ecx, 1
0x180020101  jz      loc_1800201C5
0x180020107  sub     ecx, 1
0x18002010a  jz      short loc_18002016C
0x18002010c  cmp     ecx, 1
0x18002010f  jnz     loc_18002006C
0x180020115  test    cs:byte_1801C36CB, 10h
0x18002011c  jz      loc_18002006C
0x180020122  lea     edx, [rcx+5Bh]; Ch
0x180020125  mov     rcx, r15; Str
0x180020128  call    cs:__imp_strrchr
0x18002012e  test    rax, rax
0x180020131  jz      loc_180020325
0x180020137  inc     rax
0x18002013a  mov     [rsp+130h+var_100], 2D01h
0x180020142  mov     r9d, 5
0x180020148  test    rax, rax
0x18002014b  jz      loc_180020387
0x180020151  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020155  inc     rcx
0x180020158  cmp     [rax+rcx], r14b
0x18002015c  jnz     short loc_180020155
0x18002015e  inc     ecx
0x180020160  lea     rdx, Extension_TraceFunction_Enter
0x180020167  jmp     loc_180020027
0x18002016c  test    cs:byte_1801C36CA, 10h
0x180020173  jz      loc_18002006C
0x180020179  mov     edx, 5Ch ; '\'; Ch
0x18002017e  mov     rcx, r15; Str
0x180020181  call    cs:__imp_strrchr
0x180020187  test    rax, rax
0x18002018a  jz      loc_18002032D
0x180020190  inc     rax
0x180020193  mov     [rsp+130h+var_100], 2D01h
0x18002019b  mov     r9d, 5
0x1800201a1  test    rax, rax
0x1800201a4  jz      loc_180020396
0x1800201aa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800201ae  inc     rcx
0x1800201b1  cmp     [rax+rcx], r14b
0x1800201b5  jnz     short loc_1800201AE
0x1800201b7  inc     ecx
0x1800201b9  lea     rdx, TokenProvider_TraceFunction_Enter
0x1800201c0  jmp     loc_180020027
0x1800201c5  test    cs:byte_1801C36C9, 10h
0x1800201cc  jz      loc_18002006C
0x1800201d2  mov     edx, 5Ch ; '\'; Ch
0x1800201d7  mov     rcx, r15; Str
0x1800201da  call    cs:__imp_strrchr
0x1800201e0  test    rax, rax
0x1800201e3  jz      loc_180020335
0x1800201e9  inc     rax
0x1800201ec  mov     [rsp+130h+var_100], 2D01h
0x1800201f4  mov     r9d, 5
0x1800201fa  test    rax, rax
0x1800201fd  jz      loc_1800203A5
0x180020203  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020207  inc     rcx
0x18002020a  cmp     [rax+rcx], r14b
0x18002020e  jnz     short loc_180020207
0x180020210  inc     ecx
0x180020212  lea     rdx, WlidBho_TraceFunction_Enter
0x180020219  jmp     loc_180020027
0x18002021e  test    cs:byte_1801C36C8, 8
0x180020225  jz      loc_18002006C
0x18002022b  mov     edx, 5Ch ; '\'; Ch
0x180020230  mov     rcx, r15; Str
0x180020233  call    cs:__imp_strrchr
0x180020239  test    rax, rax
0x18002023c  jz      loc_18002033D
0x180020242  inc     rax
0x180020245  mov     [rsp+130h+var_100], 2D01h
0x18002024d  mov     r9d, 5
0x180020253  test    rax, rax
0x180020256  jz      loc_1800203B4
0x18002025c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020260  inc     rcx
0x180020263  cmp     [rax+rcx], r14b
0x180020267  jnz     short loc_180020260
0x180020269  inc     ecx
0x18002026b  lea     rdx, WlidProv_TraceFunction_Enter
0x180020272  jmp     loc_180020027
0x180020277  test    cs:byte_1801C36C7, 8
0x18002027e  jz      loc_18002006C
0x180020284  mov     edx, 5Ch ; '\'; Ch
0x180020289  mov     rcx, r15; Str
0x18002028c  call    cs:__imp_strrchr
0x180020292  test    rax, rax
0x180020295  jz      loc_180020345
0x18002029b  inc     rax
0x18002029e  mov     [rsp+130h+var_100], 2D01h
0x1800202a6  mov     r9d, 5
0x1800202ac  test    rax, rax
0x1800202af  jz      loc_1800203C3
0x1800202b5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800202b9  inc     rcx
0x1800202bc  cmp     [rax+rcx], r14b
0x1800202c0  jnz     short loc_1800202B9
0x1800202c2  inc     ecx
0x1800202c4  lea     rdx, WlidCli_TraceFunction_Enter
0x1800202cb  jmp     loc_180020027
0x1800202d0  cmp     cs:byte_1801C36C5, r14b
0x1800202d7  jge     loc_18002006C
0x1800202dd  mov     edx, 5Ch ; '\'; Ch
0x1800202e2  mov     rcx, r15; Str
0x1800202e5  call    cs:__imp_strrchr
0x1800202eb  test    rax, rax
0x1800202ee  jz      short loc_18002034D
0x1800202f0  inc     rax
0x1800202f3  mov     [rsp+130h+var_100], 2D01h
0x1800202fb  mov     r9d, 5
0x180020301  test    rax, rax
0x180020304  jz      loc_1800203D2
0x18002030a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002030e  inc     rcx
0x180020311  cmp     [rax+rcx], r14b
0x180020315  jnz     short loc_18002030E
0x180020317  inc     ecx
0x180020319  lea     rdx, WlidModern_TraceFunction_Enter
0x180020320  jmp     loc_180020027
0x180020325  mov     rax, r15
0x180020328  jmp     loc_18002013A
0x18002032d  mov     rax, r15
0x180020330  jmp     loc_180020193
0x180020335  mov     rax, r15
0x180020338  jmp     loc_1800201EC
0x18002033d  mov     rax, r15
0x180020340  jmp     loc_180020245
0x180020345  mov     rax, r15
0x180020348  jmp     loc_18002029E
0x18002034d  mov     rax, r15
0x180020350  jmp     short loc_1800202F3
0x180020352  call    cs:__imp_GetLastError
0x180020358  test    eax, eax
0x18002035a  jle     short loc_180020364
0x18002035c  movzx   eax, ax
0x18002035f  or      eax, 80070000h
0x180020364  mov     [rsp+130h+var_F8], eax
0x180020368  test    eax, eax
0x18002036a  js      loc_1800203FF
0x180020370  mov     rax, [rsp+130h+var_E8]
0x180020375  mov     [rsi], rax
0x180020378  mov     [rsp+130h+var_E8], r14
0x18002037d  mov     [rsp+130h+var_E0], r14
0x180020382  jmp     loc_180020092
0x180020387  lea     rax, aNull_0; "NULL"
0x18002038e  mov     ecx, r9d
0x180020391  jmp     loc_180020160
0x180020396  lea     rax, aNull_0; "NULL"
0x18002039d  mov     ecx, r9d
0x1800203a0  jmp     loc_1800201B9
0x1800203a5  lea     rax, aNull_0; "NULL"
0x1800203ac  mov     ecx, r9d
0x1800203af  jmp     loc_180020212
0x1800203b4  lea     rax, aNull_0; "NULL"
0x1800203bb  mov     ecx, r9d
0x1800203be  jmp     loc_18002026B
0x1800203c3  lea     rax, aNull_0; "NULL"
0x1800203ca  mov     ecx, r9d
0x1800203cd  jmp     loc_1800202C4
0x1800203d2  lea     rax, aNull_0; "NULL"
0x1800203d9  mov     ecx, r9d
0x1800203dc  jmp     loc_180020319
0x1800203e1  lea     rax, aNull_0; "NULL"
0x1800203e8  mov     ecx, r9d
0x1800203eb  jmp     loc_180020020
0x1800203f0  lea     rcx, aHrIstokenappco; "hr = IsTokenAppContainer(hThreadToken, "...
0x1800203f7  mov     r8d, 2D0Bh
0x1800203fd  jmp     short loc_18002040C
0x1800203ff  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180020406  mov     r8d, 2D14h; unsigned int
0x18002040c  mov     qword ptr [rsp+130h+TokenType], rcx; char *
0x180020411  mov     r9d, eax; int
0x180020414  mov     rcx, r15; char *
0x180020417  mov     rdx, r12; char *
0x18002041a  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002041f  jmp     loc_180020092
0x180020424  lea     rdx, [rsp+130h+var_F0]
0x180020429  mov     rcx, rdi
0x18002042c  call    cs:__imp_UMgrQueryUserContext
0x180020432  mov     [rsp+130h+var_F8], eax
0x180020436  test    eax, eax
0x180020438  jns     short loc_180020449
0x18002043a  lea     rcx, aHrUmgrqueryuse; "hr = UMgrQueryUserContext(hThreadToken,"...
0x180020441  mov     r8d, 2D0Fh
0x180020447  jmp     short loc_18002040C
0x180020449  mov     rcx, [rsp+130h+var_F0]
0x18002044e  lea     rdx, [rbp+57h+hExistingToken]
0x180020452  call    cs:__imp_UMgrQueryUserToken
0x180020458  mov     [rsp+130h+var_F8], eax
0x18002045c  test    eax, eax
0x18002045e  jns     short loc_18002046F
0x180020460  lea     rcx, aHrUmgrqueryuse_0; "hr = UMgrQueryUserToken(userContext, &h"...
  ... truncated ...
```
