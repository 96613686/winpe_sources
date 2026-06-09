# SortedCatalogOpen

- ea: `0x1800037cc`
- end: `0x1800038d8`
- name: `SortedCatalogOpen`
- size: `268`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003088`
- `0x180003920`

## callees

- `0x180003478`
- `0x180003510`
- `0x1800037cc`
- `0x18004deb0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800038c5`
- `msvcrt!_wcsicmp` at `0x1800038c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180003804`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180003804`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000389d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800038b0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000389d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800038b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000382e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000382e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003815`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003815`

## pseudocode

```c
struct _SORTED_CATALOG_INFO *__fastcall SortedCatalogOpen(wchar_t *Src)
{
  struct _SORTED_CATALOG_INFO *v2; // rbx
  __int64 v3; // rax
  const wchar_t *v5; // rdx
  __int128 FileInformation; // [rsp+20h] [rbp-38h] BYREF
  FILETIME FileTime1[2]; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+40h] [rbp-18h]

  FileInformation = 0;
  v8 = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  v2 = 0;
  if ( GetFileAttributesExW(Src, GetFileExInfoStandard, &FileInformation) )
  {
    EnterCriticalSection(&MSCAT_CriticalSection);
    v2 = pSortedCatalogInfoHead;
    if ( pSortedCatalogInfoHead )
    {
      do
      {
        v5 = (const wchar_t *)*((_QWORD *)v2 + 3);
        if ( v5 && !_wcsicmp(Src, v5) )
          break;
        v2 = *(struct _SORTED_CATALOG_INFO **)v2;
      }
      while ( v2 );
      if ( v2 )
      {
        if ( v8 != *((_DWORD *)v2 + 17)
          || FileTime1[1].dwHighDateTime != *((_DWORD *)v2 + 16)
          || CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, (const FILETIME *)((char *)v2 + 52))
          || CompareFileTime((const FILETIME *)((char *)&FileInformation + 4), (const FILETIME *)((char *)v2 + 36)) )
        {
          v2 = 0;
        }
        else
        {
          ++*((_DWORD *)v2 + 4);
        }
      }
    }
    LeaveCriticalSection(&MSCAT_CriticalSection);
    if ( !v2 )
    {
      v3 = SortedCatalogInfoCreate(Src);
      v2 = (struct _SORTED_CATALOG_INFO *)v3;
      if ( v3 )
        SortedCatalogInfoAdd(v3);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800037cc  mov     [rsp+arg_8], rbx
0x1800037d1  push    rdi
0x1800037d2  sub     rsp, 50h
0x1800037d6  mov     rax, cs:__security_cookie
0x1800037dd  xor     rax, rsp
0x1800037e0  mov     [rsp+58h+var_10], rax
0x1800037e5  xorps   xmm0, xmm0
0x1800037e8  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x1800037ed  xor     eax, eax
0x1800037ef  xor     edx, edx; fInfoLevelId
0x1800037f1  movups  [rsp+58h+FileInformation], xmm0
0x1800037f6  mov     [rsp+58h+var_18], eax
0x1800037fa  mov     rdi, rcx
0x1800037fd  movups  xmmword ptr [rsp+58h+FileTime1.dwLowDateTime], xmm0
0x180003802  xor     ebx, ebx
0x180003804  call    cs:__imp_GetFileAttributesExW
0x18000380a  test    eax, eax
0x18000380c  jz      short loc_180003851
0x18000380e  lea     rcx, ?MSCAT_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003815  call    cs:__imp_EnterCriticalSection
0x18000381b  mov     rbx, cs:?pSortedCatalogInfoHead@@3PEAU_SORTED_CATALOG_INFO@@EA; _SORTED_CATALOG_INFO * pSortedCatalogInfoHead
0x180003822  test    rbx, rbx
0x180003825  jnz     short loc_18000386C
0x180003827  lea     rcx, ?MSCAT_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000382e  call    cs:__imp_LeaveCriticalSection
0x180003834  test    rbx, rbx
0x180003837  jnz     short loc_180003851
0x180003839  mov     rcx, rdi; Src
0x18000383c  call    _SortedCatalogInfoCreate
0x180003841  mov     rbx, rax
0x180003844  test    rax, rax
0x180003847  jz      short loc_180003851
0x180003849  mov     rcx, rax
0x18000384c  call    _SortedCatalogInfoAdd
0x180003851  mov     rax, rbx
0x180003854  mov     rcx, [rsp+58h+var_10]
0x180003859  xor     rcx, rsp; StackCookie
0x18000385c  call    __security_check_cookie
0x180003861  mov     rbx, [rsp+58h+arg_8]
0x180003866  add     rsp, 50h
0x18000386a  pop     rdi
0x18000386b  retn
0x18000386c  mov     rdx, [rbx+18h]; String2
0x180003870  test    rdx, rdx
0x180003873  jnz     short loc_1800038C2
0x180003875  mov     rbx, [rbx]
0x180003878  test    rbx, rbx
0x18000387b  jnz     short loc_18000386C
0x18000387d  test    rbx, rbx
0x180003880  jz      short loc_180003827
0x180003882  mov     eax, [rbx+44h]
0x180003885  cmp     [rsp+58h+var_18], eax
0x180003889  jnz     short loc_1800038D1
0x18000388b  mov     eax, [rbx+40h]
0x18000388e  cmp     [rsp+58h+FileTime1.dwHighDateTime+8], eax
0x180003892  jnz     short loc_1800038D1
0x180003894  lea     rdx, [rbx+34h]; lpFileTime2
0x180003898  lea     rcx, [rsp+58h+FileTime1.dwHighDateTime]; lpFileTime1
0x18000389d  call    cs:__imp_CompareFileTime
0x1800038a3  test    eax, eax
0x1800038a5  jnz     short loc_1800038D1
0x1800038a7  lea     rdx, [rbx+24h]; lpFileTime2
0x1800038ab  lea     rcx, [rsp+58h+FileInformation+4]; lpFileTime1
0x1800038b0  call    cs:__imp_CompareFileTime
0x1800038b6  test    eax, eax
0x1800038b8  jnz     short loc_1800038D1
0x1800038ba  inc     dword ptr [rbx+10h]
0x1800038bd  jmp     loc_180003827
0x1800038c2  mov     rcx, rdi; String1
0x1800038c5  call    cs:__imp__wcsicmp
0x1800038cb  test    eax, eax
0x1800038cd  jnz     short loc_180003875
0x1800038cf  jmp     short loc_18000387D
0x1800038d1  xor     ebx, ebx
0x1800038d3  jmp     loc_180003827
```
