# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140238a58`
- end: `0x140238bf6`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140237c44`

## callees

- `0x1401bbe80`
- `0x1401bc340`
- `0x140237dfc`
- `0x140238a58`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140238b06`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140238b06`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140238b1f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140238b1f`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238b40`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238bcd`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238b40`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238bcd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238b58`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238b58`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140238a94`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140238a94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238be5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238a84`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238a84`

## string_xrefs

- `0x140238a6f`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140238a58  mov     [rsp-18h+arg_0], rbx
0x140238a5d  mov     [rsp-18h+BufferLength], edx
0x140238a61  push    rbp
0x140238a62  push    rdi
0x140238a63  push    r14
0x140238a65  mov     rbp, rsp
0x140238a68  sub     rsp, 70h
0x140238a6c  mov     rbx, rcx
0x140238a6f  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140238a76  xorps   xmm0, xmm0
0x140238a79  lea     rcx, [rbp+DestinationString]; DestinationString
0x140238a7d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140238a81  mov     r14, r8
0x140238a84  call    cs:__imp_RtlInitUnicodeString
0x140238a8b  nop     dword ptr [rax+rax+00h]
0x140238a90  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140238a94  call    cs:__imp_MmGetSystemRoutineAddress
0x140238a9b  nop     dword ptr [rax+rax+00h]
0x140238aa0  mov     rcx, rbx
0x140238aa3  test    rax, rax
0x140238aa6  jz      short loc_140238ACC
0x140238aa8  xor     r9d, r9d
0x140238aab  mov     r8, r14
0x140238aae  lea     edx, [r9+1]
0x140238ab2  call    _guard_dispatch_icall
0x140238ab7  test    eax, eax
0x140238ab9  js      loc_140238BA2
0x140238abf  mov     rcx, [r14]
0x140238ac2  or      word ptr [rcx+2], 8
0x140238ac7  jmp     loc_140238BA2
0x140238acc  xor     eax, eax
0x140238ace  lea     r9, [rbp+Dacl]
0x140238ad2  xorps   xmm0, xmm0
0x140238ad5  mov     [rbp+var_8], rax
0x140238ad9  lea     r8, [rbp+arg_18]
0x140238add  mov     [rbp+arg_18], eax
0x140238ae0  movups  [rbp+SecurityDescriptor], xmm0
0x140238ae4  mov     [rbp+BufferLength], eax
0x140238ae7  xor     edi, edi
0x140238ae9  movups  [rbp+var_18], xmm0
0x140238aed  mov     [rbp+Dacl], rax
0x140238af1  mov     [r14], rax
0x140238af4  call    SepSddlDaclFromSDDLString
0x140238af9  mov     ebx, eax
0x140238afb  test    eax, eax
0x140238afd  js      short loc_140238B71
0x140238aff  lea     edx, [rdi+1]; Revision
0x140238b02  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140238b06  call    cs:__imp_RtlCreateSecurityDescriptor
0x140238b0d  nop     dword ptr [rax+rax+00h]
0x140238b12  mov     r8, [rbp+Dacl]; Dacl
0x140238b16  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140238b1a  xor     r9d, r9d; DaclDefaulted
0x140238b1d  mov     dl, 1; DaclPresent
0x140238b1f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140238b26  nop     dword ptr [rax+rax+00h]
0x140238b2b  movzx   eax, word ptr [rbp+arg_18]
0x140238b2f  lea     r8, [rbp+BufferLength]; BufferLength
0x140238b33  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140238b37  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140238b3b  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140238b3d  mov     [rbp+BufferLength], edi
0x140238b40  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140238b47  nop     dword ptr [rax+rax+00h]
0x140238b4c  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140238b4f  lea     ecx, [rdi+1]; PoolType
0x140238b52  mov     r8d, 64536553h; Tag
0x140238b58  call    cs:__imp_ExAllocatePoolWithTag
0x140238b5f  nop     dword ptr [rax+rax+00h]
0x140238b64  mov     rdi, rax
0x140238b67  test    rax, rax
0x140238b6a  jnz     short loc_140238BB4
0x140238b6c  mov     ebx, 0C000009Ah
0x140238b71  cmp     [rbp+Dacl], 0
0x140238b76  jz      short loc_140238B8A
0x140238b78  mov     rcx, [rbp+Dacl]; P
0x140238b7c  xor     edx, edx; Tag
0x140238b7e  call    cs:__imp_ExFreePoolWithTag
0x140238b85  nop     dword ptr [rax+rax+00h]
0x140238b8a  test    rdi, rdi
0x140238b8d  jz      short loc_140238BA0
0x140238b8f  xor     edx, edx; Tag
0x140238b91  mov     rcx, rdi; P
0x140238b94  call    cs:__imp_ExFreePoolWithTag
0x140238b9b  nop     dword ptr [rax+rax+00h]
0x140238ba0  mov     eax, ebx
0x140238ba2  mov     rbx, [rsp+70h+arg_0]
0x140238baa  add     rsp, 70h
0x140238bae  pop     r14
0x140238bb0  pop     rdi
0x140238bb1  pop     rbp
0x140238bb2  retn
0x140238bb4  mov     r8d, [rbp+BufferLength]; Size
0x140238bb8  xor     edx, edx; Val
0x140238bba  mov     rcx, rdi; void *
0x140238bbd  call    memset
0x140238bc2  lea     r8, [rbp+BufferLength]; BufferLength
0x140238bc6  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140238bc9  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140238bcd  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140238bd4  nop     dword ptr [rax+rax+00h]
0x140238bd9  mov     ebx, eax
0x140238bdb  test    eax, eax
0x140238bdd  js      short loc_140238B71
0x140238bdf  mov     rcx, [rbp+Dacl]; P
0x140238be3  xor     edx, edx; Tag
0x140238be5  call    cs:__imp_ExFreePoolWithTag
0x140238bec  nop     dword ptr [rax+rax+00h]
0x140238bf1  mov     [r14], rdi
0x140238bf4  jmp     short loc_140238BA0
```
