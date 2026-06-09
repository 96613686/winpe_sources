# VmxpReadPrimaryPackId(void)

- ea: `0x1400092b8`
- end: `0x1400093b8`
- name: `?VmxpReadPrimaryPackId@@YAJXZ`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14005f078`

## callees

- `0x1400092b8`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x140009384`
- `ntoskrnl!RtlGUIDFromString` at `0x140009384`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009329`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009329`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000935c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009339`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009339`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009398`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009398`

## string_xrefs

- `0x140009308`: `RtlQueryRegistryValuesEx`
- `0x140009355`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
__int64 VmxpReadPrimaryPackId(void)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  unsigned int v2; // ebx
  UNICODE_STRING GuidString; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v5[14]; // [rsp+50h] [rbp-19h] BYREF

  GuidString = 0;
  *(GUID *)((char *)Global + 216) = GUID_NULL;
  memset(v5, 0, sizeof(v5));
  LODWORD(v5[1]) = 292;
  v5[2] = L"PrimaryPackId";
  LODWORD(v5[4]) = 0x1000000;
  v5[3] = &GuidString;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  result = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX",
             v5,
             0,
             0);
  if ( (int)result >= 0 )
  {
    v2 = RtlGUIDFromString(&GuidString, (GUID *)((char *)Global + 216));
    ExFreePoolWithTag(GuidString.Buffer, 0);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1400092b8  mov     [rsp-8+arg_0], rbx
0x1400092bd  push    rbp
0x1400092be  lea     rbp, [rsp-57h]
0x1400092c3  sub     rsp, 0C0h
0x1400092ca  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400092d1  lea     rcx, [rbp+57h+var_70]; void *
0x1400092d5  movups  xmm1, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1400092dc  xor     edx, edx; Val
0x1400092de  xorps   xmm0, xmm0
0x1400092e1  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400092e5  lea     r8d, [rdx+70h]; Size
0x1400092e9  movdqu  xmmword ptr [rax+0D8h], xmm1
0x1400092f1  call    memset
0x1400092f6  lea     rax, aPrimarypackid; "PrimaryPackId"
0x1400092fd  mov     [rbp+57h+var_68], 124h
0x140009304  mov     [rbp+57h+var_60], rax
0x140009308  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000930f  lea     rax, [rbp+57h+GuidString]
0x140009313  mov     [rbp+57h+var_50], 1000000h
0x14000931a  xorps   xmm0, xmm0
0x14000931d  mov     [rbp+57h+var_58], rax
0x140009321  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140009325  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140009329  call    cs:__imp_RtlInitUnicodeString
0x140009330  nop     dword ptr [rax+rax+00h]
0x140009335  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140009339  call    cs:__imp_MmGetSystemRoutineAddress
0x140009340  nop     dword ptr [rax+rax+00h]
0x140009345  lea     r8, [rbp+57h+var_70]
0x140009349  mov     [rsp+0C0h+var_A0], 0
0x140009352  test    rax, rax
0x140009355  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000935c  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140009364  xor     r9d, r9d
0x140009367  xor     ecx, ecx
0x140009369  call    _guard_dispatch_icall
0x14000936e  test    eax, eax
0x140009370  js      short loc_1400093A6
0x140009372  mov     rdx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140009379  lea     rcx, [rbp+57h+GuidString]; GuidString
0x14000937d  add     rdx, 0D8h; Guid
0x140009384  call    cs:__imp_RtlGUIDFromString
0x14000938b  nop     dword ptr [rax+rax+00h]
0x140009390  mov     rcx, [rbp+57h+GuidString.Buffer]; P
0x140009394  xor     edx, edx; Tag
0x140009396  mov     ebx, eax
0x140009398  call    cs:__imp_ExFreePoolWithTag
0x14000939f  nop     dword ptr [rax+rax+00h]
0x1400093a4  mov     eax, ebx
0x1400093a6  mov     rbx, [rsp+0C0h+arg_0]
0x1400093ae  add     rsp, 0C0h
0x1400093b5  pop     rbp
0x1400093b6  retn
```
