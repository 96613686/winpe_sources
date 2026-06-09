# TdxIsV6RegistryDisabled

- ea: `0x140014988`
- end: `0x140014aaa`
- name: `TdxIsV6RegistryDisabled`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140014c84`

## callees

- `0x140014988`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140014a7e`
- `ntoskrnl!ZwClose` at `0x140014a7e`
- `ntoskrnl!ZwQueryValueKey` at `0x140014a4f`
- `ntoskrnl!ZwQueryValueKey` at `0x140014a4f`
- `ntoskrnl!ZwOpenKey` at `0x140014a0a`
- `ntoskrnl!ZwOpenKey` at `0x140014a0a`

## string_xrefs

- `0x1400149bf`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x140014a1e`: `DisabledComponents`

## pseudocode

```c
bool TdxIsV6RegistryDisabled()
{
  bool v0; // bl
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v4[2]; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  __int128 KeyValueInformation; // [rsp+90h] [rbp+37h] BYREF
  int v8; // [rsp+A0h] [rbp+47h]

  v4[0] = 9175178;
  v8 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  v4[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip6\\Parameters";
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  ValueName = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v0 = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    ValueName.Buffer = L"DisabledComponents";
    *(_DWORD *)&ValueName.Length = 2490404;
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      v0 = BYTE12(KeyValueInformation) == 0xFF;
    }
    ZwClose(KeyHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x140014988  mov     [rsp-8+arg_0], rbx
0x14001498d  push    rbp
0x14001498e  lea     rbp, [rsp-57h]
0x140014993  sub     rsp, 0B0h
0x14001499a  mov     rax, cs:__security_cookie
0x1400149a1  xor     rax, rsp
0x1400149a4  mov     [rbp+57h+var_8], rax
0x1400149a8  xor     eax, eax
0x1400149aa  mov     [rbp+57h+var_70], 8C008Ah
0x1400149b2  xorps   xmm0, xmm0
0x1400149b5  mov     [rbp+57h+var_10], eax
0x1400149b8  mov     [rbp+57h+var_80], eax
0x1400149bb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400149bf  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400149c6  mov     [rbp+57h+KeyHandle], 0
0x1400149ce  mov     [rbp+57h+var_68], rax
0x1400149d2  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400149d6  lea     rax, [rbp+57h+var_70]
0x1400149da  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400149e2  mov     edx, 20019h; DesiredAccess
0x1400149e7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400149eb  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1400149ef  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400149f7  xor     bl, bl
0x1400149f9  movups  [rbp+57h+KeyValueInformation], xmm0
0x1400149fd  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140014a05  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140014a0a  call    cs:__imp_ZwOpenKey
0x140014a11  nop     dword ptr [rax+rax+00h]
0x140014a16  test    eax, eax
0x140014a18  js      short loc_140014A8A
0x140014a1a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140014a1e  lea     rax, aDisabledcompon; "DisabledComponents"
0x140014a25  mov     [rbp+57h+ValueName.Buffer], rax
0x140014a29  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140014a2d  lea     rax, [rbp+57h+var_80]
0x140014a31  mov     dword ptr [rbp+57h+ValueName.Length], 260024h
0x140014a38  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140014a3d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140014a41  mov     r8d, 2; KeyValueInformationClass
0x140014a47  mov     [rsp+0B0h+Length], 14h; Length
0x140014a4f  call    cs:__imp_ZwQueryValueKey
0x140014a56  nop     dword ptr [rax+rax+00h]
0x140014a5b  test    eax, eax
0x140014a5d  js      short loc_140014A7A
0x140014a5f  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x140014a63  jnz     short loc_140014A7A
0x140014a65  cmp     dword ptr [rbp+57h+KeyValueInformation+8], 4
0x140014a69  jnz     short loc_140014A7A
0x140014a6b  cmp     byte ptr [rbp+57h+KeyValueInformation+0Ch], 0FFh
0x140014a6f  mov     eax, 1
0x140014a74  movzx   ebx, bl
0x140014a77  cmovz   ebx, eax
0x140014a7a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140014a7e  call    cs:__imp_ZwClose
0x140014a85  nop     dword ptr [rax+rax+00h]
0x140014a8a  mov     al, bl
0x140014a8c  mov     rcx, [rbp+57h+var_8]
0x140014a90  xor     rcx, rsp; StackCookie
0x140014a93  call    __security_check_cookie
0x140014a98  mov     rbx, [rsp+0B0h+arg_0]
0x140014aa0  add     rsp, 0B0h
0x140014aa7  pop     rbp
0x140014aa8  retn
```
