# ComputeService::ContainerUtilities::_anonymous_namespace_::CreateMappedDirectoryRoot

- ea: `0x1400d9af4`
- end: `0x1400d9ce2`
- name: `ComputeService::ContainerUtilities::_anonymous_namespace_::CreateMappedDirectoryRoot`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d9ce8`

## callees

- `0x140005360`
- `0x140008760`
- `0x14004346c`
- `0x140044adc`
- `0x1400d9af4`

## import_xrefs

- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d9c50`
- `ntdll!NtCreateSymbolicLinkObject` at `0x1400d9c50`
- `ntdll!NtCreateDirectoryObject` at `0x1400d9ba5`
- `ntdll!NtCreateDirectoryObject` at `0x1400d9ba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d9c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d9c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d9c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d9c8b`

## string_xrefs

- `0x1400d9cbb`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`
- `0x1400d9cd0`: `onecore\vm\compute\management\shared\container\containerstorage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void ComputeService::ContainerUtilities::_anonymous_namespace_::CreateMappedDirectoryRoot()
{
  _QWORD *v0; // rax
  NTSTATUS v1; // eax
  _QWORD *v2; // rax
  NTSTATUS v3; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-69h] BYREF
  void *DirectoryHandle[2]; // [rsp+50h] [rbp-39h] BYREF
  void *SymbolicLinkHandle[2]; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING Name; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v8[2]; // [rsp+80h] [rbp-9h] BYREF
  __int64 v9; // [rsp+90h] [rbp+7h]
  unsigned __int64 v10; // [rsp+98h] [rbp+Fh]
  _QWORD Src[2]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v12; // [rsp+B0h] [rbp+27h]
  unsigned __int64 v13; // [rsp+B8h] [rbp+2Fh]
  __int128 v14; // [rsp+C0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  Vml::FormatString(Src, (wchar_t *)L"%s\\ContainerMappedDirectories");
  v0 = Src;
  if ( v13 > 7 )
    v0 = (_QWORD *)Src[0];
  HIWORD(DirectoryHandle[0]) = 0;
  DirectoryHandle[1] = v0;
  LOWORD(DirectoryHandle[0]) = 2 * v12;
  *(_DWORD *)((char *)DirectoryHandle + 2) = (unsigned __int16)(2 * v12);
  Name = *(struct _UNICODE_STRING *)DirectoryHandle;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 80;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &Name;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DirectoryHandle[0] = 0;
  v1 = NtCreateDirectoryObject(DirectoryHandle, 0xF000Fu, &ObjectAttributes);
  if ( v1 != -1073741771 )
  {
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)v1,
        ObjectAttributes.Length);
    Vml::FormatString(v8, (wchar_t *)L"%s\\GLOBAL??\\ContainerMappedDirectories");
    v2 = v8;
    if ( v10 > 7 )
      v2 = (_QWORD *)v8[0];
    HIWORD(SymbolicLinkHandle[0]) = 0;
    SymbolicLinkHandle[1] = v2;
    LOWORD(SymbolicLinkHandle[0]) = 2 * v9;
    *(_DWORD *)((char *)SymbolicLinkHandle + 2) = (unsigned __int16)(2 * v9);
    v14 = *(_OWORD *)SymbolicLinkHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 16;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    SymbolicLinkHandle[0] = 0;
    v3 = NtCreateSymbolicLinkObject(SymbolicLinkHandle, 0xFFFFFu, &ObjectAttributes, &Name);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerstorage.cpp",
        (const char *)(unsigned int)v3,
        ObjectAttributes.Length);
    if ( (unsigned __int64)SymbolicLinkHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(SymbolicLinkHandle[0]);
    std::wstring::~wstring(v8);
  }
  if ( (unsigned __int64)DirectoryHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(DirectoryHandle[0]);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x1400d9af4  mov     [rsp-8+arg_8], rbx
0x1400d9af9  push    rbp
0x1400d9afa  lea     rbp, [rsp-57h]
0x1400d9aff  sub     rsp, 0E0h
0x1400d9b06  mov     rax, cs:__security_cookie
0x1400d9b0d  xor     rax, rsp
0x1400d9b10  mov     [rbp+57h+var_10], rax
0x1400d9b14  mov     rbx, rcx
0x1400d9b17  cmp     qword ptr [rcx+18h], 7
0x1400d9b1c  jbe     short loc_1400D9B23
0x1400d9b1e  mov     r8, [rcx]
0x1400d9b21  jmp     short loc_1400D9B26
0x1400d9b23  mov     r8, rbx
0x1400d9b26  lea     rdx, aSContainermapp; "%s\\ContainerMappedDirectories"
0x1400d9b2d  lea     rcx, [rbp+57h+Src]; Src
0x1400d9b31  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d9b36  nop
0x1400d9b37  lea     rax, [rbp+57h+Src]
0x1400d9b3b  cmp     [rbp+57h+var_28], 7
0x1400d9b40  cmova   rax, [rbp+57h+Src]
0x1400d9b45  mov     rcx, [rbp+57h+var_30]
0x1400d9b49  mov     dword ptr [rbp+57h+DirectoryHandle+4], 0
0x1400d9b50  mov     [rbp+57h+DirectoryHandle+8], rax
0x1400d9b54  add     cx, cx
0x1400d9b57  mov     word ptr [rbp+57h+DirectoryHandle], cx
0x1400d9b5b  mov     word ptr [rbp+57h+DirectoryHandle+2], cx
0x1400d9b5f  movaps  xmm0, xmmword ptr [rbp+57h+DirectoryHandle]
0x1400d9b63  movdqa  xmmword ptr [rbp+57h+Name.Length], xmm0
0x1400d9b68  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d9b70  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 50h ; 'P'
0x1400d9b78  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d9b80  lea     rax, [rbp+57h+Name]
0x1400d9b84  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d9b88  xorps   xmm0, xmm0
0x1400d9b8b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d9b90  mov     [rbp+57h+DirectoryHandle], 0
0x1400d9b98  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d9b9c  mov     edx, 0F000Fh; DesiredAccess
0x1400d9ba1  lea     rcx, [rbp+57h+DirectoryHandle]; DirectoryHandle
0x1400d9ba5  call    cs:__imp_NtCreateDirectoryObject
0x1400d9bab  cmp     eax, 0C0000035h
0x1400d9bb0  jz      loc_1400D9C7D
0x1400d9bb6  mov     rcx, [rbp+5Fh]; this
0x1400d9bba  test    eax, eax
0x1400d9bbc  js      loc_1400D9CCD
0x1400d9bc2  cmp     qword ptr [rbx+18h], 7
0x1400d9bc7  jbe     short loc_1400D9BCC
0x1400d9bc9  mov     rbx, [rbx]
0x1400d9bcc  mov     r8, rbx
0x1400d9bcf  lea     rdx, aSGlobalContain; "%s\\GLOBAL??\\ContainerMappedDirectorie"...
0x1400d9bd6  lea     rcx, [rbp+57h+var_60]; Src
0x1400d9bda  call    ?FormatString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(ushort const *,...)
0x1400d9bdf  nop
0x1400d9be0  lea     rax, [rbp+57h+var_60]
0x1400d9be4  cmp     [rbp+57h+var_48], 7
0x1400d9be9  cmova   rax, [rbp+57h+var_60]
0x1400d9bee  mov     rcx, [rbp+57h+var_50]
0x1400d9bf2  mov     dword ptr [rbp+57h+SymbolicLinkHandle+4], 0
0x1400d9bf9  mov     [rbp+57h+SymbolicLinkHandle+8], rax
0x1400d9bfd  add     cx, cx
0x1400d9c00  mov     word ptr [rbp+57h+SymbolicLinkHandle], cx
0x1400d9c04  mov     word ptr [rbp+57h+SymbolicLinkHandle+2], cx
0x1400d9c08  movaps  xmm0, xmmword ptr [rbp+57h+SymbolicLinkHandle]
0x1400d9c0c  movdqa  [rbp+57h+var_20], xmm0
0x1400d9c11  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400d9c18  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400d9c20  mov     [rbp+57h+ObjectAttributes.Attributes], 10h
0x1400d9c27  lea     rax, [rbp+57h+var_20]
0x1400d9c2b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400d9c2f  xorps   xmm0, xmm0
0x1400d9c32  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d9c37  mov     [rbp+57h+SymbolicLinkHandle], 0
0x1400d9c3f  lea     r9, [rbp+57h+Name]; Name
0x1400d9c43  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400d9c47  mov     edx, 0FFFFFh; DesiredAccess
0x1400d9c4c  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x1400d9c50  call    cs:__imp_NtCreateSymbolicLinkObject
0x1400d9c56  mov     rcx, [rbp+5Fh]; this
0x1400d9c5a  test    eax, eax
0x1400d9c5c  js      short loc_1400D9CB8
0x1400d9c5e  mov     rcx, [rbp+57h+SymbolicLinkHandle]; hObject
0x1400d9c62  lea     rax, [rcx-1]
0x1400d9c66  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d9c6a  ja      short loc_1400D9C73
0x1400d9c6c  call    cs:__imp_CloseHandle
0x1400d9c72  nop
0x1400d9c73  lea     rcx, [rbp+57h+var_60]; void *
0x1400d9c77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9c7c  nop
0x1400d9c7d  mov     rcx, [rbp+57h+DirectoryHandle]; hObject
0x1400d9c81  lea     rax, [rcx-1]
0x1400d9c85  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d9c89  ja      short loc_1400D9C92
0x1400d9c8b  call    cs:__imp_CloseHandle
0x1400d9c91  nop
0x1400d9c92  lea     rcx, [rbp+57h+Src]; void *
0x1400d9c96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400d9c9b  mov     rcx, [rbp+57h+var_10]
0x1400d9c9f  xor     rcx, rsp; StackCookie
0x1400d9ca2  call    __security_check_cookie
0x1400d9ca7  mov     rbx, [rsp+0E0h+arg_8]
0x1400d9caf  add     rsp, 0E0h
0x1400d9cb6  pop     rbp
0x1400d9cb7  retn
0x1400d9cb8  mov     r9d, eax; char *
0x1400d9cbb  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400d9cc2  mov     edx, 57h ; 'W'; void *
0x1400d9cc7  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1400d9ccd  mov     r9d, eax; char *
0x1400d9cd0  lea     r8, aOnecoreVmCompu_40; "onecore\\vm\\compute\\management\\share"...
0x1400d9cd7  mov     edx, 4Ch ; 'L'; void *
0x1400d9cdc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
