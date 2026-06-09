# SvcHostMain

- ea: `0x140002cb0`
- end: `0x140002d6f`
- name: `SvcHostMain`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002ca0`

## callees

- `0x140001010`
- `0x140001970`
- `0x140002300`
- `0x140002cb0`
- `0x140002d90`
- `0x140004720`
- `0x1400049f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002d62`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002d62`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002d29`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002d29`
- `api-ms-win-service-private-l1-1-3!I_RegisterSvchostNotificationCallback` at `0x140002cd9`
- `api-ms-win-service-private-l1-1-3!I_RegisterSvchostNotificationCallback` at `0x140002cd9`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140002ce8`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140002ce8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002d02`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002d02`

## pseudocode

```c
void __noreturn SvcHostMain()
{
  const SERVICE_TABLE_ENTRYW *v0; // rbx
  __int64 v1; // rcx
  LPWSTR CommandLineW; // rax
  int v3; // r8d
  int v4; // r9d
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v6[16]; // [rsp+50h] [rbp-28h] BYREF

  v0 = (const SERVICE_TABLE_ENTRYW *)InitializeSvcHostLib();
  if ( v0 )
  {
    I_RegisterSvchostNotificationCallback(&SvcHostNotificationCallback);
    StartServiceCtrlDispatcherW(v0);
    if ( ShouldCoUninit )
    {
      WaitForServiceDllsToUnload();
      CoUninitialize();
    }
  }
  DeInitializeServiceMemoryTracing();
  if ( (unsigned int)dword_14000F000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(v1, 0) )
    {
      CommandLineW = GetCommandLineW();
      tlgCreate1Sz_wchar_t(v6, CommandLineW);
      tlgWriteTransfer_EventWriteTransfer((int)&v5, (int)&dword_14000B8D1, v3, v4, 3u, &v5);
    }
  }
  ExitProcess(0);
}

```

## disassembly

```asm
0x140002cb0  push    rbx
0x140002cb2  sub     rsp, 70h
0x140002cb6  mov     rax, cs:__security_cookie
0x140002cbd  xor     rax, rsp
0x140002cc0  mov     [rsp+78h+var_18], rax
0x140002cc5  call    InitializeSvcHostLib
0x140002cca  mov     rbx, rax
0x140002ccd  test    rax, rax
0x140002cd0  jz      short loc_140002D0E
0x140002cd2  lea     rcx, SvcHostNotificationCallback
0x140002cd9  call    cs:__imp_I_RegisterSvchostNotificationCallback
0x140002ce0  nop     dword ptr [rax+rax+00h]
0x140002ce5  mov     rcx, rbx; lpServiceStartTable
0x140002ce8  call    cs:__imp_StartServiceCtrlDispatcherW
0x140002cef  nop     dword ptr [rax+rax+00h]
0x140002cf4  cmp     cs:ShouldCoUninit, 0
0x140002cfb  jz      short loc_140002D0E
0x140002cfd  call    WaitForServiceDllsToUnload
0x140002d02  call    cs:__imp_CoUninitialize
0x140002d09  nop     dword ptr [rax+rax+00h]
0x140002d0e  call    DeInitializeServiceMemoryTracing
0x140002d13  mov     eax, cs:dword_14000F000
0x140002d19  cmp     eax, 5
0x140002d1c  jbe     short loc_140002D60
0x140002d1e  xor     edx, edx
0x140002d20  call    _tlgKeywordOn
0x140002d25  test    al, al
0x140002d27  jz      short loc_140002D60
0x140002d29  call    cs:__imp_GetCommandLineW
0x140002d30  nop     dword ptr [rax+rax+00h]
0x140002d35  mov     rdx, rax
0x140002d38  lea     rcx, [rsp+78h+var_28]
0x140002d3d  call    _tlgCreate1Sz_wchar_t
0x140002d42  lea     rcx, [rsp+78h+var_48]; int
0x140002d47  mov     [rsp+78h+var_50], rcx; PEVENT_DATA_DESCRIPTOR
0x140002d4c  lea     rdx, dword_14000B8D1; int
0x140002d53  mov     [rsp+78h+var_58], 3; ULONG
0x140002d5b  call    _tlgWriteTransfer_EventWriteTransfer
0x140002d60  xor     ecx, ecx; uExitCode
0x140002d62  call    cs:__imp_ExitProcess
```
