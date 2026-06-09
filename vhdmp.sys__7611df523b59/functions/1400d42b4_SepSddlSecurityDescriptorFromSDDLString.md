# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400d42b4`
- end: `0x1400d4452`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d3af4`

## callees

- `0x14005d840`
- `0x14005dd00`
- `0x1400d3cac`
- `0x1400d42b4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400d42f0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400d42f0`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400d4362`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400d4362`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400d437b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400d437b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d42e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d42e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4441`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d43f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d4441`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d43b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d43b4`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d439c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d4429`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d439c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400d4429`

## string_xrefs

- `0x1400d42cb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400d42b4  mov     [rsp-18h+arg_0], rbx
0x1400d42b9  mov     [rsp-18h+BufferLength], edx
0x1400d42bd  push    rbp
0x1400d42be  push    rdi
0x1400d42bf  push    r14
0x1400d42c1  mov     rbp, rsp
0x1400d42c4  sub     rsp, 70h
0x1400d42c8  mov     rbx, rcx
0x1400d42cb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400d42d2  xorps   xmm0, xmm0
0x1400d42d5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400d42d9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400d42dd  mov     r14, r8
0x1400d42e0  call    cs:__imp_RtlInitUnicodeString
0x1400d42e7  nop     dword ptr [rax+rax+00h]
0x1400d42ec  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400d42f0  call    cs:__imp_MmGetSystemRoutineAddress
0x1400d42f7  nop     dword ptr [rax+rax+00h]
0x1400d42fc  mov     rcx, rbx
0x1400d42ff  test    rax, rax
0x1400d4302  jz      short loc_1400D4328
0x1400d4304  xor     r9d, r9d
0x1400d4307  mov     r8, r14
0x1400d430a  lea     edx, [r9+1]
0x1400d430e  call    _guard_dispatch_icall
0x1400d4313  test    eax, eax
0x1400d4315  js      loc_1400D43FE
0x1400d431b  mov     rcx, [r14]
0x1400d431e  or      word ptr [rcx+2], 8
0x1400d4323  jmp     loc_1400D43FE
0x1400d4328  xor     eax, eax
0x1400d432a  lea     r9, [rbp+Dacl]
0x1400d432e  xorps   xmm0, xmm0
0x1400d4331  mov     [rbp+var_8], rax
0x1400d4335  lea     r8, [rbp+arg_18]
0x1400d4339  mov     [rbp+arg_18], eax
0x1400d433c  movups  [rbp+SecurityDescriptor], xmm0
0x1400d4340  mov     [rbp+BufferLength], eax
0x1400d4343  xor     edi, edi
0x1400d4345  movups  [rbp+var_18], xmm0
0x1400d4349  mov     [rbp+Dacl], rax
0x1400d434d  mov     [r14], rax
0x1400d4350  call    SepSddlDaclFromSDDLString
0x1400d4355  mov     ebx, eax
0x1400d4357  test    eax, eax
0x1400d4359  js      short loc_1400D43CD
0x1400d435b  lea     edx, [rdi+1]; Revision
0x1400d435e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d4362  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400d4369  nop     dword ptr [rax+rax+00h]
0x1400d436e  mov     r8, [rbp+Dacl]; Dacl
0x1400d4372  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400d4376  xor     r9d, r9d; DaclDefaulted
0x1400d4379  mov     dl, 1; DaclPresent
0x1400d437b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400d4382  nop     dword ptr [rax+rax+00h]
0x1400d4387  movzx   eax, word ptr [rbp+arg_18]
0x1400d438b  lea     r8, [rbp+BufferLength]; BufferLength
0x1400d438f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400d4393  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400d4397  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400d4399  mov     [rbp+BufferLength], edi
0x1400d439c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400d43a3  nop     dword ptr [rax+rax+00h]
0x1400d43a8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x1400d43ab  lea     ecx, [rdi+1]; PoolType
0x1400d43ae  mov     r8d, 64536553h; Tag
0x1400d43b4  call    cs:__imp_ExAllocatePoolWithTag
0x1400d43bb  nop     dword ptr [rax+rax+00h]
0x1400d43c0  mov     rdi, rax
0x1400d43c3  test    rax, rax
0x1400d43c6  jnz     short loc_1400D4410
0x1400d43c8  mov     ebx, 0C000009Ah
0x1400d43cd  cmp     [rbp+Dacl], 0
0x1400d43d2  jz      short loc_1400D43E6
0x1400d43d4  mov     rcx, [rbp+Dacl]; P
0x1400d43d8  xor     edx, edx; Tag
0x1400d43da  call    cs:__imp_ExFreePoolWithTag
0x1400d43e1  nop     dword ptr [rax+rax+00h]
0x1400d43e6  test    rdi, rdi
0x1400d43e9  jz      short loc_1400D43FC
0x1400d43eb  xor     edx, edx; Tag
0x1400d43ed  mov     rcx, rdi; P
0x1400d43f0  call    cs:__imp_ExFreePoolWithTag
0x1400d43f7  nop     dword ptr [rax+rax+00h]
0x1400d43fc  mov     eax, ebx
0x1400d43fe  mov     rbx, [rsp+70h+arg_0]
0x1400d4406  add     rsp, 70h
0x1400d440a  pop     r14
0x1400d440c  pop     rdi
0x1400d440d  pop     rbp
0x1400d440e  retn
0x1400d4410  mov     r8d, [rbp+BufferLength]; Size
0x1400d4414  xor     edx, edx; Val
0x1400d4416  mov     rcx, rdi; void *
0x1400d4419  call    memset
0x1400d441e  lea     r8, [rbp+BufferLength]; BufferLength
0x1400d4422  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400d4425  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400d4429  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400d4430  nop     dword ptr [rax+rax+00h]
0x1400d4435  mov     ebx, eax
0x1400d4437  test    eax, eax
0x1400d4439  js      short loc_1400D43CD
0x1400d443b  mov     rcx, [rbp+Dacl]; P
0x1400d443f  xor     edx, edx; Tag
0x1400d4441  call    cs:__imp_ExFreePoolWithTag
0x1400d4448  nop     dword ptr [rax+rax+00h]
0x1400d444d  mov     [r14], rdi
0x1400d4450  jmp     short loc_1400D43FC
```
