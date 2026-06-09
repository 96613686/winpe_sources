# CServiceModule::Shutdown(void)

- ea: `0x180045600`
- end: `0x18004573f`
- name: `?Shutdown@CServiceModule@@AEAAXXZ`
- size: `319`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800458e0`

## callees

- `0x180014038`
- `0x18003b1cc`
- `0x180045600`
- `0x1800515a0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045610`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800456c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800456c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045651`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045651`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045721`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045721`

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
0x180045600  push    rbx
0x180045602  sub     rsp, 30h
0x180045606  mov     rbx, rcx
0x180045609  lea     rcx, CriticalSection; lpCriticalSection
0x180045610  call    cs:__imp_EnterCriticalSection
0x180045617  nop     dword ptr [rax+rax+00h]
0x18004561c  mov     eax, [rbx+50h]
0x18004561f  test    eax, eax
0x180045621  jz      short loc_18004567C
0x180045623  xor     edx, edx; pUnkOuter
0x180045625  mov     dword ptr [rbx+50h], 0
0x18004562c  lea     rax, [rsp+38h+arg_0]
0x180045631  mov     [rsp+38h+arg_0], 0
0x18004563a  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x180045641  mov     [rsp+38h+ppv], rax; ppv
0x180045646  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x18004564d  lea     r8d, [rdx+1]; dwClsContext
0x180045651  call    cs:__imp_CoCreateInstance
0x180045658  nop     dword ptr [rax+rax+00h]
0x18004565d  test    eax, eax
0x18004565f  js      short loc_18004567C
0x180045661  mov     rcx, [rsp+38h+arg_0]
0x180045666  mov     rax, [rcx]
0x180045669  mov     rax, [rax+20h]
0x18004566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045672  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180045677  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18004567c  lea     rcx, CriticalSection; lpCriticalSection
0x180045683  call    cs:__imp_LeaveCriticalSection
0x18004568a  nop     dword ptr [rax+rax+00h]
0x18004568f  cmp     dword ptr [rbx+54h], 0
0x180045693  jz      short loc_1800456A1
0x180045695  call    ?HrHttpShutdown@@YAJXZ; HrHttpShutdown(void)
0x18004569a  mov     dword ptr [rbx+54h], 0
0x1800456a1  cmp     cs:?g_hUnregWorkItemEvent@@3PEAXEA, 0; void * g_hUnregWorkItemEvent
0x1800456a9  jz      loc_180045738
0x1800456af  mov     eax, cs:?g_lUnregDeviceWorkItems@@3JC; long volatile g_lUnregDeviceWorkItems
0x1800456b5  test    eax, eax
0x1800456b7  jle     short loc_18004571A
0x1800456b9  mov     rcx, cs:?g_hUnregWorkItemEvent@@3PEAXEA; hHandle
0x1800456c0  mov     edx, 7D0h; dwMilliseconds
0x1800456c5  call    cs:__imp_WaitForSingleObject
0x1800456cc  nop     dword ptr [rax+rax+00h]
0x1800456d1  cmp     eax, 0FFFFFFFFh
0x1800456d4  jnz     short loc_1800456AF
0x1800456d6  mov     rax, cs:WPP_GLOBAL_Control
0x1800456dd  lea     rcx, WPP_GLOBAL_Control
0x1800456e4  cmp     rax, rcx
0x1800456e7  jz      short loc_18004571A
0x1800456e9  test    byte ptr [rax+1Ch], 1
0x1800456ed  jz      short loc_18004571A
0x1800456ef  call    cs:__imp_GetLastError
0x1800456f6  nop     dword ptr [rax+rax+00h]
0x1800456fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180045702  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x180045709  mov     edx, 22h ; '"'
0x18004570e  mov     r9d, eax
0x180045711  mov     rcx, [rcx+10h]
0x180045715  call    WPP_SF_d
0x18004571a  mov     rcx, cs:?g_hUnregWorkItemEvent@@3PEAXEA; hObject
0x180045721  call    cs:__imp_CloseHandle
0x180045728  nop     dword ptr [rax+rax+00h]
0x18004572d  mov     cs:?g_hUnregWorkItemEvent@@3PEAXEA, 0; void * g_hUnregWorkItemEvent
0x180045738  add     rsp, 30h
0x18004573c  pop     rbx
0x18004573d  retn
```
