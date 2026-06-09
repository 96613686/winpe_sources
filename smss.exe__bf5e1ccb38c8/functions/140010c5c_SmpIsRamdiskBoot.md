# SmpIsRamdiskBoot

- ea: `0x140010c5c`
- end: `0x140010dc0`
- name: `SmpIsRamdiskBoot`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f120`

## callees

- `0x140010c5c`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140010d6d`
- `ntdll!RtlInitUnicodeString` at `0x140010d6d`
- `ntdll!NtClose` at `0x140010d94`
- `ntdll!NtClose` at `0x140010d94`
- `ntdll!NtOpenKey` at `0x140010d14`
- `ntdll!NtOpenKey` at `0x140010d14`
- `ntdll!NtQueryValueKey` at `0x140010d4b`
- `ntdll!NtQueryValueKey` at `0x140010d4b`
- `ntdll!RtlPrefixUnicodeString` at `0x140010d80`
- `ntdll!RtlPrefixUnicodeString` at `0x140010d80`

## string_xrefs

- `0x140010ca5`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall SmpIsRamdiskBoot(BOOLEAN *a1)
{
  NTSTATUS v2; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v12; // [rsp+B4h] [rbp-4Ch]
  WCHAR SourceString[258]; // [rsp+BCh] [rbp-44h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v6[0] = 6684772;
  v6[1] = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control";
  *(_QWORD *)&ValueName.Length = 2228256;
  ValueName.Buffer = L"SystemBootDevice";
  *(_QWORD *)&String1.Length = 1048590;
  String1.Buffer = L"ramdisk";
  ResultLength = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  DestinationString = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    ResultLength = 528;
    v2 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x210u, &ResultLength);
    if ( v2 >= 0 )
    {
      if ( v12 == 1 )
      {
        RtlInitUnicodeString(&DestinationString, SourceString);
        *a1 = RtlPrefixUnicodeString(&String1, &DestinationString, 1u);
        v2 = 0;
      }
      else
      {
        v2 = -1073741275;
      }
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140010c5c  mov     [rsp-8+arg_8], rbx
0x140010c61  mov     [rsp-8+arg_10], rdi
0x140010c66  push    rbp
0x140010c67  lea     rbp, [rsp-1D0h]
0x140010c6f  sub     rsp, 2D0h
0x140010c76  mov     rax, cs:__security_cookie
0x140010c7d  xor     rax, rsp
0x140010c80  mov     [rbp+1D0h+var_10], rax
0x140010c87  xor     eax, eax
0x140010c89  mov     qword ptr [rbp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x140010c91  mov     [rsp+2D0h+KeyHandle], rax
0x140010c96  lea     r8, [rbp+1D0h+ObjectAttributes]; ObjectAttributes
0x140010c9a  xorps   xmm0, xmm0
0x140010c9d  mov     qword ptr [rbp+1D0h+ObjectAttributes.Attributes], 40h ; '@'
0x140010ca5  lea     rax, aRegistryMachin_110; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x140010cac  mov     [rsp+2D0h+var_290], 660064h
0x140010cb5  mov     [rsp+2D0h+var_288], rax
0x140010cba  mov     rdi, rcx
0x140010cbd  lea     rax, aSystembootdevi; "SystemBootDevice"
0x140010cc4  mov     qword ptr [rsp+2D0h+ValueName.Length], 220020h
0x140010ccd  mov     [rsp+2D0h+ValueName.Buffer], rax
0x140010cd2  lea     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140010cd7  lea     rax, aRamdisk; "ramdisk"
0x140010cde  mov     qword ptr [rsp+2D0h+String1.Length], 10000Eh
0x140010ce7  mov     [rsp+2D0h+String1.Buffer], rax
0x140010cec  mov     edx, 20019h; DesiredAccess
0x140010cf1  lea     rax, [rsp+2D0h+var_290]
0x140010cf6  mov     [rsp+2D0h+var_2A0], 0
0x140010cfe  mov     [rbp+1D0h+ObjectAttributes.ObjectName], rax
0x140010d02  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x140010d07  mov     [rbp+1D0h+ObjectAttributes.RootDirectory], 0
0x140010d0f  movdqu  xmmword ptr [rbp+1D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140010d14  call    cs:__imp_NtOpenKey
0x140010d1a  mov     ebx, eax
0x140010d1c  test    eax, eax
0x140010d1e  js      short loc_140010D8A
0x140010d20  mov     ecx, 210h
0x140010d25  lea     rax, [rsp+2D0h+var_2A0]
0x140010d2a  mov     [rsp+2D0h+ResultLength], rax; ResultLength
0x140010d2f  lea     r9, [rbp+1D0h+KeyValueInformation]; KeyValueInformation
0x140010d33  mov     [rsp+2D0h+Length], ecx; Length
0x140010d37  lea     rdx, [rsp+2D0h+ValueName]; ValueName
0x140010d3c  mov     [rsp+2D0h+var_2A0], ecx
0x140010d40  mov     r8d, 2; KeyValueInformationClass
0x140010d46  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x140010d4b  call    cs:__imp_NtQueryValueKey
0x140010d51  mov     ebx, eax
0x140010d53  test    eax, eax
0x140010d55  js      short loc_140010D8A
0x140010d57  cmp     [rbp+1D0h+var_21C], 1
0x140010d5b  jz      short loc_140010D64
0x140010d5d  mov     ebx, 0C0000225h
0x140010d62  jmp     short loc_140010D8A
0x140010d64  lea     rdx, [rbp+1D0h+SourceString]; SourceString
0x140010d68  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x140010d6d  call    cs:__imp_RtlInitUnicodeString
0x140010d73  mov     r8b, 1; CaseInSensitive
0x140010d76  lea     rdx, [rsp+2D0h+DestinationString]; String2
0x140010d7b  lea     rcx, [rsp+2D0h+String1]; String1
0x140010d80  call    cs:__imp_RtlPrefixUnicodeString
0x140010d86  mov     [rdi], al
0x140010d88  xor     ebx, ebx
0x140010d8a  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x140010d8f  test    rcx, rcx
0x140010d92  jz      short loc_140010D9A
0x140010d94  call    cs:__imp_NtClose
0x140010d9a  mov     eax, ebx
0x140010d9c  mov     rcx, [rbp+1D0h+var_10]
0x140010da3  xor     rcx, rsp; StackCookie
0x140010da6  call    __security_check_cookie
0x140010dab  lea     r11, [rsp+2D0h+var_s0]
0x140010db3  mov     rbx, [r11+18h]
0x140010db7  mov     rdi, [r11+20h]
0x140010dbb  mov     rsp, r11
0x140010dbe  pop     rbp
0x140010dbf  retn
```
