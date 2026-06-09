# CService::MiscThread(void)

- ea: `0x180039304`
- end: `0x180039457`
- name: `?MiscThread@CService@@IEAAJXZ`
- size: `339`
- prototype: `void __fastcall __noreturn(CService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003a180`

## callees

- `0x18000a210`
- `0x180013150`
- `0x1800241f0`
- `0x180038538`
- `0x180039304`
- `0x18003986c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003935d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003935d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039350`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180039350`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180039450`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180039450`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039448`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180039448`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039320`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180039320`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800393f2`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800393fe`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800393f2`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x1800393fe`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180039372`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180039372`

## string_xrefs

- `0x18003932c`: `CService::MiscThread`
- `0x180039336`: `CComUtils::CoInitialize failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn CService::MiscThread(HANDLE *this)
{
  HRESULT v2; // eax
  DWORD v3; // ebx
  struct ATL::_ATL_COM_MODULE70 *v4; // rcx
  const struct _GUID *v5; // r8
  LPUNKNOWN v6; // rcx
  LPUNKNOWN pUnk; // [rsp+48h] [rbp+18h] BYREF
  LPUNKNOWN v8; // [rsp+50h] [rbp+20h] BYREF

  v2 = CoInitializeEx(0, 4u);
  v3 = v2;
  if ( v2 >= 0 )
  {
    SetEvent(this[9]);
    WaitForSingleObject(this[11], 0xFFFFFFFF);
    if ( dword_18012BBA8 )
    {
      CoRevokeClassObject(dwRegister);
      dword_18012BBA8 = 0;
    }
    SmartPtr<ITerminal>::operator=(&qword_18012BBB0, 0);
    pUnk = 0;
    if ( ATL::AtlComModuleGetClassObject(v4, &CLSID_RemoteConnectionManager, v5, (void **)&pUnk) >= 0 )
    {
      v8 = 0;
      if ( ((int (__fastcall *)(LPUNKNOWN, _QWORD, GUID *, LPUNKNOWN *))pUnk->lpVtbl[1].QueryInterface)(
             pUnk,
             0,
             &IID_IConnectionManager,
             &v8) >= 0 )
      {
        ((void (__fastcall *)(LPUNKNOWN))v8->lpVtbl[8].AddRef)(v8);
        CoDisconnectObject(pUnk, 0);
        CoDisconnectObject(v8, 0);
        SmartPtr<ITerminal>::operator=(&v8, 0);
      }
      v6 = pUnk;
      pUnk = 0;
      if ( v6 )
        ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&v8);
    }
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&pUnk);
    CService::ServiceStopCleanupObjects((CService *)this);
    CoUninitialize();
  }
  else
  {
    _DbgPrintMessage(8, "CComUtils::CoInitialize failed: 0x%x in %s", v2, "CService::MiscThread");
  }
  ExitThread(v3);
}

```

## disassembly

```asm
0x180039304  mov     [rsp-8+arg_0], rbx
0x180039309  mov     [rsp-8+arg_18], rdi
0x18003930e  push    rbp
0x18003930f  mov     rbp, rsp
0x180039312  sub     rsp, 30h
0x180039316  mov     rdi, rcx
0x180039319  mov     edx, 4; dwCoInit
0x18003931e  xor     ecx, ecx; pvReserved
0x180039320  call    cs:__imp_CoInitializeEx
0x180039326  mov     ebx, eax
0x180039328  test    eax, eax
0x18003932a  jns     short loc_18003934C
0x18003932c  lea     r9, aCserviceMiscth; "CService::MiscThread"
0x180039333  mov     r8d, eax
0x180039336  lea     rdx, aCcomutilsCoini; "CComUtils::CoInitialize failed: 0x%x in"...
0x18003933d  mov     ecx, 8; int
0x180039342  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180039347  jmp     loc_18003944E
0x18003934c  mov     rcx, [rdi+48h]; hEvent
0x180039350  call    cs:__imp_SetEvent
0x180039356  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180039359  mov     rcx, [rdi+58h]; hHandle
0x18003935d  call    cs:__imp_WaitForSingleObject
0x180039363  cmp     cs:dword_18012BBA8, 0
0x18003936a  jz      short loc_180039382
0x18003936c  mov     ecx, cs:dwRegister; dwRegister
0x180039372  call    cs:__imp_CoRevokeClassObject
0x180039378  mov     cs:dword_18012BBA8, 0
0x180039382  xor     edx, edx
0x180039384  lea     rcx, qword_18012BBB0
0x18003938b  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180039390  mov     [rbp+pUnk], 0
0x180039398  lea     r9, [rbp+pUnk]; void **
0x18003939c  lea     rdx, CLSID_RemoteConnectionManager; struct _GUID *
0x1800393a3  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800393a8  test    eax, eax
0x1800393aa  js      loc_180039437
0x1800393b0  mov     [rbp+arg_10], 0
0x1800393b8  mov     rcx, [rbp+pUnk]
0x1800393bc  mov     rax, [rcx]
0x1800393bf  lea     r9, [rbp+arg_10]
0x1800393c3  lea     r8, IID_IConnectionManager
0x1800393ca  xor     edx, edx
0x1800393cc  mov     rax, [rax+18h]
0x1800393d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393d5  test    eax, eax
0x1800393d7  js      short loc_18003940F
0x1800393d9  mov     rcx, [rbp+arg_10]
0x1800393dd  mov     rax, [rcx]
0x1800393e0  mov     rax, [rax+0C8h]
0x1800393e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393ec  xor     edx, edx; dwReserved
0x1800393ee  mov     rcx, [rbp+pUnk]; pUnk
0x1800393f2  call    cs:__imp_CoDisconnectObject
0x1800393f8  xor     edx, edx; dwReserved
0x1800393fa  mov     rcx, [rbp+arg_10]; pUnk
0x1800393fe  call    cs:__imp_CoDisconnectObject
0x180039404  xor     edx, edx
0x180039406  lea     rcx, [rbp+arg_10]
0x18003940a  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18003940f  mov     rcx, [rbp+pUnk]
0x180039413  mov     [rbp+pUnk], 0
0x18003941b  test    rcx, rcx
0x18003941e  jz      short loc_18003942D
0x180039420  mov     rax, [rcx]
0x180039423  mov     rax, [rax+10h]
0x180039427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003942c  nop
0x18003942d  lea     rcx, [rbp+arg_10]; void *
0x180039431  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180039436  nop
0x180039437  lea     rcx, [rbp+pUnk]; void *
0x18003943b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180039440  mov     rcx, rdi; this
0x180039443  call    ?ServiceStopCleanupObjects@CService@@IEAAJXZ; CService::ServiceStopCleanupObjects(void)
0x180039448  call    cs:__imp_CoUninitialize
0x18003944e  mov     ecx, ebx; dwExitCode
0x180039450  call    cs:__imp_ExitThread
```
