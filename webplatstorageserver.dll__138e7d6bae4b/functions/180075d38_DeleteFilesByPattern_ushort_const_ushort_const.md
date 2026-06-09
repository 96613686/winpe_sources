# DeleteFilesByPattern(ushort const *,ushort const *)

- ea: `0x180075d38`
- end: `0x180075e93`
- name: `?DeleteFilesByPattern@@YAXPEBG0@Z`
- size: `347`
- prototype: `void(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800c0998`

## callees

- `0x1800169b0`
- `0x18001c800`
- `0x18003ffd4`
- `0x1800412c4`
- `0x18005a2b8`
- `0x180075d38`
- `0x180075ea8`
- `0x180080fb0`
- `0x180081b40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180075dcf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180075dcf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180075e2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180075e2e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180075e45`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180075e45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x180075df3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x180075df3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DeleteFilesByPattern(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const WCHAR *v3; // rcx
  char *FirstFile; // rbx
  const WCHAR *v5; // rcx
  char *v6; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR v7[4]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Src[40]; // [rsp+78h] [rbp-88h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  std::wstring::wstring(Src, a1);
  EnsureTrailingSlash(Src);
  std::operator+<unsigned short>(lpFileName, Src, a2);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v3 = lpFileName[0];
  FirstFile = (char *)FindFirstFileExW(v3, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v6 = FirstFile;
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 && PathMatchSpecW(FindFileData.cFileName, a2) )
      {
        std::operator+<unsigned short>(v7, Src, FindFileData.cFileName);
        RemoveReadonlyAttribute(v7, FindFileData.dwFileAttributes);
        v5 = (const WCHAR *)v7;
        if ( v7[3] > (LPCWSTR)7 )
          v5 = v7[0];
        DeleteFileW(v5);
        std::wstring::~wstring(v7);
      }
    }
    while ( FindNextFileW(FirstFile, &FindFileData) );
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v6);
  std::wstring::~wstring(lpFileName);
  std::wstring::~wstring(Src);
}

```

## disassembly

```asm
0x180075d38  mov     [rsp-8+arg_10], rbx
0x180075d3d  mov     [rsp-8+arg_18], rdi
0x180075d42  push    rbp
0x180075d43  lea     rbp, [rsp-200h]
0x180075d4b  sub     rsp, 300h
0x180075d52  mov     rax, cs:__security_cookie
0x180075d59  xor     rax, rsp
0x180075d5c  mov     [rbp+200h+var_10], rax
0x180075d63  mov     rdi, rdx
0x180075d66  mov     rdx, rcx
0x180075d69  lea     rcx, [rsp+300h+Src]
0x180075d6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180075d73  nop
0x180075d74  lea     rcx, [rsp+300h+Src]
0x180075d79  call    ?EnsureTrailingSlash@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EnsureTrailingSlash(std::wstring &)
0x180075d7e  mov     r8, rdi; void *
0x180075d81  lea     rdx, [rsp+300h+Src]; Src
0x180075d86  lea     rcx, [rsp+300h+lpFileName]; void *
0x180075d8b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180075d90  nop
0x180075d91  xor     edx, edx; Val
0x180075d93  mov     r8d, 250h; Size
0x180075d99  lea     rcx, [rbp+200h+FindFileData]; void *
0x180075d9d  call    memset_0
0x180075da2  lea     rcx, [rsp+300h+lpFileName]
0x180075da7  cmp     [rsp+300h+var_290], 7
0x180075dad  cmova   rcx, [rsp+300h+lpFileName]; lpFileName
0x180075db3  mov     [rsp+300h+dwAdditionalFlags], 0; dwAdditionalFlags
0x180075dbb  mov     [rsp+300h+lpSearchFilter], 0; lpSearchFilter
0x180075dc4  xor     r9d, r9d; fSearchOp
0x180075dc7  lea     r8, [rbp+200h+FindFileData]; lpFindFileData
0x180075dcb  lea     edx, [r9+1]; fInfoLevelId
0x180075dcf  call    cs:__imp_FindFirstFileExW
0x180075dd5  mov     rbx, rax
0x180075dd8  mov     [rsp+300h+var_2D0], rax
0x180075ddd  dec     rax
0x180075de0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180075de4  ja      short loc_180075E4F
0x180075de6  test    byte ptr [rbp+200h+FindFileData], 10h
0x180075dea  jnz     short loc_180075E3E
0x180075dec  mov     rdx, rdi; pszSpec
0x180075def  lea     rcx, [rbp+200h+pszFile]; pszFile
0x180075df3  call    cs:__imp_PathMatchSpecW
0x180075df9  test    eax, eax
0x180075dfb  jz      short loc_180075E3E
0x180075dfd  lea     r8, [rbp+200h+pszFile]; void *
0x180075e01  lea     rdx, [rsp+300h+Src]; Src
0x180075e06  lea     rcx, [rsp+300h+var_2C8]; void *
0x180075e0b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180075e10  mov     edx, [rbp+200h+FindFileData]
0x180075e13  lea     rcx, [rsp+300h+var_2C8]
0x180075e18  call    RemoveReadonlyAttribute
0x180075e1d  lea     rcx, [rsp+300h+var_2C8]
0x180075e22  cmp     [rsp+300h+var_2B0], 7
0x180075e28  cmova   rcx, [rsp+300h+var_2C8]; lpFileName
0x180075e2e  call    cs:__imp_DeleteFileW
0x180075e34  lea     rcx, [rsp+300h+var_2C8]; void *
0x180075e39  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180075e3e  lea     rdx, [rbp+200h+FindFileData]; lpFindFileData
0x180075e42  mov     rcx, rbx; hFindFile
0x180075e45  call    cs:__imp_FindNextFileW
0x180075e4b  test    eax, eax
0x180075e4d  jnz     short loc_180075DE6
0x180075e4f  lea     rcx, [rsp+300h+var_2D0]
0x180075e54  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180075e59  nop
0x180075e5a  lea     rcx, [rsp+300h+lpFileName]; void *
0x180075e5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180075e64  nop
0x180075e65  lea     rcx, [rsp+300h+Src]; void *
0x180075e6a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180075e6f  mov     rcx, [rbp+200h+var_10]
0x180075e76  xor     rcx, rsp; StackCookie
0x180075e79  call    __security_check_cookie
0x180075e7e  lea     r11, [rsp+300h+var_s0]
0x180075e86  mov     rbx, [r11+20h]
0x180075e8a  mov     rdi, [r11+28h]
0x180075e8e  mov     rsp, r11
0x180075e91  pop     rbp
0x180075e92  retn
```
