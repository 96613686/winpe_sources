# UserMgrCli::OpenProcessAndTokenForAccess(void *,ulong,ulong,void * *,void * *)

- ea: `0x1800b45ac`
- end: `0x1800b4c57`
- name: `?OpenProcessAndTokenForAccess@UserMgrCli@@QEAAJPEAXKKPEAPEAX1@Z`
- size: `1707`
- prototype: `int(UserMgrCli *__hidden this, void *, unsigned int, unsigned int, void **, void **)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5fa0`
- `0x1800b5fd0`

## callees

- `0x180007920`
- `0x180007ef4`
- `0x180008b10`
- `0x180008b70`
- `0x18000acdc`
- `0x18000c350`
- `0x18000c6d0`
- `0x18000cd30`
- `0x18000ce48`
- `0x180012890`
- `0x180015960`
- `0x18002618c`
- `0x180037ee4`
- `0x18003e290`
- `0x18004e4e8`
- `0x18004e58c`
- `0x18006f1c9`
- `0x1800b45ac`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b4894`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800b4894`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b48ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800b48ca`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800b47a5`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800b47a5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b49dc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b49dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4777`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b492d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4777`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b492d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800b46e1`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800b46e1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b4732`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b48ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b4732`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b48ed`
- `ntdll!NtCompareTokens` at `0x1800b497a`
- `ntdll!NtCompareTokens` at `0x1800b497a`

## string_xrefs

- `0x1800b4aba`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4ad1`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4ae5`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4af6`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b0d`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b24`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b35`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b46`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b57`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b6b`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b7f`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4b93`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4ba7`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4bbe`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4bd2`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4be3`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4bf4`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4c05`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4c1c`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4c33`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x1800b4c44`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UserMgrCli::OpenProcessAndTokenForAccess(
        UserMgrCli *this,
        void *a2,
        int a3,
        DWORD a4,
        void **a5,
        void **phNewToken)
{
  unsigned __int64 v6; // rbp
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  void *v12; // rdx
  char v13; // al
  int BasicCallerInformation; // eax
  const char *v15; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rbx
  const char *v19; // r9
  const char *v20; // r9
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, unsigned __int64); // rbx
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  int DefaultAccountUserContext; // eax
  int v29; // eax
  PSRWLOCK v30; // rbx
  RTL_SRWLOCK *v31; // r15
  _QWORD *v32; // rdx
  DWORD v33; // edi
  int v34; // ebx
  HANDLE v35; // rax
  const char *v36; // r9
  void *v37; // rbx
  const char *v38; // r9
  const char *v39; // r9
  void *v40; // rcx
  NTSTATUS v41; // eax
  const char *v42; // r9
  const struct _tlgProvider_t *v43; // rax
  int v44; // r8d
  int v45; // r9d
  __int64 result; // rax
  const struct _tlgProvider_t *v47; // rax
  int v48; // ebx
  wil *v49; // rcx
  int v50; // r8d
  int v51; // r9d
  int TokenType; // [rsp+20h] [rbp-40h]
  unsigned __int8 Equal[4]; // [rsp+60h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+2E8h] [rbp+288h]

  v6 = (unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL;
  *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = a3;
  *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = a4;
  v9 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v9 > 4u )
  {
    *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4) = a4;
    *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 8) = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)&word_18012A2E6,
      v10,
      v11,
      v6 + 8,
      v6 + 4);
  }
  memset_0((void *)(v6 + 160), 0, 0x1A0u);
  try
  {
    *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
    *(_BYTE *)v6 = 0;
    if ( byte_1801481CC )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x8000FFFFLL,
        TokenType);
    if ( a5 || (v13 = 1, phNewToken) )
      v13 = 0;
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x426,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070057LL,
        TokenType);
    BasicCallerInformation = UserMgrCli::GetBasicCallerInformation(
                               retaddr,
                               v12,
                               (struct _BASIC_CALLER_INFORMATION *)(v6 + 160));
    if ( BasicCallerInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x428,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)BasicCallerInformation,
        TokenType);
    UserMgrCli::CheckApiRestrictionsForCaller(
      retaddr,
      (struct _BASIC_CALLER_INFORMATION *)(v6 + 160),
      (const struct _CALLER_RESTRICTIONS *)byte_1801135F0);
    if ( !ProcessIdToSessionId(a4, (DWORD *)(v6 + 24)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x42C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v15);
    if ( *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) != *(_DWORD *)(((unsigned __int64)Equal
                                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                            + 0xA8) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        TokenType);
    if ( (a3 & 0xFFEFCBAE) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        TokenType);
    v16 = OpenProcess(a3 | 0x1000u, 0, a4);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 64,
      v16);
    v18 = *(void **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x80) = v18;
    if ( !v18 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x432,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v17);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 48,
      0);
    if ( !OpenProcessToken(v18, 0xAu, (PHANDLE)(v6 + 48)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x434,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v19);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 40,
      0);
    if ( !DuplicateToken(
            *(HANDLE *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            SecurityIdentification,
            (PHANDLE)(v6 + 40)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x435,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v20);
    v21 = Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>((__int64 *)(v6 + 88));
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x436,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v21,
        TokenType);
    v22 = *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x58);
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64))(*(_QWORD *)v22 + 176LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v6 + 56);
    v24 = v23(v22, *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x28), v6 + 56);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x437,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v24,
        TokenType);
    v27 = *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
    if ( v27 )
    {
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v27 + 56LL))(v27, v6 + 4);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x43F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)v29,
          TokenType);
      if ( !*(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x440,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)0x80070005LL,
          TokenType);
    }
    else
    {
      DefaultAccountUserContext = UserManagerTokenAndShellHandler::QueryDefaultAccountUserContext(
                                    (UserManagerTokenAndShellHandler *)qword_180148188,
                                    *(void **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
                                    v25,
                                    v26,
                                    (unsigned __int64 *)(v6 + 120));
      if ( DefaultAccountUserContext < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x43A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
          (const char *)(unsigned int)DefaultAccountUserContext,
          TokenType);
    }
    v30 = qword_180148188;
    *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 8) = *(_DWORD *)(((unsigned __int64)Equal
                                                                                    & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                   + 0xA8);
    v31 = v30 + 9;
    AcquireSRWLockShared(v30 + 9);
    std::_Tree<std::_Tmap_traits<unsigned int,Windows::System::Internal::Implementation::SignOutProgress *,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(
      &v30[10],
      v6 + 32,
      v6 + 8);
    v32 = *(_QWORD **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    if ( v32 == v30[10].Ptr )
    {
      v33 = 0;
      v34 = -2146893807;
    }
    else
    {
      v33 = *(_DWORD *)(v32[5] + 16LL);
      v34 = 0;
    }
    ReleaseSRWLockShared(v31);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x444,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v34,
        TokenType);
    v35 = OpenProcess(0x1000u, 0, v33);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 104,
      v35);
    v37 = *(void **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x68);
    if ( !v37 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x44C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v36);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 72,
      0);
    if ( !OpenProcessToken(v37, 8u, (PHANDLE)(v6 + 72)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x44E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v38);
    *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x70) = 0;
    GetCallerToken((PHANDLE)(v6 + 112));
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v6 + 96,
      *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x70));
    v40 = *(void **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
    if ( !v40 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x453,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v39);
    v41 = NtCompareTokens(
            v40,
            *(HANDLE *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x48),
            (PBOOLEAN)((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL));
    if ( v41 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x455,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v41,
        TokenType);
    if ( !*(_BYTE *)v6 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x456,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)0x80070005LL,
        TokenType);
    if ( a5 )
    {
      *(_QWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
      *a5 = *(void **)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
    }
    if ( phNewToken
      && !DuplicateTokenEx(
            *(HANDLE *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            8u,
            0,
            SecurityIdentification,
            TokenImpersonation,
            phNewToken) )
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x45F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        v42);
    }
    v43 = UserMgrUserModelTelemetry::Provider();
    if ( *(_DWORD *)v43 > 4u )
    {
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4) = a4;
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v43,
        (unsigned int)byte_18012A21B,
        v44,
        v45,
        v6 + 32,
        v6 + 4,
        v6 + 8);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v6 + 88);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v6 + 56);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 96);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 64);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 104);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 72);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 40);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v6 + 48);
    result = 0;
  }
  catch ( ... )
  {
    v47 = UserMgrUserModelTelemetry::Provider();
    v48 = (int)v47;
    v49 = (wil *)*(unsigned int *)v47;
    if ( (unsigned int)v49 > 4 )
    {
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = wil::ResultFromCaughtException(v49);
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 8) = *(_DWORD *)(((unsigned __int64)Equal
                                                                                      & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                     + 0x50);
      *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4) = *(_DWORD *)(((unsigned __int64)Equal
                                                                                      & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                     + 0x10);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v48,
        (unsigned int)&byte_18012A277,
        v50,
        v51,
        ((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 4,
        ((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 8,
        ((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 32);
    }
    *(_DWORD *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = wil::ResultFromCaughtException(v49);
    return *(unsigned int *)(((unsigned __int64)Equal & 0xFFFFFFFFFFFFFFE0uLL) + 0x10);
  }
  return result;
}

```

## disassembly

```asm
0x1800b45ac  mov     [rsp-8+arg_0], rbx
0x1800b45b1  push    rbp
0x1800b45b2  push    rsi
0x1800b45b3  push    rdi
0x1800b45b4  push    r12
0x1800b45b6  push    r13
0x1800b45b8  push    r14
0x1800b45ba  push    r15
0x1800b45bc  sub     rsp, 2B0h
0x1800b45c3  lea     rbp, [rsp+60h]
0x1800b45c8  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800b45cc  mov     rax, cs:__security_cookie
0x1800b45d3  xor     rax, rsp
0x1800b45d6  mov     [rbp+280h+var_40], rax
0x1800b45dd  mov     r14d, r9d
0x1800b45e0  mov     esi, r8d
0x1800b45e3  mov     [rbp+280h+var_270], r8d
0x1800b45e7  mov     [rbp+280h+var_230], r9d
0x1800b45eb  mov     r12, [rsp+2E0h+arg_20]
0x1800b45f3  mov     r13, [rsp+2E0h+arg_28]
0x1800b45fb  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b4600  mov     ecx, [rax]
0x1800b4602  cmp     ecx, 4
0x1800b4605  jbe     short loc_1800B462F
0x1800b4607  mov     [rbp+280h+var_27C], r14d
0x1800b460b  mov     [rbp+280h+var_278], esi
0x1800b460e  lea     rcx, [rbp+280h+var_27C]
0x1800b4612  mov     [rsp+2E0h+phNewToken], rcx
0x1800b4617  lea     rcx, [rbp+280h+var_278]
0x1800b461b  mov     qword ptr [rsp+2E0h+TokenType], rcx; int
0x1800b4620  lea     rdx, word_18012A2E6
0x1800b4627  mov     rcx, rax
0x1800b462a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b462f  xor     edx, edx; Val
0x1800b4631  mov     r8d, 1A0h; Size
0x1800b4637  lea     rcx, [rbp+280h+var_1E0]; void *
0x1800b463e  call    memset_0
0x1800b4643  xor     r15d, r15d
0x1800b4646  mov     [rbp+280h+pSessionId], r15d
0x1800b464a  mov     [rbp+280h+TokenHandle], r15
0x1800b464e  mov     [rbp+280h+DuplicateTokenHandle], r15
0x1800b4652  mov     [rbp+280h+SecondTokenHandle], r15
0x1800b4656  mov     [rbp+280h+var_218], r15
0x1800b465a  mov     [rbp+280h+ProcessHandle], r15
0x1800b465e  mov     [rbp+280h+FirstTokenHandle], r15
0x1800b4662  mov     [rbp+280h+var_248], r15
0x1800b4666  mov     [rbp+280h+var_228], r15
0x1800b466a  mov     [rbp+280h+var_208], r15
0x1800b466e  mov     [rbp+280h+Equal], r15b
0x1800b4672  cmp     cs:byte_1801481CC, r15b
0x1800b4679  setnz   al
0x1800b467c  mov     rcx, [rsp+2E8h]; this
0x1800b4684  test    al, al
0x1800b4686  jnz     loc_1800B4AB4
0x1800b468c  test    r12, r12
0x1800b468f  jnz     short loc_1800B4698
0x1800b4691  test    r13, r13
0x1800b4694  mov     al, 1
0x1800b4696  jz      short loc_1800B469B
0x1800b4698  mov     al, r15b
0x1800b469b  mov     rcx, [rsp+2E8h]; this
0x1800b46a3  test    al, al
0x1800b46a5  jnz     loc_1800B4ACB
0x1800b46ab  lea     r8, [rbp+280h+var_1E0]; struct _BASIC_CALLER_INFORMATION *
0x1800b46b2  call    ?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z; UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)
0x1800b46b7  mov     rcx, [rsp+2E8h]; this
0x1800b46bf  test    eax, eax
0x1800b46c1  js      loc_1800B4AE2
0x1800b46c7  lea     r8, byte_1801135F0; struct _CALLER_RESTRICTIONS *
0x1800b46ce  lea     rdx, [rbp+280h+var_1E0]; struct _BASIC_CALLER_INFORMATION *
0x1800b46d5  call    ?CheckApiRestrictionsForCaller@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEBU_CALLER_RESTRICTIONS@@@Z; UserMgrCli::CheckApiRestrictionsForCaller(_BASIC_CALLER_INFORMATION *,_CALLER_RESTRICTIONS const *)
0x1800b46da  lea     rdx, [rbp+280h+pSessionId]; pSessionId
0x1800b46de  mov     ecx, r14d; dwProcessId
0x1800b46e1  call    cs:__imp_ProcessIdToSessionId
0x1800b46e7  mov     rcx, [rsp+2E8h]; this
0x1800b46ef  test    eax, eax
0x1800b46f1  jz      loc_1800B4AF6
0x1800b46f7  mov     eax, [rbp+280h+var_1D8]
0x1800b46fd  cmp     [rbp+280h+pSessionId], eax
0x1800b4700  setnz   al
0x1800b4703  mov     rcx, [rsp+2E8h]; this
0x1800b470b  test    al, al
0x1800b470d  jnz     loc_1800B4B07
0x1800b4713  mov     rcx, [rsp+2E8h]; this
0x1800b471b  test    esi, 0FFEFCBAEh
0x1800b4721  jnz     loc_1800B4B1E
0x1800b4727  mov     ecx, esi
0x1800b4729  bts     ecx, 0Ch; dwDesiredAccess
0x1800b472d  mov     r8d, r14d; dwProcessId
0x1800b4730  xor     edx, edx; bInheritHandle
0x1800b4732  call    cs:__imp_OpenProcess
0x1800b4738  mov     rdx, rax
0x1800b473b  lea     rcx, [rbp+280h+ProcessHandle]
0x1800b473f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b4744  mov     rcx, [rsp+2E8h]; this
0x1800b474c  mov     rbx, [rbp+280h+ProcessHandle]
0x1800b4750  mov     [rbp+280h+var_200], rbx
0x1800b4757  test    rbx, rbx
0x1800b475a  jz      loc_1800B4B35
0x1800b4760  xor     edx, edx
0x1800b4762  lea     rcx, [rbp+280h+TokenHandle]
0x1800b4766  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b476b  lea     r8, [rbp+280h+TokenHandle]; TokenHandle
0x1800b476f  mov     edx, 0Ah; DesiredAccess
0x1800b4774  mov     rcx, rbx; ProcessHandle
0x1800b4777  call    cs:__imp_OpenProcessToken
0x1800b477d  mov     rcx, [rsp+2E8h]; this
0x1800b4785  test    eax, eax
0x1800b4787  jz      loc_1800B4B46
0x1800b478d  xor     edx, edx
0x1800b478f  lea     rcx, [rbp+280h+DuplicateTokenHandle]
0x1800b4793  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b4798  lea     r8, [rbp+280h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800b479c  mov     edx, 1; ImpersonationLevel
0x1800b47a1  mov     rcx, [rbp+280h+TokenHandle]; ExistingTokenHandle
0x1800b47a5  call    cs:__imp_DuplicateToken
0x1800b47ab  mov     rcx, [rsp+2E8h]; this
0x1800b47b3  test    eax, eax
0x1800b47b5  jz      loc_1800B4B57
0x1800b47bb  lea     rcx, [rbp+280h+var_228]
0x1800b47bf  call    ??$GetStaticInstance@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@StaticsCache@Internal@System@Windows@@SAJV?$ComPtrRef@V?$ComPtr@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@K@Z; Windows::System::Internal::StaticsCache::GetStaticInstance<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserStaticsInternal>>,ulong)
0x1800b47c4  mov     rcx, [rsp+2E8h]; this
0x1800b47cc  test    eax, eax
0x1800b47ce  js      loc_1800B4B68
0x1800b47d4  mov     rdi, [rbp+280h+var_228]
0x1800b47d8  mov     rax, [rdi]
0x1800b47db  mov     rbx, [rax+0B0h]
0x1800b47e2  lea     rcx, [rbp+280h+var_248]
0x1800b47e6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b47eb  lea     r8, [rbp+280h+var_248]
0x1800b47ef  mov     rdx, [rbp+280h+DuplicateTokenHandle]
0x1800b47f3  mov     rcx, rdi
0x1800b47f6  mov     rax, rbx
0x1800b47f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b47fe  mov     rcx, [rsp+2E8h]; this
0x1800b4806  test    eax, eax
0x1800b4808  js      loc_1800B4B7C
0x1800b480e  mov     rcx, [rbp+280h+var_248]
0x1800b4812  test    rcx, rcx
0x1800b4815  jnz     short loc_1800B4842
0x1800b4817  lea     rax, [rbp+280h+var_208]
0x1800b481b  mov     qword ptr [rsp+2E0h+TokenType], rax; int
0x1800b4820  mov     rdx, [rbp+280h+DuplicateTokenHandle]; void *
0x1800b4824  mov     rcx, cs:qword_180148188; this
0x1800b482b  call    ?QueryDefaultAccountUserContext@UserManagerTokenAndShellHandler@@QEAAJPEAXHHPEA_K@Z; UserManagerTokenAndShellHandler::QueryDefaultAccountUserContext(void *,int,int,unsigned __int64 *)
0x1800b4830  mov     rcx, [rsp+2E8h]; this
0x1800b4838  test    eax, eax
0x1800b483a  js      loc_1800B4B90
0x1800b4840  jmp     short loc_1800B487D
0x1800b4842  mov     [rbp+280h+var_27C], r15d
0x1800b4846  mov     rax, [rcx]
0x1800b4849  lea     rdx, [rbp+280h+var_27C]
0x1800b484d  mov     rax, [rax+38h]
0x1800b4851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4856  mov     rcx, [rsp+2E8h]; this
0x1800b485e  test    eax, eax
0x1800b4860  js      loc_1800B4BA4
0x1800b4866  cmp     [rbp+280h+var_27C], r15d
0x1800b486a  setz    al
0x1800b486d  mov     rcx, [rsp+2E8h]; this
0x1800b4875  test    al, al
0x1800b4877  jnz     loc_1800B4BB8
0x1800b487d  mov     rbx, cs:qword_180148188
0x1800b4884  mov     eax, [rbp+280h+var_1D8]
0x1800b488a  mov     [rbp+280h+var_278], eax
0x1800b488d  lea     r15, [rbx+48h]
0x1800b4891  mov     rcx, r15; SRWLock
0x1800b4894  call    cs:__imp_AcquireSRWLockShared
0x1800b489a  lea     r8, [rbp+280h+var_278]
0x1800b489e  lea     rdx, [rbp+280h+var_260]
0x1800b48a2  lea     rcx, [rbx+50h]
0x1800b48a6  call    ?find@?$_Tree@V?$_Tmap_traits@IPEAVSignOutProgress@Implementation@Internal@System@Windows@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBIPEAVSignOutProgress@Implementation@Internal@System@Windows@@@std@@@std@@@std@@@2@AEBI@Z; std::_Tree<std::_Tmap_traits<uint,Windows::System::Internal::Implementation::SignOutProgress *,std::less<uint>,std::allocator<std::pair<uint const,Windows::System::Internal::Implementation::SignOutProgress *>>,0>>::find(uint const &)
0x1800b48ab  mov     rdx, [rbp+280h+var_260]
0x1800b48af  cmp     rdx, [rbx+50h]
0x1800b48b3  jnz     short loc_1800B48BE
0x1800b48b5  xor     edi, edi
0x1800b48b7  mov     ebx, 80090011h
0x1800b48bc  jmp     short loc_1800B48C7
0x1800b48be  mov     rax, [rdx+28h]
0x1800b48c2  mov     edi, [rax+10h]
0x1800b48c5  xor     ebx, ebx
0x1800b48c7  mov     rcx, r15; SRWLock
0x1800b48ca  call    cs:__imp_ReleaseSRWLockShared
0x1800b48d0  mov     rcx, [rsp+2E8h]; this
0x1800b48d8  xor     r15d, r15d
0x1800b48db  test    ebx, ebx
0x1800b48dd  js      loc_1800B4BCF
0x1800b48e3  mov     r8d, edi; dwProcessId
0x1800b48e6  xor     edx, edx; bInheritHandle
0x1800b48e8  mov     ecx, 1000h; dwDesiredAccess
0x1800b48ed  call    cs:__imp_OpenProcess
0x1800b48f3  mov     rdx, rax
0x1800b48f6  lea     rcx, [rbp+280h+var_218]
0x1800b48fa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b48ff  mov     rcx, [rsp+2E8h]; this
0x1800b4907  mov     rbx, [rbp+280h+var_218]
0x1800b490b  test    rbx, rbx
0x1800b490e  jz      loc_1800B4BE3
0x1800b4914  xor     edx, edx
0x1800b4916  lea     rcx, [rbp+280h+SecondTokenHandle]
0x1800b491a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b491f  lea     r8, [rbp+280h+SecondTokenHandle]; TokenHandle
0x1800b4923  mov     edi, 8
0x1800b4928  mov     edx, edi; DesiredAccess
0x1800b492a  mov     rcx, rbx; ProcessHandle
0x1800b492d  call    cs:__imp_OpenProcessToken
0x1800b4933  mov     rcx, [rsp+2E8h]; this
0x1800b493b  test    eax, eax
0x1800b493d  jz      loc_1800B4BF4
0x1800b4943  mov     [rbp+280h+var_210], r15
0x1800b4947  lea     rcx, [rbp+280h+var_210]; phNewToken
0x1800b494b  call    ?GetCallerToken@@YAJPEAPEAX@Z; GetCallerToken(void * *)
0x1800b4950  mov     rdx, [rbp+280h+var_210]
0x1800b4954  lea     rcx, [rbp+280h+FirstTokenHandle]
0x1800b4958  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b495d  mov     rax, [rsp+2E8h]
0x1800b4965  mov     rcx, [rbp+280h+FirstTokenHandle]; FirstTokenHandle
0x1800b4969  test    rcx, rcx
0x1800b496c  jz      loc_1800B4C05
0x1800b4972  lea     r8, [rbp+280h+Equal]; Equal
0x1800b4976  mov     rdx, [rbp+280h+SecondTokenHandle]; SecondTokenHandle
0x1800b497a  call    cs:__imp_NtCompareTokens
0x1800b4980  mov     rcx, [rsp+2E8h]; this
0x1800b4988  test    eax, eax
0x1800b498a  js      loc_1800B4C19
0x1800b4990  cmp     [rbp+280h+Equal], r15b
0x1800b4994  setnz   al
0x1800b4997  mov     rcx, [rsp+2E8h]; this
0x1800b499f  test    al, al
0x1800b49a1  jz      loc_1800B4C2D
0x1800b49a7  test    r12, r12
0x1800b49aa  jz      short loc_1800B49BB
0x1800b49ac  mov     [rbp+280h+ProcessHandle], r15
0x1800b49b0  mov     rax, [rbp+280h+var_200]
0x1800b49b7  mov     [r12], rax
0x1800b49bb  test    r13, r13
0x1800b49be  jz      short loc_1800B49F2
0x1800b49c0  mov     [rsp+2E0h+phNewToken], r13; phNewToken
0x1800b49c5  mov     [rsp+2E0h+TokenType], 2; TokenType
0x1800b49cd  mov     r9d, 1; ImpersonationLevel
0x1800b49d3  xor     r8d, r8d; lpTokenAttributes
0x1800b49d6  mov     edx, edi; dwDesiredAccess
0x1800b49d8  mov     rcx, [rbp+280h+TokenHandle]; hExistingToken
0x1800b49dc  call    cs:__imp_DuplicateTokenEx
0x1800b49e2  mov     rcx, [rsp+2E8h]; this
0x1800b49ea  test    eax, eax
0x1800b49ec  jz      loc_1800B4C44
0x1800b49f2  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x1800b49f7  mov     ecx, [rax]
0x1800b49f9  cmp     ecx, 4
0x1800b49fc  jbe     short loc_1800B4A34
0x1800b49fe  mov     [rbp+280h+var_278], r15d
0x1800b4a02  mov     [rbp+280h+var_27C], r14d
0x1800b4a06  mov     dword ptr [rbp+280h+var_260], esi
0x1800b4a09  lea     rcx, [rbp+280h+var_278]
0x1800b4a0d  mov     [rsp+2E0h+var_2B0], rcx
0x1800b4a12  lea     rcx, [rbp+280h+var_27C]
0x1800b4a16  mov     [rsp+2E0h+phNewToken], rcx
0x1800b4a1b  lea     rcx, [rbp+280h+var_260]
0x1800b4a1f  mov     qword ptr [rsp+2E0h+TokenType], rcx
0x1800b4a24  lea     rdx, byte_18012A21B
0x1800b4a2b  mov     rcx, rax
0x1800b4a2e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4a33  nop
0x1800b4a34  lea     rcx, [rbp+280h+var_228]
0x1800b4a38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4a3d  nop
0x1800b4a3e  lea     rcx, [rbp+280h+var_248]
0x1800b4a42  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b4a47  nop
0x1800b4a48  lea     rcx, [rbp+280h+FirstTokenHandle]
0x1800b4a4c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a51  nop
0x1800b4a52  lea     rcx, [rbp+280h+ProcessHandle]
0x1800b4a56  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a5b  nop
0x1800b4a5c  lea     rcx, [rbp+280h+var_218]
0x1800b4a60  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a65  nop
0x1800b4a66  lea     rcx, [rbp+280h+SecondTokenHandle]
0x1800b4a6a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a6f  nop
0x1800b4a70  lea     rcx, [rbp+280h+DuplicateTokenHandle]
0x1800b4a74  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a79  nop
0x1800b4a7a  lea     rcx, [rbp+280h+TokenHandle]
0x1800b4a7e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b4a83  xor     eax, eax
0x1800b4a85  jmp     short loc_1800B4A8A
0x1800b4a87  mov     eax, [rbp+280h+var_270]
0x1800b4a8a  mov     rcx, [rbp+280h+var_40]
0x1800b4a91  xor     rcx, rsp; StackCookie
0x1800b4a94  call    __security_check_cookie
0x1800b4a99  mov     rbx, [rsp+2E0h+arg_0]
0x1800b4aa1  add     rsp, 2B0h
0x1800b4aa8  pop     r15
0x1800b4aaa  pop     r14
0x1800b4aac  pop     r13
0x1800b4aae  pop     r12
0x1800b4ab0  pop     rdi
  ... truncated ...
```
