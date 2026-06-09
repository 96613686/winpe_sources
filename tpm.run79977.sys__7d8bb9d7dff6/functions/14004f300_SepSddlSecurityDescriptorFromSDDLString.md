# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x14004f300`
- end: `0x14004f48e`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004eb48`

## callees

- `0x140039780`
- `0x140039b40`
- `0x14004ed00`
- `0x14004f300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004f416`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f47d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f416`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f42c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f47d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004f3b7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004f3b7`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004f3d8`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004f465`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004f3d8`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14004f465`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004f3f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004f3f0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004f39e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004f39e`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004f33c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004f33c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004f32c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004f32c`

## string_xrefs

- `0x14004f317`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SepSddlSecurityDescriptorFromSDDLString(__int64 a1, ULONG a2, _QWORD *a3)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, __int64, _QWORD *); // rax
  __int64 v6; // rdx
  void *v8; // rdi
  NTSTATUS v9; // ebx
  PVOID PoolWithTag; // rax
  PACL Dacl; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  ULONG BufferLength; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF

  BufferLength = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SeConvertStringSecurityDescriptorToSecurityDescriptor");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, __int64, _QWORD *))MmGetSystemRoutineAddress(&DestinationString);
  if ( SystemRoutineAddress )
    return SystemRoutineAddress(a1, 1, a3);
  v14 = 0;
  v16 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  BufferLength = 0;
  v8 = 0;
  Dacl = 0;
  *a3 = 0;
  v9 = SepSddlDaclFromSDDLString(a1, v6, &v16, &Dacl);
  if ( v9 < 0 )
    goto LABEL_6;
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
  WORD1(SecurityDescriptor[0]) |= v16;
  BufferLength = 0;
  RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x64536553u);
  v8 = PoolWithTag;
  if ( !PoolWithTag )
  {
    v9 = -1073741670;
LABEL_6:
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v9;
  }
  memset(PoolWithTag, 0, BufferLength);
  v9 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v8, &BufferLength);
  if ( v9 < 0 )
    goto LABEL_6;
  ExFreePoolWithTag(Dacl, 0);
  *a3 = v8;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14004f300  mov     [rsp-18h+arg_0], rbx
0x14004f305  mov     [rsp-18h+BufferLength], edx
0x14004f309  push    rbp
0x14004f30a  push    rdi
0x14004f30b  push    r14
0x14004f30d  mov     rbp, rsp
0x14004f310  sub     rsp, 70h
0x14004f314  mov     rbx, rcx
0x14004f317  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x14004f31e  xorps   xmm0, xmm0
0x14004f321  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004f325  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004f329  mov     r14, r8
0x14004f32c  call    cs:__imp_RtlInitUnicodeString
0x14004f333  nop     dword ptr [rax+rax+00h]
0x14004f338  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x14004f33c  call    cs:__imp_MmGetSystemRoutineAddress
0x14004f343  nop     dword ptr [rax+rax+00h]
0x14004f348  mov     rcx, rbx
0x14004f34b  test    rax, rax
0x14004f34e  jz      short loc_14004F364
0x14004f350  xor     r9d, r9d
0x14004f353  mov     r8, r14
0x14004f356  lea     edx, [r9+1]
0x14004f35a  call    _guard_dispatch_icall
0x14004f35f  jmp     loc_14004F43A
0x14004f364  xor     eax, eax
0x14004f366  lea     r9, [rbp+Dacl]
0x14004f36a  xorps   xmm0, xmm0
0x14004f36d  mov     [rbp+var_8], rax
0x14004f371  lea     r8, [rbp+arg_18]
0x14004f375  mov     [rbp+arg_18], eax
0x14004f378  movups  [rbp+SecurityDescriptor], xmm0
0x14004f37c  mov     [rbp+BufferLength], eax
0x14004f37f  xor     edi, edi
0x14004f381  movups  [rbp+var_18], xmm0
0x14004f385  mov     [rbp+Dacl], rax
0x14004f389  mov     [r14], rax
0x14004f38c  call    SepSddlDaclFromSDDLString
0x14004f391  mov     ebx, eax
0x14004f393  test    eax, eax
0x14004f395  js      short loc_14004F409
0x14004f397  lea     edx, [rdi+1]; Revision
0x14004f39a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14004f39e  call    cs:__imp_RtlCreateSecurityDescriptor
0x14004f3a5  nop     dword ptr [rax+rax+00h]
0x14004f3aa  mov     r8, [rbp+Dacl]; Dacl
0x14004f3ae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14004f3b2  xor     r9d, r9d; DaclDefaulted
0x14004f3b5  mov     dl, 1; DaclPresent
0x14004f3b7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14004f3be  nop     dword ptr [rax+rax+00h]
0x14004f3c3  movzx   eax, word ptr [rbp+arg_18]
0x14004f3c7  lea     r8, [rbp+BufferLength]; BufferLength
0x14004f3cb  or      word ptr [rbp+SecurityDescriptor+2], ax
0x14004f3cf  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14004f3d3  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14004f3d5  mov     [rbp+BufferLength], edi
0x14004f3d8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14004f3df  nop     dword ptr [rax+rax+00h]
0x14004f3e4  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x14004f3e7  lea     ecx, [rdi+1]; PoolType
0x14004f3ea  mov     r8d, 64536553h; Tag
0x14004f3f0  call    cs:__imp_ExAllocatePoolWithTag
0x14004f3f7  nop     dword ptr [rax+rax+00h]
0x14004f3fc  mov     rdi, rax
0x14004f3ff  test    rax, rax
0x14004f402  jnz     short loc_14004F44C
0x14004f404  mov     ebx, 0C000009Ah
0x14004f409  cmp     [rbp+Dacl], 0
0x14004f40e  jz      short loc_14004F422
0x14004f410  mov     rcx, [rbp+Dacl]; P
0x14004f414  xor     edx, edx; Tag
0x14004f416  call    cs:__imp_ExFreePoolWithTag
0x14004f41d  nop     dword ptr [rax+rax+00h]
0x14004f422  test    rdi, rdi
0x14004f425  jz      short loc_14004F438
0x14004f427  xor     edx, edx; Tag
0x14004f429  mov     rcx, rdi; P
0x14004f42c  call    cs:__imp_ExFreePoolWithTag
0x14004f433  nop     dword ptr [rax+rax+00h]
0x14004f438  mov     eax, ebx
0x14004f43a  mov     rbx, [rsp+70h+arg_0]
0x14004f442  add     rsp, 70h
0x14004f446  pop     r14
0x14004f448  pop     rdi
0x14004f449  pop     rbp
0x14004f44a  retn
0x14004f44c  mov     r8d, [rbp+BufferLength]; Size
0x14004f450  xor     edx, edx; Val
0x14004f452  mov     rcx, rdi; void *
0x14004f455  call    memset
0x14004f45a  lea     r8, [rbp+BufferLength]; BufferLength
0x14004f45e  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x14004f461  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14004f465  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14004f46c  nop     dword ptr [rax+rax+00h]
0x14004f471  mov     ebx, eax
0x14004f473  test    eax, eax
0x14004f475  js      short loc_14004F409
0x14004f477  mov     rcx, [rbp+Dacl]; P
0x14004f47b  xor     edx, edx; Tag
0x14004f47d  call    cs:__imp_ExFreePoolWithTag
0x14004f484  nop     dword ptr [rax+rax+00h]
0x14004f489  mov     [r14], rdi
0x14004f48c  jmp     short loc_14004F438
```
