# UserMgrCli::GetImpersonationTokenForContext(void *,void *,unsigned __int64,void * *)

- ea: `0x18003c650`
- end: `0x18003cc34`
- name: `?GetImpersonationTokenForContext@UserMgrCli@@QEAAJPEAX0_KPEAPEAX@Z`
- size: `1508`
- prototype: `int(UserMgrCli *__hidden this, void *, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c630`

## callees

- `0x180006130`
- `0x180007920`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c6d0`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180014ee0`
- `0x180016380`
- `0x180036684`
- `0x180039d70`
- `0x18003c650`
- `0x18004e4e8`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c792`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c814`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c9cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c792`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c814`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c9cd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003c99d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003c99d`
- `ntdll!RtlCheckSandboxedToken` at `0x18003c74b`
- `ntdll!RtlCheckSandboxedToken` at `0x18003c74b`
- `ntdll!RtlEqualSid` at `0x18003c840`
- `ntdll!RtlEqualSid` at `0x18003c840`

## string_xrefs

- `0x18003ca88`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003ca9c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cab3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cac4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cad8`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cae9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cafa`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb11`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb28`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb3c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb53`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb67`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb7b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cb92`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cba6`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cbbd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cbd1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cbe8`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cbfc`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cc0d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003cc21`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserMgrCli::GetImpersonationTokenForContext(
        UserMgrCli *this,
        void *a2,
        void *a3,
        __int64 a4,
        void **phNewToken)
{
  unsigned __int64 v5; // rbp
  const struct _tlgProvider_t *v8; // rax
  int v9; // r8d
  int v10; // r9d
  void *v11; // rdx
  UserMgrCli *v12; // rcx
  int BasicCallerInformation; // eax
  int v14; // eax
  const char *v15; // r9
  int UserToken; // eax
  const char *v17; // r9
  const char *v18; // r9
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, unsigned __int64); // rbx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  void *v27; // rcx
  const char *v28; // r9
  unsigned int v29; // edx
  const char *v30; // r9
  int v31; // eax
  const struct _tlgProvider_t *v32; // rax
  __int64 result; // rax
  const struct _tlgProvider_t *v34; // rax
  int v35; // ebx
  wil *v36; // rcx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  int ReturnLengtha; // [rsp+20h] [rbp-30h]
  int ReturnLengthb; // [rsp+20h] [rbp-30h]
  int ReturnLengthc; // [rsp+20h] [rbp-30h]
  _BYTE v41[4]; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+3A8h] [rbp+358h]

  v5 = (unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = a4;
  v8 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v8 > 4u )
  {
    *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)&byte_180128E6F,
      v9,
      v10,
      v5 + 8);
  }
  memset_0((void *)(v5 + 192), 0, 0x1A0u);
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2C) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1C) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_BYTE *)v5 = 0;
  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x34) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
  memset_0((void *)(v5 + 104), 0, 0x50u);
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v12,
                               v11,
                               (struct _BASIC_CALLER_INFORMATION *)(v5 + 192));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC93,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        ReturnLength);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v5 + 192),
      (const struct _CALLER_RESTRICTIONS *)&dword_1801135EC);
    v14 = RtlCheckSandboxedToken(a3, (unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xC99,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v14,
        ReturnLength);
    if ( *(_BYTE *)v5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        ReturnLength);
    if ( !GetTokenInformation(a3, TokenSessionId, (LPVOID)(v5 + 4), 4u, (PDWORD)(v5 + 40)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC9D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v15);
    UserToken = _InternalQueryUserToken(
                  *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4),
                  (PHANDLE)(v5 + 72));
    if ( UserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)UserToken,
        ReturnLengtha);
    if ( !GetTokenInformation(a3, TokenUser, (LPVOID)(v5 + 704), 0x54u, (PDWORD)(v5 + 44)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xC9F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v17);
    if ( !GetTokenInformation(
            *(HANDLE *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
            TokenUser,
            (LPVOID)(v5 + 608),
            0x54u,
            (PDWORD)(v5 + 48)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xCA0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v18);
    if ( !RtlEqualSid(
            *(PSID *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2C0),
            *(PSID *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x260)) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        ReturnLengthb);
    v19 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v5 + 56));
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v19,
        ReturnLengthb);
    v20 = *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
    v21 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64))(*(_QWORD *)v20 + 160LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 16);
    v22 = v21(v20, a4, v5 + 16);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v22,
        ReturnLengthb);
    if ( !*(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v23 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 16),
            (__int64 *)(v5 + 32));
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v23,
        ReturnLengthb);
    v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v41
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x20)
                                                              + 96LL))(
            *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
            v5 + 24);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v24,
        ReturnLengthb);
    if ( *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) != *(_DWORD *)(((unsigned __int64)v41
                                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                          + 4) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v25 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v41
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x10)
                                                              + 56LL))(
            *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
            v5 + 28);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v25,
        ReturnLengthb);
    if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x1C) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v41
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x20)
                                                              + 80LL))(
            *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
            v5 + 80);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v26,
        ReturnLengthb);
    v27 = *(void **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
    if ( !v27 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    if ( !DuplicateTokenEx(v27, 0x80040004, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xCBB,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v28);
    if ( !GetTokenInformation(*phNewToken, TokenUser, (LPVOID)(v5 + 96), 0x58u, (PDWORD)(v5 + 52)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xCC3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v30);
    v31 = GiveTokenUserAdditionalAccess(
            *phNewToken,
            v29,
            *(void **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60));
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v31,
        ReturnLengthc);
    v32 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v32 > 4u )
    {
      *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)&word_180128E1E,
        0,
        0,
        v5 + 64,
        v5 + 8);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 32);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5 + 56);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 16);
    result = 0;
  }
  catch ( ... )
  {
    v34 = UserMgrUserModelTelemetry::Provider();
    v35 = (int)v34;
    v36 = (wil *)*(unsigned int *)v34;
    if ( (unsigned int)v36 > 4 )
    {
      *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v36);
      *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = *(_QWORD *)(((unsigned __int64)v41
                                                                                       & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                      + 0x58);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned int)word_180128D6A,
        0,
        0,
        ((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 64,
        ((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    }
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v36);
    return *(unsigned int *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8);
  }
  return result;
}

```

## disassembly

```asm
0x18003c650  mov     [rsp-8+arg_0], rbx
0x18003c655  push    rbp
0x18003c656  push    rsi
0x18003c657  push    rdi
0x18003c658  push    r14
0x18003c65a  push    r15
0x18003c65c  sub     rsp, 380h
0x18003c663  lea     rbp, [rsp+50h]
0x18003c668  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18003c66c  mov     rax, cs:__security_cookie
0x18003c673  xor     rax, rsp
0x18003c676  mov     [rbp+350h+var_30], rax
0x18003c67d  mov     rsi, r9
0x18003c680  mov     rbx, r8
0x18003c683  mov     [rbp+350h+var_2F8], r9
0x18003c687  mov     r14, [rsp+3A0h+arg_20]
0x18003c68f  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18003c694  mov     ecx, [rax]
0x18003c696  cmp     ecx, 4
0x18003c699  jbe     short loc_18003C6B7
0x18003c69b  mov     qword ptr [rbp+350h+var_348], rsi
0x18003c69f  lea     rcx, [rbp+350h+var_348]
0x18003c6a3  mov     [rsp+3A0h+ReturnLength], rcx; int
0x18003c6a8  lea     rdx, byte_180128E6F
0x18003c6af  mov     rcx, rax
0x18003c6b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18003c6b7  xor     edx, edx; Val
0x18003c6b9  mov     r8d, 1A0h; Size
0x18003c6bf  lea     rcx, [rbp+350h+var_290]; void *
0x18003c6c6  call    memset_0
0x18003c6cb  xor     r15d, r15d
0x18003c6ce  mov     [rbp+350h+TokenHandle], r15
0x18003c6d2  mov     [rbp+350h+var_324], r15d
0x18003c6d6  mov     [rbp+350h+var_320], r15d
0x18003c6da  mov     [rbp+350h+var_340], r15
0x18003c6de  mov     [rbp+350h+var_318], r15
0x18003c6e2  mov     [rbp+350h+var_330], r15
0x18003c6e6  mov     [rbp+350h+hExistingToken], r15
0x18003c6ea  mov     [rbp+350h+var_334], r15d
0x18003c6ee  mov     [rbp+350h+TokenInformation], r15d
0x18003c6f2  mov     [rbp+350h+var_328], r15d
0x18003c6f6  mov     [rbp+350h+var_338], r15d
0x18003c6fa  mov     [rbp+350h+var_350], r15b
0x18003c6fe  mov     [rbp+350h+var_31C], r15d
0x18003c702  mov     [rbp+350h+var_2F0], r15
0x18003c706  xor     edx, edx; Val
0x18003c708  lea     r8d, [r15+50h]; Size
0x18003c70c  lea     rcx, [rbp+350h+var_2E8]; void *
0x18003c710  call    memset_0
0x18003c715  lea     r8, [rbp+350h+var_290]; struct _BASIC_CALLER_INFORMATION *
0x18003c71c  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x18003c721  mov     rcx, [rsp+3A8h]; this
0x18003c729  test    eax, eax
0x18003c72b  js      loc_18003CA85
0x18003c731  lea     r8, dword_1801135EC; struct _CALLER_RESTRICTIONS *
0x18003c738  lea     rdx, [rbp+350h+var_290]; struct _BASIC_CALLER_INFORMATION *
0x18003c73f  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x18003c744  lea     rdx, [rbp+350h+var_350]
0x18003c748  mov     rcx, rbx
0x18003c74b  call    cs:__imp_RtlCheckSandboxedToken
0x18003c751  mov     rcx, [rsp+3A8h]; this
0x18003c759  test    eax, eax
0x18003c75b  js      loc_18003CA99
0x18003c761  cmp     [rbp+350h+var_350], r15b
0x18003c765  setnz   al
0x18003c768  mov     rcx, [rsp+3A8h]; this
0x18003c770  test    al, al
0x18003c772  jnz     loc_18003CAAD
0x18003c778  lea     rax, [rbp+350h+var_328]
0x18003c77c  mov     [rsp+3A0h+ReturnLength], rax; int
0x18003c781  mov     r9d, 4; TokenInformationLength
0x18003c787  lea     r8, [rbp+350h+TokenInformation]; TokenInformation
0x18003c78b  lea     edx, [r9+8]; TokenInformationClass
0x18003c78f  mov     rcx, rbx; TokenHandle
0x18003c792  call    cs:__imp_GetTokenInformation
0x18003c798  mov     rcx, [rsp+3A8h]; this
0x18003c7a0  test    eax, eax
0x18003c7a2  jz      loc_18003CAC4
0x18003c7a8  lea     rdx, [rbp+350h+TokenHandle]; phNewToken
0x18003c7ac  mov     ecx, [rbp+350h+TokenInformation]; SessionId
0x18003c7af  call    ?_InternalQueryUserToken@@YAJKPEAPEAX@Z; _InternalQueryUserToken(ulong,void * *)
0x18003c7b4  mov     rcx, [rsp+3A8h]; this
0x18003c7bc  test    eax, eax
0x18003c7be  js      loc_18003CAD5
0x18003c7c4  lea     rax, [rbp+350h+var_324]
0x18003c7c8  mov     [rsp+3A0h+ReturnLength], rax; ReturnLength
0x18003c7cd  mov     edi, 54h ; 'T'
0x18003c7d2  mov     r9d, edi; TokenInformationLength
0x18003c7d5  lea     r8, [rbp+350h+Sid1]; TokenInformation
0x18003c7dc  lea     edx, [rdi-53h]; TokenInformationClass
0x18003c7df  mov     rcx, rbx; TokenHandle
0x18003c7e2  call    cs:__imp_GetTokenInformation
0x18003c7e8  mov     rcx, [rsp+3A8h]; this
0x18003c7f0  test    eax, eax
0x18003c7f2  jz      loc_18003CAE9
0x18003c7f8  lea     rax, [rbp+350h+var_320]
0x18003c7fc  mov     [rsp+3A0h+ReturnLength], rax; int
0x18003c801  mov     r9d, edi; TokenInformationLength
0x18003c804  lea     r8, [rbp+350h+Sid2]; TokenInformation
0x18003c80b  mov     edx, 1; TokenInformationClass
0x18003c810  mov     rcx, [rbp+350h+TokenHandle]; TokenHandle
0x18003c814  call    cs:__imp_GetTokenInformation
0x18003c81a  mov     rcx, [rsp+3A8h]; this
0x18003c822  test    eax, eax
0x18003c824  jz      loc_18003CAFA
0x18003c82a  mov     rbx, [rsp+3A8h]
0x18003c832  mov     rdx, [rbp+350h+Sid2]; Sid2
0x18003c839  mov     rcx, [rbp+350h+Sid1]; Sid1
0x18003c840  call    cs:__imp_RtlEqualSid
0x18003c846  test    al, al
0x18003c848  jz      loc_18003CB0B
0x18003c84e  lea     rcx, [rbp+350h+var_318]
0x18003c852  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x18003c857  mov     rcx, [rsp+3A8h]; this
0x18003c85f  test    eax, eax
0x18003c861  js      loc_18003CB25
0x18003c867  mov     rdi, [rbp+350h+var_318]
0x18003c86b  mov     rax, [rdi]
0x18003c86e  mov     rbx, [rax+0A0h]
0x18003c875  lea     rcx, [rbp+350h+var_340]
0x18003c879  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c87e  lea     r8, [rbp+350h+var_340]
0x18003c882  mov     rdx, rsi
0x18003c885  mov     rcx, rdi
0x18003c888  mov     rax, rbx
0x18003c88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c890  mov     rcx, [rsp+3A8h]; this
0x18003c898  test    eax, eax
0x18003c89a  js      loc_18003CB39
0x18003c8a0  mov     rcx, [rsp+3A8h]; this
0x18003c8a8  cmp     [rbp+350h+var_340], r15
0x18003c8ac  jz      loc_18003CB4D
0x18003c8b2  lea     rdx, [rbp+350h+var_330]
0x18003c8b6  lea     rcx, [rbp+350h+var_340]
0x18003c8ba  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18003c8bf  mov     rcx, [rsp+3A8h]; this
0x18003c8c7  test    eax, eax
0x18003c8c9  js      loc_18003CB64
0x18003c8cf  mov     rcx, [rbp+350h+var_330]
0x18003c8d3  mov     rax, [rcx]
0x18003c8d6  lea     rdx, [rbp+350h+var_338]
0x18003c8da  mov     rax, [rax+60h]
0x18003c8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8e3  mov     rcx, [rsp+3A8h]; this
0x18003c8eb  test    eax, eax
0x18003c8ed  js      loc_18003CB78
0x18003c8f3  mov     eax, [rbp+350h+TokenInformation]
0x18003c8f6  cmp     [rbp+350h+var_338], eax
0x18003c8f9  setnz   al
0x18003c8fc  mov     rcx, [rsp+3A8h]; this
0x18003c904  test    al, al
0x18003c906  jnz     loc_18003CB8C
0x18003c90c  mov     rcx, [rbp+350h+var_340]
0x18003c910  mov     rax, [rcx]
0x18003c913  lea     rdx, [rbp+350h+var_334]
0x18003c917  mov     rax, [rax+38h]
0x18003c91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c920  mov     rcx, [rsp+3A8h]; this
0x18003c928  test    eax, eax
0x18003c92a  js      loc_18003CBA3
0x18003c930  cmp     [rbp+350h+var_334], r15d
0x18003c934  setz    al
0x18003c937  mov     rcx, [rsp+3A8h]; this
0x18003c93f  test    al, al
0x18003c941  jnz     loc_18003CBB7
0x18003c947  mov     rcx, [rbp+350h+var_330]
0x18003c94b  mov     rax, [rcx]
0x18003c94e  lea     rdx, [rbp+350h+hExistingToken]
0x18003c952  mov     rax, [rax+50h]
0x18003c956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c95b  mov     rcx, [rsp+3A8h]; this
0x18003c963  test    eax, eax
0x18003c965  js      loc_18003CBCE
0x18003c96b  mov     rcx, [rbp+350h+hExistingToken]; hExistingToken
0x18003c96f  test    rcx, rcx
0x18003c972  setz    al
0x18003c975  mov     r10, [rsp+3A8h]
0x18003c97d  test    al, al
0x18003c97f  jnz     loc_18003CBE2
0x18003c985  mov     [rsp+3A0h+phNewToken], r14; phNewToken
0x18003c98a  mov     r9d, 2; ImpersonationLevel
0x18003c990  mov     dword ptr [rsp+3A0h+ReturnLength], r9d; TokenType
0x18003c995  xor     r8d, r8d; lpTokenAttributes
0x18003c998  mov     edx, 80040004h; dwDesiredAccess
0x18003c99d  call    cs:__imp_DuplicateTokenEx
0x18003c9a3  mov     rcx, [rsp+3A8h]; this
0x18003c9ab  test    eax, eax
0x18003c9ad  jz      loc_18003CBFC
0x18003c9b3  lea     rax, [rbp+350h+var_31C]
0x18003c9b7  mov     [rsp+3A0h+ReturnLength], rax; int
0x18003c9bc  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18003c9c2  lea     r8, [rbp+350h+var_2F0]; TokenInformation
0x18003c9c6  lea     edx, [r9-57h]; TokenInformationClass
0x18003c9ca  mov     rcx, [r14]; TokenHandle
0x18003c9cd  call    cs:__imp_GetTokenInformation
0x18003c9d3  mov     rcx, [rsp+3A8h]; this
0x18003c9db  test    eax, eax
0x18003c9dd  jz      loc_18003CC0D
0x18003c9e3  mov     r8, [rbp+350h+var_2F0]; void *
0x18003c9e7  mov     rcx, [r14]; handle
0x18003c9ea  call    ?GiveTokenUserAdditionalAccess@@YAJPEAXK0@Z; GiveTokenUserAdditionalAccess(void *,ulong,void *)
0x18003c9ef  mov     rcx, [rsp+3A8h]; this
0x18003c9f7  test    eax, eax
0x18003c9f9  js      loc_18003CC1E
0x18003c9ff  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18003ca04  mov     ecx, [rax]
0x18003ca06  cmp     ecx, 4
0x18003ca09  jbe     short loc_18003CA3B
0x18003ca0b  mov     [rbp+350h+var_348], r15d
0x18003ca0f  mov     [rbp+350h+var_310], rsi
0x18003ca13  lea     rcx, [rbp+350h+var_348]
0x18003ca17  mov     [rsp+3A0h+phNewToken], rcx
0x18003ca1c  lea     rcx, [rbp+350h+var_310]
0x18003ca20  mov     [rsp+3A0h+ReturnLength], rcx
0x18003ca25  xor     r9d, r9d
0x18003ca28  xor     r8d, r8d
0x18003ca2b  lea     rdx, word_180128E1E
0x18003ca32  mov     rcx, rax
0x18003ca35  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003ca3a  nop
0x18003ca3b  lea     rcx, [rbp+350h+var_330]
0x18003ca3f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003ca44  nop
0x18003ca45  lea     rcx, [rbp+350h+var_318]
0x18003ca49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ca4e  nop
0x18003ca4f  lea     rcx, [rbp+350h+var_340]
0x18003ca53  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003ca58  xor     eax, eax
0x18003ca5a  jmp     short loc_18003CA5F
0x18003ca5c  mov     eax, [rbp+350h+var_348]
0x18003ca5f  mov     rcx, [rbp+350h+var_30]
0x18003ca66  xor     rcx, rsp; StackCookie
0x18003ca69  call    __security_check_cookie
0x18003ca6e  mov     rbx, [rsp+3A0h+arg_0]
0x18003ca76  add     rsp, 380h
0x18003ca7d  pop     r15
0x18003ca7f  pop     r14
0x18003ca81  pop     rdi
0x18003ca82  pop     rsi
0x18003ca83  pop     rbp
0x18003ca84  retn
0x18003ca85  mov     r9d, eax; char *
0x18003ca88  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003ca8f  mov     edx, 0C93h; void *
0x18003ca94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ca99  mov     r9d, eax; char *
0x18003ca9c  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003caa3  mov     edx, 0C99h; void *
0x18003caa8  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18003caad  mov     r9d, 80070005h; char *
0x18003cab3  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003caba  mov     edx, 0C9Ah; void *
0x18003cabf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cac4  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cacb  mov     edx, 0C9Dh; void *
0x18003cad0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003cad5  mov     r9d, eax; char *
0x18003cad8  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cadf  mov     edx, 0C9Eh; void *
0x18003cae4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cae9  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003caf0  mov     edx, 0C9Fh; void *
0x18003caf5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003cafa  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb01  mov     edx, 0CA0h; void *
0x18003cb06  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003cb0b  mov     r9d, 80070005h; char *
0x18003cb11  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb18  mov     edx, 0CA1h; void *
0x18003cb1d  mov     rcx, rbx; this
0x18003cb20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb25  mov     r9d, eax; char *
0x18003cb28  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb2f  mov     edx, 0CA7h; void *
0x18003cb34  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb39  mov     r9d, eax; char *
0x18003cb3c  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb43  mov     edx, 0CA8h; void *
0x18003cb48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb4d  mov     r9d, 80070520h; char *
0x18003cb53  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb5a  mov     edx, 0CA9h; void *
0x18003cb5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb64  mov     r9d, eax; char *
0x18003cb67  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb6e  mov     edx, 0CACh; void *
0x18003cb73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb78  mov     r9d, eax; char *
0x18003cb7b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb82  mov     edx, 0CADh; void *
0x18003cb87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cb8c  mov     r9d, 80070520h; char *
0x18003cb92  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cb99  mov     edx, 0CAEh; void *
0x18003cb9e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003cba3  mov     r9d, eax; char *
0x18003cba6  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x18003cbad  mov     edx, 0CB0h; void *
0x18003cbb2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
