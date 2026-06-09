# SecurityManager::InitializeRpcClient(void)

- ea: `0x140273248`
- end: `0x140273484`
- name: `?InitializeRpcClient@SecurityManager@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1402740a0`

## callees

- `0x14005ade4`
- `0x14005ae6c`
- `0x1400b42d0`
- `0x1400b654c`
- `0x140132960`
- `0x14013361c`
- `0x140273248`
- `0x140274814`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1402732ce`
- `RPCRT4!RpcStringFreeW` at `0x140273333`
- `RPCRT4!RpcStringFreeW` at `0x140273451`
- `RPCRT4!RpcStringFreeW` at `0x1402732ce`
- `RPCRT4!RpcStringFreeW` at `0x140273333`
- `RPCRT4!RpcStringFreeW` at `0x140273451`
- `RPCRT4!RpcBindingSetOption` at `0x1402733dc`
- `RPCRT4!RpcBindingSetOption` at `0x1402733dc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1402732ff`
- `RPCRT4!RpcStringBindingComposeW` at `0x1402732ff`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027342d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027342d`
- `RPCRT4!RpcEpResolveBinding` at `0x1402733b0`
- `RPCRT4!RpcEpResolveBinding` at `0x1402733b0`
- `RPCRT4!RpcBindingFree` at `0x14027338a`
- `RPCRT4!RpcBindingFree` at `0x14027338a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140273352`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140273352`

## string_xrefs

- `0x1402732b0`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273318`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
__int64 __fastcall SecurityManager::InitializeRpcClient(SecurityManager *this)
{
  int v2; // eax
  unsigned int v3; // edi
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  void *v8; // rdi
  RPC_BINDING_HANDLE v9; // rsi
  void *v10; // rcx
  int Options; // [rsp+20h] [rbp-99h]
  unsigned int Optionsa; // [rsp+20h] [rbp-99h]
  _BYTE v13[8]; // [rsp+40h] [rbp-79h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-71h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE v16; // [rsp+58h] [rbp-61h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int16 Endpoint[64]; // [rsp+70h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  String = 0;
  memset_0(Endpoint, 0, sizeof(Endpoint));
  v2 = StringCchPrintfW(Endpoint, 0x40u, L"%016llX", *((_QWORD *)this + 48));
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E5,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v2,
      Options);
    return v3;
  }
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &String);
  if ( v5 )
  {
    v6 = 2288;
LABEL_5:
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
           (const char *)v5,
           Optionsa);
    if ( String )
      RpcStringFreeW(&String);
    return v7;
  }
  Binding = 0;
  v5 = RpcBindingFromStringBindingW(String, &Binding);
  if ( v5 )
  {
    v6 = 2296;
    goto LABEL_5;
  }
  v8 = (void *)*((_QWORD *)this + 46);
  v9 = Binding;
  if ( v8 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v13);
    v16 = v8;
    RpcBindingFree(&v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
  }
  *((_QWORD *)this + 46) = v9;
  v5 = RpcEpResolveBinding(v9, qword_1402DBCC0);
  if ( v5 )
  {
    v6 = 2305;
    goto LABEL_5;
  }
  v5 = RpcBindingSetOption(*((RPC_BINDING_HANDLE *)this + 46), 0xCu, 0x15F90u);
  if ( v5 )
  {
    v6 = 2316;
    goto LABEL_5;
  }
  v10 = (void *)*((_QWORD *)this + 46);
  *(_QWORD *)&SecurityQOS.Version = 1;
  SecurityQOS.IdentityTracking = 0;
  SecurityQOS.ImpersonationType = 2;
  v5 = RpcBindingSetAuthInfoExW(v10, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v5 )
  {
    v6 = 2355;
    goto LABEL_5;
  }
  if ( String )
    RpcStringFreeW(&String);
  return 0;
}

```

## disassembly

```asm
0x140273248  mov     [rsp-8+arg_8], rbx
0x14027324d  mov     [rsp-8+arg_10], rsi
0x140273252  push    rbp
0x140273253  push    rdi
0x140273254  push    r14
0x140273256  lea     rbp, [rsp-47h]
0x14027325b  sub     rsp, 100h
0x140273262  mov     rax, cs:__security_cookie
0x140273269  xor     rax, rsp
0x14027326c  mov     [rbp+57h+var_20], rax
0x140273270  mov     rbx, rcx
0x140273273  xor     r14d, r14d
0x140273276  lea     rcx, [rbp+57h+Endpoint]; void *
0x14027327a  mov     [rbp+57h+String], r14
0x14027327e  xor     edx, edx; Val
0x140273280  mov     r8d, 80h; Size
0x140273286  call    memset_0
0x14027328b  mov     r9, [rbx+180h]
0x140273292  lea     r8, a016llx; "%016llX"
0x140273299  lea     edx, [r14+40h]; unsigned __int64
0x14027329d  lea     rcx, [rbp+57h+Endpoint]; unsigned __int16 *
0x1402732a1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1402732a6  mov     edi, eax
0x1402732a8  test    eax, eax
0x1402732aa  jns     short loc_1402732E1
0x1402732ac  mov     rcx, [rbp+5Fh]; this
0x1402732b0  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402732b7  mov     r9d, eax; char *
0x1402732ba  mov     edx, 8E5h; void *
0x1402732bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402732c4  cmp     [rbp+57h+String], r14
0x1402732c8  jz      short loc_1402732DA
0x1402732ca  lea     rcx, [rbp+57h+String]; String
0x1402732ce  call    cs:__imp_RpcStringFreeW
0x1402732d5  nop     dword ptr [rax+rax+00h]
0x1402732da  mov     eax, edi
0x1402732dc  jmp     loc_14027345F
0x1402732e1  lea     rax, [rbp+57h+String]
0x1402732e5  xor     r8d, r8d; NetworkAddr
0x1402732e8  mov     [rsp+110h+StringBinding], rax; StringBinding
0x1402732ed  lea     r9, [rbp+57h+Endpoint]; Endpoint
0x1402732f1  lea     rdx, ProtSeq; "ncalrpc"
0x1402732f8  mov     [rsp+110h+Options], r14; unsigned int
0x1402732fd  xor     ecx, ecx; ObjUuid
0x1402732ff  call    cs:__imp_RpcStringBindingComposeW
0x140273306  nop     dword ptr [rax+rax+00h]
0x14027330b  test    eax, eax
0x14027330d  jz      short loc_140273346
0x14027330f  mov     edx, 8F0h; void *
0x140273314  mov     rcx, [rbp+5Fh]; this
0x140273318  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x14027331f  mov     r9d, eax; char *
0x140273322  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140273327  mov     ebx, eax
0x140273329  cmp     [rbp+57h+String], r14
0x14027332d  jz      short loc_14027333F
0x14027332f  lea     rcx, [rbp+57h+String]; String
0x140273333  call    cs:__imp_RpcStringFreeW
0x14027333a  nop     dword ptr [rax+rax+00h]
0x14027333f  mov     eax, ebx
0x140273341  jmp     loc_14027345F
0x140273346  mov     rcx, [rbp+57h+String]; StringBinding
0x14027334a  lea     rdx, [rbp+57h+Binding]; Binding
0x14027334e  mov     [rbp+57h+Binding], r14
0x140273352  call    cs:__imp_RpcBindingFromStringBindingW
0x140273359  nop     dword ptr [rax+rax+00h]
0x14027335e  test    eax, eax
0x140273360  jz      short loc_140273369
0x140273362  mov     edx, 8F8h
0x140273367  jmp     short loc_140273314
0x140273369  mov     rdi, [rbx+170h]
0x140273370  mov     rsi, [rbp+57h+Binding]
0x140273374  test    rdi, rdi
0x140273377  jz      short loc_14027339F
0x140273379  lea     rcx, [rbp+57h+var_D0]; this
0x14027337d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140273382  lea     rcx, [rbp+57h+var_B8]; Binding
0x140273386  mov     [rbp+57h+var_B8], rdi
0x14027338a  call    cs:__imp_RpcBindingFree
0x140273391  nop     dword ptr [rax+rax+00h]
0x140273396  lea     rcx, [rbp+57h+var_D0]; this
0x14027339a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14027339f  lea     rdx, qword_1402DBCC0; IfSpec
0x1402733a6  mov     [rbx+170h], rsi
0x1402733ad  mov     rcx, rsi; Binding
0x1402733b0  call    cs:__imp_RpcEpResolveBinding
0x1402733b7  nop     dword ptr [rax+rax+00h]
0x1402733bc  test    eax, eax
0x1402733be  jz      short loc_1402733CA
0x1402733c0  mov     edx, 901h
0x1402733c5  jmp     loc_140273314
0x1402733ca  mov     rcx, [rbx+170h]; hBinding
0x1402733d1  mov     edx, 0Ch; option
0x1402733d6  mov     r8d, 15F90h; optionValue
0x1402733dc  call    cs:__imp_RpcBindingSetOption
0x1402733e3  nop     dword ptr [rax+rax+00h]
0x1402733e8  test    eax, eax
0x1402733ea  jz      short loc_1402733F6
0x1402733ec  mov     edx, 90Ch
0x1402733f1  jmp     loc_140273314
0x1402733f6  mov     rcx, [rbx+170h]; Binding
0x1402733fd  lea     rax, [rbp+57h+var_B0]
0x140273401  xor     edx, edx; ServerPrincName
0x140273403  mov     [rsp+110h+SecurityQOS], rax; SecurityQOS
0x140273408  mov     dword ptr [rsp+110h+StringBinding], r14d; AuthzSvc
0x14027340d  mov     qword ptr [rbp+57h+var_B0.Version], 1
0x140273415  mov     [rbp+57h+var_B0.IdentityTracking], r14d
0x140273419  lea     r9d, [rdx+0Ah]; AuthnSvc
0x14027341d  mov     [rbp+57h+var_B0.ImpersonationType], 2
0x140273424  lea     r8d, [rdx+6]; AuthnLevel
0x140273428  mov     [rsp+110h+Options], r14; AuthIdentity
0x14027342d  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140273434  nop     dword ptr [rax+rax+00h]
0x140273439  test    eax, eax
0x14027343b  jz      short loc_140273447
0x14027343d  mov     edx, 933h
0x140273442  jmp     loc_140273314
0x140273447  cmp     [rbp+57h+String], r14
0x14027344b  jz      short loc_14027345D
0x14027344d  lea     rcx, [rbp+57h+String]; String
0x140273451  call    cs:__imp_RpcStringFreeW
0x140273458  nop     dword ptr [rax+rax+00h]
0x14027345d  xor     eax, eax
0x14027345f  mov     rcx, [rbp+57h+var_20]
0x140273463  xor     rcx, rsp; StackCookie
0x140273466  call    __security_check_cookie
0x14027346b  lea     r11, [rsp+110h+var_10]
0x140273473  mov     rbx, [r11+28h]
0x140273477  mov     rsi, [r11+30h]
0x14027347b  mov     rsp, r11
0x14027347e  pop     r14
0x140273480  pop     rdi
0x140273481  pop     rbp
0x140273482  retn
```
