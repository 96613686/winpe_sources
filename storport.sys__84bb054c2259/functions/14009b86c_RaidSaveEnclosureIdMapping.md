# RaidSaveEnclosureIdMapping

- ea: `0x14009b86c`
- end: `0x14009b9a7`
- name: `RaidSaveEnclosureIdMapping`
- size: `315`
- prototype: `__int64 __fastcall(PVOID ValueData, ULONG ValueLength, const GUID *Guid)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400e7314`

## callees

- `0x14009b86c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14009b96b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14009b96b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b8b6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b8b6`
- `ntoskrnl!ZwClose` at `0x14009b980`
- `ntoskrnl!ZwClose` at `0x14009b980`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b959`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b959`
- `ntoskrnl!ZwCreateKey` at `0x14009b912`
- `ntoskrnl!ZwCreateKey` at `0x14009b912`
- `ntoskrnl!RtlStringFromGUID` at `0x14009b92b`
- `ntoskrnl!RtlStringFromGUID` at `0x14009b92b`

## string_xrefs

- `0x14009b88e`: `\Registry\Machine\System\CurrentControlSet\Control\StorPort\EnclosureIdMappings`

## pseudocode

```c
__int64 __fastcall RaidSaveEnclosureIdMapping(PVOID ValueData, ULONG ValueLength, const GUID *Guid)
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
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\StorPort\\EnclosureIdMappings");
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
0x14009b86c  mov     [rsp-8+arg_0], rbx
0x14009b871  mov     [rsp-8+arg_8], rsi
0x14009b876  push    rbp
0x14009b877  push    rdi
0x14009b878  push    r14
0x14009b87a  lea     rbp, [rsp-47h]
0x14009b87f  sub     rsp, 90h
0x14009b886  xorps   xmm0, xmm0
0x14009b889  mov     esi, edx
0x14009b88b  mov     r14, rcx
0x14009b88e  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14009b895  xor     eax, eax
0x14009b897  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14009b89b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14009b89f  mov     rdi, r8
0x14009b8a2  mov     [rbp+57h+KeyHandle], rax
0x14009b8a6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14009b8aa  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14009b8ae  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009b8b2  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x14009b8b6  call    cs:__imp_RtlInitUnicodeString
0x14009b8bd  nop     dword ptr [rax+rax+00h]
0x14009b8c2  lea     rax, [rbp+57h+DestinationString]
0x14009b8c6  mov     [rsp+0A0h+Disposition], 0; Disposition
0x14009b8cf  xorps   xmm0, xmm0
0x14009b8d2  mov     [rsp+0A0h+CreateOptions], 0; CreateOptions
0x14009b8da  xor     r9d, r9d; TitleIndex
0x14009b8dd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009b8e1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009b8e5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14009b8ec  mov     edx, 20006h; DesiredAccess
0x14009b8f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14009b8f9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009b8fd  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14009b904  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009b909  mov     [rsp+0A0h+Class], 0; Class
0x14009b912  call    cs:__imp_ZwCreateKey
0x14009b919  nop     dword ptr [rax+rax+00h]
0x14009b91e  mov     ebx, eax
0x14009b920  test    eax, eax
0x14009b922  js      short loc_14009B967
0x14009b924  lea     rdx, [rbp+57h+GuidString]; GuidString
0x14009b928  mov     rcx, rdi; Guid
0x14009b92b  call    cs:__imp_RtlStringFromGUID
0x14009b932  nop     dword ptr [rax+rax+00h]
0x14009b937  mov     ebx, eax
0x14009b939  test    eax, eax
0x14009b93b  js      short loc_14009B967
0x14009b93d  mov     r8, [rbp+57h+GuidString.Buffer]; ValueName
0x14009b941  mov     r9d, 3; ValueType
0x14009b947  mov     rdx, [rbp+57h+KeyHandle]; Path
0x14009b94b  mov     ecx, 40000000h; RelativeTo
0x14009b950  mov     [rsp+0A0h+CreateOptions], esi; ValueLength
0x14009b954  mov     [rsp+0A0h+Class], r14; ValueData
0x14009b959  call    cs:__imp_RtlWriteRegistryValue
0x14009b960  nop     dword ptr [rax+rax+00h]
0x14009b965  mov     ebx, eax
0x14009b967  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x14009b96b  call    cs:__imp_RtlFreeUnicodeString
0x14009b972  nop     dword ptr [rax+rax+00h]
0x14009b977  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14009b97b  test    rcx, rcx
0x14009b97e  jz      short loc_14009B98C
0x14009b980  call    cs:__imp_ZwClose
0x14009b987  nop     dword ptr [rax+rax+00h]
0x14009b98c  lea     r11, [rsp+0A0h+var_10]
0x14009b994  mov     eax, ebx
0x14009b996  mov     rbx, [r11+20h]
0x14009b99a  mov     rsi, [r11+28h]
0x14009b99e  mov     rsp, r11
0x14009b9a1  pop     r14
0x14009b9a3  pop     rdi
0x14009b9a4  pop     rbp
0x14009b9a5  retn
```
