# QueryRegDWord

- ea: `0x18000a880`
- end: `0x18000a98e`
- name: `QueryRegDWord`
- size: `270`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a5d4`
- `0x180025e94`

## callees

- `0x18000a880`
- `0x18001deb0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000a907`
- `ntdll!NtOpenKey` at `0x18000a907`
- `ntdll!NtQueryValueKey` at `0x18000a945`
- `ntdll!NtQueryValueKey` at `0x18000a945`
- `ntdll!RtlInitUnicodeString` at `0x18000a8cd`
- `ntdll!RtlInitUnicodeString` at `0x18000a91a`
- `ntdll!RtlInitUnicodeString` at `0x18000a8cd`
- `ntdll!RtlInitUnicodeString` at `0x18000a91a`
- `ntdll!NtClose` at `0x18000a967`
- `ntdll!NtClose` at `0x18000a967`

## pseudocode

```c
__int64 __fastcall QueryRegDWord(PCWSTR SourceString, PCWSTR a2, _DWORD *a3)
{
  NTSTATUS v5; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-69h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp-39h] BYREF
  int v12; // [rsp+84h] [rbp-35h]
  unsigned int v13; // [rsp+88h] [rbp-31h]
  int v14; // [rsp+8Ch] [rbp-2Dh]

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v5 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v5 = NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x64u,
           &ResultLength);
    if ( v5 >= 0 && v13 >= 4 && v12 == 4 )
      *a3 = v14;
    NtClose(KeyHandle);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a880  mov     [rsp-8+arg_18], rbx
0x18000a885  push    rbp
0x18000a886  push    rsi
0x18000a887  push    rdi
0x18000a888  lea     rbp, [rsp-47h]
0x18000a88d  sub     rsp, 100h
0x18000a894  mov     rax, cs:__security_cookie
0x18000a89b  xor     rax, rsp
0x18000a89e  mov     [rbp+57h+var_20], rax
0x18000a8a2  xorps   xmm0, xmm0
0x18000a8a5  xor     eax, eax
0x18000a8a7  mov     rsi, rdx
0x18000a8aa  mov     [rsp+110h+KeyHandle], rax
0x18000a8af  mov     rdx, rcx; SourceString
0x18000a8b2  mov     [rsp+110h+var_E0], eax
0x18000a8b6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000a8ba  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000a8be  mov     rdi, r8
0x18000a8c1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000a8c5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000a8c9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000a8cd  call    cs:__imp_RtlInitUnicodeString
0x18000a8d3  lea     rax, [rbp+57h+DestinationString]
0x18000a8d7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000a8de  xorps   xmm0, xmm0
0x18000a8e1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000a8e5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000a8e9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000a8f1  mov     edx, 20019h; DesiredAccess
0x18000a8f6  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a8fd  lea     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x18000a902  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a907  call    cs:__imp_NtOpenKey
0x18000a90d  mov     ebx, eax
0x18000a90f  test    eax, eax
0x18000a911  js      short loc_18000A96D
0x18000a913  mov     rdx, rsi; SourceString
0x18000a916  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000a91a  call    cs:__imp_RtlInitUnicodeString
0x18000a920  mov     rcx, [rsp+110h+KeyHandle]; KeyHandle
0x18000a925  lea     rax, [rsp+110h+var_E0]
0x18000a92a  mov     [rsp+110h+ResultLength], rax; ResultLength
0x18000a92f  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000a933  mov     r8d, 2; KeyValueInformationClass
0x18000a939  mov     [rsp+110h+Length], 64h ; 'd'; Length
0x18000a941  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000a945  call    cs:__imp_NtQueryValueKey
0x18000a94b  mov     ebx, eax
0x18000a94d  test    eax, eax
0x18000a94f  js      short loc_18000A962
0x18000a951  cmp     [rbp+57h+var_88], 4
0x18000a955  jb      short loc_18000A962
0x18000a957  cmp     [rbp+57h+var_8C], 4
0x18000a95b  jnz     short loc_18000A962
0x18000a95d  mov     eax, [rbp+57h+var_84]
0x18000a960  mov     [rdi], eax
0x18000a962  mov     rcx, [rsp+110h+KeyHandle]; Handle
0x18000a967  call    cs:__imp_NtClose
0x18000a96d  mov     eax, ebx
0x18000a96f  mov     rcx, [rbp+57h+var_20]
0x18000a973  xor     rcx, rsp; StackCookie
0x18000a976  call    __security_check_cookie
0x18000a97b  mov     rbx, [rsp+110h+arg_18]
0x18000a983  add     rsp, 100h
0x18000a98a  pop     rdi
0x18000a98b  pop     rsi
0x18000a98c  pop     rbp
0x18000a98d  retn
```
