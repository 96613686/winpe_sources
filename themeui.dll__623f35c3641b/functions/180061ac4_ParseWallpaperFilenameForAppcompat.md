# ParseWallpaperFilenameForAppcompat

- ea: `0x180061ac4`
- end: `0x180061bf5`
- name: `ParseWallpaperFilenameForAppcompat`
- size: `305`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180043224`

## callees

- `0x18000ab10`
- `0x1800358c0`
- `0x180052974`
- `0x180061ac4`
- `0x1800625c4`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180061b18`
- `SHLWAPI!PathFindFileNameW` at `0x180061b18`
- `SHLWAPI!PathFileExistsW` at `0x180061b62`
- `SHLWAPI!PathFileExistsW` at `0x180061ba4`
- `SHLWAPI!PathFileExistsW` at `0x180061b62`
- `SHLWAPI!PathFileExistsW` at `0x180061ba4`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180061b0f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180061b6f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180061b0f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180061b6f`
- `SHLWAPI!__imp_FixSlashesAndColonW` at `0x180061b06`
- `SHLWAPI!__imp_FixSlashesAndColonW` at `0x180061b06`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180061af3`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x180061af3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180061b29`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180061b93`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180061b29`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180061b93`

## pseudocode

```c
__int64 __fastcall ParseWallpaperFilenameForAppcompat(
        LPCWSTR pszPath,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  HRESULT v7; // ebx
  const WCHAR *FileNameW; // rsi
  struct IUnknown *v9; // rdx
  unsigned int v10; // r8d
  unsigned int v12[4]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR pszPatha[264]; // [rsp+30h] [rbp-238h] BYREF

  v7 = SHExpandEnvironmentStringsW(pszPath, a2, 260);
  if ( v7 < 0 )
    goto LABEL_12;
  FixSlashesAndColonW(a2);
  PathRemoveFileSpecW(a2);
  FileNameW = PathFindFileNameW(pszPath);
  v7 = PathCchAppend(a2, 0x104u, FileNameW);
  if ( v7 < 0 )
    goto LABEL_12;
  v12[0] = -1;
  SHMapUrlToZoneEx(a2, v9, v10, v12);
  if ( v12[0] )
  {
    if ( !a5 )
      goto LABEL_12;
  }
  if ( !PathFileExistsW(a2) )
  {
    PathRemoveFileSpecW(a2);
    v7 = SHGetVirtualizedFolderPath(a2, pszPatha);
    if ( v7 < 0 )
      goto LABEL_12;
    v7 = PathCchAppend(pszPatha, 0x104u, FileNameW);
    if ( v7 < 0 )
      goto LABEL_12;
    if ( !PathFileExistsW(pszPatha) )
    {
      v7 = -2147024894;
LABEL_12:
      *a2 = 0;
      return (unsigned int)v7;
    }
    v7 = StringCchCopyW(a2, 0x104u, pszPatha);
    if ( v7 < 0 )
      goto LABEL_12;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180061ac4  mov     [rsp+arg_10], rbx
0x180061ac9  push    rbp
0x180061aca  push    rsi
0x180061acb  push    rdi
0x180061acc  sub     rsp, 250h
0x180061ad3  mov     rax, cs:__security_cookie
0x180061ada  xor     rax, rsp
0x180061add  mov     [rsp+268h+var_28], rax
0x180061ae5  mov     ebp, 104h
0x180061aea  mov     rdi, rdx
0x180061aed  mov     r8d, ebp
0x180061af0  mov     rsi, rcx
0x180061af3  call    cs:__imp_SHExpandEnvironmentStringsW
0x180061af9  mov     ebx, eax
0x180061afb  test    eax, eax
0x180061afd  js      loc_180061BCB
0x180061b03  mov     rcx, rdi
0x180061b06  call    cs:__imp_FixSlashesAndColonW
0x180061b0c  mov     rcx, rdi; pszPath
0x180061b0f  call    cs:__imp_PathRemoveFileSpecW
0x180061b15  mov     rcx, rsi; pszPath
0x180061b18  call    cs:__imp_PathFindFileNameW
0x180061b1e  mov     edx, ebp; cchPath
0x180061b20  mov     rcx, rdi; pszPath
0x180061b23  mov     r8, rax; pszMore
0x180061b26  mov     rsi, rax
0x180061b29  call    cs:__imp_PathCchAppend
0x180061b2f  mov     ebx, eax
0x180061b31  test    eax, eax
0x180061b33  js      loc_180061BCB
0x180061b39  lea     r9, [rsp+268h+var_248]; unsigned int *
0x180061b3e  mov     [rsp+268h+var_248], 0FFFFFFFFh
0x180061b46  mov     rcx, rdi; unsigned __int16 *
0x180061b49  call    ?SHMapUrlToZoneEx@@YAJPEBGPEAUIUnknown@@KPEAK@Z; SHMapUrlToZoneEx(ushort const *,IUnknown *,ulong,ulong *)
0x180061b4e  cmp     [rsp+268h+var_248], 0
0x180061b53  jz      short loc_180061B5F
0x180061b55  cmp     [rsp+268h+arg_20], 0
0x180061b5d  jz      short loc_180061BCB
0x180061b5f  mov     rcx, rdi; pszPath
0x180061b62  call    cs:__imp_PathFileExistsW
0x180061b68  test    eax, eax
0x180061b6a  jnz     short loc_180061BD0
0x180061b6c  mov     rcx, rdi; pszPath
0x180061b6f  call    cs:__imp_PathRemoveFileSpecW
0x180061b75  lea     rdx, [rsp+268h+pszPath]; unsigned __int16 *
0x180061b7a  mov     rcx, rdi; pszPath
0x180061b7d  call    SHGetVirtualizedFolderPath
0x180061b82  mov     ebx, eax
0x180061b84  test    eax, eax
0x180061b86  js      short loc_180061BCB
0x180061b88  mov     r8, rsi; pszMore
0x180061b8b  lea     rcx, [rsp+268h+pszPath]; pszPath
0x180061b90  mov     rdx, rbp; cchPath
0x180061b93  call    cs:__imp_PathCchAppend
0x180061b99  mov     ebx, eax
0x180061b9b  test    eax, eax
0x180061b9d  js      short loc_180061BCB
0x180061b9f  lea     rcx, [rsp+268h+pszPath]; pszPath
0x180061ba4  call    cs:__imp_PathFileExistsW
0x180061baa  test    eax, eax
0x180061bac  jz      short loc_180061BC6
0x180061bae  lea     r8, [rsp+268h+pszPath]; unsigned __int16 *
0x180061bb3  mov     rdx, rbp; unsigned __int64
0x180061bb6  mov     rcx, rdi; unsigned __int16 *
0x180061bb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061bbe  mov     ebx, eax
0x180061bc0  test    eax, eax
0x180061bc2  jns     short loc_180061BD0
0x180061bc4  jmp     short loc_180061BCB
0x180061bc6  mov     ebx, 80070002h
0x180061bcb  xor     eax, eax
0x180061bcd  mov     [rdi], ax
0x180061bd0  mov     eax, ebx
0x180061bd2  mov     rcx, [rsp+268h+var_28]
0x180061bda  xor     rcx, rsp; StackCookie
0x180061bdd  call    __security_check_cookie
0x180061be2  mov     rbx, [rsp+268h+arg_10]
0x180061bea  add     rsp, 250h
0x180061bf1  pop     rdi
0x180061bf2  pop     rsi
0x180061bf3  pop     rbp
0x180061bf4  retn
```
