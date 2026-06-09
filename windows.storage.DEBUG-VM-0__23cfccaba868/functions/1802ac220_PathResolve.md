# PathResolve

- ea: `0x1802ac220`
- end: `0x1802ac368`
- name: `PathResolve`
- size: `328`
- prototype: `int __stdcall(PWSTR pszPath, PZPCWSTR dirs, UINT fFlags)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a77d0`
- `0x1805a332c`
- `0x1805a4294`
- `0x1805aaf00`

## callees

- `0x1801b77d0`
- `0x1802ac220`
- `0x1802e1900`
- `0x1805bc9c0`
- `0x1805bcfc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802ac250`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1802ac250`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802ac2fc`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x1802ac2fc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1802ac272`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1802ac272`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1802ac31b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1802ac31b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802ac262`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1802ac262`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802ac259`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x1802ac259`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802ac2ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1802ac2ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802ac29b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsFileSpecW` at `0x1802ac29b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathFindOnPathW` at `0x1802ac2d4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathFindOnPathW` at `0x1802ac2d4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_PathFindOnPathExW` at `0x1802ac2c4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_PathFindOnPathExW` at `0x1802ac2c4`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802ac355`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180657a44`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180657a93`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1802ac355`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180657a44`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x180657a93`

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
0x1802ac220  push    rbx
0x1802ac222  push    rbp
0x1802ac223  push    rsi
0x1802ac224  push    rdi
0x1802ac225  push    r14
0x1802ac227  push    r15
0x1802ac229  sub     rsp, 28h
0x1802ac22d  mov     eax, r8d
0x1802ac230  mov     r14d, r8d
0x1802ac233  and     al, 8
0x1802ac235  mov     edi, r8d
0x1802ac238  neg     al
0x1802ac23a  mov     rsi, rdx
0x1802ac23d  mov     rbx, rcx
0x1802ac240  sbb     ebp, ebp
0x1802ac242  and     ebp, 0FFFFFFD0h
0x1802ac245  and     r14d, 1
0x1802ac249  jz      short loc_1802AC256
0x1802ac24b  mov     ecx, 2; dwErrCode
0x1802ac250  call    cs:__imp_SetLastError
0x1802ac256  mov     rcx, rbx; lpsz
0x1802ac259  call    cs:__imp_PathUnquoteSpacesW
0x1802ac25f  mov     rcx, rbx; pszPath
0x1802ac262  call    cs:__imp_PathIsRootW
0x1802ac268  xor     r15d, r15d
0x1802ac26b  mov     rcx, rbx; pszPath
0x1802ac26e  test    eax, eax
0x1802ac270  jz      short loc_1802AC29B
0x1802ac272  call    cs:__imp_PathIsUNCServerW
0x1802ac278  test    eax, eax
0x1802ac27a  jz      loc_1802AC318
0x1802ac280  test    r14d, r14d
0x1802ac283  jnz     loc_1802AC350
0x1802ac289  mov     eax, 1
0x1802ac28e  add     rsp, 28h
0x1802ac292  pop     r15
0x1802ac294  pop     r14
0x1802ac296  pop     rdi
0x1802ac297  pop     rsi
0x1802ac298  pop     rbp
0x1802ac299  pop     rbx
0x1802ac29a  retn
0x1802ac29b  call    cs:__imp_PathIsFileSpecW
0x1802ac2a1  test    eax, eax
0x1802ac2a3  jz      short loc_1802AC2F9
0x1802ac2a5  test    dil, 3
0x1802ac2a9  jz      short loc_1802AC2CE
0x1802ac2ab  mov     rcx, rbx; pszPath
0x1802ac2ae  call    cs:__imp_PathFindExtensionW
0x1802ac2b4  cmp     [rax], r15w
0x1802ac2b8  jnz     short loc_1802AC2CE
0x1802ac2ba  lea     r8d, [rbp+3Fh]
0x1802ac2be  mov     rdx, rsi
0x1802ac2c1  mov     rcx, rbx
0x1802ac2c4  call    cs:__imp_PathFindOnPathExW
0x1802ac2ca  test    eax, eax
0x1802ac2cc  jnz     short loc_1802AC289
0x1802ac2ce  mov     rdx, rsi; ppszOtherDirs
0x1802ac2d1  mov     rcx, rbx; pszPath
0x1802ac2d4  call    cs:__imp_PathFindOnPathW
0x1802ac2da  test    eax, eax
0x1802ac2dc  jnz     short loc_1802AC2E2
0x1802ac2de  xor     eax, eax
0x1802ac2e0  jmp     short loc_1802AC28E
0x1802ac2e2  test    dil, 10h
0x1802ac2e6  jz      short loc_1802AC289
0x1802ac2e8  mov     rcx, rbx; pszPath
0x1802ac2eb  call    ?PathIsAbsolute@@YAHPEBG@Z; PathIsAbsolute(ushort const *)
0x1802ac2f0  test    eax, eax
0x1802ac2f2  jnz     short loc_1802AC289
0x1802ac2f4  jmp     loc_180657A2F
0x1802ac2f9  mov     rcx, rbx; pszPath
0x1802ac2fc  call    cs:__imp_PathIsURLW
0x1802ac302  test    eax, eax
0x1802ac304  jnz     short loc_1802AC2DE
0x1802ac306  test    dil, 4
0x1802ac30a  jz      loc_180657A50
0x1802ac310  mov     r8, [rsi]
0x1802ac313  jmp     loc_180657A53
0x1802ac318  mov     rcx, rbx; pszPath
0x1802ac31b  call    cs:__imp_PathIsUNCServerShareW
0x1802ac321  test    eax, eax
0x1802ac323  jnz     loc_1802AC280
0x1802ac329  cmp     word ptr [rbx], 5Ch ; '\'
0x1802ac32d  jnz     loc_1802AC280
0x1802ac333  cmp     [rbx+2], r15w
0x1802ac338  jnz     loc_1802AC280
0x1802ac33e  test    dil, 4
0x1802ac342  jz      loc_180657A16
0x1802ac348  mov     r8, [rsi]
0x1802ac34b  jmp     loc_180657A19
0x1802ac350  xor     edx, edx
0x1802ac352  mov     rcx, rbx
0x1802ac355  call    cs:__imp_PathFileExistsAndAttributesW
0x1802ac35b  test    eax, eax
0x1802ac35d  jnz     loc_1802AC289
0x1802ac363  jmp     loc_1802AC2DE
0x180657a16  mov     r8, r15; unsigned __int16 *
0x180657a19  xor     r9d, r9d
0x180657a1c  mov     edx, 104h; unsigned __int64
0x180657a21  mov     rcx, rbx; unsigned __int16 *
0x180657a24  call    PathQualifyDef
0x180657a29  nop
0x180657a2a  jmp     loc_1802AC280
0x180657a2f  mov     rcx, rbx; pszMore
0x180657a32  call    ?CombineWithCurrentDirectory@@YAHPEAGI@Z; CombineWithCurrentDirectory(ushort *,uint)
0x180657a37  test    eax, eax
0x180657a39  jz      loc_1802AC2DE
0x180657a3f  xor     edx, edx
0x180657a41  mov     rcx, rbx
0x180657a44  call    cs:__imp_PathFileExistsAndAttributesW
0x180657a4a  nop
0x180657a4b  jmp     loc_1802AC28E
0x180657a50  mov     r8, r15; unsigned __int16 *
0x180657a53  mov     edx, 104h; unsigned __int64
0x180657a58  mov     r9d, 1
0x180657a5e  mov     rcx, rbx; unsigned __int16 *
0x180657a61  call    PathQualifyDef
0x180657a66  test    r14d, r14d
0x180657a69  jz      loc_1802AC289
0x180657a6f  test    dil, 3
0x180657a73  jz      short loc_180657A8B
0x180657a75  lea     r9d, [rbp+3Fh]; unsigned int
0x180657a79  xor     r8d, r8d; int
0x180657a7c  mov     rdx, rsi; unsigned __int16 **
0x180657a7f  mov     rcx, rbx; unsigned __int16 *
0x180657a82  call    ?LookForExtensions@@YAHPEAGPEAPEBGHI@Z; LookForExtensions(ushort *,ushort const * *,int,uint)
0x180657a87  test    eax, eax
0x180657a89  jnz     short loc_180657A9D
0x180657a8b  xor     edx, edx
0x180657a8d  mov     rcx, rbx
0x180657a90  mov     esi, r15d
0x180657a93  call    cs:__imp_PathFileExistsAndAttributesW
0x180657a99  test    eax, eax
0x180657a9b  jz      short loc_180657AB8
0x180657a9d  mov     esi, 1
0x180657aa2  test    dil, 10h
0x180657aa6  jz      short loc_180657AB8
0x180657aa8  mov     rcx, rbx; pszPath
0x180657aab  call    ?PathIsAbsolute@@YAHPEBG@Z; PathIsAbsolute(ushort const *)
0x180657ab0  test    eax, eax
0x180657ab2  jz      loc_180657A2F
0x180657ab8  mov     eax, esi
0x180657aba  jmp     loc_1802AC28E
```
