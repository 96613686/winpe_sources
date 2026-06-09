# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1402389f8`
- end: `0x140238b96`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140237be4`

## callees

- `0x1401bbe10`
- `0x1401bc2c0`
- `0x140237d9c`
- `0x1402389f8`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140238aa6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140238aa6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140238abf`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140238abf`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238ae0`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238b6d`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238ae0`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140238b6d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238af8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238af8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140238a34`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140238a34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140238b85`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238a24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140238a24`

## string_xrefs

- `0x140238a0f`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1402389f8  mov     [rsp-18h+arg_0], rbx
0x1402389fd  mov     [rsp-18h+BufferLength], edx
0x140238a01  push    rbp
0x140238a02  push    rdi
0x140238a03  push    r14
0x140238a05  mov     rbp, rsp
0x140238a08  sub     rsp, 70h
0x140238a0c  mov     rbx, rcx
0x140238a0f  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140238a16  xorps   xmm0, xmm0
0x140238a19  lea     rcx, [rbp+DestinationString]; DestinationString
0x140238a1d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140238a21  mov     r14, r8
0x140238a24  call    cs:__imp_RtlInitUnicodeString
0x140238a2b  nop     dword ptr [rax+rax+00h]
0x140238a30  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140238a34  call    cs:__imp_MmGetSystemRoutineAddress
0x140238a3b  nop     dword ptr [rax+rax+00h]
0x140238a40  mov     rcx, rbx
0x140238a43  test    rax, rax
0x140238a46  jz      short loc_140238A6C
0x140238a48  xor     r9d, r9d
0x140238a4b  mov     r8, r14
0x140238a4e  lea     edx, [r9+1]
0x140238a52  call    _guard_dispatch_icall
0x140238a57  test    eax, eax
0x140238a59  js      loc_140238B42
0x140238a5f  mov     rcx, [r14]
0x140238a62  or      word ptr [rcx+2], 8
0x140238a67  jmp     loc_140238B42
0x140238a6c  xor     eax, eax
0x140238a6e  lea     r9, [rbp+Dacl]
0x140238a72  xorps   xmm0, xmm0
0x140238a75  mov     [rbp+var_8], rax
0x140238a79  lea     r8, [rbp+arg_18]
0x140238a7d  mov     [rbp+arg_18], eax
0x140238a80  movups  [rbp+SecurityDescriptor], xmm0
0x140238a84  mov     [rbp+BufferLength], eax
0x140238a87  xor     edi, edi
0x140238a89  movups  [rbp+var_18], xmm0
0x140238a8d  mov     [rbp+Dacl], rax
0x140238a91  mov     [r14], rax
0x140238a94  call    SepSddlDaclFromSDDLString
0x140238a99  mov     ebx, eax
0x140238a9b  test    eax, eax
0x140238a9d  js      short loc_140238B11
0x140238a9f  lea     edx, [rdi+1]; Revision
0x140238aa2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140238aa6  call    cs:__imp_RtlCreateSecurityDescriptor
0x140238aad  nop     dword ptr [rax+rax+00h]
0x140238ab2  mov     r8, [rbp+Dacl]; Dacl
0x140238ab6  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140238aba  xor     r9d, r9d; DaclDefaulted
0x140238abd  mov     dl, 1; DaclPresent
0x140238abf  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140238ac6  nop     dword ptr [rax+rax+00h]
0x140238acb  movzx   eax, word ptr [rbp+arg_18]
0x140238acf  lea     r8, [rbp+BufferLength]; BufferLength
0x140238ad3  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140238ad7  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140238adb  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140238add  mov     [rbp+BufferLength], edi
0x140238ae0  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140238ae7  nop     dword ptr [rax+rax+00h]
0x140238aec  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140238aef  lea     ecx, [rdi+1]; PoolType
0x140238af2  mov     r8d, 64536553h; Tag
0x140238af8  call    cs:__imp_ExAllocatePoolWithTag
0x140238aff  nop     dword ptr [rax+rax+00h]
0x140238b04  mov     rdi, rax
0x140238b07  test    rax, rax
0x140238b0a  jnz     short loc_140238B54
0x140238b0c  mov     ebx, 0C000009Ah
0x140238b11  cmp     [rbp+Dacl], 0
0x140238b16  jz      short loc_140238B2A
0x140238b18  mov     rcx, [rbp+Dacl]; P
0x140238b1c  xor     edx, edx; Tag
0x140238b1e  call    cs:__imp_ExFreePoolWithTag
0x140238b25  nop     dword ptr [rax+rax+00h]
0x140238b2a  test    rdi, rdi
0x140238b2d  jz      short loc_140238B40
0x140238b2f  xor     edx, edx; Tag
0x140238b31  mov     rcx, rdi; P
0x140238b34  call    cs:__imp_ExFreePoolWithTag
0x140238b3b  nop     dword ptr [rax+rax+00h]
0x140238b40  mov     eax, ebx
0x140238b42  mov     rbx, [rsp+70h+arg_0]
0x140238b4a  add     rsp, 70h
0x140238b4e  pop     r14
0x140238b50  pop     rdi
0x140238b51  pop     rbp
0x140238b52  retn
0x140238b54  mov     r8d, [rbp+BufferLength]; Size
0x140238b58  xor     edx, edx; Val
0x140238b5a  mov     rcx, rdi; void *
0x140238b5d  call    memset
0x140238b62  lea     r8, [rbp+BufferLength]; BufferLength
0x140238b66  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140238b69  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140238b6d  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140238b74  nop     dword ptr [rax+rax+00h]
0x140238b79  mov     ebx, eax
0x140238b7b  test    eax, eax
0x140238b7d  js      short loc_140238B11
0x140238b7f  mov     rcx, [rbp+Dacl]; P
0x140238b83  xor     edx, edx; Tag
0x140238b85  call    cs:__imp_ExFreePoolWithTag
0x140238b8c  nop     dword ptr [rax+rax+00h]
0x140238b91  mov     [r14], rdi
0x140238b94  jmp     short loc_140238B40
```
