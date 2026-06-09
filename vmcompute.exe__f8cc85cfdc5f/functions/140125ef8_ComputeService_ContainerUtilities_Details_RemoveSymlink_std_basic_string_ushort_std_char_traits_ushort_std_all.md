# ComputeService::ContainerUtilities::Details::RemoveSymlink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x140125ef8`
- end: `0x14012604e`
- name: `?RemoveSymlink@Details@ContainerUtilities@ComputeService@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(Schema::Responses::System::CrashReportProcessDump *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1402159ac`

## callees

- `0x140017040`
- `0x140024030`
- `0x140042468`
- `0x140125ef8`
- `0x140126054`
- `0x1401332f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140125f4f`
- `ntdll!RtlInitUnicodeString` at `0x140125f4f`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140125f96`
- `ntdll!NtOpenSymbolicLinkObject` at `0x140125f96`
- `ntdll!NtMakeTemporaryObject` at `0x140125ff4`
- `ntdll!NtMakeTemporaryObject` at `0x140125ff4`

## string_xrefs

- `0x140125fd0`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140126011`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x140125fc4`: `Symlink: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputeService::ContainerUtilities::Details::RemoveSymlink(
        Schema::Responses::System::CrashReportProcessDump *this)
{
  const WCHAR *v2; // rdx
  void **v3; // rax
  unsigned int v4; // eax
  const char *v5; // r9
  const char *v6; // rax
  const char *v7; // rdi
  unsigned int TemporaryObject; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-29h] BYREF
  Schema::Responses::System::CrashReportProcessDump *v10; // [rsp+60h] [rbp+7h]
  HANDLE Handle; // [rsp+68h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v10 = this;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Handle = 0;
  if ( *((_QWORD *)this + 3) <= 7u )
    v2 = (const WCHAR *)this;
  else
    v2 = *(const WCHAR **)this;
  RtlInitUnicodeString(&DestinationString, v2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&Handle);
  v4 = NtOpenSymbolicLinkObject(v3, 0x10000u, &ObjectAttributes);
  v5 = (const char *)v4;
  if ( v4 != -1073741772 )
  {
    if ( *((_QWORD *)this + 3) <= 7u )
      v6 = (const char *)this;
    else
      v6 = *(const char **)this;
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      v5,
      (int)"Symlink: %ws",
      v6,
      *(_QWORD *)&ObjectAttributes.Length,
      ObjectAttributes.RootDirectory,
      ObjectAttributes.ObjectName,
      *(_QWORD *)&ObjectAttributes.Attributes,
      ObjectAttributes.SecurityDescriptor);
    if ( *((_QWORD *)this + 3) <= 7u )
      v7 = (const char *)this;
    else
      v7 = *(const char **)this;
    TemporaryObject = NtMakeTemporaryObject(Handle);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)TemporaryObject,
      (int)"Symlink: %ws",
      v7);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Handle);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(this);
}

```

## disassembly

```asm
0x140125ef8  push    rbp
0x140125efa  push    rbx
0x140125efb  push    rsi
0x140125efc  push    rdi
0x140125efd  lea     rbp, [rsp-3Fh]
0x140125f02  sub     rsp, 98h
0x140125f09  mov     rax, cs:__security_cookie
0x140125f10  xor     rax, rsp
0x140125f13  mov     [rbp+57h+var_30], rax
0x140125f17  mov     rbx, rcx
0x140125f1a  mov     [rbp+57h+var_50], rcx
0x140125f1e  xorps   xmm0, xmm0
0x140125f21  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140125f25  xorps   xmm1, xmm1
0x140125f28  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x140125f2c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x140125f30  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x140125f34  mov     [rbp+57h+Handle], 0
0x140125f3c  cmp     qword ptr [rcx+18h], 7
0x140125f41  jbe     short loc_140125F48
0x140125f43  mov     rdx, [rcx]
0x140125f46  jmp     short loc_140125F4B
0x140125f48  mov     rdx, rbx; SourceString
0x140125f4b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140125f4f  call    cs:__imp_RtlInitUnicodeString
0x140125f56  nop     dword ptr [rax+rax+00h]
0x140125f5b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140125f62  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140125f6a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x140125f71  lea     rax, [rbp+57h+DestinationString]
0x140125f75  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140125f79  xorps   xmm0, xmm0
0x140125f7c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140125f81  lea     rcx, [rbp+57h+Handle]
0x140125f85  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x140125f8a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140125f8e  mov     edx, 10000h; DesiredAccess
0x140125f93  mov     rcx, rax; SymbolicLinkHandle
0x140125f96  call    cs:__imp_NtOpenSymbolicLinkObject
0x140125f9d  nop     dword ptr [rax+rax+00h]
0x140125fa2  mov     r9d, eax; char *
0x140125fa5  cmp     eax, 0C0000034h
0x140125faa  jz      short loc_140126023
0x140125fac  cmp     qword ptr [rbx+18h], 7
0x140125fb1  jbe     short loc_140125FB8
0x140125fb3  mov     rax, [rbx]
0x140125fb6  jmp     short loc_140125FBB
0x140125fb8  mov     rax, rbx
0x140125fbb  mov     rcx, [rbp+5Fh]; this
0x140125fbf  mov     [rsp+0B0h+var_88], rax; char *
0x140125fc4  lea     rsi, aSymlinkWs; "Symlink: %ws"
0x140125fcb  mov     qword ptr [rsp+0B0h+var_90], rsi; int
0x140125fd0  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x140125fd7  mov     edx, 1B6h; void *
0x140125fdc  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140125fe1  cmp     qword ptr [rbx+18h], 7
0x140125fe6  jbe     short loc_140125FED
0x140125fe8  mov     rdi, [rbx]
0x140125feb  jmp     short loc_140125FF0
0x140125fed  mov     rdi, rbx
0x140125ff0  mov     rcx, [rbp+57h+Handle]; Handle
0x140125ff4  call    cs:__imp_NtMakeTemporaryObject
0x140125ffb  nop     dword ptr [rax+rax+00h]
0x140126000  mov     rcx, [rbp+5Fh]; this
0x140126004  mov     [rsp+0B0h+var_88], rdi; char *
0x140126009  mov     qword ptr [rsp+0B0h+var_90], rsi; int
0x14012600e  mov     r9d, eax; char *
0x140126011  lea     r8, aOnecoreVmCompu_146; "onecore\\vm\\compute\\management\\share"...
0x140126018  mov     edx, 1BAh; void *
0x14012601d  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x140126022  nop
0x140126023  lea     rcx, [rbp+57h+Handle]; void *
0x140126027  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14012602c  nop
0x14012602d  mov     rcx, rbx; this
0x140126030  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140126035  mov     rcx, [rbp+57h+var_30]
0x140126039  xor     rcx, rsp; StackCookie
0x14012603c  call    __security_check_cookie
0x140126041  add     rsp, 98h
0x140126048  pop     rdi
0x140126049  pop     rsi
0x14012604a  pop     rbx
0x14012604b  pop     rbp
0x14012604c  retn
```
