# InitInstrument(ulong *)

- ea: `0x18001cfb4`
- end: `0x18001d11f`
- name: `?InitInstrument@@YAHPEAK@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d168`

## callees

- `0x18001cfb4`
- `0x180088420`
- `0x180096e00`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18001d08d`
- `ntdll!NtQueryValueKey` at `0x18001d0cf`
- `ntdll!NtQueryValueKey` at `0x180099f7d`
- `ntdll!NtQueryValueKey` at `0x18001d08d`
- `ntdll!NtQueryValueKey` at `0x18001d0cf`
- `ntdll!NtQueryValueKey` at `0x180099f7d`
- `ntdll!NtClose` at `0x18001d0e6`
- `ntdll!NtClose` at `0x18001d0e6`
- `ntdll!NtOpenKey` at `0x18001d04b`
- `ntdll!NtOpenKey` at `0x18001d04b`
- `ntdll!RtlInitUnicodeString` at `0x18001d012`
- `ntdll!RtlInitUnicodeString` at `0x18001d066`
- `ntdll!RtlInitUnicodeString` at `0x18001d0a6`
- `ntdll!RtlInitUnicodeString` at `0x180099f54`
- `ntdll!RtlInitUnicodeString` at `0x18001d012`
- `ntdll!RtlInitUnicodeString` at `0x18001d066`
- `ntdll!RtlInitUnicodeString` at `0x18001d0a6`
- `ntdll!RtlInitUnicodeString` at `0x180099f54`

## string_xrefs

- `0x18001cfe2`: `\Registry\Machine\System\CurrentControlSet\Control\Error Message Instrument\`

## pseudocode

```c
_BOOL8 __fastcall InitInstrument(unsigned int *a1)
{
  int v1; // ebx
  unsigned int v3; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING v8; // [rsp+60h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+37h] BYREF
  __int64 v11; // [rsp+B0h] [rbp+47h]

  KeyHandle = 0;
  DestinationString = 0;
  v11 = 0;
  ValueName = 0;
  ResultLength = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Error Message Instrument\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    return 0;
  v1 = 0;
  RtlInitUnicodeString(&ValueName, L"EnableLogging");
  if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x18u, &ResultLength) >= 0 )
  {
    v1 = HIDWORD(KeyValueInformation);
    RtlInitUnicodeString(&v8, L"LogSeverity");
    if ( NtQueryValueKey(KeyHandle, &v8, KeyValuePartialInformation, &KeyValueInformation, 0x18u, &ResultLength) < 0 )
    {
      v3 = 4;
    }
    else
    {
      v3 = HIDWORD(KeyValueInformation);
      if ( HIDWORD(KeyValueInformation) > 5 )
        v3 = 5;
    }
    gdwEMIControl = v3;
  }
  RtlInitUnicodeString(&ValueName, L"EnableDefaultReply");
  if ( NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x18u, &ResultLength) >= 0 )
    gfDMREnable = HIDWORD(KeyValueInformation);
  NtClose(KeyHandle);
  return v1 && (int)CreateLogSource() >= 0;
}

```

## disassembly

```asm
0x18001cfb4  mov     [rsp-8+arg_0], rbx
0x18001cfb9  push    rbp
0x18001cfba  lea     rbp, [rsp-57h]
0x18001cfbf  sub     rsp, 0C0h
0x18001cfc6  mov     rax, cs:__security_cookie
0x18001cfcd  xor     rax, rsp
0x18001cfd0  mov     [rbp+57h+var_8], rax
0x18001cfd4  xorps   xmm1, xmm1
0x18001cfd7  mov     [rbp+57h+KeyHandle], 0
0x18001cfdf  xorps   xmm0, xmm0
0x18001cfe2  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001cfe9  xor     eax, eax
0x18001cfeb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001cfef  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001cff3  mov     [rbp+57h+var_10], rax
0x18001cff7  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x18001cffb  mov     [rbp+57h+var_90], eax
0x18001cffe  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x18001d002  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x18001d006  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x18001d00a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x18001d00e  movups  [rbp+57h+KeyValueInformation], xmm0
0x18001d012  call    cs:__imp_RtlInitUnicodeString
0x18001d018  lea     rax, [rbp+57h+DestinationString]
0x18001d01c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001d023  xorps   xmm0, xmm0
0x18001d026  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001d02a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001d02e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001d036  mov     edx, 20019h; DesiredAccess
0x18001d03b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001d042  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d046  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001d04b  call    cs:__imp_NtOpenKey
0x18001d051  test    eax, eax
0x18001d053  js      loc_18001D0F0
0x18001d059  lea     rdx, aEnablelogging; "EnableLogging"
0x18001d060  xor     ebx, ebx
0x18001d062  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18001d066  call    cs:__imp_RtlInitUnicodeString
0x18001d06c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d070  lea     rax, [rbp+57h+var_90]
0x18001d074  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18001d079  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001d07d  lea     r8d, [rbx+2]; KeyValueInformationClass
0x18001d081  mov     [rsp+0C0h+Length], 18h; Length
0x18001d089  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001d08d  call    cs:__imp_NtQueryValueKey
0x18001d093  test    eax, eax
0x18001d095  jns     loc_180099F46
0x18001d09b  lea     rdx, aEnabledefaultr; "EnableDefaultReply"
0x18001d0a2  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18001d0a6  call    cs:__imp_RtlInitUnicodeString
0x18001d0ac  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18001d0b0  lea     rax, [rbp+57h+var_90]
0x18001d0b4  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x18001d0b9  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18001d0bd  mov     r8d, 2; KeyValueInformationClass
0x18001d0c3  mov     [rsp+0C0h+Length], 18h; Length
0x18001d0cb  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18001d0cf  call    cs:__imp_NtQueryValueKey
0x18001d0d5  test    eax, eax
0x18001d0d7  js      short loc_18001D0E2
0x18001d0d9  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x18001d0dc  mov     cs:?gfDMREnable@@3HA, eax; int gfDMREnable
0x18001d0e2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18001d0e6  call    cs:__imp_NtClose
0x18001d0ec  test    ebx, ebx
0x18001d0ee  jnz     short loc_18001D10F
0x18001d0f0  xor     eax, eax
0x18001d0f2  mov     rcx, [rbp+57h+var_8]
0x18001d0f6  xor     rcx, rsp; StackCookie
0x18001d0f9  call    __security_check_cookie
0x18001d0fe  mov     rbx, [rsp+0C0h+arg_0]
0x18001d106  add     rsp, 0C0h
0x18001d10d  pop     rbp
0x18001d10e  retn
0x18001d10f  call    ?CreateLogSource@@YAJXZ; CreateLogSource(void)
0x18001d114  xor     ecx, ecx
0x18001d116  test    eax, eax
0x18001d118  setns   cl
0x18001d11b  mov     eax, ecx
0x18001d11d  jmp     short loc_18001D0F2
0x180099f46  mov     ebx, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180099f49  lea     rdx, aLogseverity; "LogSeverity"
0x180099f50  lea     rcx, [rbp+57h+var_60]; DestinationString
0x180099f54  call    cs:__imp_RtlInitUnicodeString
0x180099f5a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180099f5e  lea     rax, [rbp+57h+var_90]
0x180099f62  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180099f67  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180099f6b  mov     r8d, 2; KeyValueInformationClass
0x180099f71  mov     [rsp+0C0h+Length], 18h; Length
0x180099f79  lea     rdx, [rbp+57h+var_60]; ValueName
0x180099f7d  call    cs:__imp_NtQueryValueKey
0x180099f83  test    eax, eax
0x180099f85  js      short loc_180099F96
0x180099f87  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x180099f8a  cmp     eax, 5
0x180099f8d  jbe     short loc_180099F9B
0x180099f8f  mov     eax, 5
0x180099f94  jmp     short loc_180099F9B
0x180099f96  mov     eax, 4
0x180099f9b  mov     cs:?gdwEMIControl@@3KA, eax; ulong gdwEMIControl
0x180099fa1  jmp     loc_18001D09B
```
