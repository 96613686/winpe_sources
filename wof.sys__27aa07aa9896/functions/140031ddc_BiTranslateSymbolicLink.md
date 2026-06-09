# BiTranslateSymbolicLink

- ea: `0x140031ddc`
- end: `0x140031f8b`
- name: `BiTranslateSymbolicLink`
- size: `431`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140030f38`
- `0x140031f94`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x140031ddc`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140031e81`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140031e81`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031e51`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031f33`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031e51`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031f33`
- `ntoskrnl!ExAllocatePool2` at `0x140031ec0`
- `ntoskrnl!ExAllocatePool2` at `0x140031ec0`

## pseudocode

```c
NTSTATUS __fastcall BiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  WCHAR *Pool2; // rax
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnedLength; // [rsp+A0h] [rbp+30h] BYREF
  void *LinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  ReturnedLength = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
  LinkHandle = 0;
  LinkTarget.Buffer = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString_0(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString_0(&LinkTarget, 0);
    v4 = 0;
    ReturnedLength = 0;
    do
    {
      while ( 1 )
      {
        v5 = ZwQuerySymbolicLinkObject(LinkHandle, &LinkTarget, &ReturnedLength);
        if ( v5 != -1073741789 )
          break;
        if ( LinkTarget.Buffer )
          ExFreePoolWithTag_0(LinkTarget.Buffer, 0x4B444342u);
        LinkTarget.MaximumLength = ReturnedLength;
        v4 = ReturnedLength + 2;
        Pool2 = (WCHAR *)ExAllocatePool2(258, ReturnedLength + 2, 1262764866);
        LinkTarget.Buffer = Pool2;
        if ( !Pool2 )
        {
          v5 = -1073741670;
          goto LABEL_11;
        }
      }
      ZwClose_0(LinkHandle);
      Pool2 = LinkTarget.Buffer;
      LinkHandle = 0;
      if ( v5 < 0 )
        goto LABEL_14;
      LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &LinkTarget;
      LinkTarget.MaximumLength = v4;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
    while ( ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes) >= 0 );
    Pool2 = LinkTarget.Buffer;
    v5 = 0;
    *a2 = LinkTarget.Buffer;
LABEL_11:
    if ( LinkHandle )
    {
      ZwClose_0(LinkHandle);
      Pool2 = LinkTarget.Buffer;
    }
    if ( v5 < 0 )
    {
LABEL_14:
      if ( Pool2 )
        ExFreePoolWithTag_0(Pool2, 0x4B444342u);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x140031ddc  mov     [rsp-18h+arg_0], rbx
0x140031de1  push    rbp
0x140031de2  push    rsi
0x140031de3  push    rdi
0x140031de4  mov     rbp, rsp
0x140031de7  sub     rsp, 70h
0x140031deb  xorps   xmm0, xmm0
0x140031dee  xor     eax, eax
0x140031df0  mov     rsi, rdx
0x140031df3  mov     [rbp+ReturnedLength], eax
0x140031df6  mov     rdx, rcx; SourceString
0x140031df9  mov     qword ptr [rbp+LinkTarget.Length], rax
0x140031dfd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140031e01  lea     rcx, [rbp+DestinationString]; DestinationString
0x140031e05  mov     [rbp+LinkHandle], rax
0x140031e09  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140031e0d  mov     [rbp+LinkTarget.Buffer], rax
0x140031e11  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140031e15  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140031e19  call    RtlInitUnicodeString_0
0x140031e1e  lea     rax, [rbp+DestinationString]
0x140031e22  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031e29  xorps   xmm0, xmm0
0x140031e2c  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140031e30  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140031e34  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140031e3c  mov     edx, 1; DesiredAccess
0x140031e41  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140031e48  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x140031e4c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140031e51  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140031e58  nop     dword ptr [rax+rax+00h]
0x140031e5d  test    eax, eax
0x140031e5f  js      loc_140031F7A
0x140031e65  xor     edx, edx; SourceString
0x140031e67  lea     rcx, [rbp+LinkTarget]; DestinationString
0x140031e6b  call    RtlInitUnicodeString_0
0x140031e70  xor     edi, edi
0x140031e72  mov     [rbp+ReturnedLength], edi
0x140031e75  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x140031e79  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x140031e7d  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x140031e81  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140031e88  nop     dword ptr [rax+rax+00h]
0x140031e8d  mov     ebx, eax
0x140031e8f  cmp     eax, 0C0000023h
0x140031e94  jnz     short loc_140031EDC
0x140031e96  mov     rcx, [rbp+LinkTarget.Buffer]; P
0x140031e9a  test    rcx, rcx
0x140031e9d  jz      short loc_140031EA9
0x140031e9f  mov     edx, 4B444342h; Tag
0x140031ea4  call    ExFreePoolWithTag_0
0x140031ea9  mov     eax, [rbp+ReturnedLength]
0x140031eac  mov     ecx, 102h
0x140031eb1  mov     r8d, 4B444342h
0x140031eb7  mov     [rbp+LinkTarget.MaximumLength], ax
0x140031ebb  lea     edi, [rax+2]
0x140031ebe  mov     edx, edi
0x140031ec0  call    cs:__imp_ExAllocatePool2
0x140031ec7  nop     dword ptr [rax+rax+00h]
0x140031ecc  mov     [rbp+LinkTarget.Buffer], rax
0x140031ed0  test    rax, rax
0x140031ed3  jnz     short loc_140031E75
0x140031ed5  mov     ebx, 0C000009Ah
0x140031eda  jmp     short loc_140031F50
0x140031edc  mov     rcx, [rbp+LinkHandle]; Handle
0x140031ee0  call    ZwClose_0
0x140031ee5  mov     rax, [rbp+LinkTarget.Buffer]
0x140031ee9  mov     [rbp+LinkHandle], 0
0x140031ef1  test    ebx, ebx
0x140031ef3  js      short loc_140031F66
0x140031ef5  movzx   edx, [rbp+LinkTarget.Length]
0x140031ef9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140031efd  xor     ecx, ecx
0x140031eff  shr     rdx, 1
0x140031f02  xorps   xmm0, xmm0
0x140031f05  mov     [rax+rdx*2], cx
0x140031f09  lea     rax, [rbp+LinkTarget]
0x140031f0d  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140031f11  lea     edx, [rcx+1]; DesiredAccess
0x140031f14  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x140031f18  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140031f1c  mov     [rbp+LinkTarget.MaximumLength], di
0x140031f20  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031f27  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140031f2e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140031f33  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140031f3a  nop     dword ptr [rax+rax+00h]
0x140031f3f  test    eax, eax
0x140031f41  jns     loc_140031E75
0x140031f47  mov     rax, [rbp+LinkTarget.Buffer]
0x140031f4b  xor     ebx, ebx
0x140031f4d  mov     [rsi], rax
0x140031f50  mov     rcx, [rbp+LinkHandle]; Handle
0x140031f54  test    rcx, rcx
0x140031f57  jz      short loc_140031F62
0x140031f59  call    ZwClose_0
0x140031f5e  mov     rax, [rbp+LinkTarget.Buffer]
0x140031f62  test    ebx, ebx
0x140031f64  jns     short loc_140031F78
0x140031f66  test    rax, rax
0x140031f69  jz      short loc_140031F78
0x140031f6b  mov     edx, 4B444342h; Tag
0x140031f70  mov     rcx, rax; P
0x140031f73  call    ExFreePoolWithTag_0
0x140031f78  mov     eax, ebx
0x140031f7a  mov     rbx, [rsp+70h+arg_0]
0x140031f82  add     rsp, 70h
0x140031f86  pop     rdi
0x140031f87  pop     rsi
0x140031f88  pop     rbp
0x140031f89  retn
```
