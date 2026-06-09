# ComputeService::ContainerUtilities::Details::CreateSymlink(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1400d3c44`
- end: `0x1400d3e53`
- name: `?CreateSymlink@Details@ContainerUtilities@ComputeService@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_N@Z`
- size: `527`
- prototype: `__int64 __fastcall(char *, PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d33f4`

## callees

- `0x140005360`
- `0x14004161c`
- `0x1400d3c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3d58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d3d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3cfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d3d45`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d3d29`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1400d3d29`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d3dec`
- `ntdll!NtSetInformationSymbolicLink` at `0x1400d3dec`
- `ntdll!RtlInitUnicodeString` at `0x1400d3ca8`
- `ntdll!RtlInitUnicodeString` at `0x1400d3cc1`
- `ntdll!RtlInitUnicodeString` at `0x1400d3ca8`
- `ntdll!RtlInitUnicodeString` at `0x1400d3cc1`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d3d90`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d3d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3e2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3d06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d3e2a`

## string_xrefs

- `0x1400d3db3`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d3e0a`: `onecore\vm\compute\management\shared\container\containerutilities.cpp`
- `0x1400d3dfb`: `Symlink: %ws`
- `0x1400d3da4`: `Symlink: %ws => %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ComputeService::ContainerUtilities::Details::CreateSymlink(char *a1, PCWSTR SourceString, char a3)
{
  char *v5; // rdi
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rdx
  DWORD LastError; // ebx
  HANDLE v9; // r14
  DWORD v10; // ebx
  const char *v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  int result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-9h] BYREF
  int v17; // [rsp+78h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+7h] BYREF
  struct _UNICODE_STRING Name; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = a1;
  DestinationString = 0;
  Name = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  hObject = 0;
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v6 = (const WCHAR *)a1;
  else
    v6 = *(const WCHAR **)a1;
  RtlInitUnicodeString(&DestinationString, v6);
  if ( *((_QWORD *)SourceString + 3) <= 7u )
    v7 = SourceString;
  else
    v7 = *(const WCHAR **)SourceString;
  RtlInitUnicodeString(&Name, v7);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 80;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(hObject);
    SetLastError(LastError);
  }
  hObject = 0;
  if ( NtOpenSymbolicLinkObject(&hObject, 0x80000000, &ObjectAttributes) < 0 )
  {
    v9 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v10 = GetLastError();
      CloseHandle(v9);
      SetLastError(v10);
    }
    if ( *((_QWORD *)SourceString + 3) > 7u )
      SourceString = *(PCWSTR *)SourceString;
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v11 = v5;
    else
      v11 = *(const char **)v5;
    hObject = 0;
    v12 = NtCreateSymbolicLinkObject(&hObject, 0xFFFFFu, &ObjectAttributes, &Name);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
      (const char *)v12,
      (int)"Symlink: %ws => %ws",
      v11,
      SourceString);
    if ( a3 )
    {
      v17 = 0;
      if ( *((_QWORD *)v5 + 3) > 7u )
        v5 = *(char **)v5;
      v13 = NtSetInformationSymbolicLink(hObject, 1, &v17, 4);
      wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerutilities.cpp",
        (const char *)v13,
        (int)"Symlink: %ws",
        v5);
    }
  }
  result = (_DWORD)hObject - 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return CloseHandle(hObject);
  return result;
}

```

## disassembly

```asm
0x1400d3c44  mov     [rsp-8+arg_10], rbx
0x1400d3c49  push    rbp
0x1400d3c4a  push    rsi
0x1400d3c4b  push    rdi
0x1400d3c4c  push    r14
0x1400d3c4e  push    r15
0x1400d3c50  lea     rbp, [rsp-37h]
0x1400d3c55  sub     rsp, 0B0h
0x1400d3c5c  mov     rax, cs:__security_cookie
0x1400d3c63  xor     rax, rsp
0x1400d3c66  mov     [rbp+57h+var_30], rax
0x1400d3c6a  mov     r15b, r8b
0x1400d3c6d  mov     rsi, rdx
0x1400d3c70  mov     rdi, rcx
0x1400d3c73  xorps   xmm0, xmm0
0x1400d3c76  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d3c7a  xorps   xmm1, xmm1
0x1400d3c7d  movups  xmmword ptr [rbp+57h+Name.Length], xmm1
0x1400d3c81  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400d3c85  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400d3c89  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d3c8d  mov     [rbp+57h+hObject], 0
0x1400d3c95  cmp     qword ptr [rcx+18h], 7
0x1400d3c9a  jbe     short loc_1400D3CA1
0x1400d3c9c  mov     rdx, [rcx]
0x1400d3c9f  jmp     short loc_1400D3CA4
0x1400d3ca1  mov     rdx, rdi; SourceString
0x1400d3ca4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d3ca8  call    cs:__imp_RtlInitUnicodeString
0x1400d3cae  cmp     qword ptr [rsi+18h], 7
0x1400d3cb3  jbe     short loc_1400D3CBA
0x1400d3cb5  mov     rdx, [rsi]
0x1400d3cb8  jmp     short loc_1400D3CBD
0x1400d3cba  mov     rdx, rsi; SourceString
0x1400d3cbd  lea     rcx, [rbp+57h+Name]; DestinationString
0x1400d3cc1  call    cs:__imp_RtlInitUnicodeString
0x1400d3cc7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d3cce  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d3cd6  mov     [rbp+57h+ObjectAttributes.Attributes], 50h ; 'P'
0x1400d3cdd  lea     rax, [rbp+57h+DestinationString]
0x1400d3ce1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d3ce5  xorps   xmm0, xmm0
0x1400d3ce8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d3ced  mov     r14, [rbp+57h+hObject]
0x1400d3cf1  lea     rax, [r14-1]
0x1400d3cf5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d3cf9  ja      short loc_1400D3D14
0x1400d3cfb  call    cs:__imp_GetLastError
0x1400d3d01  mov     ebx, eax
0x1400d3d03  mov     rcx, r14; hObject
0x1400d3d06  call    cs:__imp_CloseHandle
0x1400d3d0c  mov     ecx, ebx; dwErrCode
0x1400d3d0e  call    cs:__imp_SetLastError
0x1400d3d14  mov     [rbp+57h+hObject], 0
0x1400d3d1c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d3d20  mov     edx, 80000000h; DesiredAccess
0x1400d3d25  lea     rcx, [rbp+57h+hObject]; SymbolicLinkHandle
0x1400d3d29  call    cs:__imp_NtOpenSymbolicLinkObject
0x1400d3d2f  test    eax, eax
0x1400d3d31  jns     loc_1400D3E1C
0x1400d3d37  mov     r14, [rbp+57h+hObject]
0x1400d3d3b  lea     rax, [r14-1]
0x1400d3d3f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d3d43  ja      short loc_1400D3D5E
0x1400d3d45  call    cs:__imp_GetLastError
0x1400d3d4b  mov     ebx, eax
0x1400d3d4d  mov     rcx, r14; hObject
0x1400d3d50  call    cs:__imp_CloseHandle
0x1400d3d56  mov     ecx, ebx; dwErrCode
0x1400d3d58  call    cs:__imp_SetLastError
0x1400d3d5e  cmp     qword ptr [rsi+18h], 7
0x1400d3d63  jbe     short loc_1400D3D68
0x1400d3d65  mov     rsi, [rsi]
0x1400d3d68  cmp     qword ptr [rdi+18h], 7
0x1400d3d6d  jbe     short loc_1400D3D74
0x1400d3d6f  mov     rbx, [rdi]
0x1400d3d72  jmp     short loc_1400D3D77
0x1400d3d74  mov     rbx, rdi
0x1400d3d77  mov     [rbp+57h+hObject], 0
0x1400d3d7f  lea     r9, [rbp+57h+Name]; Name
0x1400d3d83  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d3d87  mov     edx, 0FFFFFh; DesiredAccess
0x1400d3d8c  lea     rcx, [rbp+57h+hObject]; SymbolicLinkHandle
0x1400d3d90  call    cs:__imp_NtCreateSymbolicLinkObject
0x1400d3d96  mov     rcx, [rbp+5Fh]; this
0x1400d3d9a  mov     [rsp+0D0h+var_A0], rsi
0x1400d3d9f  mov     [rsp+0D0h+var_A8], rbx; char *
0x1400d3da4  lea     rdx, aSymlinkWsWs; "Symlink: %ws => %ws"
0x1400d3dab  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x1400d3db0  mov     r9d, eax; char *
0x1400d3db3  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d3dba  mov     edx, 18Bh; void *
0x1400d3dbf  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d3dc4  test    r15b, r15b
0x1400d3dc7  jz      short loc_1400D3E1C
0x1400d3dc9  mov     [rbp+57h+var_58], 0
0x1400d3dd0  cmp     qword ptr [rdi+18h], 7
0x1400d3dd5  jbe     short loc_1400D3DDA
0x1400d3dd7  mov     rdi, [rdi]
0x1400d3dda  mov     r9d, 4
0x1400d3de0  lea     r8, [rbp+57h+var_58]
0x1400d3de4  lea     edx, [r9-3]
0x1400d3de8  mov     rcx, [rbp+57h+hObject]
0x1400d3dec  call    cs:__imp_NtSetInformationSymbolicLink
0x1400d3df2  mov     rcx, [rbp+5Fh]; this
0x1400d3df6  mov     [rsp+0D0h+var_A8], rdi; char *
0x1400d3dfb  lea     rdx, aSymlinkWs; "Symlink: %ws"
0x1400d3e02  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x1400d3e07  mov     r9d, eax; char *
0x1400d3e0a  lea     r8, aOnecoreVmCompu_52; "onecore\\vm\\compute\\management\\share"...
0x1400d3e11  mov     edx, 193h; void *
0x1400d3e16  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400d3e1b  nop
0x1400d3e1c  mov     rcx, [rbp+57h+hObject]; hObject
0x1400d3e20  lea     rax, [rcx-1]
0x1400d3e24  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d3e28  ja      short loc_1400D3E30
0x1400d3e2a  call    cs:__imp_CloseHandle
0x1400d3e30  mov     rcx, [rbp+57h+var_30]
0x1400d3e34  xor     rcx, rsp; StackCookie
0x1400d3e37  call    __security_check_cookie
0x1400d3e3c  mov     rbx, [rsp+0D0h+arg_10]
0x1400d3e44  add     rsp, 0B0h
0x1400d3e4b  pop     r15
0x1400d3e4d  pop     r14
0x1400d3e4f  pop     rdi
0x1400d3e50  pop     rsi
0x1400d3e51  pop     rbp
0x1400d3e52  retn
```
