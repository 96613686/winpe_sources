# PathResolve

- ea: `0x1802bbb40`
- end: `0x1802bbccf`
- name: `PathResolve`
- size: `399`
- prototype: `int __stdcall(PWSTR pszPath, PZPCWSTR dirs, UINT fFlags)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180102bb0`
- `0x1805bf5ec`
- `0x1805c04c0`
- `0x1805c76b0`

## callees

- `0x1800d3e50`
- `0x1802bbb40`
- `0x1802f2114`
- `0x1805d9b0c`
- `0x1805da190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802bbb70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802bbb70`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802bbc51`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802bbc51`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1802bbba4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1802bbba4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1802bbc76`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1802bbc76`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802bbb8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802bbb8e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bbb7f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802bbb7f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802bbbed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802bbbed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802bbbd4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802bbbd4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathFindOnPathW` at `0x1802bbc1f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathFindOnPathW` at `0x1802bbc1f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_PathFindOnPathExW` at `0x1802bbc09`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_PathFindOnPathExW` at `0x1802bbc09`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802bbcb6`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18067a95e`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18067a9b3`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802bbcb6`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18067a95e`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18067a9b3`

## pseudocode

```c
int __stdcall PathResolve(PWSTR pszPath, PZPCWSTR dirs, UINT fFlags)
{
  char v3; // di
  unsigned int v6; // ebp
  UINT v7; // r14d
  unsigned int v9; // edx
  unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // r8
  int v12; // esi

  v3 = fFlags;
  v6 = (fFlags & 8) != 0 ? 0xFFFFFFD0 : 0;
  v7 = fFlags & 1;
  if ( (fFlags & 1) != 0 )
    SetLastError(2u);
  PathUnquoteSpacesW(pszPath);
  if ( PathIsRootW(pszPath) )
  {
    if ( !PathIsUNCServerW(pszPath) && !PathIsUNCServerShareW(pszPath) && *pszPath == 92 && !pszPath[1] )
    {
      if ( (v3 & 4) != 0 )
        v11 = (unsigned __int16 *)*dirs;
      else
        v11 = 0;
      PathQualifyDef(pszPath, 0x104u, v11);
    }
    return !v7 || (unsigned int)PathFileExistsAndAttributesW(pszPath, 0);
  }
  if ( PathIsFileSpecW(pszPath) )
  {
    if ( (v3 & 3) != 0 && !*PathFindExtensionW(pszPath) && (unsigned int)PathFindOnPathExW(pszPath, dirs, v6 + 63) )
      return 1;
    if ( !PathFindOnPathW(pszPath, dirs) )
      return 0;
    if ( (v3 & 0x10) == 0 || (unsigned int)PathIsAbsolute(pszPath) )
      return 1;
  }
  else
  {
    if ( PathIsURLW(pszPath) )
      return 0;
    if ( (v3 & 4) != 0 )
      v10 = (unsigned __int16 *)*dirs;
    else
      v10 = 0;
    PathQualifyDef(pszPath, 0x104u, v10);
    if ( !v7 )
      return 1;
    if ( (v3 & 3) == 0 || !(unsigned int)LookForExtensions(pszPath, dirs, 0, v6 + 63) )
    {
      v12 = 0;
      if ( !(unsigned int)PathFileExistsAndAttributesW(pszPath, 0) )
        return v12;
    }
    v12 = 1;
    if ( (v3 & 0x10) == 0 || (unsigned int)PathIsAbsolute(pszPath) )
      return v12;
  }
  if ( !(unsigned int)CombineWithCurrentDirectory(pszPath, v9) )
    return 0;
  return PathFileExistsAndAttributesW(pszPath, 0);
}

```

## disassembly

```asm
0x1802bbb40  push    rbx
0x1802bbb42  push    rbp
0x1802bbb43  push    rsi
0x1802bbb44  push    rdi
0x1802bbb45  push    r14
0x1802bbb47  push    r15
0x1802bbb49  sub     rsp, 28h
0x1802bbb4d  mov     eax, r8d
0x1802bbb50  mov     r14d, r8d
0x1802bbb53  and     al, 8
0x1802bbb55  mov     edi, r8d
0x1802bbb58  neg     al
0x1802bbb5a  mov     rsi, rdx
0x1802bbb5d  mov     rbx, rcx
0x1802bbb60  sbb     ebp, ebp
0x1802bbb62  and     ebp, 0FFFFFFD0h
0x1802bbb65  and     r14d, 1
0x1802bbb69  jz      short loc_1802BBB7C
0x1802bbb6b  mov     ecx, 2; dwErrCode
0x1802bbb70  call    cs:__imp_SetLastError
0x1802bbb77  nop     dword ptr [rax+rax+00h]
0x1802bbb7c  mov     rcx, rbx; lpsz
0x1802bbb7f  call    cs:__imp_PathUnquoteSpacesW
0x1802bbb86  nop     dword ptr [rax+rax+00h]
0x1802bbb8b  mov     rcx, rbx; pszPath
0x1802bbb8e  call    cs:__imp_PathIsRootW
0x1802bbb95  nop     dword ptr [rax+rax+00h]
0x1802bbb9a  xor     r15d, r15d
0x1802bbb9d  mov     rcx, rbx; pszPath
0x1802bbba0  test    eax, eax
0x1802bbba2  jz      short loc_1802BBBD4
0x1802bbba4  call    cs:__imp_PathIsUNCServerW
0x1802bbbab  nop     dword ptr [rax+rax+00h]
0x1802bbbb0  test    eax, eax
0x1802bbbb2  jz      loc_1802BBC73
0x1802bbbb8  test    r14d, r14d
0x1802bbbbb  jnz     loc_1802BBCB1
0x1802bbbc1  mov     eax, 1
0x1802bbbc6  add     rsp, 28h
0x1802bbbca  pop     r15
0x1802bbbcc  pop     r14
0x1802bbbce  pop     rdi
0x1802bbbcf  pop     rsi
0x1802bbbd0  pop     rbp
0x1802bbbd1  pop     rbx
0x1802bbbd2  retn
0x1802bbbd4  call    cs:__imp_PathIsFileSpecW
0x1802bbbdb  nop     dword ptr [rax+rax+00h]
0x1802bbbe0  test    eax, eax
0x1802bbbe2  jz      short loc_1802BBC4E
0x1802bbbe4  test    dil, 3
0x1802bbbe8  jz      short loc_1802BBC19
0x1802bbbea  mov     rcx, rbx; pszPath
0x1802bbbed  call    cs:__imp_PathFindExtensionW
0x1802bbbf4  nop     dword ptr [rax+rax+00h]
0x1802bbbf9  cmp     [rax], r15w
0x1802bbbfd  jnz     short loc_1802BBC19
0x1802bbbff  lea     r8d, [rbp+3Fh]
0x1802bbc03  mov     rdx, rsi
0x1802bbc06  mov     rcx, rbx
0x1802bbc09  call    cs:__imp_PathFindOnPathExW
0x1802bbc10  nop     dword ptr [rax+rax+00h]
0x1802bbc15  test    eax, eax
0x1802bbc17  jnz     short loc_1802BBBC1
0x1802bbc19  mov     rdx, rsi; ppszOtherDirs
0x1802bbc1c  mov     rcx, rbx; pszPath
0x1802bbc1f  call    cs:__imp_PathFindOnPathW
0x1802bbc26  nop     dword ptr [rax+rax+00h]
0x1802bbc2b  test    eax, eax
0x1802bbc2d  jnz     short loc_1802BBC33
0x1802bbc2f  xor     eax, eax
0x1802bbc31  jmp     short loc_1802BBBC6
0x1802bbc33  test    dil, 10h
0x1802bbc37  jz      short loc_1802BBBC1
0x1802bbc39  mov     rcx, rbx; pszPath
0x1802bbc3c  call    ?PathIsAbsolute@@YAHPEBG@Z; PathIsAbsolute(ushort const *)
0x1802bbc41  test    eax, eax
0x1802bbc43  jnz     loc_1802BBBC1
0x1802bbc49  jmp     loc_18067A949
0x1802bbc4e  mov     rcx, rbx; pszPath
0x1802bbc51  call    cs:__imp_PathIsURLW
0x1802bbc58  nop     dword ptr [rax+rax+00h]
0x1802bbc5d  test    eax, eax
0x1802bbc5f  jnz     short loc_1802BBC2F
0x1802bbc61  test    dil, 4
0x1802bbc65  jz      loc_18067A970
0x1802bbc6b  mov     r8, [rsi]
0x1802bbc6e  jmp     loc_18067A973
0x1802bbc73  mov     rcx, rbx; pszPath
0x1802bbc76  call    cs:__imp_PathIsUNCServerShareW
0x1802bbc7d  nop     dword ptr [rax+rax+00h]
0x1802bbc82  test    eax, eax
0x1802bbc84  jnz     loc_1802BBBB8
0x1802bbc8a  cmp     word ptr [rbx], 5Ch ; '\'
0x1802bbc8e  jnz     loc_1802BBBB8
0x1802bbc94  cmp     [rbx+2], r15w
0x1802bbc99  jnz     loc_1802BBBB8
0x1802bbc9f  test    dil, 4
0x1802bbca3  jz      loc_18067A930
0x1802bbca9  mov     r8, [rsi]
0x1802bbcac  jmp     loc_18067A933
0x1802bbcb1  xor     edx, edx
0x1802bbcb3  mov     rcx, rbx
0x1802bbcb6  call    cs:__imp_PathFileExistsAndAttributesW
0x1802bbcbd  nop     dword ptr [rax+rax+00h]
0x1802bbcc2  test    eax, eax
0x1802bbcc4  jnz     loc_1802BBBC1
0x1802bbcca  jmp     loc_1802BBC2F
0x18067a930  mov     r8, r15; unsigned __int16 *
0x18067a933  xor     r9d, r9d
0x18067a936  mov     edx, 104h; unsigned __int64
0x18067a93b  mov     rcx, rbx; unsigned __int16 *
0x18067a93e  call    PathQualifyDef
0x18067a943  nop
0x18067a944  jmp     loc_1802BBBB8
0x18067a949  mov     rcx, rbx; pszMore
0x18067a94c  call    ?CombineWithCurrentDirectory@@YAHPEAGI@Z; CombineWithCurrentDirectory(ushort *,uint)
0x18067a951  test    eax, eax
0x18067a953  jz      loc_1802BBC2F
0x18067a959  xor     edx, edx
0x18067a95b  mov     rcx, rbx
0x18067a95e  call    cs:__imp_PathFileExistsAndAttributesW
0x18067a965  nop     dword ptr [rax+rax+00h]
0x18067a96a  nop
0x18067a96b  jmp     loc_1802BBBC6
0x18067a970  mov     r8, r15; unsigned __int16 *
0x18067a973  mov     edx, 104h; unsigned __int64
0x18067a978  mov     r9d, 1
0x18067a97e  mov     rcx, rbx; unsigned __int16 *
0x18067a981  call    PathQualifyDef
0x18067a986  test    r14d, r14d
0x18067a989  jz      loc_1802BBBC1
0x18067a98f  test    dil, 3
0x18067a993  jz      short loc_18067A9AB
0x18067a995  lea     r9d, [rbp+3Fh]; unsigned int
0x18067a999  xor     r8d, r8d; int
0x18067a99c  mov     rdx, rsi; unsigned __int16 **
0x18067a99f  mov     rcx, rbx; unsigned __int16 *
0x18067a9a2  call    ?LookForExtensions@@YAHPEAGPEAPEBGHI@Z; LookForExtensions(ushort *,ushort const * *,int,uint)
0x18067a9a7  test    eax, eax
0x18067a9a9  jnz     short loc_18067A9C3
0x18067a9ab  xor     edx, edx
0x18067a9ad  mov     rcx, rbx
0x18067a9b0  mov     esi, r15d
0x18067a9b3  call    cs:__imp_PathFileExistsAndAttributesW
0x18067a9ba  nop     dword ptr [rax+rax+00h]
0x18067a9bf  test    eax, eax
0x18067a9c1  jz      short loc_18067A9DE
0x18067a9c3  mov     esi, 1
0x18067a9c8  test    dil, 10h
0x18067a9cc  jz      short loc_18067A9DE
0x18067a9ce  mov     rcx, rbx; pszPath
0x18067a9d1  call    ?PathIsAbsolute@@YAHPEBG@Z; PathIsAbsolute(ushort const *)
0x18067a9d6  test    eax, eax
0x18067a9d8  jz      loc_18067A949
0x18067a9de  mov     eax, esi
0x18067a9e0  jmp     loc_1802BBBC6
```
