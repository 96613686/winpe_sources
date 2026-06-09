# PathIsDirectoryW

- ea: `0x180008300`
- end: `0x1800083f4`
- name: `PathIsDirectoryW`
- size: `244`
- prototype: `BOOL __stdcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180008300`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008358`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008358`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000834b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18000834b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180008323`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180008323`
- `MPR!WNetGetResourceInformationW` at `0x1800083ba`
- `MPR!WNetGetResourceInformationW` at `0x1800083ba`

## pseudocode

```c
BOOL __stdcall PathIsDirectoryW(LPCWSTR pszPath)
{
  BOOL result; // eax
  DWORD FileAttributesW; // edx
  LPWSTR lpSystem; // [rsp+20h] [rbp-428h] BYREF
  struct _NETRESOURCEW NetResource; // [rsp+30h] [rbp-418h] BYREF
  DWORD cbBuffer; // [rsp+430h] [rbp-18h] BYREF

  if ( !pszPath || PathIsUNCServerW(pszPath) )
    return 0;
  if ( PathIsUNCServerShareW(pszPath)
    && (memset_0(&NetResource.dwType, 0, 0x3FCu),
        lpSystem = 0,
        cbBuffer = 1024,
        *(_QWORD *)&NetResource.dwScope = 2,
        NetResource.lpRemoteName = (LPWSTR)pszPath,
        !WNetGetResourceInformationW(&NetResource, &NetResource, &cbBuffer, &lpSystem))
    && NetResource.dwDisplayType )
  {
    if ( NetResource.dwDisplayType != 3 )
      return 0;
    return !NetResource.dwType || NetResource.dwType == 1;
  }
  else
  {
    FileAttributesW = GetFileAttributesW(pszPath);
    result = 0;
    if ( FileAttributesW != -1 )
      return FileAttributesW & 0x10;
  }
  return result;
}

```

## disassembly

```asm
0x180008300  push    rbx
0x180008302  sub     rsp, 440h
0x180008309  mov     rax, cs:__security_cookie
0x180008310  xor     rax, rsp
0x180008313  mov     [rsp+448h+var_10], rax
0x18000831b  mov     rbx, rcx
0x18000831e  test    rcx, rcx
0x180008321  jz      short loc_18000832D
0x180008323  call    cs:__imp_PathIsUNCServerW
0x180008329  test    eax, eax
0x18000832b  jz      short loc_180008348
0x18000832d  xor     eax, eax
0x18000832f  mov     rcx, [rsp+448h+var_10]
0x180008337  xor     rcx, rsp; StackCookie
0x18000833a  call    __security_check_cookie
0x18000833f  add     rsp, 440h
0x180008346  pop     rbx
0x180008347  retn
0x180008348  mov     rcx, rbx; pszPath
0x18000834b  call    cs:__imp_PathIsUNCServerShareW
0x180008351  test    eax, eax
0x180008353  jnz     short loc_18000836F
0x180008355  mov     rcx, rbx; lpFileName
0x180008358  call    cs:__imp_GetFileAttributesW
0x18000835e  mov     ecx, eax
0x180008360  mov     edx, eax
0x180008362  and     ecx, 10h
0x180008365  xor     eax, eax
0x180008367  cmp     edx, 0FFFFFFFFh
0x18000836a  cmovnz  eax, ecx
0x18000836d  jmp     short loc_18000832F
0x18000836f  xor     edx, edx; Val
0x180008371  lea     rcx, [rsp+448h+NetResource.dwType]; void *
0x180008376  mov     r8d, 3FCh; Size
0x18000837c  call    memset_0
0x180008381  lea     r9, [rsp+448h+lpSystem]; lplpSystem
0x180008386  mov     [rsp+448h+lpSystem], 0
0x18000838f  lea     r8, [rsp+448h+cbBuffer]; lpcbBuffer
0x180008397  mov     [rsp+448h+cbBuffer], 400h
0x1800083a2  lea     rdx, [rsp+448h+NetResource]; lpBuffer
0x1800083a7  mov     qword ptr [rsp+448h+NetResource.dwScope], 2
0x1800083b0  lea     rcx, [rsp+448h+NetResource]; lpNetResource
0x1800083b5  mov     [rsp+448h+NetResource.lpRemoteName], rbx
0x1800083ba  call    cs:__imp_WNetGetResourceInformationW
0x1800083c0  test    eax, eax
0x1800083c2  jnz     short loc_180008355
0x1800083c4  mov     eax, [rsp+448h+NetResource.dwDisplayType]
0x1800083c8  test    eax, eax
0x1800083ca  jz      short loc_180008355
0x1800083cc  cmp     eax, 3
0x1800083cf  jnz     loc_18000832D
0x1800083d5  mov     ecx, [rsp+448h+NetResource.dwType]
0x1800083d9  test    ecx, ecx
0x1800083db  jz      short loc_1800083EA
0x1800083dd  xor     eax, eax
0x1800083df  cmp     ecx, 1
0x1800083e2  setz    al
0x1800083e5  jmp     loc_18000832F
0x1800083ea  mov     eax, 1
0x1800083ef  jmp     loc_18000832F
```
