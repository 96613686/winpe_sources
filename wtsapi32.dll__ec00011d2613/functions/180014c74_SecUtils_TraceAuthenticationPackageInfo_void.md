# SecUtils::TraceAuthenticationPackageInfo(void *)

- ea: `0x180014c74`
- end: `0x180014fe4`
- name: `?TraceAuthenticationPackageInfo@SecUtils@@YAJPEAX@Z`
- size: `880`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x1800012ec`
- `0x18000173c`
- `0x180014bb0`
- `0x180014c44`
- `0x180014c74`
- `0x180015488`
- `0x18001559a`
- `0x1800155c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d62`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014e9a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014e9a`
- `SspiCli!LsaGetLogonSessionData` at `0x180014ddd`
- `SspiCli!LsaGetLogonSessionData` at `0x180014ddd`
- `SspiCli!LsaFreeReturnBuffer` at `0x180014fc0`
- `SspiCli!LsaFreeReturnBuffer` at `0x180014fc0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014d58`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014d58`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014d37`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014d37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014fa7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180014fa7`

## string_xrefs

- `0x180014cfd`: `Invalid token handle`
- `0x180014db4`: `GetTokenInformation failed on token`

## pseudocode

```c
__int64 __fastcall SecUtils::TraceAuthenticationPackageInfo(HANDLE TokenHandle, void *a2)
{
  signed int v3; // ebx
  int ActivityIdPrefix; // eax
  BOOL v5; // r15d
  signed int LastError; // eax
  int v7; // eax
  NTSTATUS LogonSessionData; // edi
  int v9; // edi
  const wchar_t *v10; // rsi
  unsigned int v11; // edi
  __int64 v12; // rcx
  int v13; // r14d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  PVOID v18; // rcx
  PVOID Buffer; // [rsp+60h] [rbp-A0h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-98h] BYREF
  int v22; // [rsp+6Ch] [rbp-94h] BYREF
  int v23; // [rsp+70h] [rbp-90h] BYREF
  PSECURITY_LOGON_SESSION_DATA *v24; // [rsp+78h] [rbp-88h] BYREF
  char *v25; // [rsp+80h] [rbp-80h] BYREF
  const char *v26; // [rsp+88h] [rbp-78h] BYREF
  const char *v27; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+98h] [rbp-68h] BYREF
  const char *v29; // [rsp+A0h] [rbp-60h] BYREF
  GUID ActivityId; // [rsp+B0h] [rbp-50h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData[2]; // [rsp+C0h] [rbp-40h] BYREF
  char v32; // [rsp+D0h] [rbp-30h]
  _OWORD TokenInformation[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v34; // [rsp+110h] [rbp+10h]

  Buffer = 0;
  v34 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v3 = 0;
    v5 = ImpersonateLoggedOnUser(TokenHandle);
    if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_14:
      ppLogonSessionData[1] = 0;
      ppLogonSessionData[0] = (PSECURITY_LOGON_SESSION_DATA)&Buffer;
      v32 = 1;
      LogonSessionData = LsaGetLogonSessionData((PLUID)TokenInformation + 1, &ppLogonSessionData[1]);
      wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&long LsaFreeReturnBuffer(void *)>>>(ppLogonSessionData);
      v9 = LogonSessionData | 0x10000000;
      if ( v9 < 0 )
      {
        v3 = v9;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
            v17,
            (__int64)"LsaGetLogonSessionData failed",
            v9);
        }
      }
      else if ( Buffer )
      {
        v10 = (const wchar_t *)*((_QWORD *)Buffer + 7);
        v11 = *((unsigned __int16 *)Buffer + 24) >> 1;
        if ( !wcsncmp_0(v10, L"NTLM", v11)
          || !wcsncmp_0(v10, L"MICROSOFT_AUTHENTICATION_PACKAGE_V1_0", v11)
          || (v13 = 0, !wcsncmp_0(v10, L"MSV1_0", v11)) )
        {
          v13 = 1;
        }
        if ( (unsigned int)dword_18001F000 > 4 && (unsigned __int8)tlgKeywordOn(v12, 0x470000000000LL) )
        {
          ActivityId = 0;
          ActivityId.Data1 = -186646528;
          EventActivityIdControl(1u, &ActivityId);
          v24 = ppLogonSessionData;
          *(GUID *)ppLogonSessionData = ActivityId;
          v22 = v13;
          v14 = *((_DWORD *)Buffer + 16);
          v25 = (char *)Buffer + 48;
          v26 = "Authentication";
          v27 = "Stack";
          v29 = "Checkpoint";
          v23 = v14;
          v28 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v14,
            (unsigned int)&word_18001AC46,
            v15,
            v16,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v22,
            (__int64)&v24);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = ((__int64 (*)(void))RdpX_GetActivityIdPrefix)();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        v7,
        (__int64)"GetTokenInformation failed on token",
        v3);
    }
    if ( v5 )
      RevertToSelf();
  }
  else
  {
    v3 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids,
        ActivityIdPrefix,
        (__int64)"Invalid token handle",
        87);
    }
  }
  v18 = Buffer;
  Buffer = 0;
  if ( v18 )
    LsaFreeReturnBuffer(v18);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180014c74  push    rbp
0x180014c76  push    rbx
0x180014c77  push    rsi
0x180014c78  push    rdi
0x180014c79  push    r14
0x180014c7b  push    r15
0x180014c7d  lea     rbp, [rsp-28h]
0x180014c82  sub     rsp, 128h
0x180014c89  mov     rax, cs:__security_cookie
0x180014c90  xor     rax, rsp
0x180014c93  mov     [rbp+50h+var_38], rax
0x180014c97  xor     eax, eax
0x180014c99  mov     [rsp+150h+Buffer], 0
0x180014ca2  xorps   xmm0, xmm0
0x180014ca5  mov     [rbp+50h+var_40], rax
0x180014ca9  mov     [rsp+150h+var_E8], eax
0x180014cad  mov     rdi, rcx
0x180014cb0  lea     rax, [rcx+1]
0x180014cb4  movups  [rbp+50h+TokenInformation], xmm0
0x180014cb8  movups  [rbp+50h+var_60], xmm0
0x180014cbc  movups  [rbp+50h+var_50], xmm0
0x180014cc0  test    rax, 0FFFFFFFFFFFFFFFEh
0x180014cc6  jnz     short loc_180014D35
0x180014cc8  mov     ebx, 80070057h
0x180014ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180014cd4  lea     rax, WPP_GLOBAL_Control
0x180014cdb  cmp     rcx, rax
0x180014cde  jz      loc_180014FAD
0x180014ce4  test    byte ptr [rcx+1Ch], 8
0x180014ce8  jz      loc_180014FAD
0x180014cee  cmp     byte ptr [rcx+19h], 2
0x180014cf2  jb      loc_180014FAD
0x180014cf8  call    RdpX_GetActivityIdPrefix
0x180014cfd  lea     rcx, aInvalidTokenHa; "Invalid token handle"
0x180014d04  mov     dword ptr [rsp+150h+var_128], 80070057h
0x180014d0c  mov     [rsp+150h+ReturnLength], rcx
0x180014d11  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x180014d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d1f  mov     edx, 0Ch
0x180014d24  mov     r9d, eax
0x180014d27  mov     rcx, [rcx+10h]
0x180014d2b  call    WPP_SF_DsD
0x180014d30  jmp     loc_180014FAD
0x180014d35  xor     ebx, ebx
0x180014d37  call    cs:__imp_ImpersonateLoggedOnUser
0x180014d3d  lea     r9d, [rbx+38h]; TokenInformationLength
0x180014d41  mov     rcx, rdi; TokenHandle
0x180014d44  mov     r15d, eax
0x180014d47  lea     r8, [rbp+50h+TokenInformation]; TokenInformation
0x180014d4b  lea     rax, [rsp+150h+var_E8]
0x180014d50  lea     edx, [rbx+0Ah]; TokenInformationClass
0x180014d53  mov     [rsp+150h+ReturnLength], rax; ReturnLength
0x180014d58  call    cs:__imp_GetTokenInformation
0x180014d5e  test    eax, eax
0x180014d60  jnz     short loc_180014DC0
0x180014d62  call    cs:__imp_GetLastError
0x180014d68  mov     ebx, eax
0x180014d6a  test    eax, eax
0x180014d6c  jle     short loc_180014D77
0x180014d6e  movzx   ebx, ax
0x180014d71  or      ebx, 80070000h
0x180014d77  test    ebx, ebx
0x180014d79  jns     short loc_180014DC0
0x180014d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d82  lea     rax, WPP_GLOBAL_Control
0x180014d89  cmp     rcx, rax
0x180014d8c  jz      loc_180014FA2
0x180014d92  test    byte ptr [rcx+1Ch], 8
0x180014d96  jz      loc_180014FA2
0x180014d9c  cmp     byte ptr [rcx+19h], 2
0x180014da0  jb      loc_180014FA2
0x180014da6  call    RdpX_GetActivityIdPrefix
0x180014dab  mov     edx, 0Dh
0x180014db0  mov     dword ptr [rsp+150h+var_128], ebx
0x180014db4  lea     rcx, aGettokeninform_0; "GetTokenInformation failed on token"
0x180014dbb  jmp     loc_180014F83
0x180014dc0  lea     rax, [rsp+150h+Buffer]
0x180014dc5  mov     [rbp+50h+ppLogonSessionData+8], 0
0x180014dcd  lea     rdx, [rbp+50h+ppLogonSessionData+8]; ppLogonSessionData
0x180014dd1  mov     [rbp+50h+ppLogonSessionData], rax
0x180014dd5  lea     rcx, [rbp+50h+TokenInformation+8]; LogonId
0x180014dd9  mov     [rbp+50h+var_80], 1
0x180014ddd  call    cs:__imp_LsaGetLogonSessionData
0x180014de3  lea     rcx, [rbp+50h+ppLogonSessionData]
0x180014de7  mov     edi, eax
0x180014de9  call    ??1?$out_param_t@V?$unique_ptr@U_SECURITY_LOGON_SESSION_DATA@@U?$function_deleter@P6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<_SECURITY_LOGON_SESSION_DATA,wil::function_deleter<long (*)(void *),&LsaFreeReturnBuffer(void *)>>>(void)
0x180014dee  or      edi, 10000000h
0x180014df4  jl      loc_180014F4D
0x180014dfa  mov     rax, [rsp+150h+Buffer]
0x180014dff  test    rax, rax
0x180014e02  jz      loc_180014FA2
0x180014e08  movzx   edi, word ptr [rax+30h]
0x180014e0c  lea     rdx, aNtlm; "NTLM"
0x180014e13  mov     rsi, [rax+38h]
0x180014e17  shr     edi, 1
0x180014e19  mov     rcx, rsi; String1
0x180014e1c  mov     r8d, edi; MaxCount
0x180014e1f  call    wcsncmp_0
0x180014e24  test    eax, eax
0x180014e26  jz      short loc_180014E57
0x180014e28  mov     r8d, edi; MaxCount
0x180014e2b  lea     rdx, aMicrosoftAuthe; "MICROSOFT_AUTHENTICATION_PACKAGE_V1_0"
0x180014e32  mov     rcx, rsi; String1
0x180014e35  call    wcsncmp_0
0x180014e3a  test    eax, eax
0x180014e3c  jz      short loc_180014E57
0x180014e3e  mov     r8d, edi; MaxCount
0x180014e41  lea     rdx, aMsv10; "MSV1_0"
0x180014e48  mov     rcx, rsi; String1
0x180014e4b  xor     r14d, r14d
0x180014e4e  call    wcsncmp_0
0x180014e53  test    eax, eax
0x180014e55  jnz     short loc_180014E5D
0x180014e57  mov     r14d, 1
0x180014e5d  mov     eax, cs:dword_18001F000
0x180014e63  cmp     eax, 4
0x180014e66  jbe     loc_180014FA2
0x180014e6c  mov     rdx, 470000000000h
0x180014e76  call    _tlgKeywordOn
0x180014e7b  test    al, al
0x180014e7d  jz      loc_180014FA2
0x180014e83  xorps   xmm0, xmm0
0x180014e86  lea     rdx, [rbp+50h+ActivityId]; ActivityId
0x180014e8a  movups  xmmword ptr [rbp+50h+ActivityId.Data1], xmm0
0x180014e8e  mov     ecx, 1; ControlCode
0x180014e93  mov     [rbp+50h+ActivityId.Data1], 0F4E00000h
0x180014e9a  call    cs:__imp_EventActivityIdControl
0x180014ea0  movaps  xmm0, xmmword ptr [rbp+50h+ActivityId.Data1]
0x180014ea4  lea     rax, [rbp+50h+ppLogonSessionData]
0x180014ea8  mov     [rsp+150h+var_D8], rax
0x180014ead  lea     rdx, word_18001AC46
0x180014eb4  mov     rax, [rsp+150h+Buffer]
0x180014eb9  movdqa  xmmword ptr [rbp+50h+ppLogonSessionData], xmm0
0x180014ebe  mov     [rsp+150h+var_E4], r14d
0x180014ec3  mov     ecx, [rax+40h]
0x180014ec6  add     rax, 30h ; '0'
0x180014eca  mov     [rbp+50h+var_D0], rax
0x180014ece  lea     rax, aAuthentication; "Authentication"
0x180014ed5  mov     [rbp+50h+var_C8], rax
0x180014ed9  lea     rax, aStack; "Stack"
0x180014ee0  mov     [rbp+50h+var_C0], rax
0x180014ee4  lea     rax, aCheckpoint; "Checkpoint"
0x180014eeb  mov     [rbp+50h+var_B0], rax
0x180014eef  lea     rax, [rsp+150h+var_D8]
0x180014ef4  mov     [rsp+150h+var_F8], rax
0x180014ef9  lea     rax, [rsp+150h+var_E4]
0x180014efe  mov     [rsp+150h+var_100], rax
0x180014f03  lea     rax, [rsp+150h+var_E0]
0x180014f08  mov     [rsp+150h+var_108], rax
0x180014f0d  lea     rax, [rbp+50h+var_D0]
0x180014f11  mov     [rsp+150h+var_110], rax
0x180014f16  lea     rax, [rbp+50h+var_C8]
0x180014f1a  mov     [rsp+150h+var_118], rax
0x180014f1f  lea     rax, [rbp+50h+var_C0]
0x180014f23  mov     [rsp+150h+var_120], rax
0x180014f28  lea     rax, [rbp+50h+var_B8]
0x180014f2c  mov     [rsp+150h+var_128], rax
0x180014f31  lea     rax, [rbp+50h+var_B0]
0x180014f35  mov     [rsp+150h+ReturnLength], rax
0x180014f3a  mov     [rsp+150h+var_E0], ecx
0x180014f3e  mov     [rbp+50h+var_B8], 1000000h
0x180014f46  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014f4b  jmp     short loc_180014FA2
0x180014f4d  mov     ebx, edi
0x180014f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f56  lea     rax, WPP_GLOBAL_Control
0x180014f5d  cmp     rcx, rax
0x180014f60  jz      short loc_180014FA2
0x180014f62  test    byte ptr [rcx+1Ch], 8
0x180014f66  jz      short loc_180014FA2
0x180014f68  cmp     byte ptr [rcx+19h], 2
0x180014f6c  jb      short loc_180014FA2
0x180014f6e  call    RdpX_GetActivityIdPrefix
0x180014f73  mov     edx, 0Eh
0x180014f78  mov     dword ptr [rsp+150h+var_128], edi
0x180014f7c  lea     rcx, aLsagetlogonses; "LsaGetLogonSessionData failed"
0x180014f83  mov     [rsp+150h+ReturnLength], rcx
0x180014f88  lea     r8, WPP_f5b992e9d455330a647a66dd3f03467f_Traceguids
0x180014f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f96  mov     r9d, eax
0x180014f99  mov     rcx, [rcx+10h]
0x180014f9d  call    WPP_SF_DsD
0x180014fa2  test    r15d, r15d
0x180014fa5  jz      short loc_180014FAD
0x180014fa7  call    cs:__imp_RevertToSelf
0x180014fad  mov     rcx, [rsp+150h+Buffer]; Buffer
0x180014fb2  mov     [rsp+150h+Buffer], 0
0x180014fbb  test    rcx, rcx
0x180014fbe  jz      short loc_180014FC6
0x180014fc0  call    cs:__imp_LsaFreeReturnBuffer
0x180014fc6  mov     eax, ebx
0x180014fc8  mov     rcx, [rbp+50h+var_38]
0x180014fcc  xor     rcx, rsp; StackCookie
0x180014fcf  call    __security_check_cookie
0x180014fd4  add     rsp, 128h
0x180014fdb  pop     r15
0x180014fdd  pop     r14
0x180014fdf  pop     rdi
0x180014fe0  pop     rsi
0x180014fe1  pop     rbx
0x180014fe2  pop     rbp
0x180014fe3  retn
```
