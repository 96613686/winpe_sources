# CIEBrowserModeFilter::enumerateCacheEntries(ushort const *,bool,void *,long (*)(void *,_INTERNET_CACHE_ENTRY_INFOW *))

- ea: `0x180086f98`
- end: `0x1800872f3`
- name: `?enumerateCacheEntries@CIEBrowserModeFilter@@AEAAJPEBG_NPEAXP6AJ2PEAU_INTERNET_CACHE_ENTRY_INFOW@@@Z@Z`
- size: `859`
- prototype: `__int64 __fastcall(CIEBrowserModeFilter *this, const unsigned __int16 *, char, void *, int (*)(void *, struct _INTERNET_CACHE_ENTRY_INFOW *))`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b29b0`
- `0x1800b31d0`
- `0x1800b4be4`

## callees

- `0x180086f98`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180087119`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180087119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087089`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008722b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087089`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008722b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800872e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180087212`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800872e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180086ff7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180086ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800871d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800871d9`
- `WININET!FindCloseUrlCache` at `0x1800872bb`
- `WININET!FindCloseUrlCache` at `0x1800872bb`
- `WININET!FindNextUrlCacheEntryW` at `0x1800871bc`
- `WININET!FindNextUrlCacheEntryW` at `0x180087254`
- `WININET!FindNextUrlCacheEntryW` at `0x1800871bc`
- `WININET!FindNextUrlCacheEntryW` at `0x180087254`
- `WININET!FindFirstUrlCacheEntryExW` at `0x18008703f`
- `WININET!FindFirstUrlCacheEntryExW` at `0x1800870d5`
- `WININET!FindFirstUrlCacheEntryExW` at `0x18008703f`
- `WININET!FindFirstUrlCacheEntryExW` at `0x1800870d5`

## pseudocode

```c
__int64 __fastcall CIEBrowserModeFilter::enumerateCacheEntries(
        CIEBrowserModeFilter *this,
        const unsigned __int16 *a2,
        char a3,
        void *a4,
        int (*a5)(void *, struct _INTERNET_CACHE_ENTRY_INFOW *))
{
  struct _INTERNET_CACHE_ENTRY_INFOW *p_FirstCacheEntryInfo; // rdi
  unsigned int v6; // ebx
  DWORD v8; // r14d
  HANDLE ProcessHeap; // r12
  HANDLE FirstUrlCacheEntry; // r15
  struct _INTERNET_CACHE_ENTRY_INFOW *v11; // rsi
  signed int LastError; // eax
  struct _INTERNET_CACHE_ENTRY_INFOW *lpFirstCacheEntryInfo; // rax
  HANDLE v14; // rax
  const WCHAR *lpszSourceUrlName; // rcx
  __int64 v16; // r8
  unsigned int v17; // eax
  unsigned int v18; // ebx
  signed int v20; // eax
  struct _INTERNET_CACHE_ENTRY_INFOW *v21; // rax
  BOOL NextUrlCacheEntryW; // eax
  DWORD cbCacheEntryInfo; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+54h] [rbp-ACh]
  CIEBrowserModeFilter *v25; // [rsp+58h] [rbp-A8h]
  void *v26; // [rsp+60h] [rbp-A0h]
  int (*v27)(void *, struct _INTERNET_CACHE_ENTRY_INFOW *); // [rsp+68h] [rbp-98h]
  struct _INTERNET_CACHE_ENTRY_INFOW FirstCacheEntryInfo; // [rsp+70h] [rbp-90h] BYREF

  p_FirstCacheEntryInfo = &FirstCacheEntryInfo;
  v6 = 0;
  v27 = a5;
  v26 = a4;
  v8 = 748;
  v24 = a3;
  v25 = this;
  ProcessHeap = GetProcessHeap();
  FirstCacheEntryInfo.dwStructSize = 748;
  cbCacheEntryInfo = 748;
  FirstUrlCacheEntry = FindFirstUrlCacheEntryExW(a2, 0, 0xFFFFFFFF, 0, &FirstCacheEntryInfo, &cbCacheEntryInfo, 0, 0, 0);
  if ( FirstUrlCacheEntry )
  {
    v11 = &FirstCacheEntryInfo;
    goto LABEL_10;
  }
  v11 = 0;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 == -2147024774 )
  {
    v8 = cbCacheEntryInfo;
    lpFirstCacheEntryInfo = (struct _INTERNET_CACHE_ENTRY_INFOW *)HeapAlloc(ProcessHeap, 0, cbCacheEntryInfo);
    p_FirstCacheEntryInfo = lpFirstCacheEntryInfo;
    if ( !lpFirstCacheEntryInfo )
      return (unsigned int)-2147024882;
    lpFirstCacheEntryInfo->dwStructSize = v8;
    cbCacheEntryInfo = v8;
    v14 = FindFirstUrlCacheEntryExW(a2, 0, 0xFFFFFFFF, 0, lpFirstCacheEntryInfo, &cbCacheEntryInfo, 0, 0, 0);
    FirstUrlCacheEntry = v14;
    if ( v14 )
      v11 = p_FirstCacheEntryInfo;
    v6 = v14 == 0 ? 0x8007007A : 0;
  }
LABEL_9:
  if ( !v6 )
  {
    while ( 1 )
    {
LABEL_10:
      lpszSourceUrlName = v11->lpszSourceUrlName;
      if ( lpszSourceUrlName )
      {
        v16 = -1;
        do
          ++v16;
        while ( a2[v16] );
        if ( !StrCmpNW(lpszSourceUrlName, a2, v16)
          && (v24 || *(_QWORD *)v11->lpHeaderInfo < *(_QWORD *)((char *)v25 + 36)) )
        {
          v6 = ((__int64 (__fastcall *)(void *, struct _INTERNET_CACHE_ENTRY_INFOW *))v27)(v26, v11);
        }
      }
      if ( v6 )
        break;
      p_FirstCacheEntryInfo->dwStructSize = v8;
      cbCacheEntryInfo = v8;
      if ( !FindNextUrlCacheEntryW(FirstUrlCacheEntry, p_FirstCacheEntryInfo, &cbCacheEntryInfo) )
      {
        v11 = 0;
        v20 = GetLastError();
        v6 = v20;
        if ( v20 > 0 )
          v6 = (unsigned __int16)v20 | 0x80070000;
        if ( v6 == -2147024774 )
        {
          if ( &FirstCacheEntryInfo != p_FirstCacheEntryInfo )
            HeapFree(ProcessHeap, 0, p_FirstCacheEntryInfo);
          v8 = cbCacheEntryInfo;
          v21 = (struct _INTERNET_CACHE_ENTRY_INFOW *)HeapAlloc(ProcessHeap, 0, cbCacheEntryInfo);
          p_FirstCacheEntryInfo = v21;
          if ( !v21 )
          {
            v6 = -2147024882;
            break;
          }
          v21->dwStructSize = v8;
          cbCacheEntryInfo = v8;
          NextUrlCacheEntryW = FindNextUrlCacheEntryW(FirstUrlCacheEntry, v21, &cbCacheEntryInfo);
          if ( NextUrlCacheEntryW )
            v11 = p_FirstCacheEntryInfo;
          v6 = !NextUrlCacheEntryW ? 0x8007007A : 0;
        }
        goto LABEL_9;
      }
      v11 = p_FirstCacheEntryInfo;
    }
  }
  v17 = 0;
  if ( v6 != -2147024637 )
    v17 = v6;
  v18 = v17;
  if ( FirstUrlCacheEntry )
    FindCloseUrlCache(FirstUrlCacheEntry);
  if ( p_FirstCacheEntryInfo && &FirstCacheEntryInfo != p_FirstCacheEntryInfo )
    HeapFree(ProcessHeap, 0, p_FirstCacheEntryInfo);
  return v18;
}

```

## disassembly

```asm
0x180086f98  mov     [rsp-8+arg_0], rbx
0x180086f9d  push    rbp
0x180086f9e  push    rsi
0x180086f9f  push    rdi
0x180086fa0  push    r12
0x180086fa2  push    r13
0x180086fa4  push    r14
0x180086fa6  push    r15
0x180086fa8  lea     rbp, [rsp-270h]
0x180086fb0  sub     rsp, 370h
0x180086fb7  mov     rax, cs:__security_cookie
0x180086fbe  xor     rax, rsp
0x180086fc1  mov     [rbp+2A0h+var_40], rax
0x180086fc8  mov     rax, [rbp+2A0h+arg_20]
0x180086fcf  lea     rdi, [rsp+3A0h+FirstCacheEntryInfo]
0x180086fd4  xor     ebx, ebx
0x180086fd6  mov     [rsp+3A0h+var_338], rax
0x180086fdb  mov     [rsp+3A0h+cbCacheEntryInfo], ebx
0x180086fdf  mov     r13, rdx
0x180086fe2  mov     [rsp+3A0h+var_340], r9
0x180086fe7  mov     r14d, 2ECh
0x180086fed  mov     [rsp+3A0h+var_34C], r8b
0x180086ff2  mov     [rsp+3A0h+var_348], rcx
0x180086ff7  call    cs:__imp_GetProcessHeap
0x180086ffe  nop     dword ptr [rax+rax+00h]
0x180087003  mov     [rsp+3A0h+lpReserved], rbx; lpReserved
0x180087008  xor     r9d, r9d; GroupId
0x18008700b  mov     r12, rax
0x18008700e  mov     [rsp+3A0h+lpcbGroupAttributes], rbx; lpcbGroupAttributes
0x180087013  lea     rax, [rsp+3A0h+cbCacheEntryInfo]
0x180087018  mov     [rsp+3A0h+lpGroupAttributes], rbx; lpGroupAttributes
0x18008701d  mov     [rsp+3A0h+lpcbCacheEntryInfo], rax; lpcbCacheEntryInfo
0x180087022  or      r8d, 0FFFFFFFFh; dwFilter
0x180087026  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x18008702b  mov     [rsp+3A0h+FirstCacheEntryInfo.dwStructSize], r14d
0x180087030  xor     edx, edx; dwFlags
0x180087032  mov     [rsp+3A0h+lpFirstCacheEntryInfo], rax; lpFirstCacheEntryInfo
0x180087037  mov     rcx, r13; lpszUrlSearchPattern
0x18008703a  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x18008703f  call    cs:__imp_FindFirstUrlCacheEntryExW
0x180087046  nop     dword ptr [rax+rax+00h]
0x18008704b  mov     r15, rax
0x18008704e  test    rax, rax
0x180087051  jnz     loc_18008717B
0x180087057  mov     esi, ebx
0x180087059  call    cs:__imp_GetLastError
0x180087060  nop     dword ptr [rax+rax+00h]
0x180087065  xor     edx, edx; dwFlags
0x180087067  mov     ebx, eax
0x180087069  test    eax, eax
0x18008706b  jle     short loc_180087076
0x18008706d  movzx   ebx, ax
0x180087070  or      ebx, 80070000h
0x180087076  cmp     ebx, 8007007Ah
0x18008707c  jnz     short loc_1800870FA
0x18008707e  mov     r14d, [rsp+3A0h+cbCacheEntryInfo]
0x180087083  mov     rcx, r12; hHeap
0x180087086  mov     r8d, r14d; dwBytes
0x180087089  call    cs:__imp_HeapAlloc
0x180087090  nop     dword ptr [rax+rax+00h]
0x180087095  xor     ebx, ebx
0x180087097  mov     rdi, rax
0x18008709a  test    rax, rax
0x18008709d  jz      loc_180087279
0x1800870a3  mov     [rsp+3A0h+lpReserved], rbx; lpReserved
0x1800870a8  xor     r9d, r9d; GroupId
0x1800870ab  mov     [rax], r14d
0x1800870ae  or      r8d, 0FFFFFFFFh; dwFilter
0x1800870b2  mov     [rsp+3A0h+lpcbGroupAttributes], rbx; lpcbGroupAttributes
0x1800870b7  lea     rax, [rsp+3A0h+cbCacheEntryInfo]
0x1800870bc  mov     [rsp+3A0h+lpGroupAttributes], rbx; lpGroupAttributes
0x1800870c1  xor     edx, edx; dwFlags
0x1800870c3  mov     [rsp+3A0h+lpcbCacheEntryInfo], rax; lpcbCacheEntryInfo
0x1800870c8  mov     rcx, r13; lpszUrlSearchPattern
0x1800870cb  mov     [rsp+3A0h+lpFirstCacheEntryInfo], rdi; lpFirstCacheEntryInfo
0x1800870d0  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x1800870d5  call    cs:__imp_FindFirstUrlCacheEntryExW
0x1800870dc  nop     dword ptr [rax+rax+00h]
0x1800870e1  test    rax, rax
0x1800870e4  mov     r15, rax
0x1800870e7  cmovnz  rsi, rdi
0x1800870eb  neg     rax
0x1800870ee  sbb     ebx, ebx
0x1800870f0  not     ebx
0x1800870f2  and     ebx, 8007007Ah
0x1800870f8  xor     edx, edx
0x1800870fa  test    ebx, ebx
0x1800870fc  jnz     short loc_18008712F
0x1800870fe  mov     rcx, [rsi+8]; psz1
0x180087102  test    rcx, rcx
0x180087105  jz      short loc_18008712B
0x180087107  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008710b  inc     r8; nChar
0x18008710e  cmp     [r13+r8*2+0], dx
0x180087114  jnz     short loc_18008710B
0x180087116  mov     rdx, r13; psz2
0x180087119  call    cs:__imp_StrCmpNW
0x180087120  nop     dword ptr [rax+rax+00h]
0x180087125  xor     edx, edx
0x180087127  test    eax, eax
0x180087129  jz      short loc_180087187
0x18008712b  test    ebx, ebx
0x18008712d  jz      short loc_1800871A9
0x18008712f  cmp     ebx, 80070103h
0x180087135  mov     eax, edx
0x180087137  cmovnz  eax, ebx
0x18008713a  mov     ebx, eax
0x18008713c  test    r15, r15
0x18008713f  jnz     loc_1800872B8
0x180087145  test    rdi, rdi
0x180087148  jnz     loc_1800872CC
0x18008714e  mov     eax, ebx
0x180087150  mov     rcx, [rbp+2A0h+var_40]
0x180087157  xor     rcx, rsp; StackCookie
0x18008715a  call    __security_check_cookie
0x18008715f  mov     rbx, [rsp+3A0h+arg_0]
0x180087167  add     rsp, 370h
0x18008716e  pop     r15
0x180087170  pop     r14
0x180087172  pop     r13
0x180087174  pop     r12
0x180087176  pop     rdi
0x180087177  pop     rsi
0x180087178  pop     rbp
0x180087179  retn
0x18008717b  lea     rsi, [rsp+3A0h+FirstCacheEntryInfo]
0x180087180  xor     edx, edx
0x180087182  jmp     loc_1800870FE
0x180087187  cmp     [rsp+3A0h+var_34C], dl
0x18008718b  jz      loc_180087283
0x180087191  mov     rcx, [rsp+3A0h+var_340]
0x180087196  mov     rdx, rsi
0x180087199  mov     rax, [rsp+3A0h+var_338]
0x18008719e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871a3  mov     ebx, eax
0x1800871a5  xor     edx, edx
0x1800871a7  jmp     short loc_18008712B
0x1800871a9  mov     [rdi], r14d
0x1800871ac  lea     r8, [rsp+3A0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800871b1  mov     rdx, rdi; lpNextCacheEntryInfo
0x1800871b4  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x1800871b9  mov     rcx, r15; hEnumHandle
0x1800871bc  call    cs:__imp_FindNextUrlCacheEntryW
0x1800871c3  nop     dword ptr [rax+rax+00h]
0x1800871c8  xor     edx, edx
0x1800871ca  test    eax, eax
0x1800871cc  jz      short loc_1800871D6
0x1800871ce  mov     rsi, rdi
0x1800871d1  jmp     loc_1800870FE
0x1800871d6  mov     rsi, rdx
0x1800871d9  call    cs:__imp_GetLastError
0x1800871e0  nop     dword ptr [rax+rax+00h]
0x1800871e5  xor     edx, edx; dwFlags
0x1800871e7  mov     ebx, eax
0x1800871e9  test    eax, eax
0x1800871eb  jle     short loc_1800871F6
0x1800871ed  movzx   ebx, ax
0x1800871f0  or      ebx, 80070000h
0x1800871f6  cmp     ebx, 8007007Ah
0x1800871fc  jnz     loc_1800870FA
0x180087202  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x180087207  cmp     rax, rdi
0x18008720a  jz      short loc_18008721E
0x18008720c  mov     r8, rdi; lpMem
0x18008720f  mov     rcx, r12; hHeap
0x180087212  call    cs:__imp_HeapFree
0x180087219  nop     dword ptr [rax+rax+00h]
0x18008721e  mov     r14d, [rsp+3A0h+cbCacheEntryInfo]
0x180087223  xor     edx, edx; dwFlags
0x180087225  mov     r8d, r14d; dwBytes
0x180087228  mov     rcx, r12; hHeap
0x18008722b  call    cs:__imp_HeapAlloc
0x180087232  nop     dword ptr [rax+rax+00h]
0x180087237  xor     edx, edx
0x180087239  mov     rdi, rax
0x18008723c  test    rax, rax
0x18008723f  jz      short loc_1800872AE
0x180087241  mov     [rax], r14d
0x180087244  lea     r8, [rsp+3A0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180087249  mov     rdx, rax; lpNextCacheEntryInfo
0x18008724c  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x180087251  mov     rcx, r15; hEnumHandle
0x180087254  call    cs:__imp_FindNextUrlCacheEntryW
0x18008725b  nop     dword ptr [rax+rax+00h]
0x180087260  xor     edx, edx
0x180087262  test    eax, eax
0x180087264  cmovnz  rsi, rdi
0x180087268  neg     eax
0x18008726a  sbb     ebx, ebx
0x18008726c  not     ebx
0x18008726e  and     ebx, 8007007Ah
0x180087274  jmp     loc_1800870FA
0x180087279  mov     ebx, 8007000Eh
0x18008727e  jmp     loc_18008714E
0x180087283  mov     rcx, [rsi+50h]
0x180087287  mov     rdx, [rsp+3A0h+var_348]
0x18008728c  mov     eax, [rcx+4]
0x18008728f  cmp     eax, [rdx+28h]
0x180087292  jb      loc_180087191
0x180087298  jnz     loc_1800871A5
0x18008729e  mov     eax, [rdx+24h]
0x1800872a1  cmp     [rcx], eax
0x1800872a3  jnb     loc_1800871A5
0x1800872a9  jmp     loc_180087191
0x1800872ae  mov     ebx, 8007000Eh
0x1800872b3  jmp     loc_18008712F
0x1800872b8  mov     rcx, r15; hEnumHandle
0x1800872bb  call    cs:__imp_FindCloseUrlCache
0x1800872c2  nop     dword ptr [rax+rax+00h]
0x1800872c7  jmp     loc_180087145
0x1800872cc  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x1800872d1  cmp     rax, rdi
0x1800872d4  jz      loc_18008714E
0x1800872da  mov     r8, rdi; lpMem
0x1800872dd  xor     edx, edx; dwFlags
0x1800872df  mov     rcx, r12; hHeap
0x1800872e2  call    cs:__imp_HeapFree
0x1800872e9  nop     dword ptr [rax+rax+00h]
0x1800872ee  jmp     loc_18008714E
```
