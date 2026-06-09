# ImpersonatePrinterClient

- ea: `0x14000e590`
- end: `0x14000e676`
- name: `ImpersonatePrinterClient`
- size: `230`
- prototype: `BOOL __stdcall(HANDLE hToken)`
- caller_count: `15`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140004e90`
- `0x14000d520`
- `0x14000e67c`
- `0x14001283c`
- `0x140012adc`
- `0x140014e40`
- `0x140017a80`
- `0x1400605c0`
- `0x1400606a0`
- `0x14006533c`
- `0x140067ca0`
- `0x140069f68`
- `0x14006b5c4`
- `0x140076bf8`
- `0x140076d5c`

## callees

- `0x14000e590`
- `0x1400140cc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x14000e648`
- `ntdll!RtlNtStatusToDosError` at `0x14000e648`
- `ntdll!NtClose` at `0x14000e607`
- `ntdll!NtClose` at `0x14000e607`
- `ntdll!NtSetInformationThread` at `0x14000e63c`
- `ntdll!NtSetInformationThread` at `0x14000e63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e656`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e61f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e650`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e5fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e61f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e650`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000e5e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000e5e9`

## string_xrefs

- `0x14000e666`: `ImpersonatePrinterClient`

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
0x14000e590  mov     [rsp+Handle], rcx
0x14000e595  push    rbx
0x14000e596  sub     rsp, 30h
0x14000e59a  mov     rbx, rcx
0x14000e59d  test    rcx, rcx
0x14000e5a0  jnz     short loc_14000E5B5
0x14000e5a2  mov     ecx, 6; dwErrCode
0x14000e5a7  call    cs:__imp_SetLastError
0x14000e5ad  xor     eax, eax
0x14000e5af  add     rsp, 30h
0x14000e5b3  pop     rbx
0x14000e5b4  retn
0x14000e5b5  xor     eax, eax
0x14000e5b7  mov     [rsp+38h+arg_18], rdi
0x14000e5bc  mov     [rsp+38h+TokenInformation], eax
0x14000e5c0  mov     [rsp+38h+arg_10], eax
0x14000e5c4  call    cs:__imp_GetLastError
0x14000e5ca  mov     r9d, 4; TokenInformationLength
0x14000e5d0  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14000e5d5  mov     edi, eax
0x14000e5d7  mov     edx, 8; TokenInformationClass
0x14000e5dc  lea     rax, [rsp+38h+arg_10]
0x14000e5e1  mov     rcx, rbx; TokenHandle
0x14000e5e4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14000e5e9  call    cs:__imp_GetTokenInformation
0x14000e5ef  test    eax, eax
0x14000e5f1  jz      short loc_14000E61D
0x14000e5f3  cmp     [rsp+38h+TokenInformation], 2
0x14000e5f8  jz      short loc_14000E61D
0x14000e5fa  mov     ecx, edi; dwErrCode
0x14000e5fc  call    cs:__imp_SetLastError
0x14000e602  mov     rcx, [rsp+38h+Handle]; Handle
0x14000e607  call    cs:__imp_NtClose
0x14000e60d  mov     eax, 1
0x14000e612  mov     rdi, [rsp+38h+arg_18]
0x14000e617  add     rsp, 30h
0x14000e61b  pop     rbx
0x14000e61c  retn
0x14000e61d  mov     ecx, edi; dwErrCode
0x14000e61f  call    cs:__imp_SetLastError
0x14000e625  mov     r9d, 8; ThreadInformationLength
0x14000e62b  lea     r8, [rsp+38h+Handle]; ThreadInformation
0x14000e630  mov     edx, 5; ThreadInformationClass
0x14000e635  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14000e63c  call    cs:__imp_NtSetInformationThread
0x14000e642  test    eax, eax
0x14000e644  jns     short loc_14000E602
0x14000e646  mov     ecx, eax; Status
0x14000e648  call    cs:__imp_RtlNtStatusToDosError
0x14000e64e  mov     ecx, eax; dwErrCode
0x14000e650  call    cs:__imp_SetLastError
0x14000e656  call    cs:__imp_GetLastError
0x14000e65c  mov     r8d, eax
0x14000e65f  lea     rdx, aFailedErrorD; "Failed.  Error %d."
0x14000e666  lea     rcx, aImpersonatepri; "ImpersonatePrinterClient"
0x14000e66d  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000e672  xor     eax, eax
0x14000e674  jmp     short loc_14000E612
```
