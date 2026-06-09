# RevertToPrinterSelf

- ea: `0x140014eb0`
- end: `0x140014fbc`
- name: `RevertToPrinterSelf`
- size: `268`
- prototype: `HANDLE(void)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140004e90`
- `0x1400088b0`
- `0x14000d520`
- `0x14001283c`
- `0x140012adc`
- `0x140014e40`
- `0x1400605c0`
- `0x1400606a0`
- `0x140061e98`
- `0x14006533c`
- `0x140067ca0`
- `0x140069f68`
- `0x14006b5c4`
- `0x140076bf8`
- `0x140076d5c`

## callees

- `0x14000fb34`
- `0x1400140cc`
- `0x140014eb0`
- `0x140014fc4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x140014f75`
- `ntdll!RtlNtStatusToDosError` at `0x140014f75`
- `ntdll!NtOpenThreadToken` at `0x140014ef3`
- `ntdll!NtOpenThreadToken` at `0x140014f18`
- `ntdll!NtOpenThreadToken` at `0x140014ef3`
- `ntdll!NtOpenThreadToken` at `0x140014f18`
- `ntdll!NtClose` at `0x140014fa9`
- `ntdll!NtClose` at `0x140014fa9`
- `ntdll!NtSetInformationThread` at `0x140014f3b`
- `ntdll!NtSetInformationThread` at `0x140014f3b`
- `ntdll!NtOpenProcessToken` at `0x140014f5b`
- `ntdll!NtOpenProcessToken` at `0x140014f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014f83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014f7d`

## pseudocode

```c
HANDLE RevertToPrinterSelf(void)
{
  void *v0; // rdx
  SecurityHelper *v1; // rcx
  BOOLEAN v2; // r8
  int v3; // ebx
  void *v4; // rdx
  SecurityHelper *v5; // rcx
  ULONG v7; // eax
  DWORD LastError; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  __int64 ThreadInformation; // [rsp+38h] [rbp+10h] BYREF

  ThreadInformation = 0;
  TokenHandle = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &TokenHandle) >= 0 )
    {
LABEL_6:
      SecurityHelper::DumpTokenInfoToDebugOutput(v1, v0);
      v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      goto LABEL_9;
    }
    v2 = 0;
  }
  else
  {
    v2 = gbWindowsProtectedPrintSpoolerWorkerEnabled == 0;
  }
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, v2, &TokenHandle);
  if ( v3 >= 0 )
    goto LABEL_6;
  if ( v3 != -1073741700 )
    goto LABEL_11;
  v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  SecurityHelper::DumpTokenInfoToDebugOutput(v5, v4);
LABEL_9:
  if ( v3 >= 0 )
    return TokenHandle;
LABEL_11:
  v7 = RtlNtStatusToDosError(v3);
  SetLastError(v7);
  LastError = GetLastError();
  PrvSpoolssTelemetry::WriteDbgTraceError("RevertToPrinterSelf", L"Failed.  Error %d.", LastError);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x140014eb0  mov     [rsp+arg_10], rbx
0x140014eb5  push    rdi
0x140014eb6  sub     rsp, 20h
0x140014eba  mov     [rsp+28h+ThreadInformation], 0
0x140014ec3  mov     [rsp+28h+TokenHandle], 0
0x140014ecc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140014ed3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140014ed8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x140014edd  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x140014ee4  mov     rcx, rdi; ThreadHandle
0x140014ee7  mov     edx, 4; DesiredAccess
0x140014eec  test    al, al
0x140014eee  jz      short loc_140014F0D
0x140014ef0  mov     r8b, 1; OpenAsSelf
0x140014ef3  call    cs:__imp_NtOpenThreadToken
0x140014ef9  test    eax, eax
0x140014efb  jns     short loc_140014F24
0x140014efd  lea     r9, [rsp+28h+TokenHandle]
0x140014f02  xor     r8d, r8d
0x140014f05  lea     edx, [rdi+6]
0x140014f08  mov     rcx, rdi
0x140014f0b  jmp     short loc_140014F18
0x140014f0d  cmp     cs:?gbWindowsProtectedPrintSpoolerWorkerEnabled@@3HA, 0; int gbWindowsProtectedPrintSpoolerWorkerEnabled
0x140014f14  setz    r8b; OpenAsSelf
0x140014f18  call    cs:__imp_NtOpenThreadToken
0x140014f1e  mov     ebx, eax
0x140014f20  test    eax, eax
0x140014f22  js      short loc_140014F45
0x140014f24  call    ?DumpTokenInfoToDebugOutput@SecurityHelper@@YAXPEAX@Z; SecurityHelper::DumpTokenInfoToDebugOutput(void *)
0x140014f29  mov     r9d, 8; ThreadInformationLength
0x140014f2f  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x140014f34  mov     rcx, rdi; ThreadHandle
0x140014f37  lea     edx, [r9-3]; ThreadInformationClass
0x140014f3b  call    cs:__imp_NtSetInformationThread
0x140014f41  mov     ebx, eax
0x140014f43  jmp     short loc_140014F68
0x140014f45  cmp     ebx, 0C000007Ch
0x140014f4b  jnz     short loc_140014F73
0x140014f4d  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x140014f52  mov     edx, 8; DesiredAccess
0x140014f57  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140014f5b  call    cs:__imp_NtOpenProcessToken
0x140014f61  mov     ebx, eax
0x140014f63  call    ?DumpTokenInfoToDebugOutput@SecurityHelper@@YAXPEAX@Z; SecurityHelper::DumpTokenInfoToDebugOutput(void *)
0x140014f68  test    ebx, ebx
0x140014f6a  js      short loc_140014F73
0x140014f6c  mov     rax, [rsp+28h+TokenHandle]
0x140014f71  jmp     short loc_140014FB1
0x140014f73  mov     ecx, ebx; Status
0x140014f75  call    cs:__imp_RtlNtStatusToDosError
0x140014f7b  mov     ecx, eax; dwErrCode
0x140014f7d  call    cs:__imp_SetLastError
0x140014f83  call    cs:__imp_GetLastError
0x140014f89  mov     r8d, eax
0x140014f8c  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x140014f93  lea     rcx, aReverttoprinte; "RevertToPrinterSelf"
0x140014f9a  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140014f9f  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x140014fa4  test    rcx, rcx
0x140014fa7  jz      short loc_140014FAF
0x140014fa9  call    cs:__imp_NtClose
0x140014faf  xor     eax, eax
0x140014fb1  mov     rbx, [rsp+28h+arg_10]
0x140014fb6  add     rsp, 20h
0x140014fba  pop     rdi
0x140014fbb  retn
```
