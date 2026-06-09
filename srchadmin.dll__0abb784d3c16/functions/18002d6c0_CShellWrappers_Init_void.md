# CShellWrappers::Init(void)

- ea: `0x18002d6c0`
- end: `0x18002d912`
- name: `?Init@CShellWrappers@@QEAAJXZ`
- size: `594`
- prototype: `__int64 __fastcall(CShellWrappers *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015f04`
- `0x180025fac`

## callees

- `0x180005cc0`
- `0x18000d4dc`
- `0x18002c900`
- `0x18002d6c0`
- `0x180032010`

## import_xrefs

- `SHELL32!SHGetDesktopFolder` at `0x18002d6ee`
- `SHELL32!SHGetDesktopFolder` at `0x18002d6ee`
- `SHELL32!SHGetFolderPathW` at `0x18002d86e`
- `SHELL32!SHGetFolderPathW` at `0x18002d86e`
- `SHELL32!__imp_SHGetSetSettings` at `0x18002d7b3`
- `SHELL32!__imp_SHGetSetSettings` at `0x18002d7b3`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8b9`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8ce`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8e3`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8b9`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8ce`
- `SHELL32!__imp_Shell_GetCachedImageIndex` at `0x18002d8e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d7db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d80d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d83f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d7db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d80d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002d83f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002d8a1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002d8a1`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002d884`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18002d884`
- `ole32!CreateBindCtx` at `0x18002d716`
- `ole32!CreateBindCtx` at `0x18002d716`

## string_xrefs

- `0x18002d890`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CShellWrappers::Init(CShellWrappers *this)
{
  HRESULT Error; // ebx
  LPBC v3; // rcx
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  $D321FDA48A4D82B6F6ABB6499405B63E v6; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pwszIconPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  Error = SHGetDesktopFolder((IShellFolder **)this);
  if ( Error >= 0 )
  {
    *((_QWORD *)this + 1) = 0;
    ppbc = 0;
    Error = CreateBindCtx(0, &ppbc);
    if ( Error >= 0 )
    {
      Error = BindCtx_AddObjectParam(
                ppbc,
                L"Allow binding to Internet shell folder handlers and negate STR_PARSE_PREFER_WEB_BROWSING");
      if ( Error >= 0 )
      {
        v3 = ppbc;
        *((_QWORD *)this + 1) = ppbc;
        ((void (__fastcall *)(LPBC))v3->lpVtbl->AddRef)(v3);
      }
      ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      if ( Error >= 0 )
      {
        Error = BindCtx_AddObjectParam(*((_QWORD *)this + 1), L"Validate URL");
        if ( Error >= 0 )
          Error = BindCtx_AddObjectParam(*((_QWORD *)this + 1), L"Search Control Panel Folders");
      }
    }
  }
  *((_DWORD *)this + 4) = 32;
  if ( Error >= 0 )
  {
    memset(&v6, 0, sizeof(v6));
    SHGetSetSettings(&v6, 1u, 0);
    if ( (*(_BYTE *)&v6 & 1) != 0 )
      *((_DWORD *)this + 4) |= 0x80u;
    if ( LoadStringW(Globals, 0x274u, (LPWSTR)this + 16, 256) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( LoadStringW(Globals, 0x275u, (LPWSTR)this + 528, 256) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( !LoadStringW(Globals, 0x276u, (LPWSTR)this + 272, 256) )
          Error = ResultFromKnownLastError();
        if ( Error >= 0 )
        {
          Error = SHGetFolderPathW(0, 37, 0, 0, pwszIconPath);
          if ( Error >= 0 )
          {
            Error = PathCchAddBackslash(pwszIconPath, 0x104u);
            if ( Error >= 0 )
            {
              Error = PathCchAppend(pwszIconPath, 0x104u, L"shell32.dll");
              if ( Error >= 0 )
              {
                *((_DWORD *)this + 5) = Shell_GetCachedImageIndex(pwszIconPath, 3, 0);
                *((_DWORD *)this + 6) = Shell_GetCachedImageIndex(pwszIconPath, 8, 0);
                *((_DWORD *)this + 7) = Shell_GetCachedImageIndex(pwszIconPath, 7, 0);
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002d6c0  mov     [rsp-8+arg_8], rbx
0x18002d6c5  mov     [rsp-8+arg_10], rdi
0x18002d6ca  push    rbp
0x18002d6cb  lea     rbp, [rsp-180h]
0x18002d6d3  sub     rsp, 280h
0x18002d6da  mov     rax, cs:__security_cookie
0x18002d6e1  xor     rax, rsp
0x18002d6e4  mov     [rbp+180h+var_10], rax
0x18002d6eb  mov     rdi, rcx
0x18002d6ee  call    cs:__imp_SHGetDesktopFolder
0x18002d6f4  mov     ebx, eax
0x18002d6f6  test    eax, eax
0x18002d6f8  js      loc_18002D78B
0x18002d6fe  lea     rdx, [rsp+280h+ppbc]; ppbc
0x18002d703  mov     qword ptr [rdi+8], 0
0x18002d70b  xor     ecx, ecx; reserved
0x18002d70d  mov     [rsp+280h+ppbc], 0
0x18002d716  call    cs:__imp_CreateBindCtx
0x18002d71c  mov     ebx, eax
0x18002d71e  test    eax, eax
0x18002d720  js      short loc_18002D78B
0x18002d722  mov     rcx, [rsp+280h+ppbc]
0x18002d727  lea     rdx, aAllowBindingTo; "Allow binding to Internet shell folder "...
0x18002d72e  call    BindCtx_AddObjectParam
0x18002d733  mov     ebx, eax
0x18002d735  test    eax, eax
0x18002d737  js      short loc_18002D74E
0x18002d739  mov     rcx, [rsp+280h+ppbc]
0x18002d73e  mov     [rdi+8], rcx
0x18002d742  mov     rax, [rcx]
0x18002d745  mov     rax, [rax+8]
0x18002d749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d74e  mov     rcx, [rsp+280h+ppbc]
0x18002d753  mov     rax, [rcx]
0x18002d756  mov     rax, [rax+10h]
0x18002d75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d75f  test    ebx, ebx
0x18002d761  js      short loc_18002D78B
0x18002d763  mov     rcx, [rdi+8]
0x18002d767  lea     rdx, aValidateUrl; "Validate URL"
0x18002d76e  call    BindCtx_AddObjectParam
0x18002d773  mov     ebx, eax
0x18002d775  test    eax, eax
0x18002d777  js      short loc_18002D78B
0x18002d779  mov     rcx, [rdi+8]
0x18002d77d  lea     rdx, aSearchControlP; "Search Control Panel Folders"
0x18002d784  call    BindCtx_AddObjectParam
0x18002d789  mov     ebx, eax
0x18002d78b  mov     dword ptr [rdi+10h], 20h ; ' '
0x18002d792  test    ebx, ebx
0x18002d794  js      loc_18002D8EC
0x18002d79a  xorps   xmm0, xmm0
0x18002d79d  lea     rcx, [rsp+280h+var_248]; lpss
0x18002d7a2  xor     r8d, r8d; bSet
0x18002d7a5  movups  xmmword ptr [rsp+280h+var_248.fShowAllObjects], xmm0
0x18002d7aa  movups  xmmword ptr [rsp+280h+var_248.iSortDirection], xmm0
0x18002d7af  lea     edx, [r8+1]; dwMask
0x18002d7b3  call    cs:__imp_SHGetSetSettings
0x18002d7b9  test    byte ptr [rsp+280h+var_248.fShowAllObjects], 1
0x18002d7be  jz      short loc_18002D7C5
0x18002d7c0  bts     dword ptr [rdi+10h], 7
0x18002d7c5  mov     rcx, cs:Globals; hInstance
0x18002d7cc  lea     r8, [rdi+20h]; lpBuffer
0x18002d7d0  mov     edx, 274h; uID
0x18002d7d5  mov     r9d, 100h; cchBufferMax
0x18002d7db  call    cs:__imp_LoadStringW
0x18002d7e1  test    eax, eax
0x18002d7e3  jnz     short loc_18002D7F4
0x18002d7e5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d7ea  mov     ebx, eax
0x18002d7ec  test    eax, eax
0x18002d7ee  js      loc_18002D8EC
0x18002d7f4  mov     rcx, cs:Globals; hInstance
0x18002d7fb  lea     r8, [rdi+420h]; lpBuffer
0x18002d802  mov     edx, 275h; uID
0x18002d807  mov     r9d, 100h; cchBufferMax
0x18002d80d  call    cs:__imp_LoadStringW
0x18002d813  test    eax, eax
0x18002d815  jnz     short loc_18002D826
0x18002d817  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d81c  mov     ebx, eax
0x18002d81e  test    eax, eax
0x18002d820  js      loc_18002D8EC
0x18002d826  mov     rcx, cs:Globals; hInstance
0x18002d82d  lea     r8, [rdi+220h]; lpBuffer
0x18002d834  mov     edx, 276h; uID
0x18002d839  mov     r9d, 100h; cchBufferMax
0x18002d83f  call    cs:__imp_LoadStringW
0x18002d845  test    eax, eax
0x18002d847  jnz     short loc_18002D850
0x18002d849  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002d84e  mov     ebx, eax
0x18002d850  test    ebx, ebx
0x18002d852  js      loc_18002D8EC
0x18002d858  xor     r9d, r9d; dwFlags
0x18002d85b  lea     rax, [rsp+280h+pwszIconPath]
0x18002d860  xor     r8d, r8d; hToken
0x18002d863  mov     [rsp+280h+pszPath], rax; pszPath
0x18002d868  xor     ecx, ecx; hwnd
0x18002d86a  lea     edx, [r9+25h]; csidl
0x18002d86e  call    cs:__imp_SHGetFolderPathW
0x18002d874  mov     ebx, eax
0x18002d876  test    eax, eax
0x18002d878  js      short loc_18002D8EC
0x18002d87a  mov     edx, 104h; cchPath
0x18002d87f  lea     rcx, [rsp+280h+pwszIconPath]; pszPath
0x18002d884  call    cs:__imp_PathCchAddBackslash
0x18002d88a  mov     ebx, eax
0x18002d88c  test    eax, eax
0x18002d88e  js      short loc_18002D8EC
0x18002d890  lea     r8, pszMore; "shell32.dll"
0x18002d897  mov     edx, 104h; cchPath
0x18002d89c  lea     rcx, [rsp+280h+pwszIconPath]; pszPath
0x18002d8a1  call    cs:__imp_PathCchAppend
0x18002d8a7  mov     ebx, eax
0x18002d8a9  test    eax, eax
0x18002d8ab  js      short loc_18002D8EC
0x18002d8ad  xor     r8d, r8d; uIconFlags
0x18002d8b0  lea     rcx, [rsp+280h+pwszIconPath]; pwszIconPath
0x18002d8b5  lea     edx, [r8+3]; iIconIndex
0x18002d8b9  call    cs:__imp_Shell_GetCachedImageIndex
0x18002d8bf  xor     r8d, r8d; uIconFlags
0x18002d8c2  lea     rcx, [rsp+280h+pwszIconPath]; pwszIconPath
0x18002d8c7  mov     [rdi+14h], eax
0x18002d8ca  lea     edx, [r8+8]; iIconIndex
0x18002d8ce  call    cs:__imp_Shell_GetCachedImageIndex
0x18002d8d4  xor     r8d, r8d; uIconFlags
0x18002d8d7  lea     rcx, [rsp+280h+pwszIconPath]; pwszIconPath
0x18002d8dc  mov     [rdi+18h], eax
0x18002d8df  lea     edx, [r8+7]; iIconIndex
0x18002d8e3  call    cs:__imp_Shell_GetCachedImageIndex
0x18002d8e9  mov     [rdi+1Ch], eax
0x18002d8ec  mov     eax, ebx
0x18002d8ee  mov     rcx, [rbp+180h+var_10]
0x18002d8f5  xor     rcx, rsp; StackCookie
0x18002d8f8  call    __security_check_cookie
0x18002d8fd  lea     r11, [rsp+280h+var_s0]
0x18002d905  mov     rbx, [r11+18h]
0x18002d909  mov     rdi, [r11+20h]
0x18002d90d  mov     rsp, r11
0x18002d910  pop     rbp
0x18002d911  retn
```
