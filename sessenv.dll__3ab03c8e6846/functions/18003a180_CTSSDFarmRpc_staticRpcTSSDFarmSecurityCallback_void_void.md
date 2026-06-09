# CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback(void *,void *)

- ea: `0x18003a180`
- end: `0x18003a452`
- name: `?staticRpcTSSDFarmSecurityCallback@CTSSDFarmRpc@@SAJPEAX0@Z`
- size: `722`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x180038814`
- `0x18003a180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a30e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a3f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a3f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a304`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003a304`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a2f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003a2f0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003a432`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003a432`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003a371`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003a371`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a3a3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a3a3`
- `RPCRT4!RpcStringFreeW` at `0x18003a403`
- `RPCRT4!RpcStringFreeW` at `0x18003a423`
- `RPCRT4!RpcStringFreeW` at `0x18003a403`
- `RPCRT4!RpcStringFreeW` at `0x18003a423`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003a204`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18003a204`
- `RPCRT4!RpcStringBindingParseW` at `0x18003a23c`
- `RPCRT4!RpcStringBindingParseW` at `0x18003a23c`
- `RPCRT4!RpcImpersonateClient` at `0x18003a2cf`
- `RPCRT4!RpcImpersonateClient` at `0x18003a2cf`
- `RPCRT4!RpcRevertToSelf` at `0x18003a31f`
- `RPCRT4!RpcRevertToSelf` at `0x18003a338`
- `RPCRT4!RpcRevertToSelf` at `0x18003a31f`
- `RPCRT4!RpcRevertToSelf` at `0x18003a338`
- `RPCRT4!RpcBindingFree` at `0x18003a413`
- `RPCRT4!RpcBindingFree` at `0x18003a413`
- `RPCRT4!RpcBindingServerFromClient` at `0x18003a1d6`
- `RPCRT4!RpcBindingServerFromClient` at `0x18003a1d6`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18003a293`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x18003a293`

## string_xrefs

- `0x18003a38e`: `AllocateAndInitializeSid failed: 0x%x in %s`
- `0x18003a32c`: `OpenThreadToken failed: 0x%x in %s`
- `0x18003a3cd`: `CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback`
- `0x18003a3c3`: `CheckTokenMembership failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  int v3; // eax
  bool v4; // sf
  const char *v5; // rdx
  bool v6; // sf
  const unsigned __int16 *v7; // rdx
  bool v8; // sf
  bool v9; // sf
  bool v10; // sf
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v13; // ebx
  bool v14; // sf
  bool v15; // sf
  unsigned int v16; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-19h] BYREF
  unsigned int AuthnLevel; // [rsp+64h] [rbp-15h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+68h] [rbp-11h] BYREF
  RPC_WSTR StringBinding; // [rsp+70h] [rbp-9h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-1h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+80h] [rbp+7h] BYREF
  PSID SidToCheck; // [rsp+88h] [rbp+Fh] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+90h] [rbp+17h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+98h] [rbp+1Fh] BYREF

  AuthnLevel = 1;
  TokenHandle = 0;
  IsMember = 0;
  Privs = 0;
  NetworkAddr = 0;
  ServerBinding = 0;
  StringBinding = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  v3 = RpcBindingServerFromClient(Context, &ServerBinding);
  v4 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v4 = v3 < 0;
    }
    if ( v4 )
    {
      v5 = "RpcBindingServerFromClient failed: 0x%x in %s";
LABEL_45:
      _DbgPrintMessage(8, v5, (unsigned int)v3, "CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback");
      goto LABEL_46;
    }
  }
  v3 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
  v6 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v6 = v3 < 0;
    }
    if ( v6 )
    {
      v5 = "RpcBindingToStringBinding failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
  v3 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
  v8 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v8 = v3 < 0;
    }
    if ( v8 )
    {
      v5 = "RpcStringBindingParse failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
  if ( !(unsigned int)CTSSDFarmRpc::CheckRPCClientProtoSeq(Context, v7) )
  {
    _DbgPrintMessage(
      8,
      "CheckRPCClientProtoSeq failed: 0x%x in %s",
      2147944103LL,
      "CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback");
    goto LABEL_46;
  }
  v3 = RpcBindingInqAuthClientW(Context, &Privs, 0, &AuthnLevel, 0, 0);
  v9 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v9 = v3 < 0;
    }
    if ( v9 )
    {
      v5 = "RpcBindingInqAuthClient failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
  if ( AuthnLevel != 6 )
  {
    _DbgPrintMessage(
      8,
      "RpcBindingInqAuthClient dwAuthn != RPC_C_AUTHN_LEVEL_PKT_PRIVACY failed: 0x%x in %s",
      2147944221LL,
      "CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback");
    goto LABEL_46;
  }
  v3 = RpcImpersonateClient(Context);
  v10 = v3 < 0;
  if ( v3 )
  {
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v10 = v3 < 0;
    }
    if ( v10 )
    {
      v5 = "v failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    RpcRevertToSelf();
    if ( v13 < 0 )
    {
      _DbgPrintMessage(
        8,
        "OpenThreadToken failed: 0x%x in %s",
        (unsigned int)v13,
        "CTSSDFarmRpc::staticRpcTSSDFarmSecurityCallback");
      goto LABEL_46;
    }
  }
  RpcRevertToSelf();
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x241u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v3 = GetLastError();
    v14 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v14 = v3 < 0;
    }
    if ( v14 )
    {
      v5 = "AllocateAndInitializeSid failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
  if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
  {
    IsMember = 0;
    v3 = GetLastError();
    v15 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v15 = v3 < 0;
    }
    if ( v15 )
    {
      v5 = "CheckTokenMembership failed: 0x%x in %s";
      goto LABEL_45;
    }
  }
LABEL_46:
  v16 = IsMember == 0 ? 5 : 0;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( NetworkAddr )
    RpcStringFreeW(&NetworkAddr);
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return v16;
}

```

## disassembly

```asm
0x18003a180  push    rbp
0x18003a182  push    rbx
0x18003a183  push    rsi
0x18003a184  push    rdi
0x18003a185  lea     rbp, [rsp-3Fh]
0x18003a18a  sub     rsp, 0B8h
0x18003a191  mov     rax, cs:__security_cookie
0x18003a198  xor     rax, rsp
0x18003a19b  mov     [rbp+57h+var_30], rax
0x18003a19f  xor     edi, edi
0x18003a1a1  mov     [rbp+57h+AuthnLevel], 1
0x18003a1a8  mov     rbx, rdx
0x18003a1ab  mov     [rbp+57h+TokenHandle], rdi
0x18003a1af  mov     rcx, rbx; ClientBinding
0x18003a1b2  mov     [rbp+57h+IsMember], edi
0x18003a1b5  lea     rdx, [rbp+57h+ServerBinding]; ServerBinding
0x18003a1b9  mov     [rbp+57h+Privs], rdi
0x18003a1bd  mov     [rbp+57h+NetworkAddr], rdi
0x18003a1c1  mov     [rbp+57h+ServerBinding], rdi
0x18003a1c5  mov     [rbp+57h+StringBinding], rdi
0x18003a1c9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003a1cc  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003a1d2  mov     [rbp+57h+SidToCheck], rdi
0x18003a1d6  call    cs:__imp_RpcBindingServerFromClient
0x18003a1dc  mov     esi, 80070000h
0x18003a1e1  test    eax, eax
0x18003a1e3  jz      short loc_18003A1FC
0x18003a1e5  jle     short loc_18003A1EE
0x18003a1e7  movzx   eax, ax
0x18003a1ea  or      eax, esi
0x18003a1ec  test    eax, eax
0x18003a1ee  jns     short loc_18003A1FC
0x18003a1f0  lea     rdx, aRpcbindingserv_0; "RpcBindingServerFromClient failed: 0x%x"...
0x18003a1f7  jmp     loc_18003A3CA
0x18003a1fc  mov     rcx, [rbp+57h+ServerBinding]; Binding
0x18003a200  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x18003a204  call    cs:__imp_RpcBindingToStringBindingW
0x18003a20a  test    eax, eax
0x18003a20c  jz      short loc_18003A225
0x18003a20e  jle     short loc_18003A217
0x18003a210  movzx   eax, ax
0x18003a213  or      eax, esi
0x18003a215  test    eax, eax
0x18003a217  jns     short loc_18003A225
0x18003a219  lea     rdx, aRpcbindingtost_0; "RpcBindingToStringBinding failed: 0x%x "...
0x18003a220  jmp     loc_18003A3CA
0x18003a225  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x18003a229  lea     r9, [rbp+57h+NetworkAddr]; NetworkAddr
0x18003a22d  mov     [rsp+0D0h+NetworkOptions], rdi; NetworkOptions
0x18003a232  xor     r8d, r8d; Protseq
0x18003a235  xor     edx, edx; ObjUuid
0x18003a237  mov     [rsp+0D0h+Endpoint], rdi; Endpoint
0x18003a23c  call    cs:__imp_RpcStringBindingParseW
0x18003a242  test    eax, eax
0x18003a244  jz      short loc_18003A25D
0x18003a246  jle     short loc_18003A24F
0x18003a248  movzx   eax, ax
0x18003a24b  or      eax, esi
0x18003a24d  test    eax, eax
0x18003a24f  jns     short loc_18003A25D
0x18003a251  lea     rdx, aRpcstringbindi_1; "RpcStringBindingParse failed: 0x%x in %"...
0x18003a258  jmp     loc_18003A3CA
0x18003a25d  mov     rcx, rbx; void *
0x18003a260  call    ?CheckRPCClientProtoSeq@CTSSDFarmRpc@@SAHPEAXPEBG@Z; CTSSDFarmRpc::CheckRPCClientProtoSeq(void *,ushort const *)
0x18003a265  test    eax, eax
0x18003a267  jnz     short loc_18003A27B
0x18003a269  mov     r8d, 800706A7h
0x18003a26f  lea     rdx, aCheckrpcclient; "CheckRPCClientProtoSeq failed: 0x%x in "...
0x18003a276  jmp     loc_18003A3CD
0x18003a27b  mov     [rsp+0D0h+NetworkOptions], rdi; AuthzSvc
0x18003a280  lea     r9, [rbp+57h+AuthnLevel]; AuthnLevel
0x18003a284  xor     r8d, r8d; ServerPrincName
0x18003a287  mov     [rsp+0D0h+Endpoint], rdi; AuthnSvc
0x18003a28c  lea     rdx, [rbp+57h+Privs]; Privs
0x18003a290  mov     rcx, rbx; ClientBinding
0x18003a293  call    cs:__imp_RpcBindingInqAuthClientW
0x18003a299  test    eax, eax
0x18003a29b  jz      short loc_18003A2B4
0x18003a29d  jle     short loc_18003A2A6
0x18003a29f  movzx   eax, ax
0x18003a2a2  or      eax, esi
0x18003a2a4  test    eax, eax
0x18003a2a6  jns     short loc_18003A2B4
0x18003a2a8  lea     rdx, aRpcbindinginqa_1; "RpcBindingInqAuthClient failed: 0x%x in"...
0x18003a2af  jmp     loc_18003A3CA
0x18003a2b4  cmp     [rbp+57h+AuthnLevel], 6
0x18003a2b8  jz      short loc_18003A2CC
0x18003a2ba  mov     r8d, 8007071Dh
0x18003a2c0  lea     rdx, aRpcbindinginqa_0; "RpcBindingInqAuthClient dwAuthn != RPC_"...
0x18003a2c7  jmp     loc_18003A3CD
0x18003a2cc  mov     rcx, rbx; BindingHandle
0x18003a2cf  call    cs:__imp_RpcImpersonateClient
0x18003a2d5  test    eax, eax
0x18003a2d7  jz      short loc_18003A2F0
0x18003a2d9  jle     short loc_18003A2E2
0x18003a2db  movzx   eax, ax
0x18003a2de  or      eax, esi
0x18003a2e0  test    eax, eax
0x18003a2e2  jns     short loc_18003A2F0
0x18003a2e4  lea     rdx, aVFailed0xXInS; "v failed: 0x%x in %s"
0x18003a2eb  jmp     loc_18003A3CA
0x18003a2f0  call    cs:__imp_GetCurrentThread
0x18003a2f6  xor     r8d, r8d; OpenAsSelf
0x18003a2f9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003a2fd  mov     rcx, rax; ThreadHandle
0x18003a300  lea     edx, [r8+8]; DesiredAccess
0x18003a304  call    cs:__imp_OpenThreadToken
0x18003a30a  test    eax, eax
0x18003a30c  jnz     short loc_18003A338
0x18003a30e  call    cs:__imp_GetLastError
0x18003a314  mov     ebx, eax
0x18003a316  test    eax, eax
0x18003a318  jle     short loc_18003A31F
0x18003a31a  movzx   ebx, ax
0x18003a31d  or      ebx, esi
0x18003a31f  call    cs:__imp_RpcRevertToSelf
0x18003a325  test    ebx, ebx
0x18003a327  jns     short loc_18003A338
0x18003a329  mov     r8d, ebx
0x18003a32c  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x18003a333  jmp     loc_18003A3CD
0x18003a338  call    cs:__imp_RpcRevertToSelf
0x18003a33e  lea     rax, [rbp+57h+SidToCheck]
0x18003a342  mov     r9d, 241h; nSubAuthority1
0x18003a348  mov     [rsp+0D0h+pSid], rax; pSid
0x18003a34d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003a351  mov     [rsp+0D0h+nSubAuthority7], edi; nSubAuthority7
0x18003a355  mov     r8d, 20h ; ' '; nSubAuthority0
0x18003a35b  mov     [rsp+0D0h+nSubAuthority6], edi; nSubAuthority6
0x18003a35f  mov     dl, 2; nSubAuthorityCount
0x18003a361  mov     [rsp+0D0h+nSubAuthority5], edi; nSubAuthority5
0x18003a365  mov     [rsp+0D0h+nSubAuthority4], edi; nSubAuthority4
0x18003a369  mov     dword ptr [rsp+0D0h+NetworkOptions], edi; nSubAuthority3
0x18003a36d  mov     dword ptr [rsp+0D0h+Endpoint], edi; nSubAuthority2
0x18003a371  call    cs:__imp_AllocateAndInitializeSid
0x18003a377  test    eax, eax
0x18003a379  jnz     short loc_18003A397
0x18003a37b  call    cs:__imp_GetLastError
0x18003a381  test    eax, eax
0x18003a383  jle     short loc_18003A38C
0x18003a385  movzx   eax, ax
0x18003a388  or      eax, esi
0x18003a38a  test    eax, eax
0x18003a38c  jns     short loc_18003A397
0x18003a38e  lea     rdx, aAllocateandini; "AllocateAndInitializeSid failed: 0x%x i"...
0x18003a395  jmp     short loc_18003A3CA
0x18003a397  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003a39b  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003a39f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003a3a3  call    cs:__imp_CheckTokenMembership
0x18003a3a9  test    eax, eax
0x18003a3ab  jnz     short loc_18003A3DE
0x18003a3ad  mov     [rbp+57h+IsMember], edi
0x18003a3b0  call    cs:__imp_GetLastError
0x18003a3b6  test    eax, eax
0x18003a3b8  jle     short loc_18003A3C1
0x18003a3ba  movzx   eax, ax
0x18003a3bd  or      eax, esi
0x18003a3bf  test    eax, eax
0x18003a3c1  jns     short loc_18003A3DE
0x18003a3c3  lea     rdx, aChecktokenmemb; "CheckTokenMembership failed: 0x%x in %s"
0x18003a3ca  mov     r8d, eax
0x18003a3cd  lea     r9, aCtssdfarmrpcSt_0; "CTSSDFarmRpc::staticRpcTSSDFarmSecurity"...
0x18003a3d4  mov     ecx, 8; int
0x18003a3d9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003a3de  mov     eax, [rbp+57h+IsMember]
0x18003a3e1  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18003a3e5  neg     eax
0x18003a3e7  sbb     ebx, ebx
0x18003a3e9  not     ebx
0x18003a3eb  and     ebx, 5
0x18003a3ee  test    rcx, rcx
0x18003a3f1  jz      short loc_18003A3F9
0x18003a3f3  call    cs:__imp_CloseHandle
0x18003a3f9  cmp     [rbp+57h+NetworkAddr], rdi
0x18003a3fd  jz      short loc_18003A409
0x18003a3ff  lea     rcx, [rbp+57h+NetworkAddr]; String
0x18003a403  call    cs:__imp_RpcStringFreeW
0x18003a409  cmp     [rbp+57h+ServerBinding], rdi
0x18003a40d  jz      short loc_18003A419
0x18003a40f  lea     rcx, [rbp+57h+ServerBinding]; Binding
0x18003a413  call    cs:__imp_RpcBindingFree
0x18003a419  cmp     [rbp+57h+StringBinding], rdi
0x18003a41d  jz      short loc_18003A429
0x18003a41f  lea     rcx, [rbp+57h+StringBinding]; String
0x18003a423  call    cs:__imp_RpcStringFreeW
0x18003a429  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003a42d  test    rcx, rcx
0x18003a430  jz      short loc_18003A438
0x18003a432  call    cs:__imp_FreeSid
0x18003a438  mov     eax, ebx
0x18003a43a  mov     rcx, [rbp+57h+var_30]
0x18003a43e  xor     rcx, rsp; StackCookie
0x18003a441  call    __security_check_cookie
0x18003a446  add     rsp, 0B8h
0x18003a44d  pop     rdi
0x18003a44e  pop     rsi
0x18003a44f  pop     rbx
0x18003a450  pop     rbp
0x18003a451  retn
```
