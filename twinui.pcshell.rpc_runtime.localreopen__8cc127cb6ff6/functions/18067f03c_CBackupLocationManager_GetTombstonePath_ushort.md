# CBackupLocationManager::GetTombstonePath(ushort * *)

- ea: `0x18067f03c`
- end: `0x18067f188`
- name: `?GetTombstonePath@CBackupLocationManager@@QEBAJPEAPEAG@Z`
- size: `332`
- prototype: `int(CBackupLocationManager *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180684700`

## callees

- `0x1800290dc`
- `0x1802789e0`
- `0x180356360`
- `0x18067f03c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067f15e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067f15e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18067f11f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18067f11f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18067f10e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18067f10e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067f0e3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067f0fd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067f0e3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18067f0fd`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18067f13c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18067f13c`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067f0a6`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x18067f0a6`
- `Windows.Storage!SHGetPathFromIDListW` at `0x18067f0ca`
- `Windows.Storage!SHGetPathFromIDListW` at `0x18067f0ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBackupLocationManager::GetTombstonePath(PCWSTR *this, unsigned __int16 **a2)
{
  HRESULT Error; // ebx
  ITEMIDLIST *v5; // rcx
  LPCITEMIDLIST *p_pidl; // [rsp+20h] [rbp-E0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+28h] [rbp-D8h] BYREF
  char v9; // [rsp+30h] [rbp-D0h]
  LPCITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  *a2 = 0;
  pidl = 0;
  p_pidl = &pidl;
  ppidl = 0;
  v9 = 1;
  Error = SHGetKnownFolderIDList(&FOLDERID_UserPinned, 0x9000u, 0, &ppidl);
  wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
  if ( Error >= 0 )
  {
    if ( SHGetPathFromIDListW(pidl, pszPath) )
    {
      Error = PathCchAppend(pszPath, 0x104u, *this);
      if ( Error >= 0 )
      {
        Error = PathCchAppend(pszPath, 0x104u, L"Tombstones");
        if ( Error >= 0 )
        {
          if ( PathFileExistsW(pszPath)
            || CreateDirectoryW(pszPath, 0)
            || (Error = ResultFromKnownLastError(), Error >= 0) )
          {
            Error = SHStrDupW(pszPath, a2);
          }
        }
      }
    }
    else
    {
      Error = -2147024882;
    }
  }
  v5 = (ITEMIDLIST *)pidl;
  pidl = 0;
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18067f03c  mov     [rsp-8+arg_10], rbx
0x18067f041  push    rbp
0x18067f042  push    rsi
0x18067f043  push    rdi
0x18067f044  lea     rbp, [rsp-160h]
0x18067f04c  sub     rsp, 260h
0x18067f053  mov     rax, cs:__security_cookie
0x18067f05a  xor     rax, rsp
0x18067f05d  mov     [rbp+170h+var_20], rax
0x18067f064  mov     rdi, rdx
0x18067f067  mov     rsi, rcx
0x18067f06a  mov     qword ptr [rdx], 0
0x18067f071  mov     [rsp+270h+pidl], 0
0x18067f07a  lea     rax, [rsp+270h+pidl]
0x18067f07f  mov     [rsp+270h+var_250], rax
0x18067f084  mov     [rsp+270h+ppidl], 0
0x18067f08d  mov     [rsp+270h+var_240], 1
0x18067f092  lea     r9, [rsp+270h+ppidl]; ppidl
0x18067f097  xor     r8d, r8d; hToken
0x18067f09a  mov     edx, 9000h; dwFlags
0x18067f09f  lea     rcx, FOLDERID_UserPinned; rfid
0x18067f0a6  call    cs:__imp_SHGetKnownFolderIDList
0x18067f0ac  mov     ebx, eax
0x18067f0ae  lea     rcx, [rsp+270h+var_250]
0x18067f0b3  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18067f0b8  test    ebx, ebx
0x18067f0ba  js      loc_18067F14B
0x18067f0c0  lea     rdx, [rsp+270h+pszPath]; pszPath
0x18067f0c5  mov     rcx, [rsp+270h+pidl]; pidl
0x18067f0ca  call    cs:__imp_SHGetPathFromIDListW
0x18067f0d0  test    eax, eax
0x18067f0d2  jz      short loc_18067F146
0x18067f0d4  mov     r8, [rsi]; pszMore
0x18067f0d7  mov     esi, 104h
0x18067f0dc  mov     edx, esi; cchPath
0x18067f0de  lea     rcx, [rsp+270h+pszPath]; pszPath
0x18067f0e3  call    cs:__imp_PathCchAppend
0x18067f0e9  mov     ebx, eax
0x18067f0eb  test    eax, eax
0x18067f0ed  js      short loc_18067F14B
0x18067f0ef  lea     r8, pszMore; "Tombstones"
0x18067f0f6  mov     edx, esi; cchPath
0x18067f0f8  lea     rcx, [rsp+270h+pszPath]; pszPath
0x18067f0fd  call    cs:__imp_PathCchAppend
0x18067f103  mov     ebx, eax
0x18067f105  test    eax, eax
0x18067f107  js      short loc_18067F14B
0x18067f109  lea     rcx, [rsp+270h+pszPath]; pszPath
0x18067f10e  call    cs:__imp_PathFileExistsW
0x18067f114  test    eax, eax
0x18067f116  jnz     short loc_18067F134
0x18067f118  xor     edx, edx; lpSecurityAttributes
0x18067f11a  lea     rcx, [rsp+270h+pszPath]; lpPathName
0x18067f11f  call    cs:__imp_CreateDirectoryW
0x18067f125  test    eax, eax
0x18067f127  jnz     short loc_18067F134
0x18067f129  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18067f12e  mov     ebx, eax
0x18067f130  test    eax, eax
0x18067f132  js      short loc_18067F14B
0x18067f134  mov     rdx, rdi; ppwsz
0x18067f137  lea     rcx, [rsp+270h+pszPath]; psz
0x18067f13c  call    cs:__imp_SHStrDupW
0x18067f142  mov     ebx, eax
0x18067f144  jmp     short loc_18067F14B
0x18067f146  mov     ebx, 8007000Eh
0x18067f14b  mov     rcx, [rsp+270h+pidl]; pv
0x18067f150  mov     [rsp+270h+pidl], 0
0x18067f159  test    rcx, rcx
0x18067f15c  jz      short loc_18067F164
0x18067f15e  call    cs:__imp_CoTaskMemFree
0x18067f164  mov     eax, ebx
0x18067f166  mov     rcx, [rbp+170h+var_20]
0x18067f16d  xor     rcx, rsp; StackCookie
0x18067f170  call    __security_check_cookie
0x18067f175  mov     rbx, [rsp+270h+arg_10]
0x18067f17d  add     rsp, 260h
0x18067f184  pop     rdi
0x18067f185  pop     rsi
0x18067f186  pop     rbp
0x18067f187  retn
```
