# WppLoadTracingSupport

- ea: `0x14000c4c4`
- end: `0x14000c604`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d03c`

## callees

- `0x140006370`
- `0x14000c4c4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c514`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c542`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c59d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c5d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c514`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c542`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c59d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c5d0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c4f6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c524`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c552`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c5ad`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c5e0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c4f6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c524`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c552`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c5ad`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c5e0`

## pseudocode

```c
PVOID WppLoadTracingSupport()
{
  PVOID result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v2; // [rsp+50h] [rbp+10h] BYREF

  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"PsGetVersion");
  pfnWppGetVersion = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiTraceMessage");
  pfnWppTraceMessage = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  RtlInitUnicodeString(&DestinationString, L"WmiQueryTraceInformation");
  pfnWppQueryTraceInformation = (__int64)MmGetSystemRoutineAddress(&DestinationString);
  result = pfnWppGetVersion;
  WPPTraceSuite = 2;
  if ( pfnWppGetVersion )
    result = (PVOID)pfnWppGetVersion(&v2, 0, 0, 0);
  if ( v2 >= 6 )
  {
    RtlInitUnicodeString(&DestinationString, L"EtwRegisterClassicProvider");
    result = MmGetSystemRoutineAddress(&DestinationString);
    pfnEtwRegisterClassicProvider = (__int64)result;
    if ( result )
    {
      RtlInitUnicodeString(&DestinationString, L"EtwUnregister");
      result = MmGetSystemRoutineAddress(&DestinationString);
      pfnEtwUnregister = (__int64)result;
      WPPTraceSuite = 4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c4c4  push    rbp
0x14000c4c6  mov     rbp, rsp
0x14000c4c9  sub     rsp, 40h
0x14000c4cd  xorps   xmm0, xmm0
0x14000c4d0  mov     [rbp+arg_0], 0
0x14000c4d7  lea     rdx, SourceString; "PsGetVersion"
0x14000c4de  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c4e2  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000c4e6  call    cs:__imp_RtlInitUnicodeString
0x14000c4ed  nop     dword ptr [rax+rax+00h]
0x14000c4f2  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000c4f6  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c4fd  nop     dword ptr [rax+rax+00h]
0x14000c502  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x14000c509  mov     cs:pfnWppGetVersion, rax
0x14000c510  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c514  call    cs:__imp_RtlInitUnicodeString
0x14000c51b  nop     dword ptr [rax+rax+00h]
0x14000c520  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000c524  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c52b  nop     dword ptr [rax+rax+00h]
0x14000c530  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x14000c537  mov     cs:pfnWppTraceMessage, rax
0x14000c53e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c542  call    cs:__imp_RtlInitUnicodeString
0x14000c549  nop     dword ptr [rax+rax+00h]
0x14000c54e  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000c552  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c559  nop     dword ptr [rax+rax+00h]
0x14000c55e  mov     cs:pfnWppQueryTraceInformation, rax
0x14000c565  mov     rax, cs:pfnWppGetVersion
0x14000c56c  mov     cs:WPPTraceSuite, 2
0x14000c576  test    rax, rax
0x14000c579  jz      short loc_14000C58C
0x14000c57b  xor     r9d, r9d
0x14000c57e  lea     rcx, [rbp+arg_0]
0x14000c582  xor     r8d, r8d
0x14000c585  xor     edx, edx
0x14000c587  call    _guard_dispatch_icall
0x14000c58c  cmp     [rbp+arg_0], 6
0x14000c590  jb      short loc_14000C5FD
0x14000c592  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x14000c599  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c59d  call    cs:__imp_RtlInitUnicodeString
0x14000c5a4  nop     dword ptr [rax+rax+00h]
0x14000c5a9  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000c5ad  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c5b4  nop     dword ptr [rax+rax+00h]
0x14000c5b9  mov     cs:pfnEtwRegisterClassicProvider, rax
0x14000c5c0  test    rax, rax
0x14000c5c3  jz      short loc_14000C5FD
0x14000c5c5  lea     rdx, aEtwunregister; "EtwUnregister"
0x14000c5cc  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c5d0  call    cs:__imp_RtlInitUnicodeString
0x14000c5d7  nop     dword ptr [rax+rax+00h]
0x14000c5dc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000c5e0  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c5e7  nop     dword ptr [rax+rax+00h]
0x14000c5ec  mov     cs:pfnEtwUnregister, rax
0x14000c5f3  mov     cs:WPPTraceSuite, 4
0x14000c5fd  add     rsp, 40h
0x14000c601  pop     rbp
0x14000c602  retn
```
