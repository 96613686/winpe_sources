# SampDeleteKeyForPostBootPromote

- ea: `0x180072df0`
- end: `0x180072fea`
- name: `SampDeleteKeyForPostBootPromote`
- size: `506`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800715d0`
- `0x180071780`
- `0x180072220`
- `0x1800975e0`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180072df0`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180072e96`
- `ntdll!NtDeleteValueKey` at `0x180072ee2`
- `ntdll!NtDeleteValueKey` at `0x180072e96`
- `ntdll!NtDeleteValueKey` at `0x180072ee2`
- `ntdll!NtOpenKey` at `0x180072e66`
- `ntdll!NtOpenKey` at `0x180072e66`
- `ntdll!NtFlushKey` at `0x180072f32`
- `ntdll!NtFlushKey` at `0x180072f32`
- `ntdll!NtClose` at `0x180072f67`
- `ntdll!NtClose` at `0x180072f67`
- `ntdll!RtlInitUnicodeString` at `0x180072e2d`
- `ntdll!RtlInitUnicodeString` at `0x180072e88`
- `ntdll!RtlInitUnicodeString` at `0x180072ed4`
- `ntdll!RtlInitUnicodeString` at `0x180072e2d`
- `ntdll!RtlInitUnicodeString` at `0x180072e88`
- `ntdll!RtlInitUnicodeString` at `0x180072ed4`

## string_xrefs

- `0x180072e0e`: `\Registry\Machine\System\CurrentControlSet\Services\SAMSS`

## pseudocode

```c
__int64 SampDeleteKeyForPostBootPromote()
{
  NTSTATUS v0; // eax
  int v1; // ebx
  NTSTATUS v2; // eax
  unsigned int v3; // r14d
  NTSTATUS v4; // eax
  PUNICODE_STRING v5; // rcx
  __int64 v6; // rdx
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+7h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+67h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\SAMSS");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenKey(&KeyHandle, 0x10000000u, &ObjectAttributes);
  v1 = v0;
  if ( v0 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v6 = 115;
      goto LABEL_24;
    }
  }
  else
  {
    RtlInitUnicodeString(&ValueName, L"PostPromoteBoot");
    v2 = NtDeleteValueKey(KeyHandle, &ValueName);
    v1 = v2;
    if ( v2 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 111, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v2);
    RtlInitUnicodeString(&ValueName, L"AdminInfo");
    v3 = NtDeleteValueKey(KeyHandle, &ValueName);
    if ( (int)(v3 + 0x80000000) >= 0 && v3 != -1073741772 )
    {
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 112, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, v3);
      if ( v1 >= 0 )
        v1 = v3;
    }
    v4 = NtFlushKey(KeyHandle);
    if ( v4 < 0 && *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 113, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v4);
    v0 = NtClose(KeyHandle);
    if ( v0 >= 0 )
      goto LABEL_25;
    v5 = WPP_GLOBAL_Control;
    if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      v6 = 114;
LABEL_24:
      WPP_SF_d(v5[3].Buffer, v6, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v0);
LABEL_25:
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( (*(_DWORD *)(&v5[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v5[3].Buffer, 116, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids, (unsigned int)v1, v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180072df0  push    rbp
0x180072df2  push    rbx
0x180072df3  push    r14
0x180072df5  push    r15
0x180072df7  lea     rbp, [rsp-3Fh]
0x180072dfc  sub     rsp, 88h
0x180072e03  xorps   xmm0, xmm0
0x180072e06  mov     [rbp+57h+KeyHandle], 0
0x180072e0e  lea     rdx, aRegistryMachin_7; "\\Registry\\Machine\\System\\CurrentCon"...
0x180072e15  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180072e19  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180072e1d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180072e21  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072e25  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180072e29  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x180072e2d  call    cs:__imp_RtlInitUnicodeString
0x180072e33  lea     rax, [rbp+57h+DestinationString]
0x180072e37  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180072e3e  xorps   xmm0, xmm0
0x180072e41  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180072e45  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180072e49  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180072e51  mov     edx, 10000000h; DesiredAccess
0x180072e56  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180072e5d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180072e61  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180072e66  call    cs:__imp_NtOpenKey
0x180072e6c  lea     r15, WPP_c357d61c12eb3c5dab907a04143038bd_Traceguids
0x180072e73  mov     ebx, eax
0x180072e75  test    eax, eax
0x180072e77  js      loc_180072F8B
0x180072e7d  lea     rdx, aPostpromoteboo; "PostPromoteBoot"
0x180072e84  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180072e88  call    cs:__imp_RtlInitUnicodeString
0x180072e8e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180072e92  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180072e96  call    cs:__imp_NtDeleteValueKey
0x180072e9c  mov     ebx, eax
0x180072e9e  test    eax, eax
0x180072ea0  jns     short loc_180072EC9
0x180072ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ea9  test    byte ptr [rcx+44h], 80h
0x180072ead  jz      short loc_180072EC9
0x180072eaf  cmp     byte ptr [rcx+41h], 2
0x180072eb3  jb      short loc_180072EC9
0x180072eb5  mov     rcx, [rcx+38h]
0x180072eb9  mov     edx, 6Fh ; 'o'
0x180072ebe  mov     r9d, eax
0x180072ec1  mov     r8, r15
0x180072ec4  call    WPP_SF_d
0x180072ec9  lea     rdx, aAdmininfo; "AdminInfo"
0x180072ed0  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x180072ed4  call    cs:__imp_RtlInitUnicodeString
0x180072eda  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180072ede  lea     rdx, [rbp+57h+ValueName]; ValueName
0x180072ee2  call    cs:__imp_NtDeleteValueKey
0x180072ee8  mov     r14d, eax
0x180072eeb  mov     eax, 80000000h
0x180072ef0  lea     ecx, [r14+rax]
0x180072ef4  test    eax, ecx
0x180072ef6  jnz     short loc_180072F2E
0x180072ef8  cmp     r14d, 0C0000034h
0x180072eff  jz      short loc_180072F2E
0x180072f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f08  test    byte ptr [rcx+44h], 80h
0x180072f0c  jz      short loc_180072F28
0x180072f0e  cmp     byte ptr [rcx+41h], 2
0x180072f12  jb      short loc_180072F28
0x180072f14  mov     rcx, [rcx+38h]
0x180072f18  mov     edx, 70h ; 'p'
0x180072f1d  mov     r9d, r14d
0x180072f20  mov     r8, r15
0x180072f23  call    WPP_SF_d
0x180072f28  test    ebx, ebx
0x180072f2a  cmovns  ebx, r14d
0x180072f2e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180072f32  call    cs:__imp_NtFlushKey
0x180072f38  test    eax, eax
0x180072f3a  jns     short loc_180072F63
0x180072f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f43  test    byte ptr [rcx+44h], 80h
0x180072f47  jz      short loc_180072F63
0x180072f49  cmp     byte ptr [rcx+41h], 2
0x180072f4d  jb      short loc_180072F63
0x180072f4f  mov     rcx, [rcx+38h]
0x180072f53  mov     edx, 71h ; 'q'
0x180072f58  mov     r9d, eax
0x180072f5b  mov     r8, r15
0x180072f5e  call    WPP_SF_d
0x180072f63  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180072f67  call    cs:__imp_NtClose
0x180072f6d  test    eax, eax
0x180072f6f  jns     short loc_180072FB2
0x180072f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f78  test    byte ptr [rcx+44h], 80h
0x180072f7c  jz      short loc_180072FB9
0x180072f7e  cmp     byte ptr [rcx+41h], 2
0x180072f82  jb      short loc_180072FB9
0x180072f84  mov     edx, 72h ; 'r'
0x180072f89  jmp     short loc_180072FA3
0x180072f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180072f92  test    byte ptr [rcx+44h], 80h
0x180072f96  jz      short loc_180072FB9
0x180072f98  cmp     byte ptr [rcx+41h], 2
0x180072f9c  jb      short loc_180072FB9
0x180072f9e  mov     edx, 73h ; 's'
0x180072fa3  mov     rcx, [rcx+38h]
0x180072fa7  mov     r9d, eax
0x180072faa  mov     r8, r15
0x180072fad  call    WPP_SF_d
0x180072fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180072fb9  test    dword ptr [rcx+44h], 20000h
0x180072fc0  jz      short loc_180072FDA
0x180072fc2  mov     rcx, [rcx+38h]
0x180072fc6  mov     edx, 74h ; 't'
0x180072fcb  mov     r9d, ebx
0x180072fce  mov     [rsp+0A0h+var_80], ebx
0x180072fd2  mov     r8, r15
0x180072fd5  call    WPP_SF_Dd
0x180072fda  mov     eax, ebx
0x180072fdc  add     rsp, 88h
0x180072fe3  pop     r15
0x180072fe5  pop     r14
0x180072fe7  pop     rbx
0x180072fe8  pop     rbp
0x180072fe9  retn
```
