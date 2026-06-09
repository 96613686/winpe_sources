# UserMgrCli::FindAuthenticatedUserBySid(ushort const *,_BASIC_CALLER_INFORMATION *,Windows::System::Internal::Implementation::IUserInternal * *)

- ea: `0x18000b510`
- end: `0x18000c24d`
- name: `?FindAuthenticatedUserBySid@UserMgrCli@@AEAAJPEBGPEAU_BASIC_CALLER_INFORMATION@@PEAPEAUIUserInternal@Implementation@Internal@System@Windows@@@Z`
- size: `3389`
- prototype: `int(UserMgrCli *__hidden this, const unsigned __int16 *, struct _BASIC_CALLER_INFORMATION *, struct Windows::System::Internal::Implementation::IUserInternal **)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028620`
- `0x18003e3a4`

## callees

- `0x1800088e8`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000acdc`
- `0x18000b510`
- `0x18000c2c0`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x18006f1c9`
- `0x18007512c`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b56f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b56f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b5f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b689`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b5f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b689`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b93c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b970`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bda9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c070`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b93c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b970`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bda9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000c070`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000ba15`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000ba15`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c141`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000c141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c218`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b676`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c211`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b676`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bce0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c22b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bce0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c22b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bcf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bcf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b6ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b6ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bc90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000bd4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c170`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c170`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c0f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c0f9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c10b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000c10b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b83d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b83d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c236`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c241`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd43`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000b8e8`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000c09d`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000b8e8`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000c09d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000bdd8`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c040`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000bdd8`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000c040`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7ff`
- `ntdll!RtlNtStatusToDosError` at `0x18000b7ff`
- `ntdll!RtlEqualSid` at `0x18000bd2c`
- `ntdll!RtlEqualSid` at `0x18000bd2c`
- `ntdll!RtlIsMultiSessionSku` at `0x18000bdee`
- `ntdll!RtlIsMultiSessionSku` at `0x18000bdee`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000bacf`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000bacf`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b7f7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b7f7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000ba87`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000ba87`
- `RPCRT4!RpcRevertToSelf` at `0x18000b859`
- `RPCRT4!RpcRevertToSelf` at `0x18000b859`
- `RPCRT4!RpcImpersonateClient` at `0x18000b7e4`
- `RPCRT4!RpcImpersonateClient` at `0x18000b7e4`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000bf94`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000bf94`

## string_xrefs

- `0x18000c1b4`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000bf29`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000bf3e`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000bfb8`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000bfca`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000bfdc`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000bfee`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c000`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c157`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c1d6`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000c1e8`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000be7b`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000be93`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000bf14`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000c015`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000c0bf`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000c0d1`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000bc51`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000bc69`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000beab`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000bec0`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000bed5`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000beea`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000beff`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18000bf69`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x18000c189`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall UserMgrCli::FindAuthenticatedUserBySid(
        UserMgrCli *this,
        WCHAR *a2,
        struct _BASIC_CALLER_INFORMATION *a3,
        struct Windows::System::Internal::Implementation::IUserInternal **a4)
{
  unsigned __int64 v4; // rbp
  unsigned int *v8; // rdi
  RTL_SRWLOCK *v9; // r15
  unsigned int **i; // rbx
  __int64 v11; // rdx
  int SessionIdFromCallerInfo; // eax
  unsigned int **v13; // rbx
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  HRESULT StringReference; // eax
  int v17; // eax
  __int64 (__fastcall *v18)(unsigned int **, GUID *, unsigned __int64); // rdi
  __int64 v19; // rcx
  int v20; // eax
  UserMgrCli *v21; // rcx
  RPC_STATUS v22; // eax
  NTSTATUS v23; // eax
  signed int v24; // eax
  HANDLE CurrentThread; // rax
  const char *v26; // r9
  char *v27; // rcx
  void *v28; // rdi
  const char *v29; // r9
  int v30; // eax
  const char *v31; // r9
  const char *v32; // r9
  void *v33; // rdx
  const char *v34; // r9
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38; // eax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, unsigned __int64); // rbx
  __int64 (__fastcall *v40)(_QWORD, GUID *, unsigned __int64); // rdi
  __int64 v41; // rcx
  int v42; // eax
  struct Windows::System::Internal::Implementation::IUserInternal *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v47; // rsi
  __int64 (__fastcall *v48)(__int64, unsigned __int64); // rdi
  int v49; // eax
  __int64 v50; // rsi
  unsigned int (__fastcall *v51)(__int64, PCWSTR, unsigned __int64); // r12
  void *v52; // r15
  DWORD v53; // edi
  PCWSTR StringRawBuffer; // rax
  const char *v55; // r9
  void *v56; // rcx
  char v57; // r15
  __int64 v58; // r14
  int v61; // eax
  DWORD v62; // eax
  unsigned int PackageFullNameFromToken; // eax
  const char *v65; // r9
  HANDLE CurrentProcess; // rax
  const char *v68; // r9
  const char *v69; // r9
  bool v70; // sf
  DWORD LastError; // edi
  int ReturnLength; // [rsp+20h] [rbp-60h]
  _BYTE v73[4]; // [rsp+80h] [rbp+0h] BYREF
  UserMgrCli *retaddr; // [rsp+368h] [rbp+2E8h]

  v4 = (unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(v4 + 40) = 0;
  *(_QWORD *)(v4 + 56) = 0;
  *(_DWORD *)(v4 + 8) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  LODWORD(v8) = -2147467262;
  v9 = &Windows::System::Internal::StaticsCache::s_rwLock;
LABEL_2:
  AcquireSRWLockShared(v9);
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = v9;
  for ( i = (unsigned int **)Windows::System::Internal::StaticsCache::s_cache;
        (unsigned __int64)i < *((_QWORD *)&Windows::System::Internal::StaticsCache::s_cache + 1);
        i += 2 )
  {
    v8 = *i;
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(unsigned int *))(*(_QWORD *)v8 + 8LL))(v8) )
    {
      LODWORD(v8) = 0;
LABEL_9:
      ReleaseSRWLockShared(v9);
      goto LABEL_10;
    }
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    v11 = v8[2];
    if ( (_DWORD)v11 )
    {
      LODWORD(v8) = v8[3];
      if ( (int)v8 < 0 )
        continue;
      LODWORD(v8) = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, unsigned __int64))(*(_QWORD *)qword_1801486B0
                                                                                          + 40LL))(
                      qword_1801486B0,
                      v11,
                      &GUID_44bb24bf_81c4_4741_b9c7_43d4e55f5591,
                      v4 + 64);
    }
    else
    {
      LODWORD(v8) = -2147024809;
    }
    if ( (int)v8 >= 0 )
      goto LABEL_9;
  }
  while ( 1 )
  {
    _InterlockedExchange(&Windows::System::Internal::StaticsCache::s_registered, 0);
    ReleaseSRWLockShared(v9);
    if ( (unsigned __int8)wil::slim_event_t<1>::wait(&Windows::System::Internal::StaticsCache::s_registered, 30000) )
      goto LABEL_2;
LABEL_10:
    if ( (int)v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x913,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)v8,
        ReturnLength);
    SessionIdFromCallerInfo = UserMgrCli::GetSessionIdFromCallerInfo(retaddr, a3, (unsigned int *)(v4 + 8));
    if ( SessionIdFromCallerInfo < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x915,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
        (const char *)(unsigned int)SessionIdFromCallerInfo,
        ReturnLength);
    v13 = *(unsigned int ***)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
    v8 = *v13;
    v14 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    if ( v14 )
    {
      *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF8) = 0;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    v9 = (RTL_SRWLOCK *)0xFFFFFFFFLL;
    if ( v15 <= 0xFFFFFFFF && (int)v15 + 1 >= (unsigned int)v15 )
      break;
    RaiseException(0x80070216, 1u, 0, 0);
  }
  StringReference = WindowsCreateStringReference(a2, v15, (HSTRING_HEADER *)(v4 + 224), (HSTRING *)(v4 + 248));
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    goto LABEL_146;
  }
  v17 = (*((__int64 (__fastcall **)(unsigned int **, _QWORD, _QWORD, unsigned __int64))v8 + 18))(
          v13,
          *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF8),
          *(unsigned int *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8),
          v4 + 40);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x916,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)(unsigned int)v17,
      ReturnLength);
  v13 = *(unsigned int ***)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
  if ( !v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x917,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)0x80070520LL,
      ReturnLength);
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = v13;
  (*((void (__fastcall **)(unsigned int **))*v13 + 1))(v13);
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
  (*(void (__fastcall **)(void *, unsigned __int64))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL))(
    &Windows::System::Internal::Adapters::g_AdapterCollection,
    v4 + 80);
  memset_0((void *)(v4 + 256), 0, 0x1A0u);
  v18 = *(__int64 (__fastcall **)(unsigned int **, GUID *, unsigned __int64))*v13;
  v19 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
  if ( v19 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v18(v13, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, v4 + 48);
  v21 = retaddr;
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
      (const char *)(unsigned int)v20,
      ReturnLength);
  if ( a3 )
    goto LABEL_56;
  *(_BYTE *)v4 = 0;
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = (unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE8) = 1;
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  v22 = RpcImpersonateClient(0);
  if ( v22 != 1725 )
  {
    v23 = I_RpcMapWin32Status(v22);
    v24 = RtlNtStatusToDosError(v23);
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)(unsigned int)v24,
        ReturnLength);
    *(_BYTE *)v4 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)(v4 + 32)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v26);
    goto LABEL_34;
  }
  a2 = *(WCHAR **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  if ( (unsigned __int64)a2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_146:
    LastError = GetLastError();
    CloseHandle(a2);
    SetLastError(LastError);
  }
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xAu, (PHANDLE)(v4 + 24)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v68);
  if ( !DuplicateTokenEx(
          *(HANDLE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
          0,
          0,
          SecurityImpersonation,
          TokenImpersonation,
          (PHANDLE)(v4 + 32)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v69);
LABEL_34:
  if ( *(_BYTE *)v4 )
    RpcRevertToSelf();
  v27 = *(char **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v27);
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  v28 = *(void **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
  *(_WORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x100) = 256;
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x108) = -1;
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x101) = IsTokenAppContainer(v28);
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x100) = DoesTokenHasPrivilege(v28, 7u);
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x180) = DoesTokenHasPrivilege(v28, 0x1Du);
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 0;
  if ( (unsigned int)CheckTokenCapability(v28, &CapMumaSidBuffer, v4 + 8) )
  {
    if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
      goto LABEL_40;
    *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
    *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = 0;
    *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF0) = 0;
    v57 = 0;
    v58 = (__int64)v28;
    if ( !v28 )
      v58 = -6;
    if ( GetTokenInformation((HANDLE)v58, TokenIsAppContainer, (LPVOID)(v4 + 12), 4u, (PDWORD)(v4 + 16)) )
    {
      if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_149;
      if ( !(unsigned int)CheckTokenMembershipEx(
                            v58,
                            &CapMumaGroupSidBuffer,
                            *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) != 0,
                            v4 + 4) )
        goto LABEL_112;
      if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_149;
      if ( !(unsigned __int8)RtlIsMultiSessionSku()
        && !(unsigned int)CheckTokenMembershipEx(
                            v58,
                            &DefaultAliasWellKnownSid,
                            *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) != 0,
                            v4 + 4) )
      {
        goto LABEL_112;
      }
      if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      {
LABEL_149:
        if ( !*(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) )
          goto LABEL_95;
        if ( !(unsigned int)CheckTokenCapability(v58, &CapMumaSidBuffer, v4 + 4) )
          goto LABEL_112;
        if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
LABEL_95:
          v57 = 1;
      }
LABEL_96:
      if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8) || v57 )
LABEL_40:
        *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 1;
      v30 = 0;
    }
    else
    {
LABEL_112:
      v62 = GetLastError();
      if ( !v62 )
        goto LABEL_96;
      v30 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x18D,
              (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
              (const char *)v62,
              ReturnLength);
    }
  }
  else
  {
    v30 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
            v29);
  }
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v30,
      ReturnLength);
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  if ( !GetTokenInformation(v28, TokenSessionId, (LPVOID)(v4 + 264), 4u, (PDWORD)(v4 + 16)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v31);
  if ( !GetTokenInformation(v28, TokenUser, (LPVOID)(v4 + 288), 0x54u, (PDWORD)(v4 + 24)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v32);
  v33 = *(void **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x120);
  *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x178) = v33;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF0) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x102) = 0;
  if ( !v33 )
  {
    if ( !GetTokenInformation(v28, TokenUser, (LPVOID)(v4 + 96), 0x54u, (PDWORD)(v4 + 16)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v65);
    v33 = *(void **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
  }
  if ( !AccessCheckByType(
          qword_18010A700,
          v33,
          v28,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&GenericMapping,
          (PPRIVILEGE_SET)(v4 + 224),
          (LPDWORD)(v4 + 4),
          (LPDWORD)(v4 + 12),
          (LPBOOL)(v4 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v34);
  if ( *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 8)
    && (*(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) & 1) != 0 )
  {
    *(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x102) = 1;
  }
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB8) = 0;
  *(_OWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8) = 0;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 3;
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x64) = 112;
  v35 = RpcServerInqCallAttributesW(0, (void *)(v4 + 96));
  if ( v35 )
  {
    if ( v35 == 1725 )
    {
      *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = GetCurrentProcessId();
    }
    else
    {
      v70 = v35 < 0;
      if ( v35 > 0 )
      {
        v35 = (unsigned __int16)v35 | 0x80070000;
        v70 = v35 < 0;
      }
      if ( v70 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
          (const char *)(unsigned int)v35,
          ReturnLength);
    }
  }
  else
  {
    *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = *(_DWORD *)(((unsigned __int64)v73
                                                                                      & 0xFFFFFFFFFFFFFFE0uLL)
                                                                                     + 0xA0);
  }
  if ( !*(_BYTE *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x101)
    || (*(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 128,
        PackageFullNameFromToken = GetPackageFullNameFromToken(v28, (UINT32 *)(v4 + 16), (PWSTR)(v4 + 388)),
        PackageFullNameFromToken == 15700) )
  {
    *(_WORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x184) = 0;
  }
  else if ( PackageFullNameFromToken )
  {
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)PackageFullNameFromToken,
      ReturnLength);
  }
  a3 = (struct _BASIC_CALLER_INFORMATION *)(v4 + 256);
  v21 = *(UserMgrCli **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
  if ( (unsigned __int64)v21 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v21);
LABEL_56:
  if ( *((_DWORD *)a3 + 2) != (unsigned int)RtlGetCurrentServiceSessionId(v21) )
  {
    v61 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v73
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x30)
                                                              + 96LL))(
            *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30),
            v4 + 72);
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)(unsigned int)v61,
        ReturnLength);
    if ( *((_DWORD *)a3 + 2) != *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)0x80070520LL,
        ReturnLength);
  }
  if ( !*((_BYTE *)a3 + 12) )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v47 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
    v48 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v47 + 72LL);
    WindowsDeleteString(0);
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v49 = v48(v47, v4 + 32);
    if ( v49 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)(unsigned int)v49,
        ReturnLength);
    v50 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
    v51 = *(unsigned int (__fastcall **)(__int64, PCWSTR, unsigned __int64))(*(_QWORD *)v50 + 40LL);
    v52 = *(void **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v52 )
    {
      v53 = GetLastError();
      LocalFree(v52);
      SetLastError(v53);
    }
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20), 0);
    if ( !v51(v50, StringRawBuffer, v4 + 24) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        v55);
    if ( !RtlEqualSid(*((PSID *)a3 + 15), *(PSID *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18)) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)0x80070520LL,
        ReturnLength);
    v56 = *(void **)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v56 )
      LocalFree(v56);
    WindowsDeleteString(*(HSTRING *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20));
  }
  v36 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50);
  if ( v36 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x50) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30);
  if ( v37 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  (*((void (__fastcall **)(unsigned int **))*v13 + 2))(v13);
  *(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C) = 0;
  v38 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v73
                                                                           & 0xFFFFFFFFFFFFFFE0uLL)
                                                                          + 0x28)
                                                            + 56LL))(
          *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
          v4 + 76);
  if ( v38 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)(unsigned int)v38,
      ReturnLength);
  if ( !*(_DWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x4C) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)0x80070520LL,
      ReturnLength);
  v39 = *(__int64 (__fastcall ****)(_QWORD, GUID *, unsigned __int64))(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL)
                                                                     + 0x28);
  v40 = **v39;
  v41 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
  if ( v41 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v40(v39, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, v4 + 56);
  if ( v42 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91E,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermgrcli.cpp",
      (const char *)(unsigned int)v42,
      ReturnLength);
  v43 = *(struct Windows::System::Internal::Implementation::IUserInternal **)(((unsigned __int64)v73
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x38);
  if ( v43 )
  {
    (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserInternal *))(*(_QWORD *)v43 + 8LL))(v43);
    v43 = *(struct Windows::System::Internal::Implementation::IUserInternal **)(((unsigned __int64)v73
                                                                               & 0xFFFFFFFFFFFFFFE0uLL)
                                                                              + 0x38);
  }
  *a4 = v43;
  if ( v43 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    (*(void (__fastcall **)(struct Windows::System::Internal::Implementation::IUserInternal *))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
  if ( v44 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
  if ( v45 )
  {
    *(_QWORD *)(((unsigned __int64)v73 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b510  mov     [rsp-8+arg_0], rbx
0x18000b515  push    rbp
0x18000b516  push    rsi
0x18000b517  push    rdi
0x18000b518  push    r12
0x18000b51a  push    r13
0x18000b51c  push    r14
0x18000b51e  push    r15
0x18000b520  sub     rsp, 330h
0x18000b527  lea     rbp, [rsp+80h]
0x18000b52f  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18000b533  mov     rax, cs:__security_cookie
0x18000b53a  xor     rax, rsp
0x18000b53d  mov     [rbp+2E0h+var_40], rax
0x18000b544  mov     r13, r9
0x18000b547  mov     r14, r8
0x18000b54a  mov     rsi, rdx
0x18000b54d  xor     r12d, r12d
0x18000b550  mov     [rbp+2E0h+var_2B8], r12
0x18000b554  mov     [rbp+2E0h+var_2A8], r12
0x18000b558  mov     [rbp+2E0h+var_2D8], r12d
0x18000b55c  mov     [rbp+2E0h+var_2A0], r12
0x18000b560  mov     edi, 80004002h
0x18000b565  lea     r15, ?s_rwLock@StaticsCache@Internal@System@Windows@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock Windows::System::Internal::StaticsCache::s_rwLock
0x18000b56c  mov     rcx, r15; SRWLock
0x18000b56f  call    cs:__imp_AcquireSRWLockShared
0x18000b575  mov     [rbp+2E0h+var_290], r15
0x18000b579  mov     rbx, qword ptr cs:?s_cache@StaticsCache@Internal@System@Windows@@0V?$vector@V?$shared_ptr@VGitPtr@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VGitPtr@Internal@Windows@@@std@@@2@@std@@A; std::vector<std::shared_ptr<Windows::Internal::GitPtr>> Windows::System::Internal::StaticsCache::s_cache
0x18000b580  cmp     rbx, qword ptr cs:?s_cache@StaticsCache@Internal@System@Windows@@0V?$vector@V?$shared_ptr@VGitPtr@Internal@Windows@@@std@@V?$allocator@V?$shared_ptr@VGitPtr@Internal@Windows@@@std@@@2@@std@@A+8; std::vector<std::shared_ptr<Windows::Internal::GitPtr>> Windows::System::Internal::StaticsCache::s_cache
0x18000b587  jnb     loc_18000B67D
0x18000b58d  mov     rdi, [rbx]
0x18000b590  mov     [rbp+2E0h+var_2A0], r12
0x18000b594  mov     rax, [rdi]
0x18000b597  mov     rcx, rdi
0x18000b59a  mov     rax, [rax+8]
0x18000b59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a3  test    al, al
0x18000b5a5  jz      loc_18000BE2F
0x18000b5ab  mov     [rbp+2E0h+var_2A0], r12
0x18000b5af  mov     edx, [rdi+8]
0x18000b5b2  test    edx, edx
0x18000b5b4  jz      loc_18000C1FA
0x18000b5ba  mov     edi, [rdi+0Ch]
0x18000b5bd  test    edi, edi
0x18000b5bf  js      loc_18000B6AD
0x18000b5c5  mov     rcx, cs:qword_1801486B0
0x18000b5cc  mov     rax, [rcx]
0x18000b5cf  lea     r9, [rbp+2E0h+var_2A0]
0x18000b5d3  lea     r8, _GUID_44bb24bf_81c4_4741_b9c7_43d4e55f5591
0x18000b5da  mov     rax, [rax+28h]
0x18000b5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e3  mov     edi, eax
0x18000b5e5  test    edi, edi
0x18000b5e7  js      loc_18000B6AD
0x18000b5ed  mov     rcx, r15; SRWLock
0x18000b5f0  call    cs:__imp_ReleaseSRWLockShared
0x18000b5f6  mov     rcx, [rsp+368h]; this
0x18000b5fe  test    edi, edi
0x18000b600  js      loc_18000BEA8
0x18000b606  lea     r8, [rbp+2E0h+var_2D8]; unsigned int *
0x18000b60a  mov     rdx, r14; struct _BASIC_CALLER_INFORMATION *
0x18000b60d  call    ?GetSessionIdFromCallerInfo@UserMgrCli@@AEAAJPEAU_BASIC_CALLER_INFORMATION@@PEAK@Z; UserMgrCli::GetSessionIdFromCallerInfo(_BASIC_CALLER_INFORMATION *,ulong *)
0x18000b612  mov     rcx, [rsp+368h]; this
0x18000b61a  test    eax, eax
0x18000b61c  js      loc_18000BEBD
0x18000b622  mov     rbx, [rbp+2E0h+var_2A0]
0x18000b626  mov     rdi, [rbx]
0x18000b629  mov     rcx, [rbp+2E0h+var_2B8]
0x18000b62d  test    rcx, rcx
0x18000b630  jz      short loc_18000B643
0x18000b632  mov     [rbp+2E0h+var_2B8], r12
0x18000b636  mov     rax, [rcx]
0x18000b639  mov     rax, [rax+10h]
0x18000b63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b642  nop
0x18000b643  mov     [rbp+2E0h+string], r12
0x18000b64a  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000b651  inc     rdx; length
0x18000b654  cmp     word ptr [rsi+rdx*2], 0
0x18000b659  jnz     short loc_18000B651
0x18000b65b  mov     r15d, 0FFFFFFFFh
0x18000b661  cmp     rdx, r15
0x18000b664  jbe     short loc_18000B6B6
0x18000b666  xor     r9d, r9d; lpArguments
0x18000b669  xor     r8d, r8d; nNumberOfArguments
0x18000b66c  mov     edx, 1; dwExceptionFlags
0x18000b671  mov     ecx, 80070216h; dwExceptionCode
0x18000b676  call    cs:__imp_RaiseException
0x18000b67c  nop
0x18000b67d  mov     eax, r12d
0x18000b680  xchg    eax, cs:?s_registered@StaticsCache@Internal@System@Windows@@0V?$slim_event_t@$00@wil@@A; wil::slim_event_t<1> Windows::System::Internal::StaticsCache::s_registered
0x18000b686  mov     rcx, r15; SRWLock
0x18000b689  call    cs:__imp_ReleaseSRWLockShared
0x18000b68f  mov     edx, 7530h
0x18000b694  lea     rcx, ?s_registered@StaticsCache@Internal@System@Windows@@0V?$slim_event_t@$00@wil@@A; wil::slim_event_t<1> Windows::System::Internal::StaticsCache::s_registered
0x18000b69b  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x18000b6a0  test    al, al
0x18000b6a2  jnz     loc_18000B56C
0x18000b6a8  jmp     loc_18000B5F6
0x18000b6ad  add     rbx, 10h
0x18000b6b1  jmp     loc_18000B580
0x18000b6b6  lea     eax, [rdx+1]
0x18000b6b9  cmp     eax, edx
0x18000b6bb  jb      short loc_18000B666
0x18000b6bd  lea     r9, [rbp+2E0h+string]; string
0x18000b6c4  lea     r8, [rbp+2E0h+hstringHeader]; hstringHeader
0x18000b6cb  mov     rcx, rsi; sourceString
0x18000b6ce  call    cs:__imp_WindowsCreateStringReference
0x18000b6d4  test    eax, eax
0x18000b6d6  js      loc_18000C204
0x18000b6dc  lea     r9, [rbp+2E0h+var_2B8]
0x18000b6e0  mov     r8d, [rbp+2E0h+var_2D8]
0x18000b6e4  mov     rdx, [rbp+2E0h+string]
0x18000b6eb  mov     rcx, rbx
0x18000b6ee  mov     rax, [rdi+90h]
0x18000b6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6fa  mov     rcx, [rsp+368h]; this
0x18000b702  test    eax, eax
0x18000b704  js      loc_18000BED2
0x18000b70a  mov     rcx, [rsp+368h]; this
0x18000b712  mov     rbx, [rbp+2E0h+var_2B8]
0x18000b716  test    rbx, rbx
0x18000b719  jz      loc_18000BC4B
0x18000b71f  mov     [rbp+2E0h+var_288], rbx
0x18000b723  test    rbx, rbx
0x18000b726  jz      short loc_18000B738
0x18000b728  mov     rax, [rbx]
0x18000b72b  mov     rcx, rbx
0x18000b72e  mov     rax, [rax+8]
0x18000b732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b737  nop
0x18000b738  mov     [rbp+2E0h+var_2B0], r12
0x18000b73c  mov     [rbp+2E0h+var_298], r12d
0x18000b740  mov     [rbp+2E0h+var_290], r12
0x18000b744  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18000b74b  lea     rdx, [rbp+2E0h+var_290]
0x18000b74f  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x18000b756  mov     rax, [rax+38h]
0x18000b75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75f  xor     edx, edx; Val
0x18000b761  mov     r8d, 1A0h; Size
0x18000b767  lea     rcx, [rbp+2E0h+var_1E0]; void *
0x18000b76e  call    memset_0
0x18000b773  nop
0x18000b774  mov     rax, [rbx]
0x18000b777  mov     rdi, [rax]
0x18000b77a  mov     rcx, [rbp+2E0h+var_2B0]
0x18000b77e  test    rcx, rcx
0x18000b781  jz      short loc_18000B794
0x18000b783  mov     [rbp+2E0h+var_2B0], r12
0x18000b787  mov     rdx, [rcx]
0x18000b78a  mov     rax, [rdx+10h]
0x18000b78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b793  nop
0x18000b794  lea     r8, [rbp+2E0h+var_2B0]
0x18000b798  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x18000b79f  mov     rcx, rbx
0x18000b7a2  mov     rax, rdi
0x18000b7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7aa  nop
0x18000b7ab  mov     rcx, [rsp+368h]; this
0x18000b7b3  test    eax, eax
0x18000b7b5  js      loc_18000BF11
0x18000b7bb  test    r14, r14
0x18000b7be  jnz     loc_18000BACF
0x18000b7c4  mov     [rbp+2E0h+var_2E0], r14b
0x18000b7c8  mov     qword ptr [rbp+2E0h+var_2C8], r12
0x18000b7cc  lea     rax, [rbp+2E0h+var_2E0]
0x18000b7d0  mov     qword ptr [rbp+2E0h+hstringHeader.Reserved], rax
0x18000b7d7  mov     byte ptr [rbp+2E0h+hstringHeader.Reserved+8], 1
0x18000b7de  mov     [rbp+2E0h+TokenHandle], r12
0x18000b7e2  xor     ecx, ecx; BindingHandle
0x18000b7e4  call    cs:__imp_RpcImpersonateClient
0x18000b7ea  cmp     eax, 6BDh
0x18000b7ef  jz      loc_18000C0E3
0x18000b7f5  mov     ecx, eax; Status
0x18000b7f7  call    cs:__imp_I_RpcMapWin32Status
0x18000b7fd  mov     ecx, eax; Status
0x18000b7ff  call    cs:__imp_RtlNtStatusToDosError
0x18000b805  test    eax, eax
0x18000b807  jle     short loc_18000B811
0x18000b809  movzx   eax, ax
0x18000b80c  or      eax, 80070000h
0x18000b811  mov     rcx, [rsp+368h]; this
0x18000b819  test    eax, eax
0x18000b81b  js      loc_18000BF3B
0x18000b821  mov     [rbp+2E0h+var_2E0], 1
0x18000b825  call    cs:__imp_GetCurrentThread
0x18000b82b  mov     rcx, rax; ThreadHandle
0x18000b82e  lea     r9, [rbp+2E0h+TokenHandle]; TokenHandle
0x18000b832  mov     edx, 8; DesiredAccess
0x18000b837  mov     r8d, 1; OpenAsSelf
0x18000b83d  call    cs:__imp_OpenThreadToken
0x18000b843  mov     rcx, [rsp+368h]; this
0x18000b84b  test    eax, eax
0x18000b84d  jz      loc_18000C000
0x18000b853  cmp     [rbp+2E0h+var_2E0], 0
0x18000b857  jz      short loc_18000B860
0x18000b859  call    cs:__imp_RpcRevertToSelf
0x18000b85f  nop
0x18000b860  mov     rcx, qword ptr [rbp+2E0h+var_2C8]; hObject
0x18000b864  lea     rax, [rcx-1]
0x18000b868  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b86c  jbe     loc_18000C236
0x18000b872  mov     [rbp+2E0h+var_2C8], r12d
0x18000b876  mov     rdi, [rbp+2E0h+TokenHandle]
0x18000b87a  mov     [rbp+2E0h+var_1E0], 100h
0x18000b883  mov     [rbp+2E0h+var_1D4], 0
0x18000b88a  mov     [rbp+2E0h+TokenInformation], r15d
0x18000b891  mov     rcx, rdi; void *
0x18000b894  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x18000b899  mov     byte ptr [rbp+2E0h+var_1E0+1], al
0x18000b89f  mov     edx, 7; unsigned int
0x18000b8a4  mov     rcx, rdi; void *
0x18000b8a7  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000b8ac  mov     byte ptr [rbp+2E0h+var_1E0], al
0x18000b8b2  mov     [rbp+2E0h+var_1DC], r12d
0x18000b8b9  mov     edx, 1Dh; unsigned int
0x18000b8be  mov     rcx, rdi; void *
0x18000b8c1  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000b8c6  movzx   eax, al
0x18000b8c9  mov     [rbp+2E0h+var_160], eax
0x18000b8cf  mov     [rbp+2E0h+var_2D8], r12d
0x18000b8d3  mov     [rbp+2E0h+var_1D4], 0
0x18000b8da  lea     r8, [rbp+2E0h+var_2D8]
0x18000b8de  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x18000b8e5  mov     rcx, rdi
0x18000b8e8  call    cs:__imp_CheckTokenCapability
0x18000b8ee  test    eax, eax
0x18000b8f0  jz      loc_18000C181
0x18000b8f6  cmp     [rbp+2E0h+var_2D8], 0
0x18000b8fa  jz      loc_18000BD5C
0x18000b900  mov     [rbp+2E0h+var_1D4], 1
0x18000b907  mov     eax, r12d
0x18000b90a  mov     rcx, [rsp+368h]; this
0x18000b912  test    eax, eax
0x18000b914  js      loc_18000BF26
0x18000b91a  mov     [rbp+2E0h+packageFullNameLength], r12d
0x18000b91e  lea     rax, [rbp+2E0h+packageFullNameLength]
0x18000b922  mov     [rsp+360h+ReturnLength], rax; ReturnLength
0x18000b927  mov     r9d, 4; TokenInformationLength
0x18000b92d  lea     r8, [rbp+2E0h+TokenInformation]; TokenInformation
0x18000b934  mov     edx, 0Ch; TokenInformationClass
0x18000b939  mov     rcx, rdi; TokenHandle
0x18000b93c  call    cs:__imp_GetTokenInformation
0x18000b942  mov     rcx, [rsp+368h]; this
0x18000b94a  test    eax, eax
0x18000b94c  jz      loc_18000BFCA
0x18000b952  lea     rax, [rbp+2E0h+var_2C8]
0x18000b956  mov     [rsp+360h+ReturnLength], rax; ReturnLength
0x18000b95b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000b961  lea     r8, [rbp+2E0h+PrincipalSelfSid]; TokenInformation
0x18000b968  mov     edx, 1; TokenInformationClass
0x18000b96d  mov     rcx, rdi; TokenHandle
0x18000b970  call    cs:__imp_GetTokenInformation
0x18000b976  mov     rcx, [rsp+368h]; this
0x18000b97e  test    eax, eax
0x18000b980  jz      loc_18000BFDC
0x18000b986  mov     rdx, [rbp+2E0h+PrincipalSelfSid]; PrincipalSelfSid
0x18000b98d  mov     [rbp+2E0h+var_168], rdx
0x18000b994  xorps   xmm0, xmm0
0x18000b997  xor     eax, eax
0x18000b999  movups  xmmword ptr [rbp+2E0h+hstringHeader.Reserved], xmm0
0x18000b9a0  mov     dword ptr [rbp+2E0h+hstringHeader.Reserved+10h], eax
0x18000b9a6  mov     [rbp+2E0h+var_2D4], r12d
0x18000b9aa  mov     [rbp+2E0h+var_2D8], r12d
0x18000b9ae  mov     [rbp+2E0h+var_2DC], 14h
0x18000b9b5  mov     [rbp+2E0h+packageFullNameLength], r12d
0x18000b9b9  mov     [rbp+2E0h+var_1DE], al
0x18000b9bf  test    rdx, rdx
0x18000b9c2  jz      loc_18000C055
0x18000b9c8  lea     rax, [rbp+2E0h+var_2D8]
0x18000b9cc  mov     [rsp+360h+AccessStatus], rax; AccessStatus
0x18000b9d1  lea     rax, [rbp+2E0h+var_2D4]
0x18000b9d5  mov     [rsp+360h+GrantedAccess], rax; GrantedAccess
0x18000b9da  lea     rax, [rbp+2E0h+var_2DC]
0x18000b9de  mov     [rsp+360h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000b9e3  lea     rax, [rbp+2E0h+hstringHeader]
0x18000b9ea  mov     [rsp+360h+PrivilegeSet], rax; PrivilegeSet
0x18000b9ef  lea     rax, GenericMapping
0x18000b9f6  mov     [rsp+360h+GenericMapping], rax; GenericMapping
0x18000b9fb  mov     [rsp+360h+ObjectTypeListLength], r12d; ObjectTypeListLength
0x18000ba00  mov     [rsp+360h+ReturnLength], r12; int
0x18000ba05  mov     r9d, 1; DesiredAccess
0x18000ba0b  mov     r8, rdi; ClientToken
0x18000ba0e  lea     rcx, qword_18010A700; pSecurityDescriptor
0x18000ba15  call    cs:__imp_AccessCheckByType
0x18000ba1b  mov     rcx, [rsp+368h]; this
0x18000ba23  test    eax, eax
0x18000ba25  jz      loc_18000BFEE
0x18000ba2b  cmp     [rbp+2E0h+var_2D8], 0
0x18000ba2f  jz      short loc_18000BA3E
0x18000ba31  test    byte ptr [rbp+2E0h+var_2D4], 1
0x18000ba35  jz      short loc_18000BA3E
0x18000ba37  mov     [rbp+2E0h+var_1DE], 1
0x18000ba3e  mov     [rbp+2E0h+var_1DC], r12d
0x18000ba45  xorps   xmm0, xmm0
0x18000ba48  movups  [rbp+2E0h+var_278], xmm0
0x18000ba4c  movups  [rbp+2E0h+var_268], xmm0
0x18000ba50  movups  [rbp+2E0h+var_258], xmm0
  ... truncated ...
```
