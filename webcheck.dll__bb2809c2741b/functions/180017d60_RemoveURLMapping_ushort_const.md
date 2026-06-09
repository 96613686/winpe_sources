# RemoveURLMapping(ushort const *)

- ea: `0x180017d60`
- end: `0x180017e49`
- name: `?RemoveURLMapping@@YAXPEBG@Z`
- size: `233`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016f80`

## callees

- `0x180017d60`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180017e2a`
- `ADVAPI32!RegCloseKey` at `0x180017e2a`
- `ADVAPI32!RegOpenKeyExW` at `0x180017e0d`
- `ADVAPI32!RegOpenKeyExW` at `0x180017e0d`
- `ADVAPI32!RegDeleteValueW` at `0x180017e1f`
- `ADVAPI32!RegDeleteValueW` at `0x180017e1f`
- `WININET!SetUrlCacheEntryInfoW` at `0x180017ddd`
- `WININET!SetUrlCacheEntryInfoW` at `0x180017ddd`
- `WININET!GetUrlCacheEntryInfoExW` at `0x180017db3`
- `WININET!GetUrlCacheEntryInfoExW` at `0x180017db3`

## string_xrefs

- `0x180017dff`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\Cache\Preload`

## pseudocode

```c
void __fastcall RemoveURLMapping(const unsigned __int16 *a1)
{
  DWORD cbCacheEntryInfo; // [rsp+40h] [rbp-1828h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-1820h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+50h] [rbp-1818h] BYREF

  cbCacheEntryInfo = 6144;
  if ( GetUrlCacheEntryInfoExW(a1, &CacheEntryInfo, &cbCacheEntryInfo, 0, 0, 0, 0)
    && (CacheEntryInfo.CacheEntryType & 0x10000000) != 0 )
  {
    CacheEntryInfo.CacheEntryType &= ~0x10000000u;
    SetUrlCacheEntryInfoW(a1, &CacheEntryInfo, 4u);
    phkResult = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Cache\\Preload",
            0,
            0x20006u,
            &phkResult) )
    {
      RegDeleteValueW(phkResult, a1);
      RegCloseKey(phkResult);
    }
  }
}

```

## disassembly

```asm
0x180017d60  push    rbx
0x180017d62  mov     eax, 1860h
0x180017d67  call    _alloca_probe
0x180017d6c  sub     rsp, rax
0x180017d6f  mov     rax, cs:__security_cookie
0x180017d76  xor     rax, rsp
0x180017d79  mov     [rsp+1868h+var_18], rax
0x180017d81  mov     [rsp+1868h+dwFlags], 0; dwFlags
0x180017d89  lea     r8, [rsp+1868h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180017d8e  mov     [rsp+1868h+lpReserved], 0; lpReserved
0x180017d97  lea     rdx, [rsp+1868h+CacheEntryInfo]; lpCacheEntryInfo
0x180017d9c  xor     r9d, r9d; lpszRedirectUrl
0x180017d9f  mov     [rsp+1868h+lpcbRedirectUrl], 0; lpcbRedirectUrl
0x180017da8  mov     rbx, rcx
0x180017dab  mov     [rsp+1868h+cbCacheEntryInfo], 1800h
0x180017db3  call    cs:__imp_GetUrlCacheEntryInfoExW
0x180017db9  test    eax, eax
0x180017dbb  jz      short loc_180017E30
0x180017dbd  mov     eax, [rsp+1868h+CacheEntryInfo.CacheEntryType]
0x180017dc1  bt      eax, 1Ch
0x180017dc5  jnb     short loc_180017E30
0x180017dc7  btr     eax, 1Ch
0x180017dcb  lea     rdx, [rsp+1868h+CacheEntryInfo]; lpCacheEntryInfo
0x180017dd0  mov     r8d, 4; dwFieldControl
0x180017dd6  mov     [rsp+1868h+CacheEntryInfo.CacheEntryType], eax
0x180017dda  mov     rcx, rbx; lpszUrlName
0x180017ddd  call    cs:__imp_SetUrlCacheEntryInfoW
0x180017de3  lea     rax, [rsp+1868h+phkResult]
0x180017de8  mov     [rsp+1868h+phkResult], 0
0x180017df1  mov     r9d, 20006h; samDesired
0x180017df7  mov     [rsp+1868h+lpcbRedirectUrl], rax; phkResult
0x180017dfc  xor     r8d, r8d; ulOptions
0x180017dff  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180017e06  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180017e0d  call    cs:__imp_RegOpenKeyExW
0x180017e13  test    eax, eax
0x180017e15  jnz     short loc_180017E30
0x180017e17  mov     rcx, [rsp+1868h+phkResult]; hKey
0x180017e1c  mov     rdx, rbx; lpValueName
0x180017e1f  call    cs:__imp_RegDeleteValueW
0x180017e25  mov     rcx, [rsp+1868h+phkResult]; hKey
0x180017e2a  call    cs:__imp_RegCloseKey
0x180017e30  mov     rcx, [rsp+1868h+var_18]
0x180017e38  xor     rcx, rsp; StackCookie
0x180017e3b  call    __security_check_cookie
0x180017e40  add     rsp, 1860h
0x180017e47  pop     rbx
0x180017e48  retn
```
