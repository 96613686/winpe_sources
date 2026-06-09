# GetD3Policy

- ea: `0x14002befc`
- end: `0x14002c085`
- name: `GetD3Policy`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x140014d10`
- `0x14002befc`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14002bfd5`
- `ntoskrnl!ZwCreateKey` at `0x14002bfd5`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002bf5d`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002bf5d`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c055`
- `ntoskrnl!ZwQueryValueKey` at `0x14002c055`
- `ntoskrnl!ZwClose` at `0x14002bfe7`
- `ntoskrnl!ZwClose` at `0x14002c067`
- `ntoskrnl!ZwClose` at `0x14002bfe7`
- `ntoskrnl!ZwClose` at `0x14002c067`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bf7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c026`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002bf7c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002c026`

## pseudocode

```c
NTSTATUS __fastcall GetD3Policy(struct _DEVICE_OBJECT *a1, bool *a2)
{
  NTSTATUS result; // eax
  NTSTATUS v4; // ebx
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  void *DeviceRegKey; // [rsp+48h] [rbp-21h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  __int128 KeyValueInformation; // [rsp+98h] [rbp+2Fh] BYREF
  int v11; // [rsp+A8h] [rbp+3Fh]

  KeyHandle = 0;
  DeviceRegKey = 0;
  ResultLength = 0;
  v11 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  KeyValueInformation = 0;
  result = IoOpenDeviceRegistryKey(a1, 1u, 0xF003Fu, &DeviceRegKey);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"e5b3b5ac-9725-4f78-963f-03dfb1d828c7");
    ObjectAttributes.RootDirectory = DeviceRegKey;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, 0);
    ZwClose(DeviceRegKey);
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"D3ColdSupported");
      v4 = ZwQueryValueKey(
             KeyHandle,
             &DestinationString,
             KeyValuePartialInformation,
             &KeyValueInformation,
             0x14u,
             &ResultLength);
      ZwClose(KeyHandle);
      if ( v4 >= 0 )
        *a2 = HIDWORD(KeyValueInformation) != 0;
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x14002befc  mov     [rsp-8+arg_10], rbx
0x14002bf01  mov     [rsp-8+arg_18], rdi
0x14002bf06  push    rbp
0x14002bf07  lea     rbp, [rsp-57h]
0x14002bf0c  sub     rsp, 0C0h
0x14002bf13  mov     rax, cs:__security_cookie
0x14002bf1a  xor     rax, rsp
0x14002bf1d  mov     [rbp+57h+var_10], rax
0x14002bf21  xor     eax, eax
0x14002bf23  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x14002bf27  xorps   xmm0, xmm0
0x14002bf2a  mov     [rbp+57h+KeyHandle], rax
0x14002bf2e  mov     rdi, rdx
0x14002bf31  mov     [rbp+57h+DeviceRegKey], rax
0x14002bf35  xorps   xmm1, xmm1
0x14002bf38  mov     [rbp+57h+ResultLength], eax
0x14002bf3b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14002bf3f  mov     ebx, 0F003Fh
0x14002bf44  mov     [rbp+57h+var_18], eax
0x14002bf47  lea     edx, [rax+1]; DevInstKeyType
0x14002bf4a  mov     r8d, ebx; DesiredAccess
0x14002bf4d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002bf51  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14002bf55  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002bf59  movups  [rbp+57h+KeyValueInformation], xmm1
0x14002bf5d  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002bf64  nop     dword ptr [rax+rax+00h]
0x14002bf69  test    eax, eax
0x14002bf6b  js      loc_14002BFF9
0x14002bf71  lea     rdx, aE5b3b5ac97254f; "e5b3b5ac-9725-4f78-963f-03dfb1d828c7"
0x14002bf78  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002bf7c  call    cs:__imp_RtlInitUnicodeString
0x14002bf83  nop     dword ptr [rax+rax+00h]
0x14002bf88  mov     rax, [rbp+57h+DeviceRegKey]
0x14002bf8c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002bf90  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14002bf94  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002bf98  lea     rax, [rbp+57h+DestinationString]
0x14002bf9c  mov     [rsp+0C0h+Disposition], 0; Disposition
0x14002bfa5  xorps   xmm0, xmm0
0x14002bfa8  mov     [rsp+0C0h+CreateOptions], 0; CreateOptions
0x14002bfb0  xor     r9d, r9d; TitleIndex
0x14002bfb3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002bfb7  mov     edx, ebx; DesiredAccess
0x14002bfb9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002bfc0  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002bfc7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002bfcc  mov     [rsp+0C0h+Class], 0; Class
0x14002bfd5  call    cs:__imp_ZwCreateKey
0x14002bfdc  nop     dword ptr [rax+rax+00h]
0x14002bfe1  mov     rcx, [rbp+57h+DeviceRegKey]; Handle
0x14002bfe5  mov     ebx, eax
0x14002bfe7  call    cs:__imp_ZwClose
0x14002bfee  nop     dword ptr [rax+rax+00h]
0x14002bff3  test    ebx, ebx
0x14002bff5  jns     short loc_14002C01B
0x14002bff7  mov     eax, ebx
0x14002bff9  mov     rcx, [rbp+57h+var_10]
0x14002bffd  xor     rcx, rsp; StackCookie
0x14002c000  call    __security_check_cookie
0x14002c005  lea     r11, [rsp+0C0h+var_s0]
0x14002c00d  mov     rbx, [r11+20h]
0x14002c011  mov     rdi, [r11+28h]
0x14002c015  mov     rsp, r11
0x14002c018  pop     rbp
0x14002c019  retn
0x14002c01b  lea     rdx, aD3coldsupporte; "D3ColdSupported"
0x14002c022  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002c026  call    cs:__imp_RtlInitUnicodeString
0x14002c02d  nop     dword ptr [rax+rax+00h]
0x14002c032  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002c036  lea     rax, [rbp+57h+ResultLength]
0x14002c03a  mov     qword ptr [rsp+0C0h+CreateOptions], rax; ResultLength
0x14002c03f  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14002c043  mov     r8d, 2; KeyValueInformationClass
0x14002c049  mov     dword ptr [rsp+0C0h+Class], 14h; Length
0x14002c051  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14002c055  call    cs:__imp_ZwQueryValueKey
0x14002c05c  nop     dword ptr [rax+rax+00h]
0x14002c061  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14002c065  mov     ebx, eax
0x14002c067  call    cs:__imp_ZwClose
0x14002c06e  nop     dword ptr [rax+rax+00h]
0x14002c073  test    ebx, ebx
0x14002c075  js      short loc_14002BFF7
0x14002c077  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], 0
0x14002c07b  setnz   cl
0x14002c07e  mov     [rdi], cl
0x14002c080  jmp     loc_14002BFF7
```
