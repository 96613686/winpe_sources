# s_GetProfilePath(ushort *)

- ea: `0x180061704`
- end: `0x180061810`
- name: `?s_GetProfilePath@@YAJPEAG@Z`
- size: `268`
- prototype: `__int64 __fastcall(LPWSTR pszDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800615c8`

## callees

- `0x18000ab10`
- `0x180030f64`
- `0x1800358c0`
- `0x180061704`

## import_xrefs

- `SHCORE!__imp_SHCreateDirectoryExW` at `0x1800617a3`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x1800617a3`
- `SHELL32!SHGetKnownFolderPath` at `0x180061743`
- `SHELL32!SHGetKnownFolderPath` at `0x180061743`
- `SHLWAPI!PathCombineW` at `0x18006178e`
- `SHLWAPI!PathCombineW` at `0x1800617d2`
- `SHLWAPI!PathCombineW` at `0x18006178e`
- `SHLWAPI!PathCombineW` at `0x1800617d2`
- `SHLWAPI!PathAddBackslashW` at `0x180061772`
- `SHLWAPI!PathAddBackslashW` at `0x180061772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800617e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800617e7`

## pseudocode

```c
__int64 __fastcall s_GetProfilePath(LPWSTR pszDest)
{
  HRESULT Error; // ebx
  int v3; // eax
  PWSTR ppszPath; // [rsp+20h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-228h] BYREF

  ppszPath = 0;
  Error = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0x8000u, 0, &ppszPath);
  if ( Error >= 0 )
  {
    Error = StringCchCopyW(pszPath, 0x104u, ppszPath);
    if ( Error >= 0 )
    {
      if ( !PathAddBackslashW(pszPath) || !PathCombineW(pszPath, ppszPath, L"Microsoft\\Windows\\Themes\\") )
        goto LABEL_11;
      v3 = SHCreateDirectoryExW(0, pszPath, 0);
      if ( !v3 || v3 == 183 )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_12;
      }
      if ( !PathCombineW(pszDest, pszPath, L"slideshow.ini") )
LABEL_11:
        Error = -2147024774;
    }
LABEL_12:
    CoTaskMemFree(ppszPath);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180061704  mov     [rsp+arg_8], rbx
0x180061709  push    rdi
0x18006170a  sub     rsp, 250h
0x180061711  mov     rax, cs:__security_cookie
0x180061718  xor     rax, rsp
0x18006171b  mov     [rsp+258h+var_18], rax
0x180061723  mov     rdi, rcx
0x180061726  mov     [rsp+258h+ppszPath], 0
0x18006172f  lea     rcx, FOLDERID_RoamingAppData; rfid
0x180061736  xor     r8d, r8d; hToken
0x180061739  lea     r9, [rsp+258h+ppszPath]; ppszPath
0x18006173e  mov     edx, 8000h; dwFlags
0x180061743  call    cs:__imp_SHGetKnownFolderPath
0x180061749  mov     ebx, eax
0x18006174b  test    eax, eax
0x18006174d  js      loc_1800617ED
0x180061753  mov     r8, [rsp+258h+ppszPath]; unsigned __int16 *
0x180061758  lea     rcx, [rsp+258h+pszPath]; unsigned __int16 *
0x18006175d  mov     edx, 104h; unsigned __int64
0x180061762  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061767  mov     ebx, eax
0x180061769  test    eax, eax
0x18006176b  js      short loc_1800617E2
0x18006176d  lea     rcx, [rsp+258h+pszPath]; pszPath
0x180061772  call    cs:__imp_PathAddBackslashW
0x180061778  test    rax, rax
0x18006177b  jz      short loc_1800617DD
0x18006177d  mov     rdx, [rsp+258h+ppszPath]; pszDir
0x180061782  lea     r8, pszFile; "Microsoft\\Windows\\Themes\\"
0x180061789  lea     rcx, [rsp+258h+pszPath]; pszDest
0x18006178e  call    cs:__imp_PathCombineW
0x180061794  test    rax, rax
0x180061797  jz      short loc_1800617DD
0x180061799  xor     r8d, r8d; psa
0x18006179c  lea     rdx, [rsp+258h+pszPath]; pszPath
0x1800617a1  xor     ecx, ecx; hwnd
0x1800617a3  call    cs:__imp_SHCreateDirectoryExW
0x1800617a9  test    eax, eax
0x1800617ab  jz      short loc_1800617C1
0x1800617ad  cmp     eax, 0B7h
0x1800617b2  jz      short loc_1800617C1
0x1800617b4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800617b9  mov     ebx, eax
0x1800617bb  test    eax, eax
0x1800617bd  js      short loc_1800617E2
0x1800617bf  jmp     short loc_1800617C3
0x1800617c1  xor     ebx, ebx
0x1800617c3  lea     r8, aSlideshowIni; "slideshow.ini"
0x1800617ca  mov     rcx, rdi; pszDest
0x1800617cd  lea     rdx, [rsp+258h+pszPath]; pszDir
0x1800617d2  call    cs:__imp_PathCombineW
0x1800617d8  test    rax, rax
0x1800617db  jnz     short loc_1800617E2
0x1800617dd  mov     ebx, 8007007Ah
0x1800617e2  mov     rcx, [rsp+258h+ppszPath]; pv
0x1800617e7  call    cs:__imp_CoTaskMemFree
0x1800617ed  mov     eax, ebx
0x1800617ef  mov     rcx, [rsp+258h+var_18]
0x1800617f7  xor     rcx, rsp; StackCookie
0x1800617fa  call    __security_check_cookie
0x1800617ff  mov     rbx, [rsp+258h+arg_8]
0x180061807  add     rsp, 250h
0x18006180e  pop     rdi
0x18006180f  retn
```
