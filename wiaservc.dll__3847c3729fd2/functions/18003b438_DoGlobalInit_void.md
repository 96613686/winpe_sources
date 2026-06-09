# DoGlobalInit(void)

- ea: `0x18003b438`
- end: `0x18003b643`
- name: `?DoGlobalInit@@YAJXZ`
- size: `523`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800459d8`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x180010340`
- `0x1800147d0`
- `0x180022440`
- `0x180025fe0`
- `0x18002ba94`
- `0x18002de18`
- `0x18002def8`
- `0x18003b438`
- `0x18003c57c`
- `0x180046f1c`
- `0x180047800`
- `0x180047b80`
- `0x180048030`
- `0x180048590`
- `0x18004b0f0`
- `0x18004bc70`
- `0x18004fb40`
- `0x180054be0`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003b54e`
- `ole32!CoCreateInstance` at `0x18003b54e`
- `ole32!CoInitializeSecurity` at `0x18003b4cf`
- `ole32!CoInitializeSecurity` at `0x18003b4cf`

## string_xrefs

- `0x18003b4dd`: `Could not initialize COM Security (hr = 0x%08X)`
- `0x18003b501`: `Could not initialize COM Security (hr = 0x%08X)`
- `0x18003b5f4`: `Could not register our IClassFactory interface with COM - the service cannot continue`
- `0x18003b616`: `Could not register our IClassFactory interface with COM - the service cannot continue`

## pseudocode

```c
__int64 DoGlobalInit(void)
{
  char *v0; // rbx
  void *v1; // rdx
  void **v2; // rax
  void *v3; // rdx
  __int64 v4; // rcx
  HRESULT v5; // edi
  char *v6; // rbx
  void *v7; // rdx
  void **v8; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbx
  CEventNotifier *v12; // rcx
  unsigned int v13; // edx
  struct _FACTORY_DATA *v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  LPVOID ppv; // [rsp+80h] [rbp+8h] BYREF

  if ( (unsigned int)StartRpcServerListen() )
  {
    v0 = (char *)WiaTrace_TraceLog("Could not initialize the STI RPC server correctly");
    WriteDbgTraceErrorWI("DoGlobalInit", v0);
    WiaTrcLib::Free((WiaTrcLib *)v0, v1);
    v2 = (void **)WiaTrace_Trace("Could not initialize the STI RPC server correctly");
    WiaTrace_ProcessTrace_Ex(v4, v3, (void *)"DoGlobalInit", 1, v2);
  }
  v5 = CoInitializeSecurity(&CLSID_WiaDevMgr, -1, 0, 0, 2u, 3u, 0, 0x2048u, 0);
  if ( v5 < 0 )
  {
    v6 = (char *)WiaTrace_TraceLog("Could not initialize COM Security (hr = 0x%08X)");
    WriteDbgTraceErrorWI("DoGlobalInit", v6);
    WiaTrcLib::Free((WiaTrcLib *)v6, v7);
    v8 = (void **)WiaTrace_Trace("Could not initialize COM Security (hr = 0x%08X)", v5);
LABEL_5:
    WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"DoGlobalInit", 1, v8);
    return (unsigned int)v5;
  }
  ppv = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv) >= 0 && ppv )
  {
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  SchedulerInitialize();
  v11 = 0;
  do
  {
    ((void (*)(void))(&g_pServiceComponentCreators)[v11])();
    v11 = (unsigned int)(v11 + 1);
  }
  while ( (&g_pServiceComponentCreators)[v11] );
  v5 = CEventNotifier::Initialize(v12);
  if ( v5 < 0 )
  {
    v15 = (char *)WiaTrace_TraceLog("The global persistent event notification object could not be initialized correctly");
    WriteDbgTraceErrorWI("DoGlobalInit", v15);
    WiaTrcLib::Free((WiaTrcLib *)v15, v16);
    v8 = (void **)WiaTrace_Trace("The global persistent event notification object could not be initialized correctly");
    goto LABEL_5;
  }
  if ( !(unsigned int)StartFactories(v14, v13) )
  {
    v17 = (char *)WiaTrace_TraceLog("Could not register our IClassFactory interface with COM - the service cannot continue");
    WriteDbgTraceErrorWI("DoGlobalInit", v17);
    WiaTrcLib::Free((WiaTrcLib *)v17, v18);
    v19 = (void **)WiaTrace_Trace("Could not register our IClassFactory interface with COM - the service cannot continue");
    WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"DoGlobalInit", 1, v19);
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003b438  push    rbx
0x18003b43a  push    rbp
0x18003b43b  push    rdi
0x18003b43c  push    r14
0x18003b43e  sub     rsp, 58h
0x18003b442  call    ?StartRpcServerListen@@YAJXZ; StartRpcServerListen(void)
0x18003b447  lea     r14, aDoglobalinit; "DoGlobalInit"
0x18003b44e  mov     ebp, 1
0x18003b453  test    eax, eax
0x18003b455  jz      short loc_18003B495
0x18003b457  lea     rcx, aCouldNotInitia; "Could not initialize the STI RPC server"...
0x18003b45e  call    WiaTrace_TraceLog
0x18003b463  mov     rdx, rax; char *
0x18003b466  mov     rcx, r14; char *
0x18003b469  mov     rbx, rax
0x18003b46c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003b471  mov     rcx, rbx; this
0x18003b474  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003b479  lea     rcx, aCouldNotInitia; "Could not initialize the STI RPC server"...
0x18003b480  call    WiaTrace_Trace
0x18003b485  mov     r9d, ebp; int
0x18003b488  mov     qword ptr [rsp+78h+dwAuthnLevel], rax; lpMem
0x18003b48d  mov     r8, r14; int
0x18003b490  call    WiaTrace_ProcessTrace_Ex
0x18003b495  mov     [rsp+78h+pReserved3], 0; pReserved3
0x18003b49e  lea     rcx, CLSID_WiaDevMgr; pSecDesc
0x18003b4a5  mov     [rsp+78h+dwCapabilities], 2048h; dwCapabilities
0x18003b4ad  xor     r9d, r9d; pReserved1
0x18003b4b0  mov     [rsp+78h+pAuthList], 0; pAuthList
0x18003b4b9  xor     r8d, r8d; asAuthSvc
0x18003b4bc  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x18003b4c4  or      edx, 0FFFFFFFFh; cAuthSvc
0x18003b4c7  mov     [rsp+78h+dwAuthnLevel], 2; dwAuthnLevel
0x18003b4cf  call    cs:__imp_CoInitializeSecurity
0x18003b4d5  mov     edi, eax
0x18003b4d7  test    eax, eax
0x18003b4d9  jns     short loc_18003B522
0x18003b4db  mov     edx, eax
0x18003b4dd  lea     rcx, aCouldNotInitia_0; "Could not initialize COM Security (hr ="...
0x18003b4e4  call    WiaTrace_TraceLog
0x18003b4e9  mov     rdx, rax; char *
0x18003b4ec  mov     rcx, r14; char *
0x18003b4ef  mov     rbx, rax
0x18003b4f2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003b4f7  mov     rcx, rbx; this
0x18003b4fa  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003b4ff  mov     edx, edi
0x18003b501  lea     rcx, aCouldNotInitia_0; "Could not initialize COM Security (hr ="...
0x18003b508  call    WiaTrace_Trace
0x18003b50d  mov     r9d, ebp; int
0x18003b510  mov     qword ptr [rsp+78h+dwAuthnLevel], rax; lpMem
0x18003b515  mov     r8, r14; int
0x18003b518  call    WiaTrace_ProcessTrace_Ex
0x18003b51d  jmp     loc_18003B637
0x18003b522  lea     rax, [rsp+78h+ppv]
0x18003b52a  mov     [rsp+78h+ppv], 0
0x18003b536  lea     r9, IID_IGlobalOptions; riid
0x18003b53d  mov     qword ptr [rsp+78h+dwAuthnLevel], rax; ppv
0x18003b542  mov     r8d, ebp; dwClsContext
0x18003b545  lea     rcx, CLSID_GlobalOptions; rclsid
0x18003b54c  xor     edx, edx; pUnkOuter
0x18003b54e  call    cs:__imp_CoCreateInstance
0x18003b554  test    eax, eax
0x18003b556  js      short loc_18003B58D
0x18003b558  mov     rcx, [rsp+78h+ppv]
0x18003b560  test    rcx, rcx
0x18003b563  jz      short loc_18003B58D
0x18003b565  mov     rax, [rcx]
0x18003b568  mov     r8, rbp
0x18003b56b  mov     edx, 5
0x18003b570  mov     rax, [rax+18h]
0x18003b574  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b579  mov     rcx, [rsp+78h+ppv]
0x18003b581  mov     rax, [rcx]
0x18003b584  mov     rax, [rax+10h]
0x18003b588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b58d  call    ?SchedulerInitialize@@YAHXZ; SchedulerInitialize(void)
0x18003b592  xor     ebx, ebx
0x18003b594  lea     rdi, ?g_pServiceComponentCreators@@3PAP6AXXZA; void (*near * g_pServiceComponentCreators)(void)
0x18003b59b  mov     rax, ds:(?g_pServiceComponentCreators@@3PAP6AXXZA - 180079DE0h)[rdi+rbx*8]; void (*near * g_pServiceComponentCreators)(void)
0x18003b59f  call    _guard_dispatch_icall$thunk$10345483385596137414; RegistryDeviceEnumerator::CreateInstance(void)
0x18003b5a4  add     ebx, ebp
0x18003b5a6  cmp     qword ptr [rdi+rbx*8], 0
0x18003b5ab  jnz     short loc_18003B59B
0x18003b5ad  call    ?Initialize@CEventNotifier@@QEAAJXZ; CEventNotifier::Initialize(void)
0x18003b5b2  mov     edi, eax
0x18003b5b4  test    eax, eax
0x18003b5b6  jns     short loc_18003B5EB
0x18003b5b8  lea     rcx, aTheGlobalPersi; "The global persistent event notificatio"...
0x18003b5bf  call    WiaTrace_TraceLog
0x18003b5c4  mov     rdx, rax; char *
0x18003b5c7  mov     rcx, r14; char *
0x18003b5ca  mov     rbx, rax
0x18003b5cd  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003b5d2  mov     rcx, rbx; this
0x18003b5d5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003b5da  lea     rcx, aTheGlobalPersi; "The global persistent event notificatio"...
0x18003b5e1  call    WiaTrace_Trace
0x18003b5e6  jmp     loc_18003B50D
0x18003b5eb  call    ?StartFactories@@YAHPEAU_FACTORY_DATA@@I@Z; StartFactories(_FACTORY_DATA *,uint)
0x18003b5f0  test    eax, eax
0x18003b5f2  jnz     short loc_18003B637
0x18003b5f4  lea     rcx, aCouldNotRegist; "Could not register our IClassFactory in"...
0x18003b5fb  call    WiaTrace_TraceLog
0x18003b600  mov     rdx, rax; char *
0x18003b603  mov     rcx, r14; char *
0x18003b606  mov     rbx, rax
0x18003b609  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003b60e  mov     rcx, rbx; this
0x18003b611  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003b616  lea     rcx, aCouldNotRegist; "Could not register our IClassFactory in"...
0x18003b61d  call    WiaTrace_Trace
0x18003b622  mov     r9d, ebp; int
0x18003b625  mov     qword ptr [rsp+78h+dwAuthnLevel], rax; lpMem
0x18003b62a  mov     r8, r14; int
0x18003b62d  call    WiaTrace_ProcessTrace_Ex
0x18003b632  mov     edi, 8000FFFFh
0x18003b637  mov     eax, edi
0x18003b639  add     rsp, 58h
0x18003b63d  pop     r14
0x18003b63f  pop     rdi
0x18003b640  pop     rbp
0x18003b641  pop     rbx
0x18003b642  retn
```
