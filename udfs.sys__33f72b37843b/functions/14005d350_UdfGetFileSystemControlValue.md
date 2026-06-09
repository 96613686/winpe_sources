# UdfGetFileSystemControlValue

- ea: `0x14005d350`
- end: `0x14005d4ee`
- name: `UdfGetFileSystemControlValue`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005d4f4`

## callees

- `0x14001bc30`
- `0x14005d350`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14005d3d7`
- `ntoskrnl!ZwOpenKey` at `0x14005d3d7`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d427`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d498`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d427`
- `ntoskrnl!ZwQueryValueKey` at `0x14005d498`
- `ntoskrnl!ZwClose` at `0x14005d4c4`
- `ntoskrnl!ZwClose` at `0x14005d4c4`

## string_xrefs

- `0x14005d37c`: `\Registry\Machine\System\CurrentControlSet\Control\FileSystem`

## pseudocode

```c
int UdfGetFileSystemControlValue()
{
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v4[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD KeyValueInformation[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v7; // [rsp+98h] [rbp-68h]
  int v8; // [rsp+9Ch] [rbp-64h]

  KeyHandle = 0;
  ResultLength = 0;
  v4[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\FileSystem";
  v4[0] = 8126586;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ValueName = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    ValueName.Buffer = L"UdfsCloseSessionOnEject";
    *(_DWORD *)&ValueName.Length = 3145774;
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x9Cu, &ResultLength) >= 0
      && v8 )
    {
      if ( (*(_DWORD *)((char *)KeyValueInformation + v7) & 1) != 0 )
        word_140025B56 |= 4u;
      if ( (*(_DWORD *)((char *)KeyValueInformation + v7) & 2) != 0 )
        word_140025B56 |= 8u;
    }
    ValueName.Buffer = L"UdfsSoftwareDefectManagement";
    *(_DWORD *)&ValueName.Length = 3801144;
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, KeyValueInformation, 0x9Cu, &ResultLength) >= 0
      && v8
      && *(_DWORD *)((char *)KeyValueInformation + v7) == 1 )
    {
      word_140025B56 |= 2u;
    }
    return ZwClose(KeyHandle);
  }
  return result;
}

```

## disassembly

```asm
0x14005d350  mov     [rsp-8+arg_0], rdi
0x14005d355  push    rbp
0x14005d356  lea     rbp, [rsp-40h]
0x14005d35b  sub     rsp, 140h
0x14005d362  mov     rax, cs:__security_cookie
0x14005d369  xor     rax, rsp
0x14005d36c  mov     [rbp+40h+var_10], rax
0x14005d370  xorps   xmm0, xmm0
0x14005d373  mov     [rsp+140h+KeyHandle], 0
0x14005d37c  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14005d383  mov     [rsp+140h+var_110], 0
0x14005d38b  mov     [rsp+140h+var_E8], rax
0x14005d390  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x14005d395  lea     rax, [rsp+140h+var_F0]
0x14005d39a  mov     [rsp+140h+var_F0], 7C007Ah
0x14005d3a3  mov     edx, 20019h; DesiredAccess
0x14005d3a8  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x14005d3ad  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x14005d3b2  mov     qword ptr [rsp+140h+ObjectAttributes.Length], 30h ; '0'
0x14005d3bb  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x14005d3c0  mov     qword ptr [rsp+140h+ObjectAttributes.Attributes], 240h
0x14005d3c9  mov     [rsp+140h+ObjectAttributes.RootDirectory], 0
0x14005d3d2  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005d3d7  call    cs:__imp_ZwOpenKey
0x14005d3de  nop     dword ptr [rax+rax+00h]
0x14005d3e3  test    eax, eax
0x14005d3e5  js      loc_14005D4D0
0x14005d3eb  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x14005d3f0  lea     rax, aUdfsclosesessi; "UdfsCloseSessionOnEject"
0x14005d3f7  mov     [rsp+140h+ValueName.Buffer], rax
0x14005d3fc  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x14005d400  lea     rax, [rsp+140h+var_110]
0x14005d405  mov     dword ptr [rsp+140h+ValueName.Length], 30002Eh
0x14005d40d  mov     [rsp+140h+ResultLength], rax; ResultLength
0x14005d412  lea     rdx, [rsp+140h+ValueName]; ValueName
0x14005d417  mov     edi, 1
0x14005d41c  mov     [rsp+140h+Length], 9Ch; Length
0x14005d424  mov     r8d, edi; KeyValueInformationClass
0x14005d427  call    cs:__imp_ZwQueryValueKey
0x14005d42e  nop     dword ptr [rax+rax+00h]
0x14005d433  test    eax, eax
0x14005d435  js      short loc_14005D461
0x14005d437  cmp     [rbp+40h+var_A4], 0
0x14005d43b  jz      short loc_14005D461
0x14005d43d  mov     ecx, [rbp+40h+var_A8]
0x14005d440  mov     eax, [rbp+rcx+40h+KeyValueInformation]
0x14005d444  test    dil, al
0x14005d447  jz      short loc_14005D451
0x14005d449  or      cs:word_140025B56, 4
0x14005d451  mov     eax, [rbp+rcx+40h+KeyValueInformation]
0x14005d455  test    al, 2
0x14005d457  jz      short loc_14005D461
0x14005d459  or      cs:word_140025B56, 8
0x14005d461  mov     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x14005d466  lea     rax, aUdfssoftwarede; "UdfsSoftwareDefectManagement"
0x14005d46d  mov     [rsp+140h+ValueName.Buffer], rax
0x14005d472  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x14005d476  lea     rax, [rsp+140h+var_110]
0x14005d47b  mov     dword ptr [rsp+140h+ValueName.Length], 3A0038h
0x14005d483  mov     [rsp+140h+ResultLength], rax; ResultLength
0x14005d488  lea     rdx, [rsp+140h+ValueName]; ValueName
0x14005d48d  mov     r8d, edi; KeyValueInformationClass
0x14005d490  mov     [rsp+140h+Length], 9Ch; Length
0x14005d498  call    cs:__imp_ZwQueryValueKey
0x14005d49f  nop     dword ptr [rax+rax+00h]
0x14005d4a4  test    eax, eax
0x14005d4a6  js      short loc_14005D4BF
0x14005d4a8  cmp     [rbp+40h+var_A4], 0
0x14005d4ac  jz      short loc_14005D4BF
0x14005d4ae  mov     eax, [rbp+40h+var_A8]
0x14005d4b1  cmp     [rbp+rax+40h+KeyValueInformation], edi
0x14005d4b5  jnz     short loc_14005D4BF
0x14005d4b7  or      cs:word_140025B56, 2
0x14005d4bf  mov     rcx, [rsp+140h+KeyHandle]; Handle
0x14005d4c4  call    cs:__imp_ZwClose
0x14005d4cb  nop     dword ptr [rax+rax+00h]
0x14005d4d0  mov     rcx, [rbp+40h+var_10]
0x14005d4d4  xor     rcx, rsp; StackCookie
0x14005d4d7  call    __security_check_cookie
0x14005d4dc  mov     rdi, [rsp+140h+arg_0]
0x14005d4e4  add     rsp, 140h
0x14005d4eb  pop     rbp
0x14005d4ec  retn
```
