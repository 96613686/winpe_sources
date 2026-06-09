# WppLoadTracingSupport

- ea: `0x14000a7d0`
- end: `0x14000a910`
- name: `WppLoadTracingSupport`
- size: `320`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c1b8`

## callees

- `0x140003130`
- `0x14000a7d0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a802`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a830`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a85e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a8b9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a8ec`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a802`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a830`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a85e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a8b9`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000a8ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a7f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a820`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a84e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a8a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a8dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a7f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a820`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a84e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a8a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a8dc`

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
0x14000a7d0  push    rbp
0x14000a7d2  mov     rbp, rsp
0x14000a7d5  sub     rsp, 40h
0x14000a7d9  xorps   xmm0, xmm0
0x14000a7dc  mov     [rbp+arg_0], 0
0x14000a7e3  lea     rdx, SourceString; "PsGetVersion"
0x14000a7ea  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a7ee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000a7f2  call    cs:__imp_RtlInitUnicodeString
0x14000a7f9  nop     dword ptr [rax+rax+00h]
0x14000a7fe  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a802  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a809  nop     dword ptr [rax+rax+00h]
0x14000a80e  lea     rdx, aWmitracemessag; "WmiTraceMessage"
0x14000a815  mov     cs:pfnWppGetVersion, rax
0x14000a81c  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a820  call    cs:__imp_RtlInitUnicodeString
0x14000a827  nop     dword ptr [rax+rax+00h]
0x14000a82c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a830  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a837  nop     dword ptr [rax+rax+00h]
0x14000a83c  lea     rdx, aWmiquerytracei; "WmiQueryTraceInformation"
0x14000a843  mov     cs:pfnWppTraceMessage, rax
0x14000a84a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a84e  call    cs:__imp_RtlInitUnicodeString
0x14000a855  nop     dword ptr [rax+rax+00h]
0x14000a85a  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a85e  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a865  nop     dword ptr [rax+rax+00h]
0x14000a86a  mov     cs:pfnWppQueryTraceInformation, rax
0x14000a871  mov     rax, cs:pfnWppGetVersion
0x14000a878  mov     cs:WPPTraceSuite, 2
0x14000a882  test    rax, rax
0x14000a885  jz      short loc_14000A898
0x14000a887  xor     r9d, r9d
0x14000a88a  lea     rcx, [rbp+arg_0]
0x14000a88e  xor     r8d, r8d
0x14000a891  xor     edx, edx
0x14000a893  call    _guard_dispatch_icall
0x14000a898  cmp     [rbp+arg_0], 6
0x14000a89c  jb      short loc_14000A909
0x14000a89e  lea     rdx, aEtwregistercla; "EtwRegisterClassicProvider"
0x14000a8a5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a8a9  call    cs:__imp_RtlInitUnicodeString
0x14000a8b0  nop     dword ptr [rax+rax+00h]
0x14000a8b5  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a8b9  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a8c0  nop     dword ptr [rax+rax+00h]
0x14000a8c5  mov     cs:pfnEtwRegisterClassicProvider, rax
0x14000a8cc  test    rax, rax
0x14000a8cf  jz      short loc_14000A909
0x14000a8d1  lea     rdx, aEtwunregister; "EtwUnregister"
0x14000a8d8  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000a8dc  call    cs:__imp_RtlInitUnicodeString
0x14000a8e3  nop     dword ptr [rax+rax+00h]
0x14000a8e8  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14000a8ec  call    cs:__imp_MmGetSystemRoutineAddress
0x14000a8f3  nop     dword ptr [rax+rax+00h]
0x14000a8f8  mov     cs:pfnEtwUnregister, rax
0x14000a8ff  mov     cs:WPPTraceSuite, 4
0x14000a909  add     rsp, 40h
0x14000a90d  pop     rbp
0x14000a90e  retn
```
