# SampPerformWAUUpgradeIfNecessaryHelper(ulong,HKEY__ * *,ulong *)

- ea: `0x180086dc8`
- end: `0x180086fdd`
- name: `?SampPerformWAUUpgradeIfNecessaryHelper@@YAJKPEAPEAUHKEY__@@PEAK@Z`
- size: `533`
- prototype: `int(unsigned int, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007c768`

## callees

- `0x180027e24`
- `0x180086dc8`

## import_xrefs

- `ntdll!RtlpNtSetValueKey` at `0x180086ee3`
- `ntdll!RtlpNtSetValueKey` at `0x180086ee3`
- `ntdll!RtlpNtCreateKey` at `0x180086f72`
- `ntdll!RtlpNtCreateKey` at `0x180086f72`
- `ntdll!NtClose` at `0x180086e83`
- `ntdll!NtClose` at `0x180086e83`
- `ntdll!RtlpNtQueryValueKey` at `0x180086f23`
- `ntdll!RtlpNtQueryValueKey` at `0x180086f23`
- `ntdll!RtlpNtOpenKey` at `0x180086faf`
- `ntdll!RtlpNtOpenKey` at `0x180086faf`
- `ntdll!RtlInitUnicodeString` at `0x180086e0e`
- `ntdll!RtlInitUnicodeString` at `0x180086e0e`

## string_xrefs

- `0x180086ded`: `\Registry\Machine\SAM\SAM\LastSkuUpgrade`

## pseudocode

```c
__int64 __fastcall SampPerformWAUUpgradeIfNecessaryHelper(int a1, HKEY *a2, unsigned int *a3)
{
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  PUNICODE_STRING v9; // rcx
  NTSTATUS v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  void *v14; // rcx
  void *v15; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG DataLength; // [rsp+90h] [rbp+20h] BYREF
  ULONG Disposition; // [rsp+A8h] [rbp+38h] BYREF

  Disposition = 0;
  DataLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\SAM\\SAM\\LastSkuUpgrade");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( !a1 )
  {
    v10 = RtlpNtOpenKey(a2, 0x2001Fu, &ObjectAttributes, 0);
    if ( v10 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v10;
      v11 = 17;
      goto LABEL_11;
    }
LABEL_9:
    v9 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
      return (unsigned int)v10;
    v11 = 22;
LABEL_11:
    v12 = (unsigned int)v10;
    goto LABEL_12;
  }
  v6 = a1 - 1;
  if ( !v6 )
  {
    v10 = RtlpNtCreateKey(a2, 0x2001Fu, &ObjectAttributes, 0, 0, &Disposition);
    if ( v10 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v10;
      v11 = 18;
      goto LABEL_11;
    }
    goto LABEL_9;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v15 = *a2;
    DataLength = 4;
    v10 = RtlpNtQueryValueKey(v15, 0, a3, &DataLength, 0);
    if ( v10 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v10;
      v11 = 19;
      goto LABEL_11;
    }
    goto LABEL_9;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v14 = *a2;
    DataLength = 4;
    v10 = RtlpNtSetValueKey(v14, 4u, a3, 4u);
    if ( v10 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) == 0 )
        return (unsigned int)v10;
      v11 = 20;
      goto LABEL_11;
    }
    goto LABEL_9;
  }
  if ( v8 == 1 )
  {
    v10 = NtClose(*a2);
    *a2 = 0;
    goto LABEL_9;
  }
  v9 = WPP_GLOBAL_Control;
  v10 = -1073741811;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v11 = 21;
    v12 = 3221225485LL;
LABEL_12:
    WPP_SF_Dd(v9[3].Buffer, v11, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v12, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180086dc8  mov     [rsp-18h+arg_8], rbx
0x180086dcd  push    rbp
0x180086dce  push    rsi
0x180086dcf  push    rdi
0x180086dd0  mov     rbp, rsp
0x180086dd3  sub     rsp, 70h
0x180086dd7  xorps   xmm1, xmm1
0x180086dda  mov     [rbp+arg_18], 0
0x180086de1  mov     rdi, rdx
0x180086de4  mov     [rbp+DataLength], 0
0x180086deb  mov     ebx, ecx
0x180086ded  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\SAM\\SAM\\LastSkuU"...
0x180086df4  xorps   xmm0, xmm0
0x180086df7  lea     rcx, [rbp+DestinationString]; DestinationString
0x180086dfb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180086dff  mov     rsi, r8
0x180086e02  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x180086e06  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x180086e0a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x180086e0e  call    cs:__imp_RtlInitUnicodeString
0x180086e14  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180086e1b  lea     rax, [rbp+DestinationString]
0x180086e1f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180086e23  xorps   xmm0, xmm0
0x180086e26  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180086e2e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180086e35  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180086e3a  test    ebx, ebx
0x180086e3c  jz      loc_180086FA0
0x180086e42  sub     ebx, 1
0x180086e45  jz      loc_180086F51
0x180086e4b  sub     ebx, 1
0x180086e4e  jz      loc_180086F06
0x180086e54  sub     ebx, 1
0x180086e57  jz      short loc_180086ED0
0x180086e59  cmp     ebx, 1
0x180086e5c  jz      short loc_180086E80
0x180086e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e65  mov     ebx, 0C000000Dh
0x180086e6a  test    dword ptr [rcx+44h], 20000h
0x180086e71  jz      short loc_180086EBE
0x180086e73  mov     edx, 15h
0x180086e78  mov     r9d, 0C000000Dh
0x180086e7e  jmp     short loc_180086EAA
0x180086e80  mov     rcx, [rdi]; Handle
0x180086e83  call    cs:__imp_NtClose
0x180086e89  mov     ebx, eax
0x180086e8b  mov     qword ptr [rdi], 0
0x180086e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180086e99  test    dword ptr [rcx+44h], 20000h
0x180086ea0  jz      short loc_180086EBE
0x180086ea2  mov     edx, 16h
0x180086ea7  mov     r9d, ebx
0x180086eaa  mov     rcx, [rcx+38h]
0x180086eae  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x180086eb5  mov     [rsp+70h+Unused], ebx
0x180086eb9  call    WPP_SF_Dd
0x180086ebe  mov     eax, ebx
0x180086ec0  mov     rbx, [rsp+70h+arg_8]
0x180086ec8  add     rsp, 70h
0x180086ecc  pop     rdi
0x180086ecd  pop     rsi
0x180086ece  pop     rbp
0x180086ecf  retn
0x180086ed0  mov     rcx, [rdi]; KeyHandle
0x180086ed3  mov     eax, 4
0x180086ed8  mov     r9d, eax; DataLength
0x180086edb  mov     [rbp+DataLength], eax
0x180086ede  mov     edx, eax; Type
0x180086ee0  mov     r8, rsi; Data
0x180086ee3  call    cs:__imp_RtlpNtSetValueKey
0x180086ee9  mov     ebx, eax
0x180086eeb  test    eax, eax
0x180086eed  jns     short loc_180086E92
0x180086eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180086ef6  test    dword ptr [rcx+44h], 20000h
0x180086efd  jz      short loc_180086EBE
0x180086eff  mov     edx, 14h
0x180086f04  jmp     short loc_180086EA7
0x180086f06  mov     rcx, [rdi]; KeyHandle
0x180086f09  lea     r9, [rbp+DataLength]; DataLength
0x180086f0d  mov     eax, 4
0x180086f12  mov     qword ptr [rsp+70h+Unused], 0; Unused
0x180086f1b  mov     r8, rsi; Data
0x180086f1e  mov     [rbp+DataLength], eax
0x180086f21  xor     edx, edx; Type
0x180086f23  call    cs:__imp_RtlpNtQueryValueKey
0x180086f29  mov     ebx, eax
0x180086f2b  test    eax, eax
0x180086f2d  jns     loc_180086E92
0x180086f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f3a  test    dword ptr [rcx+44h], 20000h
0x180086f41  jz      loc_180086EBE
0x180086f47  mov     edx, 13h
0x180086f4c  jmp     loc_180086EA7
0x180086f51  lea     rax, [rbp+arg_18]
0x180086f55  xor     r9d, r9d; TitleIndex
0x180086f58  mov     [rsp+70h+Disposition], rax; Disposition
0x180086f5d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180086f61  mov     edx, 2001Fh; DesiredAccess
0x180086f66  mov     qword ptr [rsp+70h+Unused], 0; Class
0x180086f6f  mov     rcx, rdi; KeyHandle
0x180086f72  call    cs:__imp_RtlpNtCreateKey
0x180086f78  mov     ebx, eax
0x180086f7a  test    eax, eax
0x180086f7c  jns     loc_180086E92
0x180086f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180086f89  test    dword ptr [rcx+44h], 20000h
0x180086f90  jz      loc_180086EBE
0x180086f96  mov     edx, 12h
0x180086f9b  jmp     loc_180086EA7
0x180086fa0  xor     r9d, r9d; Unused
0x180086fa3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180086fa7  mov     edx, 2001Fh; DesiredAccess
0x180086fac  mov     rcx, rdi; KeyHandle
0x180086faf  call    cs:__imp_RtlpNtOpenKey
0x180086fb5  mov     ebx, eax
0x180086fb7  test    eax, eax
0x180086fb9  jns     loc_180086E92
0x180086fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180086fc6  test    dword ptr [rcx+44h], 20000h
0x180086fcd  jz      loc_180086EBE
0x180086fd3  mov     edx, 11h
0x180086fd8  jmp     loc_180086EA7
```
