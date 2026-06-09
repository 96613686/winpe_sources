# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140020d14`
- end: `0x140020eb2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002052c`

## callees

- `0x14000f9e0`
- `0x14000fd40`
- `0x1400206e4`
- `0x140020d14`

## import_xrefs

- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140020ddb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140020ddb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140020dfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140020e89`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140020dfc`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140020e89`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140020dc2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140020dc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020e3a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020ea1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020e14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140020e14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020d40`
- `ntoskrnl!RtlInitUnicodeString` at `0x140020d40`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020d50`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140020d50`

## string_xrefs

- `0x140020d2b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140020d14  mov     [rsp-18h+arg_0], rbx
0x140020d19  mov     [rsp-18h+BufferLength], edx
0x140020d1d  push    rbp
0x140020d1e  push    rdi
0x140020d1f  push    r14
0x140020d21  mov     rbp, rsp
0x140020d24  sub     rsp, 70h
0x140020d28  mov     rbx, rcx
0x140020d2b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140020d32  xorps   xmm0, xmm0
0x140020d35  lea     rcx, [rbp+DestinationString]; DestinationString
0x140020d39  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140020d3d  mov     r14, r8
0x140020d40  call    cs:__imp_RtlInitUnicodeString
0x140020d47  nop     dword ptr [rax+rax+00h]
0x140020d4c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140020d50  call    cs:__imp_MmGetSystemRoutineAddress
0x140020d57  nop     dword ptr [rax+rax+00h]
0x140020d5c  mov     rcx, rbx
0x140020d5f  test    rax, rax
0x140020d62  jz      short loc_140020D88
0x140020d64  xor     r9d, r9d
0x140020d67  mov     r8, r14
0x140020d6a  lea     edx, [r9+1]
0x140020d6e  call    _guard_dispatch_icall
0x140020d73  test    eax, eax
0x140020d75  js      loc_140020E5E
0x140020d7b  mov     rcx, [r14]
0x140020d7e  or      word ptr [rcx+2], 8
0x140020d83  jmp     loc_140020E5E
0x140020d88  xor     eax, eax
0x140020d8a  lea     r9, [rbp+Dacl]
0x140020d8e  xorps   xmm0, xmm0
0x140020d91  mov     [rbp+var_8], rax
0x140020d95  lea     r8, [rbp+arg_18]
0x140020d99  mov     [rbp+arg_18], eax
0x140020d9c  movups  [rbp+SecurityDescriptor], xmm0
0x140020da0  mov     [rbp+BufferLength], eax
0x140020da3  xor     edi, edi
0x140020da5  movups  [rbp+var_18], xmm0
0x140020da9  mov     [rbp+Dacl], rax
0x140020dad  mov     [r14], rax
0x140020db0  call    SepSddlDaclFromSDDLString
0x140020db5  mov     ebx, eax
0x140020db7  test    eax, eax
0x140020db9  js      short loc_140020E2D
0x140020dbb  lea     edx, [rdi+1]; Revision
0x140020dbe  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140020dc2  call    cs:__imp_RtlCreateSecurityDescriptor
0x140020dc9  nop     dword ptr [rax+rax+00h]
0x140020dce  mov     r8, [rbp+Dacl]; Dacl
0x140020dd2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140020dd6  xor     r9d, r9d; DaclDefaulted
0x140020dd9  mov     dl, 1; DaclPresent
0x140020ddb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140020de2  nop     dword ptr [rax+rax+00h]
0x140020de7  movzx   eax, word ptr [rbp+arg_18]
0x140020deb  lea     r8, [rbp+BufferLength]; BufferLength
0x140020def  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140020df3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140020df7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140020df9  mov     [rbp+BufferLength], edi
0x140020dfc  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140020e03  nop     dword ptr [rax+rax+00h]
0x140020e08  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140020e0b  lea     ecx, [rdi+1]; PoolType
0x140020e0e  mov     r8d, 64536553h; Tag
0x140020e14  call    cs:__imp_ExAllocatePoolWithTag
0x140020e1b  nop     dword ptr [rax+rax+00h]
0x140020e20  mov     rdi, rax
0x140020e23  test    rax, rax
0x140020e26  jnz     short loc_140020E70
0x140020e28  mov     ebx, 0C000009Ah
0x140020e2d  cmp     [rbp+Dacl], 0
0x140020e32  jz      short loc_140020E46
0x140020e34  mov     rcx, [rbp+Dacl]; P
0x140020e38  xor     edx, edx; Tag
0x140020e3a  call    cs:__imp_ExFreePoolWithTag
0x140020e41  nop     dword ptr [rax+rax+00h]
0x140020e46  test    rdi, rdi
0x140020e49  jz      short loc_140020E5C
0x140020e4b  xor     edx, edx; Tag
0x140020e4d  mov     rcx, rdi; P
0x140020e50  call    cs:__imp_ExFreePoolWithTag
0x140020e57  nop     dword ptr [rax+rax+00h]
0x140020e5c  mov     eax, ebx
0x140020e5e  mov     rbx, [rsp+70h+arg_0]
0x140020e66  add     rsp, 70h
0x140020e6a  pop     r14
0x140020e6c  pop     rdi
0x140020e6d  pop     rbp
0x140020e6e  retn
0x140020e70  mov     r8d, [rbp+BufferLength]; Size
0x140020e74  xor     edx, edx; Val
0x140020e76  mov     rcx, rdi; void *
0x140020e79  call    memset
0x140020e7e  lea     r8, [rbp+BufferLength]; BufferLength
0x140020e82  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140020e85  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140020e89  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140020e90  nop     dword ptr [rax+rax+00h]
0x140020e95  mov     ebx, eax
0x140020e97  test    eax, eax
0x140020e99  js      short loc_140020E2D
0x140020e9b  mov     rcx, [rbp+Dacl]; P
0x140020e9f  xor     edx, edx; Tag
0x140020ea1  call    cs:__imp_ExFreePoolWithTag
0x140020ea8  nop     dword ptr [rax+rax+00h]
0x140020ead  mov     [r14], rdi
0x140020eb0  jmp     short loc_140020E5C
```
