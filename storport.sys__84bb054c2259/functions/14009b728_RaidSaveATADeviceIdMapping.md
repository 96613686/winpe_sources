# RaidSaveATADeviceIdMapping

- ea: `0x14009b728`
- end: `0x14009b863`
- name: `RaidSaveATADeviceIdMapping`
- size: `315`
- prototype: `__int64 __fastcall(PVOID ValueData, ULONG ValueLength, const GUID *Guid)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400e6e9c`

## callees

- `0x14009b728`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14009b827`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14009b827`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b772`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b772`
- `ntoskrnl!ZwClose` at `0x14009b83c`
- `ntoskrnl!ZwClose` at `0x14009b83c`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b815`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b815`
- `ntoskrnl!ZwCreateKey` at `0x14009b7ce`
- `ntoskrnl!ZwCreateKey` at `0x14009b7ce`
- `ntoskrnl!RtlStringFromGUID` at `0x14009b7e7`
- `ntoskrnl!RtlStringFromGUID` at `0x14009b7e7`

## string_xrefs

- `0x14009b74a`: `\Registry\Machine\System\CurrentControlSet\Control\StorPort\ATADeviceIdMappings`

## pseudocode

```c
__int64 __fastcall RaidSaveATADeviceIdMapping(PVOID ValueData, ULONG ValueLength, const GUID *Guid)
{
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+7Fh] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorPort\\ATADeviceIdMappings");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = RtlStringFromGUID(Guid, &GuidString);
    if ( v6 >= 0 )
      v6 = RtlWriteRegistryValue(0x40000000u, (PCWSTR)KeyHandle, GuidString.Buffer, 3u, ValueData, ValueLength);
  }
  RtlFreeUnicodeString(&GuidString);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14009b728  mov     [rsp-8+arg_0], rbx
0x14009b72d  mov     [rsp-8+arg_8], rsi
0x14009b732  push    rbp
0x14009b733  push    rdi
0x14009b734  push    r14
0x14009b736  lea     rbp, [rsp-47h]
0x14009b73b  sub     rsp, 90h
0x14009b742  xorps   xmm0, xmm0
0x14009b745  mov     esi, edx
0x14009b747  mov     r14, rcx
0x14009b74a  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x14009b751  xor     eax, eax
0x14009b753  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14009b757  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14009b75b  mov     rdi, r8
0x14009b75e  mov     [rbp+57h+KeyHandle], rax
0x14009b762  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14009b766  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14009b76a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009b76e  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x14009b772  call    cs:__imp_RtlInitUnicodeString
0x14009b779  nop     dword ptr [rax+rax+00h]
0x14009b77e  lea     rax, [rbp+57h+DestinationString]
0x14009b782  mov     [rsp+0A0h+Disposition], 0; Disposition
0x14009b78b  xorps   xmm0, xmm0
0x14009b78e  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14009b796  xor     r9d, r9d; TitleIndex
0x14009b799  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009b79d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009b7a1  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14009b7a8  mov     edx, 20006h; DesiredAccess
0x14009b7ad  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14009b7b5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009b7b9  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14009b7c0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009b7c5  mov     [rsp+0A0h+Class], 0; Class
0x14009b7ce  call    cs:__imp_ZwCreateKey
0x14009b7d5  nop     dword ptr [rax+rax+00h]
0x14009b7da  mov     ebx, eax
0x14009b7dc  test    eax, eax
0x14009b7de  js      short loc_14009B823
0x14009b7e0  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14009b7e4  mov     rcx, rdi; Guid
0x14009b7e7  call    cs:__imp_RtlStringFromGUID
0x14009b7ee  nop     dword ptr [rax+rax+00h]
0x14009b7f3  mov     ebx, eax
0x14009b7f5  test    eax, eax
0x14009b7f7  js      short loc_14009B823
0x14009b7f9  mov     r8, [rbp+57h+GuidString.Buffer]; ValueName
0x14009b7fd  mov     r9d, 3; ValueType
0x14009b803  mov     rdx, [rbp+57h+KeyHandle]; Path
0x14009b807  mov     ecx, 40000000h; RelativeTo
0x14009b80c  mov     [rsp+0A0h+CreateOptions], esi; ValueLength
0x14009b810  mov     [rsp+0A0h+Class], r14; ValueData
0x14009b815  call    cs:__imp_RtlWriteRegistryValue
0x14009b81c  nop     dword ptr [rax+rax+00h]
0x14009b821  mov     ebx, eax
0x14009b823  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14009b827  call    cs:__imp_RtlFreeUnicodeString
0x14009b82e  nop     dword ptr [rax+rax+00h]
0x14009b833  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14009b837  test    rcx, rcx
0x14009b83a  jz      short loc_14009B848
0x14009b83c  call    cs:__imp_ZwClose
0x14009b843  nop     dword ptr [rax+rax+00h]
0x14009b848  lea     r11, [rsp+0A0h+var_10]
0x14009b850  mov     eax, ebx
0x14009b852  mov     rbx, [r11+20h]
0x14009b856  mov     rsi, [r11+28h]
0x14009b85a  mov     rsp, r11
0x14009b85d  pop     r14
0x14009b85f  pop     rdi
0x14009b860  pop     rbp
0x14009b861  retn
```
