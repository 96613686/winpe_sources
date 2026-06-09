# GetUserTileFolderPath(ushort const *,ushort * *)

- ea: `0x1800db630`
- end: `0x1800db753`
- name: `?GetUserTileFolderPath@@YAJPEBGPEAPEAG@Z`
- size: `291`
- prototype: `__int64 __fastcall(PCWSTR pszMore, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task`

## callers

- `0x1800d1a40`

## callees

- `0x1800156f0`
- `0x1800162f0`
- `0x18002e93c`
- `0x180054130`
- `0x1800db630`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800db6ef`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800db6ef`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800db6c4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800db709`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800db6c4`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800db709`
- `SHELL32!SHGetKnownFolderPath` at `0x1800db67e`
- `SHELL32!SHGetKnownFolderPath` at `0x1800db67e`

## pseudocode

```c
__int64 __fastcall GetUserTileFolderPath(PCWSTR pszMore, LPWSTR *ppwsz)
{
  HRESULT v4; // ebx
  HRESULT CurrentUsersSidString; // eax
  LPWSTR ppwsza; // [rsp+20h] [rbp-238h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  *ppwsz = 0;
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_PublicUserTiles, 0x9000u, 0, &ppszPath);
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
0x1800db630  mov     [rsp+arg_10], rbx
0x1800db635  mov     [rsp+arg_18], rsi
0x1800db63a  push    rdi
0x1800db63b  sub     rsp, 250h
0x1800db642  mov     rax, cs:__security_cookie
0x1800db649  xor     rax, rsp
0x1800db64c  mov     [rsp+258h+var_18], rax
0x1800db654  mov     rsi, rdx
0x1800db657  mov     qword ptr [rdx], 0
0x1800db65e  mov     rdi, rcx
0x1800db661  mov     [rsp+258h+ppszPath], 0
0x1800db66a  mov     edx, 9000h; dwFlags
0x1800db66f  lea     rcx, FOLDERID_PublicUserTiles; rfid
0x1800db676  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x1800db67b  xor     r8d, r8d; hToken
0x1800db67e  call    cs:__imp_SHGetKnownFolderPath
0x1800db685  nop     dword ptr [rax+rax+00h]
0x1800db68a  mov     ebx, eax
0x1800db68c  test    eax, eax
0x1800db68e  js      loc_1800DB721
0x1800db694  mov     r8, [rsp+258h+ppszPath]; unsigned __int16 *
0x1800db699  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x1800db69e  mov     edx, 104h; unsigned __int64
0x1800db6a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800db6a8  mov     ebx, eax
0x1800db6aa  test    eax, eax
0x1800db6ac  js      short loc_1800DB721
0x1800db6ae  mov     [rsp+258h+ppwsz], 0
0x1800db6b7  test    rdi, rdi
0x1800db6ba  jz      short loc_1800DB6D2
0x1800db6bc  lea     rdx, [rsp+258h+ppwsz]; ppwsz
0x1800db6c1  mov     rcx, rdi; psz
0x1800db6c4  call    cs:__imp_SHStrDupW
0x1800db6cb  nop     dword ptr [rax+rax+00h]
0x1800db6d0  jmp     short loc_1800DB6DC
0x1800db6d2  lea     rcx, [rsp+258h+ppwsz]; ppwsz
0x1800db6d7  call    ?GetCurrentUsersSidString@@YAJPEAPEAG@Z; GetCurrentUsersSidString(ushort * *)
0x1800db6dc  mov     ebx, eax
0x1800db6de  test    eax, eax
0x1800db6e0  js      short loc_1800DB717
0x1800db6e2  mov     r8, rdi; pszMore
0x1800db6e5  lea     rcx, [rsp+258h+pszPath]; pszPath
0x1800db6ea  mov     edx, 104h; cchPath
0x1800db6ef  call    cs:__imp_PathCchAppend
0x1800db6f6  nop     dword ptr [rax+rax+00h]
0x1800db6fb  mov     ebx, eax
0x1800db6fd  test    eax, eax
0x1800db6ff  js      short loc_1800DB717
0x1800db701  mov     rdx, rsi; ppwsz
0x1800db704  lea     rcx, [rsp+258h+pszPath]; psz
0x1800db709  call    cs:__imp_SHStrDupW
0x1800db710  nop     dword ptr [rax+rax+00h]
0x1800db715  mov     ebx, eax
0x1800db717  lea     rcx, [rsp+258h+ppwsz]
0x1800db71c  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800db721  lea     rcx, [rsp+258h+ppszPath]
0x1800db726  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800db72b  mov     eax, ebx
0x1800db72d  mov     rcx, [rsp+258h+var_18]
0x1800db735  xor     rcx, rsp; StackCookie
0x1800db738  call    __security_check_cookie
0x1800db73d  lea     r11, [rsp+258h+var_8]
0x1800db745  mov     rbx, [r11+20h]
0x1800db749  mov     rsi, [r11+28h]
0x1800db74d  mov     rsp, r11
0x1800db750  pop     rdi
0x1800db751  retn
```
