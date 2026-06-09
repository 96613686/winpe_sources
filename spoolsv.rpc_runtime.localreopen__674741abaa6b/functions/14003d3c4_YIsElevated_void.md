# YIsElevated(void)

- ea: `0x14003d3c4`
- end: `0x14003d535`
- name: `?YIsElevated@@YAHXZ`
- size: `369`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140034d10`

## callees

- `0x140016314`
- `0x14001748c`
- `0x14003d3c4`
- `0x14005d4e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d4f3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003d4df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003d4df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d4c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d3e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003d4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d51e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d51e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003d430`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003d479`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003d430`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14003d479`

## string_xrefs

- `0x14003d4a3`: `GetTokenInformation failed for TokenElevation: %d`
- `0x14003d4b8`: `GetTokenInformation failed for TokenElevationType: %d`
- `0x14003d4ff`: `Failed to open the thread token: %d`

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
0x14003d3c4  push    rbp
0x14003d3c6  push    rbx
0x14003d3c7  push    rdi
0x14003d3c8  mov     rbp, rsp
0x14003d3cb  sub     rsp, 30h
0x14003d3cf  xor     ebx, ebx
0x14003d3d1  mov     [rbp+TokenHandle], rbx
0x14003d3d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14003d3dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14003d3e1  test    al, al
0x14003d3e3  jz      loc_14003D4C1
0x14003d3e9  call    cs:__imp_GetCurrentThread
0x14003d3f0  nop     dword ptr [rax+rax+00h]
0x14003d3f5  mov     rcx, rax; ThreadHandle
0x14003d3f8  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14003d3fc  lea     edx, [rbx+8]; DesiredAccess
0x14003d3ff  call    ?OpenThreadToken@SecurityHelper@@YAKPEAXKPEAPEAX@Z; SecurityHelper::OpenThreadToken(void *,ulong,void * *)
0x14003d404  test    eax, eax
0x14003d406  jnz     loc_14003D4FF
0x14003d40c  lea     edi, [rbx+1]
0x14003d40f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003d413  lea     rax, [rbp+arg_8]
0x14003d417  mov     r9d, 4; TokenInformationLength
0x14003d41d  mov     [rbp+arg_8], ebx
0x14003d420  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14003d424  mov     [rbp+TokenInformation], edi
0x14003d427  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14003d42c  lea     edx, [r9+0Eh]; TokenInformationClass
0x14003d430  call    cs:__imp_GetTokenInformation
0x14003d437  nop     dword ptr [rax+rax+00h]
0x14003d43c  test    eax, eax
0x14003d43e  jz      short loc_14003D4AC
0x14003d440  cmp     [rbp+TokenInformation], 2
0x14003d444  cmovz   ebx, edi
0x14003d447  cmp     [rbp+TokenInformation], edi
0x14003d44a  jnz     loc_14003D515
0x14003d450  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14003d454  lea     rax, [rbp+arg_8]
0x14003d458  mov     r9d, 4; TokenInformationLength
0x14003d45e  mov     [rbp+arg_10], 0
0x14003d465  lea     r8, [rbp+arg_10]; TokenInformation
0x14003d469  mov     [rbp+arg_8], 4
0x14003d470  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14003d475  lea     edx, [r9+10h]; TokenInformationClass
0x14003d479  call    cs:__imp_GetTokenInformation
0x14003d480  nop     dword ptr [rax+rax+00h]
0x14003d485  test    eax, eax
0x14003d487  jz      short loc_14003D497
0x14003d489  cmp     [rbp+arg_10], 0
0x14003d48d  jz      loc_14003D515
0x14003d493  mov     ebx, edi
0x14003d495  jmp     short loc_14003D515
0x14003d497  call    cs:__imp_GetLastError
0x14003d49e  nop     dword ptr [rax+rax+00h]
0x14003d4a3  lea     rdx, aGettokeninform_0; "GetTokenInformation failed for TokenEle"...
0x14003d4aa  jmp     short loc_14003D506
0x14003d4ac  call    cs:__imp_GetLastError
0x14003d4b3  nop     dword ptr [rax+rax+00h]
0x14003d4b8  lea     rdx, aGettokeninform; "GetTokenInformation failed for TokenEle"...
0x14003d4bf  jmp     short loc_14003D506
0x14003d4c1  call    cs:__imp_GetCurrentThread
0x14003d4c8  nop     dword ptr [rax+rax+00h]
0x14003d4cd  mov     edi, 1
0x14003d4d2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14003d4d6  mov     rcx, rax; ThreadHandle
0x14003d4d9  mov     r8d, edi; OpenAsSelf
0x14003d4dc  lea     edx, [rdi+7]; DesiredAccess
0x14003d4df  call    cs:__imp_OpenThreadToken
0x14003d4e6  nop     dword ptr [rax+rax+00h]
0x14003d4eb  test    eax, eax
0x14003d4ed  jnz     loc_14003D40F
0x14003d4f3  call    cs:__imp_GetLastError
0x14003d4fa  nop     dword ptr [rax+rax+00h]
0x14003d4ff  lea     rdx, aFailedToOpenTh; "Failed to open the thread token: %d"
0x14003d506  mov     r8d, eax
0x14003d509  lea     rcx, aYiselevated; "YIsElevated"
0x14003d510  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003d515  mov     rcx, [rbp+TokenHandle]; hObject
0x14003d519  test    rcx, rcx
0x14003d51c  jz      short loc_14003D52A
0x14003d51e  call    cs:__imp_CloseHandle
0x14003d525  nop     dword ptr [rax+rax+00h]
0x14003d52a  mov     eax, ebx
0x14003d52c  add     rsp, 30h
0x14003d530  pop     rdi
0x14003d531  pop     rbx
0x14003d532  pop     rbp
0x14003d533  retn
```
