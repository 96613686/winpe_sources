# SHGetVirtualizedFolderPath

- ea: `0x1800625c4`
- end: `0x180062682`
- name: `SHGetVirtualizedFolderPath`
- size: `190`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180061ac4`

## callees

- `0x18000ab10`
- `0x180030f64`
- `0x1800358c0`
- `0x1800625c4`

## import_xrefs

- `SHLWAPI!PathFindNextComponentW` at `0x180062621`
- `SHLWAPI!PathFindNextComponentW` at `0x180062621`
- `SHLWAPI!PathIsDirectoryW` at `0x1800625f8`
- `SHLWAPI!PathIsDirectoryW` at `0x1800625f8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180062634`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180062634`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062614`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180062614`

## pseudocode

```c
__int64 __fastcall SHGetVirtualizedFolderPath(LPCWSTR pszPath, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  const WCHAR *NextComponentW; // rax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  v4 = -2147024809;
  if ( pszPath && PathIsDirectoryW(pszPath) )
  {
    if ( !ExpandEnvironmentStringsW(L"%LOCALAPPDATA%\\VirtualStore", Dst, 0x104u) )
      return (unsigned int)ResultFromKnownLastError();
    NextComponentW = PathFindNextComponentW(pszPath);
    v4 = PathCchAppend(Dst, 0x104u, NextComponentW);
    if ( v4 >= 0 )
      return (unsigned int)StringCchCopyW(a2, 0x104u, Dst);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800625c4  mov     [rsp+arg_10], rbx
0x1800625c9  mov     [rsp+arg_18], rsi
0x1800625ce  push    rdi
0x1800625cf  sub     rsp, 240h
0x1800625d6  mov     rax, cs:__security_cookie
0x1800625dd  xor     rax, rsp
0x1800625e0  mov     [rsp+248h+var_18], rax
0x1800625e8  mov     rsi, rdx
0x1800625eb  mov     rdi, rcx
0x1800625ee  mov     ebx, 80070057h
0x1800625f3  test    rcx, rcx
0x1800625f6  jz      short loc_18006265B
0x1800625f8  call    cs:__imp_PathIsDirectoryW
0x1800625fe  test    eax, eax
0x180062600  jz      short loc_18006265B
0x180062602  mov     r8d, 104h; nSize
0x180062608  lea     rdx, [rsp+248h+Dst]; lpDst
0x18006260d  lea     rcx, aLocalappdataVi; "%LOCALAPPDATA%\\VirtualStore"
0x180062614  call    cs:__imp_ExpandEnvironmentStringsW
0x18006261a  test    eax, eax
0x18006261c  jz      short loc_180062654
0x18006261e  mov     rcx, rdi; pszPath
0x180062621  call    cs:__imp_PathFindNextComponentW
0x180062627  mov     edx, 104h; cchPath
0x18006262c  lea     rcx, [rsp+248h+Dst]; pszPath
0x180062631  mov     r8, rax; pszMore
0x180062634  call    cs:__imp_PathCchAppend
0x18006263a  mov     ebx, eax
0x18006263c  test    eax, eax
0x18006263e  js      short loc_18006265B
0x180062640  lea     r8, [rsp+248h+Dst]; unsigned __int16 *
0x180062645  mov     edx, 104h; unsigned __int64
0x18006264a  mov     rcx, rsi; unsigned __int16 *
0x18006264d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062652  jmp     short loc_180062659
0x180062654  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180062659  mov     ebx, eax
0x18006265b  mov     eax, ebx
0x18006265d  mov     rcx, [rsp+248h+var_18]
0x180062665  xor     rcx, rsp; StackCookie
0x180062668  call    __security_check_cookie
0x18006266d  lea     r11, [rsp+248h+var_8]
0x180062675  mov     rbx, [r11+20h]
0x180062679  mov     rsi, [r11+28h]
0x18006267d  mov     rsp, r11
0x180062680  pop     rdi
0x180062681  retn
```
