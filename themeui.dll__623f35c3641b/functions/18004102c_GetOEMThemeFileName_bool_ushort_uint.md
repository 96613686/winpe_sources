# GetOEMThemeFileName(bool,ushort *,uint)

- ea: `0x18004102c`
- end: `0x1800410bc`
- name: `?GetOEMThemeFileName@@YAJ_NPEAGI@Z`
- size: `144`
- prototype: `int(bool, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180040fcc`
- `0x1800410c4`

## callees

- `0x18000ed70`
- `0x18004102c`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180041053`
- `SHELL32!SHGetFolderPathEx` at `0x180041053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041089`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004107f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004107f`

## pseudocode

```c
__int64 __fastcall GetOEMThemeFileName(char a1, unsigned __int16 *a2)
{
  __int64 result; // rax

  result = SHGetFolderPathEx(&FOLDERID_LocalAppData, 0, 0, a2, 260);
  if ( (int)result >= 0 )
  {
    result = StringCchCatW(a2, 0x104u, L"\\Microsoft\\Windows\\Themes");
    if ( (int)result >= 0 )
    {
      if ( !a1 || CreateDirectoryW(a2, 0) || GetLastError() == 183 )
        return StringCchCatW(a2, 0x104u, L"\\oem.theme");
      else
        return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004102c  mov     [rsp+arg_0], rbx
0x180041031  push    rdi
0x180041032  sub     rsp, 30h
0x180041036  mov     rbx, rdx
0x180041039  mov     [rsp+38h+var_18], 104h
0x180041041  mov     dil, cl
0x180041044  mov     r9, rdx
0x180041047  xor     edx, edx
0x180041049  lea     rcx, FOLDERID_LocalAppData
0x180041050  xor     r8d, r8d
0x180041053  call    cs:__imp_SHGetFolderPathEx
0x180041059  test    eax, eax
0x18004105b  js      short loc_1800410B1
0x18004105d  lea     r8, aMicrosoftWindo_2; "\\Microsoft\\Windows\\Themes"
0x180041064  mov     edx, 104h; unsigned __int64
0x180041069  mov     rcx, rbx; unsigned __int16 *
0x18004106c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041071  test    eax, eax
0x180041073  js      short loc_1800410B1
0x180041075  test    dil, dil
0x180041078  jz      short loc_18004109D
0x18004107a  xor     edx, edx; lpSecurityAttributes
0x18004107c  mov     rcx, rbx; lpPathName
0x18004107f  call    cs:__imp_CreateDirectoryW
0x180041085  test    eax, eax
0x180041087  jnz     short loc_18004109D
0x180041089  call    cs:__imp_GetLastError
0x18004108f  cmp     eax, 0B7h
0x180041094  jz      short loc_18004109D
0x180041096  mov     eax, 80004005h
0x18004109b  jmp     short loc_1800410B1
0x18004109d  lea     r8, aOemTheme; "\\oem.theme"
0x1800410a4  mov     edx, 104h; unsigned __int64
0x1800410a9  mov     rcx, rbx; unsigned __int16 *
0x1800410ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800410b1  mov     rbx, [rsp+38h+arg_0]
0x1800410b6  add     rsp, 30h
0x1800410ba  pop     rdi
0x1800410bb  retn
```
