# UbpmTerminate

- ea: `0x180001880`
- end: `0x180001a36`
- name: `UbpmTerminate`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002c420`

## callees

- `0x180001008`
- `0x180001880`
- `0x180001a3c`
- `0x180001dc0`
- `0x180007e9c`
- `0x1800101a0`
- `0x18002ca84`
- `0x1800330b4`
- `0x180039314`
- `0x18003e4e0`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180001a06`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180001a06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800019d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800019d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800019ed`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800019ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018f2`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18000195d`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18000195d`

## string_xrefs

- `0x18000198a`: `UninitializeTaskEventsLib(0x%x)`

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
0x180001880  push    rbx
0x180001882  sub     rsp, 0C0h
0x180001889  mov     rax, cs:__security_cookie
0x180001890  xor     rax, rsp
0x180001893  mov     [rsp+0C8h+var_18], rax
0x18000189b  xor     edx, edx; Val
0x18000189d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800018a2  mov     r8d, 88h; Size
0x1800018a8  call    memset_0
0x1800018ad  lea     rcx, [rsp+0C8h+var_A8]; lpTlsValue
0x1800018b2  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x1800018b7  call    UbpmUnRegisterTriggerConsumers
0x1800018bc  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x1800018c3  test    al, 10h
0x1800018c5  jz      short loc_1800018E2
0x1800018c7  call    UbpmDisableTaskHostChannelRpcInterface
0x1800018cc  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x1800018d3  mov     ecx, 0FFEFh
0x1800018d8  and     ax, cx
0x1800018db  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x1800018e2  test    al, 8
0x1800018e4  jz      short loc_180001914
0x1800018e6  mov     rcx, cs:?g_hLowPowerEpochExited@@3PEAXEA; hObject
0x1800018ed  test    rcx, rcx
0x1800018f0  jz      short loc_180001905
0x1800018f2  call    cs:__imp_CloseHandle
0x1800018f9  nop     dword ptr [rax+rax+00h]
0x1800018fe  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180001905  mov     ecx, 0FFF7h
0x18000190a  and     ax, cx
0x18000190d  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180001914  test    al, 4
0x180001916  jz      short loc_180001933
0x180001918  call    ?UbpmUtilsTerminate@@YAXXZ; UbpmUtilsTerminate(void)
0x18000191d  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180001924  mov     ecx, 0FFFBh
0x180001929  and     ax, cx
0x18000192c  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180001933  test    al, 2
0x180001935  jz      short loc_180001952
0x180001937  call    UbpmUninitializeConstraints
0x18000193c  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180001943  mov     ecx, 0FFFDh
0x180001948  and     ax, cx
0x18000194b  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x180001952  test    al, 20h
0x180001954  jz      short loc_18000197F
0x180001956  mov     rcx, cs:g_CrmRegistrationHandle
0x18000195d  call    cs:__imp_CrmUnregister
0x180001964  nop     dword ptr [rax+rax+00h]
0x180001969  movzx   eax, cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A; UBPM_INIT_STATUS g_InitializationStatus
0x180001970  mov     ecx, 0FFDFh
0x180001975  and     ax, cx
0x180001978  mov     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x18000197f  test    al, 1
0x180001981  jz      short loc_1800019BE
0x180001983  mov     rdx, cs:g_hTaskEventManager
0x18000198a  lea     rcx, aUninitializeta; "UninitializeTaskEventsLib(0x%x)"
0x180001991  call    TaskEventTrace
0x180001996  mov     rcx, cs:g_hTaskEventManager; this
0x18000199d  test    rcx, rcx
0x1800019a0  jz      short loc_1800019A7
0x1800019a2  call    ??_GEventManager@@QEAAPEAXI@Z; EventManager::`scalar deleting destructor'(uint)
0x1800019a7  mov     cs:g_hTaskEventManager, 0
0x1800019b2  mov     eax, 0FFFEh
0x1800019b7  and     cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, ax; UBPM_INIT_STATUS g_InitializationStatus
0x1800019be  call    TraceLoggingUnregister_EventUnregister
0x1800019c3  call    WppCleanupUm
0x1800019c8  mov     ebx, cs:UbpmpLockTrackerId
0x1800019ce  cmp     ebx, 0FFFFFFFFh
0x1800019d1  jz      short loc_180001A12
0x1800019d3  mov     ecx, ebx; dwTlsIndex
0x1800019d5  call    cs:__imp_TlsGetValue
0x1800019dc  nop     dword ptr [rax+rax+00h]
0x1800019e1  cmp     qword ptr [rax], 0
0x1800019e5  jz      short loc_1800019E9
0x1800019e7  int     2Ch; Windows NT - assertion failure
0x1800019e9  xor     edx, edx; lpTlsValue
0x1800019eb  mov     ecx, ebx; dwTlsIndex
0x1800019ed  call    cs:__imp_TlsSetValue
0x1800019f4  nop     dword ptr [rax+rax+00h]
0x1800019f9  mov     ebx, cs:UbpmpLockTrackerId
0x1800019ff  cmp     ebx, 0FFFFFFFFh
0x180001a02  jz      short loc_180001A12
0x180001a04  mov     ecx, ebx; dwTlsIndex
0x180001a06  call    cs:__imp_TlsFree
0x180001a0d  nop     dword ptr [rax+rax+00h]
0x180001a12  mov     cs:UbpmpLockTrackerId, 0FFFFFFFFh
0x180001a1c  mov     rcx, [rsp+0C8h+var_18]
0x180001a24  xor     rcx, rsp; StackCookie
0x180001a27  call    __security_check_cookie
0x180001a2c  add     rsp, 0C0h
0x180001a33  pop     rbx
0x180001a34  retn
```
