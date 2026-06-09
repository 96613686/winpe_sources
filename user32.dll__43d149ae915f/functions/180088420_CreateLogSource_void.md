# CreateLogSource(void)

- ea: `0x180088420`
- end: `0x180088560`
- name: `?CreateLogSource@@YAJXZ`
- size: `320`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001cfb4`

## callees

- `0x180088420`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180088514`
- `ntdll!NtQueryValueKey` at `0x180088514`
- `ntdll!NtClose` at `0x180088538`
- `ntdll!NtClose` at `0x180088538`
- `ntdll!NtOpenKey` at `0x1800884c1`
- `ntdll!NtOpenKey` at `0x1800884c1`
- `ntdll!RtlInitUnicodeString` at `0x180088481`
- `ntdll!RtlInitUnicodeString` at `0x1800884ec`
- `ntdll!RtlInitUnicodeString` at `0x180088481`
- `ntdll!RtlInitUnicodeString` at `0x1800884ec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18008852b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18008852b`

## string_xrefs

- `0x180088520`: `%SystemRoot%\System32\user32.dll`
- `0x18008845d`: `\Registry\Machine\System\CurrentControlSet\Services\EventLog\Application\Error Instrument\`

## pseudocode

```c
__int64 CreateLogSource(void)
{
  NTSTATUS v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR String1[258]; // [rsp+9Ch] [rbp-64h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ValueName = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\EventLog\\Application\\Error Instrument\\");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    memset_0(KeyValueInformation, 0, 0x210u);
    RtlInitUnicodeString(&ValueName, L"EventMessageFile");
    v0 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x210u, &ResultLength);
    if ( v0 >= 0 )
      v0 = lstrcmpiW(String1, L"%SystemRoot%\\System32\\user32.dll");
    NtClose(KeyHandle);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180088420  mov     [rsp-8+arg_0], rbx
0x180088425  push    rbp
0x180088426  lea     rbp, [rsp-1B0h]
0x18008842e  sub     rsp, 2B0h
0x180088435  mov     rax, cs:__security_cookie
0x18008843c  xor     rax, rsp
0x18008843f  mov     [rbp+1B0h+var_10], rax
0x180088446  xorps   xmm1, xmm1
0x180088449  mov     [rsp+2B0h+KeyHandle], 0
0x180088452  xorps   xmm0, xmm0
0x180088455  mov     [rsp+2B0h+var_280], 0
0x18008845d  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x180088464  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180088469  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18008846e  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm1
0x180088473  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm1
0x180088478  movups  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18008847c  movups  xmmword ptr [rsp+2B0h+ValueName.Length], xmm0
0x180088481  call    cs:__imp_RtlInitUnicodeString
0x180088487  lea     rax, [rsp+2B0h+DestinationString]
0x18008848c  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180088494  xorps   xmm0, xmm0
0x180088497  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x18008849c  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x1800884a1  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], 0
0x1800884aa  mov     edx, 20019h; DesiredAccess
0x1800884af  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800884b7  lea     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x1800884bc  movdqu  xmmword ptr [rbp+1B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800884c1  call    cs:__imp_NtOpenKey
0x1800884c7  mov     ebx, eax
0x1800884c9  test    eax, eax
0x1800884cb  js      short loc_18008853E
0x1800884cd  mov     ebx, 210h
0x1800884d2  lea     rcx, [rbp+1B0h+KeyValueInformation]; void *
0x1800884d6  mov     r8d, ebx; Size
0x1800884d9  xor     edx, edx; Val
0x1800884db  call    memset_0
0x1800884e0  lea     rdx, aEventmessagefi; "EventMessageFile"
0x1800884e7  lea     rcx, [rsp+2B0h+ValueName]; DestinationString
0x1800884ec  call    cs:__imp_RtlInitUnicodeString
0x1800884f2  mov     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x1800884f7  lea     rax, [rsp+2B0h+var_280]
0x1800884fc  mov     [rsp+2B0h+ResultLength], rax; ResultLength
0x180088501  lea     r9, [rbp+1B0h+KeyValueInformation]; KeyValueInformation
0x180088505  mov     r8d, 2; KeyValueInformationClass
0x18008850b  mov     [rsp+2B0h+Length], ebx; Length
0x18008850f  lea     rdx, [rsp+2B0h+ValueName]; ValueName
0x180088514  call    cs:__imp_NtQueryValueKey
0x18008851a  mov     ebx, eax
0x18008851c  test    eax, eax
0x18008851e  js      short loc_180088533
0x180088520  lea     rdx, aSystemrootSyst; "%SystemRoot%\\System32\\user32.dll"
0x180088527  lea     rcx, [rbp+1B0h+String1]; lpString1
0x18008852b  call    cs:__imp_lstrcmpiW
0x180088531  mov     ebx, eax
0x180088533  mov     rcx, [rsp+2B0h+KeyHandle]; Handle
0x180088538  call    cs:__imp_NtClose
0x18008853e  mov     eax, ebx
0x180088540  mov     rcx, [rbp+1B0h+var_10]
0x180088547  xor     rcx, rsp; StackCookie
0x18008854a  call    __security_check_cookie
0x18008854f  mov     rbx, [rsp+2B0h+arg_0]
0x180088557  add     rsp, 2B0h
0x18008855e  pop     rbp
0x18008855f  retn
```
