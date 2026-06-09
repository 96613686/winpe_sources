# DestroyLayer

- ea: `0x1800359a0`
- end: `0x180035abb`
- name: `DestroyLayer`
- size: `283`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002f50`
- `0x180006660`
- `0x18000d0ec`
- `0x18002f94c`
- `0x18003012c`
- `0x180030498`
- `0x1800359a0`
- `0x1800520b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a1e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180035a0e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180035a0e`

## string_xrefs

- `0x180035aa8`: `onecore\vm\compute\dll\legacy\src\graphdriver.cpp`

## pseudocode

```c
__int64 __fastcall DestroyLayer(__int64 a1, const WCHAR *a2)
{
  LPCWSTR *v4; // rcx
  const WCHAR *v5; // rcx
  const char *v6; // r9
  _QWORD *v8; // rcx
  const unsigned __int16 *v9; // rdx
  ComputeStorageInternal *v10; // rcx
  const char *v11; // r9
  __int64 result; // rax
  _QWORD Src[3]; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-38h]
  LPCWSTR lpFileName[3]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v16; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    anonymous_namespace_::LayerDiskPath(lpFileName);
    Vml::CombineFilePath(Src, *(PCWSTR *)(a1 + 8), a2);
    v4 = lpFileName;
    if ( v16 > 7 )
      v4 = (LPCWSTR *)lpFileName[0];
    if ( (unsigned int)anonymous_namespace_::FileExists(v4) )
    {
      v5 = (const WCHAR *)lpFileName;
      if ( v16 > 7 )
        v5 = lpFileName[0];
      if ( !DeleteFileW(v5) && GetLastError() != 2 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x17B,
          (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
          v6);
    }
    v8 = Src;
    if ( v14 > 7 )
      v8 = (_QWORD *)Src[0];
    if ( (unsigned int)anonymous_namespace_::FileExists(v8) )
    {
      v10 = (ComputeStorageInternal *)Src;
      if ( v14 > 7 )
        v10 = (ComputeStorageInternal *)Src[0];
      ComputeStorageInternal::DeleteFolderWithReparsePoints(v10, v9);
    }
    std::wstring::~wstring(Src);
    std::wstring::~wstring(lpFileName);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x185,
                           (unsigned int)"onecore\\vm\\compute\\dll\\legacy\\src\\graphdriver.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800359a0  mov     [rsp+arg_10], rbx
0x1800359a5  push    rdi
0x1800359a6  sub     rsp, 70h
0x1800359aa  mov     rax, cs:__security_cookie
0x1800359b1  xor     rax, rsp
0x1800359b4  mov     [rsp+78h+var_10], rax
0x1800359b9  mov     rdi, rdx
0x1800359bc  mov     rbx, rcx
0x1800359bf  mov     r8, rdx
0x1800359c2  mov     rdx, [rcx+8]
0x1800359c6  lea     rcx, [rsp+78h+lpFileName]; Src
0x1800359cb  call    _anonymous_namespace___LayerDiskPath
0x1800359d0  nop
0x1800359d1  mov     r8, rdi; pszMore
0x1800359d4  mov     rdx, [rbx+8]; pszPathIn
0x1800359d8  lea     rcx, [rsp+78h+Src]; Src
0x1800359dd  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x1800359e2  nop
0x1800359e3  lea     rcx, [rsp+78h+lpFileName]
0x1800359e8  cmp     [rsp+78h+var_18], 7
0x1800359ee  cmova   rcx, [rsp+78h+lpFileName]
0x1800359f4  call    _anonymous_namespace___FileExists
0x1800359f9  test    eax, eax
0x1800359fb  jz      short loc_180035A3E
0x1800359fd  lea     rcx, [rsp+78h+lpFileName]
0x180035a02  cmp     [rsp+78h+var_18], 7
0x180035a08  cmova   rcx, [rsp+78h+lpFileName]; lpFileName
0x180035a0e  call    cs:__imp_DeleteFileW
0x180035a15  nop     dword ptr [rax+rax+00h]
0x180035a1a  test    eax, eax
0x180035a1c  jnz     short loc_180035A33
0x180035a1e  call    cs:__imp_GetLastError
0x180035a25  nop     dword ptr [rax+rax+00h]
0x180035a2a  cmp     eax, 2
0x180035a2d  jz      short loc_180035A33
0x180035a2f  mov     al, 1
0x180035a31  jmp     short loc_180035A35
0x180035a33  xor     al, al
0x180035a35  mov     rcx, [rsp+78h]; this
0x180035a3a  test    al, al
0x180035a3c  jnz     short loc_180035AA8
0x180035a3e  lea     rcx, [rsp+78h+Src]
0x180035a43  cmp     [rsp+78h+var_38], 7
0x180035a49  cmova   rcx, [rsp+78h+Src]
0x180035a4f  call    _anonymous_namespace___FileExists
0x180035a54  test    eax, eax
0x180035a56  jz      short loc_180035A6F
0x180035a58  lea     rcx, [rsp+78h+Src]
0x180035a5d  cmp     [rsp+78h+var_38], 7
0x180035a63  cmova   rcx, [rsp+78h+Src]; this
0x180035a69  call    ?DeleteFolderWithReparsePoints@ComputeStorageInternal@@YAXPEBG@Z; ComputeStorageInternal::DeleteFolderWithReparsePoints(ushort const *)
0x180035a6e  nop
0x180035a6f  lea     rcx, [rsp+78h+Src]
0x180035a74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035a79  nop
0x180035a7a  lea     rcx, [rsp+78h+lpFileName]
0x180035a7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035a84  xor     eax, eax
0x180035a86  jmp     short loc_180035A8C
0x180035a88  mov     eax, [rsp+78h+var_58]
0x180035a8c  mov     rcx, [rsp+78h+var_10]
0x180035a91  xor     rcx, rsp; StackCookie
0x180035a94  call    __security_check_cookie
0x180035a99  mov     rbx, [rsp+78h+arg_10]
0x180035aa1  add     rsp, 70h
0x180035aa5  pop     rdi
0x180035aa6  retn
0x180035aa8  lea     r8, aOnecoreVmCompu_21; "onecore\\vm\\compute\\dll\\legacy\\src"...
0x180035aaf  mov     edx, 17Bh; void *
0x180035ab4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
