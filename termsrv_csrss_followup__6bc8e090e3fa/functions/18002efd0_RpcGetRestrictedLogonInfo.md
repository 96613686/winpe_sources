# RpcGetRestrictedLogonInfo

- ea: `0x18002efd0`
- end: `0x18002f2e9`
- name: `RpcGetRestrictedLogonInfo`
- size: `793`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x18000ba50`
- `0x18000f760`
- `0x1800139c0`
- `0x180015020`
- `0x18002efd0`
- `0x180033330`
- `0x180033f60`
- `0x180034e64`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2a4`
- `RPCRT4!RpcRevertToSelf` at `0x18002f160`
- `RPCRT4!RpcRevertToSelf` at `0x18002f160`
- `RPCRT4!RpcImpersonateClient` at `0x18002f0a7`
- `RPCRT4!RpcImpersonateClient` at `0x18002f0a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f294`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f294`

## string_xrefs

- `0x18002f2c2`: `GetTokenInformation failed: 0x%x`
- `0x18002f0c3`: `RpcImpersonateClient failed: 0x%x`
- `0x18002f26a`: `ptrRemoteTerminal->GetSecurityFilterClientToken failed: 0x%x in %s`

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
  v11 = (**v20)(v20, qword_1800E8758, &v17);
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
0x18002efd0  mov     [rsp-8+arg_0], rbx
0x18002efd5  mov     [rsp-8+arg_18], rsi
0x18002efda  push    rbp
0x18002efdb  push    r12
0x18002efdd  push    r14
0x18002efdf  lea     rbp, [rsp-0B00h]
0x18002efe7  sub     rsp, 0C00h
0x18002efee  mov     rax, cs:__security_cookie
0x18002eff5  xor     rax, rsp
0x18002eff8  mov     [rbp+0B10h+var_20], rax
0x18002efff  mov     rsi, r8
0x18002f002  mov     [rsp+0C10h+var_BB8], 0
0x18002f00b  mov     r14, rdx
0x18002f00e  mov     [rsp+0C10h+var_BC0], 0
0x18002f017  xor     edx, edx; Val
0x18002f019  mov     [rsp+0C10h+var_BD8], 0
0x18002f022  mov     r8d, 8F8h; Size
0x18002f028  mov     [rsp+0C10h+TokenHandle], 0
0x18002f031  lea     rcx, [rbp+0B10h+var_920]; void *
0x18002f038  call    memset_0
0x18002f03d  xorps   xmm0, xmm0
0x18002f040  lea     r12, aRpcgetrestrict; "RpcGetRestrictedLogonInfo"
0x18002f047  xor     eax, eax
0x18002f049  lea     rcx, [rbp+0B10h+var_B70]; this
0x18002f04d  mov     r8, r12; char *
0x18002f050  mov     [rbp+0B10h+var_B80], rax
0x18002f054  xor     edx, edx; int
0x18002f056  mov     [rsp+0C10h+var_BD0], eax
0x18002f05a  movups  [rsp+0C10h+TokenInformation], xmm0
0x18002f05f  movups  [rsp+0C10h+var_BA0], xmm0
0x18002f064  movups  [rbp+0B10h+var_B90], xmm0
0x18002f068  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x18002f06d  test    r14, r14
0x18002f070  jnz     short loc_18002F097
0x18002f072  lea     r8, aPbrestrictedlo; "pbRestrictedLogonRequested"
0x18002f079  mov     r9, r12
0x18002f07c  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x18002f083  mov     ecx, 8; int
0x18002f088  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f08d  mov     ebx, 80070057h
0x18002f092  jmp     loc_18002F195
0x18002f097  test    rsi, rsi
0x18002f09a  jnz     short loc_18002F0A5
0x18002f09c  lea     r8, aPauthenticatio; "pAuthenticationId"
0x18002f0a3  jmp     short loc_18002F079
0x18002f0a5  xor     ecx, ecx; BindingHandle
0x18002f0a7  call    cs:__imp_RpcImpersonateClient
0x18002f0ae  nop     dword ptr [rax+rax+00h]
0x18002f0b3  test    eax, eax
0x18002f0b5  jle     short loc_18002F0C1
0x18002f0b7  movzx   eax, ax
0x18002f0ba  or      eax, 80070000h
0x18002f0bf  test    eax, eax
0x18002f0c1  jns     short loc_18002F0CF
0x18002f0c3  lea     rdx, aRpcimpersonate_1; "RpcImpersonateClient failed: 0x%x"
0x18002f0ca  jmp     loc_18002F183
0x18002f0cf  lea     rcx, [rsp+0C10h+var_BB8]; struct ITSSession **
0x18002f0d4  call    ?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z; CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)
0x18002f0d9  mov     ebx, eax
0x18002f0db  test    eax, eax
0x18002f0dd  jns     short loc_18002F0F8
0x18002f0df  lea     rdx, aCrpcutilsGetse; "CRpcUtils::GetSessionFromRpcClientId fa"...
0x18002f0e6  mov     ecx, 8; int
0x18002f0eb  mov     r9, r12
0x18002f0ee  mov     r8d, eax
0x18002f0f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f0f6  jmp     short loc_18002F160
0x18002f0f8  mov     rcx, [rsp+0C10h+var_BB8]
0x18002f0fd  lea     rdx, [rsp+0C10h+var_BC0]
0x18002f102  mov     rax, [rcx]
0x18002f105  mov     rax, [rax+68h]
0x18002f109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f10e  mov     ebx, eax
0x18002f110  test    eax, eax
0x18002f112  jns     short loc_18002F11D
0x18002f114  lea     rdx, aGetterminalFai; "GetTerminal failed: 0x%x in %s"
0x18002f11b  jmp     short loc_18002F0E6
0x18002f11d  mov     rcx, [rsp+0C10h+var_BC0]
0x18002f122  lea     r8, [rsp+0C10h+var_BD8]
0x18002f127  lea     rdx, qword_1800E8758
0x18002f12e  mov     rax, [rcx]
0x18002f131  mov     rax, [rax]
0x18002f134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f139  mov     ebx, eax
0x18002f13b  cmp     eax, 80004002h
0x18002f140  jnz     loc_18002F1F1
0x18002f146  xor     ebx, ebx
0x18002f148  mov     [rsp+0C10h+var_BE0], 0
0x18002f151  mov     rax, [rsp+0C10h+var_BE0]
0x18002f156  mov     dword ptr [r14], 0
0x18002f15d  mov     [rsi], rax
0x18002f160  call    cs:__imp_RpcRevertToSelf
0x18002f167  nop     dword ptr [rax+rax+00h]
0x18002f16c  test    eax, eax
0x18002f16e  jle     short loc_18002F17A
0x18002f170  movzx   eax, ax
0x18002f173  or      eax, 80070000h
0x18002f178  test    eax, eax
0x18002f17a  jns     short loc_18002F195
0x18002f17c  lea     rdx, aRpcreverttosel_1; "RpcRevertToSelf failed: 0x%x"
0x18002f183  mov     r8d, eax
0x18002f186  mov     ecx, 8; int
0x18002f18b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f190  mov     ebx, 80070005h
0x18002f195  lea     rcx, [rbp+0B10h+var_B70]; this
0x18002f199  call    ??1CRpcCallTrace@@UEAA@XZ; CRpcCallTrace::~CRpcCallTrace(void)
0x18002f19e  lea     rcx, [rsp+0C10h+TokenHandle]; this
0x18002f1a3  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18002f1a8  lea     rcx, [rsp+0C10h+var_BD8]; void *
0x18002f1ad  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002f1b2  lea     rcx, [rsp+0C10h+var_BC0]; void *
0x18002f1b7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002f1bc  lea     rcx, [rsp+0C10h+var_BB8]; void *
0x18002f1c1  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18002f1c6  mov     eax, ebx
0x18002f1c8  mov     rcx, [rbp+0B10h+var_20]
0x18002f1cf  xor     rcx, rsp; StackCookie
0x18002f1d2  call    __security_check_cookie
0x18002f1d7  lea     r11, [rsp+0C10h+var_10]
0x18002f1df  mov     rbx, [r11+20h]
0x18002f1e3  mov     rsi, [r11+38h]
0x18002f1e7  mov     rsp, r11
0x18002f1ea  pop     r14
0x18002f1ec  pop     r12
0x18002f1ee  pop     rbp
0x18002f1ef  retn
0x18002f1f1  test    eax, eax
0x18002f1f3  jns     short loc_18002F206
0x18002f1f5  lea     rdx, aQiIremotetermi_0; "QI( IRemoteTerminal ) failed: 0x%x in %"...
0x18002f1fc  mov     ecx, 4
0x18002f201  jmp     loc_18002F0EB
0x18002f206  mov     rcx, [rsp+0C10h+var_BD8]
0x18002f20b  lea     rdx, [rbp+0B10h+var_920]
0x18002f212  mov     r8d, 8F8h
0x18002f218  mov     rax, [rcx]
0x18002f21b  mov     rax, [rax+0E8h]
0x18002f222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f227  mov     ebx, eax
0x18002f229  test    eax, eax
0x18002f22b  jns     short loc_18002F239
0x18002f22d  lea     rdx, aPtrremotetermi_10; "ptrRemoteTerminal->GetClientData failed"...
0x18002f234  jmp     loc_18002F0E6
0x18002f239  test    [rbp+0B10h+var_920], 1000h
0x18002f243  jz      loc_18002F148
0x18002f249  mov     rcx, [rsp+0C10h+var_BD8]
0x18002f24e  lea     r8, [rsp+0C10h+TokenHandle]
0x18002f253  xor     edx, edx
0x18002f255  mov     rax, [rcx]
0x18002f258  mov     rax, [rax+158h]
0x18002f25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f264  mov     ebx, eax
0x18002f266  test    eax, eax
0x18002f268  jns     short loc_18002F276
0x18002f26a  lea     rdx, aPtrremotetermi_5; "ptrRemoteTerminal->GetSecurityFilterCli"...
0x18002f271  jmp     loc_18002F0E6
0x18002f276  mov     rcx, [rsp+0C10h+TokenHandle]; TokenHandle
0x18002f27b  lea     rax, [rsp+0C10h+var_BD0]
0x18002f280  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002f286  mov     [rsp+0C10h+ReturnLength], rax; ReturnLength
0x18002f28b  lea     r8, [rsp+0C10h+TokenInformation]; TokenInformation
0x18002f290  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002f294  call    cs:__imp_GetTokenInformation
0x18002f29b  nop     dword ptr [rax+rax+00h]
0x18002f2a0  test    eax, eax
0x18002f2a2  jnz     short loc_18002F2D8
0x18002f2a4  call    cs:__imp_GetLastError
0x18002f2ab  nop     dword ptr [rax+rax+00h]
0x18002f2b0  mov     ebx, eax
0x18002f2b2  test    eax, eax
0x18002f2b4  jle     short loc_18002F2BF
0x18002f2b6  movzx   ebx, ax
0x18002f2b9  or      ebx, 80070000h
0x18002f2bf  mov     r8d, ebx
0x18002f2c2  lea     rdx, aGettokeninform; "GetTokenInformation failed: 0x%x"
0x18002f2c9  mov     ecx, 8; int
0x18002f2ce  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f2d3  jmp     loc_18002F160
0x18002f2d8  mov     rax, qword ptr [rsp+0C10h+TokenInformation+8]
0x18002f2dd  mov     dword ptr [r14], 1
0x18002f2e4  jmp     loc_18002F15D
```
