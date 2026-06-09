# SmpLoadPnPSerializeSettings

- ea: `0x1400072e0`
- end: `0x140007418`
- name: `SmpLoadPnPSerializeSettings`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140006680`

## callees

- `0x1400072e0`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtClose` at `0x1400073c2`
- `ntdll!NtClose` at `0x1400073c2`
- `ntdll!NtOpenKey` at `0x140007360`
- `ntdll!NtOpenKey` at `0x140007360`
- `ntdll!NtOpenKey` at `0x1400073f7`
- `ntdll!NtQueryValueKey` at `0x14000738f`
- `ntdll!NtQueryValueKey` at `0x14000738f`
- `ntdll!NtQueryValueKey` at `0x1400073ab`

## string_xrefs

- `0x14000730a`: `\Registry\Machine\System\CurrentControlSet\Control\PnP`

## pseudocode

```c
__int64 SmpLoadPnPSerializeSettings()
{
  NTSTATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-29h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v6[2]; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp+37h] BYREF
  int v10; // [rsp+94h] [rbp+3Bh]
  int v11; // [rsp+9Ch] [rbp+43h]

  v6[0] = 7209068;
  ResultLength = 0;
  v6[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\PnP";
  ObjectAttributes.RootDirectory = 0;
  ValueName.Buffer = L"BootOptions";
  KeyHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v6;
  *(_QWORD *)&ValueName.Length = 1572886;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  v1 = v0;
  if ( v0 < 0 )
  {
    SmpInitProgressByLine = 1547;
    SmpInitReturnStatus = v0;
    SmpInitLastCall = (__int64)NtOpenKey;
  }
  else
  {
    v2 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength);
    v1 = v2;
    if ( v2 >= 0 )
    {
      if ( v10 == 4 )
        SmpSerializeBoot = v11;
    }
    else
    {
      SmpInitProgressByLine = 1565;
      SmpInitReturnStatus = v2;
      SmpInitLastCall = (__int64)NtQueryValueKey;
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v1;
}

```

## disassembly

```asm
0x1400072e0  mov     [rsp-8+arg_0], rbx
0x1400072e5  push    rbp
0x1400072e6  lea     rbp, [rsp-57h]
0x1400072eb  sub     rsp, 0B0h
0x1400072f2  mov     rax, cs:__security_cookie
0x1400072f9  xor     rax, rsp
0x1400072fc  mov     [rbp+57h+var_8], rax
0x140007300  xor     ecx, ecx
0x140007302  mov     [rbp+57h+var_70], 6E006Ch
0x14000730a  lea     rax, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140007311  mov     [rbp+57h+var_80], ecx
0x140007314  mov     [rbp+57h+var_68], rax
0x140007318  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000731c  lea     rax, aBootoptions; "BootOptions"
0x140007323  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x140007327  mov     [rbp+57h+ValueName.Buffer], rax
0x14000732b  xorps   xmm0, xmm0
0x14000732e  lea     rax, [rbp+57h+var_70]
0x140007332  mov     [rbp+57h+KeyHandle], rcx
0x140007336  mov     edx, 20019h; DesiredAccess
0x14000733b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000733f  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140007343  mov     qword ptr [rbp+57h+ValueName.Length], 180016h
0x14000734b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140007353  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14000735b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140007360  call    cs:__imp_NtOpenKey
0x140007366  mov     ebx, eax
0x140007368  test    eax, eax
0x14000736a  js      short loc_1400073E7
0x14000736c  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140007370  lea     rax, [rbp+57h+var_80]
0x140007374  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x140007379  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000737d  mov     r8d, 2; KeyValueInformationClass
0x140007383  mov     [rsp+0B0h+Length], 14h; Length
0x14000738b  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14000738f  call    cs:__imp_NtQueryValueKey
0x140007395  mov     ebx, eax
0x140007397  test    eax, eax
0x140007399  jns     short loc_140007407
0x14000739b  mov     cs:SmpInitProgressByLine, 61Dh
0x1400073a5  mov     cs:SmpInitReturnStatus, eax
0x1400073ab  mov     rax, cs:__imp_NtQueryValueKey
0x1400073b2  mov     cs:SmpInitLastCall, rax
0x1400073b9  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400073bd  test    rcx, rcx
0x1400073c0  jz      short loc_1400073C8
0x1400073c2  call    cs:__imp_NtClose
0x1400073c8  mov     eax, ebx
0x1400073ca  mov     rcx, [rbp+57h+var_8]
0x1400073ce  xor     rcx, rsp; StackCookie
0x1400073d1  call    __security_check_cookie
0x1400073d6  mov     rbx, [rsp+0B0h+arg_0]
0x1400073de  add     rsp, 0B0h
0x1400073e5  pop     rbp
0x1400073e6  retn
0x1400073e7  mov     cs:SmpInitProgressByLine, 60Bh
0x1400073f1  mov     cs:SmpInitReturnStatus, eax
0x1400073f7  mov     rax, cs:__imp_NtOpenKey
0x1400073fe  mov     cs:SmpInitLastCall, rax
0x140007405  jmp     short loc_1400073B9
0x140007407  cmp     [rbp+57h+var_1C], 4
0x14000740b  jnz     short loc_1400073B9
0x14000740d  mov     eax, [rbp+57h+var_14]
0x140007410  mov     cs:SmpSerializeBoot, eax
0x140007416  jmp     short loc_1400073B9
```
