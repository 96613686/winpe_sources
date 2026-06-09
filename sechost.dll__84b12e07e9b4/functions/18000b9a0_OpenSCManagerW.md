# OpenSCManagerW

- ea: `0x18000b9a0`
- end: `0x18000bf09`
- name: `OpenSCManagerW`
- size: `1385`
- prototype: `SC_HANDLE __stdcall(LPCWSTR lpMachineName, LPCWSTR lpDatabaseName, DWORD dwDesiredAccess)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000afb0`
- `0x18000b1a0`
- `0x18003a330`

## callees

- `0x18000b9a0`
- `0x180012800`
- `0x180037e78`
- `0x18003ad54`
- `0x18003addc`
- `0x18003af94`
- `0x18003b1c8`
- `0x18004abac`
- `0x18004af60`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bbb7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd37`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bd37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bbac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000bbac`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ba10`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000bd74`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000ba10`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18000bd74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000befe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000befe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000baee`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000baee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000bc28`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000bc28`
- `RPCRT4!RpcStringFreeW` at `0x18000bad0`
- `RPCRT4!RpcStringFreeW` at `0x18000bad0`
- `RPCRT4!RpcBindingFree` at `0x18000bb9c`
- `RPCRT4!RpcBindingFree` at `0x18000bdcc`
- `RPCRT4!RpcBindingFree` at `0x18000be78`
- `RPCRT4!RpcBindingFree` at `0x18000bb9c`
- `RPCRT4!RpcBindingFree` at `0x18000bdcc`
- `RPCRT4!RpcBindingFree` at `0x18000be78`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000bc9f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000bc9f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bbe0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000bbe0`
- `RPCRT4!NdrClientCall2` at `0x18000bb27`
- `RPCRT4!NdrClientCall2` at `0x18000bb27`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bab4`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000bab4`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc8e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fcaa`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fc8e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fcaa`
- `RPCRT4!RpcBindingSetOption` at `0x18000bede`
- `RPCRT4!RpcBindingSetOption` at `0x18000bede`

## pseudocode

```c
SC_HANDLE __stdcall OpenSCManagerW(LPCWSTR lpMachineName, LPCWSTR lpDatabaseName, DWORD dwDesiredAccess)
{
  DWORD v3; // esi
  int v6; // edi
  unsigned __int16 *v7; // r14
  HANDLE EventW; // r12
  unsigned int LastError; // ebx
  CLIENT_CALL_RETURN v10; // rax
  DWORD v12; // esi
  PSID v13; // rsi
  int i; // r12d
  unsigned int v15; // eax
  int v16; // edx
  RPC_WSTR Options; // [rsp+20h] [rbp-F8h]
  RPC_WSTR String; // [rsp+60h] [rbp-B8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-B0h] BYREF
  RPC_BINDING_HANDLE v20; // [rsp+70h] [rbp-A8h] BYREF
  unsigned int Pointer; // [rsp+78h] [rbp-A0h]
  unsigned __int16 *v22; // [rsp+80h] [rbp-98h] BYREF
  PSID pSid; // [rsp+88h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE hBinding; // [rsp+90h] [rbp-88h] BYREF
  LPCWSTR Simple; // [rsp+98h] [rbp-80h]
  LPCWSTR v26; // [rsp+A0h] [rbp-78h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+A8h] [rbp-70h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-60h]
  PSID v29; // [rsp+C8h] [rbp-50h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp-48h] BYREF

  v3 = dwDesiredAccess;
  LODWORD(String) = dwDesiredAccess;
  v26 = lpMachineName;
  Simple = lpDatabaseName;
  LODWORD(v20) = dwDesiredAccess;
  v6 = 0;
  hBinding = 0;
  v7 = 0;
  v22 = 0;
  Binding = 0;
  EventW = OpenEventW(0x100000u, 0, L"Global\\SvcctrlStartEvent_A3752DX");
  if ( EventW )
    goto LABEL_21;
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    SecurityQOS = 0;
    *(_QWORD *)&v28 = 0;
    pSid = 0;
    LastError = ScCreateStartEventSD(&pSid);
    if ( !LastError )
    {
      SecurityQOS.Version = 24;
      LODWORD(v28) = 0;
      v13 = pSid;
      *(_QWORD *)&SecurityQOS.IdentityTracking = pSid;
      EventW = CreateEventW((LPSECURITY_ATTRIBUTES)&SecurityQOS, 1, 0, L"Global\\SvcctrlStartEvent_A3752DX");
      LastError = GetLastError();
      LocalFree(v13);
      if ( !EventW )
      {
        if ( LastError != 183 )
        {
LABEL_23:
          v3 = (unsigned int)String;
          goto LABEL_3;
        }
        EventW = OpenEventW(0x100000u, 0, L"Global\\SvcctrlStartEvent_A3752DX");
        if ( !EventW )
        {
          LastError = GetLastError();
          goto LABEL_23;
        }
      }
LABEL_21:
      v12 = WaitForSingleObject(EventW, 0x2BF20u);
      CloseHandle(EventW);
      LastError = 0;
      if ( v12 == 258 )
        LastError = 1460;
      goto LABEL_23;
    }
  }
LABEL_3:
  if ( !LastError )
  {
    if ( !lpMachineName || (LastError = ScClientCanonicalizeServerName(lpMachineName, &v22), v7 = v22, !LastError) )
    {
      if ( v7 )
      {
        for ( i = 0; ; ++i )
        {
          LODWORD(String) = i;
          if ( i >= 2 )
            break;
          v15 = i ? ScClientBindToServerUsingNamedPipes(v7, &Binding) : ScClientBindToServerUsingTCP(v7, &Binding);
          LastError = v15;
          if ( !v15 )
          {
            *(_DWORD *)pIdentifierAuthority.Value = 0;
            LastError = ROpenSCManager2(Binding, lpDatabaseName, v3, &hBinding);
            Pointer = LastError;
            RpcBindingFree(&Binding);
            Binding = 0;
            if ( !LastError || !*(_DWORD *)pIdentifierAuthority.Value )
              break;
          }
        }
        if ( LastError == 120 )
        {
          LOBYTE(v6) = i == 1;
          LastError = OpenSCManagerLegacy(lpMachineName, lpDatabaseName, v3, v6, &hBinding);
        }
        if ( !LastError )
        {
          RpcBindingSetOption(hBinding, 0xCu, 0);
          if ( i == 1 )
            ScClientMarkServerAsNeedingNamedPipeFallback((void *)lpMachineName, v16);
        }
      }
      else
      {
        String = 0;
        v20 = 0;
        SecurityQOS = 0;
        v28 = 0;
        v29 = 0;
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        pSid = 0;
        Binding = 0;
        LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"ntsvcs", 0, &String);
        if ( !LastError )
        {
          LastError = RpcBindingFromStringBindingW(String, &v20);
          if ( !LastError )
          {
            if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
            {
              SecurityQOS.Capabilities = 1;
              SecurityQOS.IdentityTracking = 1;
              SecurityQOS.Version = 3;
              SecurityQOS.ImpersonationType = 3;
              v29 = pSid;
              RpcBindingSetAuthInfoExW(v20, 0, 6u, 0xAu, 0, 1u, &SecurityQOS);
              Binding = v20;
              v20 = 0;
              LastError = 0;
            }
            else
            {
              LastError = GetLastError();
            }
          }
        }
        if ( String )
          RpcStringFreeW(&String);
        if ( v20 )
          RpcBindingFree(&v20);
        if ( pSid )
          FreeSid(pSid);
        if ( !LastError )
        {
          Simple = 0;
          LODWORD(Options) = v3;
          v10.Pointer = NdrClientCall2(&pStubDescriptor, &byte_180061132, Binding, lpDatabaseName, Options, &hBinding).Pointer;
          LastError = (unsigned int)v10.Pointer;
          Simple = (LPCWSTR)v10.Simple;
          Pointer = (unsigned int)v10.Pointer;
        }
      }
    }
  }
  if ( v7 )
    LocalFree(v7);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( !LastError )
    return (SC_HANDLE)hBinding;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x18000b9a0  push    rbx
0x18000b9a2  push    rsi
0x18000b9a3  push    rdi
0x18000b9a4  push    r12
0x18000b9a6  push    r13
0x18000b9a8  push    r14
0x18000b9aa  push    r15
0x18000b9ac  sub     rsp, 0E0h
0x18000b9b3  mov     rax, cs:__security_cookie
0x18000b9ba  xor     rax, rsp
0x18000b9bd  mov     [rsp+118h+var_40], rax
0x18000b9c5  mov     esi, r8d
0x18000b9c8  mov     dword ptr [rsp+118h+String], r8d
0x18000b9cd  mov     r13, rdx
0x18000b9d0  mov     r15, rcx
0x18000b9d3  mov     [rsp+118h+var_78], rcx
0x18000b9db  mov     [rsp+118h+var_80], rdx
0x18000b9e3  mov     dword ptr [rsp+118h+var_A8], r8d
0x18000b9e8  xor     edi, edi
0x18000b9ea  mov     [rsp+118h+hBinding], rdi
0x18000b9f2  mov     r14d, edi
0x18000b9f5  mov     [rsp+118h+var_98], rdi
0x18000b9fd  mov     [rsp+118h+Binding], rdi
0x18000ba02  lea     r8, Name; "Global\\SvcctrlStartEvent_A3752DX"
0x18000ba09  xor     edx, edx; bInheritHandle
0x18000ba0b  mov     ecx, 100000h; dwDesiredAccess
0x18000ba10  call    cs:__imp_OpenEventW
0x18000ba16  mov     r12, rax
0x18000ba19  test    rax, rax
0x18000ba1c  jnz     loc_18000BBA4
0x18000ba22  call    cs:__imp_GetLastError
0x18000ba28  mov     ebx, eax
0x18000ba2a  cmp     eax, 2
0x18000ba2d  jz      loc_18000BCCA
0x18000ba33  test    ebx, ebx
0x18000ba35  jnz     loc_18000BB53
0x18000ba3b  test    r15, r15
0x18000ba3e  jnz     loc_18000BD93
0x18000ba44  test    r14, r14
0x18000ba47  jnz     loc_18000BDD7
0x18000ba4d  mov     [rsp+118h+String], rdi
0x18000ba52  mov     [rsp+118h+var_A8], rdi
0x18000ba57  xorps   xmm0, xmm0
0x18000ba5a  xor     eax, eax
0x18000ba5c  movups  xmmword ptr [rsp+118h+SecurityQOS.Version], xmm0
0x18000ba64  movups  [rsp+118h+var_60], xmm0
0x18000ba6c  mov     [rsp+118h+var_50], rax
0x18000ba74  mov     dword ptr [rsp+118h+pIdentifierAuthority.Value], eax
0x18000ba7b  mov     word ptr [rsp+118h+pIdentifierAuthority.Value+4], 500h
0x18000ba85  mov     [rsp+118h+pSid], rdi
0x18000ba8d  mov     [rsp+118h+Binding], rdi
0x18000ba92  lea     rax, [rsp+118h+String]
0x18000ba97  mov     [rsp+118h+StringBinding], rax; StringBinding
0x18000ba9c  mov     [rsp+118h+Options], rdi; Options
0x18000baa1  lea     r9, Endpoint; "ntsvcs"
0x18000baa8  xor     r8d, r8d; NetworkAddr
0x18000baab  lea     rdx, Protseq; "ncalrpc"
0x18000bab2  xor     ecx, ecx; ObjUuid
0x18000bab4  call    cs:__imp_RpcStringBindingComposeW
0x18000baba  mov     ebx, eax
0x18000babc  test    eax, eax
0x18000babe  jz      loc_18000BBD6
0x18000bac4  cmp     [rsp+118h+String], rdi
0x18000bac9  jz      short loc_18000BAD6
0x18000bacb  lea     rcx, [rsp+118h+String]; String
0x18000bad0  call    cs:__imp_RpcStringFreeW
0x18000bad6  cmp     [rsp+118h+var_A8], rdi
0x18000badb  jnz     loc_18000BDC7
0x18000bae1  mov     rcx, [rsp+118h+pSid]; pSid
0x18000bae9  test    rcx, rcx
0x18000baec  jz      short loc_18000BAF4
0x18000baee  call    cs:__imp_FreeSid
0x18000baf4  test    ebx, ebx
0x18000baf6  jnz     short loc_18000BB53
0x18000baf8  mov     [rsp+118h+var_80], rdi
0x18000bb00  lea     rax, [rsp+118h+hBinding]
0x18000bb08  mov     [rsp+118h+StringBinding], rax
0x18000bb0d  mov     dword ptr [rsp+118h+Options], esi
0x18000bb11  mov     r9, r13
0x18000bb14  mov     r8, [rsp+118h+Binding]
0x18000bb19  lea     rdx, byte_180061132; pFormat
0x18000bb20  lea     rcx, pStubDescriptor; pStubDescriptor
0x18000bb27  call    cs:__imp_NdrClientCall2
0x18000bb2d  mov     rbx, rax
0x18000bb30  mov     [rsp+118h+var_80], rax
0x18000bb38  mov     [rsp+118h+var_A0], eax
0x18000bb3c  jmp     short loc_18000BB53
0x18000bb3e  mov     ecx, eax; unsigned int
0x18000bb40  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000bb45  mov     ebx, eax
0x18000bb47  mov     [rsp+118h+var_A0], eax
0x18000bb4b  mov     r14, [rsp+118h+var_98]
0x18000bb53  test    r14, r14
0x18000bb56  jnz     loc_18000BEFB
0x18000bb5c  cmp     [rsp+118h+Binding], 0
0x18000bb62  jnz     short loc_18000BB97
0x18000bb64  test    ebx, ebx
0x18000bb66  jnz     loc_18000BCBB
0x18000bb6c  mov     rax, [rsp+118h+hBinding]
0x18000bb74  mov     rcx, [rsp+118h+var_40]
0x18000bb7c  xor     rcx, rsp; StackCookie
0x18000bb7f  call    __security_check_cookie
0x18000bb84  add     rsp, 0E0h
0x18000bb8b  pop     r15
0x18000bb8d  pop     r14
0x18000bb8f  pop     r13
0x18000bb91  pop     r12
0x18000bb93  pop     rdi
0x18000bb94  pop     rsi
0x18000bb95  pop     rbx
0x18000bb96  retn
0x18000bb97  lea     rcx, [rsp+118h+Binding]; Binding
0x18000bb9c  call    cs:__imp_RpcBindingFree
0x18000bba2  jmp     short loc_18000BB64
0x18000bba4  mov     edx, 2BF20h; dwMilliseconds
0x18000bba9  mov     rcx, r12; hHandle
0x18000bbac  call    cs:__imp_WaitForSingleObject
0x18000bbb2  mov     esi, eax
0x18000bbb4  mov     rcx, r12; hObject
0x18000bbb7  call    cs:__imp_CloseHandle
0x18000bbbd  mov     ebx, edi
0x18000bbbf  mov     eax, 5B4h
0x18000bbc4  cmp     esi, 102h
0x18000bbca  cmovz   ebx, eax
0x18000bbcd  mov     esi, dword ptr [rsp+118h+String]
0x18000bbd1  jmp     loc_18000BA33
0x18000bbd6  lea     rdx, [rsp+118h+var_A8]; Binding
0x18000bbdb  mov     rcx, [rsp+118h+String]; StringBinding
0x18000bbe0  call    cs:__imp_RpcBindingFromStringBindingW
0x18000bbe6  mov     ebx, eax
0x18000bbe8  test    eax, eax
0x18000bbea  jnz     loc_18000BAC4
0x18000bbf0  lea     rax, [rsp+118h+pSid]
0x18000bbf8  mov     [rsp+118h+var_C8], rax; pSid
0x18000bbfd  mov     [rsp+118h+nSubAuthority7], edi; nSubAuthority7
0x18000bc01  mov     [rsp+118h+nSubAuthority6], edi; nSubAuthority6
0x18000bc05  mov     [rsp+118h+nSubAuthority5], edi; nSubAuthority5
0x18000bc09  mov     [rsp+118h+nSubAuthority4], edi; nSubAuthority4
0x18000bc0d  mov     dword ptr [rsp+118h+StringBinding], edi; nSubAuthority3
0x18000bc11  mov     dword ptr [rsp+118h+Options], edi; nSubAuthority2
0x18000bc15  xor     r9d, r9d; nSubAuthority1
0x18000bc18  mov     r8d, 12h; nSubAuthority0
0x18000bc1e  mov     dl, 1; nSubAuthorityCount
0x18000bc20  lea     rcx, [rsp+118h+pIdentifierAuthority]; pIdentifierAuthority
0x18000bc28  call    cs:__imp_AllocateAndInitializeSid
0x18000bc2e  test    eax, eax
0x18000bc30  jz      loc_18000BDBA
0x18000bc36  mov     [rsp+118h+SecurityQOS.Capabilities], 1
0x18000bc41  mov     [rsp+118h+SecurityQOS.IdentityTracking], 1
0x18000bc4c  mov     [rsp+118h+SecurityQOS.Version], 3
0x18000bc57  mov     [rsp+118h+SecurityQOS.ImpersonationType], 3
0x18000bc62  mov     rax, [rsp+118h+pSid]
0x18000bc6a  mov     [rsp+118h+var_50], rax
0x18000bc72  lea     rax, [rsp+118h+SecurityQOS]
0x18000bc7a  mov     qword ptr [rsp+118h+nSubAuthority4], rax; SecurityQOS
0x18000bc7f  mov     dword ptr [rsp+118h+StringBinding], 1; AuthzSvc
0x18000bc87  mov     [rsp+118h+Options], rdi; AuthIdentity
0x18000bc8c  xor     edx, edx; ServerPrincName
0x18000bc8e  mov     r9d, 0Ah; AuthnSvc
0x18000bc94  mov     r8d, 6; AuthnLevel
0x18000bc9a  mov     rcx, [rsp+118h+var_A8]; Binding
0x18000bc9f  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000bca5  mov     rax, [rsp+118h+var_A8]
0x18000bcaa  mov     [rsp+118h+Binding], rax
0x18000bcaf  mov     [rsp+118h+var_A8], rdi
0x18000bcb4  mov     ebx, edi
0x18000bcb6  jmp     loc_18000BAC4
0x18000bcbb  mov     ecx, ebx; dwErrCode
0x18000bcbd  call    cs:__imp_SetLastError
0x18000bcc3  xor     eax, eax
0x18000bcc5  jmp     loc_18000BB74
0x18000bcca  xorps   xmm0, xmm0
0x18000bccd  xor     eax, eax
0x18000bccf  movups  xmmword ptr [rsp+118h+SecurityQOS.Version], xmm0
0x18000bcd7  mov     qword ptr [rsp+118h+var_60], rax
0x18000bcdf  mov     [rsp+118h+pSid], rdi
0x18000bce7  lea     rcx, [rsp+118h+pSid]
0x18000bcef  call    ScCreateStartEventSD
0x18000bcf4  mov     ebx, eax
0x18000bcf6  test    eax, eax
0x18000bcf8  jnz     loc_18000BA33
0x18000bcfe  mov     [rsp+118h+SecurityQOS.Version], 18h
0x18000bd09  mov     dword ptr [rsp+118h+var_60], edi
0x18000bd10  mov     rsi, [rsp+118h+pSid]
0x18000bd18  mov     qword ptr [rsp+118h+SecurityQOS.IdentityTracking], rsi
0x18000bd20  lea     r9, Name; "Global\\SvcctrlStartEvent_A3752DX"
0x18000bd27  xor     r8d, r8d; bInitialState
0x18000bd2a  mov     edx, 1; bManualReset
0x18000bd2f  lea     rcx, [rsp+118h+SecurityQOS]; lpEventAttributes
0x18000bd37  call    cs:__imp_CreateEventW
0x18000bd3d  mov     r12, rax
0x18000bd40  call    cs:__imp_GetLastError
0x18000bd46  mov     ebx, eax
0x18000bd48  mov     rcx, rsi; hMem
0x18000bd4b  call    cs:__imp_LocalFree
0x18000bd51  test    r12, r12
0x18000bd54  jnz     loc_18000BBA4
0x18000bd5a  cmp     ebx, 0B7h
0x18000bd60  jnz     loc_18000BBCD
0x18000bd66  lea     r8, Name; "Global\\SvcctrlStartEvent_A3752DX"
0x18000bd6d  xor     edx, edx; bInheritHandle
0x18000bd6f  mov     ecx, 100000h; dwDesiredAccess
0x18000bd74  call    cs:__imp_OpenEventW
0x18000bd7a  mov     r12, rax
0x18000bd7d  test    rax, rax
0x18000bd80  jnz     loc_18000BBA4
0x18000bd86  call    cs:__imp_GetLastError
0x18000bd8c  mov     ebx, eax
0x18000bd8e  jmp     loc_18000BBCD
0x18000bd93  lea     rdx, [rsp+118h+var_98]; unsigned __int16 **
0x18000bd9b  mov     rcx, r15; unsigned __int16 *
0x18000bd9e  call    ?ScClientCanonicalizeServerName@@YAKPEBGPEAPEAG@Z; ScClientCanonicalizeServerName(ushort const *,ushort * *)
0x18000bda3  mov     ebx, eax
0x18000bda5  mov     r14, [rsp+118h+var_98]
0x18000bdad  test    eax, eax
0x18000bdaf  jnz     loc_18000BB53
0x18000bdb5  jmp     loc_18000BA44
0x18000bdba  call    cs:__imp_GetLastError
0x18000bdc0  mov     ebx, eax
0x18000bdc2  jmp     loc_18000BAC4
0x18000bdc7  lea     rcx, [rsp+118h+var_A8]; Binding
0x18000bdcc  call    cs:__imp_RpcBindingFree
0x18000bdd2  jmp     loc_18000BAE1
0x18000bdd7  mov     r12d, edi
0x18000bdda  mov     dword ptr [rsp+118h+String], r12d
0x18000bddf  cmp     r12d, 2
0x18000bde3  jge     loc_18000BE99
0x18000bde9  lea     rdx, [rsp+118h+Binding]; Binding
0x18000bdee  mov     rcx, r14; NetworkAddr
0x18000bdf1  test    r12d, r12d
0x18000bdf4  jnz     short loc_18000BDFD
0x18000bdf6  call    ?ScClientBindToServerUsingTCP@@YAKPEAGPEAPEAX@Z; ScClientBindToServerUsingTCP(ushort *,void * *)
0x18000bdfb  jmp     short loc_18000BE02
0x18000bdfd  call    ?ScClientBindToServerUsingNamedPipes@@YAKPEAGPEAPEAX@Z; ScClientBindToServerUsingNamedPipes(ushort *,void * *)
0x18000be02  mov     ebx, eax
0x18000be04  test    eax, eax
0x18000be06  jnz     loc_18000BE91
0x18000be0c  mov     dword ptr [rsp+118h+pIdentifierAuthority.Value], edi
0x18000be13  lea     r9, [rsp+118h+hBinding]
0x18000be1b  mov     r8d, esi
0x18000be1e  mov     rdx, r13
0x18000be21  mov     rcx, [rsp+118h+Binding]
0x18000be26  call    ROpenSCManager2
0x18000be2b  mov     ebx, eax
0x18000be2d  mov     [rsp+118h+var_A0], eax
0x18000be31  jmp     short loc_18000BE73
0x18000be33  mov     ecx, eax; unsigned int
0x18000be35  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x18000be3a  mov     ebx, eax
0x18000be3c  mov     [rsp+118h+var_A0], eax
0x18000be40  mov     dword ptr [rsp+118h+pIdentifierAuthority.Value], 1
0x18000be4b  xor     edi, edi
0x18000be4d  mov     r14, [rsp+118h+var_98]
0x18000be55  mov     r12d, dword ptr [rsp+118h+String]
0x18000be5a  mov     r15, [rsp+118h+var_78]
0x18000be62  mov     r13, [rsp+118h+var_80]
0x18000be6a  mov     esi, dword ptr [rsp+118h+var_A8]
0x18000be6e  cmp     eax, 78h ; 'x'
0x18000be71  jz      short loc_18000BE99
0x18000be73  lea     rcx, [rsp+118h+Binding]; Binding
0x18000be78  call    cs:__imp_RpcBindingFree
0x18000be7e  mov     [rsp+118h+Binding], rdi
0x18000be83  test    ebx, ebx
0x18000be85  jz      short loc_18000BE99
0x18000be87  cmp     dword ptr [rsp+118h+pIdentifierAuthority.Value], 0
0x18000be8f  jz      short loc_18000BE99
0x18000be91  inc     r12d
0x18000be94  jmp     loc_18000BDDA
0x18000be99  cmp     ebx, 78h ; 'x'
0x18000be9c  jnz     short loc_18000BEC6
0x18000be9e  cmp     r12d, 1
0x18000bea2  setz    dil
0x18000bea6  lea     rax, [rsp+118h+hBinding]
0x18000beae  mov     [rsp+118h+Options], rax; void **
0x18000beb3  mov     r9d, edi; int
0x18000beb6  mov     r8d, esi; unsigned int
0x18000beb9  mov     rdx, r13; unsigned __int16 *
0x18000bebc  mov     rcx, r15; unsigned __int16 *
0x18000bebf  call    ?OpenSCManagerLegacy@@YAKPEBG0KHPEAPEAX@Z; OpenSCManagerLegacy(ushort const *,ushort const *,ulong,int,void * *)
0x18000bec4  mov     ebx, eax
0x18000bec6  test    ebx, ebx
0x18000bec8  jnz     loc_18000BB53
0x18000bece  xor     r8d, r8d; optionValue
0x18000bed1  mov     edx, 0Ch; option
0x18000bed6  mov     rcx, [rsp+118h+hBinding]; hBinding
0x18000bede  call    cs:__imp_RpcBindingSetOption
0x18000bee4  cmp     r12d, 1
0x18000bee8  jnz     loc_18000BB53
0x18000beee  mov     rcx, r15; void *
0x18000bef1  call    ?ScClientMarkServerAsNeedingNamedPipeFallback@@YAXPEAXH@Z; ScClientMarkServerAsNeedingNamedPipeFallback(void *,int)
0x18000bef6  jmp     loc_18000BB53
0x18000befb  mov     rcx, r14; hMem
0x18000befe  call    cs:__imp_LocalFree
0x18000bf04  jmp     loc_18000BB5C
0x18004fc80  push    rbp
0x18004fc82  sub     rsp, 60h
0x18004fc86  mov     rbp, rdx
0x18004fc89  mov     rcx, [rcx]
0x18004fc8c  mov     ecx, [rcx]; ExceptionCode
0x18004fc8e  call    cs:__imp_I_RpcExceptionFilter
  ... truncated ...
```
