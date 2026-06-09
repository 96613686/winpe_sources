# IsThemePack(ushort const *)

- ea: `0x180060374`
- end: `0x180060457`
- name: `?IsThemePack@@YA_NPEBG@Z`
- size: `227`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180053ea0`

## callees

- `0x18000ab10`
- `0x18000ed70`
- `0x1800358c0`
- `0x180060374`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x1800603ee`
- `SHELL32!SHGetFolderPathEx` at `0x1800603ee`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800603b9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800603c8`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800603b9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800603c8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060430`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060430`

## pseudocode

```c
bool __fastcall IsThemePack(const unsigned __int16 *a1)
{
  char v1; // bl
  WCHAR pszPath[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR String2[264]; // [rsp+240h] [rbp-228h] BYREF

  v1 = 0;
  if ( a1
    && (int)StringCchCopyW(pszPath, 0x104u, a1) >= 0
    && PathRemoveFileSpecW(pszPath)
    && PathRemoveFileSpecW(pszPath)
    && (int)SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, String2, 260) >= 0
    && (int)StringCchCatW(String2, 0x104u, L"\\Microsoft\\Windows\\Themes") >= 0 )
  {
    return CompareStringOrdinal(pszPath, -1, String2, -1, 1) == 2;
  }
  return v1;
}

```

## disassembly

```asm
0x180060374  push    rbx
0x180060376  sub     rsp, 460h
0x18006037d  mov     rax, cs:__security_cookie
0x180060384  xor     rax, rsp
0x180060387  mov     [rsp+468h+var_18], rax
0x18006038f  xor     bl, bl
0x180060391  test    rcx, rcx
0x180060394  jz      loc_18006043C
0x18006039a  mov     r8, rcx; unsigned __int16 *
0x18006039d  mov     edx, 104h; unsigned __int64
0x1800603a2  lea     rcx, [rsp+468h+pszPath]; unsigned __int16 *
0x1800603a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800603ac  test    eax, eax
0x1800603ae  js      loc_18006043C
0x1800603b4  lea     rcx, [rsp+468h+pszPath]; pszPath
0x1800603b9  call    cs:__imp_PathRemoveFileSpecW
0x1800603bf  test    eax, eax
0x1800603c1  jz      short loc_18006043C
0x1800603c3  lea     rcx, [rsp+468h+pszPath]; pszPath
0x1800603c8  call    cs:__imp_PathRemoveFileSpecW
0x1800603ce  test    eax, eax
0x1800603d0  jz      short loc_18006043C
0x1800603d2  lea     r9, [rsp+468h+String2]
0x1800603da  mov     [rsp+468h+bIgnoreCase], 104h
0x1800603e2  xor     r8d, r8d
0x1800603e5  lea     rcx, FOLDERID_LocalAppData
0x1800603ec  xor     edx, edx
0x1800603ee  call    cs:__imp_SHGetFolderPathEx
0x1800603f4  test    eax, eax
0x1800603f6  js      short loc_18006043C
0x1800603f8  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\Themes"
0x1800603ff  mov     edx, 104h; unsigned __int64
0x180060404  lea     rcx, [rsp+468h+String2]; unsigned __int16 *
0x18006040c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180060411  test    eax, eax
0x180060413  js      short loc_18006043C
0x180060415  or      edx, 0FFFFFFFFh; cchCount1
0x180060418  mov     [rsp+468h+bIgnoreCase], 1; bIgnoreCase
0x180060420  mov     r9d, edx; cchCount2
0x180060423  lea     r8, [rsp+468h+String2]; lpString2
0x18006042b  lea     rcx, [rsp+468h+pszPath]; lpString1
0x180060430  call    cs:__imp_CompareStringOrdinal
0x180060436  cmp     eax, 2
0x180060439  setz    bl
0x18006043c  mov     al, bl
0x18006043e  mov     rcx, [rsp+468h+var_18]
0x180060446  xor     rcx, rsp; StackCookie
0x180060449  call    __security_check_cookie
0x18006044e  add     rsp, 460h
0x180060455  pop     rbx
0x180060456  retn
```
