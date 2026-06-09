# SampChangeConfigurationKeyToValue(_UNICODE_STRING *)

- ea: `0x180079464`
- end: `0x180079680`
- name: `?SampChangeConfigurationKeyToValue@@YAJPEAU_UNICODE_STRING@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(PUNICODE_STRING ValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800799a8`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x180079464`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x1800795f7`
- `ntdll!NtDeleteKey` at `0x1800795f7`
- `ntdll!NtSetValueKey` at `0x1800795e6`
- `ntdll!NtSetValueKey` at `0x1800795e6`
- `ntdll!NtOpenKey` at `0x180079555`
- `ntdll!NtOpenKey` at `0x1800795b2`
- `ntdll!NtOpenKey` at `0x180079555`
- `ntdll!NtOpenKey` at `0x1800795b2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180079508`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180079508`
- `ntdll!RtlAppendUnicodeToString` at `0x1800794d4`
- `ntdll!RtlAppendUnicodeToString` at `0x1800794f0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800794d4`
- `ntdll!RtlAppendUnicodeToString` at `0x1800794f0`
- `ntdll!NtClose` at `0x180079602`
- `ntdll!NtClose` at `0x18007960d`
- `ntdll!NtClose` at `0x180079602`
- `ntdll!NtClose` at `0x18007960d`
- `ntdll!RtlInitUnicodeString` at `0x18007956f`
- `ntdll!RtlInitUnicodeString` at `0x18007956f`

## string_xrefs

- `0x1800794be`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`
- `0x180079563`: `\Registry\Machine\System\CurrentControlSet\Control\Lsa`

## pseudocode

```c
__int64 __fastcall SampChangeConfigurationKeyToValue(PUNICODE_STRING ValueName)
{
  NTSTATUS appended; // ebx
  PUNICODE_STRING v3; // rcx
  __int64 v4; // rdx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-D0h] BYREF
  int Data; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  char v11; // [rsp+90h] [rbp-70h] BYREF

  Handle = 0;
  *(_QWORD *)&Destination.Length = 0x2000000;
  KeyHandle = 0;
  Destination.Buffer = (PWSTR)&v11;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  appended = RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
  if ( appended < 0
    || (appended = RtlAppendUnicodeToString(&Destination, L"\\"), appended < 0)
    || (appended = RtlAppendUnicodeStringToString(&Destination, ValueName), appended < 0) )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v4 = 15;
      goto LABEL_15;
    }
  }
  else
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &Destination;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x10000u, &ObjectAttributes) < 0 )
    {
      appended = 0;
    }
    else
    {
      RtlInitUnicodeString(&Destination, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Lsa");
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &Destination;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      appended = NtOpenKey(&Handle, 0x2001Fu, &ObjectAttributes);
      if ( appended >= 0 )
      {
        Data = 1;
        appended = NtSetValueKey(Handle, ValueName, 0, 4u, &Data, 4u);
        if ( appended >= 0 )
          NtDeleteKey(KeyHandle);
        NtClose(Handle);
      }
      NtClose(KeyHandle);
    }
    v3 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v4 = 16;
LABEL_15:
      WPP_SF_Dd(v3[3].Buffer, v4, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, (unsigned int)appended, appended);
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180079464  mov     [rsp-8+arg_8], rbx
0x180079469  mov     [rsp-8+arg_10], rdi
0x18007946e  push    rbp
0x18007946f  lea     rbp, [rsp-1A0h]
0x180079477  sub     rsp, 2A0h
0x18007947e  mov     rax, cs:__security_cookie
0x180079485  xor     rax, rsp
0x180079488  mov     [rbp+1A0h+var_10], rax
0x18007948f  xorps   xmm0, xmm0
0x180079492  mov     [rsp+2A0h+Handle], 0
0x18007949b  mov     rdi, rcx
0x18007949e  mov     qword ptr [rsp+2A0h+Destination.Length], 2000000h
0x1800794a7  lea     rax, [rbp+1A0h+var_210]
0x1800794ab  mov     [rsp+2A0h+KeyHandle], 0
0x1800794b4  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800794b9  mov     [rsp+2A0h+Destination.Buffer], rax
0x1800794be  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800794c5  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.Length], xmm0
0x1800794ca  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.ObjectName], xmm0
0x1800794cf  movups  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800794d4  call    cs:__imp_RtlAppendUnicodeToString
0x1800794da  mov     ebx, eax
0x1800794dc  test    eax, eax
0x1800794de  js      loc_18007962E
0x1800794e4  lea     rdx, asc_1800CA5C4; "\\"
0x1800794eb  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800794f0  call    cs:__imp_RtlAppendUnicodeToString
0x1800794f6  mov     ebx, eax
0x1800794f8  test    eax, eax
0x1800794fa  js      loc_18007962E
0x180079500  mov     rdx, rdi; Source
0x180079503  lea     rcx, [rsp+2A0h+Destination]; Destination
0x180079508  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007950e  mov     ebx, eax
0x180079510  test    eax, eax
0x180079512  js      loc_18007962E
0x180079518  lea     rax, [rsp+2A0h+Destination]
0x18007951d  mov     qword ptr [rsp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x180079526  xorps   xmm0, xmm0
0x180079529  mov     [rsp+2A0h+ObjectAttributes.ObjectName], rax
0x18007952e  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x180079533  mov     qword ptr [rsp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18007953c  mov     edx, 10000h; DesiredAccess
0x180079541  mov     [rsp+2A0h+ObjectAttributes.RootDirectory], 0
0x18007954a  lea     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x18007954f  movdqu  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180079555  call    cs:__imp_NtOpenKey
0x18007955b  test    eax, eax
0x18007955d  js      loc_180079615
0x180079563  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\CurrentCon"...
0x18007956a  lea     rcx, [rsp+2A0h+Destination]; DestinationString
0x18007956f  call    cs:__imp_RtlInitUnicodeString
0x180079575  lea     rax, [rsp+2A0h+Destination]
0x18007957a  mov     qword ptr [rsp+2A0h+ObjectAttributes.Length], 30h ; '0'
0x180079583  xorps   xmm0, xmm0
0x180079586  mov     [rsp+2A0h+ObjectAttributes.ObjectName], rax
0x18007958b  lea     r8, [rsp+2A0h+ObjectAttributes]; ObjectAttributes
0x180079590  mov     qword ptr [rsp+2A0h+ObjectAttributes.Attributes], 40h ; '@'
0x180079599  mov     edx, 2001Fh; DesiredAccess
0x18007959e  mov     [rsp+2A0h+ObjectAttributes.RootDirectory], 0
0x1800795a7  lea     rcx, [rsp+2A0h+Handle]; KeyHandle
0x1800795ac  movdqu  xmmword ptr [rsp+2A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800795b2  call    cs:__imp_NtOpenKey
0x1800795b8  mov     ebx, eax
0x1800795ba  test    eax, eax
0x1800795bc  js      short loc_180079608
0x1800795be  mov     rcx, [rsp+2A0h+Handle]; KeyHandle
0x1800795c3  lea     rax, [rsp+2A0h+var_260]
0x1800795c8  mov     r9d, 4; Type
0x1800795ce  mov     [rsp+2A0h+var_260], 1
0x1800795d6  mov     [rsp+2A0h+DataSize], r9d; DataSize
0x1800795db  xor     r8d, r8d; TitleIndex
0x1800795de  mov     rdx, rdi; ValueName
0x1800795e1  mov     [rsp+2A0h+Data], rax; Data
0x1800795e6  call    cs:__imp_NtSetValueKey
0x1800795ec  mov     ebx, eax
0x1800795ee  test    eax, eax
0x1800795f0  js      short loc_1800795FD
0x1800795f2  mov     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x1800795f7  call    cs:__imp_NtDeleteKey
0x1800795fd  mov     rcx, [rsp+2A0h+Handle]; Handle
0x180079602  call    cs:__imp_NtClose
0x180079608  mov     rcx, [rsp+2A0h+KeyHandle]; Handle
0x18007960d  call    cs:__imp_NtClose
0x180079613  jmp     short loc_180079617
0x180079615  xor     ebx, ebx
0x180079617  mov     rcx, cs:WPP_GLOBAL_Control
0x18007961e  test    dword ptr [rcx+44h], 20000h
0x180079625  jz      short loc_18007965A
0x180079627  mov     edx, 10h
0x18007962c  jmp     short loc_180079643
0x18007962e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079635  test    dword ptr [rcx+44h], 20000h
0x18007963c  jz      short loc_18007965A
0x18007963e  mov     edx, 0Fh
0x180079643  mov     rcx, [rcx+38h]
0x180079647  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18007964e  mov     r9d, ebx
0x180079651  mov     dword ptr [rsp+2A0h+Data], ebx
0x180079655  call    WPP_SF_Dd
0x18007965a  mov     eax, ebx
0x18007965c  mov     rcx, [rbp+1A0h+var_10]
0x180079663  xor     rcx, rsp; StackCookie
0x180079666  call    __security_check_cookie
0x18007966b  lea     r11, [rsp+2A0h+var_s0]
0x180079673  mov     rbx, [r11+18h]
0x180079677  mov     rdi, [r11+20h]
0x18007967b  mov     rsp, r11
0x18007967e  pop     rbp
0x18007967f  retn
```
