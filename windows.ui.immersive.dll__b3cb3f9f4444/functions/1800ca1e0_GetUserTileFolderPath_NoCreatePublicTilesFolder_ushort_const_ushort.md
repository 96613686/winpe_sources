# GetUserTileFolderPath_NoCreatePublicTilesFolder(ushort const *,ushort * *)

- ea: `0x1800ca1e0`
- end: `0x1800ca304`
- name: `?GetUserTileFolderPath_NoCreatePublicTilesFolder@@YAJPEBGPEAPEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(PCWSTR pszMore, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task`

## callers

- `0x18005021c`

## callees

- `0x1800156f0`
- `0x1800162f0`
- `0x18002e93c`
- `0x180054130`
- `0x1800ca1e0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800ca29f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800ca29f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ca274`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ca2b9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ca274`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800ca2b9`
- `SHELL32!SHGetKnownFolderPath` at `0x1800ca22e`
- `SHELL32!SHGetKnownFolderPath` at `0x1800ca22e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetUserTileFolderPath_NoCreatePublicTilesFolder(PCWSTR pszMore, LPWSTR *ppwsz)
{
  HRESULT v4; // ebx
  HRESULT CurrentUsersSidString; // eax
  LPWSTR ppwsza; // [rsp+20h] [rbp-238h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  *ppwsz = 0;
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_PublicUserTiles, 0x1000u, 0, &ppszPath);
  if ( v4 >= 0 )
  {
    v4 = StringCchCopyW(pszPath, 0x104u, ppszPath);
    if ( v4 >= 0 )
    {
      ppwsza = 0;
      if ( pszMore )
        CurrentUsersSidString = SHStrDupW(pszMore, &ppwsza);
      else
        CurrentUsersSidString = GetCurrentUsersSidString(&ppwsza);
      v4 = CurrentUsersSidString;
      if ( CurrentUsersSidString >= 0 )
      {
        v4 = PathCchAppend(pszPath, 0x104u, pszMore);
        if ( v4 >= 0 )
          v4 = SHStrDupW(pszPath, ppwsz);
      }
      CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppwsza);
    }
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&ppszPath);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ca1e0  mov     [rsp+arg_10], rbx
0x1800ca1e5  mov     [rsp+arg_18], rsi
0x1800ca1ea  push    rdi
0x1800ca1eb  sub     rsp, 250h
0x1800ca1f2  mov     rax, cs:__security_cookie
0x1800ca1f9  xor     rax, rsp
0x1800ca1fc  mov     [rsp+258h+var_18], rax
0x1800ca204  mov     rsi, rdx
0x1800ca207  mov     rdi, rcx
0x1800ca20a  mov     qword ptr [rdx], 0
0x1800ca211  mov     [rsp+258h+ppszPath], 0
0x1800ca21a  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x1800ca21f  xor     r8d, r8d; hToken
0x1800ca222  mov     edx, 1000h; dwFlags
0x1800ca227  lea     rcx, FOLDERID_PublicUserTiles; rfid
0x1800ca22e  call    cs:__imp_SHGetKnownFolderPath
0x1800ca235  nop     dword ptr [rax+rax+00h]
0x1800ca23a  mov     ebx, eax
0x1800ca23c  test    eax, eax
0x1800ca23e  js      loc_1800CA2D2
0x1800ca244  mov     r8, [rsp+258h+ppszPath]; unsigned __int16 *
0x1800ca249  mov     edx, 104h; unsigned __int64
0x1800ca24e  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800ca253  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ca258  mov     ebx, eax
0x1800ca25a  test    eax, eax
0x1800ca25c  js      short loc_1800CA2D2
0x1800ca25e  mov     [rsp+258h+ppwsz], 0
0x1800ca267  test    rdi, rdi
0x1800ca26a  jz      short loc_1800CA282
0x1800ca26c  lea     rdx, [rsp+258h+ppwsz]; ppwsz
0x1800ca271  mov     rcx, rdi; psz
0x1800ca274  call    cs:__imp_SHStrDupW
0x1800ca27b  nop     dword ptr [rax+rax+00h]
0x1800ca280  jmp     short loc_1800CA28C
0x1800ca282  lea     rcx, [rsp+258h+ppwsz]; ppwsz
0x1800ca287  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800ca28c  mov     ebx, eax
0x1800ca28e  test    eax, eax
0x1800ca290  js      short loc_1800CA2C7
0x1800ca292  mov     r8, rdi; pszMore
0x1800ca295  mov     edx, 104h; cchPath
0x1800ca29a  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800ca29f  call    cs:__imp_PathCchAppend
0x1800ca2a6  nop     dword ptr [rax+rax+00h]
0x1800ca2ab  mov     ebx, eax
0x1800ca2ad  test    eax, eax
0x1800ca2af  js      short loc_1800CA2C7
0x1800ca2b1  mov     rdx, rsi; ppwsz
0x1800ca2b4  lea     rcx, [rsp+258h+pszPath]; psz
0x1800ca2b9  call    cs:__imp_SHStrDupW
0x1800ca2c0  nop     dword ptr [rax+rax+00h]
0x1800ca2c5  mov     ebx, eax
0x1800ca2c7  lea     rcx, [rsp+258h+ppwsz]
0x1800ca2cc  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ca2d1  nop
0x1800ca2d2  lea     rcx, [rsp+258h+ppszPath]
0x1800ca2d7  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800ca2dc  mov     eax, ebx
0x1800ca2de  mov     rcx, [rsp+258h+var_18]
0x1800ca2e6  xor     rcx, rsp; StackCookie
0x1800ca2e9  call    __security_check_cookie
0x1800ca2ee  lea     r11, [rsp+258h+var_8]
0x1800ca2f6  mov     rbx, [r11+20h]
0x1800ca2fa  mov     rsi, [r11+28h]
0x1800ca2fe  mov     rsp, r11
0x1800ca301  pop     rdi
0x1800ca302  retn
```
