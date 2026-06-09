# PrvRevertToPrinterSelf

- ea: `0x180001d38`
- end: `0x180001e12`
- name: `PrvRevertToPrinterSelf`
- size: `218`
- prototype: `HANDLE()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d00`

## callees

- `0x180001d38`
- `0x18000c4c0`
- `0x180016704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001de2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180001de2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001d96`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001d96`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001daa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001daa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001d79`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001dfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180001dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001dbf`

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
0x180001d38  sub     rsp, 28h
0x180001d3c  mov     [rsp+28h+TokenHandle], 0
0x180001d45  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180001d4c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180001d51  test    al, al
0x180001d53  jz      short loc_180001D79
0x180001d55  call    cs:__imp_GetCurrentThread
0x180001d5c  nop     dword ptr [rax+rax+00h]
0x180001d61  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180001d66  mov     edx, 4; DesiredAccess
0x180001d6b  mov     rcx, rax; ThreadHandle
0x180001d6e  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x180001d73  test    eax, eax
0x180001d75  jz      short loc_180001DA6
0x180001d77  jmp     short loc_180001DDB
0x180001d79  call    cs:__imp_GetCurrentThread
0x180001d80  nop     dword ptr [rax+rax+00h]
0x180001d85  mov     edx, 4; DesiredAccess
0x180001d8a  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180001d8f  mov     rcx, rax; ThreadHandle
0x180001d92  lea     r8d, [rdx-3]; OpenAsSelf
0x180001d96  call    cs:__imp_OpenThreadToken
0x180001d9d  nop     dword ptr [rax+rax+00h]
0x180001da2  test    eax, eax
0x180001da4  jz      short loc_180001DCF
0x180001da6  xor     edx, edx; Token
0x180001da8  xor     ecx, ecx; Thread
0x180001daa  call    cs:__imp_SetThreadToken
0x180001db1  nop     dword ptr [rax+rax+00h]
0x180001db6  test    eax, eax
0x180001db8  jnz     short loc_180001E07
0x180001dba  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180001dbf  call    cs:__imp_CloseHandle
0x180001dc6  nop     dword ptr [rax+rax+00h]
0x180001dcb  xor     eax, eax
0x180001dcd  jmp     short loc_180001E0C
0x180001dcf  call    cs:__imp_GetLastError
0x180001dd6  nop     dword ptr [rax+rax+00h]
0x180001ddb  cmp     eax, 3F0h
0x180001de0  jnz     short loc_180001E07
0x180001de2  call    cs:__imp_GetCurrentProcess
0x180001de9  nop     dword ptr [rax+rax+00h]
0x180001dee  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180001df3  mov     edx, 8; DesiredAccess
0x180001df8  mov     rcx, rax; ProcessHandle
0x180001dfb  call    cs:__imp_OpenProcessToken
0x180001e02  nop     dword ptr [rax+rax+00h]
0x180001e07  mov     rax, [rsp+28h+TokenHandle]
0x180001e0c  add     rsp, 28h
0x180001e10  retn
```
