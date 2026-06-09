# PathFileExistsAndAttributesA

- ea: `0x180018bd0`
- end: `0x180018ccd`
- name: `PathFileExistsAndAttributesA`
- size: `253`
- prototype: `__int64 __fastcall(LPCSTR pszPath)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018d28`
- `0x18001cbd0`

## callees

- `0x180012550`
- `0x180018bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180018c12`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180018ca2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180018c12`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180018ca2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180018c1d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180018c1d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x180018c32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x180018c32`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x180018c3f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x180018c3f`
- `MPR!WNetGetResourceInformationA` at `0x180018c8a`
- `MPR!WNetGetResourceInformationA` at `0x180018c8a`

## pseudocode

```c
__int64 __fastcall PathFileExistsAndAttributesA(CHAR *pszPath, DWORD *a2)
{
  unsigned int v2; // ebx
  UINT v5; // ebp
  DWORD FileAttributesA; // eax
  DWORD ResourceInformationA; // eax
  LPSTR lpSystem; // [rsp+20h] [rbp-168h] BYREF
  _NETRESOURCEA NetResource; // [rsp+28h] [rbp-160h] BYREF
  DWORD cbBuffer; // [rsp+58h] [rbp-130h] BYREF
  _BYTE Buffer[256]; // [rsp+60h] [rbp-128h] BYREF

  v2 = 0;
  if ( a2 )
    *a2 = -1;
  if ( pszPath )
  {
    v5 = SetErrorMode(1u);
    FileAttributesA = GetFileAttributesA(pszPath);
    if ( a2 )
      *a2 = FileAttributesA;
    if ( FileAttributesA != -1
      || (PathIsUNCServerA(pszPath) || PathIsUNCServerShareA(pszPath))
      && ((*(_QWORD *)&NetResource.dwScope = 2,
           NetResource.lpRemoteName = pszPath,
           cbBuffer = 256,
           lpSystem = 0,
           *(_OWORD *)&NetResource.dwDisplayType = 0,
           *(_OWORD *)&NetResource.lpComment = 0,
           (ResourceInformationA = WNetGetResourceInformationA(&NetResource, Buffer, &cbBuffer, &lpSystem)) == 0)
       || ResourceInformationA == 234) )
    {
      v2 = 1;
    }
    SetErrorMode(v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180018bd0  mov     [rsp+arg_10], rbx
0x180018bd5  push    rbp
0x180018bd6  push    rsi
0x180018bd7  push    rdi
0x180018bd8  sub     rsp, 170h
0x180018bdf  mov     rax, cs:__security_cookie
0x180018be6  xor     rax, rsp
0x180018be9  mov     [rsp+188h+var_28], rax
0x180018bf1  xor     ebx, ebx
0x180018bf3  mov     rsi, rdx
0x180018bf6  mov     rdi, rcx
0x180018bf9  test    rdx, rdx
0x180018bfc  jz      short loc_180018C04
0x180018bfe  mov     dword ptr [rdx], 0FFFFFFFFh
0x180018c04  test    rdi, rdi
0x180018c07  jz      loc_180018CA8
0x180018c0d  mov     ecx, 1; uMode
0x180018c12  call    cs:__imp_SetErrorMode
0x180018c18  mov     rcx, rdi; lpFileName
0x180018c1b  mov     ebp, eax
0x180018c1d  call    cs:__imp_GetFileAttributesA
0x180018c23  test    rsi, rsi
0x180018c26  jz      short loc_180018C2A
0x180018c28  mov     [rsi], eax
0x180018c2a  cmp     eax, 0FFFFFFFFh
0x180018c2d  jnz     short loc_180018C9B
0x180018c2f  mov     rcx, rdi; pszPath
0x180018c32  call    cs:__imp_PathIsUNCServerA
0x180018c38  test    eax, eax
0x180018c3a  jnz     short loc_180018C49
0x180018c3c  mov     rcx, rdi; pszPath
0x180018c3f  call    cs:__imp_PathIsUNCServerShareA
0x180018c45  test    eax, eax
0x180018c47  jz      short loc_180018CA0
0x180018c49  xorps   xmm0, xmm0
0x180018c4c  mov     qword ptr [rsp+188h+NetResource.dwScope], 2
0x180018c55  xorps   xmm1, xmm1
0x180018c58  mov     [rsp+188h+NetResource.lpRemoteName], rdi
0x180018c5d  lea     r9, [rsp+188h+lpSystem]; lplpSystem
0x180018c62  mov     [rsp+188h+cbBuffer], 100h
0x180018c6a  lea     r8, [rsp+188h+cbBuffer]; lpcbBuffer
0x180018c6f  mov     [rsp+188h+lpSystem], rbx
0x180018c74  lea     rdx, [rsp+188h+Buffer]; lpBuffer
0x180018c79  lea     rcx, [rsp+188h+NetResource]; lpNetResource
0x180018c7e  movdqu  xmmword ptr [rsp+188h+NetResource.dwDisplayType], xmm0
0x180018c84  movdqu  xmmword ptr [rsp+188h+NetResource.lpComment], xmm1
0x180018c8a  call    cs:__imp_WNetGetResourceInformationA
0x180018c90  test    eax, eax
0x180018c92  jz      short loc_180018C9B
0x180018c94  cmp     eax, 0EAh
0x180018c99  jnz     short loc_180018CA0
0x180018c9b  mov     ebx, 1
0x180018ca0  mov     ecx, ebp; uMode
0x180018ca2  call    cs:__imp_SetErrorMode
0x180018ca8  mov     eax, ebx
0x180018caa  mov     rcx, [rsp+188h+var_28]
0x180018cb2  xor     rcx, rsp; StackCookie
0x180018cb5  call    __security_check_cookie
0x180018cba  mov     rbx, [rsp+188h+arg_10]
0x180018cc2  add     rsp, 170h
0x180018cc9  pop     rdi
0x180018cca  pop     rsi
0x180018ccb  pop     rbp
0x180018ccc  retn
```
