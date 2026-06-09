# SmpTranslateSystemPartitionInformation

- ea: `0x14000b514`
- end: `0x14000b8e8`
- name: `SmpTranslateSystemPartitionInformation`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x14000b514`
- `0x14000d4c0`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000b660`
- `ntdll!RtlInitUnicodeString` at `0x14000b660`
- `ntdll!NtClose` at `0x14000b63e`
- `ntdll!NtClose` at `0x14000b749`
- `ntdll!NtClose` at `0x14000b8a8`
- `ntdll!NtClose` at `0x14000b63e`
- `ntdll!NtClose` at `0x14000b749`
- `ntdll!NtClose` at `0x14000b8a8`
- `ntdll!RtlGetNtSystemRoot` at `0x14000b7db`
- `ntdll!RtlGetNtSystemRoot` at `0x14000b7db`
- `ntdll!NtOpenKey` at `0x14000b5f5`
- `ntdll!NtOpenKey` at `0x14000b83b`
- `ntdll!NtOpenKey` at `0x14000b5f5`
- `ntdll!NtOpenKey` at `0x14000b83b`
- `ntdll!NtSetValueKey` at `0x14000b885`
- `ntdll!NtSetValueKey` at `0x14000b885`
- `ntdll!NtQueryValueKey` at `0x14000b631`
- `ntdll!NtQueryValueKey` at `0x14000b631`
- `ntdll!RtlPrefixUnicodeString` at `0x14000b779`
- `ntdll!RtlPrefixUnicodeString` at `0x14000b779`
- `ntdll!RtlEqualUnicodeString` at `0x14000b6ba`
- `ntdll!RtlEqualUnicodeString` at `0x14000b75f`
- `ntdll!RtlEqualUnicodeString` at `0x14000b6ba`
- `ntdll!RtlEqualUnicodeString` at `0x14000b75f`
- `ntdll!NtQueryDirectoryObject` at `0x14000b69e`
- `ntdll!NtQueryDirectoryObject` at `0x14000b7c2`
- `ntdll!NtQueryDirectoryObject` at `0x14000b69e`
- `ntdll!NtQueryDirectoryObject` at `0x14000b7c2`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14000b71d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14000b71d`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14000b73c`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14000b73c`

## string_xrefs

- `0x14000b892`: `SmpTranslateSystemPartitionInformation`
- `0x14000b8b8`: `SmpTranslateSystemPartitionInformation`
- `0x14000b58c`: `SymbolicLink`
- `0x14000b597`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Setup`
- `0x14000b581`: `SystemPartition`
- `0x14000b56e`: `\Registry\Machine\System\Setup`

## pseudocode

```c
NTSTATUS SmpTranslateSystemPartitionInformation()
{
  NTSTATUS i; // eax
  __int64 v1; // rdx
  NTSTATUS v2; // ebx
  __int64 v3; // r8
  NTSTATUS v4; // ebx
  __int64 NtSystemRoot; // rax
  _BYTE *v6; // r8
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Context; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ResultLength; // [rsp+4Ch] [rbp-B4h] BYREF
  void *SymbolicLinkHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v16[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v20[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING v21; // [rsp+E8h] [rbp-18h] BYREF
  __int16 Buffer; // [rsp+100h] [rbp+0h] BYREF
  _BYTE *j; // [rsp+108h] [rbp+8h]
  UNICODE_STRING String1; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v25[544]; // [rsp+120h] [rbp+20h] BYREF
  _DWORD Data[128]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR SourceString[258]; // [rsp+54Ch] [rbp+44Ch] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  ResultLength = 0;
  Context = 0;
  SymbolicLinkHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v16[1] = L"\\Registry\\Machine\\System\\Setup";
  ValueName.Buffer = L"SystemPartition";
  String2.Buffer = L"SymbolicLink";
  v20[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Setup";
  v21.Buffer = L"BootDir";
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
  DestinationString = 0;
  v16[0] = 4063292;
  LinkTarget = 0;
  *(_QWORD *)&ValueName.Length = 2097182;
  *(_QWORD *)&String2.Length = 1703960;
  v20[0] = 8650882;
  *(_QWORD *)&v21.Length = 1048590;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  i = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( i < 0 )
  {
    v1 = 11773;
LABEL_26:
    v3 = (unsigned int)i;
    return SmpLogFailure("SmpTranslateSystemPartitionInformation", v1, v3);
  }
  v2 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x210u, &ResultLength);
  NtClose(KeyHandle);
  if ( v2 < 0 )
  {
    v3 = (unsigned int)v2;
    v1 = 11791;
    return SmpLogFailure("SmpTranslateSystemPartitionInformation", v1, v3);
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  LinkTarget.Buffer = (PWSTR)Data;
  for ( i = NtQueryDirectoryObject(SmpDosDevicesObjectDirectory, &Buffer, 0x23Au, 1u, 1u, &Context, 0);
        i >= 0;
        i = NtQueryDirectoryObject(SmpDosDevicesObjectDirectory, &Buffer, 0x23Au, 1u, 0, &Context, 0) )
  {
    if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
    {
      if ( Buffer == 4 && *((_WORD *)j + 1) == 58 )
      {
        ObjectAttributes.RootDirectory = SmpDosDevicesObjectDirectory;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&Buffer;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes) >= 0 )
        {
          *(_DWORD *)&LinkTarget.Length = 0x2000000;
          v4 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, 0);
          NtClose(SymbolicLinkHandle);
          if ( v4 >= 0
            && (RtlEqualUnicodeString(&DestinationString, &LinkTarget, 1u)
             || RtlPrefixUnicodeString(&DestinationString, &LinkTarget, 1u)
             && LinkTarget.Buffer[(unsigned __int64)DestinationString.Length >> 1] == 92) )
          {
            goto LABEL_20;
          }
        }
      }
    }
  }
  if ( i != -2147483622 )
  {
    v1 = 11894;
    goto LABEL_26;
  }
  NtSystemRoot = RtlGetNtSystemRoot();
  v6 = v25;
  v7 = 0;
  for ( j = v25; ; v6 = j )
  {
    *(_WORD *)&v6[2 * v7] = *(_WORD *)(NtSystemRoot + 2 * v7);
    if ( ++v7 == 2 )
      break;
  }
LABEL_20:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v20;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  i = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( i < 0 )
  {
    v1 = 11915;
    goto LABEL_26;
  }
  Data[0] = *(_DWORD *)j;
  Data[1] = 92;
  v8 = NtSetValueKey(KeyHandle, &v21, 0, 1u, Data, 8u);
  if ( v8 < 0 )
    SmpLogFailure("SmpTranslateSystemPartitionInformation", 11936, (unsigned int)v8);
  return NtClose(KeyHandle);
}

```

## disassembly

```asm
0x14000b514  mov     [rsp-8+arg_0], rbx
0x14000b519  mov     [rsp-8+arg_8], r14
0x14000b51e  push    rbp
0x14000b51f  lea     rbp, [rsp-660h]
0x14000b527  sub     rsp, 760h
0x14000b52e  mov     rax, cs:__security_cookie
0x14000b535  xor     rax, rsp
0x14000b538  mov     [rbp+660h+var_10], rax
0x14000b53f  xor     eax, eax
0x14000b541  mov     qword ptr [rsp+760h+ObjectAttributes.Length], 30h ; '0'
0x14000b54a  mov     [rsp+760h+KeyHandle], rax
0x14000b54f  lea     r8, [rsp+760h+ObjectAttributes]; ObjectAttributes
0x14000b554  mov     [rsp+760h+var_714], eax
0x14000b558  lea     rcx, [rsp+760h+KeyHandle]; KeyHandle
0x14000b55d  mov     [rsp+760h+Context], eax
0x14000b561  xorps   xmm0, xmm0
0x14000b564  mov     [rsp+760h+SymbolicLinkHandle], rax
0x14000b569  mov     edx, 20019h; DesiredAccess
0x14000b56e  lea     rax, aRegistryMachin_48; "\\Registry\\Machine\\System\\Setup"
0x14000b575  mov     qword ptr [rbp+660h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b57d  mov     [rbp+660h+var_6C0], rax
0x14000b581  lea     rax, aSystempartitio; "SystemPartition"
0x14000b588  mov     [rbp+660h+ValueName.Buffer], rax
0x14000b58c  lea     rax, aSymboliclink; "SymbolicLink"
0x14000b593  mov     [rbp+660h+String2.Buffer], rax
0x14000b597  lea     rax, aRegistryMachin_54; "\\Registry\\Machine\\Software\\Microsof"...
0x14000b59e  mov     [rbp+660h+var_680], rax
0x14000b5a2  lea     rax, aBootdir; "BootDir"
0x14000b5a9  mov     [rbp+660h+var_678.Buffer], rax
0x14000b5ad  lea     rax, [rbp+660h+var_6C8]
0x14000b5b1  mov     [rsp+760h+ObjectAttributes.ObjectName], rax
0x14000b5b6  movups  xmmword ptr [rbp+660h+DestinationString.Length], xmm0
0x14000b5ba  mov     [rbp+660h+var_6C8], 3E003Ch
0x14000b5c2  movups  xmmword ptr [rsp+760h+LinkTarget.Length], xmm0
0x14000b5c7  mov     qword ptr [rbp+660h+ValueName.Length], 20001Eh
0x14000b5cf  mov     qword ptr [rbp+660h+String2.Length], 1A0018h
0x14000b5d7  mov     [rbp+660h+var_688], 840082h
0x14000b5df  mov     qword ptr [rbp+660h+var_678.Length], 10000Eh
0x14000b5e7  mov     [rsp+760h+ObjectAttributes.RootDirectory], 0
0x14000b5f0  movdqu  xmmword ptr [rbp+660h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b5f5  call    cs:__imp_NtOpenKey
0x14000b5fb  test    eax, eax
0x14000b5fd  jns     short loc_14000B609
0x14000b5ff  mov     edx, 2DFDh
0x14000b604  jmp     loc_14000B8B5
0x14000b609  mov     rcx, [rsp+760h+KeyHandle]; KeyHandle
0x14000b60e  lea     rax, [rsp+760h+var_714]
0x14000b613  mov     [rsp+760h+ResultLength], rax; ResultLength
0x14000b618  lea     r9, [rbp+660h+KeyValueInformation]; KeyValueInformation
0x14000b61f  mov     r8d, 2; KeyValueInformationClass
0x14000b625  mov     [rsp+760h+Length], 210h; Length
0x14000b62d  lea     rdx, [rbp+660h+ValueName]; ValueName
0x14000b631  call    cs:__imp_NtQueryValueKey
0x14000b637  mov     rcx, [rsp+760h+KeyHandle]; Handle
0x14000b63c  mov     ebx, eax
0x14000b63e  call    cs:__imp_NtClose
0x14000b644  test    ebx, ebx
0x14000b646  jns     short loc_14000B655
0x14000b648  mov     r8d, ebx
0x14000b64b  mov     edx, 2E0Fh
0x14000b650  jmp     loc_14000B8B8
0x14000b655  lea     rdx, [rbp+660h+SourceString]; SourceString
0x14000b65c  lea     rcx, [rbp+660h+DestinationString]; DestinationString
0x14000b660  call    cs:__imp_RtlInitUnicodeString
0x14000b666  mov     rcx, cs:SmpDosDevicesObjectDirectory; DirectoryHandle
0x14000b66d  lea     rax, [rbp+660h+Data]
0x14000b674  mov     [rsp+760h+LinkTarget.Buffer], rax
0x14000b679  lea     rdx, [rbp+660h+Buffer]; Buffer
0x14000b67d  lea     rax, [rsp+760h+Context]
0x14000b682  mov     [rsp+760h+ReturnLength], 0; ReturnLength
0x14000b68b  mov     [rsp+760h+ResultLength], rax; Context
0x14000b690  mov     r9b, 1; ReturnSingleEntry
0x14000b693  mov     r8d, 23Ah; BufferLength
0x14000b699  mov     byte ptr [rsp+760h+Length], 1; RestartScan
0x14000b69e  call    cs:__imp_NtQueryDirectoryObject
0x14000b6a4  mov     r14d, 5Ch ; '\'
0x14000b6aa  jmp     loc_14000B7C8
0x14000b6af  mov     r8b, 1; CaseInSensitive
0x14000b6b2  lea     rdx, [rbp+660h+String2]; String2
0x14000b6b6  lea     rcx, [rbp+660h+String1]; String1
0x14000b6ba  call    cs:__imp_RtlEqualUnicodeString
0x14000b6c0  test    al, al
0x14000b6c2  jz      loc_14000B796
0x14000b6c8  cmp     [rbp+660h+Buffer], 4
0x14000b6cd  jnz     loc_14000B796
0x14000b6d3  mov     rax, [rbp+660h+var_658]
0x14000b6d7  cmp     word ptr [rax+2], 3Ah ; ':'
0x14000b6dc  jnz     loc_14000B796
0x14000b6e2  mov     rax, cs:SmpDosDevicesObjectDirectory
0x14000b6e9  lea     r8, [rsp+760h+ObjectAttributes]; ObjectAttributes
0x14000b6ee  mov     [rsp+760h+ObjectAttributes.RootDirectory], rax
0x14000b6f3  lea     rcx, [rsp+760h+SymbolicLinkHandle]; SymbolicLinkHandle
0x14000b6f8  lea     rax, [rbp+660h+Buffer]
0x14000b6fc  mov     [rsp+760h+ObjectAttributes.Length], 30h ; '0'
0x14000b704  xorps   xmm0, xmm0
0x14000b707  mov     [rsp+760h+ObjectAttributes.ObjectName], rax
0x14000b70c  mov     edx, 0F0001h; DesiredAccess
0x14000b711  mov     [rbp+660h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b718  movdqu  xmmword ptr [rbp+660h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b71d  call    cs:__imp_NtOpenSymbolicLinkObject
0x14000b723  test    eax, eax
0x14000b725  js      short loc_14000B796
0x14000b727  mov     rcx, [rsp+760h+SymbolicLinkHandle]; SymLinkObjHandle
0x14000b72c  lea     rdx, [rsp+760h+LinkTarget]; LinkTarget
0x14000b731  xor     r8d, r8d; DataWritten
0x14000b734  mov     dword ptr [rsp+760h+LinkTarget.Length], 2000000h
0x14000b73c  call    cs:__imp_NtQuerySymbolicLinkObject
0x14000b742  mov     rcx, [rsp+760h+SymbolicLinkHandle]; Handle
0x14000b747  mov     ebx, eax
0x14000b749  call    cs:__imp_NtClose
0x14000b74f  test    ebx, ebx
0x14000b751  js      short loc_14000B796
0x14000b753  mov     r8b, 1; CaseInSensitive
0x14000b756  lea     rdx, [rsp+760h+LinkTarget]; String2
0x14000b75b  lea     rcx, [rbp+660h+DestinationString]; String1
0x14000b75f  call    cs:__imp_RtlEqualUnicodeString
0x14000b765  test    al, al
0x14000b767  jnz     loc_14000B803
0x14000b76d  mov     r8b, 1; CaseInSensitive
0x14000b770  lea     rdx, [rsp+760h+LinkTarget]; String2
0x14000b775  lea     rcx, [rbp+660h+DestinationString]; String1
0x14000b779  call    cs:__imp_RtlPrefixUnicodeString
0x14000b77f  test    al, al
0x14000b781  jz      short loc_14000B796
0x14000b783  movzx   ecx, [rbp+660h+DestinationString.Length]
0x14000b787  mov     rax, [rsp+760h+LinkTarget.Buffer]
0x14000b78c  shr     rcx, 1
0x14000b78f  cmp     [rax+rcx*2], r14w
0x14000b794  jz      short loc_14000B803
0x14000b796  mov     rcx, cs:SmpDosDevicesObjectDirectory; DirectoryHandle
0x14000b79d  lea     rax, [rsp+760h+Context]
0x14000b7a2  mov     [rsp+760h+ReturnLength], 0; ReturnLength
0x14000b7ab  lea     rdx, [rbp+660h+Buffer]; Buffer
0x14000b7af  mov     [rsp+760h+ResultLength], rax; Context
0x14000b7b4  mov     r9b, 1; ReturnSingleEntry
0x14000b7b7  mov     r8d, 23Ah; BufferLength
0x14000b7bd  mov     byte ptr [rsp+760h+Length], 0; RestartScan
0x14000b7c2  call    cs:__imp_NtQueryDirectoryObject
0x14000b7c8  test    eax, eax
0x14000b7ca  jns     loc_14000B6AF
0x14000b7d0  cmp     eax, 8000001Ah
0x14000b7d5  jnz     loc_14000B8B0
0x14000b7db  call    cs:__imp_RtlGetNtSystemRoot
0x14000b7e1  lea     r8, [rbp+660h+var_640]
0x14000b7e5  xor     edx, edx
0x14000b7e7  mov     [rbp+660h+var_658], r8
0x14000b7eb  movzx   ecx, word ptr [rax+rdx*2]
0x14000b7ef  mov     [r8+rdx*2], cx
0x14000b7f4  inc     rdx
0x14000b7f7  cmp     rdx, 2
0x14000b7fb  jz      short loc_14000B803
0x14000b7fd  mov     r8, [rbp+660h+var_658]
0x14000b801  jmp     short loc_14000B7EB
0x14000b803  lea     rax, [rbp+660h+var_688]
0x14000b807  mov     [rsp+760h+ObjectAttributes.Length], 30h ; '0'
0x14000b80f  xorps   xmm0, xmm0
0x14000b812  mov     [rsp+760h+ObjectAttributes.ObjectName], rax
0x14000b817  lea     r8, [rsp+760h+ObjectAttributes]; ObjectAttributes
0x14000b81c  mov     [rsp+760h+ObjectAttributes.RootDirectory], 0
0x14000b825  mov     edx, 0F003Fh; DesiredAccess
0x14000b82a  mov     [rbp+660h+ObjectAttributes.Attributes], 40h ; '@'
0x14000b831  lea     rcx, [rsp+760h+KeyHandle]; KeyHandle
0x14000b836  movdqu  xmmword ptr [rbp+660h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b83b  call    cs:__imp_NtOpenKey
0x14000b841  test    eax, eax
0x14000b843  jns     short loc_14000B84C
0x14000b845  mov     edx, 2E8Bh
0x14000b84a  jmp     short loc_14000B8B5
0x14000b84c  mov     rax, [rbp+660h+var_658]
0x14000b850  lea     rdx, [rbp+660h+var_678]; ValueName
0x14000b854  mov     dword ptr [rsp+760h+ResultLength], 8; DataSize
0x14000b85c  mov     r9d, 1; Type
0x14000b862  xor     r8d, r8d; TitleIndex
0x14000b865  mov     ecx, [rax]
0x14000b867  lea     rax, [rbp+660h+Data]
0x14000b86e  mov     [rbp+660h+Data], ecx
0x14000b874  mov     rcx, [rsp+760h+KeyHandle]; KeyHandle
0x14000b879  mov     qword ptr [rsp+760h+Length], rax; Data
0x14000b87e  mov     [rbp+660h+var_41C], r14d
0x14000b885  call    cs:__imp_NtSetValueKey
0x14000b88b  test    eax, eax
0x14000b88d  jns     short loc_14000B8A3
0x14000b88f  mov     r8d, eax
0x14000b892  lea     rcx, aSmptranslatesy; "SmpTranslateSystemPartitionInformation"
0x14000b899  mov     edx, 2EA0h
0x14000b89e  call    SmpLogFailure
0x14000b8a3  mov     rcx, [rsp+760h+KeyHandle]; Handle
0x14000b8a8  call    cs:__imp_NtClose
0x14000b8ae  jmp     short loc_14000B8C4
0x14000b8b0  mov     edx, 2E76h
0x14000b8b5  mov     r8d, eax
0x14000b8b8  lea     rcx, aSmptranslatesy; "SmpTranslateSystemPartitionInformation"
0x14000b8bf  call    SmpLogFailure
0x14000b8c4  mov     rcx, [rbp+660h+var_10]
0x14000b8cb  xor     rcx, rsp; StackCookie
0x14000b8ce  call    __security_check_cookie
0x14000b8d3  lea     r11, [rsp+760h+var_s0]
0x14000b8db  mov     rbx, [r11+10h]
0x14000b8df  mov     r14, [r11+18h]
0x14000b8e3  mov     rsp, r11
0x14000b8e6  pop     rbp
0x14000b8e7  retn
```
