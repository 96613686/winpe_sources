# CServiceModule::Shutdown(void)

- ea: `0x180042c0c`
- end: `0x180042d22`
- name: `?Shutdown@CServiceModule@@AEAAXXZ`
- size: `278`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180042eb8`

## callees

- `0x18001ef30`
- `0x180038ce4`
- `0x180042c0c`
- `0x18004e0d8`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042c1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042c1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042cbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180042cbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042c83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042cdf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042c57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042d0b`

## pseudocode

```c
void __fastcall CServiceModule::Shutdown(CServiceModule *this)
{
  DWORD LastError; // eax
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection(&CriticalSection);
  if ( *((_DWORD *)this + 20) )
  {
    *((_DWORD *)this + 20) = 0;
    ppv = 0;
    if ( CoCreateInstance(&CLSID_UPnPRegistrar, 0, 1u, &GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56, (LPVOID *)&ppv) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl[1].AddRef)(ppv);
      ReleaseObj(ppv);
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( *((_DWORD *)this + 21) )
  {
    HrHttpShutdown();
    *((_DWORD *)this + 21) = 0;
  }
  if ( g_hUnregWorkItemEvent )
  {
    while ( g_lUnregDeviceWorkItems > 0 )
    {
      if ( WaitForSingleObject(g_hUnregWorkItemEvent, 0x7D0u) == -1 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids, LastError);
        }
        break;
      }
    }
    CloseHandle(g_hUnregWorkItemEvent);
    g_hUnregWorkItemEvent = 0;
  }
}

```

## disassembly

```asm
0x180042c0c  push    rbx
0x180042c0e  sub     rsp, 30h
0x180042c12  mov     rbx, rcx
0x180042c15  lea     rcx, CriticalSection; lpCriticalSection
0x180042c1c  call    cs:__imp_EnterCriticalSection
0x180042c22  mov     eax, [rbx+50h]
0x180042c25  test    eax, eax
0x180042c27  jz      short loc_180042C7C
0x180042c29  xor     edx, edx; pUnkOuter
0x180042c2b  mov     dword ptr [rbx+50h], 0
0x180042c32  lea     rax, [rsp+38h+arg_0]
0x180042c37  mov     [rsp+38h+arg_0], 0
0x180042c40  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x180042c47  mov     [rsp+38h+ppv], rax; ppv
0x180042c4c  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180042c53  lea     r8d, [rdx+1]; dwClsContext
0x180042c57  call    cs:__imp_CoCreateInstance
0x180042c5d  test    eax, eax
0x180042c5f  js      short loc_180042C7C
0x180042c61  mov     rcx, [rsp+38h+arg_0]
0x180042c66  mov     rax, [rcx]
0x180042c69  mov     rax, [rax+20h]
0x180042c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c72  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180042c77  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180042c7c  lea     rcx, CriticalSection; lpCriticalSection
0x180042c83  call    cs:__imp_LeaveCriticalSection
0x180042c89  cmp     dword ptr [rbx+54h], 0
0x180042c8d  jz      short loc_180042C9B
0x180042c8f  call    ?HrHttpShutdown@@YAJXZ; HrHttpShutdown(void)
0x180042c94  mov     dword ptr [rbx+54h], 0
0x180042c9b  cmp     cs:?g_hUnregWorkItemEvent@@3PEAXEA, 0; void * g_hUnregWorkItemEvent
0x180042ca3  jz      short loc_180042D1C
0x180042ca5  mov     eax, cs:?g_lUnregDeviceWorkItems@@3JC; long volatile g_lUnregDeviceWorkItems
0x180042cab  test    eax, eax
0x180042cad  jle     short loc_180042D04
0x180042caf  mov     rcx, cs:?g_hUnregWorkItemEvent@@3PEAXEA; hHandle
0x180042cb6  mov     edx, 7D0h; dwMilliseconds
0x180042cbb  call    cs:__imp_WaitForSingleObject
0x180042cc1  cmp     eax, 0FFFFFFFFh
0x180042cc4  jnz     short loc_180042CA5
0x180042cc6  mov     rax, cs:WPP_GLOBAL_Control
0x180042ccd  lea     rcx, WPP_GLOBAL_Control
0x180042cd4  cmp     rax, rcx
0x180042cd7  jz      short loc_180042D04
0x180042cd9  test    byte ptr [rax+1Ch], 1
0x180042cdd  jz      short loc_180042D04
0x180042cdf  call    cs:__imp_GetLastError
0x180042ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180042cec  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180042cf3  mov     edx, 22h ; '"'
0x180042cf8  mov     r9d, eax
0x180042cfb  mov     rcx, [rcx+10h]
0x180042cff  call    WPP_SF_d
0x180042d04  mov     rcx, cs:?g_hUnregWorkItemEvent@@3PEAXEA; hObject
0x180042d0b  call    cs:__imp_CloseHandle
0x180042d11  mov     cs:?g_hUnregWorkItemEvent@@3PEAXEA, 0; void * g_hUnregWorkItemEvent
0x180042d1c  add     rsp, 30h
0x180042d20  pop     rbx
0x180042d21  retn
```
