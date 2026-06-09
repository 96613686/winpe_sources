# YIsInAdministratorGroup(void)

- ea: `0x14003d53c`
- end: `0x14003d5f2`
- name: `?YIsInAdministratorGroup@@YAHXZ`
- size: `182`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140025dac`
- `0x140034890`
- `0x140034bc0`
- `0x140034d10`
- `0x140037630`

## callees

- `0x140016314`
- `0x14001748c`
- `0x14003d53c`
- `0x14005d330`
- `0x14005d4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d5c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003d598`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003d598`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d57b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d5b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d5b9`

## string_xrefs

- `0x14003d5d6`: `Failed to open the thread token: %d`

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
0x14003d53c  push    rbx
0x14003d53e  sub     rsp, 20h
0x14003d542  xor     ebx, ebx
0x14003d544  mov     [rsp+28h+TokenHandle], rbx
0x14003d549  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14003d550  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14003d555  test    al, al
0x14003d557  jz      short loc_14003D57B
0x14003d559  call    cs:__imp_GetCurrentThread
0x14003d560  nop     dword ptr [rax+rax+00h]
0x14003d565  mov     rcx, rax; ThreadHandle
0x14003d568  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x14003d56d  lea     edx, [rbx+8]; DesiredAccess
0x14003d570  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14003d575  test    eax, eax
0x14003d577  jnz     short loc_14003D5D3
0x14003d579  jmp     short loc_14003D5A8
0x14003d57b  call    cs:__imp_GetCurrentThread
0x14003d582  nop     dword ptr [rax+rax+00h]
0x14003d587  mov     edx, 8; DesiredAccess
0x14003d58c  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x14003d591  mov     rcx, rax; ThreadHandle
0x14003d594  lea     r8d, [rdx-7]; OpenAsSelf
0x14003d598  call    cs:__imp_OpenThreadToken
0x14003d59f  nop     dword ptr [rax+rax+00h]
0x14003d5a4  test    eax, eax
0x14003d5a6  jz      short loc_14003D5C7
0x14003d5a8  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x14003d5ad  call    ?IsInAdministratorGroup@SecurityHelper@@YAHPEAX@Z; SecurityHelper::IsInAdministratorGroup(void *)
0x14003d5b2  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x14003d5b7  mov     ebx, eax
0x14003d5b9  call    cs:__imp_CloseHandle
0x14003d5c0  nop     dword ptr [rax+rax+00h]
0x14003d5c5  jmp     short loc_14003D5E9
0x14003d5c7  call    cs:__imp_GetLastError
0x14003d5ce  nop     dword ptr [rax+rax+00h]
0x14003d5d3  mov     r8d, eax
0x14003d5d6  lea     rdx, aFailedToOpenTh; "Failed to open the thread token: %d"
0x14003d5dd  lea     rcx, aYisinadministr; "YIsInAdministratorGroup"
0x14003d5e4  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003d5e9  mov     eax, ebx
0x14003d5eb  add     rsp, 20h
0x14003d5ef  pop     rbx
0x14003d5f0  retn
```
