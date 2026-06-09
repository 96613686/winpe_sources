# MapOldTheme(bool *,bool *)

- ea: `0x180041704`
- end: `0x180041a23`
- name: `?MapOldTheme@@YAJPEA_N0@Z`
- size: `799`
- prototype: `__int64 __fastcall(bool *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041a2c`

## callees

- `0x180014e40`
- `0x180021fb4`
- `0x180033524`
- `0x1800358c0`
- `0x180041704`
- `0x180060058`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180041997`
- `SHLWAPI!PathFileExistsW` at `0x180041997`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004185b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800418ad`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800418ec`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004192b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004197c`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004185b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800418ad`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x1800418ec`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004192b`
- `SHLWAPI!__imp_SHExpandEnvironmentStringsW` at `0x18004197c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041880`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041950`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041880`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041950`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800419ec`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800419ec`

## string_xrefs

- `0x18004178d`: `%WinDir%\Resources\Ease of Access Themes\Classic.theme`
- `0x1800417f8`: `%WinDir%\Resources\Ease of Access Themes\Basic.theme`

## pseudocode

```c
__int64 __fastcall MapOldTheme(bool *a1, bool *a2)
{
  signed int Path; // ebx
  unsigned int v5; // r14d
  const wchar_t *v6; // rcx
  int v7; // eax
  int v8; // eax
  int i; // edi
  int v10; // eax
  HKEY v11; // rcx
  int v12; // r9d
  HKEY v13; // rcx
  unsigned int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  const wchar_t *v16; // [rsp+40h] [rbp-C0h]
  _QWORD v17[21]; // [rsp+48h] [rbp-B8h]
  WCHAR String1[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR String2[264]; // [rsp+300h] [rbp+200h] BYREF

  *a1 = 0;
  *a2 = 0;
  Path = HrRegGetPath(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
           L"CurrentTheme",
           String1,
           bIgnoreCase);
  if ( Path < 0 )
  {
    return 0;
  }
  else
  {
    v5 = 0;
    v17[4] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v16 = L"%WinDir%\\Resources\\Themes\\Windows Classic.theme";
    v17[0] = &Default;
    v17[1] = L"%WinDir%\\Resources\\Ease of Access Themes\\Classic.theme";
    v17[3] = L"%WinDir%\\Resources\\Themes\\Architecture.theme";
    v17[5] = L"%WinDir%\\Resources\\Themes\\Characters.theme";
    v17[7] = L"%WinDir%\\Resources\\Themes\\Landscapes.theme";
    v17[9] = L"%WinDir%\\Resources\\Themes\\Nature.theme";
    v17[11] = L"%WinDir%\\Resources\\Themes\\Scenes.theme";
    v17[13] = L"%WinDir%\\Resources\\Themes\\theme1.theme";
    v17[15] = L"%WinDir%\\Resources\\Themes\\theme2.theme";
    v17[17] = L"%WinDir%\\Resources\\Themes\\Light.theme";
    v17[19] = L"%WinDir%\\Resources\\Ease of Access Themes\\Basic.theme";
    v17[2] = &Default;
    v17[6] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[8] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[10] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[12] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[14] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[16] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[18] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    v17[20] = L"%WinDir%\\Resources\\Themes\\Aero.theme";
    while ( v5 < 0xB )
    {
      if ( (unsigned int)SHExpandEnvironmentStringsW(v17[2 * v5 - 1], String2, 260)
        && CompareStringOrdinal(String1, -1, String2, -1, 1) == 2 )
      {
        _mm_lfence();
        v6 = L"%WinDir%\\Resources\\Themes\\Aero.theme";
        if ( *(_WORD *)v17[2 * v5] )
          v6 = (const wchar_t *)v17[2 * v5];
        v7 = SHExpandEnvironmentStringsW(v6, String1, 260);
        *a1 = 1;
        *a2 = 1;
        Path = v7 == 0 ? 0x80004005 : 0;
        break;
      }
      ++v5;
    }
    if ( !*a2 )
    {
      if ( (unsigned int)IsStagedThemeFile(String1) )
      {
        v8 = SHExpandEnvironmentStringsW(L"%WinDir%\\Resources\\Themes\\Aero.theme", String1, 260);
        *a1 = 1;
        *a2 = 1;
        Path = v8 == 0 ? 0x80004005 : 0;
      }
      if ( !*a2 )
      {
        for ( i = 0; !i; i = 1 )
        {
          if ( (unsigned int)SHExpandEnvironmentStringsW(L"%WinDir%\\Resources\\Themes\\Aero.theme", String2, 260)
            && CompareStringOrdinal(String1, -1, String2, -1, 1) == 2 )
          {
            _mm_lfence();
            v10 = SHExpandEnvironmentStringsW(L"%WinDir%\\Resources\\Themes\\Aero.theme", String1, 260);
            *a1 = 1;
            Path = v10 == 0 ? 0x80004005 : 0;
            break;
          }
        }
      }
    }
    if ( Path >= 0 )
    {
      if ( PathFileExistsW(String1) )
      {
        Path = HrRegSetPath(v11, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"CurrentTheme", v12, String1);
        if ( Path >= 0 && *a1 )
          SHRegSetBOOL(v13, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"ColorSetFromTheme", 0);
      }
    }
    RegDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\LastTheme");
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x180041704  mov     [rsp-8+arg_10], rbx
0x180041709  push    rbp
0x18004170a  push    rsi
0x18004170b  push    rdi
0x18004170c  push    r12
0x18004170e  push    r13
0x180041710  push    r14
0x180041712  push    r15
0x180041714  lea     rbp, [rsp-420h]
0x18004171c  sub     rsp, 520h
0x180041723  mov     rax, cs:__security_cookie
0x18004172a  xor     rax, rsp
0x18004172d  mov     [rbp+450h+var_40], rax
0x180041734  xor     r13d, r13d
0x180041737  lea     r9, [rbp+450h+String1]; unsigned __int16 *
0x18004173b  mov     [rcx], r13b
0x18004173e  lea     r8, aCurrenttheme; "CurrentTheme"
0x180041745  mov     [rdx], r13b
0x180041748  mov     rdi, rdx
0x18004174b  mov     r15, rcx
0x18004174e  lea     rdx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180041755  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18004175c  call    ?HrRegGetPath@@YAJPEAUHKEY__@@PEBG1PEAGK@Z; HrRegGetPath(HKEY__ *,ushort const *,ushort const *,ushort *,ulong)
0x180041761  mov     ebx, eax
0x180041763  test    eax, eax
0x180041765  js      loc_1800419F4
0x18004176b  lea     rsi, aWindirResource_17; "%WinDir%\\Resources\\Themes\\Aero.theme"
0x180041772  mov     r14d, r13d
0x180041775  lea     rax, aWindirResource_12; "%WinDir%\\Resources\\Themes\\Windows Cl"...
0x18004177c  mov     [rsp+550h+var_4E8], rsi
0x180041781  mov     [rsp+550h+var_510], rax
0x180041786  lea     rcx, Default
0x18004178d  lea     rax, aWindirResource_13; "%WinDir%\\Resources\\Ease of Access The"...
0x180041794  mov     [rsp+550h+var_508], rcx
0x180041799  mov     [rsp+550h+var_500], rax
0x18004179e  lea     rax, aWindirResource_4; "%WinDir%\\Resources\\Themes\\Architectu"...
0x1800417a5  mov     [rsp+550h+var_4F0], rax
0x1800417aa  lea     rax, aWindirResource_1; "%WinDir%\\Resources\\Themes\\Characters"...
0x1800417b1  mov     [rsp+550h+var_4E0], rax
0x1800417b6  lea     rax, aWindirResource_6; "%WinDir%\\Resources\\Themes\\Landscapes"...
0x1800417bd  mov     [rbp+450h+var_4D0], rax
0x1800417c1  lea     rax, aWindirResource_23; "%WinDir%\\Resources\\Themes\\Nature.the"...
0x1800417c8  mov     [rbp+450h+var_4C0], rax
0x1800417cc  lea     rax, aWindirResource_8; "%WinDir%\\Resources\\Themes\\Scenes.the"...
0x1800417d3  mov     [rbp+450h+var_4B0], rax
0x1800417d7  lea     rax, aWindirResource_7; "%WinDir%\\Resources\\Themes\\theme1.the"...
0x1800417de  mov     [rbp+450h+var_4A0], rax
0x1800417e2  lea     rax, aWindirResource_9; "%WinDir%\\Resources\\Themes\\theme2.the"...
0x1800417e9  mov     [rbp+450h+var_490], rax
0x1800417ed  lea     rax, aWindirResource_2; "%WinDir%\\Resources\\Themes\\Light.them"...
0x1800417f4  mov     [rbp+450h+var_480], rax
0x1800417f8  lea     rax, aWindirResource_22; "%WinDir%\\Resources\\Ease of Access The"...
0x1800417ff  mov     [rbp+450h+var_470], rax
0x180041803  mov     [rsp+550h+var_4F8], rcx
0x180041808  mov     [rsp+550h+var_4D8], rsi
0x18004180d  mov     [rbp+450h+var_4C8], rsi
0x180041811  mov     [rbp+450h+var_4B8], rsi
0x180041815  mov     [rbp+450h+var_4A8], rsi
0x180041819  mov     [rbp+450h+var_498], rsi
0x18004181d  mov     [rbp+450h+var_488], rsi
0x180041821  mov     [rbp+450h+var_478], rsi
0x180041825  mov     [rbp+450h+var_468], rsi
0x180041829  mov     [rsp+550h+var_520], rsi
0x18004182e  mov     [rsp+550h+var_518], rsi
0x180041833  mov     r12d, 80004005h
0x180041839  cmp     r14d, 0Bh
0x18004183d  jnb     loc_1800418C9
0x180041843  mov     r12d, r14d
0x180041846  lea     rdx, [rbp+450h+String2]
0x18004184d  add     r12, r12
0x180041850  mov     r8d, 104h
0x180041856  mov     rcx, [rsp+r12*8+550h+var_510]
0x18004185b  call    cs:__imp_SHExpandEnvironmentStringsW
0x180041861  test    eax, eax
0x180041863  jz      short loc_18004188B
0x180041865  or      eax, 0FFFFFFFFh
0x180041868  mov     [rsp+550h+bIgnoreCase], 1; bIgnoreCase
0x180041870  mov     r9d, eax; cchCount2
0x180041873  lea     r8, [rbp+450h+String2]; lpString2
0x18004187a  mov     edx, eax; cchCount1
0x18004187c  lea     rcx, [rbp+450h+String1]; lpString1
0x180041880  call    cs:__imp_CompareStringOrdinal
0x180041886  cmp     eax, 2
0x180041889  jz      short loc_180041890
0x18004188b  inc     r14d
0x18004188e  jmp     short loc_180041833
0x180041890  lfence
0x180041893  mov     rax, [rsp+r12*8+550h+var_508]
0x180041898  lea     rdx, [rbp+450h+String1]
0x18004189c  mov     rcx, rsi
0x18004189f  mov     r8d, 104h
0x1800418a5  cmp     [rax], r13w
0x1800418a9  cmovnz  rcx, rax
0x1800418ad  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800418b3  mov     r12d, 80004005h
0x1800418b9  mov     byte ptr [r15], 1
0x1800418bd  neg     eax
0x1800418bf  mov     byte ptr [rdi], 1
0x1800418c2  sbb     ebx, ebx
0x1800418c4  not     ebx
0x1800418c6  and     ebx, r12d
0x1800418c9  cmp     [rdi], r13b
0x1800418cc  jnz     loc_18004198F
0x1800418d2  lea     rcx, [rbp+450h+String1]; lpFileName
0x1800418d6  call    ?IsStagedThemeFile@@YAHPEBG@Z; IsStagedThemeFile(ushort const *)
0x1800418db  test    eax, eax
0x1800418dd  jz      short loc_180041902
0x1800418df  mov     r8d, 104h
0x1800418e5  lea     rdx, [rbp+450h+String1]
0x1800418e9  mov     rcx, rsi
0x1800418ec  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800418f2  neg     eax
0x1800418f4  mov     byte ptr [r15], 1
0x1800418f8  mov     byte ptr [rdi], 1
0x1800418fb  sbb     ebx, ebx
0x1800418fd  not     ebx
0x1800418ff  and     ebx, r12d
0x180041902  cmp     [rdi], r13b
0x180041905  jnz     loc_18004198F
0x18004190b  mov     edi, r13d
0x18004190e  cmp     edi, 1
0x180041911  jnb     short loc_18004198F
0x180041913  mov     r14d, edi
0x180041916  lea     rdx, [rbp+450h+String2]
0x18004191d  add     r14, r14
0x180041920  mov     r8d, 104h
0x180041926  mov     rcx, [rsp+r14*8+550h+var_520]
0x18004192b  call    cs:__imp_SHExpandEnvironmentStringsW
0x180041931  test    eax, eax
0x180041933  jz      short loc_18004195B
0x180041935  or      eax, 0FFFFFFFFh
0x180041938  mov     [rsp+550h+bIgnoreCase], 1; bIgnoreCase
0x180041940  mov     r9d, eax; cchCount2
0x180041943  lea     r8, [rbp+450h+String2]; lpString2
0x18004194a  mov     edx, eax; cchCount1
0x18004194c  lea     rcx, [rbp+450h+String1]; lpString1
0x180041950  call    cs:__imp_CompareStringOrdinal
0x180041956  cmp     eax, 2
0x180041959  jz      short loc_18004195F
0x18004195b  inc     edi
0x18004195d  jmp     short loc_18004190E
0x18004195f  lfence
0x180041962  mov     rax, [rsp+r14*8+550h+var_518]
0x180041967  lea     rdx, [rbp+450h+String1]
0x18004196b  mov     r8d, 104h
0x180041971  cmp     [rax], r13w
0x180041975  cmovnz  rsi, rax
0x180041979  mov     rcx, rsi
0x18004197c  call    cs:__imp_SHExpandEnvironmentStringsW
0x180041982  neg     eax
0x180041984  mov     byte ptr [r15], 1
0x180041988  sbb     ebx, ebx
0x18004198a  not     ebx
0x18004198c  and     ebx, r12d
0x18004198f  test    ebx, ebx
0x180041991  js      short loc_1800419DE
0x180041993  lea     rcx, [rbp+450h+String1]; pszPath
0x180041997  call    cs:__imp_PathFileExistsW
0x18004199d  test    eax, eax
0x18004199f  jz      short loc_1800419DE
0x1800419a1  lea     rax, [rbp+450h+String1]
0x1800419a5  lea     r8, aCurrenttheme; "CurrentTheme"
0x1800419ac  mov     qword ptr [rsp+550h+bIgnoreCase], rax; unsigned __int16 *
0x1800419b1  lea     rdx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800419b8  call    ?HrRegSetPath@@YAJPEAUHKEY__@@PEBG1H1@Z; HrRegSetPath(HKEY__ *,ushort const *,ushort const *,int,ushort const *)
0x1800419bd  mov     ebx, eax
0x1800419bf  test    eax, eax
0x1800419c1  js      short loc_1800419DE
0x1800419c3  cmp     [r15], r13b
0x1800419c6  jz      short loc_1800419DE
0x1800419c8  xor     r9d, r9d; int
0x1800419cb  lea     r8, aColorsetfromth; "ColorSetFromTheme"
0x1800419d2  lea     rdx, pszKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800419d9  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1800419de  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800419e5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800419ec  call    cs:__imp_RegDeleteKeyW
0x1800419f2  jmp     short loc_1800419F7
0x1800419f4  mov     ebx, r13d
0x1800419f7  mov     eax, ebx
0x1800419f9  mov     rcx, [rbp+450h+var_40]
0x180041a00  xor     rcx, rsp; StackCookie
0x180041a03  call    __security_check_cookie
0x180041a08  mov     rbx, [rsp+550h+arg_10]
0x180041a10  add     rsp, 520h
0x180041a17  pop     r15
0x180041a19  pop     r14
0x180041a1b  pop     r13
0x180041a1d  pop     r12
0x180041a1f  pop     rdi
0x180041a20  pop     rsi
0x180041a21  pop     rbp
0x180041a22  retn
```
