# GetRegistryKeyValue(ushort *,ushort *,_KEY_VALUE_PARTIAL_INFORMATION *,ulong)

- ea: `0x1800516c8`
- end: `0x1800517bc`
- name: `?GetRegistryKeyValue@@YAKPEAG0PEAU_KEY_VALUE_PARTIAL_INFORMATION@@K@Z`
- size: `244`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, PCWSTR, PVOID KeyValueInformation, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006440`
- `0x180051664`

## callees

- `0x1800516c8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800517ac`
- `ntdll!RtlNtStatusToDosError` at `0x1800517ac`
- `ntdll!NtQueryValueKey` at `0x180051785`
- `ntdll!NtQueryValueKey` at `0x180051785`
- `ntdll!NtClose` at `0x180051791`
- `ntdll!NtClose` at `0x180051791`
- `ntdll!NtOpenKey` at `0x180051758`
- `ntdll!NtOpenKey` at `0x180051758`
- `ntdll!RtlInitUnicodeString` at `0x180051712`
- `ntdll!RtlInitUnicodeString` at `0x18005171f`
- `ntdll!RtlInitUnicodeString` at `0x180051712`
- `ntdll!RtlInitUnicodeString` at `0x18005171f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800517b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800517b4`

## pseudocode

```c
__int64 __fastcall GetRegistryKeyValue(PCWSTR SourceString, PCWSTR a2, PVOID KeyValueInformation, int a4)
{
  int v7; // ebx
  ULONG v9; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&ValueName, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v7 < 0
    || (v7 = NtQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               a4 + 12,
               &ResultLength),
        NtClose(KeyHandle),
        v7 < 0) )
  {
    v9 = RtlNtStatusToDosError(v7);
    SetLastError(v9);
  }
  return ResultLength;
}

```

## disassembly

```asm
0x1800516c8  push    rbp
0x1800516ca  push    rbx
0x1800516cb  push    rsi
0x1800516cc  push    rdi
0x1800516cd  lea     rbp, [rsp-3Fh]
0x1800516d2  sub     rsp, 98h
0x1800516d9  xorps   xmm0, xmm0
0x1800516dc  mov     [rbp+57h+KeyHandle], 0
0x1800516e4  mov     rbx, rdx
0x1800516e7  mov     [rbp+57h+var_80], 0
0x1800516ee  mov     rdx, rcx; SourceString
0x1800516f1  xorps   xmm1, xmm1
0x1800516f4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800516f8  mov     edi, r9d
0x1800516fb  mov     rsi, r8
0x1800516fe  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180051702  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180051706  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005170a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18005170e  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x180051712  call    cs:__imp_RtlInitUnicodeString
0x180051718  mov     rdx, rbx; SourceString
0x18005171b  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x18005171f  call    cs:__imp_RtlInitUnicodeString
0x180051725  lea     rax, [rbp+57h+DestinationString]
0x180051729  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180051730  xorps   xmm0, xmm0
0x180051733  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180051737  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005173b  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180051743  mov     edx, 20019h; DesiredAccess
0x180051748  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18005174f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180051753  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051758  call    cs:__imp_NtOpenKey
0x18005175e  mov     ebx, eax
0x180051760  test    eax, eax
0x180051762  js      short loc_1800517AA
0x180051764  lea     rcx, [rbp+57h+var_80]
0x180051768  mov     r9, rsi; KeyValueInformation
0x18005176b  mov     [rsp+0B0h+ResultLength], rcx; ResultLength
0x180051770  lea     eax, [rdi+0Ch]
0x180051773  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180051777  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005177b  mov     r8d, 2; KeyValueInformationClass
0x180051781  mov     [rsp+0B0h+Length], eax; Length
0x180051785  call    cs:__imp_NtQueryValueKey
0x18005178b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18005178f  mov     ebx, eax
0x180051791  call    cs:__imp_NtClose
0x180051797  test    ebx, ebx
0x180051799  js      short loc_1800517AA
0x18005179b  mov     eax, [rbp+57h+var_80]
0x18005179e  add     rsp, 98h
0x1800517a5  pop     rdi
0x1800517a6  pop     rsi
0x1800517a7  pop     rbx
0x1800517a8  pop     rbp
0x1800517a9  retn
0x1800517aa  mov     ecx, ebx; Status
0x1800517ac  call    cs:__imp_RtlNtStatusToDosError
0x1800517b2  mov     ecx, eax; dwErrCode
0x1800517b4  call    cs:__imp_SetLastError
0x1800517ba  jmp     short loc_18005179B
```
