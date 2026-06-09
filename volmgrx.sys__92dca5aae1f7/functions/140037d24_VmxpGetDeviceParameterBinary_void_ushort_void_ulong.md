# VmxpGetDeviceParameterBinary(void *,ushort *,void * *,ulong *)

- ea: `0x140037d24`
- end: `0x140037de0`
- name: `?VmxpGetDeviceParameterBinary@@YAJPEAXPEAGPEAPEAXPEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140046648`

## callees

- `0x14001b9a0`
- `0x14001be80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140037d8d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140037d8d`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140037dc6`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140037d9e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140037d9e`

## string_xrefs

- `0x140037d62`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall VmxpGetDeviceParameterBinary(void *a1, unsigned __int16 *a2, void **a3, unsigned int *a4)
{
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v11[19]; // [rsp+40h] [rbp-98h] BYREF

  memset(&v11[1], 0, 0x68u);
  *a3 = 0;
  v11[0] = VmxpGetDeviceParameterBinaryCallback;
  LODWORD(v11[1]) = 260;
  v11[2] = a2;
  DestinationString = 0;
  v11[3] = a3;
  LODWORD(v11[4]) = 50331648;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  return ((__int64 (__fastcall *)(__int64, void *, _QWORD *, unsigned int *, _QWORD))SystemRoutineAddress)(
           0x40000000,
           a1,
           v11,
           a4,
           0);
}

```

## disassembly

```asm
0x140037d24  push    rbx
0x140037d26  push    rbp
0x140037d27  push    rsi
0x140037d28  push    rdi
0x140037d29  sub     rsp, 0B8h
0x140037d30  mov     rbx, rdx
0x140037d33  mov     rdi, r8
0x140037d36  xor     edx, edx; Val
0x140037d38  mov     rsi, rcx
0x140037d3b  lea     rcx, [rsp+0D8h+var_90]; void *
0x140037d40  mov     rbp, r9
0x140037d43  lea     r8d, [rdx+68h]; Size
0x140037d47  call    memset
0x140037d4c  lea     rax, VmxpGetDeviceParameterBinaryCallback
0x140037d53  mov     qword ptr [rdi], 0
0x140037d5a  xorps   xmm0, xmm0
0x140037d5d  mov     [rsp+0D8h+var_98], rax
0x140037d62  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140037d69  mov     [rsp+0D8h+var_90], 104h
0x140037d71  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x140037d76  mov     [rsp+0D8h+var_88], rbx
0x140037d7b  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x140037d80  mov     [rsp+0D8h+var_80], rdi
0x140037d85  mov     [rsp+0D8h+var_78], 3000000h
0x140037d8d  call    cs:__imp_RtlInitUnicodeString
0x140037d94  nop     dword ptr [rax+rax+00h]
0x140037d99  lea     rcx, [rsp+0D8h+DestinationString]; SystemRoutineName
0x140037d9e  call    cs:__imp_MmGetSystemRoutineAddress
0x140037da5  nop     dword ptr [rax+rax+00h]
0x140037daa  mov     r9, rbp
0x140037dad  mov     [rsp+0D8h+var_B8], 0
0x140037db6  test    rax, rax
0x140037db9  lea     r8, [rsp+0D8h+var_98]
0x140037dbe  mov     rdx, rsi
0x140037dc1  mov     ecx, 40000000h
0x140037dc6  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140037dce  call    _guard_dispatch_icall
0x140037dd3  add     rsp, 0B8h
0x140037dda  pop     rdi
0x140037ddb  pop     rsi
0x140037ddc  pop     rbp
0x140037ddd  pop     rbx
0x140037dde  retn
```
