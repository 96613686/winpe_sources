# VmxpReadOnlineSplitBrainVolumes(void)

- ea: `0x1400090c4`
- end: `0x1400091a8`
- name: `?VmxpReadOnlineSplitBrainVolumes@@YAJXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14005f078`

## callees

- `0x1400090c4`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000913f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000913f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140009172`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000914f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000914f`

## string_xrefs

- `0x14000910f`: `RtlQueryRegistryValuesEx`
- `0x14000916b`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
__int64 VmxpReadOnlineSplitBrainVolumes(void)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v3[14]; // [rsp+40h] [rbp-19h] BYREF
  int v4; // [rsp+C0h] [rbp+67h] BYREF
  int v5; // [rsp+C8h] [rbp+6Fh] BYREF

  v4 = 0;
  v5 = 0;
  *((_BYTE *)Global + 278) = 0;
  memset(v3, 0, sizeof(v3));
  LODWORD(v3[1]) = 288;
  v3[2] = L"OnlineSplitBrainVolumes";
  LODWORD(v3[4]) = 0x4000000;
  v3[3] = &v4;
  LODWORD(v3[6]) = 4;
  v3[5] = &v5;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  result = ((__int64 (__fastcall *)(_QWORD, const WCHAR *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\VolMgrX",
             v3,
             0,
             0);
  if ( (int)result >= 0 )
  {
    *((_BYTE *)Global + 278) = v4 != 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400090c4  push    rbp
0x1400090c6  lea     rbp, [rsp-57h]
0x1400090cb  sub     rsp, 0B0h
0x1400090d2  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400090d9  lea     rcx, [rbp+57h+var_70]; void *
0x1400090dd  xor     edx, edx; Val
0x1400090df  mov     [rbp+57h+arg_0], 0
0x1400090e6  mov     [rbp+57h+arg_8], 0
0x1400090ed  mov     byte ptr [rax+116h], 0
0x1400090f4  lea     r8d, [rdx+70h]; Size
0x1400090f8  call    memset
0x1400090fd  lea     rax, aOnlinesplitbra; "OnlineSplitBrainVolumes"
0x140009104  mov     [rbp+57h+var_68], 120h
0x14000910b  mov     [rbp+57h+var_60], rax
0x14000910f  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140009116  lea     rax, [rbp+57h+arg_0]
0x14000911a  mov     [rbp+57h+var_50], 4000000h
0x140009121  mov     [rbp+57h+var_58], rax
0x140009125  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140009129  lea     rax, [rbp+57h+arg_8]
0x14000912d  mov     [rbp+57h+var_40], 4
0x140009134  xorps   xmm0, xmm0
0x140009137  mov     [rbp+57h+var_48], rax
0x14000913b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000913f  call    cs:__imp_RtlInitUnicodeString
0x140009146  nop     dword ptr [rax+rax+00h]
0x14000914b  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14000914f  call    cs:__imp_MmGetSystemRoutineAddress
0x140009156  nop     dword ptr [rax+rax+00h]
0x14000915b  lea     r8, [rbp+57h+var_70]
0x14000915f  mov     [rsp+0B0h+var_90], 0
0x140009168  test    rax, rax
0x14000916b  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x140009172  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000917a  xor     r9d, r9d
0x14000917d  xor     ecx, ecx
0x14000917f  call    _guard_dispatch_icall
0x140009184  test    eax, eax
0x140009186  js      short loc_14000919E
0x140009188  cmp     [rbp+57h+arg_0], 0
0x14000918c  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140009193  setnz   cl
0x140009196  mov     [rax+116h], cl
0x14000919c  xor     eax, eax
0x14000919e  add     rsp, 0B0h
0x1400091a5  pop     rbp
0x1400091a6  retn
```
