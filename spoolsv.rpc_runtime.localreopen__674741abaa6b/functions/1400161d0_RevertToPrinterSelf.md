# RevertToPrinterSelf

- ea: `0x1400161d0`
- end: `0x14001630d`
- name: `RevertToPrinterSelf`
- size: `317`
- prototype: `HANDLE(void)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005630`
- `0x140009470`
- `0x14000e700`
- `0x140013a5c`
- `0x140013d28`
- `0x140016160`
- `0x1400664b0`
- `0x1400665b0`
- `0x140067e4c`
- `0x14006b70c`
- `0x14006e42c`
- `0x1400709e0`
- `0x1400721b8`
- `0x14007de84`
- `0x14007e00c`

## callees

- `0x140010d34`
- `0x140015378`
- `0x1400161d0`
- `0x140016314`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1400162ad`
- `ntdll!RtlNtStatusToDosError` at `0x1400162ad`
- `ntdll!NtOpenThreadToken` at `0x140016213`
- `ntdll!NtOpenThreadToken` at `0x14001623e`
- `ntdll!NtOpenThreadToken` at `0x140016213`
- `ntdll!NtOpenThreadToken` at `0x14001623e`
- `ntdll!NtClose` at `0x1400162f3`
- `ntdll!NtClose` at `0x1400162f3`
- `ntdll!NtSetInformationThread` at `0x140016267`
- `ntdll!NtSetInformationThread` at `0x140016267`
- `ntdll!NtOpenProcessToken` at `0x14001628d`
- `ntdll!NtOpenProcessToken` at `0x14001628d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400162c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400162bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400162bb`

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
0x1400161d0  mov     [rsp+arg_10], rbx
0x1400161d5  push    rdi
0x1400161d6  sub     rsp, 20h
0x1400161da  mov     [rsp+28h+ThreadInformation], 0
0x1400161e3  mov     [rsp+28h+TokenHandle], 0
0x1400161ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1400161f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1400161f8  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1400161fd  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x140016204  mov     rcx, rdi; ThreadHandle
0x140016207  mov     edx, 4; DesiredAccess
0x14001620c  test    al, al
0x14001620e  jz      short loc_140016233
0x140016210  mov     r8b, 1; OpenAsSelf
0x140016213  call    cs:__imp_NtOpenThreadToken
0x14001621a  nop     dword ptr [rax+rax+00h]
0x14001621f  test    eax, eax
0x140016221  jns     short loc_140016250
0x140016223  lea     r9, [rsp+28h+TokenHandle]
0x140016228  xor     r8d, r8d
0x14001622b  lea     edx, [rdi+6]
0x14001622e  mov     rcx, rdi
0x140016231  jmp     short loc_14001623E
0x140016233  cmp     cs:?gbWindowsProtectedPrintSpoolerWorkerEnabled@@3HA, 0; int gbWindowsProtectedPrintSpoolerWorkerEnabled
0x14001623a  setz    r8b; OpenAsSelf
0x14001623e  call    cs:__imp_NtOpenThreadToken
0x140016245  nop     dword ptr [rax+rax+00h]
0x14001624a  mov     ebx, eax
0x14001624c  test    eax, eax
0x14001624e  js      short loc_140016277
0x140016250  call    ?DumpTokenInfoToDebugOutput@SecurityHelper@@YAXPEAX@Z; SecurityHelper::DumpTokenInfoToDebugOutput(void *)
0x140016255  mov     r9d, 8; ThreadInformationLength
0x14001625b  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x140016260  mov     rcx, rdi; ThreadHandle
0x140016263  lea     edx, [r9-3]; ThreadInformationClass
0x140016267  call    cs:__imp_NtSetInformationThread
0x14001626e  nop     dword ptr [rax+rax+00h]
0x140016273  mov     ebx, eax
0x140016275  jmp     short loc_1400162A0
0x140016277  cmp     ebx, 0C000007Ch
0x14001627d  jnz     short loc_1400162AB
0x14001627f  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x140016284  mov     edx, 8; DesiredAccess
0x140016289  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14001628d  call    cs:__imp_NtOpenProcessToken
0x140016294  nop     dword ptr [rax+rax+00h]
0x140016299  mov     ebx, eax
0x14001629b  call    ?DumpTokenInfoToDebugOutput@SecurityHelper@@YAXPEAX@Z; SecurityHelper::DumpTokenInfoToDebugOutput(void *)
0x1400162a0  test    ebx, ebx
0x1400162a2  js      short loc_1400162AB
0x1400162a4  mov     rax, [rsp+28h+TokenHandle]
0x1400162a9  jmp     short loc_140016301
0x1400162ab  mov     ecx, ebx; Status
0x1400162ad  call    cs:__imp_RtlNtStatusToDosError
0x1400162b4  nop     dword ptr [rax+rax+00h]
0x1400162b9  mov     ecx, eax; dwErrCode
0x1400162bb  call    cs:__imp_SetLastError
0x1400162c2  nop     dword ptr [rax+rax+00h]
0x1400162c7  call    cs:__imp_GetLastError
0x1400162ce  nop     dword ptr [rax+rax+00h]
0x1400162d3  mov     r8d, eax
0x1400162d6  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x1400162dd  lea     rcx, aReverttoprinte; "RevertToPrinterSelf"
0x1400162e4  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400162e9  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x1400162ee  test    rcx, rcx
0x1400162f1  jz      short loc_1400162FF
0x1400162f3  call    cs:__imp_NtClose
0x1400162fa  nop     dword ptr [rax+rax+00h]
0x1400162ff  xor     eax, eax
0x140016301  mov     rbx, [rsp+28h+arg_10]
0x140016306  add     rsp, 20h
0x14001630a  pop     rdi
0x14001630b  retn
```
