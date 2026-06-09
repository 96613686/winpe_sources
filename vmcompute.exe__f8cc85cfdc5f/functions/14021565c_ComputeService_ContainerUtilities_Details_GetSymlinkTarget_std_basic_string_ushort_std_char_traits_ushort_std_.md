# ComputeService::ContainerUtilities::Details::GetSymlinkTarget(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14021565c`
- end: `0x14021586a`
- name: `?GetSymlinkTarget@Details@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140214cbc`
- `0x1402159ac`

## callees

- `0x140017040`
- `0x140024030`
- `0x1400421f0`
- `0x140042468`
- `0x140044974`
- `0x14009d8a4`
- `0x1400a97c8`
- `0x1400e4f40`
- `0x140126054`
- `0x1401332f0`
- `0x140211694`
- `0x14021565c`
- `0x140215f20`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1402156fb`
- `ntdll!RtlInitUnicodeString` at `0x1402156fb`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140215750`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140215750`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1402157c7`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1402157c7`

## string_xrefs

- `0x140215774`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140215804`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140215765`: `Symlink: %ws`
- `0x1402157f5`: `Symlink: %ws Status: %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ComputeService::ContainerUtilities::Details::GetSymlinkTarget(__int64 a1, __int64 a2)
{
  ULONG v4; // edi
  __int64 v5; // rax
  const WCHAR *v6; // rdx
  PCWSTR *v7; // rbx
  void **v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned int v11; // eax
  PCWSTR *v12; // rdx
  _QWORD v14[2]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-69h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+70h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-39h] BYREF
  ULONG DataWritten; // [rsp+B0h] [rbp-9h] BYREF
  WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  HANDLE SymLinkObjHandle; // [rsp+C0h] [rbp+7h] BYREF
  PCWSTR SourceString[3]; // [rsp+C8h] [rbp+Fh] BYREF
  unsigned __int64 v22; // [rsp+E0h] [rbp+27h]
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v14[0] = a1;
  std::wstring::wstring(SourceString);
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  SymLinkObjHandle = 0;
  v19 = 0;
  v4 = 200;
  DataWritten = 0;
  LinkTarget = 0;
  v5 = ComputeService::ContainerUtilities::Details::SubstituteGlobalPrefix(v15, a2);
  std::wstring::operator=(SourceString, v5);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v15);
  v6 = (const WCHAR *)SourceString;
  if ( v22 > 7 )
    v6 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v6);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = SourceString;
  if ( v22 > 7 )
    v7 = (PCWSTR *)SourceString[0];
  v8 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&SymLinkObjHandle);
  v9 = NtOpenSymbolicLinkObject(v8, 1u, &ObjectAttributes);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
    (const char *)v9,
    (int)"Symlink: %ws",
    (const char *)v7);
  do
  {
    v10 = std::make_unique<unsigned short [0],0>(v14, v4);
    std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(&v19, v10);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v14);
    v4 *= 2;
    DataWritten = v4;
    *(_QWORD *)&LinkTarget.Length = 0;
    LinkTarget.MaximumLength = v4;
    LinkTarget.Buffer = v19;
    v11 = NtQuerySymbolicLinkObject(SymLinkObjHandle, &LinkTarget, &DataWritten);
  }
  while ( v11 == -1073741789 );
  v12 = SourceString;
  if ( v22 > 7 )
    v12 = (PCWSTR *)SourceString[0];
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x140,
    (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
    (const char *)v11,
    (int)"Symlink: %ws Status: %x",
    (const char *)v12,
    v11);
  std::wstring::wstring(a1, LinkTarget.Buffer, (unsigned __int64)LinkTarget.Length >> 1);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v19);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&SymLinkObjHandle);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)SourceString);
  return a1;
}

```

## disassembly

```asm
0x14021565c  mov     [rsp-8+arg_10], rbx
0x140215661  push    rbp
0x140215662  push    rsi
0x140215663  push    rdi
0x140215664  lea     rbp, [rsp-47h]
0x140215669  sub     rsp, 100h
0x140215670  mov     rax, cs:__security_cookie
0x140215677  xor     rax, rsp
0x14021567a  mov     [rbp+57h+var_18], rax
0x14021567e  mov     rbx, rdx
0x140215681  mov     rsi, rcx
0x140215684  mov     [rbp+57h+var_D0], rcx
0x140215688  lea     rcx, [rbp+57h+SourceString]; void *
0x14021568c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140215691  nop
0x140215692  xorps   xmm0, xmm0
0x140215695  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140215699  xorps   xmm1, xmm1
0x14021569c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1402156a0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1402156a4  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1402156a8  mov     [rbp+57h+SymLinkObjHandle], 0
0x1402156b0  mov     [rbp+57h+var_58], 0
0x1402156b8  mov     edi, 0C8h
0x1402156bd  mov     [rbp+57h+DataWritten], 0
0x1402156c4  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1402156c8  mov     rdx, rbx
0x1402156cb  lea     rcx, [rbp+57h+var_C0]
0x1402156cf  call    ?SubstituteGlobalPrefix@Details@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; ComputeService::ContainerUtilities::Details::SubstituteGlobalPrefix(std::wstring const &)
0x1402156d4  mov     rdx, rax
0x1402156d7  lea     rcx, [rbp+57h+SourceString]
0x1402156db  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1402156e0  lea     rcx, [rbp+57h+var_C0]; this
0x1402156e4  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1402156e9  lea     rdx, [rbp+57h+SourceString]
0x1402156ed  cmp     [rbp+57h+var_30], 7
0x1402156f2  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x1402156f7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1402156fb  call    cs:__imp_RtlInitUnicodeString
0x140215702  nop     dword ptr [rax+rax+00h]
0x140215707  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14021570e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140215716  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14021571d  lea     rax, [rbp+57h+DestinationString]
0x140215721  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140215725  xorps   xmm0, xmm0
0x140215728  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14021572d  lea     rbx, [rbp+57h+SourceString]
0x140215731  cmp     [rbp+57h+var_30], 7
0x140215736  cmova   rbx, [rbp+57h+SourceString]
0x14021573b  lea     rcx, [rbp+57h+SymLinkObjHandle]
0x14021573f  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140215744  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140215748  mov     edx, 1; DesiredAccess
0x14021574d  mov     rcx, rax; SymbolicLinkHandle
0x140215750  call    cs:__imp_NtOpenSymbolicLinkObject
0x140215757  nop     dword ptr [rax+rax+00h]
0x14021575c  mov     rcx, [rbp+5Fh]; this
0x140215760  mov     [rsp+110h+var_E8], rbx; char *
0x140215765  lea     rdx, aSymlinkWs; "Symlink: %ws"
0x14021576c  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x140215771  mov     r9d, eax; char *
0x140215774  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x14021577b  lea     edx, [rdi+65h]; void *
0x14021577e  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140215783  mov     edx, edi
0x140215785  lea     rcx, [rbp+57h+var_D0]
0x140215789  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x14021578e  mov     rdx, rax
0x140215791  lea     rcx, [rbp+57h+var_58]
0x140215795  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x14021579a  lea     rcx, [rbp+57h+var_D0]
0x14021579e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1402157a3  add     edi, edi
0x1402157a5  mov     [rbp+57h+DataWritten], edi
0x1402157a8  xorps   xmm0, xmm0
0x1402157ab  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x1402157af  mov     [rbp+57h+LinkTarget.MaximumLength], di
0x1402157b3  mov     rax, [rbp+57h+var_58]
0x1402157b7  mov     [rbp+57h+LinkTarget.Buffer], rax
0x1402157bb  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x1402157bf  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x1402157c3  mov     rcx, [rbp+57h+SymLinkObjHandle]; SymLinkObjHandle
0x1402157c7  call    cs:__imp_NtQuerySymbolicLinkObject
0x1402157ce  nop     dword ptr [rax+rax+00h]
0x1402157d3  cmp     eax, 0C0000023h
0x1402157d8  jz      short loc_140215783
0x1402157da  lea     rdx, [rbp+57h+SourceString]
0x1402157de  cmp     [rbp+57h+var_30], 7
0x1402157e3  cmova   rdx, [rbp+57h+SourceString]
0x1402157e8  mov     rcx, [rbp+5Fh]; this
0x1402157ec  mov     [rsp+110h+var_E0], eax
0x1402157f0  mov     [rsp+110h+var_E8], rdx; char *
0x1402157f5  lea     rdx, aSymlinkWsStatu; "Symlink: %ws Status: %x"
0x1402157fc  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x140215801  mov     r9d, eax; char *
0x140215804  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x14021580b  mov     edx, 140h; void *
0x140215810  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140215815  movzx   r8d, [rbp+57h+LinkTarget.Length]
0x14021581a  shr     r8, 1
0x14021581d  mov     rdx, [rbp+57h+LinkTarget.Buffer]
0x140215821  mov     rcx, rsi
0x140215824  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x140215829  nop
0x14021582a  lea     rcx, [rbp+57h+var_58]
0x14021582e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x140215833  nop
0x140215834  lea     rcx, [rbp+57h+SymLinkObjHandle]; void *
0x140215838  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14021583d  nop
0x14021583e  lea     rcx, [rbp+57h+SourceString]; this
0x140215842  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140215847  mov     rax, rsi
0x14021584a  mov     rcx, [rbp+57h+var_18]
0x14021584e  xor     rcx, rsp; StackCookie
0x140215851  call    __security_check_cookie
0x140215856  mov     rbx, [rsp+110h+arg_10]
0x14021585e  add     rsp, 100h
0x140215865  pop     rdi
0x140215866  pop     rsi
0x140215867  pop     rbp
0x140215868  retn
```
