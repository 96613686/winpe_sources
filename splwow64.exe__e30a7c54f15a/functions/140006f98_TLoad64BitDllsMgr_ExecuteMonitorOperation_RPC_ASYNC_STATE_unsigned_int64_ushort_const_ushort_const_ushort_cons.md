# TLoad64BitDllsMgr::ExecuteMonitorOperation(_RPC_ASYNC_STATE *,unsigned __int64,ushort const *,ushort const *,ushort const *,EPortOp,ulong *)

- ea: `0x140006f98`
- end: `0x140007194`
- name: `?ExecuteMonitorOperation@TLoad64BitDllsMgr@@QEAAXPEAU_RPC_ASYNC_STATE@@_KPEBG22W4EPortOp@@PEAK@Z`
- size: `508`
- prototype: `void __high(struct _RPC_ASYNC_STATE *, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum EPortOp, unsigned int *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d860`
- `0x14000d8a0`
- `0x14000d8e0`

## callees

- `0x140001ee0`
- `0x140006f98`
- `0x140007d00`
- `0x1400082c0`
- `0x1400085d8`
- `0x14001293c`
- `0x140012a20`
- `0x140012a9c`
- `0x140012f28`
- `0x140016010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x140007144`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140007167`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140007144`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140007167`
- `RPCRT4!RpcRevertToSelf` at `0x140007125`
- `RPCRT4!RpcRevertToSelf` at `0x140007125`
- `RPCRT4!RpcImpersonateClient` at `0x140007073`
- `RPCRT4!RpcImpersonateClient` at `0x140007073`

## string_xrefs

- `0x140007091`: `TLoad64BitDllsMgr::ExecuteMonitorOperation`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::ExecuteMonitorOperation(
        __int64 a1,
        struct _RPC_ASYNC_STATE *a2,
        void *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        int a7,
        _DWORD *a8)
{
  TLoad64BitDllsMgr *v11; // r15
  unsigned int (__fastcall *v12)(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *); // rdi
  unsigned int AuthenticationIdAndIntegrity; // eax
  int v14; // edx
  unsigned int v15; // eax
  RPC_STATUS v16; // eax
  NSecurityLibrary *v17; // rcx
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // eax
  int v21; // edx
  unsigned int v22; // eax
  int Reply; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v24; // [rsp+34h] [rbp-A5h] BYREF
  _LUID v25; // [rsp+38h] [rbp-A1h] BYREF
  struct _LUID v26; // [rsp+40h] [rbp-99h] BYREF
  const unsigned __int16 *v27; // [rsp+48h] [rbp-91h]
  _BYTE v28[64]; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v29[64]; // [rsp+90h] [rbp-49h] BYREF

  v27 = a6;
  Reply = 1;
  if ( a5 && *a5 )
  {
    v11 = pGLdrObj;
    *a8 = 0;
    if ( a7 == 2 )
    {
      v12 = TLoad64BitDllsMgr::AddPortUI;
    }
    else if ( a7 )
    {
      v12 = 0;
      if ( a7 == 1 )
        v12 = TLoad64BitDllsMgr::DeletePortUI;
    }
    else
    {
      v12 = TLoad64BitDllsMgr::ConfigurePortUI;
    }
    NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v29, (int)a2, (int)a3);
    v25 = 0;
    v24 = 0;
    AuthenticationIdAndIntegrity = NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
                                     (NSecurityLibrary::TSidUserContext *)v29,
                                     &v25,
                                     &v24);
    v15 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)AuthenticationIdAndIntegrity, v14);
    *a8 = v15;
    if ( !v15 )
    {
      v16 = RpcImpersonateClient(a2->RuntimeInfo);
      if ( v16 )
      {
        *a8 = v16;
      }
      else
      {
        if ( NSecurityLibrary::IsClientAppContainer(v17) )
        {
          SplWow64Telemetry::WriteDbgTraceError(
            "TLoad64BitDllsMgr::ExecuteMonitorOperation",
            L"called from AppContainer");
          *a8 = 5;
          Reply = 0;
        }
        else
        {
          v26 = 0;
          v25.LowPart = 0;
          NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v28, v18, v19);
          v20 = NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
                  (NSecurityLibrary::TSidUserContext *)v28,
                  &v26,
                  (unsigned int *)&v25);
          v22 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v20, v21);
          *a8 = v22;
          if ( !v22 )
          {
            if ( v25.LowPart < v24 )
            {
              *a8 = 5;
            }
            else
            {
              TLoad64BitDllsMgr::RefreshLifeSpan(v11);
              *a8 = v12(a3, a4, a5, v27);
            }
          }
          NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v28);
        }
        RpcRevertToSelf();
      }
    }
    if ( *a8 )
      Reply = 0;
    RpcAsyncCompleteCall(a2, &Reply);
    NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v29);
  }
  else
  {
    Reply = 0;
    *a8 = 87;
    RpcAsyncCompleteCall(a2, &Reply);
  }
}

```

## disassembly

```asm
0x140006f98  mov     [rsp-8+arg_0], rbx
0x140006f9d  push    rbp
0x140006f9e  push    rsi
0x140006f9f  push    rdi
0x140006fa0  push    r12
0x140006fa2  push    r13
0x140006fa4  push    r14
0x140006fa6  push    r15
0x140006fa8  lea     rbp, [rsp-7]
0x140006fad  sub     rsp, 0E0h
0x140006fb4  mov     rax, cs:__security_cookie
0x140006fbb  xor     rax, rsp
0x140006fbe  mov     [rbp+37h+var_40], rax
0x140006fc2  mov     r14, [rbp+37h+arg_20]
0x140006fc6  xor     ecx, ecx
0x140006fc8  mov     rax, [rbp+37h+arg_28]
0x140006fcc  mov     r13, r9
0x140006fcf  mov     rbx, [rbp+37h+arg_38]
0x140006fd3  mov     r12, r8
0x140006fd6  mov     [rsp+110h+var_C8], rax
0x140006fdb  mov     rsi, rdx
0x140006fde  mov     [rsp+110h+Reply], 1
0x140006fe6  test    r14, r14
0x140006fe9  jz      loc_140007155
0x140006fef  cmp     [r14], cx
0x140006ff3  jz      loc_140007155
0x140006ff9  mov     eax, [rbp+37h+arg_30]
0x140006ffc  mov     r15, cs:?pGLdrObj@@3PEAVTLoad64BitDllsMgr@@EA; TLoad64BitDllsMgr * pGLdrObj
0x140007003  mov     [rbx], ecx
0x140007005  cmp     eax, 2
0x140007008  jnz     short loc_140007013
0x14000700a  lea     rdi, ?AddPortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z; TLoad64BitDllsMgr::AddPortUI(void *,ushort const *,ushort const *,ushort const *)
0x140007011  jmp     short loc_140007031
0x140007013  test    eax, eax
0x140007015  jnz     short loc_140007020
0x140007017  lea     rdi, ?ConfigurePortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z; TLoad64BitDllsMgr::ConfigurePortUI(void *,ushort const *,ushort const *,ushort const *)
0x14000701e  jmp     short loc_140007031
0x140007020  mov     rdi, rcx
0x140007023  cmp     eax, 1
0x140007026  lea     rcx, ?DeletePortUI@TLoad64BitDllsMgr@@KAKPEAXPEBG11@Z; TLoad64BitDllsMgr::DeletePortUI(void *,ushort const *,ushort const *,ushort const *)
0x14000702d  cmovz   rdi, rcx
0x140007031  lea     rcx, [rbp+37h+var_80]; this
0x140007035  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x14000703a  lea     r8, [rsp+110h+var_DC]; unsigned int *
0x14000703f  mov     qword ptr [rsp+110h+var_D8.LowPart], 0
0x140007048  lea     rdx, [rsp+110h+var_D8]; struct _LUID *
0x14000704d  mov     [rsp+110h+var_DC], 0
0x140007055  lea     rcx, [rbp+37h+var_80]; this
0x140007059  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x14000705e  mov     ecx, eax; this
0x140007060  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x140007065  mov     [rbx], eax
0x140007067  test    eax, eax
0x140007069  jnz     loc_14000712F
0x14000706f  mov     rcx, [rsi+20h]; BindingHandle
0x140007073  call    cs:__imp_RpcImpersonateClient
0x140007079  test    eax, eax
0x14000707b  jnz     loc_14000712D
0x140007081  call    ?IsClientAppContainer@NSecurityLibrary@@YA_NXZ; NSecurityLibrary::IsClientAppContainer(void)
0x140007086  test    al, al
0x140007088  jz      short loc_1400070AD
0x14000708a  lea     rdx, aCalledFromAppc; "called from AppContainer"
0x140007091  lea     rcx, aTload64bitdlls_9; "TLoad64BitDllsMgr::ExecuteMonitorOperat"...
0x140007098  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000709d  mov     dword ptr [rbx], 5
0x1400070a3  mov     [rsp+110h+Reply], 0
0x1400070ab  jmp     short loc_140007125
0x1400070ad  lea     rcx, [rsp+110h+var_C0]; this
0x1400070b2  mov     qword ptr [rsp+110h+var_D0.LowPart], 0
0x1400070bb  mov     [rsp+110h+var_D8.LowPart], 0
0x1400070c3  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x1400070c8  lea     r8, [rsp+110h+var_D8]; unsigned int *
0x1400070cd  lea     rdx, [rsp+110h+var_D0]; struct _LUID *
0x1400070d2  lea     rcx, [rsp+110h+var_C0]; this
0x1400070d7  call    ?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z; NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)
0x1400070dc  mov     ecx, eax; this
0x1400070de  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x1400070e3  mov     [rbx], eax
0x1400070e5  test    eax, eax
0x1400070e7  jnz     short loc_14000711B
0x1400070e9  mov     ecx, [rsp+110h+var_DC]
0x1400070ed  cmp     [rsp+110h+var_D8.LowPart], ecx
0x1400070f1  jb      short loc_140007115
0x1400070f3  mov     rcx, r15; this
0x1400070f6  call    ?RefreshLifeSpan@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::RefreshLifeSpan(void)
0x1400070fb  mov     r9, [rsp+110h+var_C8]
0x140007100  mov     r8, r14
0x140007103  mov     rdx, r13
0x140007106  mov     rcx, r12
0x140007109  mov     rax, rdi
0x14000710c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007111  mov     [rbx], eax
0x140007113  jmp     short loc_14000711B
0x140007115  mov     dword ptr [rbx], 5
0x14000711b  lea     rcx, [rsp+110h+var_C0]; this
0x140007120  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140007125  call    cs:__imp_RpcRevertToSelf
0x14000712b  jmp     short loc_14000712F
0x14000712d  mov     [rbx], eax
0x14000712f  cmp     dword ptr [rbx], 0
0x140007132  jz      short loc_14000713C
0x140007134  mov     [rsp+110h+Reply], 0
0x14000713c  lea     rdx, [rsp+110h+Reply]; Reply
0x140007141  mov     rcx, rsi; pAsync
0x140007144  call    cs:__imp_RpcAsyncCompleteCall
0x14000714a  lea     rcx, [rbp+37h+var_80]; this
0x14000714e  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x140007153  jmp     short loc_14000716D
0x140007155  mov     [rsp+110h+Reply], ecx
0x140007159  lea     rdx, [rsp+110h+Reply]; Reply
0x14000715e  mov     rcx, rsi; pAsync
0x140007161  mov     dword ptr [rbx], 57h ; 'W'
0x140007167  call    cs:__imp_RpcAsyncCompleteCall
0x14000716d  mov     rcx, [rbp+37h+var_40]
0x140007171  xor     rcx, rsp; StackCookie
0x140007174  call    __security_check_cookie
0x140007179  mov     rbx, [rsp+110h+arg_0]
0x140007181  add     rsp, 0E0h
0x140007188  pop     r15
0x14000718a  pop     r14
0x14000718c  pop     r13
0x14000718e  pop     r12
0x140007190  pop     rdi
0x140007191  pop     rsi
0x140007192  pop     rbp
0x140007193  retn
```
