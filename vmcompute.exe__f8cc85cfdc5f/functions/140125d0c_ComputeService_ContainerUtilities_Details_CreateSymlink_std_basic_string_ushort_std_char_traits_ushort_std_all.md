# ComputeService::ContainerUtilities::Details::CreateSymlink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x140125d0c`
- end: `0x140125eef`
- name: `?CreateSymlink@Details@ContainerUtilities@ComputeService@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z`
- size: `483`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140214cbc`

## callees

- `0x140024030`
- `0x140042468`
- `0x140057fec`
- `0x140125d0c`
- `0x140126054`
- `0x1401332f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140125d72`
- `ntdll!RtlInitUnicodeString` at `0x140125d91`
- `ntdll!RtlInitUnicodeString` at `0x140125d72`
- `ntdll!RtlInitUnicodeString` at `0x140125d91`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140125dd8`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140125dd8`
- `ntdll!NtSetInformationSymbolicLink` at `0x140125e8b`
- `ntdll!NtSetInformationSymbolicLink` at `0x140125e8b`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140125e29`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140125e29`

## string_xrefs

- `0x140125e52`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140125eaf`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140125ea0`: `Symlink: %ws`
- `0x140125e43`: `Symlink: %ws => %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ComputeService::ContainerUtilities::Details::CreateSymlink(
        const WCHAR *SourceString,
        PCWSTR a2,
        char a3)
{
  PCWSTR v5; // rbx
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rdx
  void **v8; // rax
  const char *v9; // rsi
  void **v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  __int64 v14; // [rsp+70h] [rbp+7h] BYREF
  int v15; // [rsp+78h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+17h] BYREF
  struct _UNICODE_STRING Name; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v5 = SourceString;
  DestinationString = 0;
  Name = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v14 = 0;
  if ( *((_QWORD *)SourceString + 3) <= 7u )
    v6 = SourceString;
  else
    v6 = *(const WCHAR **)SourceString;
  RtlInitUnicodeString(&DestinationString, v6);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v7 = a2;
  else
    v7 = *(const WCHAR **)a2;
  RtlInitUnicodeString(&Name, v7);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 80;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v14);
  if ( NtOpenSymbolicLinkObject(v8, 0x80000000, &ObjectAttributes) < 0 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v14,
      0);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(PCWSTR *)a2;
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v9 = (const char *)v5;
    else
      v9 = *(const char **)v5;
    v10 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v14);
    v11 = NtCreateSymbolicLinkObject(v10, 0xFFFFFu, &ObjectAttributes, &Name);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)v11,
      (int)"Symlink: %ws => %ws",
      v9,
      a2);
    if ( a3 )
    {
      v15 = 0;
      if ( *((_QWORD *)v5 + 3) > 7u )
        v5 = *(PCWSTR *)v5;
      v12 = NtSetInformationSymbolicLink(v14, 1, &v15, 4);
      wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)v12,
        (int)"Symlink: %ws",
        (const char *)v5);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
}

```

## disassembly

```asm
0x140125d0c  mov     [rsp-8+arg_10], rbx
0x140125d11  mov     [rsp-8+arg_18], rsi
0x140125d16  push    rbp
0x140125d17  push    rdi
0x140125d18  push    r14
0x140125d1a  lea     rbp, [rsp-47h]
0x140125d1f  sub     rsp, 0B0h
0x140125d26  mov     rax, cs:__security_cookie
0x140125d2d  xor     rax, rsp
0x140125d30  mov     [rbp+57h+var_20], rax
0x140125d34  mov     r14b, r8b
0x140125d37  mov     rdi, rdx
0x140125d3a  mov     rbx, rcx
0x140125d3d  xorps   xmm0, xmm0
0x140125d40  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140125d44  xorps   xmm1, xmm1
0x140125d47  movups  xmmword ptr [rbp+57h+Name.Length], xmm1
0x140125d4b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140125d4f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140125d53  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140125d57  mov     [rbp+57h+var_50], 0
0x140125d5f  cmp     qword ptr [rcx+18h], 7
0x140125d64  jbe     short loc_140125D6B
0x140125d66  mov     rdx, [rcx]
0x140125d69  jmp     short loc_140125D6E
0x140125d6b  mov     rdx, rbx; SourceString
0x140125d6e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140125d72  call    cs:__imp_RtlInitUnicodeString
0x140125d79  nop     dword ptr [rax+rax+00h]
0x140125d7e  cmp     qword ptr [rdi+18h], 7
0x140125d83  jbe     short loc_140125D8A
0x140125d85  mov     rdx, [rdi]
0x140125d88  jmp     short loc_140125D8D
0x140125d8a  mov     rdx, rdi; SourceString
0x140125d8d  lea     rcx, [rbp+57h+Name]; DestinationString
0x140125d91  call    cs:__imp_RtlInitUnicodeString
0x140125d98  nop     dword ptr [rax+rax+00h]
0x140125d9d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140125da4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140125dac  mov     [rbp+57h+ObjectAttributes.Attributes], 50h ; 'P'
0x140125db3  lea     rax, [rbp+57h+DestinationString]
0x140125db7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140125dbb  xorps   xmm0, xmm0
0x140125dbe  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140125dc3  lea     rcx, [rbp+57h+var_50]
0x140125dc7  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140125dcc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140125dd0  mov     edx, 80000000h; DesiredAccess
0x140125dd5  mov     rcx, rax; SymbolicLinkHandle
0x140125dd8  call    cs:__imp_NtOpenSymbolicLinkObject
0x140125ddf  nop     dword ptr [rax+rax+00h]
0x140125de4  test    eax, eax
0x140125de6  jns     loc_140125EC1
0x140125dec  xor     edx, edx
0x140125dee  lea     rcx, [rbp+57h+var_50]
0x140125df2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140125df7  cmp     qword ptr [rdi+18h], 7
0x140125dfc  jbe     short loc_140125E01
0x140125dfe  mov     rdi, [rdi]
0x140125e01  cmp     qword ptr [rbx+18h], 7
0x140125e06  jbe     short loc_140125E0D
0x140125e08  mov     rsi, [rbx]
0x140125e0b  jmp     short loc_140125E10
0x140125e0d  mov     rsi, rbx
0x140125e10  lea     rcx, [rbp+57h+var_50]
0x140125e14  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140125e19  lea     r9, [rbp+57h+Name]; Name
0x140125e1d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140125e21  mov     edx, 0FFFFFh; DesiredAccess
0x140125e26  mov     rcx, rax; SymbolicLinkHandle
0x140125e29  call    cs:__imp_NtCreateSymbolicLinkObject
0x140125e30  nop     dword ptr [rax+rax+00h]
0x140125e35  mov     rcx, [rbp+5Fh]; this
0x140125e39  mov     [rsp+0C0h+var_90], rdi
0x140125e3e  mov     [rsp+0C0h+var_98], rsi; char *
0x140125e43  lea     rdx, aSymlinkWsWs; "Symlink: %ws => %ws"
0x140125e4a  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x140125e4f  mov     r9d, eax; char *
0x140125e52  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x140125e59  mov     edx, 18Bh; void *
0x140125e5e  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140125e63  test    r14b, r14b
0x140125e66  jz      short loc_140125EC1
0x140125e68  mov     [rbp+57h+var_48], 0
0x140125e6f  cmp     qword ptr [rbx+18h], 7
0x140125e74  jbe     short loc_140125E79
0x140125e76  mov     rbx, [rbx]
0x140125e79  mov     r9d, 4
0x140125e7f  lea     r8, [rbp+57h+var_48]
0x140125e83  lea     edx, [r9-3]
0x140125e87  mov     rcx, [rbp+57h+var_50]
0x140125e8b  call    cs:__imp_NtSetInformationSymbolicLink
0x140125e92  nop     dword ptr [rax+rax+00h]
0x140125e97  mov     rcx, [rbp+5Fh]; this
0x140125e9b  mov     [rsp+0C0h+var_98], rbx; char *
0x140125ea0  lea     rdx, aSymlinkWs; "Symlink: %ws"
0x140125ea7  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x140125eac  mov     r9d, eax; char *
0x140125eaf  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x140125eb6  mov     edx, 193h; void *
0x140125ebb  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140125ec0  nop
0x140125ec1  lea     rcx, [rbp+57h+var_50]; void *
0x140125ec5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140125eca  mov     rcx, [rbp+57h+var_20]
0x140125ece  xor     rcx, rsp; StackCookie
0x140125ed1  call    __security_check_cookie
0x140125ed6  lea     r11, [rsp+0C0h+var_10]
0x140125ede  mov     rbx, [r11+30h]
0x140125ee2  mov     rsi, [r11+38h]
0x140125ee6  mov     rsp, r11
0x140125ee9  pop     r14
0x140125eeb  pop     rdi
0x140125eec  pop     rbp
0x140125eed  retn
```
