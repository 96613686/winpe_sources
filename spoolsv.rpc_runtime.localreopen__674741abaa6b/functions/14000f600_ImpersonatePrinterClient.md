# ImpersonatePrinterClient

- ea: `0x14000f600`
- end: `0x14000f727`
- name: `ImpersonatePrinterClient`
- size: `295`
- prototype: `BOOL __stdcall(HANDLE hToken)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005630`
- `0x14000e700`
- `0x14000f8e8`
- `0x140013a5c`
- `0x140013d28`
- `0x140016160`
- `0x140018f50`
- `0x1400664b0`
- `0x1400665b0`
- `0x14006b70c`
- `0x14006e42c`
- `0x1400709e0`
- `0x1400721b8`
- `0x14007de84`
- `0x14007e00c`

## callees

- `0x14000f600`
- `0x140015378`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000f6e4`
- `ntdll!RtlNtStatusToDosError` at `0x14000f6e4`
- `ntdll!NtClose` at `0x14000f690`
- `ntdll!NtClose` at `0x14000f690`
- `ntdll!NtSetInformationThread` at `0x14000f6d2`
- `ntdll!NtSetInformationThread` at `0x14000f6d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f63b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f6fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f617`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f67f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f6af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f617`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f67f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f6af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000f6f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000f666`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000f666`

## string_xrefs

- `0x14000f714`: `ImpersonatePrinterClient`

## pseudocode

```c
BOOL __stdcall ImpersonatePrinterClient(HANDLE hToken)
{
  DWORD LastError; // edi
  int v4; // eax
  ULONG v5; // eax
  DWORD v6; // eax
  HANDLE Handle; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  Handle = hToken;
  if ( !hToken )
  {
    SetLastError(6u);
    return 0;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  LastError = GetLastError();
  if ( GetTokenInformation(hToken, TokenType, &TokenInformation, 4u, &ReturnLength) && TokenInformation != 2 )
  {
    SetLastError(LastError);
LABEL_6:
    NtClose(Handle);
    return 1;
  }
  SetLastError(LastError);
  v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
  if ( v4 >= 0 )
    goto LABEL_6;
  v5 = RtlNtStatusToDosError(v4);
  SetLastError(v5);
  v6 = GetLastError();
  PrvSpoolssTelemetry::WriteDbgTraceError("ImpersonatePrinterClient", L"Failed.  Error %d.", v6);
  return 0;
}

```

## disassembly

```asm
0x14000f600  mov     [rsp+Handle], rcx
0x14000f605  push    rbx
0x14000f606  sub     rsp, 30h
0x14000f60a  mov     rbx, rcx
0x14000f60d  test    rcx, rcx
0x14000f610  jnz     short loc_14000F62C
0x14000f612  mov     ecx, 6; dwErrCode
0x14000f617  call    cs:__imp_SetLastError
0x14000f61e  nop     dword ptr [rax+rax+00h]
0x14000f623  xor     eax, eax
0x14000f625  add     rsp, 30h
0x14000f629  pop     rbx
0x14000f62a  retn
0x14000f62c  xor     eax, eax
0x14000f62e  mov     [rsp+38h+arg_18], rdi
0x14000f633  mov     [rsp+38h+TokenInformation], eax
0x14000f637  mov     [rsp+38h+arg_10], eax
0x14000f63b  call    cs:__imp_GetLastError
0x14000f642  nop     dword ptr [rax+rax+00h]
0x14000f647  mov     r9d, 4; TokenInformationLength
0x14000f64d  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14000f652  mov     edi, eax
0x14000f654  mov     edx, 8; TokenInformationClass
0x14000f659  lea     rax, [rsp+38h+arg_10]
0x14000f65e  mov     rcx, rbx; TokenHandle
0x14000f661  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14000f666  call    cs:__imp_GetTokenInformation
0x14000f66d  nop     dword ptr [rax+rax+00h]
0x14000f672  test    eax, eax
0x14000f674  jz      short loc_14000F6AD
0x14000f676  cmp     [rsp+38h+TokenInformation], 2
0x14000f67b  jz      short loc_14000F6AD
0x14000f67d  mov     ecx, edi; dwErrCode
0x14000f67f  call    cs:__imp_SetLastError
0x14000f686  nop     dword ptr [rax+rax+00h]
0x14000f68b  mov     rcx, [rsp+38h+Handle]; Handle
0x14000f690  call    cs:__imp_NtClose
0x14000f697  nop     dword ptr [rax+rax+00h]
0x14000f69c  mov     eax, 1
0x14000f6a1  mov     rdi, [rsp+38h+arg_18]
0x14000f6a6  add     rsp, 30h
0x14000f6aa  pop     rbx
0x14000f6ab  retn
0x14000f6ad  mov     ecx, edi; dwErrCode
0x14000f6af  call    cs:__imp_SetLastError
0x14000f6b6  nop     dword ptr [rax+rax+00h]
0x14000f6bb  mov     r9d, 8; ThreadInformationLength
0x14000f6c1  lea     r8, [rsp+38h+Handle]; ThreadInformation
0x14000f6c6  mov     edx, 5; ThreadInformationClass
0x14000f6cb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14000f6d2  call    cs:__imp_NtSetInformationThread
0x14000f6d9  nop     dword ptr [rax+rax+00h]
0x14000f6de  test    eax, eax
0x14000f6e0  jns     short loc_14000F68B
0x14000f6e2  mov     ecx, eax; Status
0x14000f6e4  call    cs:__imp_RtlNtStatusToDosError
0x14000f6eb  nop     dword ptr [rax+rax+00h]
0x14000f6f0  mov     ecx, eax; dwErrCode
0x14000f6f2  call    cs:__imp_SetLastError
0x14000f6f9  nop     dword ptr [rax+rax+00h]
0x14000f6fe  call    cs:__imp_GetLastError
0x14000f705  nop     dword ptr [rax+rax+00h]
0x14000f70a  mov     r8d, eax
0x14000f70d  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14000f714  lea     rcx, aImpersonatepri; "ImpersonatePrinterClient"
0x14000f71b  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000f720  xor     eax, eax
0x14000f722  jmp     loc_14000F6A1
```
