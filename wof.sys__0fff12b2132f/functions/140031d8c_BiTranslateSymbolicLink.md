# BiTranslateSymbolicLink

- ea: `0x140031d8c`
- end: `0x140031f3b`
- name: `BiTranslateSymbolicLink`
- size: `431`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140030ee8`
- `0x140031f44`

## callees

- `0x14000da0d`
- `0x14000da31`
- `0x14000da55`
- `0x140031d8c`

## import_xrefs

- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140031e31`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140031e31`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031e01`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031ee3`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031e01`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140031ee3`
- `ntoskrnl!ExAllocatePool2` at `0x140031e70`
- `ntoskrnl!ExAllocatePool2` at `0x140031e70`

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
0x140031d8c  mov     [rsp-18h+arg_0], rbx
0x140031d91  push    rbp
0x140031d92  push    rsi
0x140031d93  push    rdi
0x140031d94  mov     rbp, rsp
0x140031d97  sub     rsp, 70h
0x140031d9b  xorps   xmm0, xmm0
0x140031d9e  xor     eax, eax
0x140031da0  mov     rsi, rdx
0x140031da3  mov     [rbp+ReturnedLength], eax
0x140031da6  mov     rdx, rcx; SourceString
0x140031da9  mov     qword ptr [rbp+LinkTarget.Length], rax
0x140031dad  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140031db1  lea     rcx, [rbp+DestinationString]; DestinationString
0x140031db5  mov     [rbp+LinkHandle], rax
0x140031db9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140031dbd  mov     [rbp+LinkTarget.Buffer], rax
0x140031dc1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140031dc5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140031dc9  call    RtlInitUnicodeString_0
0x140031dce  lea     rax, [rbp+DestinationString]
0x140031dd2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031dd9  xorps   xmm0, xmm0
0x140031ddc  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140031de0  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140031de4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140031dec  mov     edx, 1; DesiredAccess
0x140031df1  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140031df8  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x140031dfc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140031e01  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140031e08  nop     dword ptr [rax+rax+00h]
0x140031e0d  test    eax, eax
0x140031e0f  js      loc_140031F2A
0x140031e15  xor     edx, edx; SourceString
0x140031e17  lea     rcx, [rbp+LinkTarget]; DestinationString
0x140031e1b  call    RtlInitUnicodeString_0
0x140031e20  xor     edi, edi
0x140031e22  mov     [rbp+ReturnedLength], edi
0x140031e25  mov     rcx, [rbp+LinkHandle]; LinkHandle
0x140031e29  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x140031e2d  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x140031e31  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140031e38  nop     dword ptr [rax+rax+00h]
0x140031e3d  mov     ebx, eax
0x140031e3f  cmp     eax, 0C0000023h
0x140031e44  jnz     short loc_140031E8C
0x140031e46  mov     rcx, [rbp+LinkTarget.Buffer]; P
0x140031e4a  test    rcx, rcx
0x140031e4d  jz      short loc_140031E59
0x140031e4f  mov     edx, 4B444342h; Tag
0x140031e54  call    ExFreePoolWithTag_0
0x140031e59  mov     eax, [rbp+ReturnedLength]
0x140031e5c  mov     ecx, 102h
0x140031e61  mov     r8d, 4B444342h
0x140031e67  mov     [rbp+LinkTarget.MaximumLength], ax
0x140031e6b  lea     edi, [rax+2]
0x140031e6e  mov     edx, edi
0x140031e70  call    cs:__imp_ExAllocatePool2
0x140031e77  nop     dword ptr [rax+rax+00h]
0x140031e7c  mov     [rbp+LinkTarget.Buffer], rax
0x140031e80  test    rax, rax
0x140031e83  jnz     short loc_140031E25
0x140031e85  mov     ebx, 0C000009Ah
0x140031e8a  jmp     short loc_140031F00
0x140031e8c  mov     rcx, [rbp+LinkHandle]; Handle
0x140031e90  call    ZwClose_0
0x140031e95  mov     rax, [rbp+LinkTarget.Buffer]
0x140031e99  mov     [rbp+LinkHandle], 0
0x140031ea1  test    ebx, ebx
0x140031ea3  js      short loc_140031F16
0x140031ea5  movzx   edx, [rbp+LinkTarget.Length]
0x140031ea9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140031ead  xor     ecx, ecx
0x140031eaf  shr     rdx, 1
0x140031eb2  xorps   xmm0, xmm0
0x140031eb5  mov     [rax+rdx*2], cx
0x140031eb9  lea     rax, [rbp+LinkTarget]
0x140031ebd  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140031ec1  lea     edx, [rcx+1]; DesiredAccess
0x140031ec4  lea     rcx, [rbp+LinkHandle]; LinkHandle
0x140031ec8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140031ecc  mov     [rbp+LinkTarget.MaximumLength], di
0x140031ed0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140031ed7  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140031ede  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140031ee3  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140031eea  nop     dword ptr [rax+rax+00h]
0x140031eef  test    eax, eax
0x140031ef1  jns     loc_140031E25
0x140031ef7  mov     rax, [rbp+LinkTarget.Buffer]
0x140031efb  xor     ebx, ebx
0x140031efd  mov     [rsi], rax
0x140031f00  mov     rcx, [rbp+LinkHandle]; Handle
0x140031f04  test    rcx, rcx
0x140031f07  jz      short loc_140031F12
0x140031f09  call    ZwClose_0
0x140031f0e  mov     rax, [rbp+LinkTarget.Buffer]
0x140031f12  test    ebx, ebx
0x140031f14  jns     short loc_140031F28
0x140031f16  test    rax, rax
0x140031f19  jz      short loc_140031F28
0x140031f1b  mov     edx, 4B444342h; Tag
0x140031f20  mov     rcx, rax; P
0x140031f23  call    ExFreePoolWithTag_0
0x140031f28  mov     eax, ebx
0x140031f2a  mov     rbx, [rsp+70h+arg_0]
0x140031f32  add     rsp, 70h
0x140031f36  pop     rdi
0x140031f37  pop     rsi
0x140031f38  pop     rbp
0x140031f39  retn
```
