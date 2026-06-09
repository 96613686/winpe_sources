# VmxpReadTestMode(void)

- ea: `0x1400093c0`
- end: `0x1400094a6`
- name: `?VmxpReadTestMode@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14005f078`

## callees

- `0x1400093c0`
- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000943b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000943b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000946e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000944b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000944b`

## string_xrefs

- `0x14000940b`: `RtlQueryRegistryValuesEx`
- `0x140009467`: `\Registry\Machine\System\CurrentControlSet\Services\VolMgrX`

## pseudocode

```c
__int64 VmxpReadTestMode(void)
{
  PVOID SystemRoutineAddress; // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v3[14]; // [rsp+40h] [rbp-19h] BYREF
  int v4; // [rsp+C0h] [rbp+67h] BYREF
  int v5; // [rsp+C8h] [rbp+6Fh] BYREF

  v5 = 0;
  v4 = 0;
  *((_BYTE *)Global + 276) = 0;
  memset(v3, 0, sizeof(v3));
  LODWORD(v3[1]) = 288;
  v3[2] = L"TestMode";
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
    *((_BYTE *)Global + 276) = v4 != 0;
    return (unsigned int)result;
  }
  return result;
}

```

## disassembly

```asm
0x1400093c0  push    rbp
0x1400093c2  lea     rbp, [rsp-57h]
0x1400093c7  sub     rsp, 0B0h
0x1400093ce  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400093d5  lea     rcx, [rbp+57h+var_70]; void *
0x1400093d9  xor     edx, edx; Val
0x1400093db  mov     [rbp+57h+arg_8], 0
0x1400093e2  mov     [rbp+57h+arg_0], 0
0x1400093e9  mov     byte ptr [rax+114h], 0
0x1400093f0  lea     r8d, [rdx+70h]; Size
0x1400093f4  call    memset
0x1400093f9  lea     rax, aTestmode; "TestMode"
0x140009400  mov     [rbp+57h+var_68], 120h
0x140009407  mov     [rbp+57h+var_60], rax
0x14000940b  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140009412  lea     rax, [rbp+57h+arg_0]
0x140009416  mov     [rbp+57h+var_50], 4000000h
0x14000941d  mov     [rbp+57h+var_58], rax
0x140009421  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140009425  lea     rax, [rbp+57h+arg_8]
0x140009429  mov     [rbp+57h+var_40], 4
0x140009430  xorps   xmm0, xmm0
0x140009433  mov     [rbp+57h+var_48], rax
0x140009437  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000943b  call    cs:__imp_RtlInitUnicodeString
0x140009442  nop     dword ptr [rax+rax+00h]
0x140009447  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14000944b  call    cs:__imp_MmGetSystemRoutineAddress
0x140009452  nop     dword ptr [rax+rax+00h]
0x140009457  lea     r8, [rbp+57h+var_70]
0x14000945b  mov     [rsp+0B0h+var_90], 0
0x140009464  test    rax, rax
0x140009467  lea     rdx, Path; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000946e  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140009476  xor     r9d, r9d
0x140009479  xor     ecx, ecx
0x14000947b  call    _guard_dispatch_icall
0x140009480  mov     edx, eax
0x140009482  test    eax, eax
0x140009484  js      short loc_14000949C
0x140009486  cmp     [rbp+57h+arg_0], 0
0x14000948a  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x140009491  setnz   cl
0x140009494  mov     [rax+114h], cl
0x14000949a  mov     eax, edx
0x14000949c  add     rsp, 0B0h
0x1400094a3  pop     rbp
0x1400094a4  retn
```
