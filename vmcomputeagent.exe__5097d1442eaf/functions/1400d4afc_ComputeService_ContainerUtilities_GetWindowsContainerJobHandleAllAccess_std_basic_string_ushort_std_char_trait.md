# ComputeService::ContainerUtilities::GetWindowsContainerJobHandleAllAccess(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400d4afc`
- end: `0x1400d4c1a`
- name: `?GetWindowsContainerJobHandleAllAccess@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(PHANDLE JobHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14008c5c0`

## callees

- `0x140005360`
- `0x140008760`
- `0x140044adc`
- `0x1400d4afc`
- `0x1400d4d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4bb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4ba0`
- `ntdll!RtlInitUnicodeString` at `0x1400d4b67`
- `ntdll!RtlInitUnicodeString` at `0x1400d4b67`
- `ntdll!NtOpenJobObject` at `0x1400d4bcc`
- `ntdll!NtOpenJobObject` at `0x1400d4bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4bab`

## string_xrefs

- `0x1400d4c08`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHANDLE __fastcall ComputeService::ContainerUtilities::GetWindowsContainerJobHandleAllAccess(
        PHANDLE JobHandle,
        __int64 a2)
{
  const WCHAR *v3; // rdx
  void *v4; // rsi
  DWORD LastError; // ebx
  NTSTATUS v6; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  PCWSTR SourceString[4]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  *JobHandle = 0;
  ComputeService::ContainerUtilities::GetWindowsContainerJobName(SourceString, a2);
  v3 = (const WCHAR *)SourceString;
  if ( SourceString[3] > (PCWSTR)7 )
    v3 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = *JobHandle;
  if ( (char *)*JobHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  *JobHandle = 0;
  v6 = NtOpenJobObject(JobHandle, 0x1F003Fu, &ObjectAttributes);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x215,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v6,
      1);
  std::wstring::~wstring(SourceString);
  return JobHandle;
}

```

## disassembly

```asm
0x1400d4afc  mov     [rsp-8+arg_10], rbx
0x1400d4b01  push    rbp
0x1400d4b02  push    rsi
0x1400d4b03  push    rdi
0x1400d4b04  lea     rbp, [rsp-47h]
0x1400d4b09  sub     rsp, 0A0h
0x1400d4b10  mov     rax, cs:__security_cookie
0x1400d4b17  xor     rax, rsp
0x1400d4b1a  mov     [rbp+57h+var_20], rax
0x1400d4b1e  mov     rdi, rcx
0x1400d4b21  mov     [rbp+57h+var_88], rcx
0x1400d4b25  mov     [rbp+57h+var_90], 0
0x1400d4b2c  xorps   xmm0, xmm0
0x1400d4b2f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400d4b33  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400d4b37  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d4b3b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d4b3f  xor     eax, eax
0x1400d4b41  mov     [rcx], rax
0x1400d4b44  mov     [rbp+57h+var_90], 1
0x1400d4b4b  lea     rcx, [rbp+57h+SourceString]
0x1400d4b4f  call    ?GetWindowsContainerJobName@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::ContainerUtilities::GetWindowsContainerJobName(std::wstring const &)
0x1400d4b54  nop
0x1400d4b55  lea     rdx, [rbp+57h+SourceString]
0x1400d4b59  cmp     [rbp+57h+var_28], 7
0x1400d4b5e  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x1400d4b63  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d4b67  call    cs:__imp_RtlInitUnicodeString
0x1400d4b6d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d4b74  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d4b7c  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1400d4b83  lea     rax, [rbp+57h+DestinationString]
0x1400d4b87  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d4b8b  xorps   xmm0, xmm0
0x1400d4b8e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d4b93  mov     rsi, [rdi]
0x1400d4b96  lea     rax, [rsi-1]
0x1400d4b9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d4b9e  ja      short loc_1400D4BB9
0x1400d4ba0  call    cs:__imp_GetLastError
0x1400d4ba6  mov     ebx, eax
0x1400d4ba8  mov     rcx, rsi; hObject
0x1400d4bab  call    cs:__imp_CloseHandle
0x1400d4bb1  mov     ecx, ebx; dwErrCode
0x1400d4bb3  call    cs:__imp_SetLastError
0x1400d4bb9  mov     qword ptr [rdi], 0
0x1400d4bc0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d4bc4  mov     edx, 1F003Fh; DesiredAccess
0x1400d4bc9  mov     rcx, rdi; JobHandle
0x1400d4bcc  call    cs:__imp_NtOpenJobObject
0x1400d4bd2  mov     rcx, [rbp+5Fh]; this
0x1400d4bd6  test    eax, eax
0x1400d4bd8  js      short loc_1400D4C05
0x1400d4bda  lea     rcx, [rbp+57h+SourceString]; void *
0x1400d4bde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d4be3  mov     rax, rdi
0x1400d4be6  mov     rcx, [rbp+57h+var_20]
0x1400d4bea  xor     rcx, rsp; StackCookie
0x1400d4bed  call    __security_check_cookie
0x1400d4bf2  mov     rbx, [rsp+0B0h+arg_10]
0x1400d4bfa  add     rsp, 0A0h
0x1400d4c01  pop     rdi
0x1400d4c02  pop     rsi
0x1400d4c03  pop     rbp
0x1400d4c04  retn
0x1400d4c05  mov     r9d, eax; char *
0x1400d4c08  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d4c0f  mov     edx, 215h; void *
0x1400d4c14  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
