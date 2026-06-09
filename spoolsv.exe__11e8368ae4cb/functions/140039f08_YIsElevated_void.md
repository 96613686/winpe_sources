# YIsElevated(void)

- ea: `0x140039f08`
- end: `0x14003a03e`
- name: `?YIsElevated@@YAHXZ`
- size: `310`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400323f0`

## callees

- `0x140014fc4`
- `0x1400160a0`
- `0x140039f08`
- `0x140057e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039fd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003a009`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140039ffb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140039ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140039f2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140039fe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140039f2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140039fe3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003a02e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140039f6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140039fb1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140039f6e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140039fb1`

## string_xrefs

- `0x140039fcb`: `GetTokenInformation failed for TokenElevation: %d`
- `0x140039fda`: `GetTokenInformation failed for TokenElevationType: %d`
- `0x14003a00f`: `Failed to open the thread token: %d`

## pseudocode

```c
__int64 YIsElevated(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentThread; // rax
  void **v2; // r9
  DWORD LastError; // eax
  DWORD v4; // eax
  DWORD v5; // eax
  HANDLE v6; // rax
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+28h] BYREF
  int v10; // [rsp+60h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  v0 = 0;
  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    CurrentThread = GetCurrentThread();
    LastError = SecurityHelper::OpenThreadToken(CurrentThread, 8u, &TokenHandle, v2);
    if ( !LastError )
      goto LABEL_3;
LABEL_14:
    SpoolerServiceTelemetry::WriteDbgTraceError("YIsElevated", L"Failed to open the thread token: %d", LastError);
    goto LABEL_15;
  }
  v6 = GetCurrentThread();
  if ( !OpenThreadToken(v6, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
LABEL_3:
  ReturnLength = 0;
  TokenInformation = 1;
  if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( TokenInformation == 2 )
      v0 = 1;
    if ( TokenInformation == 1 )
    {
      v10 = 0;
      ReturnLength = 4;
      if ( GetTokenInformation(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength) )
      {
        if ( v10 )
          v0 = 1;
      }
      else
      {
        v4 = GetLastError();
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "YIsElevated",
          L"GetTokenInformation failed for TokenElevation: %d",
          v4);
      }
    }
  }
  else
  {
    v5 = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError(
      "YIsElevated",
      L"GetTokenInformation failed for TokenElevationType: %d",
      v5);
  }
LABEL_15:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x140039f08  push    rbp
0x140039f0a  push    rbx
0x140039f0b  push    rdi
0x140039f0c  mov     rbp, rsp
0x140039f0f  sub     rsp, 30h
0x140039f13  xor     ebx, ebx
0x140039f15  mov     [rbp+TokenHandle], rbx
0x140039f19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140039f20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140039f25  test    al, al
0x140039f27  jz      loc_140039FE3
0x140039f2d  call    cs:__imp_GetCurrentThread
0x140039f33  mov     rcx, rax; ThreadHandle
0x140039f36  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140039f3a  lea     edx, [rbx+8]; DesiredAccess
0x140039f3d  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x140039f42  test    eax, eax
0x140039f44  jnz     loc_14003A00F
0x140039f4a  lea     edi, [rbx+1]
0x140039f4d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140039f51  lea     rax, [rbp+arg_8]
0x140039f55  mov     r9d, 4; TokenInformationLength
0x140039f5b  mov     [rbp+arg_8], ebx
0x140039f5e  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140039f62  mov     [rbp+TokenInformation], edi
0x140039f65  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140039f6a  lea     edx, [r9+0Eh]; TokenInformationClass
0x140039f6e  call    cs:__imp_GetTokenInformation
0x140039f74  test    eax, eax
0x140039f76  jz      short loc_140039FD4
0x140039f78  cmp     [rbp+TokenInformation], 2
0x140039f7c  cmovz   ebx, edi
0x140039f7f  cmp     [rbp+TokenInformation], edi
0x140039f82  jnz     loc_14003A025
0x140039f88  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140039f8c  lea     rax, [rbp+arg_8]
0x140039f90  mov     r9d, 4; TokenInformationLength
0x140039f96  mov     [rbp+arg_10], 0
0x140039f9d  lea     r8, [rbp+arg_10]; TokenInformation
0x140039fa1  mov     [rbp+arg_8], 4
0x140039fa8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140039fad  lea     edx, [r9+10h]; TokenInformationClass
0x140039fb1  call    cs:__imp_GetTokenInformation
0x140039fb7  test    eax, eax
0x140039fb9  jz      short loc_140039FC5
0x140039fbb  cmp     [rbp+arg_10], 0
0x140039fbf  jz      short loc_14003A025
0x140039fc1  mov     ebx, edi
0x140039fc3  jmp     short loc_14003A025
0x140039fc5  call    cs:__imp_GetLastError
0x140039fcb  lea     rdx, aGettokeninform_0; "GetTokenInformation failed for TokenEle"...
0x140039fd2  jmp     short loc_14003A016
0x140039fd4  call    cs:__imp_GetLastError
0x140039fda  lea     rdx, aGettokeninform; "GetTokenInformation failed for TokenEle"...
0x140039fe1  jmp     short loc_14003A016
0x140039fe3  call    cs:__imp_GetCurrentThread
0x140039fe9  mov     edi, 1
0x140039fee  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140039ff2  mov     rcx, rax; ThreadHandle
0x140039ff5  mov     r8d, edi; OpenAsSelf
0x140039ff8  lea     edx, [rdi+7]; DesiredAccess
0x140039ffb  call    cs:__imp_OpenThreadToken
0x14003a001  test    eax, eax
0x14003a003  jnz     loc_140039F4D
0x14003a009  call    cs:__imp_GetLastError
0x14003a00f  lea     rdx, aFailedToOpenTh; "Failed to open the thread token: %d"
0x14003a016  mov     r8d, eax
0x14003a019  lea     rcx, aYiselevated; "YIsElevated"
0x14003a020  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003a025  mov     rcx, [rbp+TokenHandle]; hObject
0x14003a029  test    rcx, rcx
0x14003a02c  jz      short loc_14003A034
0x14003a02e  call    cs:__imp_CloseHandle
0x14003a034  mov     eax, ebx
0x14003a036  add     rsp, 30h
0x14003a03a  pop     rdi
0x14003a03b  pop     rbx
0x14003a03c  pop     rbp
0x14003a03d  retn
```
