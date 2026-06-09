# OsImageUtilities::Helpers::CreateSandboxStateDirectory(ushort const *)

- ea: `0x18005340c`
- end: `0x180053595`
- name: `?CreateSandboxStateDirectory@Helpers@OsImageUtilities@@YAXPEBG@Z`
- size: `393`
- prototype: `void __fastcall(PCWSTR pszPathIn, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800369c0`
- `0x1800542e4`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x18002e454`
- `0x18002eb7c`
- `0x18002f94c`
- `0x18005340c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800534fa`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800534fa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800534cf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800534cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053535`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180053449`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180053449`

## string_xrefs

- `0x18005355f`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180053571`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`
- `0x180053583`: `onecore\vm\compute\dll\lib\storage\osimageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall OsImageUtilities::Helpers::CreateSandboxStateDirectory(PCWSTR pszPathIn, const unsigned __int16 *a2)
{
  const char *v3; // r9
  const WCHAR *v4; // rcx
  const char *v5; // r9
  const WCHAR *v6; // rcx
  const char *v7; // r9
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+20h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-11h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+40h] [rbp-9h] BYREF
  unsigned __int64 v11; // [rsp+58h] [rbp+Fh]
  __int128 v12; // [rsp+60h] [rbp+17h] BYREF
  __int64 v13; // [rsp+70h] [rbp+27h]
  __int128 v14; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v15; // [rsp+88h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;OICI;GA;;;SY)", 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v3);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  v14 = 0;
  v15 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v14, 17);
  v12 = 0;
  v13 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v12, 18);
  Vml::CombineFilePath(lpPathName, pszPathIn, L"WcSandboxState");
  v4 = (const WCHAR *)lpPathName;
  if ( v11 > 7 )
    v4 = lpPathName[0];
  if ( !CreateDirectoryW(v4, &SecurityAttributes) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14E,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v5);
  v6 = (const WCHAR *)lpPathName;
  if ( v11 > 7 )
    v6 = lpPathName[0];
  if ( !SetFileAttributesW(v6, 6u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\osimageutilities.cpp",
      v7);
  std::wstring::~wstring(lpPathName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v12);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((Vml::TemporaryPrivilege *)&v14);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x18005340c  mov     [rsp-8+arg_8], rbx
0x180053411  push    rbp
0x180053412  lea     rbp, [rsp-57h]
0x180053417  sub     rsp, 0A0h
0x18005341e  mov     rax, cs:__security_cookie
0x180053425  xor     rax, rsp
0x180053428  mov     [rbp+57h+var_10], rax
0x18005342c  mov     rbx, rcx
0x18005342f  mov     [rbp+57h+SecurityDescriptor], 0
0x180053437  xor     r9d, r9d; SecurityDescriptorSize
0x18005343a  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18005343e  lea     edx, [r9+1]; StringSDRevision
0x180053442  lea     rcx, aDPAOiciGaSy; "D:P(A;OICI;GA;;;SY)"
0x180053449  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180053450  nop     dword ptr [rax+rax+00h]
0x180053455  mov     rcx, [rbp+5Fh]; this
0x180053459  test    eax, eax
0x18005345b  jz      loc_180053571
0x180053461  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x180053469  mov     rax, [rbp+57h+SecurityDescriptor]
0x18005346d  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180053471  xor     eax, eax
0x180053473  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x180053477  xorps   xmm0, xmm0
0x18005347a  movups  [rbp+57h+var_28], xmm0
0x18005347e  mov     [rbp+57h+var_18], rax
0x180053482  lea     edx, [rax+11h]; int
0x180053485  lea     rcx, [rbp+57h+var_28]; this
0x180053489  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18005348e  nop
0x18005348f  xorps   xmm0, xmm0
0x180053492  xor     eax, eax
0x180053494  movups  [rbp+57h+var_40], xmm0
0x180053498  mov     [rbp+57h+var_30], rax
0x18005349c  lea     edx, [rax+12h]; int
0x18005349f  lea     rcx, [rbp+57h+var_40]; this
0x1800534a3  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x1800534a8  nop
0x1800534a9  lea     r8, aWcsandboxstate; "WcSandboxState"
0x1800534b0  mov     rdx, rbx; pszPathIn
0x1800534b3  lea     rcx, [rbp+57h+lpPathName]; Src
0x1800534b7  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800534bc  nop
0x1800534bd  lea     rcx, [rbp+57h+lpPathName]
0x1800534c1  cmp     [rbp+57h+var_48], 7
0x1800534c6  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x1800534cb  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800534cf  call    cs:__imp_CreateDirectoryW
0x1800534d6  nop     dword ptr [rax+rax+00h]
0x1800534db  mov     rcx, [rbp+5Fh]; this
0x1800534df  test    eax, eax
0x1800534e1  jz      loc_180053583
0x1800534e7  lea     rcx, [rbp+57h+lpPathName]
0x1800534eb  cmp     [rbp+57h+var_48], 7
0x1800534f0  cmova   rcx, [rbp+57h+lpPathName]; lpFileName
0x1800534f5  mov     edx, 6; dwFileAttributes
0x1800534fa  call    cs:__imp_SetFileAttributesW
0x180053501  nop     dword ptr [rax+rax+00h]
0x180053506  mov     rcx, [rbp+5Fh]; this
0x18005350a  test    eax, eax
0x18005350c  jz      short loc_18005355F
0x18005350e  lea     rcx, [rbp+57h+lpPathName]
0x180053512  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180053517  nop
0x180053518  lea     rcx, [rbp+57h+var_40]; this
0x18005351c  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180053521  nop
0x180053522  lea     rcx, [rbp+57h+var_28]; this
0x180053526  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18005352b  nop
0x18005352c  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180053530  test    rcx, rcx
0x180053533  jz      short loc_180053541
0x180053535  call    cs:__imp_LocalFree
0x18005353c  nop     dword ptr [rax+rax+00h]
0x180053541  mov     rcx, [rbp+57h+var_10]
0x180053545  xor     rcx, rsp; StackCookie
0x180053548  call    __security_check_cookie
0x18005354d  mov     rbx, [rsp+0A0h+arg_8]
0x180053555  add     rsp, 0A0h
0x18005355c  pop     rbp
0x18005355d  retn
0x18005355f  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053566  mov     edx, 14Fh; void *
0x18005356b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180053571  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180053578  mov     edx, 146h; void *
0x18005357d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180053583  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18005358a  mov     edx, 14Eh; void *
0x18005358f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
