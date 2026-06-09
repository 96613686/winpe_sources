# GetHardErrorMode

- ea: `0x18000bf38`
- end: `0x18000c04a`
- name: `GetHardErrorMode`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dda0`

## callees

- `0x18000bf38`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18000c008`
- `ntdll!NtQueryValueKey` at `0x18000c008`
- `ntdll!NtOpenKey` at `0x18000bfc0`
- `ntdll!NtOpenKey` at `0x18000bfc0`
- `ntdll!RtlInitUnicodeString` at `0x18000bf85`
- `ntdll!RtlInitUnicodeString` at `0x18000bfdb`
- `ntdll!RtlInitUnicodeString` at `0x18000bf85`
- `ntdll!RtlInitUnicodeString` at `0x18000bfdb`
- `ntdll!NtClose` at `0x18000c01e`
- `ntdll!NtClose` at `0x18000c01e`

## string_xrefs

- `0x18000bf65`: `\Registry\Machine\System\CurrentControlSet\Control\Windows`

## pseudocode

```c
__int64 GetHardErrorMode()
{
  unsigned int v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+80h] [rbp+37h] BYREF
  unsigned int v7; // [rsp+8Ch] [rbp+43h]

  KeyHandle = 0;
  ResultLength = 0;
  v0 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Windows");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ErrorMode");
    if ( NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
      v0 = v7;
    NtClose(KeyHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x18000bf38  mov     [rsp-8+arg_0], rbx
0x18000bf3d  push    rbp
0x18000bf3e  lea     rbp, [rsp-57h]
0x18000bf43  sub     rsp, 0A0h
0x18000bf4a  mov     rax, cs:__security_cookie
0x18000bf51  xor     rax, rsp
0x18000bf54  mov     [rbp+57h+var_8], rax
0x18000bf58  xorps   xmm0, xmm0
0x18000bf5b  mov     [rbp+57h+KeyHandle], 0
0x18000bf63  xor     eax, eax
0x18000bf65  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000bf6c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000bf70  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000bf74  mov     [rbp+57h+var_70], eax
0x18000bf77  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000bf7b  xor     ebx, ebx
0x18000bf7d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000bf81  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000bf85  call    cs:__imp_RtlInitUnicodeString
0x18000bf8c  nop     dword ptr [rax+rax+00h]
0x18000bf91  lea     rax, [rbp+57h+DestinationString]
0x18000bf95  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000bf9c  xorps   xmm0, xmm0
0x18000bf9f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000bfa3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000bfa7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x18000bfab  mov     edx, 20019h; DesiredAccess
0x18000bfb0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000bfb7  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000bfbb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000bfc0  call    cs:__imp_NtOpenKey
0x18000bfc7  nop     dword ptr [rax+rax+00h]
0x18000bfcc  test    eax, eax
0x18000bfce  js      short loc_18000C02A
0x18000bfd0  lea     rdx, aErrormode; "ErrorMode"
0x18000bfd7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000bfdb  call    cs:__imp_RtlInitUnicodeString
0x18000bfe2  nop     dword ptr [rax+rax+00h]
0x18000bfe7  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000bfeb  lea     rax, [rbp+57h+var_70]
0x18000bfef  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18000bff4  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000bff8  lea     r8d, [rbx+2]; KeyValueInformationClass
0x18000bffc  mov     [rsp+0A0h+Length], 14h; Length
0x18000c004  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000c008  call    cs:__imp_NtQueryValueKey
0x18000c00f  nop     dword ptr [rax+rax+00h]
0x18000c014  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000c018  test    eax, eax
0x18000c01a  cmovns  ebx, [rbp+57h+var_14]
0x18000c01e  call    cs:__imp_NtClose
0x18000c025  nop     dword ptr [rax+rax+00h]
0x18000c02a  mov     eax, ebx
0x18000c02c  mov     rcx, [rbp+57h+var_8]
0x18000c030  xor     rcx, rsp; StackCookie
0x18000c033  call    __security_check_cookie
0x18000c038  mov     rbx, [rsp+0A0h+arg_0]
0x18000c040  add     rsp, 0A0h
0x18000c047  pop     rbp
0x18000c048  retn
```
