# GetUrlInfoAndMakeSticky(ushort const *,ushort const *,_INTERNET_CACHE_ENTRY_INFOW *,ulong,__int64)

- ea: `0x18002041c`
- end: `0x1800204a3`
- name: `?GetUrlInfoAndMakeSticky@@YAJPEBG0PEAU_INTERNET_CACHE_ENTRY_INFOW@@K_J@Z`
- size: `135`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, struct _INTERNET_CACHE_ENTRY_INFOW *, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020620`
- `0x180020860`
- `0x180021a5c`

## callees

- `0x18002041c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020476`
- `KERNEL32!GetLastError` at `0x180020476`
- `WININET!GetUrlCacheEntryInfoW` at `0x18002043f`
- `WININET!GetUrlCacheEntryInfoW` at `0x18002043f`
- `WININET!SetUrlCacheEntryGroupW` at `0x18002046c`
- `WININET!SetUrlCacheEntryGroupW` at `0x18002046c`

## pseudocode

```c
__int64 __fastcall GetUrlInfoAndMakeSticky(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _INTERNET_CACHE_ENTRY_INFOW *a3,
        __int64 a4,
        GROUPID GroupId)
{
  DWORD LastError; // eax
  DWORD cbCacheEntryInfo[6]; // [rsp+30h] [rbp-18h] BYREF

  a3->dwStructSize = 6144;
  cbCacheEntryInfo[0] = 6144;
  if ( !GetUrlCacheEntryInfoW(a2, a3, cbCacheEntryInfo) )
    return 2147500037LL;
  if ( GroupId && !SetUrlCacheEntryGroupW(a2, 0, GroupId, 0, 0, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 2 || LastError == 112 )
      return 2147942414LL;
    if ( LastError != 1816 )
      return 2147500037LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18002041c  push    rbx
0x18002041e  sub     rsp, 40h
0x180020422  mov     ecx, 1800h
0x180020427  mov     rax, r8
0x18002042a  mov     rbx, rdx
0x18002042d  mov     [r8], ecx
0x180020430  mov     [rsp+48h+cbCacheEntryInfo], ecx
0x180020434  lea     r8, [rsp+48h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180020439  mov     rcx, rbx; lpszUrlName
0x18002043c  mov     rdx, rax; lpCacheEntryInfo
0x18002043f  call    cs:__imp_GetUrlCacheEntryInfoW
0x180020445  test    eax, eax
0x180020447  jz      short loc_18002048D
0x180020449  mov     r8, [rsp+48h+GroupId]; GroupId
0x18002044e  test    r8, r8
0x180020451  jz      short loc_18002049F
0x180020453  mov     [rsp+48h+lpReserved], 0; lpReserved
0x18002045c  xor     r9d, r9d; pbGroupAttributes
0x18002045f  xor     edx, edx; dwFlags
0x180020461  mov     [rsp+48h+cbGroupAttributes], 0; cbGroupAttributes
0x180020469  mov     rcx, rbx; lpszUrlName
0x18002046c  call    cs:__imp_SetUrlCacheEntryGroupW
0x180020472  test    eax, eax
0x180020474  jnz     short loc_18002049F
0x180020476  call    cs:__imp_GetLastError
0x18002047c  cmp     eax, 2
0x18002047f  jz      short loc_180020498
0x180020481  cmp     eax, 70h ; 'p'
0x180020484  jz      short loc_180020498
0x180020486  cmp     eax, 718h
0x18002048b  jz      short loc_18002049F
0x18002048d  mov     eax, 80004005h
0x180020492  add     rsp, 40h
0x180020496  pop     rbx
0x180020497  retn
0x180020498  mov     eax, 8007000Eh
0x18002049d  jmp     short loc_180020492
0x18002049f  xor     eax, eax
0x1800204a1  jmp     short loc_180020492
```
