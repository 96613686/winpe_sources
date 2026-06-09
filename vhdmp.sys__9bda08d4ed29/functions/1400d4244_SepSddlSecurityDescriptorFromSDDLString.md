# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400d4244`
- end: `0x1400d43e2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d3a84`

## callees

- `0x14005dc30`
- `0x14005e100`
- `0x1400d3c3c`
- `0x1400d4244`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400d4280`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400d4280`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400d42f2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400d42f2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400d430b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400d430b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d4270`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d4270`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d436a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4380`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d436a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4380`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43d1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d4344`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d4344`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d432c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d43b9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d432c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d43b9`

## string_xrefs

- `0x1400d425b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SepSddlSecurityDescriptorFromSDDLString(__int64 a1, ULONG a2, __int64 a3)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, __int64, __int64); // rax
  __int64 v6; // rdx
  __int64 result; // rax
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
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, __int64, __int64))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
  {
    v14 = 0;
    v16 = 0;
    memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
    BufferLength = 0;
    v8 = 0;
    Dacl = 0;
    *(_QWORD *)a3 = 0;
    v9 = SepSddlDaclFromSDDLString(a1, v6, &v16, &Dacl);
    if ( v9 >= 0 )
    {
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
      WORD1(SecurityDescriptor[0]) |= v16;
      BufferLength = 0;
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x64536553u);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, BufferLength);
        v9 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v8, &BufferLength);
        if ( v9 >= 0 )
        {
          ExFreePoolWithTag(Dacl, 0);
          *(_QWORD *)a3 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        v9 = -1073741670;
      }
    }
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v9;
  }
  result = SystemRoutineAddress(a1, 1, a3);
  if ( (int)result >= 0 )
    *(_WORD *)(*(_QWORD *)a3 + 2LL) |= 8u;
  return result;
}

```

## disassembly

```asm
0x1400d4244  mov     [rsp-18h+arg_0], rbx
0x1400d4249  mov     [rsp-18h+BufferLength], edx
0x1400d424d  push    rbp
0x1400d424e  push    rdi
0x1400d424f  push    r14
0x1400d4251  mov     rbp, rsp
0x1400d4254  sub     rsp, 70h
0x1400d4258  mov     rbx, rcx
0x1400d425b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400d4262  xorps   xmm0, xmm0
0x1400d4265  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d4269  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d426d  mov     r14, r8
0x1400d4270  call    cs:__imp_RtlInitUnicodeString
0x1400d4277  nop     dword ptr [rax+rax+00h]
0x1400d427c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400d4280  call    cs:__imp_MmGetSystemRoutineAddress
0x1400d4287  nop     dword ptr [rax+rax+00h]
0x1400d428c  mov     rcx, rbx
0x1400d428f  test    rax, rax
0x1400d4292  jz      short loc_1400D42B8
0x1400d4294  xor     r9d, r9d
0x1400d4297  mov     r8, r14
0x1400d429a  lea     edx, [r9+1]
0x1400d429e  call    _guard_dispatch_icall
0x1400d42a3  test    eax, eax
0x1400d42a5  js      loc_1400D438E
0x1400d42ab  mov     rcx, [r14]
0x1400d42ae  or      word ptr [rcx+2], 8
0x1400d42b3  jmp     loc_1400D438E
0x1400d42b8  xor     eax, eax
0x1400d42ba  lea     r9, [rbp+Dacl]
0x1400d42be  xorps   xmm0, xmm0
0x1400d42c1  mov     [rbp+var_8], rax
0x1400d42c5  lea     r8, [rbp+arg_18]
0x1400d42c9  mov     [rbp+arg_18], eax
0x1400d42cc  movups  [rbp+SecurityDescriptor], xmm0
0x1400d42d0  mov     [rbp+BufferLength], eax
0x1400d42d3  xor     edi, edi
0x1400d42d5  movups  [rbp+var_18], xmm0
0x1400d42d9  mov     [rbp+Dacl], rax
0x1400d42dd  mov     [r14], rax
0x1400d42e0  call    SepSddlDaclFromSDDLString
0x1400d42e5  mov     ebx, eax
0x1400d42e7  test    eax, eax
0x1400d42e9  js      short loc_1400D435D
0x1400d42eb  lea     edx, [rdi+1]; Revision
0x1400d42ee  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d42f2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400d42f9  nop     dword ptr [rax+rax+00h]
0x1400d42fe  mov     r8, [rbp+Dacl]; Dacl
0x1400d4302  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d4306  xor     r9d, r9d; DaclDefaulted
0x1400d4309  mov     dl, 1; DaclPresent
0x1400d430b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400d4312  nop     dword ptr [rax+rax+00h]
0x1400d4317  movzx   eax, word ptr [rbp+arg_18]
0x1400d431b  lea     r8, [rbp+BufferLength]; BufferLength
0x1400d431f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400d4323  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400d4327  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400d4329  mov     [rbp+BufferLength], edi
0x1400d432c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400d4333  nop     dword ptr [rax+rax+00h]
0x1400d4338  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x1400d433b  lea     ecx, [rdi+1]; PoolType
0x1400d433e  mov     r8d, 64536553h; Tag
0x1400d4344  call    cs:__imp_ExAllocatePoolWithTag
0x1400d434b  nop     dword ptr [rax+rax+00h]
0x1400d4350  mov     rdi, rax
0x1400d4353  test    rax, rax
0x1400d4356  jnz     short loc_1400D43A0
0x1400d4358  mov     ebx, 0C000009Ah
0x1400d435d  cmp     [rbp+Dacl], 0
0x1400d4362  jz      short loc_1400D4376
0x1400d4364  mov     rcx, [rbp+Dacl]; P
0x1400d4368  xor     edx, edx; Tag
0x1400d436a  call    cs:__imp_ExFreePoolWithTag
0x1400d4371  nop     dword ptr [rax+rax+00h]
0x1400d4376  test    rdi, rdi
0x1400d4379  jz      short loc_1400D438C
0x1400d437b  xor     edx, edx; Tag
0x1400d437d  mov     rcx, rdi; P
0x1400d4380  call    cs:__imp_ExFreePoolWithTag
0x1400d4387  nop     dword ptr [rax+rax+00h]
0x1400d438c  mov     eax, ebx
0x1400d438e  mov     rbx, [rsp+70h+arg_0]
0x1400d4396  add     rsp, 70h
0x1400d439a  pop     r14
0x1400d439c  pop     rdi
0x1400d439d  pop     rbp
0x1400d439e  retn
0x1400d43a0  mov     r8d, [rbp+BufferLength]; Size
0x1400d43a4  xor     edx, edx; Val
0x1400d43a6  mov     rcx, rdi; void *
0x1400d43a9  call    memset
0x1400d43ae  lea     r8, [rbp+BufferLength]; BufferLength
0x1400d43b2  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400d43b5  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400d43b9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400d43c0  nop     dword ptr [rax+rax+00h]
0x1400d43c5  mov     ebx, eax
0x1400d43c7  test    eax, eax
0x1400d43c9  js      short loc_1400D435D
0x1400d43cb  mov     rcx, [rbp+Dacl]; P
0x1400d43cf  xor     edx, edx; Tag
0x1400d43d1  call    cs:__imp_ExFreePoolWithTag
0x1400d43d8  nop     dword ptr [rax+rax+00h]
0x1400d43dd  mov     [r14], rdi
0x1400d43e0  jmp     short loc_1400D438C
```
