# CService::MiscThread(void)

- ea: `0x18003b338`
- end: `0x18003b4bb`
- name: `?MiscThread@CService@@IEAAJXZ`
- size: `387`
- prototype: `void __fastcall __noreturn(CService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c2d0`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x18002558c`
- `0x18003a520`
- `0x18003b338`
- `0x18003b8ec`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b39d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003b39d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b38a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003b38a`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003b4ae`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003b4ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003b4a0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003b4a0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003b354`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18003b354`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18003b43e`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18003b450`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18003b43e`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18003b450`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18003b3b8`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18003b3b8`

## string_xrefs

- `0x18003b366`: `CService::MiscThread`
- `0x18003b370`: `CComUtils::CoInitialize failed: 0x%x in %s`

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
    if ( dword_180131BA8 )
    {
      CoRevokeClassObject(dwRegister);
      dword_180131BA8 = 0;
    }
    SmartPtr<ITerminal>::operator=(&qword_180131BB0, 0);
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
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v8);
    }
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&pUnk);
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
0x18003b338  mov     [rsp-8+arg_0], rbx
0x18003b33d  mov     [rsp-8+arg_18], rdi
0x18003b342  push    rbp
0x18003b343  mov     rbp, rsp
0x18003b346  sub     rsp, 30h
0x18003b34a  mov     rdi, rcx
0x18003b34d  mov     edx, 4; dwCoInit
0x18003b352  xor     ecx, ecx; pvReserved
0x18003b354  call    cs:__imp_CoInitializeEx
0x18003b35b  nop     dword ptr [rax+rax+00h]
0x18003b360  mov     ebx, eax
0x18003b362  test    eax, eax
0x18003b364  jns     short loc_18003B386
0x18003b366  lea     r9, aCserviceMiscth; "CService::MiscThread"
0x18003b36d  mov     r8d, eax
0x18003b370  lea     rdx, aCcomutilsCoini; "CComUtils::CoInitialize failed: 0x%x in"...
0x18003b377  mov     ecx, 8; int
0x18003b37c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003b381  jmp     loc_18003B4AC
0x18003b386  mov     rcx, [rdi+48h]; hEvent
0x18003b38a  call    cs:__imp_SetEvent
0x18003b391  nop     dword ptr [rax+rax+00h]
0x18003b396  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003b399  mov     rcx, [rdi+58h]; hHandle
0x18003b39d  call    cs:__imp_WaitForSingleObject
0x18003b3a4  nop     dword ptr [rax+rax+00h]
0x18003b3a9  cmp     cs:dword_180131BA8, 0
0x18003b3b0  jz      short loc_18003B3CE
0x18003b3b2  mov     ecx, cs:dwRegister; dwRegister
0x18003b3b8  call    cs:__imp_CoRevokeClassObject
0x18003b3bf  nop     dword ptr [rax+rax+00h]
0x18003b3c4  mov     cs:dword_180131BA8, 0
0x18003b3ce  xor     edx, edx
0x18003b3d0  lea     rcx, qword_180131BB0
0x18003b3d7  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18003b3dc  mov     [rbp+pUnk], 0
0x18003b3e4  lea     r9, [rbp+pUnk]; void **
0x18003b3e8  lea     rdx, CLSID_RemoteConnectionManager; struct _GUID *
0x18003b3ef  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18003b3f4  test    eax, eax
0x18003b3f6  js      loc_18003B48F
0x18003b3fc  mov     [rbp+arg_10], 0
0x18003b404  mov     rcx, [rbp+pUnk]
0x18003b408  mov     rax, [rcx]
0x18003b40b  lea     r9, [rbp+arg_10]
0x18003b40f  lea     r8, IID_IConnectionManager
0x18003b416  xor     edx, edx
0x18003b418  mov     rax, [rax+18h]
0x18003b41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b421  test    eax, eax
0x18003b423  js      short loc_18003B467
0x18003b425  mov     rcx, [rbp+arg_10]
0x18003b429  mov     rax, [rcx]
0x18003b42c  mov     rax, [rax+0C8h]
0x18003b433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b438  xor     edx, edx; dwReserved
0x18003b43a  mov     rcx, [rbp+pUnk]; pUnk
0x18003b43e  call    cs:__imp_CoDisconnectObject
0x18003b445  nop     dword ptr [rax+rax+00h]
0x18003b44a  xor     edx, edx; dwReserved
0x18003b44c  mov     rcx, [rbp+arg_10]; pUnk
0x18003b450  call    cs:__imp_CoDisconnectObject
0x18003b457  nop     dword ptr [rax+rax+00h]
0x18003b45c  xor     edx, edx
0x18003b45e  lea     rcx, [rbp+arg_10]
0x18003b462  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18003b467  mov     rcx, [rbp+pUnk]
0x18003b46b  mov     [rbp+pUnk], 0
0x18003b473  test    rcx, rcx
0x18003b476  jz      short loc_18003B485
0x18003b478  mov     rax, [rcx]
0x18003b47b  mov     rax, [rax+10h]
0x18003b47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b484  nop
0x18003b485  lea     rcx, [rbp+arg_10]; void *
0x18003b489  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003b48e  nop
0x18003b48f  lea     rcx, [rbp+pUnk]; void *
0x18003b493  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18003b498  mov     rcx, rdi; this
0x18003b49b  call    ?ServiceStopCleanupObjects@CService@@IEAAJXZ; CService::ServiceStopCleanupObjects(void)
0x18003b4a0  call    cs:__imp_CoUninitialize
0x18003b4a7  nop     dword ptr [rax+rax+00h]
0x18003b4ac  mov     ecx, ebx; dwExitCode
0x18003b4ae  call    cs:__imp_ExitThread
```
