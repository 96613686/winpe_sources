# CThemeManager2::_IsOEMTheme(ITheme *)

- ea: `0x1800504c0`
- end: `0x180050555`
- name: `?_IsOEMTheme@CThemeManager2@@AEAA_NPEAUITheme@@@Z`
- size: `149`
- prototype: `bool __fastcall(CThemeManager2 *__hidden this, struct ITheme *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180050414`

## callees

- `0x18004d958`
- `0x1800504c0`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800504f8`
- `SHLWAPI!PathFindFileNameW` at `0x180050528`
- `SHLWAPI!PathFindFileNameW` at `0x1800504f8`
- `SHLWAPI!PathFindFileNameW` at `0x180050528`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180050517`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180050517`
- `OLEAUT32!__imp_SysFreeString` at `0x180050547`
- `OLEAUT32!__imp_SysFreeString` at `0x180050547`

## string_xrefs

- `0x180050535`: `PathFindFileName(bstrPath) = ('%ws') oemTheme=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CThemeManager2::_IsOEMTheme(CThemeManager2 *this, struct ITheme *a2)
{
  bool v2; // bl
  const WCHAR *FileNameW; // rax
  LPWSTR v4; // rax
  LPCWSTR pszPath; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  pszPath = 0;
  if ( (*(int (__fastcall **)(struct ITheme *, __int64, LPCWSTR *))(*(_QWORD *)a2 + 288LL))(a2, 0xFFFFFFFFLL, &pszPath) >= 0 )
  {
    FileNameW = PathFindFileNameW(pszPath);
    v2 = CompareStringOrdinal(FileNameW, -1, L"oem.theme", -1, 1) == 2;
    v4 = PathFindFileNameW(pszPath);
    ThemesTelemetry::TraceLoggingInfo("PathFindFileName(bstrPath) = ('%ws') oemTheme=%d", v4, v2);
  }
  SysFreeString((BSTR)pszPath);
  return v2;
}

```

## disassembly

```asm
0x1800504c0  mov     [rsp+pszPath], rcx
0x1800504c5  push    rbx
0x1800504c6  sub     rsp, 30h
0x1800504ca  mov     rcx, rdx
0x1800504cd  xor     bl, bl
0x1800504cf  mov     [rsp+38h+pszPath], 0
0x1800504d8  mov     rax, [rdx]
0x1800504db  or      edx, 0FFFFFFFFh
0x1800504de  lea     r8, [rsp+38h+pszPath]
0x1800504e3  mov     rax, [rax+120h]
0x1800504ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504ef  test    eax, eax
0x1800504f1  js      short loc_180050542
0x1800504f3  mov     rcx, [rsp+38h+pszPath]; pszPath
0x1800504f8  call    cs:__imp_PathFindFileNameW
0x1800504fe  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180050506  or      r9d, 0FFFFFFFFh; cchCount2
0x18005050a  lea     r8, aOemTheme_0; "oem.theme"
0x180050511  or      edx, r9d; cchCount1
0x180050514  mov     rcx, rax; lpString1
0x180050517  call    cs:__imp_CompareStringOrdinal
0x18005051d  cmp     eax, 2
0x180050520  setz    bl
0x180050523  mov     rcx, [rsp+38h+pszPath]; pszPath
0x180050528  call    cs:__imp_PathFindFileNameW
0x18005052e  movzx   r8d, bl
0x180050532  mov     rdx, rax
0x180050535  lea     rcx, aPathfindfilena; "PathFindFileName(bstrPath) = ('%ws') oe"...
0x18005053c  call    ?TraceLoggingInfo@ThemesTelemetry@@SAXPEBDZZ; ThemesTelemetry::TraceLoggingInfo(char const *,...)
0x180050541  nop
0x180050542  mov     rcx, [rsp+38h+pszPath]; bstrString
0x180050547  call    cs:__imp_SysFreeString
0x18005054d  mov     al, bl
0x18005054f  add     rsp, 30h
0x180050553  pop     rbx
0x180050554  retn
```
