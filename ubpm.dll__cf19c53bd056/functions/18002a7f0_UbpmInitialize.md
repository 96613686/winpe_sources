# UbpmInitialize

- ea: `0x18002a7f0`
- end: `0x18002a90b`
- name: `UbpmInitialize`
- size: `283`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callees

- `0x180029ad0`
- `0x18002a0cc`
- `0x18002a7f0`
- `0x18002a914`
- `0x18002ab60`
- `0x18002af50`
- `0x180030ac8`
- `0x180030d38`
- `0x180031fd4`
- `0x180036344`
- `0x18003c1e0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18002a892`
- `ntdll!RtlNtStatusToDosError` at `0x18002a892`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002a7f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002a7f9`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002a886`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x18002a886`

## string_xrefs

- `0x18002a873`: `UBPM / Task Scheduler`

## pseudocode

```c
__int64 __fastcall UbpmInitialize(__int64 a1)
{
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  ULONG v4; // eax

  UbpmpLockTrackerId = TlsAlloc();
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  qword_18004CA18 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_Regular;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  qword_18004CA20 = 1;
  WppInitUm();
  g_ScheduleServiceHandle = a1;
  v2 = UbpmInitializeConsumerEventing();
  if ( !v2 )
  {
    g_InitializationStatus |= 1u;
    if ( (unsigned __int8)IsCrmRegisterPresent() )
    {
      v3 = CrmRegister(&g_CrmRegistrationHandle, 302, L"UBPM / Task Scheduler");
      if ( v3 < 0 && (v4 = RtlNtStatusToDosError(v3), (v2 = v4) != 0) )
      {
        if ( v4 != 50 )
          goto LABEL_12;
      }
      else
      {
        g_InitializationStatus |= 0x20u;
      }
    }
    v2 = UbpmInitializeConstraints();
    if ( !v2 )
    {
      g_InitializationStatus |= 2u;
      v2 = UbpmUtilsInitialize();
      if ( !v2 )
      {
        g_InitializationStatus |= 4u;
        UbpmpInitTaskHostServer();
        g_InitializationStatus |= 8u;
        v2 = UbpmEnableTaskHostChannelRpcInterface();
        if ( !v2 )
          g_InitializationStatus |= 0x10u;
      }
    }
  }
LABEL_12:
  UbpmTelemReportServiceStart(v2);
  if ( v2 )
    UbpmTerminate();
  return v2;
}

```

## disassembly

```asm
0x18002a7f0  push    rbx
0x18002a7f2  sub     rsp, 20h
0x18002a7f6  mov     rbx, rcx
0x18002a7f9  call    cs:__imp_TlsAlloc
0x18002a7ff  mov     cs:UbpmpLockTrackerId, eax
0x18002a805  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002a80a  lea     rax, WPP_ThisDir_CTLGUID_Regular
0x18002a811  mov     cs:qword_18004CA18, 0
0x18002a81c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18002a823  lea     rax, WPP_MAIN_CB
0x18002a82a  mov     cs:WPP_GLOBAL_Control, rax
0x18002a831  mov     cs:WPP_MAIN_CB, 0
0x18002a83c  mov     cs:qword_18004CA20, 1
0x18002a847  call    WppInitUm
0x18002a84c  mov     cs:g_ScheduleServiceHandle, rbx
0x18002a853  call    UbpmInitializeConsumerEventing
0x18002a858  mov     ebx, eax
0x18002a85a  test    eax, eax
0x18002a85c  jnz     loc_18002A8F3
0x18002a862  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 1; UBPM_INIT_STATUS g_InitializationStatus
0x18002a86a  call    IsCrmRegisterPresent
0x18002a86f  test    al, al
0x18002a871  jz      short loc_18002A8AD
0x18002a873  lea     r8, aUbpmTaskSchedu; "UBPM / Task Scheduler"
0x18002a87a  mov     edx, 12Eh
0x18002a87f  lea     rcx, g_CrmRegistrationHandle
0x18002a886  call    cs:__imp_CrmRegister
0x18002a88c  test    eax, eax
0x18002a88e  jns     short loc_18002A8A5
0x18002a890  mov     ecx, eax; Status
0x18002a892  call    cs:__imp_RtlNtStatusToDosError
0x18002a898  mov     ebx, eax
0x18002a89a  test    eax, eax
0x18002a89c  jz      short loc_18002A8A5
0x18002a89e  cmp     eax, 32h ; '2'
0x18002a8a1  jz      short loc_18002A8AD
0x18002a8a3  jmp     short loc_18002A8F3
0x18002a8a5  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 20h; UBPM_INIT_STATUS g_InitializationStatus
0x18002a8ad  call    UbpmInitializeConstraints
0x18002a8b2  mov     ebx, eax
0x18002a8b4  test    eax, eax
0x18002a8b6  jnz     short loc_18002A8F3
0x18002a8b8  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 2; UBPM_INIT_STATUS g_InitializationStatus
0x18002a8c0  call    ?UbpmUtilsInitialize@@YAKXZ; UbpmUtilsInitialize(void)
0x18002a8c5  mov     ebx, eax
0x18002a8c7  test    eax, eax
0x18002a8c9  jnz     short loc_18002A8F3
0x18002a8cb  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 4; UBPM_INIT_STATUS g_InitializationStatus
0x18002a8d3  call    UbpmpInitTaskHostServer
0x18002a8d8  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 8; UBPM_INIT_STATUS g_InitializationStatus
0x18002a8e0  call    UbpmEnableTaskHostChannelRpcInterface
0x18002a8e5  mov     ebx, eax
0x18002a8e7  test    eax, eax
0x18002a8e9  jnz     short loc_18002A8F3
0x18002a8eb  or      cs:?g_InitializationStatus@@3TUBPM_INIT_STATUS@@A, 10h; UBPM_INIT_STATUS g_InitializationStatus
0x18002a8f3  mov     ecx, ebx
0x18002a8f5  call    UbpmTelemReportServiceStart
0x18002a8fa  test    ebx, ebx
0x18002a8fc  jz      short loc_18002A903
0x18002a8fe  call    UbpmTerminate
0x18002a903  mov     eax, ebx
0x18002a905  add     rsp, 20h
0x18002a909  pop     rbx
0x18002a90a  retn
```
