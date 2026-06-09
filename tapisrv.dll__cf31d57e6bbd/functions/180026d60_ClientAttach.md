# ClientAttach

- ea: `0x180026d60`
- end: `0x180027eb5`
- name: `ClientAttach`
- size: `4437`
- prototype: `__int64 __fastcall(_QWORD *, DWORD, HANDLE *, const WCHAR *, wchar_t *Str)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001600`
- `0x180001f50`
- `0x18001c740`
- `0x18001c7c0`
- `0x18001c854`
- `0x180026d60`
- `0x18002a130`
- `0x18002a5ac`
- `0x18002c8d4`
- `0x18002f410`
- `0x18003cb8c`
- `0x18003cd30`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`
- `0x180040010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002765b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027248`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002765b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026e94`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800276a3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800276c0`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180026e94`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800276a3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800276c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027d46`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180027c64`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180027c64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027ce2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180027ce2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c94`
- `RPCRT4!RpcRevertToSelf` at `0x1800270ac`
- `RPCRT4!RpcRevertToSelf` at `0x180027349`
- `RPCRT4!RpcRevertToSelf` at `0x180027b3e`
- `RPCRT4!RpcRevertToSelf` at `0x180027b7c`
- `RPCRT4!RpcRevertToSelf` at `0x180027bc8`
- `RPCRT4!RpcRevertToSelf` at `0x180027d6c`
- `RPCRT4!RpcRevertToSelf` at `0x180027e87`
- `RPCRT4!RpcRevertToSelf` at `0x1800270ac`
- `RPCRT4!RpcRevertToSelf` at `0x180027349`
- `RPCRT4!RpcRevertToSelf` at `0x180027b3e`
- `RPCRT4!RpcRevertToSelf` at `0x180027b7c`
- `RPCRT4!RpcRevertToSelf` at `0x180027bc8`
- `RPCRT4!RpcRevertToSelf` at `0x180027d6c`
- `RPCRT4!RpcRevertToSelf` at `0x180027e87`
- `RPCRT4!NdrClientCall3` at `0x18002799f`
- `RPCRT4!NdrClientCall3` at `0x18002799f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002746c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18002746c`
- `RPCRT4!RpcBindingFree` at `0x180027a14`
- `RPCRT4!RpcBindingFree` at `0x180027a14`
- `RPCRT4!RpcStringFreeW` at `0x1800277d5`
- `RPCRT4!RpcStringFreeW` at `0x180027a1f`
- `RPCRT4!RpcStringFreeW` at `0x1800277d5`
- `RPCRT4!RpcStringFreeW` at `0x180027a1f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcd6`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcf2`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fd0e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcd6`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fcf2`
- `RPCRT4!I_RpcExceptionFilter` at `0x18003fd0e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002770b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002770b`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180027929`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x180027929`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180027739`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180027739`
- `RPCRT4!RpcImpersonateClient` at `0x180026f6c`
- `RPCRT4!RpcImpersonateClient` at `0x180027af7`
- `RPCRT4!RpcImpersonateClient` at `0x180027bdc`
- `RPCRT4!RpcImpersonateClient` at `0x180026f6c`
- `RPCRT4!RpcImpersonateClient` at `0x180027af7`
- `RPCRT4!RpcImpersonateClient` at `0x180027bdc`
- `KERNEL32!GetComputerNameW` at `0x18002722e`
- `KERNEL32!GetComputerNameW` at `0x18002722e`
- `KERNEL32!HeapAlloc` at `0x180026ebf`
- `KERNEL32!HeapAlloc` at `0x180026f11`
- `KERNEL32!HeapAlloc` at `0x180026ff2`
- `KERNEL32!HeapAlloc` at `0x18002708c`
- `KERNEL32!HeapAlloc` at `0x180027377`
- `KERNEL32!HeapAlloc` at `0x1800273c3`
- `KERNEL32!HeapAlloc` at `0x180027421`
- `KERNEL32!HeapAlloc` at `0x18002761d`
- `KERNEL32!HeapAlloc` at `0x1800278a3`
- `KERNEL32!HeapAlloc` at `0x180026ebf`
- `KERNEL32!HeapAlloc` at `0x180026f11`
- `KERNEL32!HeapAlloc` at `0x180026ff2`
- `KERNEL32!HeapAlloc` at `0x18002708c`
- `KERNEL32!HeapAlloc` at `0x180027377`
- `KERNEL32!HeapAlloc` at `0x1800273c3`
- `KERNEL32!HeapAlloc` at `0x180027421`
- `KERNEL32!HeapAlloc` at `0x18002761d`
- `KERNEL32!HeapAlloc` at `0x1800278a3`
- `KERNEL32!GetMailslotInfo` at `0x18002757b`
- `KERNEL32!GetMailslotInfo` at `0x18002757b`
- `KERNEL32!GetCurrentThread` at `0x180026f8f`
- `KERNEL32!GetCurrentThread` at `0x180026f8f`
- `KERNEL32!CreateEventW` at `0x180027b6a`
- `KERNEL32!CreateEventW` at `0x180027b6a`
- `KERNEL32!OpenProcess` at `0x180027b15`
- `KERNEL32!OpenProcess` at `0x180027b15`
- `KERNEL32!CreateFileW` at `0x180027546`
- `KERNEL32!CreateFileW` at `0x180027546`
- `KERNEL32!GetPrivateProfileIntW` at `0x180027320`
- `KERNEL32!GetPrivateProfileIntW` at `0x180027320`
- `KERNEL32!CloseHandle` at `0x1800270a6`
- `KERNEL32!CloseHandle` at `0x180027343`
- `KERNEL32!CloseHandle` at `0x180027597`
- `KERNEL32!CloseHandle` at `0x180027e81`
- `KERNEL32!CloseHandle` at `0x1800270a6`
- `KERNEL32!CloseHandle` at `0x180027343`
- `KERNEL32!CloseHandle` at `0x180027597`
- `KERNEL32!CloseHandle` at `0x180027e81`
- `KERNEL32!GetLastError` at `0x180026fb2`
- `KERNEL32!GetLastError` at `0x180027039`
- `KERNEL32!GetLastError` at `0x180027058`
- `KERNEL32!GetLastError` at `0x180027146`
- `KERNEL32!GetLastError` at `0x1800271ed`
- `KERNEL32!GetLastError` at `0x1800275b8`
- `KERNEL32!GetLastError` at `0x180027b24`
- `KERNEL32!GetLastError` at `0x180027bb1`
- `KERNEL32!GetLastError` at `0x180027e5a`
- `KERNEL32!GetLastError` at `0x180026fb2`
- `KERNEL32!GetLastError` at `0x180027039`
- `KERNEL32!GetLastError` at `0x180027058`
- `KERNEL32!GetLastError` at `0x180027146`
- `KERNEL32!GetLastError` at `0x1800271ed`
- `KERNEL32!GetLastError` at `0x1800275b8`
- `KERNEL32!GetLastError` at `0x180027b24`
- `KERNEL32!GetLastError` at `0x180027bb1`
- `KERNEL32!GetLastError` at `0x180027e5a`
- `KERNEL32!DuplicateHandle` at `0x180027ba7`
- `KERNEL32!DuplicateHandle` at `0x180027ba7`
- `KERNEL32!GetCurrentThreadId` at `0x180027d89`
- `KERNEL32!GetCurrentThreadId` at `0x180027e0f`
- `KERNEL32!GetCurrentThreadId` at `0x180027d89`
- `KERNEL32!GetCurrentThreadId` at `0x180027e0f`
- `KERNEL32!LeaveCriticalSection` at `0x180027818`
- `KERNEL32!LeaveCriticalSection` at `0x180027964`
- `KERNEL32!LeaveCriticalSection` at `0x180027a68`
- `KERNEL32!LeaveCriticalSection` at `0x180027d66`
- `KERNEL32!LeaveCriticalSection` at `0x180027e35`
- `KERNEL32!LeaveCriticalSection` at `0x180027818`
- `KERNEL32!LeaveCriticalSection` at `0x180027964`
- `KERNEL32!LeaveCriticalSection` at `0x180027a68`
- `KERNEL32!LeaveCriticalSection` at `0x180027d66`
- `KERNEL32!LeaveCriticalSection` at `0x180027e35`
- `KERNEL32!lstrlenW` at `0x180027357`
- `KERNEL32!lstrlenW` at `0x1800273a6`
- `KERNEL32!lstrlenW` at `0x180027401`
- `KERNEL32!lstrlenW` at `0x1800275fd`
- `KERNEL32!lstrlenW` at `0x180027357`
- `KERNEL32!lstrlenW` at `0x1800273a6`
- `KERNEL32!lstrlenW` at `0x180027401`
- `KERNEL32!lstrlenW` at `0x1800275fd`
- `KERNEL32!EnterCriticalSection` at `0x180027690`
- `KERNEL32!EnterCriticalSection` at `0x180027c2c`
- `KERNEL32!EnterCriticalSection` at `0x180027d79`
- `KERNEL32!EnterCriticalSection` at `0x180027690`
- `KERNEL32!EnterCriticalSection` at `0x180027c2c`
- `KERNEL32!EnterCriticalSection` at `0x180027d79`
- `ADVAPI32!LookupAccountSidW` at `0x18002713c`
- `ADVAPI32!LookupAccountSidW` at `0x18002713c`
- `ADVAPI32!OpenThreadToken` at `0x180026fa8`
- `ADVAPI32!OpenThreadToken` at `0x180026fa8`
- `ADVAPI32!CheckTokenMembership` at `0x1800271e3`
- `ADVAPI32!CheckTokenMembership` at `0x1800271e3`
- `ADVAPI32!FreeSid` at `0x1800272b6`
- `ADVAPI32!FreeSid` at `0x1800272b6`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800271b4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800271b4`
- `ADVAPI32!GetTokenInformation` at `0x18002702b`
- `ADVAPI32!GetTokenInformation` at `0x18002702b`
- `DSPARSE!DsMakeSpnW` at `0x180027880`
- `DSPARSE!DsMakeSpnW` at `0x1800278d8`
- `DSPARSE!DsMakeSpnW` at `0x180027880`
- `DSPARSE!DsMakeSpnW` at `0x1800278d8`

## string_xrefs

- `0x180026f79`: `ClientAttach: RpcImpersonateClient failed, err=%d`
- `0x180027be6`: `ClientAttach: RpcImpersonateClient failed, err=%d`
- `0x180026fbb`: `ClientAttach: OpenThreadToken failed, err=%u`
- `0x180027042`: `ClientAttach: GetTokenInformation failed, err=%u`
- `0x18002714c`: `ClientAttach: LookupAccountSidW failed, err=%u`
- `0x180027168`: `ClientAttach: LookupAccountSidW: User name %ls Domain name %ls`
- `0x1800271f6`: `ClientAttach: CheckTokenMembership failed, err=%u`
- `0x180027e60`: `ClientAttach: AllocateAndInitializeSid failed, err=%u`
- `0x1800275b1`: `ClientAttach: CreateFile(%ws) failed, err=%u`
- `0x18002771f`: `ClientAttach: RpcStringBindingComposeW failed, err=%d`
- `0x180027b01`: `RpcImpersonateClient failed, err=%d`
- `0x180027b30`: `OpenProcess(pid=x%x) failed, err=%u`
- `0x180027d30`: `RegOpenKey('\HandoffPri') failed, err=%ld`
- `0x180027d51`: `RegOpenCurrentUser failed, err=%ld`

## pseudocode

```c
__int64 __fastcall ClientAttach(_QWORD *a1, DWORD a2, HANDLE *a3, const WCHAR *a4, wchar_t *Str)
{
  void *v7; // rdi
  const char *v8; // rdx
  wchar_t *v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rcx
  _DWORD *v12; // r13
  int v13; // eax
  LPVOID v14; // rax
  __int64 v15; // rcx
  RPC_STATUS v16; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  PSID *v19; // r12
  DWORD v20; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  unsigned int v24; // eax
  wchar_t *v25; // rax
  int v26; // eax
  size_t v27; // r12
  wchar_t *v28; // rax
  const wchar_t *v29; // r12
  unsigned int v30; // eax
  wchar_t *v31; // rax
  __int64 v32; // rax
  const WCHAR *v33; // rcx
  HANDLE FileW; // rax
  void *v35; // rcx
  const char *v36; // r15
  DWORD v37; // eax
  int v38; // eax
  size_t v39; // r12
  unsigned __int16 *v40; // r15
  wchar_t *v41; // rcx
  const wchar_t *v42; // rax
  wchar_t *v43; // rax
  unsigned __int16 *v44; // r12
  wchar_t *v45; // rax
  __int64 v46; // rax
  RPC_STATUS v47; // eax
  RPC_STATUS v48; // eax
  RPC_STATUS v49; // r12d
  const WCHAR *v50; // r12
  RPC_STATUS v51; // r12d
  HANDLE v52; // rax
  DWORD v53; // eax
  HANDLE EventW; // rax
  DWORD v55; // eax
  WCHAR *v56; // rcx
  LSTATUS v57; // eax
  LSTATUS v58; // eax
  size_t v59; // rdx
  __int64 v60; // r10
  _QWORD *i; // rdi
  void (__fastcall *v62)(_QWORD); // rax
  size_t v63; // rdx
  DWORD v64; // eax
  __int64 v65; // rcx
  BOOL IsMember; // [rsp+60h] [rbp-5F8h] BYREF
  DWORD TokenInformationLength; // [rsp+64h] [rbp-5F4h] BYREF
  RPC_WSTR ProtSeq; // [rsp+68h] [rbp-5F0h] BYREF
  size_t cbDest; // [rsp+70h] [rbp-5E8h] BYREF
  LPHANDLE lpTargetHandle; // [rsp+78h] [rbp-5E0h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+80h] [rbp-5D8h]
  HANDLE TokenHandle; // [rsp+88h] [rbp-5D0h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp-5C8h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp-5C0h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp-5B8h]
  void *v76; // [rsp+A8h] [rbp-5B0h]
  RPC_STATUS v77; // [rsp+B0h] [rbp-5A8h]
  unsigned int AuthnLevel; // [rsp+B4h] [rbp-5A4h]
  int v79; // [rsp+B8h] [rbp-5A0h]
  DWORD MessageCount[2]; // [rsp+C0h] [rbp-598h] BYREF
  DWORD NextSize[2]; // [rsp+C8h] [rbp-590h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+D0h] [rbp-588h] BYREF
  DWORD cchReferencedDomainName; // [rsp+D4h] [rbp-584h] BYREF
  DWORD cchName; // [rsp+D8h] [rbp-580h] BYREF
  PSID SidToCheck[2]; // [rsp+E0h] [rbp-578h] BYREF
  __int64 v86; // [rsp+F0h] [rbp-568h] BYREF
  int v87; // [rsp+F8h] [rbp-560h]
  _QWORD *v88; // [rsp+100h] [rbp-558h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+108h] [rbp-550h] BYREF
  __int64 RpcCallAttributes; // [rsp+110h] [rbp-548h] BYREF
  _BYTE v91[32]; // [rsp+118h] [rbp-540h] BYREF
  int v92; // [rsp+138h] [rbp-520h]
  WCHAR ReferencedDomainName[192]; // [rsp+190h] [rbp-4C8h] BYREF
  WCHAR Name[192]; // [rsp+310h] [rbp-348h] BYREF
  WCHAR Buffer[192]; // [rsp+490h] [rbp-1C8h] BYREF

  lpFileName = a4;
  lpTargetHandle = a3;
  v88 = a1;
  pszSrc = Str;
  ReturnLength = 0;
  TokenInformationLength = 0;
  cchName = 192;
  cchReferencedDomainName = 192;
  TokenHandle = 0;
  SidToCheck[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  peUse = 0;
  memset_0(&RpcCallAttributes, 0, 0x78u);
  if ( !(unsigned int)ValidClientAttachParams(a2, a4, Str) )
  {
    LODWORD(v7) = -2147483598;
    return (unsigned int)v7;
  }
  TRACELogPrint(524290, "ClientAttach: enter, pid=x%x, user='%ls', machine='%ls'", a2, a4, Str);
  if ( a2 == -1 && (dword_180051900 & 2) == 0 )
  {
    v8 = "ClientAttach: remotesp attach request received, but this is not a telephony svr!";
LABEL_6:
    LODWORD(v7) = -2147483576;
    TRACELogPrint(65538, v8);
    goto LABEL_30;
  }
  if ( a2 == -3 && !gbNTServer )
  {
    v8 = "ClientAttach: tapimgmt attach request received, but this is not a svr sku!";
    goto LABEL_6;
  }
  ProtSeq = 0;
  v7 = 0;
  v9 = wcschr(Str, 0x22u);
  if ( v9 )
  {
    *v9 = 0;
    ProtSeq = v9 + 1;
  }
  v10 = HeapAlloc(ghTapisrvHeap, 8u, 0x178u);
  v12 = v10;
  if ( !v10 )
    goto LABEL_30;
  v13 = NewObject(v11, v10, 0);
  v12[62] = v13;
  if ( !v13 )
  {
    ServerFree(v12);
    goto LABEL_30;
  }
  SidToCheck[1] = v12;
  v14 = HeapAlloc(ghTapisrvHeap, 8u, 0x400u);
  *((_QWORD *)v12 + 18) = v14;
  if ( !v14 )
  {
LABEL_29:
    DereferenceObject(v15, (unsigned int)v12[62], 1);
LABEL_30:
    if ( !(_DWORD)v7 )
      LODWORD(v7) = -2147483580;
    return (unsigned int)v7;
  }
  *((_QWORD *)v12 + 17) = 1024;
  *((_QWORD *)v12 + 20) = v14;
  *((_QWORD *)v12 + 19) = v14;
  *((_QWORD *)v12 + 8) = 0;
  if ( (dword_180051900 & 4) != 0 && ((a2 + 3) & 0xFFFFFFFD) == 0 )
  {
    TRACELogPrint(65538, "A client tried to attach, but TAPISRV is PAUSED");
LABEL_148:
    ServerFree(*((LPVOID *)v12 + 18));
    DereferenceObject(v65, (unsigned int)v12[62], 1);
    return 2147483720LL;
  }
  v16 = RpcImpersonateClient(0);
  if ( v16 )
  {
    TRACELogPrint(65538, "ClientAttach: RpcImpersonateClient failed, err=%d", v16);
    goto LABEL_148;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    TRACELogPrint(65538, "ClientAttach: OpenThreadToken failed, err=%u", LastError);
LABEL_147:
    RpcRevertToSelf();
    goto LABEL_148;
  }
  cbDest = 2048;
  TokenInformationLength = 2048;
  ReturnLength = 0;
  v19 = (PSID *)HeapAlloc(ghTapisrvHeap, 8u, 0x800u);
  if ( !v19 )
  {
LABEL_27:
    CloseHandle(TokenHandle);
    RpcRevertToSelf();
LABEL_28:
    ServerFree(*((LPVOID *)v12 + 18));
    goto LABEL_29;
  }
  while ( !GetTokenInformation(TokenHandle, TokenUser, v19, TokenInformationLength, &ReturnLength) )
  {
    v20 = GetLastError();
    TRACELogPrint(65538, "ClientAttach: GetTokenInformation failed, err=%u", v20);
    ServerFree(v19);
    if ( GetLastError() != 122 )
      goto LABEL_146;
    TokenInformationLength *= 2;
    cbDest = TokenInformationLength;
    ReturnLength = 0;
    v19 = (PSID *)HeapAlloc(ghTapisrvHeap, 8u, TokenInformationLength);
    if ( !v19 )
      goto LABEL_27;
  }
  if ( !LookupAccountSidW(0, *v19, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v22 = GetLastError();
    TRACELogPrint(65538, "ClientAttach: LookupAccountSidW failed, err=%u", v22);
    goto LABEL_145;
  }
  TRACELogPrint(262146, "ClientAttach: LookupAccountSidW: User name %ls Domain name %ls", Name, ReferencedDomainName);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, SidToCheck) )
  {
    v64 = GetLastError();
    TRACELogPrint(65538, "ClientAttach: AllocateAndInitializeSid failed, err=%u", v64);
LABEL_145:
    ServerFree(v19);
LABEL_146:
    CloseHandle(TokenHandle);
    goto LABEL_147;
  }
  IsMember = 0;
  v12[54] &= 0xFFFFFFF6;
  if ( !CheckTokenMembership(TokenHandle, SidToCheck[0], &IsMember) )
  {
    v23 = GetLastError();
    TRACELogPrint(65538, "ClientAttach: CheckTokenMembership failed, err=%u", v23);
  }
  if ( (dword_180051900 & 2) != 0 )
  {
    if ( !IsMember )
      goto LABEL_45;
    if ( a2 == -1 )
    {
      TokenInformationLength = 192;
      if ( GetComputerNameW(Buffer, &TokenInformationLength) )
      {
        if ( !(unsigned int)_o__wcsicmp(Buffer, ReferencedDomainName) )
        {
          IsMember = 0;
          StringCbCopyW(ReferencedDomainName, 0x180u, pszSrc);
        }
      }
    }
  }
  if ( IsMember )
  {
LABEL_46:
    v12[54] |= 8u;
    goto LABEL_47;
  }
LABEL_45:
  if ( !(unsigned int)IsLocalSystemOnly(TokenHandle) )
    goto LABEL_46;
LABEL_47:
  if ( IsMember || !(unsigned int)IsLocalSystem(TokenHandle) )
    v12[54] |= 1u;
  FreeSid(SidToCheck[0]);
  if ( gbNTServer )
  {
    if ( (v12[54] & 8) == 0 )
    {
      StringCbCopyW((STRSAFE_LPWSTR)v19, cbDest, ReferencedDomainName);
      StringCbCatW((STRSAFE_LPWSTR)v19, cbDest, L"\\");
      StringCbCatW((STRSAFE_LPWSTR)v19, cbDest, Name);
      if ( GetPrivateProfileIntW(gszTapiAdministrators, (LPCWSTR)v19, 0, gszFileName) == 1 )
        v12[54] |= 9u;
    }
  }
  ServerFree(v19);
  CloseHandle(TokenHandle);
  RpcRevertToSelf();
  v24 = 2 * lstrlenW(Name) + 2;
  v12[4] = v24;
  v25 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, v24);
  *((_QWORD *)v12 + 3) = v25;
  if ( !v25 )
    goto LABEL_28;
  StringCbCopyW(v25, (unsigned int)v12[4], Name);
  v26 = lstrlenW(ReferencedDomainName) + 1;
  v27 = 2LL * v26;
  v28 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v26));
  *((_QWORD *)v12 + 6) = v28;
  if ( !v28 )
  {
LABEL_125:
    ServerFree(*((LPVOID *)v12 + 3));
    goto LABEL_28;
  }
  StringCbCopyW(v28, v27, ReferencedDomainName);
  v29 = pszSrc;
  if ( ((a2 + 3) & 0xFFFFFFFD) == 0 )
  {
    v30 = 2 * lstrlenW(pszSrc) + 2;
    v12[8] = v30;
    v31 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, v30);
    *((_QWORD *)v12 + 5) = v31;
    if ( !v31 )
    {
LABEL_124:
      ServerFree(*((LPVOID *)v12 + 6));
      goto LABEL_125;
    }
    StringCbCopyW(v31, (unsigned int)v12[8], v29);
  }
  memset_0(v91, 0, 0x70u);
  RpcCallAttributes = 3;
  if ( RpcServerInqCallAttributesW(0, &RpcCallAttributes) )
  {
    TRACELogPrint(65538, "ClientAttach: Failed to retrieve the RPC call attributes, error 0x%x");
LABEL_121:
    LODWORD(v7) = -2147483576;
LABEL_122:
    v56 = (WCHAR *)*((_QWORD *)v12 + 5);
    if ( v56 != lpString )
      ServerFree(v56);
    goto LABEL_124;
  }
  TRACELogPrint(262146, "ClientAttach(%S): Auth level = 0x%x", *((const wchar_t **)v12 + 3), v92);
  if ( a2 == -1 )
  {
    AuthnLevel = 6;
    if ( v92 != 6 )
    {
      if ( gbHighSecurity )
      {
LABEL_64:
        TRACELogPrint(65538, "ClientAttach: unsecure call, AuthLevel=0x%x");
        goto LABEL_121;
      }
      AuthnLevel = 0;
    }
    *(_DWORD *)lpTargetHandle = -1513920091;
    v32 = -1;
    v33 = lpFileName;
    do
      ++v32;
    while ( lpFileName[v32] );
    if ( v32 )
    {
      *((_QWORD *)v12 + 1) = -2;
      LODWORD(cbDest) = 0;
      NextSize[0] = 0;
      MessageCount[0] = 0;
      IsMember = 0;
      FileW = CreateFileW(v33, 0x40000000u, 1u, 0, 3u, 0x80u, 0);
      *((_QWORD *)v12 + 16) = FileW;
      if ( FileW != (HANDLE)-1LL && GetMailslotInfo(FileW, (LPDWORD)&cbDest, NextSize, MessageCount, (LPDWORD)&IsMember) )
        goto LABEL_136;
      v35 = (void *)*((_QWORD *)v12 + 16);
      if ( v35 == (void *)-1LL )
      {
        v36 = "ClientAttach: CreateFile(%ws) failed, err=%u";
      }
      else
      {
        CloseHandle(v35);
        *((_QWORD *)v12 + 16) = -1;
        v36 = "ClientAttach: GetMailslotInfo(%ws) failed, err=%u";
      }
      v37 = GetLastError();
      TRACELogPrint(65538, v36, lpFileName, v37);
      TRACELogPrint(65538, "ClientAttach: trying connection-oriented approach...");
    }
    *((_QWORD *)v12 + 1) = -1;
    v86 = 0;
    cbDest = 0;
    IsMember = 0;
    v38 = lstrlenW(v29);
    v39 = 2LL * v38 + 6;
    v40 = (unsigned __int16 *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * v38 + 6));
    *(_QWORD *)MessageCount = v40;
    if ( !v40 )
      goto LABEL_122;
    *(_QWORD *)NextSize = pszSrc;
    v76 = 0;
    if ( (unsigned int)_o__wcsicmp(L"ncacn_np", ProtSeq) )
    {
      v41 = v40;
    }
    else
    {
      *(_DWORD *)v40 = 6029404;
      v41 = v40 + 2;
      v39 -= 4LL;
    }
    StringCbCopyW(v41, v39, pszSrc);
    EnterCriticalSection(&stru_180051A00);
    v42 = ProtSeq;
    while ( 1 )
    {
      v43 = wcschr(v42, 0x22u);
      *v43 = 0;
      v44 = v43 + 1;
      lpFileName = v43 + 1;
      v45 = wcschr(v43 + 1, 0x22u);
      lpTargetHandle = (LPHANDLE)v45;
      if ( v45 )
      {
        *v45 = 0;
      }
      else
      {
        v46 = -1;
        do
          ++v46;
        while ( v44[v46] );
        lpTargetHandle = (LPHANDLE)&v44[v46 - 1];
      }
      v47 = RpcStringBindingComposeW(0, ProtSeq, v40, v44, 0, (RPC_WSTR *)&cbDest);
      v77 = v47;
      if ( v47 )
        TRACELogPrint(65538, "ClientAttach: RpcStringBindingComposeW failed, err=%d", v47);
      v48 = RpcBindingFromStringBindingW((RPC_WSTR)cbDest, &hRemoteSP);
      v49 = v48;
      v77 = v48;
      if ( v48 )
      {
        TRACELogPrint(65538, "ClientAttach: RpcBindingFromStringBinding failed, err=%d", v48);
        TRACELogPrint(262146, "\t szMachine=%ws, protseq=%ws endpoint=%ws", pszSrc, ProtSeq, lpFileName);
      }
      if ( v49 )
      {
        RpcStringFreeW((RPC_WSTR *)&cbDest);
        v42 = (const wchar_t *)lpTargetHandle + 1;
        ProtSeq = (RPC_WSTR)lpTargetHandle + 1;
      }
      else
      {
        v42 = ProtSeq;
      }
      if ( !v49 )
        break;
      if ( !*v42 )
      {
        TRACELogPrint(65538, "ClientAttach: error, can't find a usable protseq");
        LeaveCriticalSection(&stru_180051A00);
        ServerFree(v40);
        goto LABEL_121;
      }
    }
    v50 = pszSrc;
    TRACELogPrint(524290, "ClientAttach: szMachine=%ws trying protseq=%ws endpoint=%ws", pszSrc, v42, lpFileName);
    IsMember = 0;
    if ( DsMakeSpnW(L"tapinego", v50, 0, 0, 0, (DWORD *)&IsMember, 0) == 111 )
    {
      v7 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(2 * IsMember + 2));
      v76 = v7;
      if ( DsMakeSpnW(L"tapinego", v50, 0, 0, 0, (DWORD *)&IsMember, (LPWSTR)v7) )
      {
        TRACELogPrint(65538, "ClientAttach: error,can't make SPN");
        if ( v7 )
        {
          ServerFree(v7);
          v7 = 0;
          v76 = 0;
        }
      }
    }
    v51 = RpcBindingSetAuthInfoW(hRemoteSP, (RPC_WSTR)v7, AuthnLevel, 9u, 0, 0);
    if ( v7 )
    {
      ServerFree(v7);
      v76 = 0;
    }
    if ( v51 )
    {
      TRACELogPrint(65538, "ClientAttach: error in RpcBindingSetAuthInfo");
      LeaveCriticalSection(&stru_180051A00);
      ServerFree(v40);
      LODWORD(v7) = -2147483576;
      v87 = -2147483576;
      goto LABEL_122;
    }
    lpFileName = 0;
    lpFileName = (LPCWSTR)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, &v86).Pointer;
    v79 = 0;
    RpcBindingFree(&hRemoteSP);
    RpcStringFreeW((RPC_WSTR *)&cbDest);
    LeaveCriticalSection(&stru_180051A00);
    ServerFree(v40);
    *((_QWORD *)v12 + 7) = v86;
  }
  else if ( a2 == -3 )
  {
    if ( gbHighSecurity && v92 != 6 )
      goto LABEL_64;
    if ( (v12[54] & 1) == 0 )
    {
      LODWORD(v7) = -19;
      goto LABEL_122;
    }
    *((_QWORD *)v12 + 1) = -3;
    *(_DWORD *)lpTargetHandle = 1684300900;
  }
  else
  {
    if ( RpcImpersonateClient(0) )
    {
      TRACELogPrint(65538, "RpcImpersonateClient failed, err=%d");
      goto LABEL_121;
    }
    v52 = OpenProcess(0x40u, 0, a2);
    *((_QWORD *)v12 + 1) = v52;
    if ( !v52 )
    {
      v53 = GetLastError();
      TRACELogPrint(65538, "OpenProcess(pid=x%x) failed, err=%u", a2, v53);
      RpcRevertToSelf();
      goto LABEL_122;
    }
    v12[8] = dword_180051970;
    *((_QWORD *)v12 + 5) = lpString;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v12 + 16) = EventW;
    if ( !EventW )
    {
      RpcRevertToSelf();
      goto LABEL_121;
    }
    if ( !DuplicateHandle(hSourceProcessHandle, EventW, *((HANDLE *)v12 + 1), lpTargetHandle, 0, 0, 2u) )
    {
      v55 = GetLastError();
      TRACELogPrint(65538, "ClientAttach: DupHandle failed, err=%u", v55);
    }
    RpcRevertToSelf();
    if ( !gbPriorityListsInitialized )
    {
      if ( RpcImpersonateClient(0) )
      {
        TRACELogPrint(65538, "ClientAttach: RpcImpersonateClient failed, err=%d");
        goto LABEL_121;
      }
      EnterCriticalSection(&gPriorityListCritSec);
      if ( !gbPriorityListsInitialized )
      {
        ProtSeq = 0;
        phkResult = 0;
        gbPriorityListsInitialized = 1;
        v57 = RegOpenCurrentUser(0xF003Fu, &phkResult);
        if ( v57 )
        {
          TRACELogPrint(65538, "RegOpenCurrentUser failed, err=%ld", v57);
        }
        else
        {
          v58 = RegOpenKeyExW(
                  phkResult,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony\\HandoffPriorities",
                  0,
                  0x20019u,
                  (PHKEY)&ProtSeq);
          if ( v58 )
          {
            TRACELogPrint(65538, "RegOpenKey('\\HandoffPri') failed, err=%ld", v58);
          }
          else
          {
            lpTargetHandle = 0;
            LODWORD(cbDest) = 0;
            if ( !RegCreateKeyExW(
                    (HKEY)ProtSeq,
                    L"MediaModes",
                    0,
                    (LPWSTR)&Format,
                    0,
                    0xF003Fu,
                    0,
                    (PHKEY)&lpTargetHandle,
                    (LPDWORD)&cbDest) )
            {
              GetMediaModesPriorityLists((HKEY)lpTargetHandle);
              RegCloseKey((HKEY)lpTargetHandle);
            }
            GetPriorityList((HKEY)ProtSeq, L"RequestMediaCall");
            RegCloseKey((HKEY)ProtSeq);
          }
          RegCloseKey(phkResult);
        }
      }
      LeaveCriticalSection(&gPriorityListCritSec);
      RpcRevertToSelf();
    }
  }
LABEL_136:
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 5506;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v59, "server\\server.c");
  v60 = qword_180051908;
  *((_QWORD *)v12 + 26) = qword_180051908;
  if ( qword_180051908 )
    *(_QWORD *)(v60 + 200) = v12;
  qword_180051908 = (__int64)v12;
  gfWeHadAtLeastOneClient = 1;
  *v12 = 1414417475;
  for ( i = qword_180051910; i; i = (_QWORD *)i[6] )
  {
    v62 = (void (__fastcall *)(_QWORD))i[128];
    if ( v62 )
      v62(*((unsigned int *)i + 8));
  }
  dword_1800519F8 = 5539;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v63, "server\\server.c");
  LeaveCriticalSection(&CriticalSection);
  *v88 = (unsigned int)v12[62];
  ++dword_1800518BC;
  return 0;
}

```

## disassembly

```asm
0x180026d60  push    rbx
0x180026d62  push    rsi
0x180026d63  push    rdi
0x180026d64  push    r12
0x180026d66  push    r13
0x180026d68  push    r14
0x180026d6a  push    r15
0x180026d6c  sub     rsp, 620h
0x180026d73  mov     rax, cs:__security_cookie
0x180026d7a  xor     rax, rsp
0x180026d7d  mov     [rsp+658h+var_48], rax
0x180026d85  mov     rdi, r9
0x180026d88  mov     [rsp+658h+lpFileName], r9
0x180026d90  mov     [rsp+658h+lpTargetHandle], r8
0x180026d95  mov     r15d, edx
0x180026d98  mov     [rsp+658h+var_558], rcx
0x180026da0  mov     rsi, [rsp+658h+Str]
0x180026da8  mov     [rsp+658h+pszSrc], rsi
0x180026db0  xor     ebx, ebx
0x180026db2  mov     [rsp+658h+var_5C8], ebx
0x180026db9  mov     [rsp+658h+TokenInformationLength], ebx
0x180026dbd  mov     eax, 0C0h
0x180026dc2  mov     [rsp+658h+cchName], eax
0x180026dc9  mov     [rsp+658h+var_584], eax
0x180026dd0  mov     [rsp+658h+TokenHandle], rbx
0x180026dd8  mov     [rsp+658h+SidToCheck], rbx
0x180026de0  mov     dword ptr [rsp+658h+pIdentifierAuthority.Value], ebx
0x180026de7  mov     word ptr [rsp+658h+pIdentifierAuthority.Value+4], 500h
0x180026df1  mov     [rsp+658h+var_588], ebx
0x180026df8  xor     edx, edx; Val
0x180026dfa  lea     r8d, [rbx+78h]; Size
0x180026dfe  lea     rcx, [rsp+658h+RpcCallAttributes]; void *
0x180026e06  call    memset_0
0x180026e0b  mov     r8, rsi
0x180026e0e  mov     rdx, rdi
0x180026e11  mov     ecx, r15d
0x180026e14  call    ValidClientAttachParams
0x180026e19  test    eax, eax
0x180026e1b  jnz     short loc_180026E27
0x180026e1d  mov     edi, 80000032h
0x180026e22  jmp     loc_1800270DA
0x180026e27  mov     [rsp+658h+ReturnLength], rsi
0x180026e2c  mov     r9, rdi
0x180026e2f  mov     r8d, r15d
0x180026e32  lea     rdx, aClientattachEn; "ClientAttach: enter, pid=x%x, user='%ls"...
0x180026e39  mov     ecx, 80002h
0x180026e3e  call    TRACELogPrint
0x180026e43  cmp     r15d, 0FFFFFFFFh
0x180026e47  jnz     short loc_180026E6E
0x180026e49  mov     eax, cs:dword_180051900
0x180026e4f  test    al, 2
0x180026e51  jnz     short loc_180026E6E
0x180026e53  lea     rdx, aClientattachRe_0; "ClientAttach: remotesp attach request r"...
0x180026e5a  mov     edi, 80000048h
0x180026e5f  mov     ecx, 10002h
0x180026e64  call    TRACELogPrint
0x180026e69  jmp     loc_1800270D0
0x180026e6e  cmp     r15d, 0FFFFFFFDh
0x180026e72  jnz     short loc_180026E85
0x180026e74  cmp     cs:gbNTServer, ebx
0x180026e7a  jnz     short loc_180026E85
0x180026e7c  lea     rdx, aClientattachTa; "ClientAttach: tapimgmt attach request r"...
0x180026e83  jmp     short loc_180026E5A
0x180026e85  mov     [rsp+658h+ProtSeq], rbx
0x180026e8a  mov     edi, ebx
0x180026e8c  mov     edx, 22h ; '"'; Ch
0x180026e91  mov     rcx, rsi; Str
0x180026e94  call    cs:__imp_wcschr
0x180026e9a  test    rax, rax
0x180026e9d  jz      short loc_180026EAB
0x180026e9f  mov     [rax], bx
0x180026ea2  add     rax, 2
0x180026ea6  mov     [rsp+658h+ProtSeq], rax
0x180026eab  mov     esi, 8
0x180026eb0  mov     r8d, 178h; dwBytes
0x180026eb6  mov     edx, esi; dwFlags
0x180026eb8  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180026ebf  call    cs:__imp_HeapAlloc
0x180026ec5  mov     r13, rax
0x180026ec8  test    rax, rax
0x180026ecb  jz      loc_1800270D0
0x180026ed1  xor     r8d, r8d
0x180026ed4  mov     rdx, rax
0x180026ed7  call    NewObject
0x180026edc  mov     [r13+0F8h], eax
0x180026ee3  test    eax, eax
0x180026ee5  jnz     short loc_180026EF4
0x180026ee7  mov     rcx, r13; lpMem
0x180026eea  call    ServerFree
0x180026eef  jmp     loc_1800270D0
0x180026ef4  mov     r14, r13
0x180026ef7  mov     [rsp+658h+var_570], r13
0x180026eff  mov     r12d, 400h
0x180026f05  mov     r8d, r12d; dwBytes
0x180026f08  mov     edx, esi; dwFlags
0x180026f0a  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180026f11  call    cs:__imp_HeapAlloc
0x180026f17  mov     [r13+90h], rax
0x180026f1e  test    rax, rax
0x180026f21  jz      loc_1800270BE
0x180026f27  mov     [r13+88h], r12
0x180026f2e  mov     [r13+0A0h], rax
0x180026f35  mov     [r13+98h], rax
0x180026f3c  mov     [r13+40h], rbx
0x180026f40  test    byte ptr cs:dword_180051900, 4
0x180026f47  jz      short loc_180026F6A
0x180026f49  lea     eax, [r15+3]
0x180026f4d  test    eax, 0FFFFFFFDh
0x180026f52  jnz     short loc_180026F6A
0x180026f54  lea     rdx, aAClientTriedTo; "A client tried to attach, but TAPISRV i"...
0x180026f5b  mov     ecx, 10002h
0x180026f60  call    TRACELogPrint
0x180026f65  jmp     loc_180027E8D
0x180026f6a  xor     ecx, ecx; BindingHandle
0x180026f6c  call    cs:__imp_RpcImpersonateClient
0x180026f72  test    eax, eax
0x180026f74  jz      short loc_180026F8F
0x180026f76  mov     r8d, eax
0x180026f79  lea     rdx, aClientattachRp; "ClientAttach: RpcImpersonateClient fail"...
0x180026f80  mov     ecx, 10002h
0x180026f85  call    TRACELogPrint
0x180026f8a  jmp     loc_180027E8D
0x180026f8f  call    cs:__imp_GetCurrentThread
0x180026f95  lea     r9, [rsp+658h+TokenHandle]; TokenHandle
0x180026f9d  xor     r8d, r8d; OpenAsSelf
0x180026fa0  mov     edx, 20008h; DesiredAccess
0x180026fa5  mov     rcx, rax; ThreadHandle
0x180026fa8  call    cs:__imp_OpenThreadToken
0x180026fae  test    eax, eax
0x180026fb0  jnz     short loc_180026FD1
0x180026fb2  call    cs:__imp_GetLastError
0x180026fb8  mov     r8d, eax
0x180026fbb  lea     rdx, aClientattachOp; "ClientAttach: OpenThreadToken failed, e"...
0x180026fc2  mov     ecx, 10002h
0x180026fc7  call    TRACELogPrint
0x180026fcc  jmp     loc_180027E87
0x180026fd1  mov     eax, 800h
0x180026fd6  mov     [rsp+658h+cbDest], rax
0x180026fdb  mov     [rsp+658h+TokenInformationLength], eax
0x180026fdf  mov     [rsp+658h+var_5C8], ebx
0x180026fe6  mov     r8d, eax; dwBytes
0x180026fe9  mov     edx, esi; dwFlags
0x180026feb  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180026ff2  call    cs:__imp_HeapAlloc
0x180026ff8  mov     r12, rax
0x180026ffb  test    rax, rax
0x180026ffe  jz      loc_18002709E
0x180027004  mov     esi, 10002h
0x180027009  lea     rax, [rsp+658h+var_5C8]
0x180027011  mov     [rsp+658h+ReturnLength], rax; ReturnLength
0x180027016  mov     r9d, [rsp+658h+TokenInformationLength]; TokenInformationLength
0x18002701b  mov     r8, r12; TokenInformation
0x18002701e  mov     edx, 1; TokenInformationClass
0x180027023  mov     rcx, [rsp+658h+TokenHandle]; TokenHandle
0x18002702b  call    cs:__imp_GetTokenInformation
0x180027031  test    eax, eax
0x180027033  jnz     loc_1800270FF
0x180027039  call    cs:__imp_GetLastError
0x18002703f  mov     r8d, eax
0x180027042  lea     rdx, aClientattachGe; "ClientAttach: GetTokenInformation faile"...
0x180027049  mov     ecx, esi
0x18002704b  call    TRACELogPrint
0x180027050  mov     rcx, r12; lpMem
0x180027053  call    ServerFree
0x180027058  call    cs:__imp_GetLastError
0x18002705e  cmp     eax, 7Ah ; 'z'
0x180027061  jnz     loc_180027E79
0x180027067  mov     eax, [rsp+658h+TokenInformationLength]
0x18002706b  add     eax, eax
0x18002706d  mov     [rsp+658h+TokenInformationLength], eax
0x180027071  mov     [rsp+658h+cbDest], rax
0x180027076  mov     [rsp+658h+var_5C8], ebx
0x18002707d  mov     r8d, eax; dwBytes
0x180027080  mov     edx, 8; dwFlags
0x180027085  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002708c  call    cs:__imp_HeapAlloc
0x180027092  mov     r12, rax
0x180027095  test    rax, rax
0x180027098  jnz     loc_180027009
0x18002709e  mov     rcx, [rsp+658h+TokenHandle]; hObject
0x1800270a6  call    cs:__imp_CloseHandle
0x1800270ac  call    cs:__imp_RpcRevertToSelf
0x1800270b2  mov     rcx, [r14+90h]; lpMem
0x1800270b9  call    ServerFree
0x1800270be  mov     r8d, 1
0x1800270c4  mov     edx, [r14+0F8h]
0x1800270cb  call    DereferenceObject
0x1800270d0  mov     eax, 80000044h
0x1800270d5  test    edi, edi
0x1800270d7  cmovz   edi, eax
0x1800270da  mov     eax, edi
0x1800270dc  mov     rcx, [rsp+658h+var_48]
0x1800270e4  xor     rcx, rsp; StackCookie
0x1800270e7  call    __security_check_cookie
0x1800270ec  add     rsp, 620h
0x1800270f3  pop     r15
0x1800270f5  pop     r14
0x1800270f7  pop     r13
0x1800270f9  pop     r12
0x1800270fb  pop     rdi
0x1800270fc  pop     rsi
0x1800270fd  pop     rbx
0x1800270fe  retn
0x1800270ff  lea     rax, [rsp+658h+var_588]
0x180027107  mov     [rsp+658h+peUse], rax; peUse
0x18002710c  lea     rax, [rsp+658h+var_584]
0x180027114  mov     [rsp+658h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180027119  lea     rax, [rsp+658h+ReferencedDomainName]
0x180027121  mov     [rsp+658h+ReturnLength], rax; ReferencedDomainName
0x180027126  lea     r9, [rsp+658h+cchName]; cchName
0x18002712e  lea     r8, [rsp+658h+Name]; Name
0x180027136  mov     rdx, [r12]; Sid
0x18002713a  xor     ecx, ecx; lpSystemName
0x18002713c  call    cs:__imp_LookupAccountSidW
0x180027142  test    eax, eax
0x180027144  jnz     short loc_180027158
0x180027146  call    cs:__imp_GetLastError
0x18002714c  lea     rdx, aClientattachLo_0; "ClientAttach: LookupAccountSidW failed,"...
0x180027153  jmp     loc_180027E67
0x180027158  lea     r9, [rsp+658h+ReferencedDomainName]
0x180027160  lea     r8, [rsp+658h+Name]
0x180027168  lea     rdx, aClientattachLo; "ClientAttach: LookupAccountSidW: User n"...
0x18002716f  mov     ecx, 40002h
0x180027174  call    TRACELogPrint
0x180027179  lea     rax, [rsp+658h+SidToCheck]
0x180027181  mov     [rsp+658h+pSid], rax; pSid
0x180027186  mov     [rsp+658h+nSubAuthority7], ebx; nSubAuthority7
0x18002718a  mov     [rsp+658h+nSubAuthority6], ebx; nSubAuthority6
0x18002718e  mov     [rsp+658h+nSubAuthority5], ebx; nSubAuthority5
0x180027192  mov     dword ptr [rsp+658h+peUse], ebx; nSubAuthority4
0x180027196  mov     dword ptr [rsp+658h+cchReferencedDomainName], ebx; nSubAuthority3
0x18002719a  mov     dword ptr [rsp+658h+ReturnLength], ebx; nSubAuthority2
0x18002719e  mov     r9d, 220h; nSubAuthority1
0x1800271a4  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800271aa  mov     dl, 2; nSubAuthorityCount
0x1800271ac  lea     rcx, [rsp+658h+pIdentifierAuthority]; pIdentifierAuthority
0x1800271b4  call    cs:__imp_AllocateAndInitializeSid
0x1800271ba  test    eax, eax
0x1800271bc  jz      loc_180027E5A
0x1800271c2  mov     [rsp+658h+IsMember], ebx
0x1800271c6  and     dword ptr [r13+0D8h], 0FFFFFFF6h
0x1800271ce  lea     r8, [rsp+658h+IsMember]; IsMember
0x1800271d3  mov     rdx, [rsp+658h+SidToCheck]; SidToCheck
0x1800271db  mov     rcx, [rsp+658h+TokenHandle]; TokenHandle
0x1800271e3  call    cs:__imp_CheckTokenMembership
0x1800271e9  test    eax, eax
0x1800271eb  jnz     short loc_180027204
0x1800271ed  call    cs:__imp_GetLastError
0x1800271f3  mov     r8d, eax
0x1800271f6  lea     rdx, aClientattachCh; "ClientAttach: CheckTokenMembership fail"...
0x1800271fd  mov     ecx, esi
0x1800271ff  call    TRACELogPrint
0x180027204  test    byte ptr cs:dword_180051900, 2
0x18002720b  jz      short loc_180027270
0x18002720d  cmp     [rsp+658h+IsMember], ebx
0x180027211  jz      short loc_180027276
0x180027213  cmp     r15d, 0FFFFFFFFh
0x180027217  jnz     short loc_180027270
0x180027219  mov     [rsp+658h+TokenInformationLength], 0C0h
0x180027221  lea     rdx, [rsp+658h+TokenInformationLength]; nSize
0x180027226  lea     rcx, [rsp+658h+Buffer]; lpBuffer
0x18002722e  call    cs:__imp_GetComputerNameW
0x180027234  test    eax, eax
0x180027236  jz      short loc_180027270
0x180027238  lea     rdx, [rsp+658h+ReferencedDomainName]
0x180027240  lea     rcx, [rsp+658h+Buffer]
0x180027248  call    cs:__imp__o__wcsicmp
0x18002724e  test    eax, eax
0x180027250  jnz     short loc_180027270
0x180027252  mov     [rsp+658h+IsMember], ebx
0x180027256  mov     r8, [rsp+658h+pszSrc]; pszSrc
0x18002725e  mov     edx, 180h; cbDest
0x180027263  lea     rcx, [rsp+658h+ReferencedDomainName]; pszDest
0x18002726b  call    StringCbCopyW
0x180027270  cmp     [rsp+658h+IsMember], ebx
0x180027274  jnz     short loc_180027287
0x180027276  mov     rcx, [rsp+658h+TokenHandle]
0x18002727e  call    IsLocalSystemOnly
0x180027283  test    eax, eax
0x180027285  jnz     short loc_18002728F
0x180027287  or      dword ptr [r13+0D8h], 8
0x18002728f  cmp     [rsp+658h+IsMember], ebx
0x180027293  jnz     short loc_1800272A6
0x180027295  mov     rcx, [rsp+658h+TokenHandle]
0x18002729d  call    IsLocalSystem
0x1800272a2  test    eax, eax
0x1800272a4  jnz     short loc_1800272AE
0x1800272a6  or      dword ptr [r13+0D8h], 1
0x1800272ae  mov     rcx, [rsp+658h+SidToCheck]; pSid
0x1800272b6  call    cs:__imp_FreeSid
0x1800272bc  cmp     cs:gbNTServer, ebx
0x1800272c2  jz      short loc_180027333
0x1800272c4  test    byte ptr [r13+0D8h], 8
0x1800272cc  jnz     short loc_180027333
0x1800272ce  lea     r8, [rsp+658h+ReferencedDomainName]; pszSrc
0x1800272d6  mov     rdx, [rsp+658h+cbDest]; cbDest
0x1800272db  mov     rcx, r12; pszDest
0x1800272de  call    StringCbCopyW
0x1800272e3  lea     r8, pszSrc; "\\"
0x1800272ea  mov     rdx, [rsp+658h+cbDest]; cbDest
  ... truncated ...
```
