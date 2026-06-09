# UserMgrCli::QueryUserContext(void *,void *,unsigned __int64 *)

- ea: `0x180024870`
- end: `0x180024f56`
- name: `?QueryUserContext@UserMgrCli@@QEAAJPEAX0PEA_K@Z`
- size: `1766`
- prototype: `int(UserMgrCli *__hidden this, void *, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024850`

## callees

- `0x1800018c4`
- `0x180007ef4`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c350`
- `0x18000cd30`
- `0x180024870`
- `0x18006c318`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800248c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024c5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800248c1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024c5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024962`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024ce3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024962`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180024ce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ac6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ad9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024a1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024dcb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024a1f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024dcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024de0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024de0`

## string_xrefs

- `0x180024e69`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024e80`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024e9a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024eb1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024ec5`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024ed9`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024ef0`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024f04`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024f1b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024f2f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180024f43`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UserMgrCli::QueryUserContext(UserMgrCli *this, void *a2, void *a3, unsigned __int64 *a4)
{
  unsigned __int64 v4; // rbp
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  void *v9; // rdx
  UserMgrCli *v10; // rcx
  int BasicCallerInformation; // eax
  char v12; // al
  char *v15; // rdi
  DWORD LastError; // ebx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, void *, unsigned __int64); // rsi
  __int64 v20; // rdx
  int v21; // eax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rcx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, unsigned __int64); // rbx
  __int64 (__fastcall *v27)(_QWORD, GUID *, unsigned __int64); // rdi
  __int64 v28; // rdx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  char *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 result; // rax
  const struct _tlgProvider_t *v38; // rax
  int v39; // ebx
  wil *v40; // rcx
  int v41; // r8d
  int v42; // r9d
  int UserDataCount; // [rsp+20h] [rbp-30h]
  int UserDataCounta; // [rsp+20h] [rbp-30h]
  WINBOOL fPending; // [rsp+50h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+288h]

  v4 = (unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL;
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
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 184549376;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x34) = 5;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    v8 = *(unsigned __int16 **)(v7 + 8);
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E0) = v8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E8) = *v8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1EC) = 2;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F0) = &word_180129B56;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F8) = 26;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1FC) = 1;
    *(_DWORD *)v4 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(
      *(_QWORD *)(v7 + 32),
      (PCEVENT_DESCRIPTOR)(v4 + 48),
      0,
      0,
      2u,
      (PEVENT_DATA_DESCRIPTOR)(v4 + 480));
  }
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  memset_0((void *)(v4 + 64), 0, 0x1A0u);
  try
  {
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v10,
                               v9,
                               (struct _BASIC_CALLER_INFORMATION *)(v4 + 64));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        UserDataCount);
    v12 = *(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x41);
    if ( !*(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x42) && !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x929,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        UserDataCount);
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x662,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        UserDataCount);
    if ( v12 && a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        UserDataCount);
    if ( !a3 )
    {
      v15 = *(char **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v15);
        SetLastError(LastError);
      }
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
      GetCallerToken((PHANDLE)(v4 + 32));
      a3 = *(void **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    }
    *a4 = 0;
    v17 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v4 + 40));
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x66F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v17,
        UserDataCount);
    v18 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    v19 = *(__int64 (__fastcall **)(__int64, void *, unsigned __int64))(*(_QWORD *)v18 + 176LL);
    v20 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( v20 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v19(v18, a3, v4 + 16);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x671,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v21,
        UserDataCount);
    v24 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( v24 )
    {
      *(_DWORD *)v4 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v24 + 56LL))(
              v24,
              (unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v25,
          UserDataCount);
      if ( !*(_DWORD *)v4 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x800704DCLL,
          UserDataCount);
      v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64))(((unsigned __int64)&fPending
                                                                          & 0xFFFFFFFFFFFFFFE0uLL)
                                                                         + 0x10);
      v27 = **v26;
      v28 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      if ( v28 )
      {
        *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v27(v26, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, v4 + 24);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v29,
          UserDataCount);
      v30 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**(_QWORD **)(((unsigned __int64)&fPending
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                + 0x18)
                                                                  + 88LL))(
              *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
              a4);
      if ( v30 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v30,
          UserDataCount);
    }
    else if ( (int)UserManagerTokenAndShellHandler::QueryDefaultAccountUserContext(
                     (UserManagerTokenAndShellHandler *)qword_180148188,
                     a3,
                     v22,
                     v23,
                     a4) < 0 )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x675,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        UserDataCounta);
    }
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
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = *a4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x230) = (unsigned __int64)&fPending
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x238) = 4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x220) = ((unsigned __int64)&fPending
                                                                                  & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                 + 48;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x228) = 8;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E0) = 184549376;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E4) = 5;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E8) = 0;
      v32 = *(unsigned __int16 **)(v31 + 8);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x200) = v32;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x208) = *v32;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20C) = 2;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x210) = &dword_180129ACC;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x218) = 54;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x21C) = 1;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = (unsigned int)&TraceLoggingMetadataEnd
                                                                             - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(
        *(_QWORD *)(v31 + 32),
        (PCEVENT_DESCRIPTOR)(v4 + 480),
        0,
        0,
        4u,
        (PEVENT_DATA_DESCRIPTOR)(v4 + 512));
    }
    v33 = *(char **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v33);
    v34 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v34 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    if ( v35 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    v36 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
    if ( v36 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    result = 0;
  }
  catch ( ... )
  {
    v38 = UserMgrUserModelTelemetry::Provider();
    v39 = (int)v38;
    v40 = (wil *)*(unsigned int *)v38;
    if ( (unsigned int)v40 > 5 )
    {
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v40);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v39,
        (unsigned int)byte_180129B03,
        v41,
        v42,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    }
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v40);
    return *(unsigned int *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
  }
  return result;
}

```

## disassembly

```asm
0x180024870  mov     [rsp-8+arg_0], rbx
0x180024875  push    rbp
0x180024876  push    rsi
0x180024877  push    rdi
0x180024878  push    r12
0x18002487a  push    r13
0x18002487c  push    r14
0x18002487e  push    r15
0x180024880  sub     rsp, 2A0h
0x180024887  lea     rbp, [rsp+50h]
0x18002488c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180024890  mov     rax, cs:__security_cookie
0x180024897  xor     rax, rsp
0x18002489a  mov     [rbp+280h+var_40], rax
0x1800248a1  mov     r15, r9
0x1800248a4  mov     rbx, r8
0x1800248a7  xor     esi, esi
0x1800248a9  mov     [rbp+280h+Context], rsi
0x1800248ad  mov     [rbp+280h+fPending], esi
0x1800248b0  lea     r9, [rbp+280h+Context]; lpContext
0x1800248b4  lea     r8, [rbp+280h+fPending]; fPending
0x1800248b8  xor     edx, edx; dwFlags
0x1800248ba  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x1800248c1  call    cs:__imp_InitOnceBeginInitialize
0x1800248c7  test    eax, eax
0x1800248c9  jz      loc_18002496A
0x1800248cf  cmp     [rbp+280h+fPending], esi
0x1800248d2  jz      loc_18002496A
0x1800248d8  lea     r14, qword_180147BD0
0x1800248df  mov     [rbp+280h+Context], r14
0x1800248e3  mov     cs:qword_180147BD8, rsi
0x1800248ea  mov     cs:byte_180147BE0, sil
0x1800248f1  mov     cs:dword_180147BE4, esi
0x1800248f7  lea     r12, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x1800248fe  mov     cs:qword_180147BD0, r12
0x180024905  lea     r13, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002490c  mov     cs:CallbackContext, r13
0x180024913  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x18002491a  call    atexit
0x18002491f  mov     rcx, cs:CallbackContext; CallbackContext
0x180024926  mov     cs:qword_180147BD8, rcx
0x18002492d  mov     cs:byte_180147BE0, 1
0x180024934  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180024939  mov     cs:dword_180147BE4, 1
0x180024943  mov     rax, cs:qword_180147BD0
0x18002494a  mov     rcx, r14
0x18002494d  mov     rax, [rax+8]
0x180024951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024956  mov     r8, r14; lpContext
0x180024959  xor     edx, edx; dwFlags
0x18002495b  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180024962  call    cs:__imp_InitOnceComplete
0x180024968  jmp     short loc_18002497F
0x18002496a  lea     r14, qword_180147BD0
0x180024971  lea     r12, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180024978  lea     r13, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002497f  mov     rax, [rbp+280h+Context]
0x180024983  mov     rcx, [rax+8]
0x180024987  mov     eax, [rcx]
0x180024989  cmp     eax, 5
0x18002498c  jbe     loc_180024A25
0x180024992  mov     dword ptr [rbp+280h+EventDescriptor.Id], 0B000000h
0x180024999  movzx   eax, cs:word_180129B4C
0x1800249a0  mov     dword ptr [rbp+280h+EventDescriptor.Level], eax
0x1800249a3  mov     [rbp+280h+EventDescriptor.Keyword], rsi
0x1800249a7  mov     rax, [rcx+8]
0x1800249ab  mov     [rbp+280h+var_A0.Ptr], rax
0x1800249b2  movzx   eax, word ptr [rax]
0x1800249b5  mov     [rbp+280h+var_A0.Size], eax
0x1800249bb  mov     dword ptr [rbp+280h+var_A0.0Ch], 2
0x1800249c5  lea     rax, word_180129B56
0x1800249cc  mov     [rbp+280h+var_90], rax
0x1800249d3  mov     [rbp+280h+var_88], 1Ah
0x1800249dd  mov     [rbp+280h+var_84], 1
0x1800249e7  lea     rax, _TraceLoggingMetadataEnd
0x1800249ee  lea     rdi, _TraceLoggingMetadata
0x1800249f5  sub     eax, edi
0x1800249f7  mov     [rbp+280h+fPending], eax
0x1800249fa  mov     eax, [rbp+280h+fPending]
0x1800249fd  lea     rax, [rbp+280h+var_A0]
0x180024a04  mov     [rsp+2D0h+UserData], rax; UserData
0x180024a09  mov     [rsp+2D0h+UserDataCount], 2; int
0x180024a11  xor     r9d, r9d; RelatedActivityId
0x180024a14  xor     r8d, r8d; ActivityId
0x180024a17  lea     rdx, [rbp+280h+EventDescriptor]; EventDescriptor
0x180024a1b  mov     rcx, [rcx+20h]; RegHandle
0x180024a1f  call    cs:__imp_EventWriteTransfer
0x180024a25  mov     [rbp+280h+var_270], rsi
0x180024a29  mov     [rbp+280h+var_258], rsi
0x180024a2d  mov     [rbp+280h+var_268], rsi
0x180024a31  mov     [rbp+280h+hObject], rsi
0x180024a35  xor     edx, edx; Val
0x180024a37  mov     r8d, 1A0h; Size
0x180024a3d  lea     rcx, [rbp+280h+var_240]; void *
0x180024a41  call    memset_0
0x180024a46  lea     r8, [rbp+280h+var_240]; struct _BASIC_CALLER_INFORMATION *
0x180024a4a  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x180024a4f  mov     rcx, [rsp+2D8h]; this
0x180024a57  test    eax, eax
0x180024a59  js      loc_180024E66
0x180024a5f  movzx   eax, [rbp+280h+var_23F]
0x180024a63  cmp     [rbp+280h+var_23E], 0
0x180024a67  jnz     short loc_180024A71
0x180024a69  test    al, al
0x180024a6b  jnz     short loc_180024A71
0x180024a6d  mov     cl, 1
0x180024a6f  jmp     short loc_180024A73
0x180024a71  xor     cl, cl
0x180024a73  mov     r10, [rsp+2D8h]
0x180024a7b  test    cl, cl
0x180024a7d  jnz     loc_180024E7A
0x180024a83  mov     rcx, [rsp+2D8h]; this
0x180024a8b  test    r15, r15
0x180024a8e  jz      loc_180024E94
0x180024a94  test    al, al
0x180024a96  jz      short loc_180024AA1
0x180024a98  test    rbx, rbx
0x180024a9b  jz      short loc_180024AA1
0x180024a9d  mov     al, 1
0x180024a9f  jmp     short loc_180024AA3
0x180024aa1  xor     al, al
0x180024aa3  mov     rcx, [rsp+2D8h]; this
0x180024aab  test    al, al
0x180024aad  jnz     loc_180024EAB
0x180024ab3  test    rbx, rbx
0x180024ab6  jnz     short loc_180024AF0
0x180024ab8  mov     rdi, [rbp+280h+hObject]
0x180024abc  lea     rax, [rdi-1]
0x180024ac0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024ac4  ja      short loc_180024ADF
0x180024ac6  call    cs:__imp_GetLastError
0x180024acc  mov     ebx, eax
0x180024ace  mov     rcx, rdi; hObject
0x180024ad1  call    cs:__imp_CloseHandle
0x180024ad7  mov     ecx, ebx; dwErrCode
0x180024ad9  call    cs:__imp_SetLastError
0x180024adf  mov     [rbp+280h+hObject], rsi
0x180024ae3  lea     rcx, [rbp+280h+hObject]; phNewToken
0x180024ae7  call    ?GetCallerToken@@YAJPEAPEAX@Z; GetCallerToken(void * *)
0x180024aec  mov     rbx, [rbp+280h+hObject]
0x180024af0  mov     [r15], rsi
0x180024af3  lea     rcx, [rbp+280h+var_258]
0x180024af7  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x180024afc  mov     rcx, [rsp+2D8h]; this
0x180024b04  test    eax, eax
0x180024b06  js      loc_180024EC2
0x180024b0c  mov     rdi, [rbp+280h+var_258]
0x180024b10  mov     rax, [rdi]
0x180024b13  mov     rsi, [rax+0B0h]
0x180024b1a  mov     rdx, [rbp+280h+var_270]
0x180024b1e  test    rdx, rdx
0x180024b21  jz      short loc_180024B3B
0x180024b23  mov     [rbp+280h+var_270], 0
0x180024b2b  mov     rcx, [rdx]
0x180024b2e  mov     rax, [rcx+10h]
0x180024b32  mov     rcx, rdx
0x180024b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b3a  nop
0x180024b3b  lea     r8, [rbp+280h+var_270]
0x180024b3f  mov     rdx, rbx
0x180024b42  mov     rcx, rdi
0x180024b45  mov     rax, rsi
0x180024b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b4d  mov     rcx, [rsp+2D8h]; this
0x180024b55  test    eax, eax
0x180024b57  js      loc_180024ED6
0x180024b5d  mov     rcx, [rbp+280h+var_270]
0x180024b61  test    rcx, rcx
0x180024b64  jnz     short loc_180024B92
0x180024b66  mov     qword ptr [rsp+2D0h+UserDataCount], r15; int
0x180024b6b  mov     rdx, rbx; void *
0x180024b6e  mov     rcx, cs:qword_180148188; this
0x180024b75  call    ?QueryDefaultAccountUserContext@UserManagerTokenAndShellHandler@@QEAAJPEAXHHPEA_K@Z; UserManagerTokenAndShellHandler::QueryDefaultAccountUserContext(void *,int,int,unsigned __int64 *)
0x180024b7a  mov     rcx, [rsp+2D8h]; this
0x180024b82  shr     eax, 1Fh
0x180024b85  test    al, al
0x180024b87  jnz     loc_180024EEA
0x180024b8d  jmp     loc_180024C40
0x180024b92  xor     esi, esi
0x180024b94  mov     [rbp+280h+fPending], esi
0x180024b97  mov     rax, [rcx]
0x180024b9a  lea     rdx, [rbp+280h+fPending]
0x180024b9e  mov     rax, [rax+38h]
0x180024ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba7  mov     rcx, [rsp+2D8h]; this
0x180024baf  test    eax, eax
0x180024bb1  js      loc_180024F01
0x180024bb7  cmp     [rbp+280h+fPending], esi
0x180024bba  setz    al
0x180024bbd  mov     rcx, [rsp+2D8h]; this
0x180024bc5  test    al, al
0x180024bc7  jnz     loc_180024F15
0x180024bcd  mov     rbx, [rbp+280h+var_270]
0x180024bd1  mov     rax, [rbx]
0x180024bd4  mov     rdi, [rax]
0x180024bd7  mov     rdx, [rbp+280h+var_268]
0x180024bdb  test    rdx, rdx
0x180024bde  jz      short loc_180024BF4
0x180024be0  mov     [rbp+280h+var_268], rsi
0x180024be4  mov     rcx, [rdx]
0x180024be7  mov     rax, [rcx+10h]
0x180024beb  mov     rcx, rdx
0x180024bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bf3  nop
0x180024bf4  lea     r8, [rbp+280h+var_268]
0x180024bf8  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x180024bff  mov     rcx, rbx
0x180024c02  mov     rax, rdi
0x180024c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c0a  nop
0x180024c0b  mov     rcx, [rsp+2D8h]; this
0x180024c13  test    eax, eax
0x180024c15  js      loc_180024F2C
0x180024c1b  mov     rcx, [rbp+280h+var_268]
0x180024c1f  mov     rax, [rcx]
0x180024c22  mov     rdx, r15
0x180024c25  mov     rax, [rax+58h]
0x180024c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c2e  mov     rcx, [rsp+2D8h]; this
0x180024c36  test    eax, eax
0x180024c38  js      loc_180024F40
0x180024c3e  jmp     short loc_180024C42
0x180024c40  xor     esi, esi
0x180024c42  mov     [rbp+280h+Context], rsi
0x180024c46  mov     [rbp+280h+fPending], esi
0x180024c49  lea     r9, [rbp+280h+Context]; lpContext
0x180024c4d  lea     r8, [rbp+280h+fPending]; fPending
0x180024c51  xor     edx, edx; dwFlags
0x180024c53  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180024c5a  call    cs:__imp_InitOnceBeginInitialize
0x180024c60  test    eax, eax
0x180024c62  jz      loc_180024CE9
0x180024c68  cmp     [rbp+280h+fPending], 0
0x180024c6c  jz      short loc_180024CE9
0x180024c6e  mov     [rbp+280h+Context], r14
0x180024c72  mov     cs:qword_180147BD8, rsi
0x180024c79  mov     cs:byte_180147BE0, 0
0x180024c80  mov     cs:dword_180147BE4, esi
0x180024c86  mov     cs:qword_180147BD0, r12
0x180024c8d  mov     cs:CallbackContext, r13
0x180024c94  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x180024c9b  call    atexit
0x180024ca0  mov     rcx, cs:CallbackContext; CallbackContext
0x180024ca7  mov     cs:qword_180147BD8, rcx
0x180024cae  mov     cs:byte_180147BE0, 1
0x180024cb5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180024cba  mov     cs:dword_180147BE4, 1
0x180024cc4  mov     rax, cs:qword_180147BD0
0x180024ccb  mov     rcx, r14
0x180024cce  mov     rax, [rax+8]
0x180024cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd7  mov     r8, r14; lpContext
0x180024cda  xor     edx, edx; dwFlags
0x180024cdc  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180024ce3  call    cs:__imp_InitOnceComplete
0x180024ce9  mov     rax, [rbp+280h+Context]
0x180024ced  mov     rcx, [rax+8]
0x180024cf1  mov     eax, [rcx]
0x180024cf3  cmp     eax, 5
0x180024cf6  jbe     loc_180024DD2
0x180024cfc  mov     [rbp+280h+fPending], esi
0x180024cff  mov     rax, [r15]
0x180024d02  mov     qword ptr [rbp+280h+EventDescriptor.Id], rax
0x180024d06  lea     rax, [rbp+280h+fPending]
0x180024d0a  mov     [rbp+280h+var_50], rax
0x180024d11  mov     [rbp+280h+var_48], 4
0x180024d1c  lea     rax, [rbp+280h+EventDescriptor]
0x180024d20  mov     [rbp+280h+var_60], rax
0x180024d27  mov     [rbp+280h+var_58], 8
0x180024d32  mov     dword ptr [rbp+280h+var_A0.Ptr], 0B000000h
0x180024d3c  movzx   eax, cs:word_180129AC2
0x180024d43  mov     dword ptr [rbp+280h+var_A0.Ptr+4], eax
0x180024d49  mov     qword ptr [rbp+280h+var_A0.Size], rsi
0x180024d50  mov     rax, [rcx+8]
0x180024d54  mov     [rbp+280h+var_80.Ptr], rax
0x180024d5b  movzx   eax, word ptr [rax]
0x180024d5e  mov     [rbp+280h+var_80.Size], eax
0x180024d64  mov     dword ptr [rbp+280h+var_80.0Ch], 2
0x180024d6e  lea     rax, dword_180129ACC
0x180024d75  mov     [rbp+280h+var_70], rax
0x180024d7c  mov     [rbp+280h+var_68], 36h ; '6'
0x180024d86  mov     [rbp+280h+var_64], 1
0x180024d90  lea     rax, _TraceLoggingMetadataEnd
0x180024d97  lea     rdx, _TraceLoggingMetadata
0x180024d9e  sub     eax, edx
0x180024da0  mov     dword ptr [rbp+280h+Context], eax
0x180024da3  mov     eax, dword ptr [rbp+280h+Context]
0x180024da6  lea     rax, [rbp+280h+var_80]
0x180024dad  mov     [rsp+2D0h+UserData], rax; UserData
0x180024db2  mov     [rsp+2D0h+UserDataCount], 4; UserDataCount
0x180024dba  xor     r9d, r9d; RelatedActivityId
0x180024dbd  xor     r8d, r8d; ActivityId
0x180024dc0  lea     rdx, [rbp+280h+var_A0]; EventDescriptor
0x180024dc7  mov     rcx, [rcx+20h]; RegHandle
0x180024dcb  call    cs:__imp_EventWriteTransfer
0x180024dd1  nop
0x180024dd2  mov     rcx, [rbp+280h+hObject]; hObject
0x180024dd6  lea     rax, [rcx-1]
0x180024dda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024dde  ja      short loc_180024DE7
  ... truncated ...
```
