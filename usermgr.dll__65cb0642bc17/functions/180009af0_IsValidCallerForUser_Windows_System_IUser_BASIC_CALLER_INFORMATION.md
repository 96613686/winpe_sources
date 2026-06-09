# IsValidCallerForUser(Windows::System::IUser *,_BASIC_CALLER_INFORMATION *)

- ea: `0x180009af0`
- end: `0x18000a490`
- name: `?IsValidCallerForUser@@YAJPEAUIUser@System@Windows@@PEAU_BASIC_CALLER_INFORMATION@@@Z`
- size: `2464`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, struct _BASIC_CALLER_INFORMATION *)`
- caller_count: `14`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027e60`
- `0x180035c50`
- `0x18003734c`
- `0x18003b764`
- `0x18003e674`
- `0x180042b80`
- `0x180043b10`
- `0x1800458e0`
- `0x18007c550`
- `0x18007e570`
- `0x18007e810`
- `0x18007ecf0`
- `0x1800b2614`
- `0x1800b2ff4`

## callees

- `0x1800088e8`
- `0x180009af0`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000acdc`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x18006f1c9`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a081`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009d7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a081`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000a2d7`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180009e20`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180009e20`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a3a8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009fac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a45b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a46e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009fcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009fcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a029`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009f6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a3d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a360`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a372`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000a372`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009c45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009c45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a484`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009fb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a01e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009fb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a01e`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180009cf3`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a304`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180009cf3`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000a304`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a0b0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a2a7`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a0b0`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000a2a7`
- `ntdll!RtlNtStatusToDosError` at `0x180009c07`
- `ntdll!RtlNtStatusToDosError` at `0x180009c07`
- `ntdll!RtlEqualSid` at `0x18000a007`
- `ntdll!RtlEqualSid` at `0x18000a007`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a0c6`
- `ntdll!RtlIsMultiSessionSku` at `0x18000a0c6`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009eda`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180009eda`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009bff`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009bff`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009e92`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180009e92`
- `RPCRT4!RpcRevertToSelf` at `0x180009c61`
- `RPCRT4!RpcRevertToSelf` at `0x180009c61`
- `RPCRT4!RpcImpersonateClient` at `0x180009bec`
- `RPCRT4!RpcImpersonateClient` at `0x180009bec`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000a1fb`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000a1fb`

## string_xrefs

- `0x18000a415`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000a190`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a1a5`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a21f`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a231`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a243`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a255`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a267`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a3be`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a437`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a449`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000a14b`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a163`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a17b`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a27c`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a326`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a338`: `onecore\ds\security\umstartup\usermgr\lib\userhelpers.cpp`
- `0x18000a1d0`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x18000a3ea`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall IsValidCallerForUser(struct Windows::System::IUser *a1, struct _BASIC_CALLER_INFORMATION *a2)
{
  unsigned __int64 v2; // rbp
  __int64 (__fastcall *v5)(struct Windows::System::IUser *, GUID *, unsigned __int64); // rdi
  __int64 v6; // rcx
  int v7; // eax
  wil::details::in1diag3 *v8; // rcx
  RPC_STATUS v9; // eax
  NTSTATUS v10; // eax
  signed int v11; // eax
  HANDLE CurrentThread; // rax
  const char *v13; // r9
  char *v14; // rcx
  void *v15; // rdi
  const char *v16; // r9
  int v17; // eax
  const char *v18; // r9
  const char *v19; // r9
  void *v20; // rdx
  const char *v21; // r9
  int v22; // eax
  DWORD CurrentProcessId; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, unsigned __int64); // rdi
  int v29; // eax
  __int64 v30; // r15
  unsigned int (__fastcall *v31)(__int64, PCWSTR, unsigned __int64); // r12
  void *v32; // rsi
  DWORD v33; // edi
  PCWSTR StringRawBuffer; // rax
  const char *v35; // r9
  void *v36; // rcx
  char v37; // r15
  __int64 v38; // r14
  int v41; // eax
  DWORD v42; // eax
  unsigned int PackageFullNameFromToken; // eax
  const char *v45; // r9
  char *v47; // rsi
  HANDLE CurrentProcess; // rax
  const char *v49; // r9
  const char *v50; // r9
  bool v51; // sf
  DWORD LastError; // edi
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  _BYTE v54[4]; // [rsp+80h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+2F8h]

  v2 = (unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = a1;
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)a1 + 8LL))(a1);
  *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
  *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) = 0;
  *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
  (*(void (__fastcall **)(void *, unsigned __int64))(Windows::System::Internal::Adapters::g_AdapterCollection + 56LL))(
    &Windows::System::Internal::Adapters::g_AdapterCollection,
    v2 + 56);
  memset_0((void *)(v2 + 256), 0, 0x1A0u);
  v5 = **(__int64 (__fastcall ***)(struct Windows::System::IUser *, GUID *, unsigned __int64))a1;
  v6 = *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
  if ( v6 )
  {
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = v5(a1, &GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58, v2 + 40);
  v8 = retaddr;
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
      (const char *)(unsigned int)v7,
      ReturnLength);
  if ( !a2 )
  {
    *(_BYTE *)v2 = 0;
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = (unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL;
    *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE8) = 1;
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v9 = RpcImpersonateClient(0);
    if ( v9 == 1725 )
    {
      v47 = *(char **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      if ( (unsigned __int64)(v47 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v47);
        SetLastError(LastError);
      }
      *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xAu, (PHANDLE)(v2 + 24)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v49);
      if ( !DuplicateTokenEx(
              *(HANDLE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
              0,
              0,
              SecurityImpersonation,
              TokenImpersonation,
              (PHANDLE)(v2 + 32)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v50);
    }
    else
    {
      v10 = I_RpcMapWin32Status(v9);
      v11 = RtlNtStatusToDosError(v10);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          (const char *)(unsigned int)v11,
          ReturnLength);
      *(_BYTE *)v2 = 1;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)(v2 + 32)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v13);
    }
    if ( *(_BYTE *)v2 )
      RpcRevertToSelf();
    v14 = *(char **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v15 = *(void **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    *(_WORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x100) = 256;
    *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 0;
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x108) = -1;
    *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x101) = IsTokenAppContainer(v15);
    *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x100) = DoesTokenHasPrivilege(v15, 7u);
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = 0;
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x180) = DoesTokenHasPrivilege(v15, 0x1Du);
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 0;
    if ( !(unsigned int)CheckTokenCapability(v15, &CapMumaSidBuffer, v2 + 16) )
    {
      v17 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x184,
              (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
              v16);
LABEL_20:
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1E0,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          (const char *)(unsigned int)v17,
          ReturnLength);
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
      if ( !GetTokenInformation(v15, TokenSessionId, (LPVOID)(v2 + 264), 4u, (PDWORD)(v2 + 12)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1AE,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v18);
      if ( !GetTokenInformation(v15, TokenUser, (LPVOID)(v2 + 288), 0x54u, (PDWORD)(v2 + 24)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1E2,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v19);
      v20 = *(void **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x120);
      *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x178) = v20;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = 0;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF0) = 0;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
      *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x102) = 0;
      if ( !v20 )
      {
        if ( !GetTokenInformation(v15, TokenUser, (LPVOID)(v2 + 96), 0x54u, (PDWORD)(v2 + 12)) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x10B,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v45);
        v20 = *(void **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60);
      }
      if ( !AccessCheckByType(
              qword_18010A700,
              v20,
              v15,
              1u,
              0,
              0,
              (PGENERIC_MAPPING)&GenericMapping,
              (PPRIVILEGE_SET)(v2 + 224),
              (LPDWORD)(v2 + 4),
              (LPDWORD)(v2 + 8),
              (LPBOOL)(v2 + 16)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x119,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v21);
      if ( *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10)
        && (*(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) & 1) != 0 )
      {
        *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x102) = 1;
      }
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xB8) = 0;
      *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8) = 0;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x60) = 3;
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x64) = 112;
      v22 = RpcServerInqCallAttributesW(0, (void *)(v2 + 96));
      if ( v22 )
      {
        if ( v22 != 1725 )
        {
          v51 = v22 < 0;
          if ( v22 > 0 )
          {
            v22 = (unsigned __int16)v22 | 0x80070000;
            v51 = v22 < 0;
          }
          if ( v51 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5A,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
              (const char *)(unsigned int)v22,
              ReturnLength);
          goto LABEL_31;
        }
        CurrentProcessId = GetCurrentProcessId();
      }
      else
      {
        CurrentProcessId = *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA0);
      }
      *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x104) = CurrentProcessId;
LABEL_31:
      if ( !*(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x101)
        || (*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 128,
            PackageFullNameFromToken = GetPackageFullNameFromToken(v15, (UINT32 *)(v2 + 12), (PWSTR)(v2 + 388)),
            PackageFullNameFromToken == 15700) )
      {
        *(_WORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x184) = 0;
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
      a2 = (struct _BASIC_CALLER_INFORMATION *)(v2 + 256);
      v8 = *(wil::details::in1diag3 **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
      if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v8);
      goto LABEL_35;
    }
    if ( *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
    {
LABEL_18:
      *(_BYTE *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10C) = 1;
LABEL_19:
      v17 = 0;
      goto LABEL_20;
    }
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
    *(_OWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xE0) = 0;
    *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0xF0) = 0;
    v37 = 0;
    v38 = (__int64)v15;
    if ( !v15 )
      v38 = -6;
    if ( !GetTokenInformation((HANDLE)v38, TokenIsAppContainer, (LPVOID)(v2 + 8), 4u, (PDWORD)(v2 + 12)) )
      goto LABEL_70;
    if ( !*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
    {
      if ( !(unsigned int)CheckTokenMembershipEx(
                            v38,
                            &CapMumaGroupSidBuffer,
                            *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                            v2 + 4) )
        goto LABEL_70;
      if ( !*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      {
        if ( !(unsigned __int8)RtlIsMultiSessionSku()
          && !(unsigned int)CheckTokenMembershipEx(
                              v38,
                              &DefaultAliasWellKnownSid,
                              *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                              v2 + 4) )
        {
LABEL_70:
          v42 = GetLastError();
          if ( v42 )
          {
            v17 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x18D,
                    (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                    (const char *)v42,
                    ReturnLength);
            goto LABEL_20;
          }
LABEL_60:
          if ( !*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) && !v37 )
            goto LABEL_19;
          goto LABEL_18;
        }
        if ( !*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
          goto LABEL_60;
      }
    }
    if ( *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
    {
      if ( !(unsigned int)CheckTokenCapability(v38, &CapMumaSidBuffer, v2 + 4) )
        goto LABEL_70;
      if ( !*(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_60;
    }
    v37 = 1;
    goto LABEL_60;
  }
LABEL_35:
  if ( *((_DWORD *)a2 + 2) != (unsigned int)RtlGetCurrentServiceSessionId(v8) )
  {
    v41 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(((unsigned __int64)v54
                                                                             & 0xFFFFFFFFFFFFFFE0uLL)
                                                                            + 0x28)
                                                              + 96LL))(
            *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28),
            v2 + 48);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)(unsigned int)v41,
        ReturnLength);
    if ( *((_DWORD *)a2 + 2) != *(_DWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x30) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)0x80070520LL,
        ReturnLength);
  }
  if ( !*((_BYTE *)a2 + 12) )
  {
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    v27 = *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
    v28 = *(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v27 + 72LL);
    WindowsDeleteString(0);
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
    v29 = v28(v27, v2 + 32);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)(unsigned int)v29,
        ReturnLength);
    v30 = *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
    v31 = *(unsigned int (__fastcall **)(__int64, PCWSTR, unsigned __int64))(*(_QWORD *)v30 + 40LL);
    v32 = *(void **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v32 )
    {
      v33 = GetLastError();
      LocalFree(v32);
      SetLastError(v33);
    }
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20), 0);
    if ( !v31(v30, StringRawBuffer, v2 + 24) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        v35);
    if ( !RtlEqualSid(*((PSID *)a2 + 15), *(PSID *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18)) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\userhelpers.cpp",
        (const char *)0x80070520LL,
        ReturnLength);
    v36 = *(void **)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( v36 )
      LocalFree(v36);
    WindowsDeleteString(*(HSTRING *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20));
  }
  v24 = *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38);
  if ( v24 )
  {
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x38) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28);
  if ( v25 )
  {
    *(_QWORD *)(((unsigned __int64)v54 & 0xFFFFFFFFFFFFFFE0uLL) + 0x28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180009af0  push    rbp
0x180009af2  push    rbx
0x180009af3  push    rsi
0x180009af4  push    rdi
0x180009af5  push    r12
0x180009af7  push    r13
0x180009af9  push    r14
0x180009afb  push    r15
0x180009afd  sub     rsp, 338h
0x180009b04  lea     rbp, [rsp+80h]
0x180009b0c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180009b10  mov     rax, cs:__security_cookie
0x180009b17  xor     rax, rsp
0x180009b1a  mov     [rbp+2F0h+var_50], rax
0x180009b21  mov     r14, rdx
0x180009b24  mov     rbx, rcx
0x180009b27  mov     [rbp+2F0h+var_2B0], rcx
0x180009b2b  test    rcx, rcx
0x180009b2e  jz      short loc_180009B3D
0x180009b30  mov     rax, [rcx]
0x180009b33  mov     rax, [rax+8]
0x180009b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3c  nop
0x180009b3d  xor     r13d, r13d
0x180009b40  mov     [rbp+2F0h+var_2C8], r13
0x180009b44  mov     [rbp+2F0h+var_2C0], r13d
0x180009b48  mov     [rbp+2F0h+var_2B8], r13
0x180009b4c  mov     rax, cs:?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180009b53  lea     rdx, [rbp+2F0h+var_2B8]
0x180009b57  lea     rcx, ?g_AdapterCollection@Adapters@Internal@System@Windows@@3VAdapterCollection@1234@A; Windows::System::Internal::Adapters::AdapterCollection Windows::System::Internal::Adapters::g_AdapterCollection
0x180009b5e  mov     rax, [rax+38h]
0x180009b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b67  xor     edx, edx; Val
0x180009b69  mov     r8d, 1A0h; Size
0x180009b6f  lea     rcx, [rbp+2F0h+var_1F0]; void *
0x180009b76  call    memset_0
0x180009b7b  nop
0x180009b7c  mov     rax, [rbx]
0x180009b7f  mov     rdi, [rax]
0x180009b82  mov     rcx, [rbp+2F0h+var_2C8]
0x180009b86  test    rcx, rcx
0x180009b89  jz      short loc_180009B9C
0x180009b8b  mov     [rbp+2F0h+var_2C8], r13
0x180009b8f  mov     rdx, [rcx]
0x180009b92  mov     rax, [rdx+10h]
0x180009b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b9b  nop
0x180009b9c  lea     r8, [rbp+2F0h+var_2C8]
0x180009ba0  lea     rdx, _GUID_ebe7ab25_f6a9_4472_9fa2_e979ef15ff58
0x180009ba7  mov     rcx, rbx
0x180009baa  mov     rax, rdi
0x180009bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb2  nop
0x180009bb3  mov     rcx, [rsp+378h]; this
0x180009bbb  test    eax, eax
0x180009bbd  js      loc_18000A178
0x180009bc3  test    r14, r14
0x180009bc6  jnz     loc_180009EDA
0x180009bcc  mov     [rbp+2F0h+var_2F0], r14b
0x180009bd0  mov     qword ptr [rbp+2F0h+var_2D8], r13
0x180009bd4  lea     rax, [rbp+2F0h+var_2F0]
0x180009bd8  mov     qword ptr [rbp+2F0h+var_210.PrivilegeCount], rax
0x180009bdf  mov     byte ptr [rbp+2F0h+var_210.Privilege.Luid.LowPart], 1
0x180009be6  mov     [rbp+2F0h+TokenHandle], r13
0x180009bea  xor     ecx, ecx; BindingHandle
0x180009bec  call    cs:__imp_RpcImpersonateClient
0x180009bf2  cmp     eax, 6BDh
0x180009bf7  jz      loc_18000A34A
0x180009bfd  mov     ecx, eax; Status
0x180009bff  call    cs:__imp_I_RpcMapWin32Status
0x180009c05  mov     ecx, eax; Status
0x180009c07  call    cs:__imp_RtlNtStatusToDosError
0x180009c0d  test    eax, eax
0x180009c0f  jle     short loc_180009C19
0x180009c11  movzx   eax, ax
0x180009c14  or      eax, 80070000h
0x180009c19  mov     rcx, [rsp+378h]; this
0x180009c21  test    eax, eax
0x180009c23  js      loc_18000A1A2
0x180009c29  mov     [rbp+2F0h+var_2F0], 1
0x180009c2d  call    cs:__imp_GetCurrentThread
0x180009c33  mov     rcx, rax; ThreadHandle
0x180009c36  lea     r9, [rbp+2F0h+TokenHandle]; TokenHandle
0x180009c3a  mov     edx, 8; DesiredAccess
0x180009c3f  mov     r8d, 1; OpenAsSelf
0x180009c45  call    cs:__imp_OpenThreadToken
0x180009c4b  mov     rcx, [rsp+378h]; this
0x180009c53  test    eax, eax
0x180009c55  jz      loc_18000A267
0x180009c5b  cmp     [rbp+2F0h+var_2F0], 0
0x180009c5f  jz      short loc_180009C68
0x180009c61  call    cs:__imp_RpcRevertToSelf
0x180009c67  nop
0x180009c68  mov     rcx, qword ptr [rbp+2F0h+var_2D8]; hObject
0x180009c6c  lea     rax, [rcx-1]
0x180009c70  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009c74  jbe     loc_18000A479
0x180009c7a  mov     [rbp+2F0h+var_2D8], r13d
0x180009c7e  mov     rdi, [rbp+2F0h+TokenHandle]
0x180009c82  mov     [rbp+2F0h+var_1F0], 100h
0x180009c8b  mov     [rbp+2F0h+var_1E4], 0
0x180009c92  mov     [rbp+2F0h+TokenInformation], 0FFFFFFFFh
0x180009c9c  mov     rcx, rdi; void *
0x180009c9f  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x180009ca4  mov     byte ptr [rbp+2F0h+var_1F0+1], al
0x180009caa  mov     edx, 7; unsigned int
0x180009caf  mov     rcx, rdi; void *
0x180009cb2  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x180009cb7  mov     byte ptr [rbp+2F0h+var_1F0], al
0x180009cbd  mov     [rbp+2F0h+var_1EC], r13d
0x180009cc4  mov     edx, 1Dh; unsigned int
0x180009cc9  mov     rcx, rdi; void *
0x180009ccc  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x180009cd1  movzx   eax, al
0x180009cd4  mov     [rbp+2F0h+var_170], eax
0x180009cda  mov     [rbp+2F0h+var_2E0], r13d
0x180009cde  mov     [rbp+2F0h+var_1E4], 0
0x180009ce5  lea     r8, [rbp+2F0h+var_2E0]
0x180009ce9  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x180009cf0  mov     rcx, rdi
0x180009cf3  call    cs:__imp_CheckTokenCapability
0x180009cf9  test    eax, eax
0x180009cfb  jz      loc_18000A3E2
0x180009d01  cmp     [rbp+2F0h+var_2E0], 0
0x180009d05  jz      loc_18000A034
0x180009d0b  mov     [rbp+2F0h+var_1E4], 1
0x180009d12  mov     eax, r13d
0x180009d15  mov     rcx, [rsp+378h]; this
0x180009d1d  test    eax, eax
0x180009d1f  js      loc_18000A18D
0x180009d25  mov     [rbp+2F0h+packageFullNameLength], r13d
0x180009d29  lea     rax, [rbp+2F0h+packageFullNameLength]
0x180009d2d  mov     [rsp+370h+ReturnLength], rax; ReturnLength
0x180009d32  mov     r9d, 4; TokenInformationLength
0x180009d38  lea     r8, [rbp+2F0h+TokenInformation]; TokenInformation
0x180009d3f  mov     edx, 0Ch; TokenInformationClass
0x180009d44  mov     rcx, rdi; TokenHandle
0x180009d47  call    cs:__imp_GetTokenInformation
0x180009d4d  mov     rcx, [rsp+378h]; this
0x180009d55  test    eax, eax
0x180009d57  jz      loc_18000A243
0x180009d5d  lea     rax, [rbp+2F0h+var_2D8]
0x180009d61  mov     [rsp+370h+ReturnLength], rax; ReturnLength
0x180009d66  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180009d6c  lea     r8, [rbp+2F0h+PrincipalSelfSid]; TokenInformation
0x180009d73  mov     edx, 1; TokenInformationClass
0x180009d78  mov     rcx, rdi; TokenHandle
0x180009d7b  call    cs:__imp_GetTokenInformation
0x180009d81  mov     rcx, [rsp+378h]; this
0x180009d89  test    eax, eax
0x180009d8b  jz      loc_18000A231
0x180009d91  mov     rdx, [rbp+2F0h+PrincipalSelfSid]; PrincipalSelfSid
0x180009d98  mov     [rbp+2F0h+var_178], rdx
0x180009d9f  xorps   xmm0, xmm0
0x180009da2  xor     eax, eax
0x180009da4  movups  xmmword ptr [rbp+2F0h+var_210.PrivilegeCount], xmm0
0x180009dab  mov     [rbp+2F0h+var_210.Privilege.Attributes], eax
0x180009db1  mov     [rbp+2F0h+var_2E8], r13d
0x180009db5  mov     [rbp+2F0h+var_2E0], r13d
0x180009db9  mov     [rbp+2F0h+var_2EC], 14h
0x180009dc0  mov     [rbp+2F0h+packageFullNameLength], r13d
0x180009dc4  mov     [rbp+2F0h+var_1EE], al
0x180009dca  test    rdx, rdx
0x180009dcd  jz      loc_18000A2BC
0x180009dd3  lea     rax, [rbp+2F0h+var_2E0]
0x180009dd7  mov     [rsp+370h+AccessStatus], rax; AccessStatus
0x180009ddc  lea     rax, [rbp+2F0h+var_2E8]
0x180009de0  mov     [rsp+370h+GrantedAccess], rax; GrantedAccess
0x180009de5  lea     rax, [rbp+2F0h+var_2EC]
0x180009de9  mov     [rsp+370h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180009dee  lea     rax, [rbp+2F0h+var_210]
0x180009df5  mov     [rsp+370h+PrivilegeSet], rax; PrivilegeSet
0x180009dfa  lea     rax, GenericMapping
0x180009e01  mov     [rsp+370h+GenericMapping], rax; GenericMapping
0x180009e06  mov     [rsp+370h+ObjectTypeListLength], r13d; ObjectTypeListLength
0x180009e0b  mov     [rsp+370h+ReturnLength], r13; int
0x180009e10  mov     r9d, 1; DesiredAccess
0x180009e16  mov     r8, rdi; ClientToken
0x180009e19  lea     rcx, qword_18010A700; pSecurityDescriptor
0x180009e20  call    cs:__imp_AccessCheckByType
0x180009e26  mov     rcx, [rsp+378h]; this
0x180009e2e  test    eax, eax
0x180009e30  jz      loc_18000A255
0x180009e36  cmp     [rbp+2F0h+var_2E0], 0
0x180009e3a  jz      short loc_180009E49
0x180009e3c  test    byte ptr [rbp+2F0h+var_2E8], 1
0x180009e40  jz      short loc_180009E49
0x180009e42  mov     [rbp+2F0h+var_1EE], 1
0x180009e49  mov     [rbp+2F0h+var_1EC], r13d
0x180009e50  xorps   xmm0, xmm0
0x180009e53  movups  [rbp+2F0h+var_288], xmm0
0x180009e57  movups  [rbp+2F0h+var_278], xmm0
0x180009e5b  movups  [rbp+2F0h+var_268], xmm0
0x180009e62  movups  [rbp+2F0h+var_258], xmm0
0x180009e69  movups  [rbp+2F0h+var_248], xmm0
0x180009e70  movups  [rbp+2F0h+var_238], xmm0
0x180009e77  movups  [rbp+2F0h+var_228], xmm0
0x180009e7e  mov     dword ptr [rbp+2F0h+RpcCallAttributes], 3
0x180009e85  mov     dword ptr [rbp+2F0h+RpcCallAttributes+4], 70h ; 'p'
0x180009e8c  lea     rdx, [rbp+2F0h+RpcCallAttributes]; RpcCallAttributes
0x180009e90  xor     ecx, ecx; ClientBinding
0x180009e92  call    cs:__imp_RpcServerInqCallAttributesW
0x180009e98  test    eax, eax
0x180009e9a  jnz     loc_18000A3D0
0x180009ea0  mov     eax, dword ptr [rbp+2F0h+var_258+8]
0x180009ea6  mov     [rbp+2F0h+var_1EC], eax
0x180009eac  cmp     byte ptr [rbp+2F0h+var_1F0+1], 0
0x180009eb3  jnz     loc_18000A1E6
0x180009eb9  mov     [rbp+2F0h+packageFullName], r13w
0x180009ec1  lea     r14, [rbp+2F0h+var_1F0]
0x180009ec8  mov     rcx, [rbp+2F0h+TokenHandle]; hObject
0x180009ecc  lea     rax, [rcx-1]
0x180009ed0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009ed4  jbe     loc_18000A484
0x180009eda  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180009ee0  cmp     [r14+8], eax
0x180009ee4  jnz     loc_18000A107
0x180009eea  cmp     byte ptr [r14+0Ch], 0
0x180009eef  jz      short loc_180009F5A
0x180009ef1  mov     rcx, [rbp+2F0h+var_2B8]
0x180009ef5  test    rcx, rcx
0x180009ef8  jz      short loc_180009F0B
0x180009efa  mov     [rbp+2F0h+var_2B8], r13
0x180009efe  mov     rax, [rcx]
0x180009f01  mov     rax, [rax+10h]
0x180009f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f0a  nop
0x180009f0b  mov     rcx, [rbp+2F0h+var_2C8]
0x180009f0f  test    rcx, rcx
0x180009f12  jz      short loc_180009F25
0x180009f14  mov     [rbp+2F0h+var_2C8], r13
0x180009f18  mov     rax, [rcx]
0x180009f1b  mov     rax, [rax+10h]
0x180009f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f24  nop
0x180009f25  mov     rax, [rbx]
0x180009f28  mov     rcx, rbx
0x180009f2b  mov     rax, [rax+10h]
0x180009f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f34  nop
0x180009f35  xor     eax, eax
0x180009f37  mov     rcx, [rbp+2F0h+var_50]
0x180009f3e  xor     rcx, rsp; StackCookie
0x180009f41  call    __security_check_cookie
0x180009f46  add     rsp, 338h
0x180009f4d  pop     r15
0x180009f4f  pop     r14
0x180009f51  pop     r13
0x180009f53  pop     r12
0x180009f55  pop     rdi
0x180009f56  pop     rsi
0x180009f57  pop     rbx
0x180009f58  pop     rbp
0x180009f59  retn
0x180009f5a  mov     [rbp+2F0h+TokenHandle], r13
0x180009f5e  mov     qword ptr [rbp+2F0h+var_2D8], r13
0x180009f62  mov     rsi, [rbp+2F0h+var_2C8]
0x180009f66  mov     rax, [rsi]
0x180009f69  mov     rdi, [rax+48h]
0x180009f6d  xor     ecx, ecx; string
0x180009f6f  call    cs:__imp_WindowsDeleteString
0x180009f75  mov     [rbp+2F0h+TokenHandle], r13
0x180009f79  lea     rdx, [rbp+2F0h+TokenHandle]
0x180009f7d  mov     rcx, rsi
0x180009f80  mov     rax, rdi
0x180009f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f88  mov     rcx, [rsp+378h]; this
0x180009f90  test    eax, eax
0x180009f92  js      loc_18000A279
0x180009f98  mov     r15, [rbp+2F0h+var_2B8]
0x180009f9c  mov     rax, [r15]
0x180009f9f  mov     r12, [rax+28h]
0x180009fa3  mov     rsi, qword ptr [rbp+2F0h+var_2D8]
0x180009fa7  test    rsi, rsi
0x180009faa  jz      short loc_180009FC5
0x180009fac  call    cs:__imp_GetLastError
0x180009fb2  mov     edi, eax
0x180009fb4  mov     rcx, rsi; hMem
0x180009fb7  call    cs:__imp_LocalFree
0x180009fbd  mov     ecx, edi; dwErrCode
0x180009fbf  call    cs:__imp_SetLastError
0x180009fc5  mov     qword ptr [rbp+2F0h+var_2D8], r13
0x180009fc9  xor     edx, edx; length
0x180009fcb  mov     rcx, [rbp+2F0h+TokenHandle]; string
0x180009fcf  call    cs:__imp_WindowsGetStringRawBuffer
0x180009fd5  lea     r8, [rbp+2F0h+var_2D8]
0x180009fd9  mov     rdx, rax
0x180009fdc  mov     rcx, r15
0x180009fdf  mov     rax, r12
0x180009fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fe7  mov     rcx, [rsp+378h]; this
0x180009fef  test    eax, eax
0x180009ff1  jz      loc_18000A338
0x180009ff7  mov     rdi, [rsp+378h]
0x180009fff  mov     rdx, qword ptr [rbp+2F0h+var_2D8]; Sid2
0x18000a003  mov     rcx, [r14+78h]; Sid1
0x18000a007  call    cs:__imp_RtlEqualSid
0x18000a00d  test    al, al
0x18000a00f  jz      loc_18000A15D
0x18000a015  mov     rcx, qword ptr [rbp+2F0h+var_2D8]; hMem
  ... truncated ...
```
