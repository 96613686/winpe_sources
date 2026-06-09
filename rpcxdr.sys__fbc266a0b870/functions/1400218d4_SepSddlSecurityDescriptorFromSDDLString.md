# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400218d4`
- end: `0x140021a72`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400210fc`

## callees

- `0x140015680`
- `0x140015b40`
- `0x1400212b4`
- `0x1400218d4`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021910`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021910`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021900`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021900`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002199b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002199b`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400219bc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021a49`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400219bc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140021a49`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400219d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400219d4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140021982`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140021982`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a61`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021a61`

## string_xrefs

- `0x1400218eb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400218d4  mov     [rsp-18h+arg_0], rbx
0x1400218d9  mov     [rsp-18h+BufferLength], edx
0x1400218dd  push    rbp
0x1400218de  push    rdi
0x1400218df  push    r14
0x1400218e1  mov     rbp, rsp
0x1400218e4  sub     rsp, 70h
0x1400218e8  mov     rbx, rcx
0x1400218eb  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400218f2  xorps   xmm0, xmm0
0x1400218f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400218f9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400218fd  mov     r14, r8
0x140021900  call    cs:__imp_RtlInitUnicodeString
0x140021907  nop     dword ptr [rax+rax+00h]
0x14002190c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140021910  call    cs:__imp_MmGetSystemRoutineAddress
0x140021917  nop     dword ptr [rax+rax+00h]
0x14002191c  mov     rcx, rbx
0x14002191f  test    rax, rax
0x140021922  jz      short loc_140021948
0x140021924  xor     r9d, r9d
0x140021927  mov     r8, r14
0x14002192a  lea     edx, [r9+1]
0x14002192e  call    _guard_dispatch_icall
0x140021933  test    eax, eax
0x140021935  js      loc_140021A1E
0x14002193b  mov     rcx, [r14]
0x14002193e  or      word ptr [rcx+2], 8
0x140021943  jmp     loc_140021A1E
0x140021948  xor     eax, eax
0x14002194a  lea     r9, [rbp+Dacl]
0x14002194e  xorps   xmm0, xmm0
0x140021951  mov     [rbp+var_8], rax
0x140021955  lea     r8, [rbp+arg_18]
0x140021959  mov     [rbp+arg_18], eax
0x14002195c  movups  [rbp+SecurityDescriptor], xmm0
0x140021960  mov     [rbp+BufferLength], eax
0x140021963  xor     edi, edi
0x140021965  movups  [rbp+var_18], xmm0
0x140021969  mov     [rbp+Dacl], rax
0x14002196d  mov     [r14], rax
0x140021970  call    SepSddlDaclFromSDDLString
0x140021975  mov     ebx, eax
0x140021977  test    eax, eax
0x140021979  js      short loc_1400219ED
0x14002197b  lea     edx, [rdi+1]; Revision
0x14002197e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021982  call    cs:__imp_RtlCreateSecurityDescriptor
0x140021989  nop     dword ptr [rax+rax+00h]
0x14002198e  mov     r8, [rbp+Dacl]; Dacl
0x140021992  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140021996  xor     r9d, r9d; DaclDefaulted
0x140021999  mov     dl, 1; DaclPresent
0x14002199b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400219a2  nop     dword ptr [rax+rax+00h]
0x1400219a7  movzx   eax, word ptr [rbp+arg_18]
0x1400219ab  lea     r8, [rbp+BufferLength]; BufferLength
0x1400219af  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400219b3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400219b7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400219b9  mov     [rbp+BufferLength], edi
0x1400219bc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400219c3  nop     dword ptr [rax+rax+00h]
0x1400219c8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x1400219cb  lea     ecx, [rdi+1]; PoolType
0x1400219ce  mov     r8d, 64536553h; Tag
0x1400219d4  call    cs:__imp_ExAllocatePoolWithTag
0x1400219db  nop     dword ptr [rax+rax+00h]
0x1400219e0  mov     rdi, rax
0x1400219e3  test    rax, rax
0x1400219e6  jnz     short loc_140021A30
0x1400219e8  mov     ebx, 0C000009Ah
0x1400219ed  cmp     [rbp+Dacl], 0
0x1400219f2  jz      short loc_140021A06
0x1400219f4  mov     rcx, [rbp+Dacl]; P
0x1400219f8  xor     edx, edx; Tag
0x1400219fa  call    cs:__imp_ExFreePoolWithTag
0x140021a01  nop     dword ptr [rax+rax+00h]
0x140021a06  test    rdi, rdi
0x140021a09  jz      short loc_140021A1C
0x140021a0b  xor     edx, edx; Tag
0x140021a0d  mov     rcx, rdi; P
0x140021a10  call    cs:__imp_ExFreePoolWithTag
0x140021a17  nop     dword ptr [rax+rax+00h]
0x140021a1c  mov     eax, ebx
0x140021a1e  mov     rbx, [rsp+70h+arg_0]
0x140021a26  add     rsp, 70h
0x140021a2a  pop     r14
0x140021a2c  pop     rdi
0x140021a2d  pop     rbp
0x140021a2e  retn
0x140021a30  mov     r8d, [rbp+BufferLength]; Size
0x140021a34  xor     edx, edx; Val
0x140021a36  mov     rcx, rdi; void *
0x140021a39  call    memset
0x140021a3e  lea     r8, [rbp+BufferLength]; BufferLength
0x140021a42  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140021a45  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140021a49  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140021a50  nop     dword ptr [rax+rax+00h]
0x140021a55  mov     ebx, eax
0x140021a57  test    eax, eax
0x140021a59  js      short loc_1400219ED
0x140021a5b  mov     rcx, [rbp+Dacl]; P
0x140021a5f  xor     edx, edx; Tag
0x140021a61  call    cs:__imp_ExFreePoolWithTag
0x140021a68  nop     dword ptr [rax+rax+00h]
0x140021a6d  mov     [r14], rdi
0x140021a70  jmp     short loc_140021A1C
```
