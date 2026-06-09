# PrvRevertToPrinterSelf

- ea: `0x180001d08`
- end: `0x180001db1`
- name: `PrvRevertToPrinterSelf`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x180001d08`
- `0x18000bb44`
- `0x180014d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001d8e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001d5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001d5a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d68`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001d68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d43`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001da1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001da1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001d77`

## pseudocode

```c
HANDLE PrvRevertToPrinterSelf()
{
  HANDLE CurrentThread; // rax
  void **v1; // r9
  DWORD LastError; // eax
  HANDLE v3; // rax
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    LastError = SecurityHelper::OpenThreadToken(CurrentThread, 4u, &TokenHandle, v1);
    if ( LastError )
    {
LABEL_8:
      if ( LastError == 1008 )
      {
        CurrentProcess = GetCurrentProcess();
        OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
      }
      return TokenHandle;
    }
  }
  else
  {
    v3 = GetCurrentThread();
    if ( !OpenThreadToken(v3, 4u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      goto LABEL_8;
    }
  }
  if ( !SetThreadToken(0, 0) )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x180001d08  sub     rsp, 28h
0x180001d0c  mov     [rsp+28h+TokenHandle], 0
0x180001d15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180001d1c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180001d21  test    al, al
0x180001d23  jz      short loc_180001D43
0x180001d25  call    cs:__imp_GetCurrentThread
0x180001d2b  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180001d30  mov     edx, 4; DesiredAccess
0x180001d35  mov     rcx, rax; ThreadHandle
0x180001d38  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x180001d3d  test    eax, eax
0x180001d3f  jz      short loc_180001D64
0x180001d41  jmp     short loc_180001D87
0x180001d43  call    cs:__imp_GetCurrentThread
0x180001d49  mov     edx, 4; DesiredAccess
0x180001d4e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180001d53  mov     rcx, rax; ThreadHandle
0x180001d56  lea     r8d, [rdx-3]; OpenAsSelf
0x180001d5a  call    cs:__imp_OpenThreadToken
0x180001d60  test    eax, eax
0x180001d62  jz      short loc_180001D81
0x180001d64  xor     edx, edx; Token
0x180001d66  xor     ecx, ecx; Thread
0x180001d68  call    cs:__imp_SetThreadToken
0x180001d6e  test    eax, eax
0x180001d70  jnz     short loc_180001DA7
0x180001d72  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180001d77  call    cs:__imp_CloseHandle
0x180001d7d  xor     eax, eax
0x180001d7f  jmp     short loc_180001DAC
0x180001d81  call    cs:__imp_GetLastError
0x180001d87  cmp     eax, 3F0h
0x180001d8c  jnz     short loc_180001DA7
0x180001d8e  call    cs:__imp_GetCurrentProcess
0x180001d94  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180001d99  mov     edx, 8; DesiredAccess
0x180001d9e  mov     rcx, rax; ProcessHandle
0x180001da1  call    cs:__imp_OpenProcessToken
0x180001da7  mov     rax, [rsp+28h+TokenHandle]
0x180001dac  add     rsp, 28h
0x180001db0  retn
```
