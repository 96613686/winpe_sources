# RfsRegKeyExists

- ea: `0x14004a8dc`
- end: `0x14004a971`
- name: `RfsRegKeyExists`
- size: `149`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004a4d0`

## callees

- `0x14004a8dc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14004a905`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a905`
- `ntoskrnl!ZwOpenKey` at `0x14004a944`
- `ntoskrnl!ZwOpenKey` at `0x14004a944`
- `ntoskrnl!ZwClose` at `0x14004a95c`
- `ntoskrnl!ZwClose` at `0x14004a95c`

## pseudocode

```c
char __fastcall RfsRegKeyExists(PCWSTR SourceString)
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) < 0 )
    return 0;
  ZwClose(KeyHandle);
  return 1;
}

```

## disassembly

```asm
0x14004a8dc  push    rbp
0x14004a8de  mov     rbp, rsp
0x14004a8e1  sub     rsp, 60h
0x14004a8e5  xorps   xmm0, xmm0
0x14004a8e8  xor     eax, eax
0x14004a8ea  mov     rdx, rcx; SourceString
0x14004a8ed  mov     [rbp+KeyHandle], rax
0x14004a8f1  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14004a8f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004a8f9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14004a8fd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004a901  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14004a905  call    cs:__imp_RtlInitUnicodeString
0x14004a90c  nop     dword ptr [rax+rax+00h]
0x14004a911  lea     rax, [rbp+DestinationString]
0x14004a915  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14004a91c  xorps   xmm0, xmm0
0x14004a91f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14004a923  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14004a927  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14004a92f  mov     edx, 1; DesiredAccess
0x14004a934  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14004a93b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14004a93f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004a944  call    cs:__imp_ZwOpenKey
0x14004a94b  nop     dword ptr [rax+rax+00h]
0x14004a950  test    eax, eax
0x14004a952  jns     short loc_14004A958
0x14004a954  xor     al, al
0x14004a956  jmp     short loc_14004A96A
0x14004a958  mov     rcx, [rbp+KeyHandle]; Handle
0x14004a95c  call    cs:__imp_ZwClose
0x14004a963  nop     dword ptr [rax+rax+00h]
0x14004a968  mov     al, 1
0x14004a96a  add     rsp, 60h
0x14004a96e  pop     rbp
0x14004a96f  retn
```
