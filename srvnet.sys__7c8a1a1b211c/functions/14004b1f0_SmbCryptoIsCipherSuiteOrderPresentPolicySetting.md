# SmbCryptoIsCipherSuiteOrderPresentPolicySetting

- ea: `0x14004b1f0`
- end: `0x14004b2b9`
- name: `SmbCryptoIsCipherSuiteOrderPresentPolicySetting`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14002a4c0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14004b299`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004b299`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14004b281`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b252`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004b252`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b262`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004b262`

## string_xrefs

- `0x14004b230`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall SmbCryptoIsCipherSuiteOrderPresentPolicySetting(__int64 a1)
{
  PVOID SystemRoutineAddress; // rax
  unsigned int v3; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v7[14]; // [rsp+50h] [rbp-19h] BYREF

  memset(v7, 0, sizeof(v7));
  LODWORD(v7[1]) = 308;
  LODWORD(v7[4]) = 117440512;
  v7[2] = L"CipherSuiteOrder";
  LODWORD(v7[6]) = 0;
  v7[3] = &UnicodeString;
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v3 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(0, a1, v7, 0, 0);
  RtlFreeUnicodeString(&UnicodeString);
  return v3;
}

```

## disassembly

```asm
0x14004b1f0  mov     [rsp-8+arg_0], rbx
0x14004b1f5  push    rbp
0x14004b1f6  lea     rbp, [rsp-57h]
0x14004b1fb  sub     rsp, 0C0h
0x14004b202  xor     edx, edx; Val
0x14004b204  mov     rbx, rcx
0x14004b207  lea     rcx, [rbp+57h+var_70]; void *
0x14004b20b  lea     r8d, [rdx+70h]; Size
0x14004b20f  call    memset
0x14004b214  xorps   xmm0, xmm0
0x14004b217  mov     [rbp+57h+var_68], 134h
0x14004b21e  lea     rax, aCiphersuiteord; "CipherSuiteOrder"
0x14004b225  mov     [rbp+57h+var_50], 7000000h
0x14004b22c  mov     [rbp+57h+var_60], rax
0x14004b230  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14004b237  lea     rax, [rbp+57h+UnicodeString]
0x14004b23b  mov     [rbp+57h+var_40], 0
0x14004b242  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004b246  mov     [rbp+57h+var_58], rax
0x14004b24a  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x14004b24e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004b252  call    cs:__imp_RtlInitUnicodeString
0x14004b259  nop     dword ptr [rax+rax+00h]
0x14004b25e  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14004b262  call    cs:__imp_MmGetSystemRoutineAddress
0x14004b269  nop     dword ptr [rax+rax+00h]
0x14004b26e  lea     r8, [rbp+57h+var_70]
0x14004b272  mov     [rsp+0C0h+var_A0], 0
0x14004b27b  test    rax, rax
0x14004b27e  mov     rdx, rbx
0x14004b281  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14004b289  xor     r9d, r9d
0x14004b28c  xor     ecx, ecx
0x14004b28e  call    _guard_dispatch_icall
0x14004b293  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14004b297  mov     ebx, eax
0x14004b299  call    cs:__imp_RtlFreeUnicodeString
0x14004b2a0  nop     dword ptr [rax+rax+00h]
0x14004b2a5  mov     eax, ebx
0x14004b2a7  mov     rbx, [rsp+0C0h+arg_0]
0x14004b2af  add     rsp, 0C0h
0x14004b2b6  pop     rbp
0x14004b2b7  retn
```
