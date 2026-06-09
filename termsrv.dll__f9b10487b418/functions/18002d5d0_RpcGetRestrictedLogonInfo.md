# RpcGetRestrictedLogonInfo

- ea: `0x18002d5d0`
- end: `0x18002d8d0`
- name: `RpcGetRestrictedLogonInfo`
- size: `768`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x18000bad0`
- `0x18000f1a0`
- `0x180013150`
- `0x1800148d0`
- `0x18002d5d0`
- `0x180031674`
- `0x1800321f0`
- `0x1800330c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d891`
- `RPCRT4!RpcRevertToSelf` at `0x18002d75a`
- `RPCRT4!RpcRevertToSelf` at `0x18002d75a`
- `RPCRT4!RpcImpersonateClient` at `0x18002d6a7`
- `RPCRT4!RpcImpersonateClient` at `0x18002d6a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d887`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d887`

## string_xrefs

- `0x18002d8a9`: `GetTokenInformation failed: 0x%x`
- `0x18002d6bd`: `RpcImpersonateClient failed: 0x%x`
- `0x18002d85d`: `ptrRemoteTerminal->GetSecurityFilterClientToken failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall RpcGetRestrictedLogonInfo(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  const char *v5; // r8
  unsigned int v6; // ebx
  int v7; // eax
  bool v8; // sf
  int SessionFromRpcClientId; // eax
  const char *v10; // rdx
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  bool v14; // sf
  signed int LastError; // eax
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, __int64 *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  struct ITSSession *v21; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD TokenInformation[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+90h] [rbp-70h]
  _BYTE v24[592]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v25[576]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v21 = 0;
  v20 = 0;
  v17 = 0;
  TokenHandle = 0;
  memset_0(v25, 0, 0x8F8u);
  v23 = 0;
  ReturnLength = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v24, 0, "RpcGetRestrictedLogonInfo");
  if ( !a2 )
  {
    v5 = "pbRestrictedLogonRequested";
LABEL_3:
    _DbgPrintMessage(8, "Missing paramter %s in %s", v5, "RpcGetRestrictedLogonInfo");
    v6 = -2147024809;
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v5 = "pAuthenticationId";
    goto LABEL_3;
  }
  v7 = RpcImpersonateClient(0);
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v8 = v7 < 0;
  }
  if ( v8 )
  {
    _DbgPrintMessage(8, "RpcImpersonateClient failed: 0x%x", (unsigned int)v7);
LABEL_24:
    v6 = -2147024891;
    goto LABEL_25;
  }
  SessionFromRpcClientId = CRpcUtils::GetSessionFromRpcClientId(&v21);
  v6 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v10 = "CRpcUtils::GetSessionFromRpcClientId failed: 0x%x in %s";
LABEL_12:
    _DbgPrintMessage(8, v10, (unsigned int)SessionFromRpcClientId, "RpcGetRestrictedLogonInfo");
    goto LABEL_20;
  }
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v21 + 104LL))(
                             v21,
                             &v20);
  v6 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v10 = "GetTerminal failed: 0x%x in %s";
    goto LABEL_12;
  }
  v11 = (**v20)(v20, qword_1800E2708, &v17);
  v6 = v11;
  if ( v11 == -2147467262 )
  {
    v6 = 0;
LABEL_18:
    v12 = 0;
    *a2 = 0;
LABEL_19:
    *a3 = v12;
    goto LABEL_20;
  }
  if ( v11 < 0 )
  {
    _DbgPrintMessage(4, "QI( IRemoteTerminal ) failed: 0x%x in %s", (unsigned int)v11, "RpcGetRestrictedLogonInfo");
    goto LABEL_20;
  }
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v17 + 232LL))(
                             v17,
                             v25,
                             2296);
  v6 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v10 = "ptrRemoteTerminal->GetClientData failed: 0x%x in %s";
    goto LABEL_12;
  }
  if ( (v25[0] & 0x1000) == 0 )
    goto LABEL_18;
  SessionFromRpcClientId = (*(__int64 (__fastcall **)(__int64, _QWORD, HANDLE *))(*(_QWORD *)v17 + 344LL))(
                             v17,
                             0,
                             &TokenHandle);
  v6 = SessionFromRpcClientId;
  if ( SessionFromRpcClientId < 0 )
  {
    v10 = "ptrRemoteTerminal->GetSecurityFilterClientToken failed: 0x%x in %s";
    goto LABEL_12;
  }
  if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
  {
    v12 = *((_QWORD *)&TokenInformation[0] + 1);
    *a2 = 1;
    goto LABEL_19;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v6);
LABEL_20:
  v13 = RpcRevertToSelf();
  v14 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x80070000;
    v14 = v13 < 0;
  }
  if ( v14 )
  {
    _DbgPrintMessage(8, "RpcRevertToSelf failed: 0x%x", (unsigned int)v13);
    goto LABEL_24;
  }
LABEL_25:
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v24);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v17);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v20);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v21);
  return v6;
}

```

## disassembly

```asm
0x18002d5d0  mov     [rsp-8+arg_0], rbx
0x18002d5d5  mov     [rsp-8+arg_18], rsi
0x18002d5da  push    rbp
0x18002d5db  push    r12
0x18002d5dd  push    r14
0x18002d5df  lea     rbp, [rsp-0B00h]
0x18002d5e7  sub     rsp, 0C00h
0x18002d5ee  mov     rax, cs:__security_cookie
0x18002d5f5  xor     rax, rsp
0x18002d5f8  mov     [rbp+0B10h+var_20], rax
0x18002d5ff  mov     rsi, r8
0x18002d602  mov     [rsp+0C10h+var_BB8], 0
0x18002d60b  mov     r14, rdx
0x18002d60e  mov     [rsp+0C10h+var_BC0], 0
0x18002d617  xor     edx, edx; Val
0x18002d619  mov     [rsp+0C10h+var_BD8], 0
0x18002d622  mov     r8d, 8F8h; Size
0x18002d628  mov     [rsp+0C10h+TokenHandle], 0
0x18002d631  lea     rcx, [rbp+0B10h+var_920]; void *
0x18002d638  call    memset_0
0x18002d63d  xorps   xmm0, xmm0
0x18002d640  lea     r12, aRpcgetrestrict; "RpcGetRestrictedLogonInfo"
0x18002d647  xor     eax, eax
0x18002d649  lea     rcx, [rbp+0B10h+var_B70]; this
0x18002d64d  mov     r8, r12; char *
0x18002d650  mov     [rbp+0B10h+var_B80], rax
0x18002d654  xor     edx, edx; int
0x18002d656  mov     [rsp+0C10h+var_BD0], eax
0x18002d65a  movups  [rsp+0C10h+TokenInformation], xmm0
0x18002d65f  movups  [rsp+0C10h+var_BA0], xmm0
0x18002d664  movups  [rbp+0B10h+var_B90], xmm0
0x18002d668  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002d66d  test    r14, r14
0x18002d670  jnz     short loc_18002D697
0x18002d672  lea     r8, aPbrestrictedlo; "pbRestrictedLogonRequested"
0x18002d679  mov     r9, r12
0x18002d67c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002d683  mov     ecx, 8; int
0x18002d688  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d68d  mov     ebx, 80070057h
0x18002d692  jmp     loc_18002D789
0x18002d697  test    rsi, rsi
0x18002d69a  jnz     short loc_18002D6A5
0x18002d69c  lea     r8, aPauthenticatio; "pAuthenticationId"
0x18002d6a3  jmp     short loc_18002D679
0x18002d6a5  xor     ecx, ecx; BindingHandle
0x18002d6a7  call    cs:__imp_RpcImpersonateClient
0x18002d6ad  test    eax, eax
0x18002d6af  jle     short loc_18002D6BB
0x18002d6b1  movzx   eax, ax
0x18002d6b4  or      eax, 80070000h
0x18002d6b9  test    eax, eax
0x18002d6bb  jns     short loc_18002D6C9
0x18002d6bd  lea     rdx, aRpcimpersonate_1; "RpcImpersonateClient failed: 0x%x"
0x18002d6c4  jmp     loc_18002D777
0x18002d6c9  lea     rcx, [rsp+0C10h+var_BB8]; struct ITSSession **
0x18002d6ce  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18002d6d3  mov     ebx, eax
0x18002d6d5  test    eax, eax
0x18002d6d7  jns     short loc_18002D6F2
0x18002d6d9  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x18002d6e0  mov     ecx, 8; int
0x18002d6e5  mov     r9, r12
0x18002d6e8  mov     r8d, eax
0x18002d6eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d6f0  jmp     short loc_18002D75A
0x18002d6f2  mov     rcx, [rsp+0C10h+var_BB8]
0x18002d6f7  lea     rdx, [rsp+0C10h+var_BC0]
0x18002d6fc  mov     rax, [rcx]
0x18002d6ff  mov     rax, [rax+68h]
0x18002d703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d708  mov     ebx, eax
0x18002d70a  test    eax, eax
0x18002d70c  jns     short loc_18002D717
0x18002d70e  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x18002d715  jmp     short loc_18002D6E0
0x18002d717  mov     rcx, [rsp+0C10h+var_BC0]
0x18002d71c  lea     r8, [rsp+0C10h+var_BD8]
0x18002d721  lea     rdx, qword_1800E2708
0x18002d728  mov     rax, [rcx]
0x18002d72b  mov     rax, [rax]
0x18002d72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d733  mov     ebx, eax
0x18002d735  cmp     eax, 80004002h
0x18002d73a  jnz     loc_18002D7E4
0x18002d740  xor     ebx, ebx
0x18002d742  mov     [rsp+0C10h+var_BE0], 0
0x18002d74b  mov     rax, [rsp+0C10h+var_BE0]
0x18002d750  mov     dword ptr [r14], 0
0x18002d757  mov     [rsi], rax
0x18002d75a  call    cs:__imp_RpcRevertToSelf
0x18002d760  test    eax, eax
0x18002d762  jle     short loc_18002D76E
0x18002d764  movzx   eax, ax
0x18002d767  or      eax, 80070000h
0x18002d76c  test    eax, eax
0x18002d76e  jns     short loc_18002D789
0x18002d770  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18002d777  mov     r8d, eax
0x18002d77a  mov     ecx, 8; int
0x18002d77f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d784  mov     ebx, 80070005h
0x18002d789  lea     rcx, [rbp+0B10h+var_B70]; this
0x18002d78d  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18002d792  lea     rcx, [rsp+0C10h+TokenHandle]; this
0x18002d797  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18002d79c  lea     rcx, [rsp+0C10h+var_BD8]; void *
0x18002d7a1  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002d7a6  lea     rcx, [rsp+0C10h+var_BC0]; void *
0x18002d7ab  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002d7b0  lea     rcx, [rsp+0C10h+var_BB8]; void *
0x18002d7b5  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002d7ba  mov     eax, ebx
0x18002d7bc  mov     rcx, [rbp+0B10h+var_20]
0x18002d7c3  xor     rcx, rsp; StackCookie
0x18002d7c6  call    __security_check_cookie
0x18002d7cb  lea     r11, [rsp+0C10h+var_10]
0x18002d7d3  mov     rbx, [r11+20h]
0x18002d7d7  mov     rsi, [r11+38h]
0x18002d7db  mov     rsp, r11
0x18002d7de  pop     r14
0x18002d7e0  pop     r12
0x18002d7e2  pop     rbp
0x18002d7e3  retn
0x18002d7e4  test    eax, eax
0x18002d7e6  jns     short loc_18002D7F9
0x18002d7e8  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x18002d7ef  mov     ecx, 4
0x18002d7f4  jmp     loc_18002D6E5
0x18002d7f9  mov     rcx, [rsp+0C10h+var_BD8]
0x18002d7fe  lea     rdx, [rbp+0B10h+var_920]
0x18002d805  mov     r8d, 8F8h
0x18002d80b  mov     rax, [rcx]
0x18002d80e  mov     rax, [rax+0E8h]
0x18002d815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d81a  mov     ebx, eax
0x18002d81c  test    eax, eax
0x18002d81e  jns     short loc_18002D82C
0x18002d820  lea     rdx, aPtrremotetermi_10; "ptrRemoteTerminal->GetClientData failed"...
0x18002d827  jmp     loc_18002D6E0
0x18002d82c  test    [rbp+0B10h+var_920], 1000h
0x18002d836  jz      loc_18002D742
0x18002d83c  mov     rcx, [rsp+0C10h+var_BD8]
0x18002d841  lea     r8, [rsp+0C10h+TokenHandle]
0x18002d846  xor     edx, edx
0x18002d848  mov     rax, [rcx]
0x18002d84b  mov     rax, [rax+158h]
0x18002d852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d857  mov     ebx, eax
0x18002d859  test    eax, eax
0x18002d85b  jns     short loc_18002D869
0x18002d85d  lea     rdx, aPtrremotetermi_5; "ptrRemoteTerminal->GetSecurityFilterCli"...
0x18002d864  jmp     loc_18002D6E0
0x18002d869  mov     rcx, [rsp+0C10h+TokenHandle]; TokenHandle
0x18002d86e  lea     rax, [rsp+0C10h+var_BD0]
0x18002d873  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002d879  mov     [rsp+0C10h+ReturnLength], rax; ReturnLength
0x18002d87e  lea     r8, [rsp+0C10h+TokenInformation]; TokenInformation
0x18002d883  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002d887  call    cs:__imp_GetTokenInformation
0x18002d88d  test    eax, eax
0x18002d88f  jnz     short loc_18002D8BF
0x18002d891  call    cs:__imp_GetLastError
0x18002d897  mov     ebx, eax
0x18002d899  test    eax, eax
0x18002d89b  jle     short loc_18002D8A6
0x18002d89d  movzx   ebx, ax
0x18002d8a0  or      ebx, 80070000h
0x18002d8a6  mov     r8d, ebx
0x18002d8a9  lea     rdx, aGettokeninform; "GetTokenInformation failed: 0x%x"
0x18002d8b0  mov     ecx, 8; int
0x18002d8b5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002d8ba  jmp     loc_18002D75A
0x18002d8bf  mov     rax, qword ptr [rsp+0C10h+TokenInformation+8]
0x18002d8c4  mov     dword ptr [r14], 1
0x18002d8cb  jmp     loc_18002D757
```
