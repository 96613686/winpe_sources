# ComputeService::ContainerUtilities::RemoveMappedDirectory(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1400d5dc4`
- end: `0x1400d60f7`
- name: `?RemoveMappedDirectory@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1_N@Z`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140074120`

## callees

- `0x140017040`
- `0x140018d70`
- `0x140024030`
- `0x14002d7f0`
- `0x1400421f0`
- `0x140042468`
- `0x140044974`
- `0x140080180`
- `0x1400c40e0`
- `0x1400d42bc`
- `0x1400d5bb8`
- `0x1400d5dc4`
- `0x1400d6100`
- `0x1400d62a0`
- `0x1400d630c`
- `0x1400d641c`
- `0x1401332f0`
- `0x140142dac`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d6037`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d6037`
- `ntdll!NtMakeTemporaryObject` at `0x1400d6064`
- `ntdll!NtMakeTemporaryObject` at `0x1400d6064`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400d5f93`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1400d5f93`

## string_xrefs

- `0x1400d5fa7`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d604e`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d607b`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d60c1`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ComputeService::ContainerUtilities::RemoveMappedDirectory(
        __int64 a1,
        __int64 a2,
        struct _GUID *a3,
        char a4)
{
  char *v7; // r8
  ComputeService::Storage *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rax
  _QWORD *ContainerNamespacePath; // rax
  __int64 v15; // rax
  const WCHAR *v16; // rcx
  const char *v17; // r9
  __int64 v18; // rax
  void **v19; // rax
  NTSTATUS v20; // eax
  NTSTATUS TemporaryObject; // eax
  __int64 v22; // rdx
  LPCWSTR *v23; // r8
  int v24; // eax
  WCHAR v25[8]; // [rsp+20h] [rbp-A9h] BYREF
  WCHAR v26[16]; // [rsp+40h] [rbp-89h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-69h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp-39h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int64 v30; // [rsp+B0h] [rbp-19h]
  WCHAR pszPathOut[20]; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v32; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  std::wstring::wstring(lpPathName);
  if ( *(_QWORD *)a3[1].Data4 <= 7u )
    v8 = (ComputeService::Storage *)a3;
  else
    v8 = *(ComputeService::Storage **)&a3->Data1;
  if ( ComputeService::Storage::IsDriveLetter(v8, 0, v7) )
  {
    std::wstring::wstring(pszPathOut);
    if ( a4 )
    {
      v10 = ComputeService::Storage::ResolveDirectoryPath(v26);
      std::wstring::operator=(lpPathName, v10);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v26);
      if ( *(_QWORD *)a3[1].Data4 > 7u )
        a3 = *(struct _GUID **)&a3->Data1;
      v11 = Vml::FormatString(v26, L"\\GLOBAL??\\%s", a3);
      std::wstring::operator=(pszPathOut, v11);
      v12 = v26;
    }
    else
    {
      ComputeService::ContainerUtilities::_anonymous_namespace_::GetHashPath(v25, a3);
      v13 = ComputeService::Storage::ConvertContainerPathToHostPath(v26);
      std::wstring::operator=(lpPathName, v13);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v26);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v25);
      if ( *(_QWORD *)a3[1].Data4 > 7u )
        a3 = *(struct _GUID **)&a3->Data1;
      ContainerNamespacePath = (_QWORD *)ComputeService::ContainerUtilities::QueryContainerNamespacePath(v25, a1);
      if ( ContainerNamespacePath[3] > 7u )
        ContainerNamespacePath = (_QWORD *)*ContainerNamespacePath;
      v15 = Vml::FormatString(v26, L"%s\\GLOBAL??\\%s", ContainerNamespacePath, a3);
      std::wstring::operator=(pszPathOut, v15);
      Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v26);
      v12 = v25;
    }
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v12);
    v16 = (const WCHAR *)lpPathName;
    if ( v30 > 7 )
      v16 = lpPathName[0];
    if ( !RemoveDirectoryW(v16) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        v17);
    v18 = std::wstring::operator std::basic_string_view<unsigned short>(pszPathOut, v26);
    *(_DWORD *)&v25[2] = 0;
    *(_QWORD *)&v25[4] = *(_QWORD *)v18;
    v25[0] = 2 * *(_WORD *)(v18 + 8);
    *(_DWORD *)&v25[1] = v25[0];
    v32 = *(_OWORD *)v25;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 16;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v32;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Handle = 0;
    v19 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&Handle);
    v20 = NtOpenSymbolicLinkObject(v19, 0x10000000u, &ObjectAttributes);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)v20,
        *(int *)v25);
    TemporaryObject = NtMakeTemporaryObject(Handle);
    if ( TemporaryObject < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)TemporaryObject,
        *(int *)v25);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Handle);
  }
  else
  {
    if ( a4 )
      v9 = ComputeService::Storage::ResolveDirectoryPath(pszPathOut);
    else
      v9 = ComputeService::Storage::ConvertContainerPathToHostPath(pszPathOut);
    std::wstring::operator=(lpPathName, v9);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)pszPathOut);
  v23 = lpPathName;
  if ( v30 > 7 )
    v23 = (LPCWSTR *)lpPathName[0];
  v24 = BfRemoveMappingInternal(a1, v22, v23);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
      (const char *)(unsigned int)v24,
      *(int *)v25);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpPathName);
}

```

## disassembly

```asm
0x1400d5dc4  push    rbp
0x1400d5dc6  push    rbx
0x1400d5dc7  push    rsi
0x1400d5dc8  push    rdi
0x1400d5dc9  push    r14
0x1400d5dcb  lea     rbp, [rsp-37h]
0x1400d5dd0  sub     rsp, 100h
0x1400d5dd7  mov     rax, cs:__security_cookie
0x1400d5dde  xor     rax, rsp
0x1400d5de1  mov     [rbp+57h+var_30], rax
0x1400d5de5  mov     sil, r9b
0x1400d5de8  mov     rbx, r8
0x1400d5deb  mov     rdi, rdx
0x1400d5dee  mov     r14, rcx
0x1400d5df1  lea     rcx, [rbp+57h+lpPathName]; void *
0x1400d5df5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400d5dfa  nop
0x1400d5dfb  cmp     qword ptr [rbx+18h], 7
0x1400d5e00  jbe     short loc_1400D5E07
0x1400d5e02  mov     rcx, [rbx]
0x1400d5e05  jmp     short loc_1400D5E0A
0x1400d5e07  mov     rcx, rbx; this
0x1400d5e0a  xor     edx, edx; unsigned __int16 *
0x1400d5e0c  call    ?IsDriveLetter@Storage@ComputeService@@YA_NPEBGPEAD@Z; ComputeService::Storage::IsDriveLetter(ushort const *,char *)
0x1400d5e11  test    al, al
0x1400d5e13  jnz     short loc_1400D5E66
0x1400d5e15  test    sil, sil
0x1400d5e18  jz      short loc_1400D5E41
0x1400d5e1a  cmp     qword ptr [rbx+18h], 7
0x1400d5e1f  jbe     short loc_1400D5E24
0x1400d5e21  mov     rbx, [rbx]
0x1400d5e24  mov     rdx, rbx
0x1400d5e27  lea     rcx, [rbp+57h+pszPathOut]; void *
0x1400d5e2b  call    ?ResolveDirectoryPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveDirectoryPath(ushort const *)
0x1400d5e30  mov     rdx, rax
0x1400d5e33  lea     rcx, [rbp+57h+lpPathName]
0x1400d5e37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5e3c  jmp     loc_1400D6097
0x1400d5e41  cmp     qword ptr [rbx+18h], 7
0x1400d5e46  jbe     short loc_1400D5E4B
0x1400d5e48  mov     rbx, [rbx]
0x1400d5e4b  cmp     qword ptr [rdi+18h], 7
0x1400d5e50  jbe     short loc_1400D5E55
0x1400d5e52  mov     rdi, [rdi]
0x1400d5e55  mov     r8, rbx
0x1400d5e58  mov     rdx, rdi
0x1400d5e5b  lea     rcx, [rbp+57h+pszPathOut]; pszPathOut
0x1400d5e5f  call    ?ConvertContainerPathToHostPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; ComputeService::Storage::ConvertContainerPathToHostPath(ushort const *,ushort const *)
0x1400d5e64  jmp     short loc_1400D5E30
0x1400d5e66  lea     rcx, [rbp+57h+pszPathOut]; void *
0x1400d5e6a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400d5e6f  nop
0x1400d5e70  test    sil, sil
0x1400d5e73  jz      short loc_1400D5ED8
0x1400d5e75  cmp     qword ptr [rbx+18h], 7
0x1400d5e7a  jbe     short loc_1400D5E81
0x1400d5e7c  mov     rdx, [rbx]
0x1400d5e7f  jmp     short loc_1400D5E84
0x1400d5e81  mov     rdx, rbx
0x1400d5e84  lea     rcx, [rsp+120h+var_E0]; void *
0x1400d5e89  call    ?ResolveDirectoryPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; ComputeService::Storage::ResolveDirectoryPath(ushort const *)
0x1400d5e8e  mov     rdx, rax
0x1400d5e91  lea     rcx, [rbp+57h+lpPathName]
0x1400d5e95  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5e9a  lea     rcx, [rsp+120h+var_E0]; this
0x1400d5e9f  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5ea4  cmp     qword ptr [rbx+18h], 7
0x1400d5ea9  jbe     short loc_1400D5EAE
0x1400d5eab  mov     rbx, [rbx]
0x1400d5eae  mov     r8, rbx
0x1400d5eb1  lea     rdx, aGlobalS; "\\GLOBAL??\\%s"
0x1400d5eb8  lea     rcx, [rsp+120h+var_E0]
0x1400d5ebd  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d5ec2  mov     rdx, rax
0x1400d5ec5  lea     rcx, [rbp+57h+pszPathOut]
0x1400d5ec9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5ece  lea     rcx, [rsp+120h+var_E0]
0x1400d5ed3  jmp     loc_1400D5F80
0x1400d5ed8  mov     rdx, rbx; struct _GUID *
0x1400d5edb  lea     rcx, [rsp+120h+var_100]; pszPathOut
0x1400d5ee0  call    ComputeService__ContainerUtilities___anonymous_namespace___GetHashPath
0x1400d5ee5  nop
0x1400d5ee6  cmp     qword ptr [rax+18h], 7
0x1400d5eeb  jbe     short loc_1400D5EF0
0x1400d5eed  mov     rax, [rax]
0x1400d5ef0  cmp     qword ptr [rdi+18h], 7
0x1400d5ef5  jbe     short loc_1400D5EFA
0x1400d5ef7  mov     rdi, [rdi]
0x1400d5efa  mov     r8, rax
0x1400d5efd  mov     rdx, rdi
0x1400d5f00  lea     rcx, [rsp+120h+var_E0]; pszPathOut
0x1400d5f05  call    ?ConvertContainerPathToHostPath@Storage@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; ComputeService::Storage::ConvertContainerPathToHostPath(ushort const *,ushort const *)
0x1400d5f0a  mov     rdx, rax
0x1400d5f0d  lea     rcx, [rbp+57h+lpPathName]
0x1400d5f11  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5f16  lea     rcx, [rsp+120h+var_E0]; this
0x1400d5f1b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5f20  nop
0x1400d5f21  lea     rcx, [rsp+120h+var_100]; this
0x1400d5f26  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5f2b  cmp     qword ptr [rbx+18h], 7
0x1400d5f30  jbe     short loc_1400D5F35
0x1400d5f32  mov     rbx, [rbx]
0x1400d5f35  mov     rdx, r14
0x1400d5f38  lea     rcx, [rsp+120h+var_100]
0x1400d5f3d  call    ?QueryContainerNamespacePath@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryContainerNamespacePath(void *)
0x1400d5f42  nop
0x1400d5f43  cmp     qword ptr [rax+18h], 7
0x1400d5f48  jbe     short loc_1400D5F4D
0x1400d5f4a  mov     rax, [rax]
0x1400d5f4d  mov     r9, rbx
0x1400d5f50  mov     r8, rax
0x1400d5f53  lea     rdx, aSGlobalS; "%s\\GLOBAL??\\%s"
0x1400d5f5a  lea     rcx, [rsp+120h+var_E0]
0x1400d5f5f  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d5f64  mov     rdx, rax
0x1400d5f67  lea     rcx, [rbp+57h+pszPathOut]
0x1400d5f6b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400d5f70  lea     rcx, [rsp+120h+var_E0]; this
0x1400d5f75  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5f7a  nop
0x1400d5f7b  lea     rcx, [rsp+120h+var_100]; this
0x1400d5f80  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d5f85  lea     rcx, [rbp+57h+lpPathName]
0x1400d5f89  cmp     [rbp+57h+var_70], 7
0x1400d5f8e  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x1400d5f93  call    cs:__imp_RemoveDirectoryW
0x1400d5f9a  nop     dword ptr [rax+rax+00h]
0x1400d5f9f  mov     rcx, [rbp+5Fh]; this
0x1400d5fa3  test    eax, eax
0x1400d5fa5  jnz     short loc_1400D5FB9
0x1400d5fa7  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d5fae  mov     edx, 1BCh; void *
0x1400d5fb3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400d5fb9  lea     rdx, [rsp+120h+var_E0]
0x1400d5fbe  lea     rcx, [rbp+57h+pszPathOut]
0x1400d5fc2  call    ??B?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string_view@GU?$char_traits@G@std@@@1@XZ; std::wstring::operator std::basic_string_view<ushort>(void)
0x1400d5fc7  mov     dword ptr [rsp+120h+var_100+4], 0
0x1400d5fcf  mov     rcx, [rax]
0x1400d5fd2  mov     qword ptr [rsp+120h+var_100+8], rcx
0x1400d5fd7  movzx   ecx, word ptr [rax+8]
0x1400d5fdb  add     cx, cx
0x1400d5fde  mov     [rsp+120h+var_100], cx; int
0x1400d5fe3  mov     [rsp+120h+var_100+2], cx
0x1400d5fe8  movaps  xmm0, xmmword ptr [rsp+120h+var_100]
0x1400d5fed  movdqa  [rbp+57h+var_40], xmm0
0x1400d5ff2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d5ffa  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 10h
0x1400d6002  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d600a  lea     rax, [rbp+57h+var_40]
0x1400d600e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d6012  xorps   xmm0, xmm0
0x1400d6015  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d601a  mov     [rbp+57h+Handle], 0
0x1400d6022  lea     rcx, [rbp+57h+Handle]
0x1400d6026  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1400d602b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d602f  mov     edx, 10000000h; DesiredAccess
0x1400d6034  mov     rcx, rax; SymbolicLinkHandle
0x1400d6037  call    cs:__imp_NtOpenSymbolicLinkObject
0x1400d603e  nop     dword ptr [rax+rax+00h]
0x1400d6043  mov     rcx, [rbp+5Fh]; this
0x1400d6047  test    eax, eax
0x1400d6049  jns     short loc_1400D6060
0x1400d604b  mov     r9d, eax; char *
0x1400d604e  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d6055  mov     edx, 1C1h; void *
0x1400d605a  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d6060  mov     rcx, [rbp+57h+Handle]; Handle
0x1400d6064  call    cs:__imp_NtMakeTemporaryObject
0x1400d606b  nop     dword ptr [rax+rax+00h]
0x1400d6070  mov     rcx, [rbp+5Fh]; this
0x1400d6074  test    eax, eax
0x1400d6076  jns     short loc_1400D608D
0x1400d6078  mov     r9d, eax; char *
0x1400d607b  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d6082  mov     edx, 1C2h; void *
0x1400d6087  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400d608d  lea     rcx, [rbp+57h+Handle]; void *
0x1400d6091  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400d6096  nop
0x1400d6097  lea     rcx, [rbp+57h+pszPathOut]; this
0x1400d609b  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d60a0  lea     r8, [rbp+57h+lpPathName]
0x1400d60a4  cmp     [rbp+57h+var_70], 7
0x1400d60a9  cmova   r8, [rbp+57h+lpPathName]
0x1400d60ae  mov     rcx, r14
0x1400d60b1  call    BfRemoveMappingInternal
0x1400d60b6  mov     rcx, [rbp+5Fh]; this
0x1400d60ba  test    eax, eax
0x1400d60bc  jns     short loc_1400D60D3
0x1400d60be  mov     r9d, eax; char *
0x1400d60c1  lea     r8, aOnecoreVmCompu_91; "onecore\\vm\\compute\\management\\share"...
0x1400d60c8  mov     edx, 1C5h; void *
0x1400d60cd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400d60d3  lea     rcx, [rbp+57h+lpPathName]; this
0x1400d60d7  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400d60dc  mov     rcx, [rbp+57h+var_30]
0x1400d60e0  xor     rcx, rsp; StackCookie
0x1400d60e3  call    __security_check_cookie
0x1400d60e8  add     rsp, 100h
0x1400d60ef  pop     r14
0x1400d60f1  pop     rdi
0x1400d60f2  pop     rsi
0x1400d60f3  pop     rbx
0x1400d60f4  pop     rbp
0x1400d60f5  retn
```
