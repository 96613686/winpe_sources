# ComputeService::ContainerUtilities::GetWindowsContainerJobHandleQuery(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400d4c20`
- end: `0x1400d4d3e`
- name: `?GetWindowsContainerJobHandleQuery@ContainerUtilities@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(PHANDLE JobHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140087d00`

## callees

- `0x140005360`
- `0x140008760`
- `0x140044adc`
- `0x1400d4c20`
- `0x1400d4d44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4cd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d4cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4cc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d4cc4`
- `ntdll!RtlInitUnicodeString` at `0x1400d4c8b`
- `ntdll!RtlInitUnicodeString` at `0x1400d4c8b`
- `ntdll!NtOpenJobObject` at `0x1400d4cf0`
- `ntdll!NtOpenJobObject` at `0x1400d4cf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4ccf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d4ccf`

## string_xrefs

- `0x1400d4d2c`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`

## pseudocode

```c
PHANDLE __fastcall ComputeService::ContainerUtilities::GetWindowsContainerJobHandleQuery(PHANDLE JobHandle, __int64 a2)
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
  v6 = NtOpenJobObject(JobHandle, 4u, &ObjectAttributes);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)(unsigned int)v6,
      1);
  std::wstring::~wstring(SourceString);
  return JobHandle;
}

```

## disassembly

```asm
0x1400d4c20  mov     [rsp-8+arg_10], rbx
0x1400d4c25  push    rbp
0x1400d4c26  push    rsi
0x1400d4c27  push    rdi
0x1400d4c28  lea     rbp, [rsp-47h]
0x1400d4c2d  sub     rsp, 0A0h
0x1400d4c34  mov     rax, cs:__security_cookie
0x1400d4c3b  xor     rax, rsp
0x1400d4c3e  mov     [rbp+57h+var_20], rax
0x1400d4c42  mov     rdi, rcx
0x1400d4c45  mov     [rbp+57h+var_88], rcx
0x1400d4c49  mov     [rbp+57h+var_90], 0
0x1400d4c50  xorps   xmm0, xmm0
0x1400d4c53  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400d4c57  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400d4c5b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d4c5f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d4c63  xor     eax, eax
0x1400d4c65  mov     [rcx], rax
0x1400d4c68  mov     [rbp+57h+var_90], 1
0x1400d4c6f  lea     rcx, [rbp+57h+SourceString]
0x1400d4c73  call    ?GetWindowsContainerJobName@ContainerUtilities@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ComputeService::ContainerUtilities::GetWindowsContainerJobName(std::wstring const &)
0x1400d4c78  nop
0x1400d4c79  lea     rdx, [rbp+57h+SourceString]
0x1400d4c7d  cmp     [rbp+57h+var_28], 7
0x1400d4c82  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x1400d4c87  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d4c8b  call    cs:__imp_RtlInitUnicodeString
0x1400d4c91  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d4c98  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d4ca0  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x1400d4ca7  lea     rax, [rbp+57h+DestinationString]
0x1400d4cab  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d4caf  xorps   xmm0, xmm0
0x1400d4cb2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d4cb7  mov     rsi, [rdi]
0x1400d4cba  lea     rax, [rsi-1]
0x1400d4cbe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d4cc2  ja      short loc_1400D4CDD
0x1400d4cc4  call    cs:__imp_GetLastError
0x1400d4cca  mov     ebx, eax
0x1400d4ccc  mov     rcx, rsi; hObject
0x1400d4ccf  call    cs:__imp_CloseHandle
0x1400d4cd5  mov     ecx, ebx; dwErrCode
0x1400d4cd7  call    cs:__imp_SetLastError
0x1400d4cdd  mov     qword ptr [rdi], 0
0x1400d4ce4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d4ce8  mov     edx, 4; DesiredAccess
0x1400d4ced  mov     rcx, rdi; JobHandle
0x1400d4cf0  call    cs:__imp_NtOpenJobObject
0x1400d4cf6  mov     rcx, [rbp+5Fh]; this
0x1400d4cfa  test    eax, eax
0x1400d4cfc  js      short loc_1400D4D29
0x1400d4cfe  lea     rcx, [rbp+57h+SourceString]; void *
0x1400d4d02  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d4d07  mov     rax, rdi
0x1400d4d0a  mov     rcx, [rbp+57h+var_20]
0x1400d4d0e  xor     rcx, rsp; StackCookie
0x1400d4d11  call    __security_check_cookie
0x1400d4d16  mov     rbx, [rsp+0B0h+arg_10]
0x1400d4d1e  add     rsp, 0A0h
0x1400d4d25  pop     rdi
0x1400d4d26  pop     rsi
0x1400d4d27  pop     rbp
0x1400d4d28  retn
0x1400d4d29  mov     r9d, eax; char *
0x1400d4d2c  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d4d33  mov     edx, 1F5h; void *
0x1400d4d38  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
