# UserMgrCli::GetExtendedCallerInformation(void *,_EXTENDED_CALLER_INFORMATION *)

- ea: `0x18000ad00`
- end: `0x18000b504`
- name: `?GetExtendedCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_EXTENDED_CALLER_INFORMATION@@@Z`
- size: `2052`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void *, struct _EXTENDED_CALLER_INFORMATION *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027e60`
- `0x18003b764`
- `0x1800dfbd0`

## callees

- `0x1800088e8`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000ac00`
- `0x18000acdc`
- `0x18000ad00`
- `0x18000c4f0`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aeb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aee4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b121`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b28d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aeb3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000aee4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b121`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b28d`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000af80`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18000af80`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b376`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000b376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b44d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b47f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b492`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b3a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ad98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ad98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b32e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b32e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b340`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000b340`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000adb0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000adb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b48a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b49d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b48a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b49d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4f1`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000ae65`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000b2f9`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000ae65`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000b2f9`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000b14c`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000b2d6`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000b14c`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18000b2d6`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad72`
- `ntdll!RtlNtStatusToDosError` at `0x18000ad72`
- `ntdll!RtlIsMultiSessionSku` at `0x18000b15e`
- `ntdll!RtlIsMultiSessionSku` at `0x18000b15e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ad6a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ad6a`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000afee`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000afee`
- `RPCRT4!RpcRevertToSelf` at `0x18000adcc`
- `RPCRT4!RpcRevertToSelf` at `0x18000adcc`
- `RPCRT4!RpcImpersonateClient` at `0x18000ad57`
- `RPCRT4!RpcImpersonateClient` at `0x18000ad57`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000b208`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000b208`

## string_xrefs

- `0x18000b3be`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000b3e9`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x18000b1a5`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b1bd`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b1d1`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b1e2`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b22c`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b23d`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b24e`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b260`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b2ac`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b38c`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b429`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b43b`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000b083`: `xboxAccessoryManagement`
- `0x18000b407`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x18000b466`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserMgrCli::GetExtendedCallerInformation(
        UserMgrCli *this,
        void *a2,
        struct _EXTENDED_CALLER_INFORMATION *a3)
{
  unsigned __int64 v3; // rbp
  RPC_STATUS v5; // eax
  NTSTATUS v6; // eax
  signed int v7; // eax
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  char *v10; // rcx
  void *v11; // rsi
  DWORD *v12; // r14
  const char *v13; // r9
  int v14; // eax
  const char *v15; // r9
  const char *v16; // r9
  void *v17; // rdx
  const char *v18; // r9
  int v19; // eax
  DWORD CurrentProcessId; // eax
  unsigned __int8 v21; // cl
  const char *v22; // r9
  char v23; // al
  const char *v24; // r9
  char *v25; // rcx
  __int64 result; // rax
  char v27; // r13
  __int64 v28; // r15
  int TokenInformation; // edi
  unsigned int PackageFullNameFromToken; // eax
  const char *v31; // r9
  char *v32; // rsi
  HANDLE CurrentProcess; // rax
  const char *v34; // r9
  const char *v35; // r9
  bool v36; // sf
  DWORD v37; // eax
  DWORD LastError; // edi
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-60h]
  unsigned __int8 v41[4]; // [rsp+80h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+128h]

  v3 = (unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = (unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8) = 1;
  *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  v5 = RpcImpersonateClient(0);
  try
  {
    if ( v5 == 1725 )
    {
      v32 = *(char **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      if ( (unsigned __int64)(v32 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v32);
        SetLastError(LastError);
      }
      *(_QWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xAu, (PHANDLE)(v3 + 24)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v34);
      if ( !DuplicateTokenEx(
              *(HANDLE *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
              0,
              0,
              SecurityImpersonation,
              TokenImpersonation,
              (PHANDLE)(v3 + 32)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v35);
    }
    else
    {
      v6 = I_RpcMapWin32Status(v5);
      v7 = RtlNtStatusToDosError(v6);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          (const char *)(unsigned int)v7,
          ReturnLength);
      *(_BYTE *)v3 = 1;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)(v3 + 32)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v9);
    }
    if ( *(_BYTE *)v3 )
      RpcRevertToSelf();
    v10 = *(char **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)0x80004003LL,
        ReturnLength);
    v11 = *(void **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    *(_WORD *)a3 = 256;
    *((_BYTE *)a3 + 12) = 0;
    *((_DWORD *)a3 + 2) = -1;
    *((_BYTE *)a3 + 1) = IsTokenAppContainer(v11);
    *(_BYTE *)a3 = DoesTokenHasPrivilege(v11, 7u);
    v12 = (DWORD *)((char *)a3 + 4);
    *((_DWORD *)a3 + 1) = 0;
    *((_DWORD *)a3 + 32) = DoesTokenHasPrivilege(v11, 0x1Du);
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
    *((_BYTE *)a3 + 12) = 0;
    if ( !(unsigned int)CheckTokenCapability(v11, &CapMumaSidBuffer, v3 + 16) )
    {
      v14 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x184,
              (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
              v13);
      goto LABEL_16;
    }
    if ( *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
    {
LABEL_14:
      *((_BYTE *)a3 + 12) = 1;
LABEL_15:
      v14 = 0;
      goto LABEL_16;
    }
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
    *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
    v27 = 0;
    v28 = (__int64)v11;
    if ( !v11 )
      v28 = -6;
    TokenInformation = GetTokenInformation((HANDLE)v28, TokenIsAppContainer, (LPVOID)(v3 + 8), 4u, (PDWORD)(v3 + 12));
    if ( !TokenInformation )
      goto LABEL_48;
    if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
    {
      TokenInformation = CheckTokenMembershipEx(
                           v28,
                           &CapMumaGroupSidBuffer,
                           *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                           v3 + 4);
      if ( !TokenInformation )
        goto LABEL_48;
      if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      {
        if ( !(unsigned __int8)RtlIsMultiSessionSku() )
        {
          TokenInformation = CheckTokenMembershipEx(
                               v28,
                               &DefaultAliasWellKnownSid,
                               *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                               v3 + 4);
          if ( !TokenInformation )
            goto LABEL_48;
        }
        if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
          goto LABEL_49;
      }
    }
    if ( *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
    {
      TokenInformation = CheckTokenCapability(v28, &CapMumaSidBuffer, v3 + 4);
      if ( !TokenInformation )
        goto LABEL_48;
      if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_49;
    }
    v27 = 1;
LABEL_48:
    if ( !TokenInformation )
    {
      v37 = GetLastError();
      if ( v37 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x18D,
                (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                (const char *)v37,
                ReturnLength);
LABEL_16:
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            (const char *)(unsigned int)v14,
            ReturnLength);
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
        if ( !GetTokenInformation(v11, TokenSessionId, (char *)a3 + 8, 4u, (PDWORD)(v3 + 12)) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1AE,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v15);
        if ( !GetTokenInformation(v11, TokenUser, (char *)a3 + 32, 0x54u, (PDWORD)(v3 + 24)) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x1E2,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v16);
        v17 = (void *)*((_QWORD *)a3 + 4);
        *((_QWORD *)a3 + 15) = v17;
        *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
        *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
        *((_BYTE *)a3 + 2) = 0;
        if ( !v17 )
        {
          if ( !GetTokenInformation(v11, TokenUser, (LPVOID)(v3 + 64), 0x54u, (PDWORD)(v3 + 12)) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x10B,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
              v31);
          v17 = *(void **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
        }
        if ( !AccessCheckByType(
                qword_18010A700,
                v17,
                v11,
                1u,
                0,
                0,
                (PGENERIC_MAPPING)&GenericMapping,
                (PPRIVILEGE_SET)(v3 + 192),
                (LPDWORD)(v3 + 4),
                (LPDWORD)(v3 + 8),
                (LPBOOL)(v3 + 16)) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x119,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v18);
        if ( *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10)
          && (*(_BYTE *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 8) & 1) != 0 )
        {
          *((_BYTE *)a3 + 2) = 1;
        }
        if ( a3 == (struct _EXTENDED_CALLER_INFORMATION *)-4LL )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
            (const char *)0x80004003LL,
            ReturnLengtha);
        }
        else
        {
          *v12 = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
          *(_OWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) = 0;
          *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 3;
          *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x44) = 112;
          v19 = RpcServerInqCallAttributesW(0, (void *)(v3 + 64));
          if ( v19 )
          {
            if ( v19 != 1725 )
            {
              v36 = v19 < 0;
              if ( v19 > 0 )
              {
                v19 = (unsigned __int16)v19 | 0x80070000;
                v36 = v19 < 0;
              }
              if ( v36 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x5A,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
                  (const char *)(unsigned int)v19,
                  ReturnLengtha);
              goto LABEL_28;
            }
            CurrentProcessId = GetCurrentProcessId();
          }
          else
          {
            CurrentProcessId = *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
          }
          *v12 = CurrentProcessId;
        }
LABEL_28:
        if ( !*((_BYTE *)a3 + 1)
          || (*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 128,
              PackageFullNameFromToken = GetPackageFullNameFromToken(v11, (UINT32 *)(v3 + 12), (PWSTR)a3 + 66),
              PackageFullNameFromToken == 15700) )
        {
          *((_WORD *)a3 + 66) = 0;
        }
        else if ( PackageFullNameFromToken )
        {
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1F3,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            (const char *)PackageFullNameFromToken,
            ReturnLengtha);
        }
        v21 = (_BYTE)word_180148290 == 0;
        v22 = 0;
        v23 = 0;
        *(_BYTE *)v3 = 0;
        if ( SeAllowSessionImpersonation )
        {
          v22 = (const char *)CheckTokenForAccessThroughCapability(
                                v11,
                                0,
                                &CapSessionImpersonationGroupSidBuffer,
                                &CapSessionImpersonationSidBuffer,
                                v21,
                                0,
                                (unsigned __int8 *)((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL));
          v23 = *(_BYTE *)v3;
        }
        if ( (_DWORD)v22 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x1FF,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            v22,
            ReturnLengtha);
        if ( v23 )
          *((_BYTE *)a3 + 416) = 1;
        *((_BYTE *)a3 + 417) = (int)CapabilityAccessCheck(v11, L"userSigninSupport") >= 0;
        *((_BYTE *)a3 + 418) = (int)CapabilityAccessCheck(v11, L"shellExperience") >= 0;
        *((_BYTE *)a3 + 419) = (int)CapabilityAccessCheck(v11, L"xboxAccessoryManagement") >= 0;
        v25 = *(char **)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
        if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v25);
        return 0;
      }
    }
LABEL_49:
    if ( !*(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) && !v27 )
      goto LABEL_15;
    goto LABEL_14;
  }
  catch ( ... )
  {
    *(_DWORD *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = wil::details::in1diag3::Return_CaughtException(
                                                                            retaddr,
                                                                            (void *)0x93F,
                                                                            (unsigned int)"onecore\\ds\\security\\umstart"
                                                                                          "up\\usermgr\\lib\\usermgrcli.cpp",
                                                                            v24);
    return *(unsigned int *)(((unsigned __int64)v41 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  }
  return result;
}

```

## disassembly

```asm
0x18000ad00  push    rbp
0x18000ad02  push    rbx
0x18000ad03  push    rsi
0x18000ad04  push    rdi
0x18000ad05  push    r12
0x18000ad07  push    r13
0x18000ad09  push    r14
0x18000ad0b  push    r15
0x18000ad0d  sub     rsp, 168h
0x18000ad14  lea     rbp, [rsp+80h]
0x18000ad1c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x18000ad20  mov     rax, cs:__security_cookie
0x18000ad27  xor     rax, rsp
0x18000ad2a  mov     [rbp+120h+var_48], rax
0x18000ad31  mov     rbx, r8
0x18000ad34  mov     [rbp+120h+var_120], 0
0x18000ad38  xor     r15d, r15d
0x18000ad3b  mov     qword ptr [rbp+120h+var_108], r15
0x18000ad3f  lea     rax, [rbp+120h+var_120]
0x18000ad43  mov     qword ptr [rbp+120h+var_60.PrivilegeCount], rax
0x18000ad4a  mov     byte ptr [rbp+120h+var_60.Privilege.Luid.LowPart], 1
0x18000ad51  mov     [rbp+120h+TokenHandle], r15
0x18000ad55  xor     ecx, ecx; BindingHandle
0x18000ad57  call    cs:__imp_RpcImpersonateClient
0x18000ad5d  cmp     eax, 6BDh
0x18000ad62  jz      loc_18000B318
0x18000ad68  mov     ecx, eax; Status
0x18000ad6a  call    cs:__imp_I_RpcMapWin32Status
0x18000ad70  mov     ecx, eax; Status
0x18000ad72  call    cs:__imp_RtlNtStatusToDosError
0x18000ad78  test    eax, eax
0x18000ad7a  jle     short loc_18000AD84
0x18000ad7c  movzx   eax, ax
0x18000ad7f  or      eax, 80070000h
0x18000ad84  mov     rcx, [rsp+1A8h]; this
0x18000ad8c  test    eax, eax
0x18000ad8e  js      loc_18000B1A2
0x18000ad94  mov     [rbp+120h+var_120], 1
0x18000ad98  call    cs:__imp_GetCurrentThread
0x18000ad9e  mov     rcx, rax; ThreadHandle
0x18000ada1  lea     r9, [rbp+120h+TokenHandle]; TokenHandle
0x18000ada5  mov     edx, 8; DesiredAccess
0x18000adaa  mov     r8d, 1; OpenAsSelf
0x18000adb0  call    cs:__imp_OpenThreadToken
0x18000adb6  mov     rcx, [rsp+1A8h]; this
0x18000adbe  test    eax, eax
0x18000adc0  jz      loc_18000B260
0x18000adc6  cmp     [rbp+120h+var_120], 0
0x18000adca  jz      short loc_18000ADD3
0x18000adcc  call    cs:__imp_RpcRevertToSelf
0x18000add2  nop
0x18000add3  mov     rcx, qword ptr [rbp+120h+var_108]; hObject
0x18000add7  lea     rax, [rcx-1]
0x18000addb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000addf  jbe     loc_18000B49D
0x18000ade5  mov     [rbp+120h+var_108], r15d
0x18000ade9  test    rbx, rbx
0x18000adec  jnz     loc_18000B4A8
0x18000adf2  xor     al, al
0x18000adf4  mov     rcx, [rsp+1A8h]; this
0x18000adfc  test    al, al
0x18000adfe  jz      loc_18000B1B7
0x18000ae04  mov     rsi, [rbp+120h+TokenHandle]
0x18000ae08  mov     word ptr [rbx], 100h
0x18000ae0d  mov     byte ptr [rbx+0Ch], 0
0x18000ae11  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18000ae18  mov     rcx, rsi; void *
0x18000ae1b  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x18000ae20  mov     [rbx+1], al
0x18000ae23  mov     edx, 7; unsigned int
0x18000ae28  mov     rcx, rsi; void *
0x18000ae2b  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000ae30  mov     [rbx], al
0x18000ae32  lea     r14, [rbx+4]
0x18000ae36  mov     [r14], r15d
0x18000ae39  mov     edx, 1Dh; unsigned int
0x18000ae3e  mov     rcx, rsi; void *
0x18000ae41  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x18000ae46  movzx   eax, al
0x18000ae49  mov     [rbx+80h], eax
0x18000ae4f  mov     [rbp+120h+var_110], r15d
0x18000ae53  mov     byte ptr [rbx+0Ch], 0
0x18000ae57  lea     r8, [rbp+120h+var_110]
0x18000ae5b  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x18000ae62  mov     rcx, rsi
0x18000ae65  call    cs:__imp_CheckTokenCapability
0x18000ae6b  test    eax, eax
0x18000ae6d  jz      loc_18000B3FF
0x18000ae73  cmp     [rbp+120h+var_110], 0
0x18000ae77  jz      loc_18000B0D4
0x18000ae7d  mov     byte ptr [rbx+0Ch], 1
0x18000ae81  mov     eax, r15d
0x18000ae84  mov     rcx, [rsp+1A8h]; this
0x18000ae8c  test    eax, eax
0x18000ae8e  js      loc_18000B1CE
0x18000ae94  mov     [rbp+120h+packageFullNameLength], r15d
0x18000ae98  lea     rax, [rbp+120h+packageFullNameLength]
0x18000ae9c  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18000aea1  mov     r9d, 4; TokenInformationLength
0x18000aea7  lea     r8, [rbx+8]; TokenInformation
0x18000aeab  mov     edx, 0Ch; TokenInformationClass
0x18000aeb0  mov     rcx, rsi; TokenHandle
0x18000aeb3  call    cs:__imp_GetTokenInformation
0x18000aeb9  mov     rcx, [rsp+1A8h]; this
0x18000aec1  test    eax, eax
0x18000aec3  jz      loc_18000B2AC
0x18000aec9  lea     rax, [rbp+120h+var_108]
0x18000aecd  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x18000aed2  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000aed8  lea     r8, [rbx+20h]; TokenInformation
0x18000aedc  mov     edx, 1; TokenInformationClass
0x18000aee1  mov     rcx, rsi; TokenHandle
0x18000aee4  call    cs:__imp_GetTokenInformation
0x18000aeea  mov     rcx, [rsp+1A8h]; this
0x18000aef2  test    eax, eax
0x18000aef4  jz      loc_18000B23D
0x18000aefa  mov     rdx, [rbx+20h]; PrincipalSelfSid
0x18000aefe  mov     [rbx+78h], rdx
0x18000af02  xorps   xmm0, xmm0
0x18000af05  xor     eax, eax
0x18000af07  movups  xmmword ptr [rbp+120h+var_60.PrivilegeCount], xmm0
0x18000af0e  mov     [rbp+120h+var_60.Privilege.Attributes], eax
0x18000af14  mov     [rbp+120h+TokenInformation], r15d
0x18000af18  mov     [rbp+120h+var_110], r15d
0x18000af1c  mov     [rbp+120h+var_11C], 14h
0x18000af23  mov     [rbp+120h+packageFullNameLength], r15d
0x18000af27  mov     [rbx+2], al
0x18000af2a  test    rdx, rdx
0x18000af2d  jz      loc_18000B272
0x18000af33  lea     rax, [rbp+120h+var_110]
0x18000af37  mov     [rsp+1A0h+AccessStatus], rax; AccessStatus
0x18000af3c  lea     rax, [rbp+120h+TokenInformation]
0x18000af40  mov     [rsp+1A0h+GrantedAccess], rax; GrantedAccess
0x18000af45  lea     rax, [rbp+120h+var_11C]
0x18000af49  mov     [rsp+1A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000af4e  lea     rax, [rbp+120h+var_60]
0x18000af55  mov     [rsp+1A0h+PrivilegeSet], rax; PrivilegeSet
0x18000af5a  lea     rax, GenericMapping
0x18000af61  mov     [rsp+1A0h+GenericMapping], rax; GenericMapping
0x18000af66  mov     [rsp+1A0h+ObjectTypeListLength], r15d; ObjectTypeListLength
0x18000af6b  mov     [rsp+1A0h+ReturnLength], r15; int
0x18000af70  mov     r9d, 1; DesiredAccess
0x18000af76  mov     r8, rsi; ClientToken
0x18000af79  lea     rcx, qword_18010A700; pSecurityDescriptor
0x18000af80  call    cs:__imp_AccessCheckByType
0x18000af86  mov     rcx, [rsp+1A8h]; this
0x18000af8e  test    eax, eax
0x18000af90  jz      loc_18000B24E
0x18000af96  cmp     [rbp+120h+var_110], 0
0x18000af9a  jz      short loc_18000AFA6
0x18000af9c  test    byte ptr [rbp+120h+TokenInformation], 1
0x18000afa0  jz      short loc_18000AFA6
0x18000afa2  mov     byte ptr [rbx+2], 1
0x18000afa6  test    r14, r14
0x18000afa9  jz      loc_18000B3B0
0x18000afaf  mov     [r14], r15d
0x18000afb2  xorps   xmm0, xmm0
0x18000afb5  movups  [rbp+120h+var_D8], xmm0
0x18000afb9  movups  [rbp+120h+var_C8], xmm0
0x18000afbd  movups  [rbp+120h+var_B8], xmm0
0x18000afc1  movups  [rbp+120h+var_A8], xmm0
0x18000afc5  movups  [rbp+120h+var_98], xmm0
0x18000afcc  movups  [rbp+120h+var_88], xmm0
0x18000afd3  movups  [rbp+120h+var_78], xmm0
0x18000afda  mov     dword ptr [rbp+120h+RpcCallAttributes], 3
0x18000afe1  mov     dword ptr [rbp+120h+RpcCallAttributes+4], 70h ; 'p'
0x18000afe8  lea     rdx, [rbp+120h+RpcCallAttributes]; RpcCallAttributes
0x18000afec  xor     ecx, ecx; ClientBinding
0x18000afee  call    cs:__imp_RpcServerInqCallAttributesW
0x18000aff4  test    eax, eax
0x18000aff6  jnz     loc_18000B39E
0x18000affc  mov     eax, dword ptr [rbp+120h+var_A8+8]
0x18000b002  mov     [r14], eax
0x18000b005  cmp     byte ptr [rbx+1], 0
0x18000b009  jnz     loc_18000B1F3
0x18000b00f  mov     [rbx+84h], r15w
0x18000b017  cmp     byte ptr cs:word_180148290, 0
0x18000b01e  setz    cl
0x18000b021  mov     r9d, r15d; char *
0x18000b024  xor     al, al
0x18000b026  mov     [rbp+120h+var_120], al
0x18000b029  cmp     cs:?SeAllowSessionImpersonation@@3KA, 0; ulong SeAllowSessionImpersonation
0x18000b030  jnz     loc_18000B4AF
0x18000b036  mov     rcx, [rsp+1A8h]; this
0x18000b03e  test    r9d, r9d
0x18000b041  jnz     loc_18000B1E2
0x18000b047  test    al, al
0x18000b049  jnz     loc_18000B4E5
0x18000b04f  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x18000b056  mov     rcx, rsi; void *
0x18000b059  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000b05e  shr     eax, 1Fh
0x18000b061  xor     al, 1
0x18000b063  mov     [rbx+1A1h], al
0x18000b069  lea     rdx, aShellexperienc; "shellExperience"
0x18000b070  mov     rcx, rsi; void *
0x18000b073  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000b078  shr     eax, 1Fh
0x18000b07b  xor     al, 1
0x18000b07d  mov     [rbx+1A2h], al
0x18000b083  lea     rdx, aXboxaccessorym; "xboxAccessoryManagement"
0x18000b08a  mov     rcx, rsi; void *
0x18000b08d  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000b092  shr     eax, 1Fh
0x18000b095  xor     al, 1
0x18000b097  mov     [rbx+1A3h], al
0x18000b09d  mov     rcx, [rbp+120h+TokenHandle]; hObject
0x18000b0a1  lea     rax, [rcx-1]
0x18000b0a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b0a9  jbe     loc_18000B4F1
0x18000b0af  xor     eax, eax
0x18000b0b1  mov     rcx, [rbp+120h+var_48]
0x18000b0b8  xor     rcx, rsp; StackCookie
0x18000b0bb  call    __security_check_cookie
0x18000b0c0  add     rsp, 168h
0x18000b0c7  pop     r15
0x18000b0c9  pop     r14
0x18000b0cb  pop     r13
0x18000b0cd  pop     r12
0x18000b0cf  pop     rdi
0x18000b0d0  pop     rsi
0x18000b0d1  pop     rbx
0x18000b0d2  pop     rbp
0x18000b0d3  retn
0x18000b0d4  mov     [rbp+120h+var_11C], r15d
0x18000b0d8  mov     [rbp+120h+TokenInformation], r15d
0x18000b0dc  mov     [rbp+120h+packageFullNameLength], r15d
0x18000b0e0  xorps   xmm0, xmm0
0x18000b0e3  xor     eax, eax
0x18000b0e5  movups  xmmword ptr [rbp+120h+var_60.PrivilegeCount], xmm0
0x18000b0ec  mov     [rbp+120h+var_60.Privilege.Attributes], eax
0x18000b0f2  xor     r13b, r13b
0x18000b0f5  mov     r15, rsi
0x18000b0f8  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000b0ff  test    rsi, rsi
0x18000b102  cmovz   r15, rax
0x18000b106  lea     rax, [rbp+120h+packageFullNameLength]
0x18000b10a  mov     [rsp+1A0h+ReturnLength], rax; unsigned int
0x18000b10f  mov     r9d, 4; TokenInformationLength
0x18000b115  lea     r8, [rbp+120h+TokenInformation]; TokenInformation
0x18000b119  mov     edx, 1Dh; TokenInformationClass
0x18000b11e  mov     rcx, r15; TokenHandle
0x18000b121  call    cs:__imp_GetTokenInformation
0x18000b127  mov     edi, eax
0x18000b129  test    eax, eax
0x18000b12b  jz      short loc_18000B17F
0x18000b12d  cmp     [rbp+120h+var_11C], 0
0x18000b131  jnz     short loc_18000B172
0x18000b133  xor     r8d, r8d
0x18000b136  cmp     [rbp+120h+TokenInformation], r8d
0x18000b13a  setnz   r8b
0x18000b13e  lea     r9, [rbp+120h+var_11C]
0x18000b142  lea     rdx, ?CapMumaGroupSidBuffer@@3PAEA; uchar near * CapMumaGroupSidBuffer
0x18000b149  mov     rcx, r15
0x18000b14c  call    cs:__imp_CheckTokenMembershipEx
0x18000b152  mov     edi, eax
0x18000b154  test    eax, eax
0x18000b156  jz      short loc_18000B17F
0x18000b158  cmp     [rbp+120h+var_11C], 0
0x18000b15c  jnz     short loc_18000B172
0x18000b15e  call    cs:__imp_RtlIsMultiSessionSku
0x18000b164  test    al, al
0x18000b166  jz      loc_18000B2BD
0x18000b16c  cmp     [rbp+120h+var_11C], 0
0x18000b170  jz      short loc_18000B187
0x18000b172  cmp     [rbp+120h+TokenInformation], 0
0x18000b176  jnz     loc_18000B2EB
0x18000b17c  mov     r13b, 1
0x18000b17f  test    edi, edi
0x18000b181  jz      loc_18000B44D
0x18000b187  xor     r15d, r15d
0x18000b18a  cmp     [rbp+120h+var_110], r15d
0x18000b18e  jnz     loc_18000AE7D
0x18000b194  test    r13b, r13b
0x18000b197  jz      loc_18000AE81
0x18000b19d  jmp     loc_18000AE7D
0x18000b1a2  mov     r9d, eax; char *
0x18000b1a5  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000b1ac  mov     edx, 37h ; '7'; void *
0x18000b1b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b1b7  mov     r9d, 80004003h; char *
0x18000b1bd  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000b1c4  mov     edx, 1CCh; void *
0x18000b1c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b1ce  mov     r9d, eax; char *
0x18000b1d1  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000b1d8  mov     edx, 1E0h; void *
0x18000b1dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b1e2  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000b1e9  mov     edx, 1FFh; void *
0x18000b1ee  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000b1f3  mov     [rbp+120h+packageFullNameLength], 80h
0x18000b1fa  lea     r8, [rbx+84h]; packageFullName
0x18000b201  lea     rdx, [rbp+120h+packageFullNameLength]; packageFullNameLength
0x18000b205  mov     rcx, rsi; token
0x18000b208  call    cs:__imp_GetPackageFullNameFromToken
0x18000b20e  cmp     eax, 3D54h
0x18000b213  jz      loc_18000B00F
0x18000b219  mov     rcx, [rsp+1A8h]; this
0x18000b221  test    eax, eax
  ... truncated ...
```
