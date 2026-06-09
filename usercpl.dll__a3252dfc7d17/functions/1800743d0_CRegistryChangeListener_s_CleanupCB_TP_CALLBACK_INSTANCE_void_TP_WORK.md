# CRegistryChangeListener::s_CleanupCB(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800743d0`
- end: `0x180074491`
- name: `?s_CleanupCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `193`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000dafc`
- `0x180073e08`
- `0x1800743d0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180074468`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180074468`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074432`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074432`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180074401`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180074401`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800743e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800743e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800743ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800743ec`

## pseudocode

```c
void __fastcall CRegistryChangeListener::s_CleanupCB(
        PTP_CALLBACK_INSTANCE Instance,
        unsigned int *Context,
        PTP_WORK Work)
{
  LPVOID v4; // rcx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)Context + 5), 1);
  CloseThreadpoolWait(*((PTP_WAIT *)Context + 5));
  *((_QWORD *)Context + 5) = 0;
  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, Context[12]);
      v4 = ppv;
      Context[12] = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    CoUninitialize();
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Context + 4, 0xFFFFFFFF) == 1 )
  {
    CRegistryChangeListener::~CRegistryChangeListener((CRegistryChangeListener *)Context);
    operator delete(Context);
  }
}

```

## disassembly

```asm
0x1800743d0  push    rbx
0x1800743d2  sub     rsp, 30h
0x1800743d6  mov     rbx, rdx
0x1800743d9  mov     edx, 1; fCancelPendingCallbacks
0x1800743de  mov     rcx, [rbx+28h]; pwa
0x1800743e2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800743e8  mov     rcx, [rbx+28h]; pwa
0x1800743ec  call    cs:__imp_CloseThreadpoolWait
0x1800743f2  mov     edx, 6; dwCoInit
0x1800743f7  mov     qword ptr [rbx+28h], 0
0x1800743ff  xor     ecx, ecx; pvReserved
0x180074401  call    cs:__imp_CoInitializeEx
0x180074407  test    eax, eax
0x180074409  js      short loc_18007446E
0x18007440b  xor     edx, edx; pUnkOuter
0x18007440d  mov     [rsp+38h+arg_8], 0
0x180074416  lea     rax, [rsp+38h+arg_8]
0x18007441b  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180074422  mov     [rsp+38h+ppv], rax; ppv
0x180074427  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18007442e  lea     r8d, [rdx+1]; dwClsContext
0x180074432  call    cs:__imp_CoCreateInstance
0x180074438  test    eax, eax
0x18007443a  js      short loc_180074468
0x18007443c  mov     rcx, [rsp+38h+arg_8]
0x180074441  mov     edx, [rbx+30h]
0x180074444  mov     rax, [rcx]
0x180074447  mov     rax, [rax+20h]
0x18007444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074450  mov     rcx, [rsp+38h+arg_8]
0x180074455  mov     dword ptr [rbx+30h], 0
0x18007445c  mov     rax, [rcx]
0x18007445f  mov     rax, [rax+10h]
0x180074463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074468  call    cs:__imp_CoUninitialize
0x18007446e  or      eax, 0FFFFFFFFh
0x180074471  lock xadd [rbx+10h], eax
0x180074476  cmp     eax, 1
0x180074479  jnz     short loc_18007448B
0x18007447b  mov     rcx, rbx; this
0x18007447e  call    ??1CRegistryChangeListener@@AEAA@XZ; CRegistryChangeListener::~CRegistryChangeListener(void)
0x180074483  mov     rcx, rbx; lpMem
0x180074486  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007448b  add     rsp, 30h
0x18007448f  pop     rbx
0x180074490  retn
```
