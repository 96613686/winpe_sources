# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140018b14`
- end: `0x140018cb2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001833c`

## callees

- `0x1400050f0`
- `0x1400054c0`
- `0x1400184f4`
- `0x140018b14`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140018bc2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140018bc2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140018bdb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140018bdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ca1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ca1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018b50`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140018b50`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018bfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018c89`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018bfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140018c89`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018c14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140018c14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018b40`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018b40`

## string_xrefs

- `0x140018b2b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140018b14  mov     [rsp-18h+arg_0], rbx
0x140018b19  mov     [rsp-18h+BufferLength], edx
0x140018b1d  push    rbp
0x140018b1e  push    rdi
0x140018b1f  push    r14
0x140018b21  mov     rbp, rsp
0x140018b24  sub     rsp, 70h
0x140018b28  mov     rbx, rcx
0x140018b2b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140018b32  xorps   xmm0, xmm0
0x140018b35  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018b39  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140018b3d  mov     r14, r8
0x140018b40  call    cs:__imp_RtlInitUnicodeString
0x140018b47  nop     dword ptr [rax+rax+00h]
0x140018b4c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140018b50  call    cs:__imp_MmGetSystemRoutineAddress
0x140018b57  nop     dword ptr [rax+rax+00h]
0x140018b5c  mov     rcx, rbx
0x140018b5f  test    rax, rax
0x140018b62  jz      short loc_140018B88
0x140018b64  xor     r9d, r9d
0x140018b67  mov     r8, r14
0x140018b6a  lea     edx, [r9+1]
0x140018b6e  call    _guard_dispatch_icall
0x140018b73  test    eax, eax
0x140018b75  js      loc_140018C5E
0x140018b7b  mov     rcx, [r14]
0x140018b7e  or      word ptr [rcx+2], 8
0x140018b83  jmp     loc_140018C5E
0x140018b88  xor     eax, eax
0x140018b8a  lea     r9, [rbp+Dacl]
0x140018b8e  xorps   xmm0, xmm0
0x140018b91  mov     [rbp+var_8], rax
0x140018b95  lea     r8, [rbp+arg_18]
0x140018b99  mov     [rbp+arg_18], eax
0x140018b9c  movups  [rbp+SecurityDescriptor], xmm0
0x140018ba0  mov     [rbp+BufferLength], eax
0x140018ba3  xor     edi, edi
0x140018ba5  movups  [rbp+var_18], xmm0
0x140018ba9  mov     [rbp+Dacl], rax
0x140018bad  mov     [r14], rax
0x140018bb0  call    SepSddlDaclFromSDDLString
0x140018bb5  mov     ebx, eax
0x140018bb7  test    eax, eax
0x140018bb9  js      short loc_140018C2D
0x140018bbb  lea     edx, [rdi+1]; Revision
0x140018bbe  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140018bc2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140018bc9  nop     dword ptr [rax+rax+00h]
0x140018bce  mov     r8, [rbp+Dacl]; Dacl
0x140018bd2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140018bd6  xor     r9d, r9d; DaclDefaulted
0x140018bd9  mov     dl, 1; DaclPresent
0x140018bdb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140018be2  nop     dword ptr [rax+rax+00h]
0x140018be7  movzx   eax, word ptr [rbp+arg_18]
0x140018beb  lea     r8, [rbp+BufferLength]; BufferLength
0x140018bef  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140018bf3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140018bf7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140018bf9  mov     [rbp+BufferLength], edi
0x140018bfc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140018c03  nop     dword ptr [rax+rax+00h]
0x140018c08  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140018c0b  lea     ecx, [rdi+1]; PoolType
0x140018c0e  mov     r8d, 64536553h; Tag
0x140018c14  call    cs:__imp_ExAllocatePoolWithTag
0x140018c1b  nop     dword ptr [rax+rax+00h]
0x140018c20  mov     rdi, rax
0x140018c23  test    rax, rax
0x140018c26  jnz     short loc_140018C70
0x140018c28  mov     ebx, 0C000009Ah
0x140018c2d  cmp     [rbp+Dacl], 0
0x140018c32  jz      short loc_140018C46
0x140018c34  mov     rcx, [rbp+Dacl]; P
0x140018c38  xor     edx, edx; Tag
0x140018c3a  call    cs:__imp_ExFreePoolWithTag
0x140018c41  nop     dword ptr [rax+rax+00h]
0x140018c46  test    rdi, rdi
0x140018c49  jz      short loc_140018C5C
0x140018c4b  xor     edx, edx; Tag
0x140018c4d  mov     rcx, rdi; P
0x140018c50  call    cs:__imp_ExFreePoolWithTag
0x140018c57  nop     dword ptr [rax+rax+00h]
0x140018c5c  mov     eax, ebx
0x140018c5e  mov     rbx, [rsp+70h+arg_0]
0x140018c66  add     rsp, 70h
0x140018c6a  pop     r14
0x140018c6c  pop     rdi
0x140018c6d  pop     rbp
0x140018c6e  retn
0x140018c70  mov     r8d, [rbp+BufferLength]; Size
0x140018c74  xor     edx, edx; Val
0x140018c76  mov     rcx, rdi; void *
0x140018c79  call    memset
0x140018c7e  lea     r8, [rbp+BufferLength]; BufferLength
0x140018c82  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140018c85  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140018c89  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140018c90  nop     dword ptr [rax+rax+00h]
0x140018c95  mov     ebx, eax
0x140018c97  test    eax, eax
0x140018c99  js      short loc_140018C2D
0x140018c9b  mov     rcx, [rbp+Dacl]; P
0x140018c9f  xor     edx, edx; Tag
0x140018ca1  call    cs:__imp_ExFreePoolWithTag
0x140018ca8  nop     dword ptr [rax+rax+00h]
0x140018cad  mov     [r14], rdi
0x140018cb0  jmp     short loc_140018C5C
```
