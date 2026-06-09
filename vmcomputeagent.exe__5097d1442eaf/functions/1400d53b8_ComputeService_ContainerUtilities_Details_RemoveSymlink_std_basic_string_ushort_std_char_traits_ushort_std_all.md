# ComputeService::ContainerUtilities::Details::RemoveSymlink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1400d53b8`
- end: `0x1400d552d`
- name: `?RemoveSymlink@Details@ContainerUtilities@ComputeService@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d5124`

## callees

- `0x140005360`
- `0x140008760`
- `0x14004161c`
- `0x1400d53b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d545c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d545c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d5449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d5449`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d5477`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d5477`
- `ntdll!RtlInitUnicodeString` at `0x1400d540f`
- `ntdll!RtlInitUnicodeString` at `0x1400d540f`
- `ntdll!NtMakeTemporaryObject` at `0x1400d54cf`
- `ntdll!NtMakeTemporaryObject` at `0x1400d54cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5454`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d5506`

## string_xrefs

- `0x1400d54ab`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d54e6`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d549f`: `Symlink: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ComputeService::ContainerUtilities::Details::RemoveSymlink(_QWORD *a1)
{
  const WCHAR *v2; // rdx
  DWORD LastError; // ebx
  unsigned int v4; // eax
  const char *v5; // r9
  const char *v6; // rax
  const char *v7; // rbx
  unsigned int TemporaryObject; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v10; // [rsp+60h] [rbp+7h]
  HANDLE hObject; // [rsp+68h] [rbp+Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v10 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  hObject = 0;
  if ( a1[3] <= 7u )
    v2 = (const WCHAR *)a1;
  else
    v2 = (const WCHAR *)*a1;
  RtlInitUnicodeString(&DestinationString, v2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(hObject);
    SetLastError(LastError);
  }
  hObject = 0;
  v4 = NtOpenSymbolicLinkObject(&hObject, 0x10000u, &ObjectAttributes);
  v5 = (const char *)v4;
  if ( v4 != -1073741772 )
  {
    if ( a1[3] <= 7u )
      v6 = (const char *)a1;
    else
      v6 = (const char *)*a1;
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
      ObjectAttributes.SecurityDescriptor,
      ObjectAttributes.SecurityQualityOfService,
      v10);
    if ( a1[3] <= 7u )
      v7 = (const char *)a1;
    else
      v7 = (const char *)*a1;
    TemporaryObject = NtMakeTemporaryObject(hObject);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x1BA,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)TemporaryObject,
      (int)"Symlink: %ws",
      v7);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  std::wstring::~wstring(a1);
}

```

## disassembly

```asm
0x1400d53b8  push    rbp
0x1400d53ba  push    rbx
0x1400d53bb  push    rsi
0x1400d53bc  push    rdi
0x1400d53bd  lea     rbp, [rsp-3Fh]
0x1400d53c2  sub     rsp, 98h
0x1400d53c9  mov     rax, cs:__security_cookie
0x1400d53d0  xor     rax, rsp
0x1400d53d3  mov     [rbp+57h+var_30], rax
0x1400d53d7  mov     rdi, rcx
0x1400d53da  mov     [rbp+57h+var_50], rcx
0x1400d53de  xorps   xmm0, xmm0
0x1400d53e1  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d53e5  xorps   xmm1, xmm1
0x1400d53e8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1400d53ec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1400d53f0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1400d53f4  mov     [rbp+57h+hObject], 0
0x1400d53fc  cmp     qword ptr [rcx+18h], 7
0x1400d5401  jbe     short loc_1400D5408
0x1400d5403  mov     rdx, [rcx]
0x1400d5406  jmp     short loc_1400D540B
0x1400d5408  mov     rdx, rdi; SourceString
0x1400d540b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d540f  call    cs:__imp_RtlInitUnicodeString
0x1400d5415  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d541c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d5424  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400d542b  lea     rax, [rbp+57h+DestinationString]
0x1400d542f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d5433  xorps   xmm0, xmm0
0x1400d5436  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d543b  mov     rsi, [rbp+57h+hObject]
0x1400d543f  lea     rax, [rsi-1]
0x1400d5443  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d5447  ja      short loc_1400D5462
0x1400d5449  call    cs:__imp_GetLastError
0x1400d544f  mov     ebx, eax
0x1400d5451  mov     rcx, rsi; hObject
0x1400d5454  call    cs:__imp_CloseHandle
0x1400d545a  mov     ecx, ebx; dwErrCode
0x1400d545c  call    cs:__imp_SetLastError
0x1400d5462  mov     [rbp+57h+hObject], 0
0x1400d546a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d546e  mov     edx, 10000h; DesiredAccess
0x1400d5473  lea     rcx, [rbp+57h+hObject]; SymbolicLinkHandle
0x1400d5477  call    cs:__imp_NtOpenSymbolicLinkObject
0x1400d547d  mov     r9d, eax; char *
0x1400d5480  cmp     eax, 0C0000034h
0x1400d5485  jz      short loc_1400D54F8
0x1400d5487  cmp     qword ptr [rdi+18h], 7
0x1400d548c  jbe     short loc_1400D5493
0x1400d548e  mov     rax, [rdi]
0x1400d5491  jmp     short loc_1400D5496
0x1400d5493  mov     rax, rdi
0x1400d5496  mov     rcx, [rbp+5Fh]; this
0x1400d549a  mov     [rsp+0B0h+var_88], rax; char *
0x1400d549f  lea     rsi, aSymlinkWs; "Symlink: %ws"
0x1400d54a6  mov     qword ptr [rsp+0B0h+var_90], rsi; int
0x1400d54ab  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d54b2  mov     edx, 1B6h; void *
0x1400d54b7  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d54bc  cmp     qword ptr [rdi+18h], 7
0x1400d54c1  jbe     short loc_1400D54C8
0x1400d54c3  mov     rbx, [rdi]
0x1400d54c6  jmp     short loc_1400D54CB
0x1400d54c8  mov     rbx, rdi
0x1400d54cb  mov     rcx, [rbp+57h+hObject]; Handle
0x1400d54cf  call    cs:__imp_NtMakeTemporaryObject
0x1400d54d5  mov     rcx, [rbp+5Fh]; this
0x1400d54d9  mov     [rsp+0B0h+var_88], rbx; char *
0x1400d54de  mov     qword ptr [rsp+0B0h+var_90], rsi; int
0x1400d54e3  mov     r9d, eax; char *
0x1400d54e6  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d54ed  mov     edx, 1BAh; void *
0x1400d54f2  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d54f7  nop
0x1400d54f8  mov     rcx, [rbp+57h+hObject]; hObject
0x1400d54fc  lea     rax, [rcx-1]
0x1400d5500  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d5504  ja      short loc_1400D550D
0x1400d5506  call    cs:__imp_CloseHandle
0x1400d550c  nop
0x1400d550d  mov     rcx, rdi; void *
0x1400d5510  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d5515  mov     rcx, [rbp+57h+var_30]
0x1400d5519  xor     rcx, rsp; StackCookie
0x1400d551c  call    __security_check_cookie
0x1400d5521  add     rsp, 98h
0x1400d5528  pop     rdi
0x1400d5529  pop     rsi
0x1400d552a  pop     rbx
0x1400d552b  pop     rbp
0x1400d552c  retn
```
