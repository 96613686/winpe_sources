# CIEBrowserModeFilter::enumerateCacheEntries(ushort const *,bool,void *,long (*)(void *,_INTERNET_CACHE_ENTRY_INFOW *))

- ea: `0x180081494`
- end: `0x18008179d`
- name: `?enumerateCacheEntries@CIEBrowserModeFilter@@AEAAJPEBG_NPEAXP6AJ2PEAU_INTERNET_CACHE_ENTRY_INFOW@@@Z@Z`
- size: `777`
- prototype: `int(CIEBrowserModeFilter *__hidden this, const unsigned __int16 *, bool, void *, int (*)(void *, struct _INTERNET_CACHE_ENTRY_INFOW *))`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800ab7c0`
- `0x1800abfa0`
- `0x1800ad83c`

## callees

- `0x180081494`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800815f7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x1800815f7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081573`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800816ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180081573`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800816ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800816da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081792`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800816da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081792`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800814f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800814f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800816a7`
- `WININET!FindCloseUrlCache` at `0x180081771`
- `WININET!FindCloseUrlCache` at `0x180081771`
- `WININET!FindNextUrlCacheEntryW` at `0x180081690`
- `WININET!FindNextUrlCacheEntryW` at `0x180081710`
- `WININET!FindNextUrlCacheEntryW` at `0x180081690`
- `WININET!FindNextUrlCacheEntryW` at `0x180081710`
- `WININET!FindFirstUrlCacheEntryExW` at `0x180081535`
- `WININET!FindFirstUrlCacheEntryExW` at `0x1800815b9`
- `WININET!FindFirstUrlCacheEntryExW` at `0x180081535`
- `WININET!FindFirstUrlCacheEntryExW` at `0x1800815b9`

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
0x180081494  mov     [rsp-8+arg_0], rbx
0x180081499  push    rbp
0x18008149a  push    rsi
0x18008149b  push    rdi
0x18008149c  push    r12
0x18008149e  push    r13
0x1800814a0  push    r14
0x1800814a2  push    r15
0x1800814a4  lea     rbp, [rsp-270h]
0x1800814ac  sub     rsp, 370h
0x1800814b3  mov     rax, cs:__security_cookie
0x1800814ba  xor     rax, rsp
0x1800814bd  mov     [rbp+2A0h+var_40], rax
0x1800814c4  mov     rax, [rbp+2A0h+arg_20]
0x1800814cb  lea     rdi, [rsp+3A0h+FirstCacheEntryInfo]
0x1800814d0  xor     ebx, ebx
0x1800814d2  mov     [rsp+3A0h+var_338], rax
0x1800814d7  mov     [rsp+3A0h+cbCacheEntryInfo], ebx
0x1800814db  mov     r13, rdx
0x1800814de  mov     [rsp+3A0h+var_340], r9
0x1800814e3  mov     r14d, 2ECh
0x1800814e9  mov     [rsp+3A0h+var_34C], r8b
0x1800814ee  mov     [rsp+3A0h+var_348], rcx
0x1800814f3  call    cs:__imp_GetProcessHeap
0x1800814f9  mov     [rsp+3A0h+lpReserved], rbx; lpReserved
0x1800814fe  xor     r9d, r9d; GroupId
0x180081501  mov     r12, rax
0x180081504  mov     [rsp+3A0h+lpcbGroupAttributes], rbx; lpcbGroupAttributes
0x180081509  lea     rax, [rsp+3A0h+cbCacheEntryInfo]
0x18008150e  mov     [rsp+3A0h+lpGroupAttributes], rbx; lpGroupAttributes
0x180081513  mov     [rsp+3A0h+lpcbCacheEntryInfo], rax; lpcbCacheEntryInfo
0x180081518  or      r8d, 0FFFFFFFFh; dwFilter
0x18008151c  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x180081521  mov     [rsp+3A0h+FirstCacheEntryInfo.dwStructSize], r14d
0x180081526  xor     edx, edx; dwFlags
0x180081528  mov     [rsp+3A0h+lpFirstCacheEntryInfo], rax; lpFirstCacheEntryInfo
0x18008152d  mov     rcx, r13; lpszUrlSearchPattern
0x180081530  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x180081535  call    cs:__imp_FindFirstUrlCacheEntryExW
0x18008153b  mov     r15, rax
0x18008153e  test    rax, rax
0x180081541  jnz     loc_180081652
0x180081547  mov     esi, ebx
0x180081549  call    cs:__imp_GetLastError
0x18008154f  xor     edx, edx; dwFlags
0x180081551  mov     ebx, eax
0x180081553  test    eax, eax
0x180081555  jle     short loc_180081560
0x180081557  movzx   ebx, ax
0x18008155a  or      ebx, 80070000h
0x180081560  cmp     ebx, 8007007Ah
0x180081566  jnz     short loc_1800815D8
0x180081568  mov     r14d, [rsp+3A0h+cbCacheEntryInfo]
0x18008156d  mov     rcx, r12; hHeap
0x180081570  mov     r8d, r14d; dwBytes
0x180081573  call    cs:__imp_HeapAlloc
0x180081579  xor     ebx, ebx
0x18008157b  mov     rdi, rax
0x18008157e  test    rax, rax
0x180081581  jz      loc_18008172F
0x180081587  mov     [rsp+3A0h+lpReserved], rbx; lpReserved
0x18008158c  xor     r9d, r9d; GroupId
0x18008158f  mov     [rax], r14d
0x180081592  or      r8d, 0FFFFFFFFh; dwFilter
0x180081596  mov     [rsp+3A0h+lpcbGroupAttributes], rbx; lpcbGroupAttributes
0x18008159b  lea     rax, [rsp+3A0h+cbCacheEntryInfo]
0x1800815a0  mov     [rsp+3A0h+lpGroupAttributes], rbx; lpGroupAttributes
0x1800815a5  xor     edx, edx; dwFlags
0x1800815a7  mov     [rsp+3A0h+lpcbCacheEntryInfo], rax; lpcbCacheEntryInfo
0x1800815ac  mov     rcx, r13; lpszUrlSearchPattern
0x1800815af  mov     [rsp+3A0h+lpFirstCacheEntryInfo], rdi; lpFirstCacheEntryInfo
0x1800815b4  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x1800815b9  call    cs:__imp_FindFirstUrlCacheEntryExW
0x1800815bf  test    rax, rax
0x1800815c2  mov     r15, rax
0x1800815c5  cmovnz  rsi, rdi
0x1800815c9  neg     rax
0x1800815cc  sbb     ebx, ebx
0x1800815ce  not     ebx
0x1800815d0  and     ebx, 8007007Ah
0x1800815d6  xor     edx, edx
0x1800815d8  test    ebx, ebx
0x1800815da  jnz     short loc_180081607
0x1800815dc  mov     rcx, [rsi+8]; psz1
0x1800815e0  test    rcx, rcx
0x1800815e3  jz      short loc_180081603
0x1800815e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800815e9  inc     r8; nChar
0x1800815ec  cmp     [r13+r8*2+0], dx
0x1800815f2  jnz     short loc_1800815E9
0x1800815f4  mov     rdx, r13; psz2
0x1800815f7  call    cs:__imp_StrCmpNW
0x1800815fd  xor     edx, edx
0x1800815ff  test    eax, eax
0x180081601  jz      short loc_18008165B
0x180081603  test    ebx, ebx
0x180081605  jz      short loc_18008167D
0x180081607  cmp     ebx, 80070103h
0x18008160d  mov     eax, edx
0x18008160f  cmovnz  eax, ebx
0x180081612  mov     ebx, eax
0x180081614  test    r15, r15
0x180081617  jnz     loc_18008176E
0x18008161d  test    rdi, rdi
0x180081620  jnz     loc_18008177C
0x180081626  mov     eax, ebx
0x180081628  mov     rcx, [rbp+2A0h+var_40]
0x18008162f  xor     rcx, rsp; StackCookie
0x180081632  call    __security_check_cookie
0x180081637  mov     rbx, [rsp+3A0h+arg_0]
0x18008163f  add     rsp, 370h
0x180081646  pop     r15
0x180081648  pop     r14
0x18008164a  pop     r13
0x18008164c  pop     r12
0x18008164e  pop     rdi
0x18008164f  pop     rsi
0x180081650  pop     rbp
0x180081651  retn
0x180081652  lea     rsi, [rsp+3A0h+FirstCacheEntryInfo]
0x180081657  xor     edx, edx
0x180081659  jmp     short loc_1800815DC
0x18008165b  cmp     [rsp+3A0h+var_34C], dl
0x18008165f  jz      loc_180081739
0x180081665  mov     rcx, [rsp+3A0h+var_340]
0x18008166a  mov     rdx, rsi
0x18008166d  mov     rax, [rsp+3A0h+var_338]
0x180081672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081677  mov     ebx, eax
0x180081679  xor     edx, edx
0x18008167b  jmp     short loc_180081603
0x18008167d  mov     [rdi], r14d
0x180081680  lea     r8, [rsp+3A0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180081685  mov     rdx, rdi; lpNextCacheEntryInfo
0x180081688  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x18008168d  mov     rcx, r15; hEnumHandle
0x180081690  call    cs:__imp_FindNextUrlCacheEntryW
0x180081696  xor     edx, edx
0x180081698  test    eax, eax
0x18008169a  jz      short loc_1800816A4
0x18008169c  mov     rsi, rdi
0x18008169f  jmp     loc_1800815DC
0x1800816a4  mov     rsi, rdx
0x1800816a7  call    cs:__imp_GetLastError
0x1800816ad  xor     edx, edx; dwFlags
0x1800816af  mov     ebx, eax
0x1800816b1  test    eax, eax
0x1800816b3  jle     short loc_1800816BE
0x1800816b5  movzx   ebx, ax
0x1800816b8  or      ebx, 80070000h
0x1800816be  cmp     ebx, 8007007Ah
0x1800816c4  jnz     loc_1800815D8
0x1800816ca  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x1800816cf  cmp     rax, rdi
0x1800816d2  jz      short loc_1800816E0
0x1800816d4  mov     r8, rdi; lpMem
0x1800816d7  mov     rcx, r12; hHeap
0x1800816da  call    cs:__imp_HeapFree
0x1800816e0  mov     r14d, [rsp+3A0h+cbCacheEntryInfo]
0x1800816e5  xor     edx, edx; dwFlags
0x1800816e7  mov     r8d, r14d; dwBytes
0x1800816ea  mov     rcx, r12; hHeap
0x1800816ed  call    cs:__imp_HeapAlloc
0x1800816f3  xor     edx, edx
0x1800816f5  mov     rdi, rax
0x1800816f8  test    rax, rax
0x1800816fb  jz      short loc_180081764
0x1800816fd  mov     [rax], r14d
0x180081700  lea     r8, [rsp+3A0h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180081705  mov     rdx, rax; lpNextCacheEntryInfo
0x180081708  mov     [rsp+3A0h+cbCacheEntryInfo], r14d
0x18008170d  mov     rcx, r15; hEnumHandle
0x180081710  call    cs:__imp_FindNextUrlCacheEntryW
0x180081716  xor     edx, edx
0x180081718  test    eax, eax
0x18008171a  cmovnz  rsi, rdi
0x18008171e  neg     eax
0x180081720  sbb     ebx, ebx
0x180081722  not     ebx
0x180081724  and     ebx, 8007007Ah
0x18008172a  jmp     loc_1800815D8
0x18008172f  mov     ebx, 8007000Eh
0x180081734  jmp     loc_180081626
0x180081739  mov     rcx, [rsi+50h]
0x18008173d  mov     rdx, [rsp+3A0h+var_348]
0x180081742  mov     eax, [rcx+4]
0x180081745  cmp     eax, [rdx+28h]
0x180081748  jb      loc_180081665
0x18008174e  jnz     loc_180081679
0x180081754  mov     eax, [rdx+24h]
0x180081757  cmp     [rcx], eax
0x180081759  jnb     loc_180081679
0x18008175f  jmp     loc_180081665
0x180081764  mov     ebx, 8007000Eh
0x180081769  jmp     loc_180081607
0x18008176e  mov     rcx, r15; hEnumHandle
0x180081771  call    cs:__imp_FindCloseUrlCache
0x180081777  jmp     loc_18008161D
0x18008177c  lea     rax, [rsp+3A0h+FirstCacheEntryInfo]
0x180081781  cmp     rax, rdi
0x180081784  jz      loc_180081626
0x18008178a  mov     r8, rdi; lpMem
0x18008178d  xor     edx, edx; dwFlags
0x18008178f  mov     rcx, r12; hHeap
0x180081792  call    cs:__imp_HeapFree
0x180081798  jmp     loc_180081626
```
