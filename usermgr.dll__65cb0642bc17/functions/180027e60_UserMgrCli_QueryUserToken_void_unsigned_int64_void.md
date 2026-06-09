# UserMgrCli::QueryUserToken(void *,unsigned __int64,void * *)

- ea: `0x180027e60`
- end: `0x1800285f0`
- name: `?QueryUserToken@UserMgrCli@@QEAAJPEAX_KPEAPEAX@Z`
- size: `1936`
- prototype: `int(UserMgrCli *__hidden this, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027e40`

## callees

- `0x1800018c4`
- `0x180009af0`
- `0x18000acdc`
- `0x18000ad00`
- `0x18000cd30`
- `0x180027e60`
- `0x18004e58c`
- `0x18006c318`
- `0x18006f1c9`
- `0x1800b6ac4`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002827a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002827a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180027eb5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800282aa`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180027eb5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800282aa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180027f56`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002832d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180027f56`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002832d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002802d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028444`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002802d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028444`

## string_xrefs

- `0x1800284cd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800284e4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800284fb`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028512`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028526`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18002853a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18002854e`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028562`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028576`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18002858d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800285a1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800285b5`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800285cc`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800285dd`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UserMgrCli::QueryUserToken(UserMgrCli *this, void *a2, unsigned __int64 a3, void **a4)
{
  unsigned __int64 v4; // rbp
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  void *v9; // rdx
  UserMgrCli *v10; // rcx
  int ExtendedCallerInformation; // eax
  int v13; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, unsigned __int64, unsigned __int64); // rdi
  __int64 v16; // rdx
  int v17; // eax
  struct Windows::System::IUser *v18; // rcx
  int DefaultAccountUser; // eax
  int valid; // eax
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, GUID *, unsigned __int64); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, unsigned __int64); // rdi
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  void *v27; // r10
  TOKEN_TYPE v28; // eax
  SECURITY_IMPERSONATION_LEVEL v29; // r9d
  const char *v30; // r9
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 result; // rax
  void *v37; // rdx
  UserMgrCli *v38; // rcx
  const struct _tlgProvider_t *v39; // rax
  int v40; // ebx
  wil *v41; // rcx
  int v42; // r8d
  int v43; // r9d
  ULONG UserDataCount; // [rsp+20h] [rbp-40h]
  WINBOOL fPending; // [rsp+60h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+2E8h]

  v4 = (unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = a3;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) = 0;
  if ( InitOnceBeginInitialize(
         &`UserMgrUserModelTelemetry::Instance'::`2'::wrapper,
         0,
         (PBOOL)((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL),
         (LPVOID *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8))
    && *(_DWORD *)v4 )
  {
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = &qword_180147BD0;
    qword_180147BD8 = 0;
    byte_180147BE0 = 0;
    dword_180147BE4 = 0;
    qword_180147BD0 = (__int64)&UserMgrUserModelTelemetry::`vftable';
    CallbackContext = &`UserMgrUserModelTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_720b04dfc33336bd43e851a7c42b71cc_::_lambda_invoker_cdecl_);
    qword_180147BD8 = (__int64)CallbackContext;
    byte_180147BE0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180147BE4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180147BD0 + 8))(&qword_180147BD0);
    InitOnceComplete(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &qword_180147BD0);
  }
  v7 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 8LL);
  if ( *(_DWORD *)v7 > 5u )
  {
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a3;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x260) = ((unsigned __int64)&fPending
                                                                                & 0xFFFFFFFFFFFFFFE0uLL)
                                                                               + 8;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x268) = 8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 184549376;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x3C) = 5;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    v8 = *(unsigned __int16 **)(v7 + 8);
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x240) = v8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x248) = *v8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x24C) = 2;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x250) = &dword_18012A3FC;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x258) = 37;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x25C) = 1;
    *(_DWORD *)v4 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(
      *(_QWORD *)(v7 + 32),
      (PCEVENT_DESCRIPTOR)(v4 + 56),
      0,
      0,
      3u,
      (PEVENT_DATA_DESCRIPTOR)(v4 + 576));
  }
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  memset_0((void *)(v4 + 128), 0, 0x1C0u);
  try
  {
    ExtendedCallerInformation = UserMgrCli::GetExtendedCallerInformation(
                                  v10,
                                  v9,
                                  (struct _EXTENDED_CALLER_INFORMATION *)(v4 + 128));
    if ( ExtendedCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)ExtendedCallerInformation,
        UserDataCount);
    if ( !*(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x82)
      && !*(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x81) )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x929,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        UserDataCount);
    }
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        UserDataCount);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D0,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        UserDataCount);
    *a4 = 0;
    v13 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v4 + 48));
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D7,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v13,
        UserDataCount);
    v14 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
    v15 = *(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)v14 + 160LL);
    v16 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( v16 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v15(v14, a3, v4 + 16);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D9,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v17,
        UserDataCount);
    v18 = *(struct Windows::System::IUser **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( !v18 )
    {
      DefaultAccountUser = UserManagerTokenAndShellHandler::QueryDefaultAccountUser(
                             (UserManagerTokenAndShellHandler *)qword_180148188,
                             a3,
                             (struct Windows::System::IUser **)(v4 + 16));
      if ( DefaultAccountUser < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3DC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)DefaultAccountUser,
          UserDataCount);
      v18 = *(struct Windows::System::IUser **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    }
    valid = IsValidCallerForUser(v18, (struct _BASIC_CALLER_INFORMATION *)(v4 + 128));
    if ( valid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DE,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)valid,
        UserDataCount);
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    v21 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&fPending
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x10)
                                                              + 56LL))(
            *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10),
            v4 + 40);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E1,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v21,
        UserDataCount);
    if ( !*(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E2,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        UserDataCount);
    v22 = *(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64))(((unsigned __int64)&fPending
                                                                        & 0xFFFFFFFFFFFFFFE0uLL)
                                                                       + 0x10);
    v23 = **v22;
    v24 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    if ( v24 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v23(v22, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, v4 + 32);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E4,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v25,
        UserDataCount);
    v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&fPending
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x20)
                                                              + 80LL))(
            *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20),
            v4 + 72);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v26,
        UserDataCount);
    v27 = *(void **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x48);
    if ( !v27 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3E6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        UserDataCount);
    if ( *(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) )
    {
      v28 = TokenPrimary;
      v29 = SecurityImpersonation;
    }
    else
    {
      v28 = TokenImpersonation;
      v29 = SecurityIdentification;
    }
    if ( !DuplicateTokenEx(v27, 0, 0, v29, v28, a4) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v30);
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)v4 = 0;
    if ( InitOnceBeginInitialize(
           &`UserMgrUserModelTelemetry::Instance'::`2'::wrapper,
           0,
           (PBOOL)((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL),
           (LPVOID *)(v4 + 8))
      && *(_DWORD *)v4 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = &qword_180147BD0;
      qword_180147BD8 = 0;
      byte_180147BE0 = 0;
      dword_180147BE4 = 0;
      qword_180147BD0 = (__int64)&UserMgrUserModelTelemetry::`vftable';
      CallbackContext = &`UserMgrUserModelTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_720b04dfc33336bd43e851a7c42b71cc_::_lambda_invoker_cdecl_);
      qword_180147BD8 = (__int64)CallbackContext;
      byte_180147BE0 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_180147BE4 = 1;
      (*(void (__fastcall **)(__int64 *))(qword_180147BD0 + 8))(&qword_180147BD0);
      InitOnceComplete(&`UserMgrUserModelTelemetry::Instance'::`2'::wrapper, 0, &qword_180147BD0);
    }
    v31 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 8LL);
    if ( *(_DWORD *)v31 > 5u )
    {
      *(_DWORD *)v4 = 0;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = *(_DWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x88);
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1C) = *(_DWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x84);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = a3;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x290) = (unsigned __int64)&fPending
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x298) = 4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x280) = ((unsigned __int64)&fPending
                                                                                  & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                 + 24;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x288) = 4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x270) = ((unsigned __int64)&fPending
                                                                                  & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                 + 28;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x278) = 4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x260) = ((unsigned __int64)&fPending
                                                                                  & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                 + 56;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x268) = 8;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 184549376;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x5C) = 5;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
      v32 = *(unsigned __int16 **)(v31 + 8);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x240) = v32;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x248) = *v32;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x24C) = 2;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x250) = byte_18012A33D;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x258) = 74;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x25C) = 1;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = (unsigned int)&TraceLoggingMetadataEnd
                                                                             - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(
        *(_QWORD *)(v31 + 32),
        (PCEVENT_DESCRIPTOR)(v4 + 88),
        0,
        0,
        6u,
        (PEVENT_DATA_DESCRIPTOR)(v4 + 576));
    }
    v33 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    if ( v33 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v34 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
    if ( v34 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( v35 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    result = 0;
  }
  catch ( ... )
  {
    memset_0((void *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 128), 0, 0x1C0u);
    UserMgrCli::GetExtendedCallerInformation(
      v38,
      v37,
      (struct _EXTENDED_CALLER_INFORMATION *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 128));
    v39 = UserMgrUserModelTelemetry::Provider();
    v40 = (int)v39;
    v41 = (wil *)*(unsigned int *)v39;
    if ( (unsigned int)v41 > 5 )
    {
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v41);
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1C) = *(_DWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x88);
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = *(_DWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x84);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = *(_QWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x50);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v40,
        (unsigned int)&unk_18012A388,
        v42,
        v43,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 56,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 24,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 28,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    }
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v41);
    return *(unsigned int *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
  }
  return result;
}

```

## disassembly

```asm
0x180027e60  mov     [rsp-8+arg_0], rbx
0x180027e65  push    rbp
0x180027e66  push    rsi
0x180027e67  push    rdi
0x180027e68  push    r12
0x180027e6a  push    r13
0x180027e6c  push    r14
0x180027e6e  push    r15
0x180027e70  sub     rsp, 310h
0x180027e77  lea     rbp, [rsp+60h]
0x180027e7c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180027e80  mov     rax, cs:__security_cookie
0x180027e87  xor     rax, rsp
0x180027e8a  mov     [rbp+2E0h+var_40], rax
0x180027e91  mov     r15, r9
0x180027e94  mov     r14, r8
0x180027e97  mov     [rbp+2E0h+var_290], r8
0x180027e9b  xor     edi, edi
0x180027e9d  mov     [rbp+2E0h+Context], rdi
0x180027ea1  mov     [rbp+2E0h+fPending], edi
0x180027ea4  lea     r9, [rbp+2E0h+Context]; lpContext
0x180027ea8  lea     r8, [rbp+2E0h+fPending]; fPending
0x180027eac  xor     edx, edx; dwFlags
0x180027eae  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180027eb5  call    cs:__imp_InitOnceBeginInitialize
0x180027ebb  test    eax, eax
0x180027ebd  jz      loc_180027F5E
0x180027ec3  cmp     [rbp+2E0h+fPending], edi
0x180027ec6  jz      loc_180027F5E
0x180027ecc  lea     rsi, qword_180147BD0
0x180027ed3  mov     [rbp+2E0h+Context], rsi
0x180027ed7  mov     cs:qword_180147BD8, rdi
0x180027ede  mov     cs:byte_180147BE0, dil
0x180027ee5  mov     cs:dword_180147BE4, edi
0x180027eeb  lea     r12, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180027ef2  mov     cs:qword_180147BD0, r12
0x180027ef9  lea     r13, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180027f00  mov     cs:CallbackContext, r13
0x180027f07  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x180027f0e  call    atexit
0x180027f13  mov     rcx, cs:CallbackContext; CallbackContext
0x180027f1a  mov     cs:qword_180147BD8, rcx
0x180027f21  mov     cs:byte_180147BE0, 1
0x180027f28  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180027f2d  mov     cs:dword_180147BE4, 1
0x180027f37  mov     rax, cs:qword_180147BD0
0x180027f3e  mov     rcx, rsi
0x180027f41  mov     rax, [rax+8]
0x180027f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f4a  mov     r8, rsi; lpContext
0x180027f4d  xor     edx, edx; dwFlags
0x180027f4f  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180027f56  call    cs:__imp_InitOnceComplete
0x180027f5c  jmp     short loc_180027F73
0x180027f5e  lea     rsi, qword_180147BD0
0x180027f65  lea     r12, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180027f6c  lea     r13, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180027f73  mov     rax, [rbp+2E0h+Context]
0x180027f77  mov     rcx, [rax+8]
0x180027f7b  mov     eax, [rcx]
0x180027f7d  cmp     eax, 5
0x180027f80  jbe     loc_180028033
0x180027f86  mov     [rbp+2E0h+Context], r14
0x180027f8a  lea     rax, [rbp+2E0h+Context]
0x180027f8e  mov     [rbp+2E0h+var_80], rax
0x180027f95  mov     [rbp+2E0h+var_78], 8
0x180027fa0  mov     dword ptr [rbp+2E0h+EventDescriptor.Id], 0B000000h
0x180027fa7  movzx   eax, cs:word_18012A3F2
0x180027fae  mov     dword ptr [rbp+2E0h+EventDescriptor.Level], eax
0x180027fb1  mov     [rbp+2E0h+EventDescriptor.Keyword], rdi
0x180027fb5  mov     rax, [rcx+8]
0x180027fb9  mov     [rbp+2E0h+var_A0.Ptr], rax
0x180027fc0  movzx   eax, word ptr [rax]
0x180027fc3  mov     [rbp+2E0h+var_A0.Size], eax
0x180027fc9  mov     dword ptr [rbp+2E0h+var_A0.0Ch], 2
0x180027fd3  lea     rax, dword_18012A3FC
0x180027fda  mov     [rbp+2E0h+var_90], rax
0x180027fe1  mov     [rbp+2E0h+var_88], 25h ; '%'
0x180027feb  mov     [rbp+2E0h+var_84], 1
0x180027ff5  lea     rax, _TraceLoggingMetadataEnd
0x180027ffc  lea     rbx, _TraceLoggingMetadata
0x180028003  sub     eax, ebx
0x180028005  mov     [rbp+2E0h+fPending], eax
0x180028008  mov     eax, [rbp+2E0h+fPending]
0x18002800b  lea     rax, [rbp+2E0h+var_A0]
0x180028012  mov     [rsp+340h+UserData], rax; UserData
0x180028017  mov     [rsp+340h+UserDataCount], 3; int
0x18002801f  xor     r9d, r9d; RelatedActivityId
0x180028022  xor     r8d, r8d; ActivityId
0x180028025  lea     rdx, [rbp+2E0h+EventDescriptor]; EventDescriptor
0x180028029  mov     rcx, [rcx+20h]; RegHandle
0x18002802d  call    cs:__imp_EventWriteTransfer
0x180028033  mov     [rbp+2E0h+var_2D0], rdi
0x180028037  mov     [rbp+2E0h+var_2B0], rdi
0x18002803b  mov     [rbp+2E0h+var_2C0], rdi
0x18002803f  mov     [rbp+2E0h+hExistingToken], rdi
0x180028043  xor     edx, edx; Val
0x180028045  mov     r8d, 1C0h; Size
0x18002804b  lea     rcx, [rbp+2E0h+var_260]; void *
0x180028052  call    memset_0
0x180028057  lea     r8, [rbp+2E0h+var_260]; struct _EXTENDED_CALLER_INFORMATION *
0x18002805e  call    ?GetExtendedCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_EXTENDED_CALLER_INFORMATION@@@Z; UserMgrCli::GetExtendedCallerInformation(void *,_EXTENDED_CALLER_INFORMATION *)
0x180028063  mov     rcx, [rsp+348h]; this
0x18002806b  test    eax, eax
0x18002806d  js      loc_1800284CA
0x180028073  cmp     [rbp+2E0h+var_25E], 0
0x18002807a  jnz     short loc_180028089
0x18002807c  cmp     [rbp+2E0h+var_25F], 0
0x180028083  jnz     short loc_180028089
0x180028085  mov     al, 1
0x180028087  jmp     short loc_18002808B
0x180028089  xor     al, al
0x18002808b  mov     rcx, [rsp+348h]; this
0x180028093  test    al, al
0x180028095  jnz     loc_1800284DE
0x18002809b  mov     rcx, [rsp+348h]; this
0x1800280a3  test    r14, r14
0x1800280a6  jz      loc_1800284F5
0x1800280ac  mov     rcx, [rsp+348h]; this
0x1800280b4  test    r15, r15
0x1800280b7  jz      loc_18002850C
0x1800280bd  mov     [r15], rdi
0x1800280c0  lea     rcx, [rbp+2E0h+var_2B0]
0x1800280c4  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x1800280c9  mov     rcx, [rsp+348h]; this
0x1800280d1  test    eax, eax
0x1800280d3  js      loc_180028523
0x1800280d9  mov     rbx, [rbp+2E0h+var_2B0]
0x1800280dd  mov     rax, [rbx]
0x1800280e0  mov     rdi, [rax+0A0h]
0x1800280e7  mov     rdx, [rbp+2E0h+var_2D0]
0x1800280eb  test    rdx, rdx
0x1800280ee  jz      short loc_180028108
0x1800280f0  mov     [rbp+2E0h+var_2D0], 0
0x1800280f8  mov     rcx, [rdx]
0x1800280fb  mov     rax, [rcx+10h]
0x1800280ff  mov     rcx, rdx
0x180028102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028107  nop
0x180028108  lea     r8, [rbp+2E0h+var_2D0]
0x18002810c  mov     rdx, r14
0x18002810f  mov     rcx, rbx
0x180028112  mov     rax, rdi
0x180028115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002811a  mov     rcx, [rsp+348h]; this
0x180028122  test    eax, eax
0x180028124  js      loc_180028537
0x18002812a  mov     rcx, [rbp+2E0h+var_2D0]
0x18002812e  test    rcx, rcx
0x180028131  jnz     short loc_18002815A
0x180028133  lea     r8, [rbp+2E0h+var_2D0]; struct Windows::System::IUser **
0x180028137  mov     rdx, r14; unsigned __int64
0x18002813a  mov     rcx, cs:qword_180148188; this
0x180028141  call    ?QueryDefaultAccountUser@UserManagerTokenAndShellHandler@@QEAAJ_KPEAPEAUIUser@System@Windows@@@Z; UserManagerTokenAndShellHandler::QueryDefaultAccountUser(unsigned __int64,Windows::System::IUser * *)
0x180028146  mov     rcx, [rsp+348h]; this
0x18002814e  test    eax, eax
0x180028150  js      loc_18002854B
0x180028156  mov     rcx, [rbp+2E0h+var_2D0]; struct Windows::System::IUser *
0x18002815a  lea     rdx, [rbp+2E0h+var_260]; struct _BASIC_CALLER_INFORMATION *
0x180028161  call    ?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z; IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)
0x180028166  mov     rcx, [rsp+348h]; this
0x18002816e  test    eax, eax
0x180028170  js      loc_18002855F
0x180028176  mov     [rbp+2E0h+var_2B8], 0
0x18002817d  mov     rcx, [rbp+2E0h+var_2D0]
0x180028181  mov     rax, [rcx]
0x180028184  lea     rdx, [rbp+2E0h+var_2B8]
0x180028188  mov     rax, [rax+38h]
0x18002818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028191  mov     rcx, [rsp+348h]; this
0x180028199  test    eax, eax
0x18002819b  js      loc_180028573
0x1800281a1  cmp     [rbp+2E0h+var_2B8], 0
0x1800281a5  setz    al
0x1800281a8  mov     rcx, [rsp+348h]; this
0x1800281b0  test    al, al
0x1800281b2  jnz     loc_180028587
0x1800281b8  mov     rbx, [rbp+2E0h+var_2D0]
0x1800281bc  mov     rax, [rbx]
0x1800281bf  mov     rdi, [rax]
0x1800281c2  mov     rdx, [rbp+2E0h+var_2C0]
0x1800281c6  test    rdx, rdx
0x1800281c9  jz      short loc_1800281E3
0x1800281cb  mov     [rbp+2E0h+var_2C0], 0
0x1800281d3  mov     rcx, [rdx]
0x1800281d6  mov     rax, [rcx+10h]
0x1800281da  mov     rcx, rdx
0x1800281dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e2  nop
0x1800281e3  lea     r8, [rbp+2E0h+var_2C0]
0x1800281e7  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x1800281ee  mov     rcx, rbx
0x1800281f1  mov     rax, rdi
0x1800281f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f9  nop
0x1800281fa  mov     rcx, [rsp+348h]; this
0x180028202  test    eax, eax
0x180028204  js      loc_18002859E
0x18002820a  mov     rcx, [rbp+2E0h+var_2C0]
0x18002820e  mov     rax, [rcx]
0x180028211  lea     rdx, [rbp+2E0h+hExistingToken]
0x180028215  mov     rax, [rax+50h]
0x180028219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002821e  mov     rcx, [rsp+348h]; this
0x180028226  test    eax, eax
0x180028228  js      loc_1800285B2
0x18002822e  mov     r10, [rbp+2E0h+hExistingToken]
0x180028232  test    r10, r10
0x180028235  setz    al
0x180028238  mov     rcx, [rsp+348h]; this
0x180028240  test    al, al
0x180028242  jnz     loc_1800285C6
0x180028248  cmp     [rbp+2E0h+var_260], 0
0x18002824f  jz      short loc_18002825E
0x180028251  mov     eax, 1
0x180028256  mov     r9d, 2
0x18002825c  jmp     short loc_180028269
0x18002825e  mov     eax, 2
0x180028263  mov     r9d, 1; ImpersonationLevel
0x180028269  mov     [rsp+340h+UserData], r15; phNewToken
0x18002826e  mov     [rsp+340h+UserDataCount], eax; TokenType
0x180028272  xor     r8d, r8d; lpTokenAttributes
0x180028275  xor     edx, edx; dwDesiredAccess
0x180028277  mov     rcx, r10; hExistingToken
0x18002827a  call    cs:__imp_DuplicateTokenEx
0x180028280  mov     rcx, [rsp+348h]; this
0x180028288  test    eax, eax
0x18002828a  jz      loc_1800285DD
0x180028290  xor     ebx, ebx
0x180028292  mov     [rbp+2E0h+Context], rbx
0x180028296  mov     [rbp+2E0h+fPending], ebx
0x180028299  lea     r9, [rbp+2E0h+Context]; lpContext
0x18002829d  lea     r8, [rbp+2E0h+fPending]; fPending
0x1800282a1  xor     edx, edx; dwFlags
0x1800282a3  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800282aa  call    cs:__imp_InitOnceBeginInitialize
0x1800282b0  test    eax, eax
0x1800282b2  jz      short loc_180028333
0x1800282b4  cmp     [rbp+2E0h+fPending], ebx
0x1800282b7  jz      short loc_180028333
0x1800282b9  mov     [rbp+2E0h+Context], rsi
0x1800282bd  mov     cs:qword_180147BD8, rbx
0x1800282c4  mov     cs:byte_180147BE0, bl
0x1800282ca  mov     cs:dword_180147BE4, ebx
0x1800282d0  mov     cs:qword_180147BD0, r12
0x1800282d7  mov     cs:CallbackContext, r13
0x1800282de  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x1800282e5  call    atexit
0x1800282ea  mov     rcx, cs:CallbackContext; CallbackContext
0x1800282f1  mov     cs:qword_180147BD8, rcx
0x1800282f8  mov     cs:byte_180147BE0, 1
0x1800282ff  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180028304  mov     cs:dword_180147BE4, 1
0x18002830e  mov     rax, cs:qword_180147BD0
0x180028315  mov     rcx, rsi
0x180028318  mov     rax, [rax+8]
0x18002831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028321  mov     r8, rsi; lpContext
0x180028324  xor     edx, edx; dwFlags
0x180028326  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x18002832d  call    cs:__imp_InitOnceComplete
0x180028333  mov     rax, [rbp+2E0h+Context]
0x180028337  mov     rcx, [rax+8]
0x18002833b  mov     eax, [rcx]
0x18002833d  cmp     eax, 5
0x180028340  jbe     loc_18002844B
0x180028346  mov     [rbp+2E0h+fPending], ebx
0x180028349  mov     eax, [rbp+2E0h+var_258]
0x18002834f  mov     [rbp+2E0h+var_2C8], eax
0x180028352  mov     eax, [rbp+2E0h+var_25C]
0x180028358  mov     [rbp+2E0h+var_2C4], eax
0x18002835b  mov     qword ptr [rbp+2E0h+EventDescriptor.Id], r14
0x18002835f  lea     rax, [rbp+2E0h+fPending]
0x180028363  mov     [rbp+2E0h+var_50], rax
0x18002836a  mov     [rbp+2E0h+var_48], 4
0x180028375  lea     rax, [rbp+2E0h+var_2C8]
0x180028379  mov     [rbp+2E0h+var_60], rax
0x180028380  mov     [rbp+2E0h+var_58], 4
0x18002838b  lea     rax, [rbp+2E0h+var_2C4]
0x18002838f  mov     [rbp+2E0h+var_70], rax
0x180028396  mov     [rbp+2E0h+var_68], 4
0x1800283a1  lea     rax, [rbp+2E0h+EventDescriptor]
0x1800283a5  mov     [rbp+2E0h+var_80], rax
0x1800283ac  mov     [rbp+2E0h+var_78], 8
0x1800283b7  mov     dword ptr [rbp+2E0h+var_288.Id], 0B000000h
0x1800283be  movzx   eax, cs:word_18012A333
0x1800283c5  mov     dword ptr [rbp+2E0h+var_288.Level], eax
0x1800283c8  mov     [rbp+2E0h+var_288.Keyword], rbx
0x1800283cc  mov     rax, [rcx+8]
0x1800283d0  mov     [rbp+2E0h+var_A0.Ptr], rax
0x1800283d7  movzx   eax, word ptr [rax]
0x1800283da  mov     [rbp+2E0h+var_A0.Size], eax
0x1800283e0  mov     dword ptr [rbp+2E0h+var_A0.0Ch], 2
0x1800283ea  lea     rax, byte_18012A33D
0x1800283f1  mov     [rbp+2E0h+var_90], rax
0x1800283f8  mov     [rbp+2E0h+var_88], 4Ah ; 'J'
0x180028402  mov     [rbp+2E0h+var_84], 1
0x18002840c  lea     rax, _TraceLoggingMetadataEnd
0x180028413  lea     rdx, _TraceLoggingMetadata
0x18002841a  sub     eax, edx
  ... truncated ...
```
