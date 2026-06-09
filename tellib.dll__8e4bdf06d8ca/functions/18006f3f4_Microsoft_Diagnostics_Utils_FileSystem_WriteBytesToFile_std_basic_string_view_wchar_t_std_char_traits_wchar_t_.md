# Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,gsl::span<gsl::byte const,-1>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18006f3f4`
- end: `0x18006f666`
- name: `?WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z`
- size: `626`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800707e0`
- `0x1801817c4`
- `0x180218dbc`
- `0x18028db10`
- `0x18028ddf8`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x180034d94`
- `0x180035698`
- `0x18006dd98`
- `0x18006f3f4`
- `0x18006f66c`
- `0x18007fae8`
- `0x180089d90`
- `0x18012de40`
- `0x18017c90c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f5a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f600`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006f5f0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006f5f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f522`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f578`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f522`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f578`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f491`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006f491`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  BOOL v6; // ebx
  signed int v7; // ebx
  const WCHAR *v8; // rcx
  HANDLE v9; // rax
  const WCHAR *v10; // rcx
  HANDLE FileW; // rax
  signed int v12; // eax
  __int64 v13; // rdx
  signed int LastError; // eax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-79h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-79h]
  signed int v18; // [rsp+40h] [rbp-59h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-51h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-49h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-41h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-39h] BYREF
  _QWORD v23[2]; // [rsp+78h] [rbp-21h] BYREF
  char v24; // [rsp+88h] [rbp-11h]
  LPCWSTR lpFileName[3]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int64 v26; // [rsp+A8h] [rbp+Fh]
  _BYTE v27[32]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v18 = 0;
  NumberOfBytesWritten = 0;
  hFile = (HANDLE)-1LL;
  std::wstring::wstring((__int64)lpFileName, a1);
  v23[0] = &v18;
  v23[1] = lpFileName;
  v24 = 1;
  if ( a3[1] )
  {
    SecurityDescriptor = 0;
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
      &SecurityDescriptor,
      0);
    v5 = std::wstring::wstring((__int64)v27, a3);
    if ( *(_QWORD *)(v5 + 24) > 7u )
      v5 = *(_QWORD *)v5;
    v6 = ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)v5, 1u, &SecurityDescriptor, 0);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v27);
    if ( !v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x257,
             (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
             (const char *)0x53A,
             dwCreationDisposition);
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
      goto LABEL_24;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v8 = (const WCHAR *)lpFileName;
    if ( v26 > 7 )
      v8 = lpFileName[0];
    v9 = CreateFileW(v8, 0x40000000u, 0, &SecurityAttributes, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      v9);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
  }
  else
  {
    v10 = (const WCHAR *)lpFileName;
    if ( v26 > 7 )
      v10 = lpFileName[0];
    FileW = CreateFileW(v10, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hFile,
      FileW);
  }
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( WriteFile(hFile, *(LPCVOID *)(a2 + 8), *(_DWORD *)a2, &NumberOfBytesWritten, 0) )
    {
      v7 = 0;
      goto LABEL_24;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v18 = v7;
    if ( v7 < 0 )
    {
      v13 = 641;
      goto LABEL_17;
    }
  }
  else
  {
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    v18 = v7;
    if ( v7 < 0 )
    {
      v13 = 635;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\FileSystemUtils.h",
        (const char *)(unsigned int)v7,
        dwCreationDispositiona);
    }
  }
LABEL_24:
  v24 = 0;
  `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile'::`2'::_lambda_1_::operator()(v23);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006f3f4  push    rbp
0x18006f3f6  push    rbx
0x18006f3f7  push    rdi
0x18006f3f8  lea     rbp, [rsp-47h]
0x18006f3fd  sub     rsp, 0E0h
0x18006f404  mov     rax, cs:__security_cookie
0x18006f40b  xor     rax, rsp
0x18006f40e  mov     [rbp+57h+var_20], rax
0x18006f412  mov     rbx, r8
0x18006f415  mov     rdi, rdx
0x18006f418  mov     [rbp+57h+var_B0], 0
0x18006f41f  mov     [rbp+57h+NumberOfBytesWritten], 0
0x18006f426  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x18006f42e  mov     rdx, rcx
0x18006f431  lea     rcx, [rbp+57h+lpFileName]
0x18006f435  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006f43a  nop
0x18006f43b  lea     rax, [rbp+57h+var_B0]
0x18006f43f  mov     [rbp+57h+var_78], rax
0x18006f443  lea     rax, [rbp+57h+lpFileName]
0x18006f447  mov     [rbp+57h+var_70], rax
0x18006f44b  mov     [rbp+57h+var_68], 1
0x18006f44f  cmp     qword ptr [rbx+8], 0
0x18006f454  jz      loc_18006F546
0x18006f45a  mov     [rbp+57h+SecurityDescriptor], 0
0x18006f462  xor     edx, edx
0x18006f464  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006f468  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18006f46d  mov     rdx, rbx
0x18006f470  lea     rcx, [rbp+57h+var_40]
0x18006f474  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006f479  cmp     qword ptr [rax+18h], 7
0x18006f47e  jbe     short loc_18006F483
0x18006f480  mov     rax, [rax]
0x18006f483  xor     r9d, r9d; SecurityDescriptorSize
0x18006f486  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006f48a  lea     edx, [r9+1]; StringSDRevision
0x18006f48e  mov     rcx, rax; StringSecurityDescriptor
0x18006f491  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006f498  nop     dword ptr [rax+rax+00h]
0x18006f49d  mov     ebx, eax
0x18006f49f  lea     rcx, [rbp+57h+var_40]; this
0x18006f4a3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006f4a8  test    ebx, ebx
0x18006f4aa  jnz     short loc_18006F4D7
0x18006f4ac  mov     rcx, [rbp+5Fh]; this
0x18006f4b0  mov     r9d, 53Ah; char *
0x18006f4b6  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18006f4bd  mov     edx, 257h; void *
0x18006f4c2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006f4c7  mov     ebx, eax
0x18006f4c9  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006f4cd  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006f4d2  jmp     loc_18006F62B
0x18006f4d7  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18006f4df  mov     rax, [rbp+57h+SecurityDescriptor]
0x18006f4e3  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18006f4e7  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x18006f4ef  lea     rcx, [rbp+57h+lpFileName]
0x18006f4f3  cmp     [rbp+57h+var_48], 7
0x18006f4f8  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18006f4fd  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18006f506  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f50e  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x18006f516  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18006f51a  xor     r8d, r8d; dwShareMode
0x18006f51d  mov     edx, 40000000h; dwDesiredAccess
0x18006f522  call    cs:__imp_CreateFileW
0x18006f529  nop     dword ptr [rax+rax+00h]
0x18006f52e  mov     rdx, rax
0x18006f531  lea     rcx, [rbp+57h+hFile]
0x18006f535  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006f53a  nop
0x18006f53b  lea     rcx, [rbp+57h+SecurityDescriptor]
0x18006f53f  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18006f544  jmp     short loc_18006F590
0x18006f546  lea     rcx, [rbp+57h+lpFileName]
0x18006f54a  cmp     [rbp+57h+var_48], 7
0x18006f54f  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18006f554  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18006f55d  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f565  mov     [rsp+0F0h+dwCreationDisposition], 2; int
0x18006f56d  xor     r9d, r9d; lpSecurityAttributes
0x18006f570  xor     r8d, r8d; dwShareMode
0x18006f573  mov     edx, 40000000h; dwDesiredAccess
0x18006f578  call    cs:__imp_CreateFileW
0x18006f57f  nop     dword ptr [rax+rax+00h]
0x18006f584  mov     rdx, rax
0x18006f587  lea     rcx, [rbp+57h+hFile]
0x18006f58b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006f590  mov     rcx, [rbp+57h+hFile]; hFile
0x18006f594  lea     rax, [rcx+1]
0x18006f598  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006f59e  jnz     short loc_18006F5DC
0x18006f5a0  call    cs:__imp_GetLastError
0x18006f5a7  nop     dword ptr [rax+rax+00h]
0x18006f5ac  mov     ebx, eax
0x18006f5ae  test    eax, eax
0x18006f5b0  jle     short loc_18006F5BB
0x18006f5b2  movzx   ebx, ax
0x18006f5b5  or      ebx, 80070000h
0x18006f5bb  mov     [rbp+57h+var_B0], ebx
0x18006f5be  test    ebx, ebx
0x18006f5c0  jns     short loc_18006F62B
0x18006f5c2  mov     edx, 27Bh; void *
0x18006f5c7  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x18006f5ce  mov     r9d, ebx; char *
0x18006f5d1  mov     rcx, [rbp+5Fh]; this
0x18006f5d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f5da  jmp     short loc_18006F62B
0x18006f5dc  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x18006f5df  mov     qword ptr [rsp+0F0h+dwCreationDisposition], 0; lpOverlapped
0x18006f5e8  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18006f5ec  mov     rdx, [rdi+8]; lpBuffer
0x18006f5f0  call    cs:__imp_WriteFile
0x18006f5f7  nop     dword ptr [rax+rax+00h]
0x18006f5fc  test    eax, eax
0x18006f5fe  jnz     short loc_18006F629
0x18006f600  call    cs:__imp_GetLastError
0x18006f607  nop     dword ptr [rax+rax+00h]
0x18006f60c  mov     ebx, eax
0x18006f60e  test    eax, eax
0x18006f610  jle     short loc_18006F61B
0x18006f612  movzx   ebx, ax
0x18006f615  or      ebx, 80070000h
0x18006f61b  mov     [rbp+57h+var_B0], ebx
0x18006f61e  test    ebx, ebx
0x18006f620  jns     short loc_18006F62B
0x18006f622  mov     edx, 281h
0x18006f627  jmp     short loc_18006F5C7
0x18006f629  xor     ebx, ebx
0x18006f62b  mov     [rbp+57h+var_68], 0
0x18006f62f  lea     rcx, [rbp+57h+var_78]
0x18006f633  call    ??R_lambda_1_@?1??WriteBytesToFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@0@Z@QEBA@XZ; `Microsoft::Diagnostics::Utils::FileSystem::WriteBytesToFile(std::wstring_view,gsl::span<gsl::byte const,-1>,std::wstring_view)'::`2'::_lambda_1_::operator()(void)
0x18006f638  nop
0x18006f639  lea     rcx, [rbp+57h+lpFileName]; this
0x18006f63d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18006f642  nop
0x18006f643  lea     rcx, [rbp+57h+hFile]
0x18006f647  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006f64c  mov     eax, ebx
0x18006f64e  mov     rcx, [rbp+57h+var_20]
0x18006f652  xor     rcx, rsp; StackCookie
0x18006f655  call    __security_check_cookie
0x18006f65a  add     rsp, 0E0h
0x18006f661  pop     rdi
0x18006f662  pop     rbx
0x18006f663  pop     rbp
0x18006f664  retn
```
