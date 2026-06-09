# CheckNullSessionAccess

- ea: `0x18000ad5c`
- end: `0x18000ae8a`
- name: `CheckNullSessionAccess`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a5d4`

## callees

- `0x18000ad5c`
- `0x18000ae90`
- `0x18001deb0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000ade2`
- `ntdll!NtOpenKey` at `0x18000ade2`
- `ntdll!NtQueryValueKey` at `0x18000ae22`
- `ntdll!NtQueryValueKey` at `0x18000ae22`
- `ntdll!RtlInitUnicodeString` at `0x18000ada9`
- `ntdll!RtlInitUnicodeString` at `0x18000adf9`
- `ntdll!RtlInitUnicodeString` at `0x18000ada9`
- `ntdll!RtlInitUnicodeString` at `0x18000adf9`
- `ntdll!NtClose` at `0x18000ae58`
- `ntdll!NtClose` at `0x18000ae58`

## string_xrefs

- `0x18000ad7f`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
__int64 CheckNullSessionAccess()
{
  int v0; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-79h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-59h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+80h] [rbp-29h] BYREF
  int v7; // [rsp+84h] [rbp-25h]
  unsigned int v8; // [rsp+88h] [rbp-21h]
  int v9; // [rsp+8Ch] [rbp-1Dh]

  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  SsRestrictNullSessions = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 < 0 )
    return NetpNtStatusToApiStatus(v0);
  RtlInitUnicodeString(&DestinationString, L"RestrictAnonymous");
  v0 = NtQueryValueKey(
         KeyHandle,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x64u,
         &ResultLength);
  if ( v0 < 0 )
  {
    if ( v0 == -1073741772 )
      v0 = 0;
  }
  else if ( v8 >= 4 && v7 == 4 )
  {
    if ( v9 )
      SsRestrictNullSessions = 1;
  }
  NtClose(KeyHandle);
  if ( v0 < 0 )
    return NetpNtStatusToApiStatus(v0);
  else
    return 0;
}

```

## disassembly

```asm
0x18000ad5c  mov     [rsp-8+arg_0], rbx
0x18000ad61  push    rbp
0x18000ad62  lea     rbp, [rsp-57h]
0x18000ad67  sub     rsp, 100h
0x18000ad6e  mov     rax, cs:__security_cookie
0x18000ad75  xor     rax, rsp
0x18000ad78  mov     [rbp+57h+var_10], rax
0x18000ad7c  xorps   xmm0, xmm0
0x18000ad7f  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000ad86  xor     eax, eax
0x18000ad88  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000ad8c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000ad90  mov     [rbp+57h+KeyHandle], rax
0x18000ad94  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000ad98  mov     [rbp+57h+var_D0], eax
0x18000ad9b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000ad9f  mov     cs:SsRestrictNullSessions, al
0x18000ada5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000ada9  call    cs:__imp_RtlInitUnicodeString
0x18000adaf  lea     rax, [rbp+57h+DestinationString]
0x18000adb3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000adba  xorps   xmm0, xmm0
0x18000adbd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000adc1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000adc5  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000adcd  mov     edx, 20019h; DesiredAccess
0x18000add2  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000add9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000addd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ade2  call    cs:__imp_NtOpenKey
0x18000ade8  mov     ebx, eax
0x18000adea  test    eax, eax
0x18000adec  js      short loc_18000AE66
0x18000adee  lea     rdx, aRestrictanonym; "RestrictAnonymous"
0x18000adf5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000adf9  call    cs:__imp_RtlInitUnicodeString
0x18000adff  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18000ae03  lea     rax, [rbp+57h+var_D0]
0x18000ae07  mov     [rsp+100h+ResultLength], rax; ResultLength
0x18000ae0c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x18000ae10  mov     r8d, 2; KeyValueInformationClass
0x18000ae16  mov     [rsp+100h+Length], 64h ; 'd'; Length
0x18000ae1e  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x18000ae22  call    cs:__imp_NtQueryValueKey
0x18000ae28  mov     ebx, eax
0x18000ae2a  test    eax, eax
0x18000ae2c  js      short loc_18000AE49
0x18000ae2e  cmp     [rbp+57h+var_78], 4
0x18000ae32  jb      short loc_18000AE54
0x18000ae34  cmp     [rbp+57h+var_7C], 4
0x18000ae38  jnz     short loc_18000AE54
0x18000ae3a  cmp     [rbp+57h+var_74], 1
0x18000ae3e  jb      short loc_18000AE54
0x18000ae40  mov     cs:SsRestrictNullSessions, 1
0x18000ae47  jmp     short loc_18000AE54
0x18000ae49  xor     eax, eax
0x18000ae4b  cmp     ebx, 0C0000034h
0x18000ae51  cmovz   ebx, eax
0x18000ae54  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000ae58  call    cs:__imp_NtClose
0x18000ae5e  test    ebx, ebx
0x18000ae60  js      short loc_18000AE66
0x18000ae62  xor     eax, eax
0x18000ae64  jmp     short loc_18000AE6D
0x18000ae66  mov     ecx, ebx; Status
0x18000ae68  call    NetpNtStatusToApiStatus
0x18000ae6d  mov     rcx, [rbp+57h+var_10]
0x18000ae71  xor     rcx, rsp; StackCookie
0x18000ae74  call    __security_check_cookie
0x18000ae79  mov     rbx, [rsp+100h+arg_0]
0x18000ae81  add     rsp, 100h
0x18000ae88  pop     rbp
0x18000ae89  retn
```
