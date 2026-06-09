# CThumbnailCacheAPI::_EnsureSystemDrivePath(void)

- ea: `0x180034650`
- end: `0x1800346e5`
- name: `?_EnsureSystemDrivePath@CThumbnailCacheAPI@@AEAAJXZ`
- size: `149`
- prototype: `int(CThumbnailCacheAPI *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18002ed6c`

## callees

- `0x18000bfd8`
- `0x180034650`
- `0x1800346ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180034672`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180034672`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x18003469c`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x18003469c`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800346cd`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800346cd`

## string_xrefs

- `0x180034681`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x1800346ad`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheAPI::_EnsureSystemDrivePath(WCHAR *this)
{
  WCHAR *v1; // rbx
  const char *v2; // r9
  HRESULT v4; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = this + 24;
  if ( !this[24] )
  {
    if ( !GetWindowsDirectoryW(this + 24, 0x104u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x1DD,
               (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
               v2);
    v4 = PathCchStripToRoot(v1, 0x104u);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v4,
        v6);
      return v5;
    }
    CharUpperBuffW(v1, 0x104u);
  }
  return 0;
}

```

## disassembly

```asm
0x180034650  mov     [rsp+arg_0], rbx
0x180034655  mov     [rsp+arg_8], rsi
0x18003465a  push    rdi; int
0x18003465b  sub     rsp, 20h
0x18003465f  lea     rbx, [rcx+30h]
0x180034663  xor     esi, esi
0x180034665  cmp     [rbx], si
0x180034668  jnz     short loc_1800346D3
0x18003466a  mov     edx, 104h; uSize
0x18003466f  mov     rcx, rbx; lpBuffer
0x180034672  call    cs:__imp_GetWindowsDirectoryW
0x180034678  test    eax, eax
0x18003467a  jnz     short loc_180034694
0x18003467c  mov     rcx, [rsp+28h]; this
0x180034681  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180034688  mov     edx, 1DDh; void *
0x18003468d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034692  jmp     short loc_1800346D5
0x180034694  mov     edx, 104h; cchPath
0x180034699  mov     rcx, rbx; pszPath
0x18003469c  call    cs:__imp_PathCchStripToRoot
0x1800346a2  mov     edi, eax
0x1800346a4  test    eax, eax
0x1800346a6  jns     short loc_1800346C5
0x1800346a8  mov     rcx, [rsp+28h]; this
0x1800346ad  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800346b4  mov     r9d, eax; char *
0x1800346b7  mov     edx, 1DEh; void *
0x1800346bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346c1  mov     eax, edi
0x1800346c3  jmp     short loc_1800346D5
0x1800346c5  mov     edx, 104h; cchLength
0x1800346ca  mov     rcx, rbx; lpsz
0x1800346cd  call    cs:__imp_CharUpperBuffW
0x1800346d3  xor     eax, eax
0x1800346d5  mov     rbx, [rsp+28h+arg_0]
0x1800346da  mov     rsi, [rsp+28h+arg_8]
0x1800346df  add     rsp, 20h
0x1800346e3  pop     rdi
0x1800346e4  retn
```
