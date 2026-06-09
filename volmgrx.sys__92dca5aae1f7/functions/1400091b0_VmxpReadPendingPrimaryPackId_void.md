# VmxpReadPendingPrimaryPackId(void)

- ea: `0x1400091b0`
- end: `0x1400092b0`
- name: `?VmxpReadPendingPrimaryPackId@@YAJXZ`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14005f078`

## callees

- `0x1400091b0`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x14000927c`
- `ntoskrnl!RtlGUIDFromString` at `0x14000927c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009221`
- `ntoskrnl!RtlInitUnicodeString` at `0x140009221`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140009254`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009231`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140009231`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009290`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009290`

## string_xrefs

- `0x140009200`: `RtlQueryRegistryValuesEx`
- `0x14000924d`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
__int64 VmxpReadPendingPrimaryPackId(void)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  unsigned int v2; // ebx
  UNICODE_STRING GuidString; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v5[14]; // [rsp+50h] [rbp-19h] BYREF

  GuidString = 0;
  *(GUID *)((char *)Global + 232) = GUID_NULL;
  memset(v5, 0, sizeof(v5));
  LODWORD(v5[1]) = 292;
  v5[2] = L"PendingPrimaryPackId";
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
    v2 = RtlGUIDFromString(&GuidString, (GUID *)((char *)Global + 232));
    ExFreePoolWithTag(GuidString.Buffer, 0);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1400091b0  mov     [rsp-8+arg_0], rbx
0x1400091b5  push    rbp
0x1400091b6  lea     rbp, [rsp-57h]
0x1400091bb  sub     rsp, 0C0h
0x1400091c2  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400091c9  lea     rcx, [rbp+57h+var_70]; void *
0x1400091cd  movups  xmm1, xmmword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x1400091d4  xor     edx, edx; Val
0x1400091d6  xorps   xmm0, xmm0
0x1400091d9  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400091dd  lea     r8d, [rdx+70h]; Size
0x1400091e1  movdqu  xmmword ptr [rax+0E8h], xmm1
0x1400091e9  call    memset
0x1400091ee  lea     rax, ValueName; "PendingPrimaryPackId"
0x1400091f5  mov     [rbp+57h+var_68], 124h
0x1400091fc  mov     [rbp+57h+var_60], rax
0x140009200  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140009207  lea     rax, [rbp+57h+GuidString]
0x14000920b  mov     [rbp+57h+var_50], 1000000h
0x140009212  xorps   xmm0, xmm0
0x140009215  mov     [rbp+57h+var_58], rax
0x140009219  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000921d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140009221  call    cs:__imp_RtlInitUnicodeString
0x140009228  nop     dword ptr [rax+rax+00h]
0x14000922d  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140009231  call    cs:__imp_MmGetSystemRoutineAddress
0x140009238  nop     dword ptr [rax+rax+00h]
0x14000923d  lea     r8, [rbp+57h+var_70]
0x140009241  mov     [rsp+0C0h+var_A0], 0
0x14000924a  test    rax, rax
0x14000924d  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140009254  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000925c  xor     r9d, r9d
0x14000925f  xor     ecx, ecx
0x140009261  call    _guard_dispatch_icall
0x140009266  test    eax, eax
0x140009268  js      short loc_14000929E
0x14000926a  mov     rdx, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140009271  lea     rcx, [rbp+57h+GuidString]; GuidString
0x140009275  add     rdx, 0E8h; Guid
0x14000927c  call    cs:__imp_RtlGUIDFromString
0x140009283  nop     dword ptr [rax+rax+00h]
0x140009288  mov     rcx, [rbp+57h+GuidString.Buffer]; P
0x14000928c  xor     edx, edx; Tag
0x14000928e  mov     ebx, eax
0x140009290  call    cs:__imp_ExFreePoolWithTag
0x140009297  nop     dword ptr [rax+rax+00h]
0x14000929c  mov     eax, ebx
0x14000929e  mov     rbx, [rsp+0C0h+arg_0]
0x1400092a6  add     rsp, 0C0h
0x1400092ad  pop     rbp
0x1400092ae  retn
```
