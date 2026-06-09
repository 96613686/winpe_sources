# GetCallerInformation(_BASIC_CALLER_INFORMATION *,_EXTENDED_CALLER_INFORMATION *)

- ea: `0x1800092a0`
- end: `0x180009ae8`
- name: `?GetCallerInformation@@YAXPEAU_BASIC_CALLER_INFORMATION@@PEAU_EXTENDED_CALLER_INFORMATION@@@Z`
- size: `2120`
- prototype: `void __fastcall(struct _BASIC_CALLER_INFORMATION *, struct _EXTENDED_CALLER_INFORMATION *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c2c0`

## callees

- `0x1800088e8`
- `0x1800092a0`
- `0x18000ab00`
- `0x18000ab90`
- `0x18000ac00`
- `0x18000acdc`
- `0x18000c4f0`
- `0x18004a9cc`
- `0x18004e508`
- `0x18004e58c`
- `0x180061e1c`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000949a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009700`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009469`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000949a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180009700`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800098d4`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180009536`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x180009536`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009981`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180009981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800099b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000933e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000933e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180009939`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000994b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000994b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009356`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009add`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000941b`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180009901`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x18000941b`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x180009901`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180009730`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800098a3`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180009730`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800098a3`
- `ntdll!RtlNtStatusToDosError` at `0x180009318`
- `ntdll!RtlNtStatusToDosError` at `0x180009318`
- `ntdll!RtlIsMultiSessionSku` at `0x180009743`
- `ntdll!RtlIsMultiSessionSku` at `0x180009743`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009310`
- `RPCRT4!I_RpcMapWin32Status` at `0x180009310`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800095a4`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800095a4`
- `RPCRT4!RpcRevertToSelf` at `0x180009372`
- `RPCRT4!RpcRevertToSelf` at `0x180009372`
- `RPCRT4!RpcImpersonateClient` at `0x1800092fd`
- `RPCRT4!RpcImpersonateClient` at `0x1800092fd`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000980c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFullNameFromToken` at `0x18000980c`

## string_xrefs

- `0x1800099e7`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x180009a12`: `onecore\ds\security\umstartup\usermgr\lib\comutils.cpp`
- `0x180009613`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x18000978c`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800097a1`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x1800097e5`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009830`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009842`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009854`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009866`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009878`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009997`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009a34`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009a46`: `onecore\ds\security\umstartup\usermgr\lib\tokenaccess.cpp`
- `0x180009693`: `xboxAccessoryManagement`
- `0x1800097cc`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x1800099c3`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall GetCallerInformation(struct _BASIC_CALLER_INFORMATION *a1, struct _EXTENDED_CALLER_INFORMATION *a2)
{
  unsigned __int64 v2; // rbp
  RPC_STATUS v5; // eax
  NTSTATUS v6; // eax
  signed int v7; // eax
  HANDLE CurrentThread; // rax
  const char *v9; // r9
  char *v10; // rcx
  char v11; // al
  void *v12; // rdi
  DWORD *v13; // rsi
  const char *v14; // r9
  int v15; // eax
  const char *v16; // r9
  const char *v17; // r9
  void *v18; // rdx
  const char *v19; // r9
  int v20; // eax
  DWORD CurrentProcessId; // eax
  char *v22; // rcx
  unsigned __int8 v23; // cl
  const char *v24; // r9
  char v25; // al
  __int64 v26; // r13
  char v29; // al
  DWORD v30; // eax
  unsigned int PackageFullNameFromToken; // eax
  const char *v33; // r9
  char *v35; // rsi
  HANDLE CurrentProcess; // rax
  const char *v37; // r9
  const char *v38; // r9
  bool v39; // sf
  DWORD LastError; // edi
  unsigned int ReturnLength; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-60h]
  unsigned __int8 v43[4]; // [rsp+80h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+118h]

  v2 = (unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)v2 = 0;
  *(_QWORD *)(v2 + 24) = 0;
  *(_QWORD *)(v2 + 192) = (unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL;
  *(_BYTE *)(v2 + 200) = 1;
  *(_QWORD *)(v2 + 32) = 0;
  v5 = RpcImpersonateClient(0);
  if ( v5 == 1725 )
  {
    v35 = *(char **)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v35);
      SetLastError(LastError);
    }
    *(_QWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xAu, (PHANDLE)(v2 + 24)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v37);
    if ( !DuplicateTokenEx(
            *(HANDLE *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18),
            0,
            0,
            SecurityImpersonation,
            TokenImpersonation,
            (PHANDLE)(v2 + 32)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v38);
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
    *(_BYTE *)v2 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, (PHANDLE)(v2 + 32)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v9);
  }
  if ( *(_BYTE *)v2 )
    RpcRevertToSelf();
  v10 = *(char **)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x18) = 0;
  if ( a1 )
  {
    if ( a2 )
      goto LABEL_12;
  }
  else if ( !a2 )
  {
LABEL_12:
    v11 = 0;
    goto LABEL_13;
  }
  v11 = 1;
LABEL_13:
  if ( !v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)0x80004003LL,
      ReturnLength);
  v12 = *(void **)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
  if ( !a1 )
    a1 = a2;
  *(_WORD *)a1 = 256;
  *((_BYTE *)a1 + 12) = 0;
  *((_DWORD *)a1 + 2) = -1;
  *((_BYTE *)a1 + 1) = IsTokenAppContainer(v12);
  *(_BYTE *)a1 = DoesTokenHasPrivilege(v12, 7u);
  v13 = (DWORD *)((char *)a1 + 4);
  *((_DWORD *)a1 + 1) = 0;
  *((_DWORD *)a1 + 32) = DoesTokenHasPrivilege(v12, 0x1Du);
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *((_BYTE *)a1 + 12) = 0;
  if ( (unsigned int)CheckTokenCapability(v12, &CapMumaSidBuffer, v2 + 16) )
  {
    if ( *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) )
    {
LABEL_18:
      *((_BYTE *)a1 + 12) = 1;
LABEL_19:
      v15 = 0;
      goto LABEL_20;
    }
    *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 0;
    *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
    *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
    *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
    *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
    *(_BYTE *)v2 = 0;
    v26 = (__int64)v12;
    if ( !v12 )
      v26 = -6;
    if ( !GetTokenInformation((HANDLE)v26, TokenIsAppContainer, (LPVOID)(v2 + 8), 4u, (PDWORD)(v2 + 12)) )
      goto LABEL_59;
    if ( !*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
    {
      if ( !(unsigned int)CheckTokenMembershipEx(
                            v26,
                            &CapMumaGroupSidBuffer,
                            *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                            v2 + 4) )
        goto LABEL_59;
      if ( !*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
      {
        if ( !(unsigned __int8)RtlIsMultiSessionSku()
          && !(unsigned int)CheckTokenMembershipEx(
                              v26,
                              &DefaultAliasWellKnownSid,
                              *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) != 0,
                              v2 + 4) )
        {
          goto LABEL_59;
        }
        if ( !*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
          goto LABEL_75;
      }
    }
    if ( !*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) )
    {
LABEL_53:
      v29 = 1;
      *(_BYTE *)v2 = 1;
      goto LABEL_54;
    }
    if ( (unsigned int)CheckTokenCapability(v26, &CapMumaSidBuffer, v2 + 4) )
    {
      if ( *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) )
        goto LABEL_53;
LABEL_75:
      v29 = 0;
      goto LABEL_54;
    }
LABEL_59:
    v30 = GetLastError();
    if ( v30 )
    {
      v15 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x18D,
              (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
              (const char *)v30,
              ReturnLength);
      goto LABEL_20;
    }
    v29 = *(_BYTE *)v2;
LABEL_54:
    if ( !*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) && !v29 )
      goto LABEL_19;
    goto LABEL_18;
  }
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x184,
          (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
          v14);
LABEL_20:
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      (const char *)(unsigned int)v15,
      ReturnLength);
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  if ( !GetTokenInformation(v12, TokenSessionId, (char *)a1 + 8, 4u, (PDWORD)(v2 + 12)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v16);
  if ( !GetTokenInformation(v12, TokenUser, (char *)a1 + 32, 0x54u, (PDWORD)(v2 + 24)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v17);
  v18 = (void *)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 15) = v18;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC0) = 0;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xD0) = 0;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) = 0;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10) = 0;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 20;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 0;
  *((_BYTE *)a1 + 2) = 0;
  if ( !v18 )
  {
    if ( !GetTokenInformation(v12, TokenUser, (LPVOID)(v2 + 64), 0x54u, (PDWORD)(v2 + 12)) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v33);
    v18 = *(void **)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40);
  }
  if ( !AccessCheckByType(
          qword_18010A700,
          v18,
          v12,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&GenericMapping,
          (PPRIVILEGE_SET)(v2 + 192),
          (LPDWORD)(v2 + 4),
          (LPDWORD)(v2 + 8),
          (LPBOOL)(v2 + 16)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
      v19);
  if ( *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x10)
    && (*(_BYTE *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 8) & 1) != 0 )
  {
    *((_BYTE *)a1 + 2) = 1;
  }
  if ( a1 == (struct _BASIC_CALLER_INFORMATION *)-4LL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
      (const char *)0x80004003LL,
      ReturnLengtha);
    goto LABEL_32;
  }
  *v13 = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x48) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x58) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x68) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x78) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x88) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x98) = 0;
  *(_OWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xA8) = 0;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x40) = 3;
  *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x44) = 112;
  v20 = RpcServerInqCallAttributesW(0, (void *)(v2 + 64));
  if ( !v20 )
  {
    CurrentProcessId = *(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x80);
LABEL_31:
    *v13 = CurrentProcessId;
    goto LABEL_32;
  }
  if ( v20 == 1725 )
  {
    CurrentProcessId = GetCurrentProcessId();
    goto LABEL_31;
  }
  v39 = v20 < 0;
  if ( v20 > 0 )
  {
    v20 = (unsigned __int16)v20 | 0x80070000;
    v39 = v20 < 0;
  }
  if ( v39 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\comutils.cpp",
      (const char *)(unsigned int)v20,
      ReturnLengtha);
LABEL_32:
  if ( !*((_BYTE *)a1 + 1)
    || (*(_DWORD *)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0xC) = 128,
        PackageFullNameFromToken = GetPackageFullNameFromToken(v12, (UINT32 *)(v2 + 12), (PWSTR)a1 + 66),
        PackageFullNameFromToken == 15700) )
  {
    *((_WORD *)a1 + 66) = 0;
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
  if ( a2 )
  {
    v23 = (_BYTE)word_180148290 == 0;
    v24 = 0;
    v25 = 0;
    *(_BYTE *)v2 = 0;
    if ( SeAllowSessionImpersonation )
    {
      v24 = (const char *)CheckTokenForAccessThroughCapability(
                            v12,
                            0,
                            &CapSessionImpersonationGroupSidBuffer,
                            &CapSessionImpersonationSidBuffer,
                            v23,
                            0,
                            (unsigned __int8 *)((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL));
      v25 = *(_BYTE *)v2;
    }
    if ( (_DWORD)v24 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1FF,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\tokenaccess.cpp",
        v24,
        ReturnLengtha);
    if ( v25 )
      *((_BYTE *)a2 + 416) = 1;
    *((_BYTE *)a2 + 417) = (int)CapabilityAccessCheck(v12, L"userSigninSupport") >= 0;
    *((_BYTE *)a2 + 418) = (int)CapabilityAccessCheck(v12, L"shellExperience") >= 0;
    *((_BYTE *)a2 + 419) = (int)CapabilityAccessCheck(v12, L"xboxAccessoryManagement") >= 0;
  }
  v22 = *(char **)(((unsigned __int64)v43 & 0xFFFFFFFFFFFFFFE0uLL) + 0x20);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v22);
}

```

## disassembly

```asm
0x1800092a0  mov     [rsp-8+arg_10], rbx
0x1800092a5  push    rbp
0x1800092a6  push    rsi
0x1800092a7  push    rdi
0x1800092a8  push    r12
0x1800092aa  push    r13
0x1800092ac  push    r14
0x1800092ae  push    r15
0x1800092b0  sub     rsp, 160h
0x1800092b7  lea     rbp, [rsp+80h]
0x1800092bf  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1800092c3  mov     rax, cs:__security_cookie
0x1800092ca  xor     rax, rsp
0x1800092cd  mov     [rbp+110h+var_38], rax
0x1800092d4  mov     r15, rdx
0x1800092d7  mov     rbx, rcx
0x1800092da  mov     [rbp+110h+var_110], 0
0x1800092de  xor     r13d, r13d
0x1800092e1  mov     qword ptr [rbp+110h+var_F8], r13
0x1800092e5  lea     rax, [rbp+110h+var_110]
0x1800092e9  mov     qword ptr [rbp+110h+var_50.PrivilegeCount], rax
0x1800092f0  mov     byte ptr [rbp+110h+var_50.Privilege.Luid.LowPart], 1
0x1800092f7  mov     [rbp+110h+TokenHandle], r13
0x1800092fb  xor     ecx, ecx; BindingHandle
0x1800092fd  call    cs:__imp_RpcImpersonateClient
0x180009303  cmp     eax, 6BDh
0x180009308  jz      loc_180009923
0x18000930e  mov     ecx, eax; Status
0x180009310  call    cs:__imp_I_RpcMapWin32Status
0x180009316  mov     ecx, eax; Status
0x180009318  call    cs:__imp_RtlNtStatusToDosError
0x18000931e  test    eax, eax
0x180009320  jle     short loc_18000932A
0x180009322  movzx   eax, ax
0x180009325  or      eax, 80070000h
0x18000932a  mov     rcx, [rsp+198h]; this
0x180009332  test    eax, eax
0x180009334  js      loc_18000979E
0x18000933a  mov     [rbp+110h+var_110], 1
0x18000933e  call    cs:__imp_GetCurrentThread
0x180009344  mov     rcx, rax; ThreadHandle
0x180009347  lea     r9, [rbp+110h+TokenHandle]; TokenHandle
0x18000934b  mov     edx, 8; DesiredAccess
0x180009350  mov     r8d, 1; OpenAsSelf
0x180009356  call    cs:__imp_OpenThreadToken
0x18000935c  mov     rcx, [rsp+198h]; this
0x180009364  test    eax, eax
0x180009366  jz      loc_180009878
0x18000936c  cmp     [rbp+110h+var_110], 0
0x180009370  jz      short loc_180009379
0x180009372  call    cs:__imp_RpcRevertToSelf
0x180009378  nop
0x180009379  mov     rcx, qword ptr [rbp+110h+var_F8]; hObject
0x18000937d  lea     rax, [rcx-1]
0x180009381  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009385  jbe     loc_180009A86
0x18000938b  mov     [rbp+110h+var_F8], r13d
0x18000938f  test    rbx, rbx
0x180009392  jnz     loc_180009A58
0x180009398  test    r15, r15
0x18000939b  jnz     loc_180009A61
0x1800093a1  xor     al, al
0x1800093a3  mov     rcx, [rsp+198h]; this
0x1800093ab  test    al, al
0x1800093ad  jz      loc_18000960D
0x1800093b3  mov     rdi, [rbp+110h+TokenHandle]
0x1800093b7  test    rbx, rbx
0x1800093ba  cmovz   rbx, r15
0x1800093be  mov     word ptr [rbx], 100h
0x1800093c3  mov     byte ptr [rbx+0Ch], 0
0x1800093c7  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1800093ce  mov     rcx, rdi; void *
0x1800093d1  call    ?IsTokenAppContainer@@YA_NPEAX@Z; IsTokenAppContainer(void *)
0x1800093d6  mov     [rbx+1], al
0x1800093d9  mov     edx, 7; unsigned int
0x1800093de  mov     rcx, rdi; void *
0x1800093e1  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x1800093e6  mov     [rbx], al
0x1800093e8  lea     rsi, [rbx+4]
0x1800093ec  mov     [rsi], r13d
0x1800093ef  mov     edx, 1Dh; unsigned int
0x1800093f4  mov     rcx, rdi; void *
0x1800093f7  call    ?DoesTokenHasPrivilege@@YA_NPEAXK@Z; DoesTokenHasPrivilege(void *,ulong)
0x1800093fc  movzx   eax, al
0x1800093ff  mov     [rbx+80h], eax
0x180009405  mov     [rbp+110h+var_100], r13d
0x180009409  mov     byte ptr [rbx+0Ch], 0
0x18000940d  lea     r8, [rbp+110h+var_100]
0x180009411  lea     rdx, ?CapMumaSidBuffer@@3PAEA; uchar near * CapMumaSidBuffer
0x180009418  mov     rcx, rdi
0x18000941b  call    cs:__imp_CheckTokenCapability
0x180009421  test    eax, eax
0x180009423  jz      loc_1800099BB
0x180009429  cmp     [rbp+110h+var_100], 0
0x18000942d  jz      loc_1800096B3
0x180009433  mov     byte ptr [rbx+0Ch], 1
0x180009437  mov     eax, r13d
0x18000943a  mov     rcx, [rsp+198h]; this
0x180009442  test    eax, eax
0x180009444  js      loc_180009789
0x18000944a  mov     [rbp+110h+packageFullNameLength], r13d
0x18000944e  lea     rax, [rbp+110h+packageFullNameLength]
0x180009452  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180009457  mov     r9d, 4; TokenInformationLength
0x18000945d  lea     r8, [rbx+8]; TokenInformation
0x180009461  mov     edx, 0Ch; TokenInformationClass
0x180009466  mov     rcx, rdi; TokenHandle
0x180009469  call    cs:__imp_GetTokenInformation
0x18000946f  mov     rcx, [rsp+198h]; this
0x180009477  test    eax, eax
0x180009479  jz      loc_180009842
0x18000947f  lea     rax, [rbp+110h+var_F8]
0x180009483  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x180009488  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000948e  lea     r8, [rbx+20h]; TokenInformation
0x180009492  mov     edx, 1; TokenInformationClass
0x180009497  mov     rcx, rdi; TokenHandle
0x18000949a  call    cs:__imp_GetTokenInformation
0x1800094a0  mov     rcx, [rsp+198h]; this
0x1800094a8  test    eax, eax
0x1800094aa  jz      loc_180009854
0x1800094b0  mov     rdx, [rbx+20h]; PrincipalSelfSid
0x1800094b4  mov     [rbx+78h], rdx
0x1800094b8  xorps   xmm0, xmm0
0x1800094bb  xor     eax, eax
0x1800094bd  movups  xmmword ptr [rbp+110h+var_50.PrivilegeCount], xmm0
0x1800094c4  mov     [rbp+110h+var_50.Privilege.Attributes], eax
0x1800094ca  mov     [rbp+110h+TokenInformation], r13d
0x1800094ce  mov     [rbp+110h+var_100], r13d
0x1800094d2  mov     [rbp+110h+var_10C], 14h
0x1800094d9  mov     [rbp+110h+packageFullNameLength], r13d
0x1800094dd  mov     [rbx+2], al
0x1800094e0  test    rdx, rdx
0x1800094e3  jz      loc_1800098B9
0x1800094e9  lea     rax, [rbp+110h+var_100]
0x1800094ed  mov     [rsp+190h+AccessStatus], rax; AccessStatus
0x1800094f2  lea     rax, [rbp+110h+TokenInformation]
0x1800094f6  mov     [rsp+190h+GrantedAccess], rax; GrantedAccess
0x1800094fb  lea     rax, [rbp+110h+var_10C]
0x1800094ff  mov     [rsp+190h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180009504  lea     rax, [rbp+110h+var_50]
0x18000950b  mov     [rsp+190h+PrivilegeSet], rax; PrivilegeSet
0x180009510  lea     rax, GenericMapping
0x180009517  mov     [rsp+190h+GenericMapping], rax; GenericMapping
0x18000951c  mov     [rsp+190h+ObjectTypeListLength], r13d; ObjectTypeListLength
0x180009521  mov     [rsp+190h+ReturnLength], r13; int
0x180009526  mov     r9d, 1; DesiredAccess
0x18000952c  mov     r8, rdi; ClientToken
0x18000952f  lea     rcx, qword_18010A700; pSecurityDescriptor
0x180009536  call    cs:__imp_AccessCheckByType
0x18000953c  mov     rcx, [rsp+198h]; this
0x180009544  test    eax, eax
0x180009546  jz      loc_180009866
0x18000954c  cmp     [rbp+110h+var_100], 0
0x180009550  jz      short loc_18000955C
0x180009552  test    byte ptr [rbp+110h+TokenInformation], 1
0x180009556  jz      short loc_18000955C
0x180009558  mov     byte ptr [rbx+2], 1
0x18000955c  test    rsi, rsi
0x18000955f  jz      loc_1800099D9
0x180009565  mov     [rsi], r13d
0x180009568  xorps   xmm0, xmm0
0x18000956b  movups  [rbp+110h+var_C8], xmm0
0x18000956f  movups  [rbp+110h+var_B8], xmm0
0x180009573  movups  [rbp+110h+var_A8], xmm0
0x180009577  movups  [rbp+110h+var_98], xmm0
0x18000957b  movups  [rbp+110h+var_88], xmm0
0x180009582  movups  [rbp+110h+var_78], xmm0
0x180009589  movups  [rbp+110h+var_68], xmm0
0x180009590  mov     dword ptr [rbp+110h+RpcCallAttributes], 3
0x180009597  mov     dword ptr [rbp+110h+RpcCallAttributes+4], 70h ; 'p'
0x18000959e  lea     rdx, [rbp+110h+RpcCallAttributes]; RpcCallAttributes
0x1800095a2  xor     ecx, ecx; ClientBinding
0x1800095a4  call    cs:__imp_RpcServerInqCallAttributesW
0x1800095aa  test    eax, eax
0x1800095ac  jnz     loc_1800099A9
0x1800095b2  mov     eax, dword ptr [rbp+110h+var_98+8]
0x1800095b8  mov     [rsi], eax
0x1800095ba  cmp     byte ptr [rbx+1], 0
0x1800095be  jnz     loc_1800097F7
0x1800095c4  mov     [rbx+84h], r13w
0x1800095cc  test    r15, r15
0x1800095cf  jnz     short loc_180009625
0x1800095d1  mov     rcx, [rbp+110h+TokenHandle]; hObject
0x1800095d5  lea     rax, [rcx-1]
0x1800095d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800095dd  jbe     loc_180009ADD
0x1800095e3  mov     rcx, [rbp+110h+var_38]
0x1800095ea  xor     rcx, rsp; StackCookie
0x1800095ed  call    __security_check_cookie
0x1800095f2  mov     rbx, [rsp+190h+arg_10]
0x1800095fa  add     rsp, 160h
0x180009601  pop     r15
0x180009603  pop     r14
0x180009605  pop     r13
0x180009607  pop     r12
0x180009609  pop     rdi
0x18000960a  pop     rsi
0x18000960b  pop     rbp
0x18000960c  retn
0x18000960d  mov     r9d, 80004003h; char *
0x180009613  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x18000961a  mov     edx, 1CCh; void *
0x18000961f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009625  cmp     byte ptr cs:word_180148290, 0
0x18000962c  setz    cl
0x18000962f  mov     r9d, r13d; char *
0x180009632  xor     al, al
0x180009634  mov     [rbp+110h+var_110], al
0x180009637  cmp     cs:?SeAllowSessionImpersonation@@3KA, 0; ulong SeAllowSessionImpersonation
0x18000963e  jnz     loc_180009A9A
0x180009644  mov     rcx, [rsp+198h]; this
0x18000964c  test    r9d, r9d
0x18000964f  jnz     loc_1800097E5
0x180009655  test    al, al
0x180009657  jnz     loc_180009AD0
0x18000965d  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x180009664  mov     rcx, rdi; void *
0x180009667  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x18000966c  shr     eax, 1Fh
0x18000966f  xor     al, 1
0x180009671  mov     [r15+1A1h], al
0x180009678  lea     rdx, aShellexperienc; "shellExperience"
0x18000967f  mov     rcx, rdi; void *
0x180009682  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x180009687  shr     eax, 1Fh
0x18000968a  xor     al, 1
0x18000968c  mov     [r15+1A2h], al
0x180009693  lea     rdx, aXboxaccessorym; "xboxAccessoryManagement"
0x18000969a  mov     rcx, rdi; void *
0x18000969d  call    ?CapabilityAccessCheck@@YAJPEAXPEBG@Z; CapabilityAccessCheck(void *,ushort const *)
0x1800096a2  shr     eax, 1Fh
0x1800096a5  xor     al, 1
0x1800096a7  mov     [r15+1A3h], al
0x1800096ae  jmp     loc_1800095D1
0x1800096b3  mov     [rbp+110h+var_10C], r13d
0x1800096b7  mov     [rbp+110h+TokenInformation], r13d
0x1800096bb  mov     [rbp+110h+packageFullNameLength], r13d
0x1800096bf  xorps   xmm0, xmm0
0x1800096c2  xor     eax, eax
0x1800096c4  movups  xmmword ptr [rbp+110h+var_50.PrivilegeCount], xmm0
0x1800096cb  mov     [rbp+110h+var_50.Privilege.Attributes], eax
0x1800096d1  mov     [rbp+110h+var_110], al
0x1800096d4  mov     r13, rdi
0x1800096d7  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800096de  test    rdi, rdi
0x1800096e1  cmovz   r13, rax
0x1800096e5  lea     rax, [rbp+110h+packageFullNameLength]
0x1800096e9  mov     [rsp+190h+ReturnLength], rax; unsigned int
0x1800096ee  mov     r9d, 4; TokenInformationLength
0x1800096f4  lea     r8, [rbp+110h+TokenInformation]; TokenInformation
0x1800096f8  mov     edx, 1Dh; TokenInformationClass
0x1800096fd  mov     rcx, r13; TokenHandle
0x180009700  call    cs:__imp_GetTokenInformation
0x180009706  mov     r14d, eax
0x180009709  test    eax, eax
0x18000970b  jz      loc_1800097B3
0x180009711  cmp     [rbp+110h+var_10C], 0
0x180009715  jnz     short loc_18000975B
0x180009717  xor     r8d, r8d
0x18000971a  cmp     [rbp+110h+TokenInformation], r8d
0x18000971e  setnz   r8b
0x180009722  lea     r9, [rbp+110h+var_10C]
0x180009726  lea     rdx, ?CapMumaGroupSidBuffer@@3PAEA; uchar near * CapMumaGroupSidBuffer
0x18000972d  mov     rcx, r13
0x180009730  call    cs:__imp_CheckTokenMembershipEx
0x180009736  mov     r14d, eax
0x180009739  test    eax, eax
0x18000973b  jz      short loc_1800097B3
0x18000973d  cmp     [rbp+110h+var_10C], 0
0x180009741  jnz     short loc_18000975B
0x180009743  call    cs:__imp_RtlIsMultiSessionSku
0x180009749  test    al, al
0x18000974b  jz      loc_18000988A
0x180009751  cmp     [rbp+110h+var_10C], 0
0x180009755  jz      loc_18000991C
0x18000975b  cmp     [rbp+110h+TokenInformation], 0
0x18000975f  jnz     loc_1800098F3
0x180009765  mov     al, 1
0x180009767  mov     [rbp+110h+var_110], al
0x18000976a  test    r14d, r14d
0x18000976d  jz      short loc_1800097B3
0x18000976f  xor     r13d, r13d
0x180009772  cmp     [rbp+110h+var_100], r13d
0x180009776  jnz     loc_180009433
0x18000977c  test    al, al
0x18000977e  jz      loc_180009437
0x180009784  jmp     loc_180009433
0x180009789  mov     r9d, eax; char *
0x18000978c  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x180009793  mov     edx, 1E0h; void *
0x180009798  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000979e  mov     r9d, eax; char *
0x1800097a1  lea     r8, aOnecoreDsSecur_81; "onecore\\ds\\security\\umstartup\\userm"...
0x1800097a8  mov     edx, 37h ; '7'; void *
0x1800097ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800097b3  call    cs:__imp_GetLastError
0x1800097b9  test    eax, eax
0x1800097bb  jz      loc_180009A91
0x1800097c1  mov     rcx, [rsp+198h]; this
  ... truncated ...
```
