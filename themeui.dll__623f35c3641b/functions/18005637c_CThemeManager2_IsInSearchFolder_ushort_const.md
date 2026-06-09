# CThemeManager2::_IsInSearchFolder(ushort const *)

- ea: `0x18005637c`
- end: `0x18005644a`
- name: `?_IsInSearchFolder@CThemeManager2@@AEAA_NPEBG@Z`
- size: `206`
- prototype: `bool(CThemeManager2 *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180053650`
- `0x180054ad0`

## callees

- `0x18000ed70`
- `0x1800358c0`
- `0x18005637c`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x1800563b9`
- `SHELL32!SHGetFolderPathEx` at `0x18005640a`
- `SHELL32!SHGetFolderPathEx` at `0x1800563b9`
- `SHELL32!SHGetFolderPathEx` at `0x18005640a`
- `SHLWAPI!PathIsPrefixW` at `0x1800563e5`
- `SHLWAPI!PathIsPrefixW` at `0x18005641c`
- `SHLWAPI!PathIsPrefixW` at `0x1800563e5`
- `SHLWAPI!PathIsPrefixW` at `0x18005641c`

## pseudocode

```c
bool __fastcall CThemeManager2::_IsInSearchFolder(CThemeManager2 *this, const unsigned __int16 *a2)
{
  BOOL IsPrefixW; // ebx
  WCHAR pszPrefix[264]; // [rsp+30h] [rbp-228h] BYREF

  IsPrefixW = 0;
  if ( ((int)SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, pszPrefix, 260) < 0
     || (int)StringCchCatW(pszPrefix, 0x104u, L"\\Microsoft\\Windows\\Themes") < 0
     || !(IsPrefixW = PathIsPrefixW(pszPrefix, a2)))
    && (int)SHGetFolderPathEx(&FOLDERID_ResourceDir, 0, 0, pszPrefix, 260) >= 0 )
  {
    return PathIsPrefixW(pszPrefix, a2);
  }
  return IsPrefixW;
}

```

## disassembly

```asm
0x18005637c  mov     [rsp+arg_0], rbx
0x180056381  push    rdi
0x180056382  sub     rsp, 250h
0x180056389  mov     rax, cs:__security_cookie
0x180056390  xor     rax, rsp
0x180056393  mov     [rsp+258h+var_18], rax
0x18005639b  mov     rdi, rdx
0x18005639e  mov     [rsp+258h+var_238], 104h
0x1800563a6  xor     edx, edx
0x1800563a8  lea     r9, [rsp+258h+pszPrefix]
0x1800563ad  xor     r8d, r8d
0x1800563b0  lea     rcx, FOLDERID_LocalAppData
0x1800563b7  xor     ebx, ebx
0x1800563b9  call    cs:__imp_SHGetFolderPathEx
0x1800563bf  test    eax, eax
0x1800563c1  js      short loc_1800563F1
0x1800563c3  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\Themes"
0x1800563ca  mov     edx, 104h; unsigned __int64
0x1800563cf  lea     rcx, [rsp+258h+pszPrefix]; unsigned __int16 *
0x1800563d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800563d9  test    eax, eax
0x1800563db  js      short loc_1800563F1
0x1800563dd  mov     rdx, rdi; pszPath
0x1800563e0  lea     rcx, [rsp+258h+pszPrefix]; pszPrefix
0x1800563e5  call    cs:__imp_PathIsPrefixW
0x1800563eb  mov     ebx, eax
0x1800563ed  test    eax, eax
0x1800563ef  jnz     short loc_180056424
0x1800563f1  lea     r9, [rsp+258h+pszPrefix]
0x1800563f6  mov     [rsp+258h+var_238], 104h
0x1800563fe  xor     r8d, r8d
0x180056401  lea     rcx, FOLDERID_ResourceDir
0x180056408  xor     edx, edx
0x18005640a  call    cs:__imp_SHGetFolderPathEx
0x180056410  test    eax, eax
0x180056412  js      short loc_180056424
0x180056414  mov     rdx, rdi; pszPath
0x180056417  lea     rcx, [rsp+258h+pszPrefix]; pszPrefix
0x18005641c  call    cs:__imp_PathIsPrefixW
0x180056422  mov     ebx, eax
0x180056424  test    ebx, ebx
0x180056426  setnz   al
0x180056429  mov     rcx, [rsp+258h+var_18]
0x180056431  xor     rcx, rsp; StackCookie
0x180056434  call    __security_check_cookie
0x180056439  mov     rbx, [rsp+258h+arg_0]
0x180056441  add     rsp, 250h
0x180056448  pop     rdi
0x180056449  retn
```
