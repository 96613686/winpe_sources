# UbpmTerminate

- ea: `0x180029ad0`
- end: `0x180029c67`
- name: `UbpmTerminate`
- size: `407`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002a7f0`

## callees

- `0x180001008`
- `0x180007460`
- `0x18000a500`
- `0x180017d70`
- `0x180029ad0`
- `0x180029c70`
- `0x18002ad7c`
- `0x180030dc0`
- `0x180036cd4`
- `0x18003bc28`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180029c3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180029c3e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029c19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029c19`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180029c2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180029c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b42`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180029ba7`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180029ba7`

## string_xrefs

- `0x180029bce`: `UninitializeTaskEventsLib(0x%x)`

## pseudocode

```c
int UbpmTerminate()
{
  __int16 v0; // ax
  unsigned int v1; // edx
  int result; // eax
  DWORD v3; // ebx
  _BYTE v4[144]; // [rsp+20h] [rbp-A8h] BYREF

  memset_0(v4, 0, 0x88u);
  UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v4);
  UbpmUnRegisterTriggerConsumers();
  v0 = g_InitializationStatus;
  if ( (g_InitializationStatus & 0x10) != 0 )
  {
    UbpmDisableTaskHostChannelRpcInterface();
    v0 = g_InitializationStatus & 0xFFEF;
    g_InitializationStatus &= ~0x10u;
  }
  if ( (v0 & 8) != 0 )
  {
    if ( g_hLowPowerEpochExited )
    {
      CloseHandle(g_hLowPowerEpochExited);
      v0 = g_InitializationStatus;
    }
    v0 &= ~8u;
    g_InitializationStatus = v0;
  }
  if ( (v0 & 4) != 0 )
  {
    UbpmUtilsTerminate();
    LOBYTE(v0) = g_InitializationStatus & 0xFB;
    g_InitializationStatus &= ~4u;
  }
  if ( (v0 & 2) != 0 )
  {
    UbpmUninitializeConstraints();
    LOBYTE(v0) = g_InitializationStatus & 0xFD;
    g_InitializationStatus &= ~2u;
  }
  if ( (v0 & 0x20) != 0 )
  {
    CrmUnregister(g_CrmRegistrationHandle);
    LOBYTE(v0) = g_InitializationStatus & 0xDF;
    g_InitializationStatus &= ~0x20u;
  }
  if ( (v0 & 1) != 0 )
  {
    TaskEventTrace(L"UninitializeTaskEventsLib(0x%x)", g_hTaskEventManager);
    if ( g_hTaskEventManager )
      EventManager::`scalar deleting destructor'(g_hTaskEventManager, v1);
    g_hTaskEventManager = 0;
    g_InitializationStatus &= ~1u;
  }
  TraceLoggingUnregister_EventUnregister();
  result = WppCleanupUm();
  v3 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    result = TlsSetValue(v3, 0);
    if ( UbpmpLockTrackerId != -1 )
      result = TlsFree(UbpmpLockTrackerId);
  }
  UbpmpLockTrackerId = -1;
  return result;
}

```

## disassembly

```asm
0x180029ad0  push    rbx
0x180029ad2  sub     rsp, 0C0h
0x180029ad9  mov     rax, cs:__security_cookie
0x180029ae0  xor     rax, rsp
0x180029ae3  mov     [rsp+0C8h+var_18], rax
0x180029aeb  xor     edx, edx; Val
0x180029aed  lea     rcx, [rsp+0C8h+var_A8]; void *
0x180029af2  mov     r8d, 88h; Size
0x180029af8  call    memset_0
0x180029afd  lea     rcx, [rsp+0C8h+var_A8]; lpTlsValue
0x180029b02  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x180029b07  call    UbpmUnRegisterTriggerConsumers
0x180029b0c  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029b13  test    al, 10h
0x180029b15  jz      short loc_180029B32
0x180029b17  call    UbpmDisableTaskHostChannelRpcInterface
0x180029b1c  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029b23  mov     ecx, 0FFEFh
0x180029b28  and     ax, cx
0x180029b2b  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029b32  test    al, 8
0x180029b34  jz      short loc_180029B5E
0x180029b36  mov     rcx, cs:?g_hLowPowerEpochExited@@3PEAXEA; hObject
0x180029b3d  test    rcx, rcx
0x180029b40  jz      short loc_180029B4F
0x180029b42  call    cs:__imp_CloseHandle
0x180029b48  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029b4f  mov     ecx, 0FFF7h
0x180029b54  and     ax, cx
0x180029b57  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029b5e  test    al, 4
0x180029b60  jz      short loc_180029B7D
0x180029b62  call    ?UbpmUtilsTerminate@@YAXXZ; UbpmUtilsTerminate(void)
0x180029b67  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029b6e  mov     ecx, 0FFFBh
0x180029b73  and     ax, cx
0x180029b76  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029b7d  test    al, 2
0x180029b7f  jz      short loc_180029B9C
0x180029b81  call    UbpmUninitializeConstraints
0x180029b86  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029b8d  mov     ecx, 0FFFDh
0x180029b92  and     ax, cx
0x180029b95  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029b9c  test    al, 20h
0x180029b9e  jz      short loc_180029BC3
0x180029ba0  mov     rcx, cs:g_CrmRegistrationHandle
0x180029ba7  call    cs:__imp_CrmUnregister
0x180029bad  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180029bb4  mov     ecx, 0FFDFh
0x180029bb9  and     ax, cx
0x180029bbc  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029bc3  test    al, 1
0x180029bc5  jz      short loc_180029C02
0x180029bc7  mov     rdx, cs:g_hTaskEventManager
0x180029bce  lea     rcx, aUninitializeta; "UninitializeTaskEventsLib(0x%x)"
0x180029bd5  call    TaskEventTrace
0x180029bda  mov     rcx, cs:g_hTaskEventManager; this
0x180029be1  test    rcx, rcx
0x180029be4  jz      short loc_180029BEB
0x180029be6  call    ??_GEventManager@@QEAAPEAXI@Z; EventManager::`scalar deleting destructor'(uint)
0x180029beb  mov     cs:g_hTaskEventManager, 0
0x180029bf6  mov     eax, 0FFFEh
0x180029bfb  and     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180029c02  call    TraceLoggingUnregister_EventUnregister
0x180029c07  call    WppCleanupUm
0x180029c0c  mov     ebx, cs:UbpmpLockTrackerId
0x180029c12  cmp     ebx, 0FFFFFFFFh
0x180029c15  jz      short loc_180029C44
0x180029c17  mov     ecx, ebx; dwTlsIndex
0x180029c19  call    cs:__imp_TlsGetValue
0x180029c1f  cmp     qword ptr [rax], 0
0x180029c23  jz      short loc_180029C27
0x180029c25  int     2Ch; Windows NT - assertion failure
0x180029c27  xor     edx, edx; lpTlsValue
0x180029c29  mov     ecx, ebx; dwTlsIndex
0x180029c2b  call    cs:__imp_TlsSetValue
0x180029c31  mov     ebx, cs:UbpmpLockTrackerId
0x180029c37  cmp     ebx, 0FFFFFFFFh
0x180029c3a  jz      short loc_180029C44
0x180029c3c  mov     ecx, ebx; dwTlsIndex
0x180029c3e  call    cs:__imp_TlsFree
0x180029c44  mov     cs:UbpmpLockTrackerId, 0FFFFFFFFh
0x180029c4e  mov     rcx, [rsp+0C8h+var_18]
0x180029c56  xor     rcx, rsp; StackCookie
0x180029c59  call    __security_check_cookie
0x180029c5e  add     rsp, 0C0h
0x180029c65  pop     rbx
0x180029c66  retn
```
