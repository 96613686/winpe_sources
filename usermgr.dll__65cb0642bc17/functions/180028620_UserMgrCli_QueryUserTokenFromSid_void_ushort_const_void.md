# UserMgrCli::QueryUserTokenFromSid(void *,ushort const *,void * *)

- ea: `0x180028620`
- end: `0x180028bc5`
- name: `?QueryUserTokenFromSid@UserMgrCli@@QEAAJPEAXPEBGPEAPEAX@Z`
- size: `1445`
- prototype: `int(UserMgrCli *__hidden this, void *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180028600`

## callees

- `0x1800018c4`
- `0x180008b70`
- `0x18000acdc`
- `0x18000b510`
- `0x180028620`
- `0x18004e58c`
- `0x18006c318`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028947`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180028947`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028678`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028977`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028678`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180028977`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002871b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028a01`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002871b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028a01`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028825`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028af3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028825`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028af3`

## string_xrefs

- `0x180028b4b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028b62`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028b76`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028b8a`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028ba1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x180028bb2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserMgrCli::QueryUserTokenFromSid(UserMgrCli *this, void *a2, WCHAR *a3, void **a4)
{
  unsigned __int64 v4; // rbp
  WCHAR *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rbx
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  unsigned __int16 *v11; // rax
  void *v12; // rdx
  UserMgrCli *v13; // rcx
  int BasicCallerInformation; // eax
  UserMgrCli *v16; // rcx
  int AuthenticatedUserBySid; // eax
  int v18; // eax
  void *v19; // r10
  TOKEN_TYPE v20; // eax
  SECURITY_IMPERSONATION_LEVEL v21; // r9d
  const char *v22; // r9
  __int64 v23; // rcx
  int v24; // ebx
  unsigned __int16 *v25; // rax
  __int64 v26; // rcx
  __int64 result; // rax
  const struct _tlgProvider_t *v28; // rax
  int v29; // ebx
  wil *v30; // rcx
  int v31; // r8d
  int v32; // r9d
  ULONG UserDataCount; // [rsp+20h] [rbp-30h]
  WINBOOL fPending; // [rsp+50h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+268h]

  v4 = (unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = a4;
  v5 = a3;
  *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = a3;
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
  v6 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 8LL);
  if ( *(_DWORD *)v6 <= 4u )
  {
    v7 = -1;
  }
  else
  {
    v7 = -1;
    if ( v5 )
    {
      v8 = v5;
      v9 = -1;
      do
        ++v9;
      while ( v5[v9] );
      v10 = 2 * v9 + 2;
    }
    else
    {
      v8 = &cchOriginalDestLength;
      v10 = 2;
    }
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x200) = v8;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x208) = v10;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20C) = 0;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 184549376;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 4;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    v11 = *(unsigned __int16 **)(v6 + 8);
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E0) = v11;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E8) = *v11;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1EC) = 2;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F0) = &dword_18012989C;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F8) = 40;
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1FC) = 1;
    *(_DWORD *)v4 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v6 + 32), (PCEVENT_DESCRIPTOR)(v4 + 8), 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)(v4 + 480));
  }
  memset_0((void *)(v4 + 64), 0, 0x1A0u);
  try
  {
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               v13,
                               v12,
                               (struct _BASIC_CALLER_INFORMATION *)(v4 + 64));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        UserDataCount);
    if ( !*(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x42)
      && !*(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x41) )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x929,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        UserDataCount);
    }
    v16 = *(UserMgrCli **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v16 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      (*(void (__fastcall **)(UserMgrCli *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    AuthenticatedUserBySid = UserMgrCli::FindAuthenticatedUserBySid(
                               v16,
                               v5,
                               (struct _BASIC_CALLER_INFORMATION *)(v4 + 64),
                               (struct Windows::System::Internal::Implementation::IUserInternal **)(v4 + 24));
    if ( AuthenticatedUserBySid < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)AuthenticatedUserBySid,
        UserDataCount);
    v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)&fPending
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x18)
                                                              + 80LL))(
            *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
            v4 + 40);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x710,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v18,
        UserDataCount);
    v19 = *(void **)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    if ( !v19 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x711,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070520LL,
        UserDataCount);
    if ( *(_BYTE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) )
    {
      v20 = TokenPrimary;
      v21 = SecurityImpersonation;
    }
    else
    {
      v20 = TokenImpersonation;
      v21 = SecurityIdentification;
    }
    if ( !DuplicateTokenEx(
            v19,
            0,
            0,
            v21,
            v20,
            *(PHANDLE *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x718,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v22);
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
    v23 = *(_QWORD *)(*(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) + 8LL);
    if ( *(_DWORD *)v23 > 4u )
    {
      *(_DWORD *)v4 = 0;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x210) = (unsigned __int64)&fPending
                                                                                 & 0xFFFFFFFFFFFFFFE0uLL;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x218) = 4;
      if ( v5 )
      {
        do
          ++v7;
        while ( v5[v7] );
        v24 = 2 * v7 + 2;
      }
      else
      {
        v5 = (WCHAR *)&cchOriginalDestLength;
        v24 = 2;
      }
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x200) = v5;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x208) = v24;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20C) = 0;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 184549376;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x34) = 4;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
      v25 = *(unsigned __int16 **)(v23 + 8);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E0) = v25;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1E8) = *v25;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1EC) = 2;
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F0) = &unk_1801298D0;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1F8) = 55;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x1FC) = 1;
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = (unsigned int)&TraceLoggingMetadataEnd
                                                                             - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(
        *(_QWORD *)(v23 + 32),
        (PCEVENT_DESCRIPTOR)(v4 + 48),
        0,
        0,
        4u,
        (PEVENT_DATA_DESCRIPTOR)(v4 + 480));
    }
    v26 = *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v26 )
    {
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    result = 0;
  }
  catch ( ... )
  {
    v28 = UserMgrUserModelTelemetry::Provider();
    v29 = (int)v28;
    v30 = (wil *)*(unsigned int *)v28;
    if ( (unsigned int)v30 > 4 )
    {
      *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v30);
      *(_QWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = *(_QWORD *)(((unsigned __int64)&fPending
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0x20);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v29,
        (unsigned int)byte_180129805,
        v31,
        v32,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 32,
        ((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
    }
    *(_DWORD *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8) = wil::ResultFromCaughtException(v30);
    return *(unsigned int *)(((unsigned __int64)&fPending & 0xFFFFFFFFFFFFFFE0uLL) + 8);
  }
  return result;
}

```

## disassembly

```asm
0x180028620  mov     [rsp-8+arg_0], rbx
0x180028625  push    rbp
0x180028626  push    rsi
0x180028627  push    rdi
0x180028628  push    r12
0x18002862a  push    r13
0x18002862c  push    r14
0x18002862e  push    r15
0x180028630  sub     rsp, 280h
0x180028637  lea     rbp, [rsp+50h]
0x18002863c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180028640  mov     rax, cs:__security_cookie
0x180028647  xor     rax, rsp
0x18002864a  mov     [rbp+260h+var_40], rax
0x180028651  mov     [rbp+260h+phNewToken], r9
0x180028655  mov     rdi, r8
0x180028658  mov     [rbp+260h+var_240], r8
0x18002865c  xor     r14d, r14d
0x18002865f  mov     [rbp+260h+Context], r14
0x180028663  mov     [rbp+260h+fPending], r14d
0x180028667  lea     r9, [rbp+260h+Context]; lpContext
0x18002866b  lea     r8, [rbp+260h+fPending]; fPending
0x18002866f  xor     edx, edx; dwFlags
0x180028671  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180028678  call    cs:__imp_InitOnceBeginInitialize
0x18002867e  test    eax, eax
0x180028680  jz      loc_180028723
0x180028686  cmp     [rbp+260h+fPending], r14d
0x18002868a  jz      loc_180028723
0x180028690  lea     rsi, qword_180147BD0
0x180028697  mov     [rbp+260h+Context], rsi
0x18002869b  mov     cs:qword_180147BD8, r14
0x1800286a2  mov     cs:byte_180147BE0, r14b
0x1800286a9  mov     cs:dword_180147BE4, r14d
0x1800286b0  lea     r15, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x1800286b7  mov     cs:qword_180147BD0, r15
0x1800286be  lea     r12, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800286c5  mov     cs:CallbackContext, r12
0x1800286cc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x1800286d3  call    atexit
0x1800286d8  mov     rcx, cs:CallbackContext; CallbackContext
0x1800286df  mov     cs:qword_180147BD8, rcx
0x1800286e6  mov     cs:byte_180147BE0, 1
0x1800286ed  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800286f2  mov     cs:dword_180147BE4, 1
0x1800286fc  mov     rax, cs:qword_180147BD0
0x180028703  mov     rcx, rsi
0x180028706  mov     rax, [rax+8]
0x18002870a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870f  mov     r8, rsi; lpContext
0x180028712  xor     edx, edx; dwFlags
0x180028714  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x18002871b  call    cs:__imp_InitOnceComplete
0x180028721  jmp     short loc_180028738
0x180028723  lea     rsi, qword_180147BD0
0x18002872a  lea     r15, ??_7UserMgrUserModelTelemetry@@6B@; const UserMgrUserModelTelemetry::`vftable'
0x180028731  lea     r12, ?__hInner@?1???0StaticHandle@UserMgrUserModelTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserMgrUserModelTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180028738  mov     rax, [rbp+260h+Context]
0x18002873c  mov     rcx, [rax+8]
0x180028740  mov     eax, [rcx]
0x180028742  cmp     eax, 4
0x180028745  jbe     loc_18002882D
0x18002874b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180028752  test    rdi, rdi
0x180028755  jz      short loc_180028774
0x180028757  mov     rdx, rdi
0x18002875a  mov     rax, rbx
0x18002875d  nop     dword ptr [rax]
0x180028760  lea     rax, [rax+1]
0x180028764  cmp     [rdi+rax*2], r14w
0x180028769  jnz     short loc_180028760
0x18002876b  lea     eax, ds:2[rax*2]
0x180028772  jmp     short loc_180028780
0x180028774  lea     rdx, cchOriginalDestLength
0x18002877b  mov     eax, 2
0x180028780  mov     [rbp+260h+var_60], rdx
0x180028787  mov     [rbp+260h+var_58], eax
0x18002878d  mov     [rbp+260h+var_54], r14d
0x180028794  mov     dword ptr [rbp+260h+Context], 0B000000h
0x18002879b  movzx   eax, cs:word_180129892
0x1800287a2  mov     dword ptr [rbp+260h+Context+4], eax
0x1800287a5  mov     [rbp+260h+var_250], r14
0x1800287a9  mov     rax, [rcx+8]
0x1800287ad  mov     [rbp+260h+var_80.Ptr], rax
0x1800287b4  movzx   eax, word ptr [rax]
0x1800287b7  mov     [rbp+260h+var_80.Size], eax
0x1800287bd  mov     dword ptr [rbp+260h+var_80.0Ch], 2
0x1800287c7  lea     rax, dword_18012989C
0x1800287ce  mov     [rbp+260h+var_70], rax
0x1800287d5  mov     [rbp+260h+var_68], 28h ; '('
0x1800287df  mov     [rbp+260h+var_64], 1
0x1800287e9  lea     r14, _TraceLoggingMetadataEnd
0x1800287f0  mov     rax, r14
0x1800287f3  lea     r13, _TraceLoggingMetadata
0x1800287fa  sub     eax, r13d
0x1800287fd  mov     [rbp+260h+fPending], eax
0x180028800  mov     eax, [rbp+260h+fPending]
0x180028803  lea     rax, [rbp+260h+var_80]
0x18002880a  mov     [rsp+2B0h+UserData], rax; UserData
0x18002880f  mov     [rsp+2B0h+UserDataCount], 3; UserDataCount
0x180028817  xor     r9d, r9d; RelatedActivityId
0x18002881a  xor     r8d, r8d; ActivityId
0x18002881d  lea     rdx, [rbp+260h+Context]; EventDescriptor
0x180028821  mov     rcx, [rcx+20h]; RegHandle
0x180028825  call    cs:__imp_EventWriteTransfer
0x18002882b  jmp     short loc_180028842
0x18002882d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180028834  lea     r14, _TraceLoggingMetadataEnd
0x18002883b  lea     r13, _TraceLoggingMetadata
0x180028842  xor     edx, edx; Val
0x180028844  mov     r8d, 1A0h; Size
0x18002884a  lea     rcx, [rbp+260h+var_220]; void *
0x18002884e  call    memset_0
0x180028853  xor     eax, eax
0x180028855  mov     [rbp+260h+var_248], rax
0x180028859  mov     [rbp+260h+hExistingToken], rax
0x18002885d  lea     r8, [rbp+260h+var_220]; struct _BASIC_CALLER_INFORMATION *
0x180028861  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x180028866  mov     rcx, [rsp+2B8h]; this
0x18002886e  test    eax, eax
0x180028870  js      loc_180028B48
0x180028876  cmp     [rbp+260h+var_21E], 0
0x18002887a  jnz     short loc_180028886
0x18002887c  cmp     [rbp+260h+var_21F], 0
0x180028880  jnz     short loc_180028886
0x180028882  mov     al, 1
0x180028884  jmp     short loc_180028888
0x180028886  xor     al, al
0x180028888  mov     rcx, [rsp+2B8h]; this
0x180028890  test    al, al
0x180028892  jnz     loc_180028B5C
0x180028898  mov     rcx, [rbp+260h+var_248]
0x18002889c  test    rcx, rcx
0x18002889f  jz      short loc_1800288B6
0x1800288a1  mov     [rbp+260h+var_248], 0
0x1800288a9  mov     rax, [rcx]
0x1800288ac  mov     rax, [rax+10h]
0x1800288b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288b5  nop
0x1800288b6  lea     r9, [rbp+260h+var_248]; struct Windows::System::Internal::Implementation::IUserInternal **
0x1800288ba  lea     r8, [rbp+260h+var_220]; struct _BASIC_CALLER_INFORMATION *
0x1800288be  mov     rdx, rdi; unsigned __int16 *
0x1800288c1  call    ?FindAuthenticatedUserBySid@UserMgrCli@@AEAAJPEBGPEAU_BASIC_CALLER_INFORMATION@@PEAPEAUIUserInternal@Implementation@Internal@System@Windows@@@Z; UserMgrCli::FindAuthenticatedUserBySid(ushort const *,_BASIC_CALLER_INFORMATION *,Windows::System::Internal::Implementation::IUserInternal * *)
0x1800288c6  mov     rcx, [rsp+2B8h]; this
0x1800288ce  test    eax, eax
0x1800288d0  js      loc_180028B73
0x1800288d6  mov     rcx, [rbp+260h+var_248]
0x1800288da  mov     rax, [rcx]
0x1800288dd  lea     rdx, [rbp+260h+hExistingToken]
0x1800288e1  mov     rax, [rax+50h]
0x1800288e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288ea  mov     rcx, [rsp+2B8h]; this
0x1800288f2  test    eax, eax
0x1800288f4  js      loc_180028B87
0x1800288fa  mov     r10, [rbp+260h+hExistingToken]
0x1800288fe  test    r10, r10
0x180028901  setz    al
0x180028904  mov     rcx, [rsp+2B8h]; this
0x18002890c  test    al, al
0x18002890e  jnz     loc_180028B9B
0x180028914  cmp     [rbp+260h+var_220], 0
0x180028918  jz      short loc_180028927
0x18002891a  mov     eax, 1
0x18002891f  mov     r9d, 2
0x180028925  jmp     short loc_180028932
0x180028927  mov     eax, 2
0x18002892c  mov     r9d, 1; ImpersonationLevel
0x180028932  mov     rcx, [rbp+260h+phNewToken]
0x180028936  mov     [rsp+2B0h+UserData], rcx; phNewToken
0x18002893b  mov     [rsp+2B0h+UserDataCount], eax; TokenType
0x18002893f  xor     r8d, r8d; lpTokenAttributes
0x180028942  xor     edx, edx; dwDesiredAccess
0x180028944  mov     rcx, r10; hExistingToken
0x180028947  call    cs:__imp_DuplicateTokenEx
0x18002894d  mov     rcx, [rsp+2B8h]; this
0x180028955  test    eax, eax
0x180028957  jz      loc_180028BB2
0x18002895d  xor     eax, eax
0x18002895f  mov     [rbp+260h+Context], rax
0x180028963  mov     [rbp+260h+fPending], eax
0x180028966  lea     r9, [rbp+260h+Context]; lpContext
0x18002896a  lea     r8, [rbp+260h+fPending]; fPending
0x18002896e  xor     edx, edx; dwFlags
0x180028970  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180028977  call    cs:__imp_InitOnceBeginInitialize
0x18002897d  test    eax, eax
0x18002897f  jz      loc_180028A07
0x180028985  cmp     [rbp+260h+fPending], 0
0x180028989  jz      short loc_180028A07
0x18002898b  mov     [rbp+260h+Context], rsi
0x18002898f  xor     eax, eax
0x180028991  mov     cs:qword_180147BD8, rax
0x180028998  mov     cs:byte_180147BE0, al
0x18002899e  mov     cs:dword_180147BE4, eax
0x1800289a4  mov     cs:qword_180147BD0, r15
0x1800289ab  mov     cs:CallbackContext, r12
0x1800289b2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_720b04dfc33336bd43e851a7c42b71cc_@@CA@XZ; void (__cdecl *)()
0x1800289b9  call    atexit
0x1800289be  mov     rcx, cs:CallbackContext; CallbackContext
0x1800289c5  mov     cs:qword_180147BD8, rcx
0x1800289cc  mov     cs:byte_180147BE0, 1
0x1800289d3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800289d8  mov     cs:dword_180147BE4, 1
0x1800289e2  mov     rax, cs:qword_180147BD0
0x1800289e9  mov     rcx, rsi
0x1800289ec  mov     rax, [rax+8]
0x1800289f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f5  mov     r8, rsi; lpContext
0x1800289f8  xor     edx, edx; dwFlags
0x1800289fa  lea     rcx, ?wrapper@?1??Instance@UserMgrUserModelTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUserMgrUserModelTelemetry@@@details@wil@@A; lpInitOnce
0x180028a01  call    cs:__imp_InitOnceComplete
0x180028a07  mov     rax, [rbp+260h+Context]
0x180028a0b  mov     rcx, [rax+8]
0x180028a0f  mov     eax, [rcx]
0x180028a11  cmp     eax, 4
0x180028a14  jbe     loc_180028AFB
0x180028a1a  xor     esi, esi
0x180028a1c  mov     [rbp+260h+fPending], esi
0x180028a1f  lea     rax, [rbp+260h+fPending]
0x180028a23  mov     [rbp+260h+var_50], rax
0x180028a2a  mov     [rbp+260h+var_48], 4
0x180028a35  test    rdi, rdi
0x180028a38  jz      short loc_180028A53
0x180028a3a  nop     word ptr [rax+rax+00h]
0x180028a40  lea     rbx, [rbx+1]
0x180028a44  cmp     [rdi+rbx*2], si
0x180028a48  jnz     short loc_180028A40
0x180028a4a  lea     ebx, ds:2[rbx*2]
0x180028a51  jmp     short loc_180028A5F
0x180028a53  lea     rdi, cchOriginalDestLength
0x180028a5a  mov     ebx, 2
0x180028a5f  mov     [rbp+260h+var_60], rdi
0x180028a66  mov     [rbp+260h+var_58], ebx
0x180028a6c  mov     [rbp+260h+var_54], esi
0x180028a72  mov     dword ptr [rbp+260h+phNewToken], 0B000000h
0x180028a79  movzx   eax, cs:word_1801298C6
0x180028a80  mov     dword ptr [rbp+260h+phNewToken+4], eax
0x180028a83  mov     [rbp+260h+var_228], rsi
0x180028a87  mov     rax, [rcx+8]
0x180028a8b  mov     [rbp+260h+var_80.Ptr], rax
0x180028a92  movzx   eax, word ptr [rax]
0x180028a95  mov     [rbp+260h+var_80.Size], eax
0x180028a9b  mov     dword ptr [rbp+260h+var_80.0Ch], 2
0x180028aa5  lea     rax, unk_1801298D0
0x180028aac  mov     [rbp+260h+var_70], rax
0x180028ab3  mov     [rbp+260h+var_68], 37h ; '7'
0x180028abd  mov     [rbp+260h+var_64], 1
0x180028ac7  sub     r14d, r13d
0x180028aca  mov     dword ptr [rbp+260h+Context], r14d
0x180028ace  mov     eax, dword ptr [rbp+260h+Context]
0x180028ad1  lea     rax, [rbp+260h+var_80]
0x180028ad8  mov     [rsp+2B0h+UserData], rax; UserData
0x180028add  mov     [rsp+2B0h+UserDataCount], 4; UserDataCount
0x180028ae5  xor     r9d, r9d; RelatedActivityId
0x180028ae8  xor     r8d, r8d; ActivityId
0x180028aeb  lea     rdx, [rbp+260h+phNewToken]; EventDescriptor
0x180028aef  mov     rcx, [rcx+20h]; RegHandle
0x180028af3  call    cs:__imp_EventWriteTransfer
0x180028af9  jmp     short loc_180028AFD
0x180028afb  xor     esi, esi
0x180028afd  mov     rcx, [rbp+260h+var_248]
0x180028b01  test    rcx, rcx
0x180028b04  jz      short loc_180028B17
0x180028b06  mov     [rbp+260h+var_248], rsi
0x180028b0a  mov     rax, [rcx]
0x180028b0d  mov     rax, [rax+10h]
0x180028b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b16  nop
0x180028b17  xor     eax, eax
0x180028b19  jmp     short loc_180028B1E
0x180028b1b  mov     eax, dword ptr [rbp+260h+Context]
0x180028b1e  mov     rcx, [rbp+260h+var_40]
0x180028b25  xor     rcx, rsp; StackCookie
0x180028b28  call    __security_check_cookie
0x180028b2d  mov     rbx, [rsp+2B0h+arg_0]
0x180028b35  add     rsp, 280h
0x180028b3c  pop     r15
0x180028b3e  pop     r14
0x180028b40  pop     r13
0x180028b42  pop     r12
0x180028b44  pop     rdi
0x180028b45  pop     rsi
0x180028b46  pop     rbp
0x180028b47  retn
0x180028b48  mov     r9d, eax; char *
0x180028b4b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180028b52  mov     edx, 70Bh; void *
0x180028b57  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b5c  mov     r9d, 80070005h; char *
0x180028b62  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180028b69  mov     edx, 929h; void *
0x180028b6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b73  mov     r9d, eax; char *
0x180028b76  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180028b7d  mov     edx, 70Eh; void *
0x180028b82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028b87  mov     r9d, eax; char *
0x180028b8a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\umstartup\\userm"...
0x180028b91  mov     edx, 710h; void *
0x180028b96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
