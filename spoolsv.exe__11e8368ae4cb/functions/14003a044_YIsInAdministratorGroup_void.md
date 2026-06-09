# YIsInAdministratorGroup(void)

- ea: `0x14003a044`
- end: `0x14003a0db`
- name: `?YIsInAdministratorGroup@@YAHXZ`
- size: `151`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140023dc4`
- `0x140031fa0`
- `0x1400322c0`
- `0x1400323f0`
- `0x140034a00`

## callees

- `0x140014fc4`
- `0x1400160a0`
- `0x14003a044`
- `0x140057cac`
- `0x140057e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a0b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a0b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003a094`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003a094`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003a061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003a07d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003a061`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003a07d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a0af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a0af`

## string_xrefs

- `0x14003a0c0`: `Failed to open the thread token: %d`

## pseudocode

```c
__int64 YIsInAdministratorGroup(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  void **v2; // r9
  DWORD LastError; // eax
  void *v4; // rdx
  HANDLE v5; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    LastError = SecurityHelper::OpenThreadToken(CurrentThread, 8u, &TokenHandle, v2);
    if ( !LastError )
      goto LABEL_5;
LABEL_7:
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "YIsInAdministratorGroup",
      L"Failed to open the thread token: %d",
      LastError);
    return v0;
  }
  v5 = GetCurrentThread();
  if ( !OpenThreadToken(v5, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_7;
  }
LABEL_5:
  v0 = SecurityHelper::IsInAdministratorGroup(TokenHandle, v4);
  CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x14003a044  push    rbx
0x14003a046  sub     rsp, 20h
0x14003a04a  xor     ebx, ebx
0x14003a04c  mov     [rsp+28h+TokenHandle], rbx
0x14003a051  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14003a058  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14003a05d  test    al, al
0x14003a05f  jz      short loc_14003A07D
0x14003a061  call    cs:__imp_GetCurrentThread
0x14003a067  mov     rcx, rax; ThreadHandle
0x14003a06a  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x14003a06f  lea     edx, [rbx+8]; DesiredAccess
0x14003a072  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14003a077  test    eax, eax
0x14003a079  jnz     short loc_14003A0BD
0x14003a07b  jmp     short loc_14003A09E
0x14003a07d  call    cs:__imp_GetCurrentThread
0x14003a083  mov     edx, 8; DesiredAccess
0x14003a088  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x14003a08d  mov     rcx, rax; ThreadHandle
0x14003a090  lea     r8d, [rdx-7]; OpenAsSelf
0x14003a094  call    cs:__imp_OpenThreadToken
0x14003a09a  test    eax, eax
0x14003a09c  jz      short loc_14003A0B7
0x14003a09e  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x14003a0a3  call    ?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z; SecurityHelper::IsInAdministratorGroup(void *)
0x14003a0a8  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x14003a0ad  mov     ebx, eax
0x14003a0af  call    cs:__imp_CloseHandle
0x14003a0b5  jmp     short loc_14003A0D3
0x14003a0b7  call    cs:__imp_GetLastError
0x14003a0bd  mov     r8d, eax
0x14003a0c0  lea     rdx, aFailedToOpenTh; "Failed to open the thread token: %d"
0x14003a0c7  lea     rcx, aYisinadministr; "YIsInAdministratorGroup"
0x14003a0ce  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003a0d3  mov     eax, ebx
0x14003a0d5  add     rsp, 20h
0x14003a0d9  pop     rbx
0x14003a0da  retn
```
