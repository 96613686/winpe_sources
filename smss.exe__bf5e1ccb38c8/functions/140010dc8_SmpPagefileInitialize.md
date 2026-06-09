# SmpPagefileInitialize

- ea: `0x140010dc8`
- end: `0x140011065`
- name: `SmpPagefileInitialize`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f120`

## callees

- `0x14000d4c0`
- `0x140010dc8`
- `0x140011f64`
- `0x140011fe8`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140010e83`
- `ntdll!NtQuerySystemInformation` at `0x140010e83`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140010ea8`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140010ea8`
- `ntdll!RtlGetNtSystemRoot` at `0x140010e9f`
- `ntdll!RtlGetNtSystemRoot` at `0x140010e9f`
- `ntdll!NtOpenKey` at `0x140010ef3`
- `ntdll!NtOpenKey` at `0x140010f53`
- `ntdll!NtOpenKey` at `0x140010ef3`
- `ntdll!NtOpenKey` at `0x140010f53`
- `ntdll!RtlGetVersion` at `0x14001102d`
- `ntdll!RtlGetVersion` at `0x14001102d`

## string_xrefs

- `0x140010dfa`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Memory Management`
- `0x140010e13`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
__int64 SmpPagefileInitialize()
{
  WCHAR *NtSystemRoot; // rax
  WCHAR v1; // ax
  NTSTATUS v2; // ebx
  __int64 v3; // rdx
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ecx
  bool v8; // bl
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  const wchar_t *v12; // [rsp+30h] [rbp-D0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v14[2]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v15[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 SystemInformation; // [rsp+88h] [rbp-78h] BYREF
  __int64 v17; // [rsp+98h] [rbp-68h]
  _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  char v19; // [rsp+1BAh] [rbp+BAh]

  v14[0] = 11141288;
  v15[0] = 8388734;
  v14[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Memory Management";
  v15[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl";
  memset(&ObjectAttributes.ObjectName, 0, 32);
  *(_OWORD *)&ObjectAttributes.Length = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  v17 = 0;
  qword_140030C48 = (__int64)&SmpPagingFileDescriptorList;
  SmpPagingFileDescriptorList = &SmpPagingFileDescriptorList;
  qword_140030C28 = (__int64)&SmpVolumeDescriptorList;
  SmpVolumeDescriptorList = (__int64)&SmpVolumeDescriptorList;
  SystemInformation = 0;
  NtQuerySystemInformation(SystemPrefetcherInformation|0x80, &SystemInformation, 0x18u, 0);
  SmpMemorySize = SystemInformation;
  SmpHighestPhysicalAddress = v17;
  NtSystemRoot = (WCHAR *)RtlGetNtSystemRoot();
  v1 = RtlUpcaseUnicodeChar(*NtSystemRoot);
  ObjectAttributes.RootDirectory = 0;
  SmpOsVolumeLetter = v1;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v14;
  ObjectAttributes.Length = 48;
  v2 = NtOpenKey(&SmpMmKey, 0x2001Fu, &ObjectAttributes);
  if ( v2 < 0 )
  {
    v3 = 583;
LABEL_3:
    SmpLogFailure("SmpPagefileInitialize", v3, (unsigned int)v2);
    return (unsigned int)v2;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = NtOpenKey(&SmpCrashDumpKey, 0x2001Fu, &ObjectAttributes);
  if ( v2 < 0 )
  {
    v3 = 600;
    goto LABEL_3;
  }
  v11 = 2228256;
  v12 = L"CrashDumpEnabled";
  v10 = 0;
  v6 = SmpQueryDwordFromRegistry(v5, &v11, 4, &v10);
  v7 = v10;
  if ( v6 < 0 )
    v7 = 4;
  SmpDumpType = v7;
  SmpUseDedicatedDumpFile = SmpQueryDedicatedDumpSetting();
  v11 = 1572886;
  v12 = L"FilterPages";
  v10 = 0;
  v8 = 0;
  if ( (int)SmpQueryDwordFromRegistry(v9, &v11, 0, &v10) >= 0 )
    v8 = v10 != 0;
  SmpUseFilterPagesDumpFile = v8;
  SmpForceCopyDumpFile = (SmpSystemWriteConstraintInfo & 4) != 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( RtlGetVersion(&VersionInformation) >= 0 && v19 == 1 )
    SmpClientSku = 1;
  return 0;
}

```

## disassembly

```asm
0x140010dc8  push    rbp
0x140010dca  push    rbx
0x140010dcb  push    rsi
0x140010dcc  push    r13
0x140010dce  lea     rbp, [rsp-0D8h]
0x140010dd6  sub     rsp, 1D8h
0x140010ddd  mov     rax, cs:__security_cookie
0x140010de4  xor     rax, rsp
0x140010de7  mov     [rbp+0F0h+var_30], rax
0x140010dee  xorps   xmm0, xmm0
0x140010df1  mov     [rsp+1F0h+var_188], 0AA00A8h
0x140010dfa  lea     rax, aRegistryMachin_55; "\\Registry\\Machine\\System\\CurrentCon"...
0x140010e01  mov     [rsp+1F0h+var_178], 80007Eh
0x140010e0a  mov     [rsp+1F0h+var_180], rax
0x140010e0f  lea     rcx, [rbp+0F0h+VersionInformation]; void *
0x140010e13  lea     rax, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140010e1a  xor     edx, edx; Val
0x140010e1c  mov     [rbp+0F0h+var_170], rax
0x140010e20  mov     r8d, 11Ch; Size
0x140010e26  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x140010e2b  xor     eax, eax
0x140010e2d  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x140010e32  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x140010e37  call    memset_0
0x140010e3c  xor     eax, eax
0x140010e3e  lea     rdx, [rbp+0F0h+SystemInformation]; SystemInformation
0x140010e42  mov     [rbp+0F0h+var_158], rax
0x140010e46  xor     r9d, r9d; ReturnLength
0x140010e49  lea     rax, SmpPagingFileDescriptorList
0x140010e50  xorps   xmm0, xmm0
0x140010e53  mov     cs:qword_140030C48, rax
0x140010e5a  mov     ecx, 0B8h; SystemInformationClass
0x140010e5f  mov     cs:SmpPagingFileDescriptorList, rax
0x140010e66  lea     rax, SmpVolumeDescriptorList
0x140010e6d  lea     r8d, [r9+18h]; SystemInformationLength
0x140010e71  mov     cs:qword_140030C28, rax
0x140010e78  mov     cs:SmpVolumeDescriptorList, rax
0x140010e7f  movups  [rbp+0F0h+SystemInformation], xmm0
0x140010e83  call    cs:__imp_NtQuerySystemInformation
0x140010e89  mov     rax, qword ptr [rbp+0F0h+SystemInformation]
0x140010e8d  mov     cs:SmpMemorySize, rax
0x140010e94  mov     rax, [rbp+0F0h+var_158]
0x140010e98  mov     cs:SmpHighestPhysicalAddress, rax
0x140010e9f  call    cs:__imp_RtlGetNtSystemRoot
0x140010ea5  movzx   ecx, word ptr [rax]; SourceCharacter
0x140010ea8  call    cs:__imp_RtlUpcaseUnicodeChar
0x140010eae  xorps   xmm0, xmm0
0x140010eb1  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x140010eba  mov     cs:SmpOsVolumeLetter, ax
0x140010ec1  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x140010ec6  lea     rax, [rsp+1F0h+var_188]
0x140010ecb  mov     [rsp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x140010ed3  mov     esi, 30h ; '0'
0x140010ed8  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x140010edd  mov     edx, 2001Fh; DesiredAccess
0x140010ee2  mov     [rsp+1F0h+ObjectAttributes.Length], esi
0x140010ee6  lea     rcx, SmpMmKey; KeyHandle
0x140010eed  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140010ef3  call    cs:__imp_NtOpenKey
0x140010ef9  mov     ebx, eax
0x140010efb  test    eax, eax
0x140010efd  jns     short loc_140010F1A
0x140010eff  mov     edx, 247h
0x140010f04  mov     r8d, ebx
0x140010f07  lea     rcx, aSmppagefileini; "SmpPagefileInitialize"
0x140010f0e  call    SmpLogFailure
0x140010f13  mov     eax, ebx
0x140010f15  jmp     loc_140011049
0x140010f1a  lea     rax, [rsp+1F0h+var_178]
0x140010f1f  mov     [rsp+1F0h+ObjectAttributes.Length], esi
0x140010f23  xorps   xmm0, xmm0
0x140010f26  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x140010f2b  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x140010f30  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], 0
0x140010f39  mov     edx, 2001Fh; DesiredAccess
0x140010f3e  mov     [rsp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x140010f46  lea     rcx, SmpCrashDumpKey; KeyHandle
0x140010f4d  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140010f53  call    cs:__imp_NtOpenKey
0x140010f59  mov     ebx, eax
0x140010f5b  test    eax, eax
0x140010f5d  jns     short loc_140010F66
0x140010f5f  mov     edx, 258h
0x140010f64  jmp     short loc_140010F04
0x140010f66  lea     rax, aCrashdumpenabl; "CrashDumpEnabled"
0x140010f6d  mov     [rsp+1F0h+var_1C8], 220020h
0x140010f76  mov     ebx, 4
0x140010f7b  mov     [rsp+1F0h+var_1C0], rax
0x140010f80  mov     r8d, ebx
0x140010f83  mov     [rsp+1F0h+var_1D0], 0
0x140010f8b  lea     r9, [rsp+1F0h+var_1D0]
0x140010f90  lea     rdx, [rsp+1F0h+var_1C8]
0x140010f95  call    SmpQueryDwordFromRegistry
0x140010f9a  mov     ecx, [rsp+1F0h+var_1D0]
0x140010f9e  test    eax, eax
0x140010fa0  cmovs   ecx, ebx
0x140010fa3  mov     cs:SmpDumpType, ecx
0x140010fa9  call    SmpQueryDedicatedDumpSetting
0x140010fae  mov     cs:SmpUseDedicatedDumpFile, al
0x140010fb4  lea     r9, [rsp+1F0h+var_1D0]
0x140010fb9  lea     rax, aFilterpages; "FilterPages"
0x140010fc0  mov     [rsp+1F0h+var_1C8], 180016h
0x140010fc9  xor     r8d, r8d
0x140010fcc  mov     [rsp+1F0h+var_1C0], rax
0x140010fd1  lea     rdx, [rsp+1F0h+var_1C8]
0x140010fd6  mov     [rsp+1F0h+var_1D0], 0
0x140010fde  xor     bl, bl
0x140010fe0  call    SmpQueryDwordFromRegistry
0x140010fe5  mov     esi, 1
0x140010fea  test    eax, eax
0x140010fec  js      short loc_140010FF9
0x140010fee  cmp     [rsp+1F0h+var_1D0], 0
0x140010ff3  movzx   ebx, bl
0x140010ff6  cmova   ebx, esi
0x140010ff9  mov     eax, cs:SmpSystemWriteConstraintInfo
0x140010fff  lea     rcx, [rbp+0F0h+VersionInformation.dwMajorVersion]; void *
0x140011003  shr     eax, 2
0x140011006  xor     edx, edx; Val
0x140011008  and     al, sil
0x14001100b  mov     cs:SmpUseFilterPagesDumpFile, bl
0x140011011  mov     r8d, 118h; Size
0x140011017  mov     cs:SmpForceCopyDumpFile, al
0x14001101d  call    memset_0
0x140011022  lea     rcx, [rbp+0F0h+VersionInformation]; lpVersionInformation
0x140011026  mov     [rbp+0F0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14001102d  call    cs:__imp_RtlGetVersion
0x140011033  test    eax, eax
0x140011035  js      short loc_140011047
0x140011037  cmp     [rbp+0F0h+var_36], sil
0x14001103e  jnz     short loc_140011047
0x140011040  mov     cs:SmpClientSku, sil
0x140011047  xor     eax, eax
0x140011049  mov     rcx, [rbp+0F0h+var_30]
0x140011050  xor     rcx, rsp; StackCookie
0x140011053  call    __security_check_cookie
0x140011058  add     rsp, 1D8h
0x14001105f  pop     r13
0x140011061  pop     rsi
0x140011062  pop     rbx
0x140011063  pop     rbp
0x140011064  retn
```
