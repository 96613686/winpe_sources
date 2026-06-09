# UserMgrCli::GetStandardAccessImpersonationTokenForContext(void *,void *,unsigned __int64,void * *)

- ea: `0x1800b38ec`
- end: `0x1800b3ffa`
- name: `?GetStandardAccessImpersonationTokenForContext@UserMgrCli@@QEAAJPEAX0_KPEAPEAX@Z`
- size: `1806`
- prototype: `int(UserMgrCli *__hidden this, void *, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b5f30`

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
- `0x18004a338`
- `0x18004e4e8`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800b38ec`
- `0x1800dbe24`
- `0x1800dbed0`
- `0x1800dc080`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3a5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3aaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3ade`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3cdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3d55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3a5d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3aaf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3ade`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3cdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b3d55`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800b3c64`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800b3c64`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b3d25`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b3d25`
- `ntdll!RtlCheckSandboxedToken` at `0x1800b3a16`
- `ntdll!RtlCheckSandboxedToken` at `0x1800b3a16`

## string_xrefs

- `0x1800b3e18`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e2c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e40`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e57`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e68`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e7c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e8d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3e9e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3eb5`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3ec9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3edd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3ef4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f08`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f1c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f33`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f47`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f5e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f72`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f86`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3f97`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3fae`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3fc2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3fd3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b3fe7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserMgrCli::GetStandardAccessImpersonationTokenForContext(
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
  int BasicCallerInformation; // eax
  int v13; // eax
  const char *v14; // r9
  int UserToken; // eax
  const char *v16; // r9
  const char *v17; // r9
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, unsigned __int64); // rbx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const char *v27; // r9
  void *v28; // rcx
  const char *v29; // r9
  unsigned int v30; // edx
  const char *v31; // r9
  int v32; // eax
  const struct _tlgProvider_t *v33; // rax
  __int64 result; // rax
  const struct _tlgProvider_t *v35; // rax
  int v36; // ebx
  wil *v37; // rcx
  int ReturnLength; // [rsp+20h] [rbp-30h]
  int ReturnLengtha; // [rsp+20h] [rbp-30h]
  int ReturnLengthb; // [rsp+20h] [rbp-30h]
  int ReturnLengthc; // [rsp+20h] [rbp-30h]
  _BYTE v42[4]; // [rsp+50h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+3C8h] [rbp+378h]

  v5 = (unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = a4;
  v8 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v8 > 4u )
  {
    *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = a4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (_DWORD)v8,
      (unsigned int)&word_180128DCE,
      v9,
      v10,
      v5 + 16);
  }
  memset_0((void *)(v5 + 224), 0, 0x1A0u);
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C) = 0;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  *(_BYTE *)v5 = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2C) = 2;
  *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = 0;
  memset_0((void *)(v5 + 120), 0, 0x50u);
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled() )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD05,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80004001LL,
        ReturnLength);
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               retaddr,
                               v11,
                               (struct _BASIC_CALLER_INFORMATION *)(v5 + 224));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD11,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        ReturnLength);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v5 + 224),
      (const struct _CALLER_RESTRICTIONS *)&dword_1801135EC);
    v13 = RtlCheckSandboxedToken(a3, (unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xD17,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v13,
        ReturnLength);
    if ( *(_BYTE *)v5 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD18,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        ReturnLength);
    if ( !GetTokenInformation(a3, TokenSessionId, (LPVOID)(v5 + 8), 4u, (PDWORD)(v5 + 40)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD1B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v14);
    UserToken = _InternalQueryUserToken(
                  *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 8),
                  (PHANDLE)(v5 + 80));
    if ( UserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD1C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)UserToken,
        ReturnLengtha);
    if ( !GetTokenInformation(a3, TokenUser, (LPVOID)(v5 + 640), 0x54u, (PDWORD)(v5 + 72)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD1D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v16);
    if ( !GetTokenInformation(
            *(HANDLE *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50),
            TokenUser,
            (LPVOID)(v5 + 736),
            0x54u,
            (PDWORD)(v5 + 76)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD1E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v17);
    if ( !(unsigned int)LUAIsSameUserSid(*(HANDLE *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50), a3) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD20,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        ReturnLengthb);
    v18 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v5 + 56));
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD26,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v18,
        ReturnLengthb);
    v19 = *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
    v20 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64))(*(_QWORD *)v19 + 160LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 24);
    v21 = v20(v19, a4, v5 + 24);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD27,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v21,
        ReturnLengthb);
    if ( !*(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD28,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v22 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v5 + 24),
            (__int64 *)(v5 + 48));
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD2B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v22,
        ReturnLengthb);
    v23 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v42
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x30)
                                                              + 96LL))(
            *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            v5 + 32);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD2C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v23,
        ReturnLengthb);
    if ( *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) != *(_DWORD *)(((unsigned __int64)v42
                                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                          + 8) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD2D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v42
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x18)
                                                              + 56LL))(
            *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
            v5 + 36);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD2F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v24,
        ReturnLengthb);
    if ( !*(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x24) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD30,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    v25 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v42
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x30)
                                                              + 80LL))(
            *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            v5 + 88);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD31,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v25,
        ReturnLengthb);
    *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    if ( dword_1801481C8 == 3
      && (unsigned int)LUAIsShadowAdminEnabled(retaddr)
      && (*(_BYTE *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0)
       || IsWellKnownSid(*(PSID *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x158), WinLocalServiceSid))
      && (int)LUAIsElevatedToken(a3) >= 0
      && *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40)
      && *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
    {
      v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v42
                                                                               & 0xFFFFFFFFFFFFFFE0uLL)
                                                                              + 0x30)
                                                                + 176LL))(
              *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
              v5 + 88);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v26,
          ReturnLengthb);
      if ( !*(_BYTE *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0)
        && !GetTokenInformation(a3, TokenImpersonationLevel, (LPVOID)(v5 + 44), 4u, (PDWORD)(v5 + 40)) )
      {
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xD44,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          v27);
      }
    }
    v28 = *(void **)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
    if ( !v28 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD48,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        ReturnLengthb);
    if ( !DuplicateTokenEx(
            v28,
            0x80040004,
            0,
            *(SECURITY_IMPERSONATION_LEVEL *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x2C),
            TokenImpersonation,
            phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD4F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v29);
    if ( !GetTokenInformation(*phNewToken, TokenUser, (LPVOID)(v5 + 112), 0x58u, (PDWORD)(v5 + 4)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xD57,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v31);
    v32 = GiveTokenUserAdditionalAccess(
            *phNewToken,
            v30,
            *(void **)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x70));
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD5C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v32,
        ReturnLengthc);
    v33 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v33 > 4u )
    {
      *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v33,
        (unsigned int)byte_180128D0B,
        0,
        0,
        v5 + 64,
        v5 + 16);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 48);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v5 + 56);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v5 + 24);
    result = 0;
  }
  catch ( ... )
  {
    v35 = UserMgrUserModelTelemetry::Provider();
    v36 = (int)v35;
    v37 = (wil *)*(unsigned int *)v35;
    if ( (unsigned int)v37 > 4 )
    {
      *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v37);
      *(_QWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = *(_QWORD *)(((unsigned __int64)v42
                                                                                       & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                      + 0x60);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v36,
        (unsigned int)&dword_180128C84,
        0,
        0,
        ((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 56,
        ((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
    }
    *(_DWORD *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = wil::ResultFromCaughtException(v37);
    return *(unsigned int *)(((unsigned __int64)v42 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  }
  return result;
}

```

## disassembly

```asm
0x1800b38ec  mov     [rsp-8+arg_0], rbx
0x1800b38f1  mov     [rsp-8+arg_8], rsi
0x1800b38f6  push    rbp
0x1800b38f7  push    rdi
0x1800b38f8  push    r12
0x1800b38fa  push    r14
0x1800b38fc  push    r15
0x1800b38fe  sub     rsp, 3A0h
0x1800b3905  lea     rbp, [rsp+50h]
0x1800b390a  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800b390e  mov     rax, cs:__security_cookie
0x1800b3915  xor     rax, rsp
0x1800b3918  mov     [rbp+370h+var_30], rax
0x1800b391f  mov     r14, r9
0x1800b3922  mov     rsi, r8
0x1800b3925  mov     [rbp+370h+var_310], r9
0x1800b3929  mov     r15, [rsp+3C0h+arg_20]
0x1800b3931  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b3936  mov     ecx, [rax]
0x1800b3938  cmp     ecx, 4
0x1800b393b  jbe     short loc_1800B3959
0x1800b393d  mov     qword ptr [rbp+370h+var_360], r14
0x1800b3941  lea     rcx, [rbp+370h+var_360]
0x1800b3945  mov     [rsp+3C0h+ReturnLength], rcx; int
0x1800b394a  lea     rdx, word_180128DCE
0x1800b3951  mov     rcx, rax
0x1800b3954  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1800b3959  xor     edx, edx; Val
0x1800b395b  mov     r8d, 1A0h; Size
0x1800b3961  lea     rcx, [rbp+370h+var_290]; void *
0x1800b3968  call    memset_0
0x1800b396d  xor     r12d, r12d
0x1800b3970  mov     [rbp+370h+TokenHandle], r12
0x1800b3974  mov     [rbp+370h+var_328], r12d
0x1800b3978  mov     [rbp+370h+var_324], r12d
0x1800b397c  mov     [rbp+370h+var_358], r12
0x1800b3980  mov     [rbp+370h+var_338], r12
0x1800b3984  mov     [rbp+370h+var_340], r12
0x1800b3988  mov     [rbp+370h+hExistingToken], r12
0x1800b398c  mov     [rbp+370h+var_34C], r12d
0x1800b3990  mov     [rbp+370h+TokenInformation], r12d
0x1800b3994  mov     [rbp+370h+var_348], r12d
0x1800b3998  mov     [rbp+370h+var_350], r12d
0x1800b399c  mov     [rbp+370h+var_370], r12b
0x1800b39a0  mov     [rbp+370h+var_36C], r12d
0x1800b39a4  mov     [rbp+370h+ImpersonationLevel], 2
0x1800b39ab  mov     [rbp+370h+var_300], r12
0x1800b39af  xor     edx, edx; Val
0x1800b39b1  lea     r8d, [r12+50h]; Size
0x1800b39b6  lea     rcx, [rbp+370h+var_2F8]; void *
0x1800b39ba  call    memset_0
0x1800b39bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x1800b39c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x1800b39cb  test    al, al
0x1800b39cd  setz    al
0x1800b39d0  mov     rcx, [rsp+3C8h]; this
0x1800b39d8  test    al, al
0x1800b39da  jnz     loc_1800B3E12
0x1800b39e0  lea     r8, [rbp+370h+var_290]; struct _BASIC_CALLER_INFORMATION *
0x1800b39e7  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800b39ec  mov     rcx, [rsp+3C8h]; this
0x1800b39f4  test    eax, eax
0x1800b39f6  js      loc_1800B3E29
0x1800b39fc  lea     r8, dword_1801135EC; struct _CALLER_RESTRICTIONS *
0x1800b3a03  lea     rdx, [rbp+370h+var_290]; struct _BASIC_CALLER_INFORMATION *
0x1800b3a0a  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800b3a0f  lea     rdx, [rbp+370h+var_370]
0x1800b3a13  mov     rcx, rsi
0x1800b3a16  call    cs:__imp_RtlCheckSandboxedToken
0x1800b3a1c  mov     rcx, [rsp+3C8h]; this
0x1800b3a24  test    eax, eax
0x1800b3a26  js      loc_1800B3E3D
0x1800b3a2c  cmp     [rbp+370h+var_370], r12b
0x1800b3a30  setnz   al
0x1800b3a33  mov     rcx, [rsp+3C8h]; this
0x1800b3a3b  test    al, al
0x1800b3a3d  jnz     loc_1800B3E51
0x1800b3a43  lea     rax, [rbp+370h+var_348]
0x1800b3a47  mov     [rsp+3C0h+ReturnLength], rax; int
0x1800b3a4c  mov     r9d, 4; TokenInformationLength
0x1800b3a52  lea     r8, [rbp+370h+TokenInformation]; TokenInformation
0x1800b3a56  lea     edx, [r9+8]; TokenInformationClass
0x1800b3a5a  mov     rcx, rsi; TokenHandle
0x1800b3a5d  call    cs:__imp_GetTokenInformation
0x1800b3a63  mov     rcx, [rsp+3C8h]; this
0x1800b3a6b  test    eax, eax
0x1800b3a6d  jz      loc_1800B3E68
0x1800b3a73  lea     rdx, [rbp+370h+TokenHandle]; phNewToken
0x1800b3a77  mov     ecx, [rbp+370h+TokenInformation]; SessionId
0x1800b3a7a  call    ?_InternalQueryUserToken@@YAJKPEAPEAX@Z; _InternalQueryUserToken(ulong,void * *)
0x1800b3a7f  mov     rcx, [rsp+3C8h]; this
0x1800b3a87  test    eax, eax
0x1800b3a89  js      loc_1800B3E79
0x1800b3a8f  lea     rax, [rbp+370h+var_328]
0x1800b3a93  mov     [rsp+3C0h+ReturnLength], rax; ReturnLength
0x1800b3a98  mov     ebx, 54h ; 'T'
0x1800b3a9d  mov     r9d, ebx; TokenInformationLength
0x1800b3aa0  lea     r8, [rbp+370h+var_F0]; TokenInformation
0x1800b3aa7  lea     edi, [rbx-53h]
0x1800b3aaa  mov     edx, edi; TokenInformationClass
0x1800b3aac  mov     rcx, rsi; TokenHandle
0x1800b3aaf  call    cs:__imp_GetTokenInformation
0x1800b3ab5  mov     rcx, [rsp+3C8h]; this
0x1800b3abd  test    eax, eax
0x1800b3abf  jz      loc_1800B3E8D
0x1800b3ac5  lea     rax, [rbp+370h+var_324]
0x1800b3ac9  mov     [rsp+3C0h+ReturnLength], rax; int
0x1800b3ace  mov     r9d, ebx; TokenInformationLength
0x1800b3ad1  lea     r8, [rbp+370h+var_90]; TokenInformation
0x1800b3ad8  mov     edx, edi; TokenInformationClass
0x1800b3ada  mov     rcx, [rbp+370h+TokenHandle]; TokenHandle
0x1800b3ade  call    cs:__imp_GetTokenInformation
0x1800b3ae4  mov     rcx, [rsp+3C8h]; this
0x1800b3aec  test    eax, eax
0x1800b3aee  jz      loc_1800B3E9E
0x1800b3af4  mov     rdx, rsi; HANDLE
0x1800b3af7  mov     rcx, [rbp+370h+TokenHandle]; TokenHandle
0x1800b3afb  call    LUAIsSameUserSid
0x1800b3b00  mov     rcx, [rsp+3C8h]; this
0x1800b3b08  test    eax, eax
0x1800b3b0a  jz      loc_1800B3EAF
0x1800b3b10  lea     rcx, [rbp+370h+var_338]
0x1800b3b14  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x1800b3b19  mov     rcx, [rsp+3C8h]; this
0x1800b3b21  test    eax, eax
0x1800b3b23  js      loc_1800B3EC6
0x1800b3b29  mov     rdi, [rbp+370h+var_338]
0x1800b3b2d  mov     rax, [rdi]
0x1800b3b30  mov     rbx, [rax+0A0h]
0x1800b3b37  lea     rcx, [rbp+370h+var_358]
0x1800b3b3b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b3b40  lea     r8, [rbp+370h+var_358]
0x1800b3b44  mov     rdx, r14
0x1800b3b47  mov     rcx, rdi
0x1800b3b4a  mov     rax, rbx
0x1800b3b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b52  mov     rcx, [rsp+3C8h]; this
0x1800b3b5a  test    eax, eax
0x1800b3b5c  js      loc_1800B3EDA
0x1800b3b62  mov     rcx, [rsp+3C8h]; this
0x1800b3b6a  cmp     [rbp+370h+var_358], r12
0x1800b3b6e  jz      loc_1800B3EEE
0x1800b3b74  lea     rdx, [rbp+370h+var_340]
0x1800b3b78  lea     rcx, [rbp+370h+var_358]
0x1800b3b7c  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x1800b3b81  mov     rcx, [rsp+3C8h]; this
0x1800b3b89  test    eax, eax
0x1800b3b8b  js      loc_1800B3F05
0x1800b3b91  mov     rcx, [rbp+370h+var_340]
0x1800b3b95  mov     rax, [rcx]
0x1800b3b98  lea     rdx, [rbp+370h+var_350]
0x1800b3b9c  mov     rax, [rax+60h]
0x1800b3ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ba5  mov     rcx, [rsp+3C8h]; this
0x1800b3bad  test    eax, eax
0x1800b3baf  js      loc_1800B3F19
0x1800b3bb5  mov     eax, [rbp+370h+TokenInformation]
0x1800b3bb8  cmp     [rbp+370h+var_350], eax
0x1800b3bbb  setnz   al
0x1800b3bbe  mov     rcx, [rsp+3C8h]; this
0x1800b3bc6  test    al, al
0x1800b3bc8  jnz     loc_1800B3F2D
0x1800b3bce  mov     rcx, [rbp+370h+var_358]
0x1800b3bd2  mov     rax, [rcx]
0x1800b3bd5  lea     rdx, [rbp+370h+var_34C]
0x1800b3bd9  mov     rax, [rax+38h]
0x1800b3bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3be2  mov     rcx, [rsp+3C8h]; this
0x1800b3bea  test    eax, eax
0x1800b3bec  js      loc_1800B3F44
0x1800b3bf2  cmp     [rbp+370h+var_34C], r12d
0x1800b3bf6  setz    al
0x1800b3bf9  mov     rcx, [rsp+3C8h]; this
0x1800b3c01  test    al, al
0x1800b3c03  jnz     loc_1800B3F58
0x1800b3c09  mov     rcx, [rbp+370h+var_340]
0x1800b3c0d  mov     rax, [rcx]
0x1800b3c10  lea     rdx, [rbp+370h+hExistingToken]
0x1800b3c14  mov     rax, [rax+50h]
0x1800b3c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3c1d  mov     rcx, [rsp+3C8h]; this
0x1800b3c25  test    eax, eax
0x1800b3c27  js      loc_1800B3F6F
0x1800b3c2d  mov     dword ptr [rbp+370h+var_330], r12d
0x1800b3c31  mov     [rbp+370h+var_360], r12d
0x1800b3c35  cmp     cs:dword_1801481C8, 3
0x1800b3c3c  jnz     loc_1800B3CF2
0x1800b3c42  call    LUAIsShadowAdminEnabled
0x1800b3c47  test    eax, eax
0x1800b3c49  jz      loc_1800B3CF2
0x1800b3c4f  cmp     [rbp+370h+var_290], r12b
0x1800b3c56  jnz     short loc_1800B3C72
0x1800b3c58  mov     edx, 17h; WellKnownSidType
0x1800b3c5d  mov     rcx, [rbp+370h+pSid]; pSid
0x1800b3c64  call    cs:__imp_IsWellKnownSid
0x1800b3c6a  test    eax, eax
0x1800b3c6c  jz      loc_1800B3CF2
0x1800b3c72  lea     r8, [rbp+370h+var_360]
0x1800b3c76  lea     rdx, [rbp+370h+var_330]
0x1800b3c7a  mov     rcx, rsi; TokenHandle
0x1800b3c7d  call    LUAIsElevatedToken
0x1800b3c82  test    eax, eax
0x1800b3c84  js      short loc_1800B3CF2
0x1800b3c86  cmp     dword ptr [rbp+370h+var_330], r12d
0x1800b3c8a  jz      short loc_1800B3CF2
0x1800b3c8c  cmp     [rbp+370h+var_360], r12d
0x1800b3c90  jz      short loc_1800B3CF2
0x1800b3c92  mov     rcx, [rbp+370h+var_340]
0x1800b3c96  mov     rax, [rcx]
0x1800b3c99  lea     rdx, [rbp+370h+hExistingToken]
0x1800b3c9d  mov     rax, [rax+0B0h]
0x1800b3ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ca9  mov     rcx, [rsp+3C8h]; this
0x1800b3cb1  test    eax, eax
0x1800b3cb3  js      loc_1800B3F83
0x1800b3cb9  cmp     [rbp+370h+var_290], r12b
0x1800b3cc0  jnz     short loc_1800B3CF2
0x1800b3cc2  lea     rax, [rbp+370h+var_348]
0x1800b3cc6  mov     [rsp+3C0h+ReturnLength], rax; int
0x1800b3ccb  mov     r9d, 4; TokenInformationLength
0x1800b3cd1  lea     r8, [rbp+370h+ImpersonationLevel]; TokenInformation
0x1800b3cd5  lea     edx, [r9+5]; TokenInformationClass
0x1800b3cd9  mov     rcx, rsi; TokenHandle
0x1800b3cdc  call    cs:__imp_GetTokenInformation
0x1800b3ce2  mov     rcx, [rsp+3C8h]; this
0x1800b3cea  test    eax, eax
0x1800b3cec  jz      loc_1800B3F97
0x1800b3cf2  mov     rcx, [rbp+370h+hExistingToken]; hExistingToken
0x1800b3cf6  test    rcx, rcx
0x1800b3cf9  setz    al
0x1800b3cfc  mov     r10, [rsp+3C8h]
0x1800b3d04  test    al, al
0x1800b3d06  jnz     loc_1800B3FA8
0x1800b3d0c  mov     [rsp+3C0h+phNewToken], r15; phNewToken
0x1800b3d11  mov     dword ptr [rsp+3C0h+ReturnLength], 2; TokenType
0x1800b3d19  mov     r9d, [rbp+370h+ImpersonationLevel]; ImpersonationLevel
0x1800b3d1d  xor     r8d, r8d; lpTokenAttributes
0x1800b3d20  mov     edx, 80040004h; dwDesiredAccess
0x1800b3d25  call    cs:__imp_DuplicateTokenEx
0x1800b3d2b  mov     rcx, [rsp+3C8h]; this
0x1800b3d33  test    eax, eax
0x1800b3d35  jz      loc_1800B3FC2
0x1800b3d3b  lea     rax, [rbp+370h+var_36C]
0x1800b3d3f  mov     [rsp+3C0h+ReturnLength], rax; int
0x1800b3d44  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800b3d4a  lea     r8, [rbp+370h+var_300]; TokenInformation
0x1800b3d4e  lea     edx, [r9-57h]; TokenInformationClass
0x1800b3d52  mov     rcx, [r15]; TokenHandle
0x1800b3d55  call    cs:__imp_GetTokenInformation
0x1800b3d5b  mov     rcx, [rsp+3C8h]; this
0x1800b3d63  test    eax, eax
0x1800b3d65  jz      loc_1800B3FD3
0x1800b3d6b  mov     r8, [rbp+370h+var_300]; void *
0x1800b3d6f  mov     rcx, [r15]; handle
0x1800b3d72  call    ?GiveTokenUserAdditionalAccess@@YAJPEAXK0@Z; GiveTokenUserAdditionalAccess(void *,ulong,void *)
0x1800b3d77  mov     rcx, [rsp+3C8h]; this
0x1800b3d7f  test    eax, eax
0x1800b3d81  js      loc_1800B3FE4
0x1800b3d87  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b3d8c  mov     ecx, [rax]
0x1800b3d8e  cmp     ecx, 4
0x1800b3d91  jbe     short loc_1800B3DC3
0x1800b3d93  mov     [rbp+370h+var_360], r12d
0x1800b3d97  mov     [rbp+370h+var_330], r14
0x1800b3d9b  lea     rcx, [rbp+370h+var_360]
0x1800b3d9f  mov     [rsp+3C0h+phNewToken], rcx
0x1800b3da4  lea     rcx, [rbp+370h+var_330]
0x1800b3da8  mov     [rsp+3C0h+ReturnLength], rcx
0x1800b3dad  xor     r9d, r9d
0x1800b3db0  xor     r8d, r8d
0x1800b3db3  lea     rdx, byte_180128D0B
0x1800b3dba  mov     rcx, rax
0x1800b3dbd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800b3dc2  nop
0x1800b3dc3  lea     rcx, [rbp+370h+var_340]
0x1800b3dc7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b3dcc  nop
0x1800b3dcd  lea     rcx, [rbp+370h+var_338]
0x1800b3dd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3dd6  nop
0x1800b3dd7  lea     rcx, [rbp+370h+var_358]
0x1800b3ddb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b3de0  xor     eax, eax
0x1800b3de2  jmp     short loc_1800B3DE7
0x1800b3de4  mov     eax, [rbp+370h+var_36C]
0x1800b3de7  mov     rcx, [rbp+370h+var_30]
0x1800b3dee  xor     rcx, rsp; StackCookie
0x1800b3df1  call    __security_check_cookie
0x1800b3df6  lea     r11, [rsp+3C0h+var_20]
0x1800b3dfe  mov     rbx, [r11+30h]
0x1800b3e02  mov     rsi, [r11+38h]
0x1800b3e06  mov     rsp, r11
0x1800b3e09  pop     r15
0x1800b3e0b  pop     r14
0x1800b3e0d  pop     r12
0x1800b3e0f  pop     rdi
0x1800b3e10  pop     rbp
0x1800b3e11  retn
0x1800b3e12  mov     r9d, 80004001h; char *
0x1800b3e18  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
  ... truncated ...
```
