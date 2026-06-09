# UserMgrCli::GetBasicCallerInformation(void *,_BASIC_CALLER_INFORMATION *)

- ea: `0x180008b70`
- end: `0x180009296`
- name: `?GetBasicCallerInformation@UserMgrCli@@AEAAJPEAXPEAU_BASIC_CALLER_INFORMATION@@@Z`
- size: `1830`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void *, struct _BASIC_CALLER_INFORMATION *)`
- caller_count: `28`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024870`
- `0x180028620`
- `0x180038af4`
- `0x18003c650`
- `0x18003e3a4`
- `0x18003e674`
- `0x18003ff90`
- `0x1800401b4`
- `0x180041048`
- `0x180045e44`
- `0x180045f70`
- `0x18004611c`
- `0x180046338`
- `0x1800465e4`
- `0x180046760`
- `0x1800468b0`
- `0x1800b2614`
- `0x1800b296c`
- `0x1800b3560`
- `0x1800b38ec`
- `0x1800b4000`
- `0x1800b45ac`
- `0x1800b4c60`
- `0x1800b4e08`
- `0x1800b4f80`
- `0x1800b5194`
- `0x1800b56a0`
- `0x1800b5988`

## callees

- `0x1800088e8`
- `0x180008b70`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000acdc`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008f1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800090a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008d51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008f1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800090a6`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180008ded`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180008ded`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009151`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000925a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000925a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000926d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000926d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009180`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009109`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000911b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000911b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008c20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008c20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009283`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180008cd2`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800090d3`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180008cd2`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800090d3`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180008f4a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180009075`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180008f4a`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180009075`
- `ntdll!RtlNtStatusToDosError` at `0x180008be2`
- `ntdll!RtlNtStatusToDosError` at `0x180008be2`
- `ntdll!RtlIsMultiSessionSku` at `0x180008f5d`
- `ntdll!RtlIsMultiSessionSku` at `0x180008f5d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008bda`
- `RPCRT4!I_RpcMapWin32Status` at `0x180008bda`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180008e5b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180008e5b`
- `RPCRT4!RpcRevertToSelf` at `0x180008c3c`
- `RPCRT4!RpcRevertToSelf` at `0x180008c3c`
- `RPCRT4!RpcImpersonateClient` at `0x180008bc7`
- `RPCRT4!RpcImpersonateClient` at `0x180008bc7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180008fe1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x180008fe1`

## string_xrefs

- `0x1800091b7`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x1800091e2`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x180008ec0`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008fa5`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180008fba`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009005`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009016`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009027`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009038`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000904a`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009167`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009204`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009216`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009193`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x180009241`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserMgrCli::GetBasicCallerInformation(
        UserMgrCli *this,
        void *a2,
        struct _BASIC_CALLER_INFORMATION *a3)
{
  unsigned __int64 v3; // rbp
  RPC_STATUS v5; // eax
  NTSTATUS v6; // eax
  signed int v7; // eax
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  char *v10; // rcx
  void *v11; // rdi
  DWORD *v12; // rsi
  const char *v13; // r9
  int v14; // eax
  const char *v15; // r9
  const char *v16; // r9
  void *v17; // rdx
  const char *v18; // r9
  int v19; // eax
  const char *v20; // r9
  DWORD CurrentProcessId; // eax
  char *v22; // rcx
  __int64 result; // rax
  char v24; // r13
  __int64 v25; // r12
  int TokenInformation; // r15d
  unsigned int PackageFullNameFromToken; // eax
  const char *v28; // r9
  char *v29; // rsi
  HANDLE CurrentProcess; // rax
  const char *v31; // r9
  const char *v32; // r9
  bool v33; // sf
  DWORD v34; // eax
  DWORD LastError; // edi
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-60h]
  _BYTE v38[4]; // [rsp+80h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+128h]

  v3 = (unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) = 0;
  *(_QWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  *(_QWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = (unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC8) = 1;
  *(_QWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20) = 0;
  v5 = RpcImpersonateClient(0);
  try
  {
    if ( v5 == 1725 )
    {
      v29 = *(char **)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
      if ( (unsigned __int64)(v29 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v29);
        SetLastError(LastError);
      }
      *(_QWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xAu, (PHANDLE)(v3 + 24)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v31);
      if ( !DuplicateTokenEx(
              *(HANDLE *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
              0,
              0,
              SecurityImpersonation,
              TokenImpersonation,
              (PHANDLE)(v3 + 32)) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
          v32);
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
    v10 = *(char **)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v10);
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        (const char *)0x80004003LL,
        ReturnLength);
    v11 = *(void **)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
    *(_WORD *)a3 = 256;
    *((_BYTE *)a3 + 12) = 0;
    *((_DWORD *)a3 + 2) = -1;
    *((_BYTE *)a3 + 1) = IsTokenAppContainer(v11);
    *(_BYTE *)a3 = DoesTokenHasPrivilege(v11, 7u);
    v12 = (DWORD *)((char *)a3 + 4);
    *((_DWORD *)a3 + 1) = 0;
    *((_DWORD *)a3 + 32) = DoesTokenHasPrivilege(v11, 0x1Du);
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
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
    if ( *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
    {
LABEL_14:
      *((_BYTE *)a3 + 12) = 1;
LABEL_15:
      v14 = 0;
      goto LABEL_16;
    }
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
    *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
    v24 = 0;
    v25 = (__int64)v11;
    if ( !v11 )
      v25 = -6;
    TokenInformation = GetTokenInformation((HANDLE)v25, TokenIsAppContainer, (LPVOID)(v3 + 8), 4u, (PDWORD)(v3 + 12));
    if ( !TokenInformation )
      goto LABEL_44;
    if ( !*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
    {
      TokenInformation = CheckTokenMembershipEx(
                           v25,
                           &CapMumaGroupSidBuffer,
                           *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                           v3 + 4);
      if ( !TokenInformation )
        goto LABEL_44;
      if ( !*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      {
        if ( !(unsigned __int8)RtlIsMultiSessionSku() )
        {
          TokenInformation = CheckTokenMembershipEx(
                               v25,
                               &DefaultAliasWellKnownSid,
                               *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                               v3 + 4);
          if ( !TokenInformation )
            goto LABEL_44;
        }
        if ( !*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
          goto LABEL_45;
      }
    }
    if ( *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
    {
      TokenInformation = CheckTokenCapability(v25, &CapMumaSidBuffer, v3 + 4);
      if ( !TokenInformation )
        goto LABEL_44;
      if ( !*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_45;
    }
    v24 = 1;
LABEL_44:
    if ( !TokenInformation )
    {
      v34 = GetLastError();
      if ( v34 )
      {
        v14 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x18D,
                (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                (const char *)v34,
                ReturnLength);
LABEL_16:
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E0,
            (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
            (const char *)(unsigned int)v14,
            ReturnLength);
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
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
        *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
        *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
        *((_BYTE *)a3 + 2) = 0;
        if ( !v17 )
        {
          if ( !GetTokenInformation(v11, TokenUser, (LPVOID)(v3 + 64), 0x54u, (PDWORD)(v3 + 12)) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x10B,
              (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
              v28);
          v17 = *(void **)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
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
        if ( *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10)
          && (*(_BYTE *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 8) & 1) != 0 )
        {
          *((_BYTE *)a3 + 2) = 1;
        }
        if ( a3 == (struct _BASIC_CALLER_INFORMATION *)-4LL )
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
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
          *(_OWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) = 0;
          *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 3;
          *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x44) = 112;
          v19 = RpcServerInqCallAttributesW(0, (void *)(v3 + 64));
          if ( v19 )
          {
            if ( v19 != 1725 )
            {
              v33 = v19 < 0;
              if ( v19 > 0 )
              {
                v19 = (unsigned __int16)v19 | 0x80070000;
                v33 = v19 < 0;
              }
              if ( v33 )
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
            CurrentProcessId = *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
          }
          *v12 = CurrentProcessId;
        }
LABEL_28:
        if ( !*((_BYTE *)a3 + 1)
          || (*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 128,
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
        v22 = *(char **)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
        if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v22);
        return 0;
      }
    }
LABEL_45:
    if ( !*(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) && !v24 )
      goto LABEL_15;
    goto LABEL_14;
  }
  catch ( ... )
  {
    *(_DWORD *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = wil::details::in1diag3::Return_CaughtException(
                                                                            retaddr,
                                                                            (void *)0x936,
                                                                            (unsigned int)"onecore\\ds\\security\\umstart"
                                                                                          "up\\usermgr\\lib\\usermgrcli.cpp",
                                                                            v20);
    return *(unsigned int *)(((unsigned __int64)v38 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  }
  return result;
}

```

## disassembly

```asm
0x180008b70  push    rbp
0x180008b72  push    rbx
0x180008b73  push    rsi
0x180008b74  push    rdi
0x180008b75  push    r12
0x180008b77  push    r13
0x180008b79  push    r14
0x180008b7b  push    r15
0x180008b7d  sub     rsp, 168h
0x180008b84  lea     rbp, [rsp+80h]
0x180008b8c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x180008b90  mov     rax, cs:__security_cookie
0x180008b97  xor     rax, rsp
0x180008b9a  mov     [rbp+120h+var_48], rax
0x180008ba1  mov     rbx, r8
0x180008ba4  mov     [rbp+120h+var_120], 0
0x180008ba8  xor     r15d, r15d
0x180008bab  mov     qword ptr [rbp+120h+var_108], r15
0x180008baf  lea     rax, [rbp+120h+var_120]
0x180008bb3  mov     qword ptr [rbp+120h+var_60.PrivilegeCount], rax
0x180008bba  mov     byte ptr [rbp+120h+var_60.Privilege.Luid.LowPart], 1
0x180008bc1  mov     [rbp+120h+TokenHandle], r15
0x180008bc5  xor     ecx, ecx; BindingHandle
0x180008bc7  call    cs:__imp_RpcImpersonateClient
0x180008bcd  cmp     eax, 6BDh
0x180008bd2  jz      loc_1800090F3
0x180008bd8  mov     ecx, eax; Status
0x180008bda  call    cs:__imp_I_RpcMapWin32Status
0x180008be0  mov     ecx, eax; Status
0x180008be2  call    cs:__imp_RtlNtStatusToDosError
0x180008be8  test    eax, eax
0x180008bea  jle     short loc_180008BF4
0x180008bec  movzx   eax, ax
0x180008bef  or      eax, 80070000h
0x180008bf4  mov     rcx, [rsp+1A8h]; this
0x180008bfc  test    eax, eax
0x180008bfe  js      loc_180008FB7
0x180008c04  mov     [rbp+120h+var_120], 1
0x180008c08  call    cs:__imp_GetCurrentThread
0x180008c0e  mov     rcx, rax; ThreadHandle
0x180008c11  lea     r9, [rbp+120h+TokenHandle]; TokenHandle
0x180008c15  mov     edx, 8; DesiredAccess
0x180008c1a  mov     r8d, 1; OpenAsSelf
0x180008c20  call    cs:__imp_OpenThreadToken
0x180008c26  mov     rcx, [rsp+1A8h]; this
0x180008c2e  test    eax, eax
0x180008c30  jz      loc_18000904A
0x180008c36  cmp     [rbp+120h+var_120], 0
0x180008c3a  jz      short loc_180008C43
0x180008c3c  call    cs:__imp_RpcRevertToSelf
0x180008c42  nop
0x180008c43  mov     rcx, qword ptr [rbp+120h+var_108]; hObject
0x180008c47  lea     rax, [rcx-1]
0x180008c4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c4f  jbe     loc_180009278
0x180008c55  mov     [rbp+120h+var_108], r15d
0x180008c59  mov     rcx, [rsp+1A8h]; this
0x180008c61  test    rbx, rbx
0x180008c64  jz      loc_180008EBA
0x180008c6a  mov     rdi, [rbp+120h+TokenHandle]
0x180008c6e  test    rbx, rbx
0x180008c71  cmovz   rbx, r15
0x180008c75  mov     word ptr [rbx], 100h
0x180008c7a  mov     byte ptr [rbx+0Ch], 0
0x180008c7e  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x180008c85  mov     rcx, rdi; void *
0x180008c88  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x180008c8d  mov     [rbx+1], al
0x180008c90  mov     edx, 7; unsigned int
0x180008c95  mov     rcx, rdi; void *
0x180008c98  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x180008c9d  mov     [rbx], al
0x180008c9f  lea     rsi, [rbx+4]
0x180008ca3  mov     [rsi], r15d
0x180008ca6  mov     edx, 1Dh; unsigned int
0x180008cab  mov     rcx, rdi; void *
0x180008cae  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x180008cb3  movzx   eax, al
0x180008cb6  mov     [rbx+80h], eax
0x180008cbc  mov     [rbp+120h+var_110], r15d
0x180008cc0  mov     byte ptr [rbx+0Ch], 0
0x180008cc4  lea     r8, [rbp+120h+var_110]
0x180008cc8  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x180008ccf  mov     rcx, rdi
0x180008cd2  call    cs:__imp_CheckTokenCapability
0x180008cd8  test    eax, eax
0x180008cda  jz      loc_18000918B
0x180008ce0  cmp     [rbp+120h+var_110], 0
0x180008ce4  jz      loc_180008ED1
0x180008cea  mov     byte ptr [rbx+0Ch], 1
0x180008cee  mov     eax, r15d
0x180008cf1  mov     rcx, [rsp+1A8h]; this
0x180008cf9  test    eax, eax
0x180008cfb  js      loc_180008FA2
0x180008d01  mov     [rbp+120h+packageFullNameLength], r15d
0x180008d05  lea     rax, [rbp+120h+packageFullNameLength]
0x180008d09  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180008d0e  mov     r9d, 4; TokenInformationLength
0x180008d14  lea     r8, [rbx+8]; TokenInformation
0x180008d18  mov     edx, 0Ch; TokenInformationClass
0x180008d1d  mov     rcx, rdi; TokenHandle
0x180008d20  call    cs:__imp_GetTokenInformation
0x180008d26  mov     rcx, [rsp+1A8h]; this
0x180008d2e  test    eax, eax
0x180008d30  jz      loc_180009016
0x180008d36  lea     rax, [rbp+120h+var_108]
0x180008d3a  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180008d3f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180008d45  lea     r8, [rbx+20h]; TokenInformation
0x180008d49  mov     edx, 1; TokenInformationClass
0x180008d4e  mov     rcx, rdi; TokenHandle
0x180008d51  call    cs:__imp_GetTokenInformation
0x180008d57  mov     rcx, [rsp+1A8h]; this
0x180008d5f  test    eax, eax
0x180008d61  jz      loc_180009027
0x180008d67  mov     rdx, [rbx+20h]; PrincipalSelfSid
0x180008d6b  mov     [rbx+78h], rdx
0x180008d6f  xorps   xmm0, xmm0
0x180008d72  xor     eax, eax
0x180008d74  movups  xmmword ptr [rbp+120h+var_60.PrivilegeCount], xmm0
0x180008d7b  mov     [rbp+120h+var_60.Privilege.Attributes], eax
0x180008d81  mov     [rbp+120h+TokenInformation], r15d
0x180008d85  mov     [rbp+120h+var_110], r15d
0x180008d89  mov     [rbp+120h+var_11C], 14h
0x180008d90  mov     [rbp+120h+packageFullNameLength], r15d
0x180008d94  mov     [rbx+2], al
0x180008d97  test    rdx, rdx
0x180008d9a  jz      loc_18000908B
0x180008da0  lea     rax, [rbp+120h+var_110]
0x180008da4  mov     [rsp+1A0h+AccessStatus], rax; AccessStatus
0x180008da9  lea     rax, [rbp+120h+TokenInformation]
0x180008dad  mov     [rsp+1A0h+GrantedAccess], rax; GrantedAccess
0x180008db2  lea     rax, [rbp+120h+var_11C]
0x180008db6  mov     [rsp+1A0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180008dbb  lea     rax, [rbp+120h+var_60]
0x180008dc2  mov     [rsp+1A0h+PrivilegeSet], rax; PrivilegeSet
0x180008dc7  lea     rax, GenericMapping
0x180008dce  mov     [rsp+1A0h+GenericMapping], rax; GenericMapping
0x180008dd3  mov     [rsp+1A0h+ObjectTypeListLength], r15d; ObjectTypeListLength
0x180008dd8  mov     [rsp+1A0h+ReturnLength], r15; int
0x180008ddd  mov     r9d, 1; DesiredAccess
0x180008de3  mov     r8, rdi; ClientToken
0x180008de6  lea     rcx, qword_18010A700; pSecurityDescriptor
0x180008ded  call    cs:__imp_AccessCheckByType
0x180008df3  mov     rcx, [rsp+1A8h]; this
0x180008dfb  test    eax, eax
0x180008dfd  jz      loc_180009038
0x180008e03  cmp     [rbp+120h+var_110], 0
0x180008e07  jz      short loc_180008E13
0x180008e09  test    byte ptr [rbp+120h+TokenInformation], 1
0x180008e0d  jz      short loc_180008E13
0x180008e0f  mov     byte ptr [rbx+2], 1
0x180008e13  test    rsi, rsi
0x180008e16  jz      loc_1800091A9
0x180008e1c  mov     [rsi], r15d
0x180008e1f  xorps   xmm0, xmm0
0x180008e22  movups  [rbp+120h+var_D8], xmm0
0x180008e26  movups  [rbp+120h+var_C8], xmm0
0x180008e2a  movups  [rbp+120h+var_B8], xmm0
0x180008e2e  movups  [rbp+120h+var_A8], xmm0
0x180008e32  movups  [rbp+120h+var_98], xmm0
0x180008e39  movups  [rbp+120h+var_88], xmm0
0x180008e40  movups  [rbp+120h+var_78], xmm0
0x180008e47  mov     dword ptr [rbp+120h+RpcCallAttributes], 3
0x180008e4e  mov     dword ptr [rbp+120h+RpcCallAttributes+4], 70h ; 'p'
0x180008e55  lea     rdx, [rbp+120h+RpcCallAttributes]; RpcCallAttributes
0x180008e59  xor     ecx, ecx; ClientBinding
0x180008e5b  call    cs:__imp_RpcServerInqCallAttributesW
0x180008e61  test    eax, eax
0x180008e63  jnz     loc_180009179
0x180008e69  mov     eax, dword ptr [rbp+120h+var_A8+8]
0x180008e6f  mov     [rsi], eax
0x180008e71  cmp     byte ptr [rbx+1], 0
0x180008e75  jnz     loc_180008FCC
0x180008e7b  mov     [rbx+84h], r15w
0x180008e83  mov     rcx, [rbp+120h+TokenHandle]; hObject
0x180008e87  lea     rax, [rcx-1]
0x180008e8b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008e8f  jbe     loc_180009283
0x180008e95  xor     eax, eax
0x180008e97  mov     rcx, [rbp+120h+var_48]
0x180008e9e  xor     rcx, rsp; StackCookie
0x180008ea1  call    __security_check_cookie
0x180008ea6  add     rsp, 168h
0x180008ead  pop     r15
0x180008eaf  pop     r14
0x180008eb1  pop     r13
0x180008eb3  pop     r12
0x180008eb5  pop     rdi
0x180008eb6  pop     rsi
0x180008eb7  pop     rbx
0x180008eb8  pop     rbp
0x180008eb9  retn
0x180008eba  mov     r9d, 80004003h; char *
0x180008ec0  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008ec7  mov     edx, 1CCh; void *
0x180008ecc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008ed1  mov     [rbp+120h+var_11C], r15d
0x180008ed5  mov     [rbp+120h+TokenInformation], r15d
0x180008ed9  mov     [rbp+120h+packageFullNameLength], r15d
0x180008edd  xorps   xmm0, xmm0
0x180008ee0  xor     eax, eax
0x180008ee2  movups  xmmword ptr [rbp+120h+var_60.PrivilegeCount], xmm0
0x180008ee9  mov     [rbp+120h+var_60.Privilege.Attributes], eax
0x180008eef  xor     r13b, r13b
0x180008ef2  mov     r12, rdi
0x180008ef5  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180008efc  test    rdi, rdi
0x180008eff  cmovz   r12, rax
0x180008f03  lea     rax, [rbp+120h+packageFullNameLength]
0x180008f07  mov     [rsp+1A0h+ReturnLength], rax; unsigned int
0x180008f0c  mov     r9d, 4; TokenInformationLength
0x180008f12  lea     r8, [rbp+120h+TokenInformation]; TokenInformation
0x180008f16  mov     edx, 1Dh; TokenInformationClass
0x180008f1b  mov     rcx, r12; TokenHandle
0x180008f1e  call    cs:__imp_GetTokenInformation
0x180008f24  mov     r15d, eax
0x180008f27  test    eax, eax
0x180008f29  jz      short loc_180008F7E
0x180008f2b  cmp     [rbp+120h+var_11C], 0
0x180008f2f  jnz     short loc_180008F71
0x180008f31  xor     r8d, r8d
0x180008f34  cmp     [rbp+120h+TokenInformation], r8d
0x180008f38  setnz   r8b
0x180008f3c  lea     r9, [rbp+120h+var_11C]
0x180008f40  lea     rdx, ?CapMumaGroupSidBuffer@@3PAEA; uchar near * CapMumaGroupSidBuffer
0x180008f47  mov     rcx, r12
0x180008f4a  call    cs:__imp_CheckTokenMembershipEx
0x180008f50  mov     r15d, eax
0x180008f53  test    eax, eax
0x180008f55  jz      short loc_180008F7E
0x180008f57  cmp     [rbp+120h+var_11C], 0
0x180008f5b  jnz     short loc_180008F71
0x180008f5d  call    cs:__imp_RtlIsMultiSessionSku
0x180008f63  test    al, al
0x180008f65  jz      loc_18000905C
0x180008f6b  cmp     [rbp+120h+var_11C], 0
0x180008f6f  jz      short loc_180008F87
0x180008f71  cmp     [rbp+120h+TokenInformation], 0
0x180008f75  jnz     loc_1800090C5
0x180008f7b  mov     r13b, 1
0x180008f7e  test    r15d, r15d
0x180008f81  jz      loc_180009228
0x180008f87  xor     r15d, r15d
0x180008f8a  cmp     [rbp+120h+var_110], r15d
0x180008f8e  jnz     loc_180008CEA
0x180008f94  test    r13b, r13b
0x180008f97  jz      loc_180008CEE
0x180008f9d  jmp     loc_180008CEA
0x180008fa2  mov     r9d, eax; char *
0x180008fa5  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008fac  mov     edx, 1E0h; void *
0x180008fb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008fb7  mov     r9d, eax; char *
0x180008fba  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180008fc1  mov     edx, 37h ; '7'; void *
0x180008fc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180008fcc  mov     [rbp+120h+packageFullNameLength], 80h
0x180008fd3  lea     r8, [rbx+84h]; packageFullName
0x180008fda  lea     rdx, [rbp+120h+packageFullNameLength]; packageFullNameLength
0x180008fde  mov     rcx, rdi; token
0x180008fe1  call    cs:__imp_GetPackageFullNameFromToken
0x180008fe7  cmp     eax, 3D54h
0x180008fec  jz      loc_180008E7B
0x180008ff2  mov     rcx, [rsp+1A8h]; this
0x180008ffa  test    eax, eax
0x180008ffc  jz      loc_180008E83
0x180009002  mov     r9d, eax; char *
0x180009005  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000900c  mov     edx, 1F3h; void *
0x180009011  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009016  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000901d  mov     edx, 1AEh; void *
0x180009022  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009027  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000902e  mov     edx, 1E2h; void *
0x180009033  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180009038  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000903f  mov     edx, 119h; void *
0x180009044  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000904a  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180009051  mov     edx, 39h ; '9'; void *
0x180009056  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000905c  xor     r8d, r8d
0x18000905f  cmp     [rbp+120h+TokenInformation], r8d
0x180009063  setnz   r8b
0x180009067  lea     r9, [rbp+120h+var_11C]
0x18000906b  lea     rdx, ?DefaultAliasWellKnownSid@@3PAEA; uchar near * DefaultAliasWellKnownSid
0x180009072  mov     rcx, r12
0x180009075  call    cs:__imp_CheckTokenMembershipEx
0x18000907b  mov     r15d, eax
0x18000907e  test    eax, eax
0x180009080  jnz     loc_180008F6B
0x180009086  jmp     loc_180008F7E
0x18000908b  lea     rax, [rbp+120h+packageFullNameLength]
0x18000908f  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180009094  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000909a  lea     r8, [rbp+120h+RpcCallAttributes]; TokenInformation
0x18000909e  mov     edx, 1; TokenInformationClass
0x1800090a3  mov     rcx, rdi; TokenHandle
  ... truncated ...
```
