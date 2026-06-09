# TdxIsPrematureConnectIndDisabled

- ea: `0x1400119d0`
- end: `0x140011b13`
- name: `TdxIsPrematureConnectIndDisabled`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x140012620`

## callees

- `0x1400119d0`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140011ae7`
- `ntoskrnl!ZwClose` at `0x140011ae7`
- `ntoskrnl!ZwQueryValueKey` at `0x140011ab4`
- `ntoskrnl!ZwQueryValueKey` at `0x140011ab4`
- `ntoskrnl!ZwOpenKey` at `0x140011a6a`
- `ntoskrnl!ZwOpenKey` at `0x140011a6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a85`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a85`

## string_xrefs

- `0x1400119fd`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
bool TdxIsPrematureConnectIndDisabled()
{
  bool v0; // bl
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp+27h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+37h] BYREF
  int v8; // [rsp+A0h] [rbp+47h]

  KeyHandle = 0;
  v8 = 0;
  ResultLength = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  v0 = 0;
  DestinationString = 0;
  ValueName = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"TdxPrematureConnectIndDisabled");
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      v0 = HIDWORD(KeyValueInformation) == 1;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x1400119d0  mov     [rsp-8+arg_0], rbx
0x1400119d5  push    rbp
0x1400119d6  lea     rbp, [rsp-57h]
0x1400119db  sub     rsp, 0B0h
0x1400119e2  mov     rax, cs:__security_cookie
0x1400119e9  xor     rax, rsp
0x1400119ec  mov     [rbp+57h+var_8], rax
0x1400119f0  xorps   xmm0, xmm0
0x1400119f3  mov     [rbp+57h+KeyHandle], 0
0x1400119fb  xor     eax, eax
0x1400119fd  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x140011a04  xorps   xmm1, xmm1
0x140011a07  mov     [rbp+57h+var_10], eax
0x140011a0a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140011a0e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140011a12  mov     [rbp+57h+var_80], eax
0x140011a15  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140011a19  xor     bl, bl
0x140011a1b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140011a1f  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140011a23  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140011a27  movups  [rbp+57h+KeyValueInformation], xmm0
0x140011a2b  call    cs:__imp_RtlInitUnicodeString
0x140011a32  nop     dword ptr [rax+rax+00h]
0x140011a37  lea     rax, [rbp+57h+DestinationString]
0x140011a3b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140011a42  xorps   xmm0, xmm0
0x140011a45  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140011a49  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140011a4d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140011a55  mov     edx, 20019h; DesiredAccess
0x140011a5a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140011a61  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011a65  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140011a6a  call    cs:__imp_ZwOpenKey
0x140011a71  nop     dword ptr [rax+rax+00h]
0x140011a76  test    eax, eax
0x140011a78  js      short loc_140011ADE
0x140011a7a  lea     rdx, aTdxprematureco; "TdxPrematureConnectIndDisabled"
0x140011a81  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140011a85  call    cs:__imp_RtlInitUnicodeString
0x140011a8c  nop     dword ptr [rax+rax+00h]
0x140011a91  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011a95  lea     rax, [rbp+57h+var_80]
0x140011a99  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140011a9e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140011aa2  mov     r8d, 2; KeyValueInformationClass
0x140011aa8  mov     [rsp+0B0h+Length], 14h; Length
0x140011ab0  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140011ab4  call    cs:__imp_ZwQueryValueKey
0x140011abb  nop     dword ptr [rax+rax+00h]
0x140011ac0  test    eax, eax
0x140011ac2  js      short loc_140011ADE
0x140011ac4  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140011ac8  jnz     short loc_140011ADE
0x140011aca  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x140011ace  jnz     short loc_140011ADE
0x140011ad0  mov     eax, 1
0x140011ad5  movzx   ebx, bl
0x140011ad8  cmp     dword ptr [rbp+57h+KeyValueInformation+0Ch], eax
0x140011adb  cmovz   ebx, eax
0x140011ade  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140011ae2  test    rcx, rcx
0x140011ae5  jz      short loc_140011AF3
0x140011ae7  call    cs:__imp_ZwClose
0x140011aee  nop     dword ptr [rax+rax+00h]
0x140011af3  mov     al, bl
0x140011af5  mov     rcx, [rbp+57h+var_8]
0x140011af9  xor     rcx, rsp; StackCookie
0x140011afc  call    __security_check_cookie
0x140011b01  mov     rbx, [rsp+0B0h+arg_0]
0x140011b09  add     rsp, 0B0h
0x140011b10  pop     rbp
0x140011b11  retn
```
