# SecurityManager::InitializeRpcClient(void)

- ea: `0x140279258`
- end: `0x140279494`
- name: `?InitializeRpcClient@SecurityManager@@AEAAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14027a0b0`

## callees

- `0x14006d540`
- `0x1400840cc`
- `0x140084154`
- `0x1400f0c6c`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140279258`
- `0x14027a824`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x1402792de`
- `RPCRT4!RpcStringFreeW` at `0x140279343`
- `RPCRT4!RpcStringFreeW` at `0x140279461`
- `RPCRT4!RpcStringFreeW` at `0x1402792de`
- `RPCRT4!RpcStringFreeW` at `0x140279343`
- `RPCRT4!RpcStringFreeW` at `0x140279461`
- `RPCRT4!RpcBindingSetOption` at `0x1402793ec`
- `RPCRT4!RpcBindingSetOption` at `0x1402793ec`
- `RPCRT4!RpcStringBindingComposeW` at `0x14027930f`
- `RPCRT4!RpcStringBindingComposeW` at `0x14027930f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027943d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14027943d`
- `RPCRT4!RpcEpResolveBinding` at `0x1402793c0`
- `RPCRT4!RpcEpResolveBinding` at `0x1402793c0`
- `RPCRT4!RpcBindingFree` at `0x14027939a`
- `RPCRT4!RpcBindingFree` at `0x14027939a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140279362`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140279362`

## string_xrefs

- `0x1402792c0`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279328`: `onecore\vm\worker\security\securitymanager.cpp`

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
  v5 = RpcEpResolveBinding(v9, qword_1402E5200);
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
0x140279258  mov     [rsp-8+arg_8], rbx
0x14027925d  mov     [rsp-8+arg_10], rsi
0x140279262  push    rbp
0x140279263  push    rdi
0x140279264  push    r14
0x140279266  lea     rbp, [rsp-47h]
0x14027926b  sub     rsp, 100h
0x140279272  mov     rax, cs:__security_cookie
0x140279279  xor     rax, rsp
0x14027927c  mov     [rbp+57h+var_20], rax
0x140279280  mov     rbx, rcx
0x140279283  xor     r14d, r14d
0x140279286  lea     rcx, [rbp+57h+Endpoint]; void *
0x14027928a  mov     [rbp+57h+String], r14
0x14027928e  xor     edx, edx; Val
0x140279290  mov     r8d, 80h; Size
0x140279296  call    memset_0
0x14027929b  mov     r9, [rbx+180h]
0x1402792a2  lea     r8, a016llx; "%016llX"
0x1402792a9  lea     edx, [r14+40h]; unsigned __int64
0x1402792ad  lea     rcx, [rbp+57h+Endpoint]; unsigned __int16 *
0x1402792b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1402792b6  mov     edi, eax
0x1402792b8  test    eax, eax
0x1402792ba  jns     short loc_1402792F1
0x1402792bc  mov     rcx, [rbp+5Fh]; this
0x1402792c0  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1402792c7  mov     r9d, eax; char *
0x1402792ca  mov     edx, 8E5h; void *
0x1402792cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402792d4  cmp     [rbp+57h+String], r14
0x1402792d8  jz      short loc_1402792EA
0x1402792da  lea     rcx, [rbp+57h+String]; String
0x1402792de  call    cs:__imp_RpcStringFreeW
0x1402792e5  nop     dword ptr [rax+rax+00h]
0x1402792ea  mov     eax, edi
0x1402792ec  jmp     loc_14027946F
0x1402792f1  lea     rax, [rbp+57h+String]
0x1402792f5  xor     r8d, r8d; NetworkAddr
0x1402792f8  mov     [rsp+110h+StringBinding], rax; StringBinding
0x1402792fd  lea     r9, [rbp+57h+Endpoint]; Endpoint
0x140279301  lea     rdx, ProtSeq; "ncalrpc"
0x140279308  mov     [rsp+110h+Options], r14; unsigned int
0x14027930d  xor     ecx, ecx; ObjUuid
0x14027930f  call    cs:__imp_RpcStringBindingComposeW
0x140279316  nop     dword ptr [rax+rax+00h]
0x14027931b  test    eax, eax
0x14027931d  jz      short loc_140279356
0x14027931f  mov     edx, 8F0h; void *
0x140279324  mov     rcx, [rbp+5Fh]; this
0x140279328  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x14027932f  mov     r9d, eax; char *
0x140279332  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140279337  mov     ebx, eax
0x140279339  cmp     [rbp+57h+String], r14
0x14027933d  jz      short loc_14027934F
0x14027933f  lea     rcx, [rbp+57h+String]; String
0x140279343  call    cs:__imp_RpcStringFreeW
0x14027934a  nop     dword ptr [rax+rax+00h]
0x14027934f  mov     eax, ebx
0x140279351  jmp     loc_14027946F
0x140279356  mov     rcx, [rbp+57h+String]; StringBinding
0x14027935a  lea     rdx, [rbp+57h+Binding]; Binding
0x14027935e  mov     [rbp+57h+Binding], r14
0x140279362  call    cs:__imp_RpcBindingFromStringBindingW
0x140279369  nop     dword ptr [rax+rax+00h]
0x14027936e  test    eax, eax
0x140279370  jz      short loc_140279379
0x140279372  mov     edx, 8F8h
0x140279377  jmp     short loc_140279324
0x140279379  mov     rdi, [rbx+170h]
0x140279380  mov     rsi, [rbp+57h+Binding]
0x140279384  test    rdi, rdi
0x140279387  jz      short loc_1402793AF
0x140279389  lea     rcx, [rbp+57h+var_D0]; this
0x14027938d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140279392  lea     rcx, [rbp+57h+var_B8]; Binding
0x140279396  mov     [rbp+57h+var_B8], rdi
0x14027939a  call    cs:__imp_RpcBindingFree
0x1402793a1  nop     dword ptr [rax+rax+00h]
0x1402793a6  lea     rcx, [rbp+57h+var_D0]; this
0x1402793aa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1402793af  lea     rdx, qword_1402E5200; IfSpec
0x1402793b6  mov     [rbx+170h], rsi
0x1402793bd  mov     rcx, rsi; Binding
0x1402793c0  call    cs:__imp_RpcEpResolveBinding
0x1402793c7  nop     dword ptr [rax+rax+00h]
0x1402793cc  test    eax, eax
0x1402793ce  jz      short loc_1402793DA
0x1402793d0  mov     edx, 901h
0x1402793d5  jmp     loc_140279324
0x1402793da  mov     rcx, [rbx+170h]; hBinding
0x1402793e1  mov     edx, 0Ch; option
0x1402793e6  mov     r8d, 15F90h; optionValue
0x1402793ec  call    cs:__imp_RpcBindingSetOption
0x1402793f3  nop     dword ptr [rax+rax+00h]
0x1402793f8  test    eax, eax
0x1402793fa  jz      short loc_140279406
0x1402793fc  mov     edx, 90Ch
0x140279401  jmp     loc_140279324
0x140279406  mov     rcx, [rbx+170h]; Binding
0x14027940d  lea     rax, [rbp+57h+var_B0]
0x140279411  xor     edx, edx; ServerPrincName
0x140279413  mov     [rsp+110h+SecurityQOS], rax; SecurityQOS
0x140279418  mov     dword ptr [rsp+110h+StringBinding], r14d; AuthzSvc
0x14027941d  mov     qword ptr [rbp+57h+var_B0.Version], 1
0x140279425  mov     [rbp+57h+var_B0.IdentityTracking], r14d
0x140279429  lea     r9d, [rdx+0Ah]; AuthnSvc
0x14027942d  mov     [rbp+57h+var_B0.ImpersonationType], 2
0x140279434  lea     r8d, [rdx+6]; AuthnLevel
0x140279438  mov     [rsp+110h+Options], r14; AuthIdentity
0x14027943d  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140279444  nop     dword ptr [rax+rax+00h]
0x140279449  test    eax, eax
0x14027944b  jz      short loc_140279457
0x14027944d  mov     edx, 933h
0x140279452  jmp     loc_140279324
0x140279457  cmp     [rbp+57h+String], r14
0x14027945b  jz      short loc_14027946D
0x14027945d  lea     rcx, [rbp+57h+String]; String
0x140279461  call    cs:__imp_RpcStringFreeW
0x140279468  nop     dword ptr [rax+rax+00h]
0x14027946d  xor     eax, eax
0x14027946f  mov     rcx, [rbp+57h+var_20]
0x140279473  xor     rcx, rsp; StackCookie
0x140279476  call    __security_check_cookie
0x14027947b  lea     r11, [rsp+110h+var_10]
0x140279483  mov     rbx, [r11+28h]
0x140279487  mov     rsi, [r11+30h]
0x14027948b  mov     rsp, r11
0x14027948e  pop     r14
0x140279490  pop     rdi
0x140279491  pop     rbp
0x140279492  retn
```
