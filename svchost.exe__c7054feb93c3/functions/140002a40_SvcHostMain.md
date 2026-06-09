# SvcHostMain

- ea: `0x140002a40`
- end: `0x140002ae1`
- name: `SvcHostMain`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140002a30`

## callees

- `0x140001010`
- `0x1400018d0`
- `0x1400021c0`
- `0x140002a40`
- `0x140002b00`
- `0x140004390`
- `0x140004650`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002ada`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140002ada`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002aa7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140002aa7`
- `api-ms-win-service-private-l1-1-3!I_RegisterSvchostNotificationCallback` at `0x140002a69`
- `api-ms-win-service-private-l1-1-3!I_RegisterSvchostNotificationCallback` at `0x140002a69`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140002a72`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140002a72`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002a86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140002a86`

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
      tlgWriteTransfer_EventWriteTransfer((int)&v5, (int)&byte_14000B8D1, v3, v4, 3u, &v5);
    }
  }
  ExitProcess(0);
}

```

## disassembly

```asm
0x140002a40  push    rbx
0x140002a42  sub     rsp, 70h
0x140002a46  mov     rax, cs:__security_cookie
0x140002a4d  xor     rax, rsp
0x140002a50  mov     [rsp+78h+var_18], rax
0x140002a55  call    InitializeSvcHostLib
0x140002a5a  mov     rbx, rax
0x140002a5d  test    rax, rax
0x140002a60  jz      short loc_140002A8C
0x140002a62  lea     rcx, SvcHostNotificationCallback
0x140002a69  call    cs:__imp_I_RegisterSvchostNotificationCallback
0x140002a6f  mov     rcx, rbx; lpServiceStartTable
0x140002a72  call    cs:__imp_StartServiceCtrlDispatcherW
0x140002a78  cmp     cs:ShouldCoUninit, 0
0x140002a7f  jz      short loc_140002A8C
0x140002a81  call    WaitForServiceDllsToUnload
0x140002a86  call    cs:__imp_CoUninitialize
0x140002a8c  call    DeInitializeServiceMemoryTracing
0x140002a91  mov     eax, cs:dword_14000F000
0x140002a97  cmp     eax, 5
0x140002a9a  jbe     short loc_140002AD8
0x140002a9c  xor     edx, edx
0x140002a9e  call    _tlgKeywordOn
0x140002aa3  test    al, al
0x140002aa5  jz      short loc_140002AD8
0x140002aa7  call    cs:__imp_GetCommandLineW
0x140002aad  mov     rdx, rax
0x140002ab0  lea     rcx, [rsp+78h+var_28]
0x140002ab5  call    _tlgCreate1Sz_wchar_t
0x140002aba  lea     rcx, [rsp+78h+var_48]; int
0x140002abf  mov     [rsp+78h+var_50], rcx; PEVENT_DATA_DESCRIPTOR
0x140002ac4  lea     rdx, byte_14000B8D1; int
0x140002acb  mov     [rsp+78h+var_58], 3; ULONG
0x140002ad3  call    _tlgWriteTransfer_EventWriteTransfer
0x140002ad8  xor     ecx, ecx; uExitCode
0x140002ada  call    cs:__imp_ExitProcess
```
