# LoadMUILibraryW

- ea: `0x18002edd8`
- end: `0x18002f308`
- name: `LoadMUILibraryW`
- size: `1328`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001e880`
- `0x180020270`

## callees

- `0x180001891`
- `0x180005830`
- `0x18002e6b0`
- `0x18002e7dc`
- `0x18002e910`
- `0x18002e984`
- `0x18002eb34`
- `0x18002edd8`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetUserDefaultUILanguage` at `0x18002eef2`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18002eef2`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18002f01a`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18002f01a`
- `KERNEL32!SearchPathW` at `0x18002ee84`
- `KERNEL32!SearchPathW` at `0x18002ee84`
- `KERNEL32!LoadLibraryExW` at `0x18002ee3b`
- `KERNEL32!LoadLibraryExW` at `0x18002f2b7`
- `KERNEL32!LoadLibraryExW` at `0x18002ee3b`
- `KERNEL32!LoadLibraryExW` at `0x18002f2b7`
- `KERNEL32!FindResourceExW` at `0x18002eecf`
- `KERNEL32!FindResourceExW` at `0x18002eecf`
- `KERNEL32!FreeLibrary` at `0x18002f13f`
- `KERNEL32!FreeLibrary` at `0x18002f294`
- `KERNEL32!FreeLibrary` at `0x18002f2ce`
- `KERNEL32!FreeLibrary` at `0x18002f13f`
- `KERNEL32!FreeLibrary` at `0x18002f294`
- `KERNEL32!FreeLibrary` at `0x18002f2ce`
- `KERNEL32!LocaleNameToLCID` at `0x18002efba`
- `KERNEL32!LocaleNameToLCID` at `0x18002f090`
- `KERNEL32!LocaleNameToLCID` at `0x18002f202`
- `KERNEL32!LocaleNameToLCID` at `0x18002efba`
- `KERNEL32!LocaleNameToLCID` at `0x18002f090`
- `KERNEL32!LocaleNameToLCID` at `0x18002f202`
- `KERNEL32!GetLocaleInfoW` at `0x18002ef28`
- `KERNEL32!GetLocaleInfoW` at `0x18002ef28`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  DWORD v3; // ebx
  const WCHAR *v4; // rsi
  HINSTANCE result; // rax
  HMODULE v6; // rdi
  WCHAR *v7; // r15
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rsi
  unsigned __int16 v10; // ax
  LANGID SystemDefaultUILanguage; // ax
  LANGID v12; // r12
  unsigned __int16 v13; // ax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 InstallLanguage; // r14
  unsigned __int16 v22; // ax
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR v24; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v25[88]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[88]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR LCData[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v3 = 0;
  v24 = pszFullModuleName;
  FilePart = 0;
  v4 = pszFullModuleName;
  if ( !pszFullModuleName )
    return 0;
  dword_180049E1C = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(v4, 0, dword_180049E1C & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_180049E1C & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, v4, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v6);
    return 0;
  }
  if ( FilePart )
  {
    v7 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v7 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v6, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_180049E1C & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
      {
        UserDefaultUILanguage = 3076;
        if ( GetLocaleInfoW(0x404u, 8u, LCData, 32) )
        {
          if ( wcsncmp_0(LCData, &word_18003732C, 3u) )
            UserDefaultUILanguage = 1028;
        }
      }
      while ( 1 )
      {
        StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", UserDefaultUILanguage);
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        if ( (unsigned int)LookupLangID(UserDefaultUILanguage, v25, Name, 0) )
        {
          v10 = LocaleNameToLCID(Name, 0x8000000u);
          if ( v10 )
          {
            StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", v10);
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v12 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", SystemDefaultUILanguage);
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            if ( (unsigned int)LookupLangID(v12, v25, Name, 0) )
            {
              v13 = LocaleNameToLCID(Name, 0x8000000u);
              if ( v13 )
              {
                StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", v13);
                MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart);
                if ( MUIFile )
                  goto LABEL_41;
              }
            }
          }
          if ( UserDefaultUILanguage != 1033 && v12 != 1033 )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, L"MUI\\0409", FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
          if ( MUIFile )
            goto LABEL_41;
          goto LABEL_29;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    if ( (dword_180049E1C & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", InstallLanguage);
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart);
      if ( MUIFile
        || (unsigned int)LookupLangID((unsigned __int16)InstallLanguage, v25, Name, 0)
        && (v22 = LocaleNameToLCID(Name, 0x8000000u)) != 0
        && (StringCchPrintfW(v25, 0x55u, L"MUI\\%04hx", v22),
            (MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v25, FilePart)) != 0)
        || (_WORD)InstallLanguage != 1033 && (MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, L"MUI\\0409", FilePart)) != 0
        || (MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart)) != 0 )
      {
LABEL_41:
        FreeLibrary(v6);
        return MUIFile;
      }
LABEL_29:
      v4 = v24;
    }
  }
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType(v15, v14, v16) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      LOBYTE(v3) = (GetOSType(v18, v17, v19) & 0x26) != 0;
      return LoadLibraryExW(v4, 0, v3);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002edd8  mov     [rsp-8+arg_8], rbx
0x18002eddd  mov     [rsp-8+arg_10], rsi
0x18002ede2  push    rbp
0x18002ede3  push    rdi
0x18002ede4  push    r12
0x18002ede6  push    r14
0x18002ede8  push    r15
0x18002edea  lea     rbp, [rsp-300h]
0x18002edf2  sub     rsp, 400h
0x18002edf9  mov     rax, cs:__security_cookie
0x18002ee00  xor     rax, rsp
0x18002ee03  mov     [rbp+320h+var_30], rax
0x18002ee0a  xor     ebx, ebx
0x18002ee0c  mov     [rsp+420h+var_3E8], rcx
0x18002ee11  mov     [rsp+420h+FilePart], rbx
0x18002ee16  mov     rsi, rcx
0x18002ee19  test    rcx, rcx
0x18002ee1c  jz      loc_18002F2DA
0x18002ee22  call    GetOSType
0x18002ee27  mov     cs:dword_180049E1C, eax
0x18002ee2d  xor     edx, edx; hFile
0x18002ee2f  and     eax, 20h
0x18002ee32  mov     rcx, rsi; lpLibFileName
0x18002ee35  or      eax, 2
0x18002ee38  mov     r8d, eax; dwFlags
0x18002ee3b  call    cs:__imp_LoadLibraryExW
0x18002ee42  nop     dword ptr [rax+rax+00h]
0x18002ee47  mov     rdi, rax
0x18002ee4a  test    rax, rax
0x18002ee4d  jz      loc_18002F2DA
0x18002ee53  test    byte ptr cs:dword_180049E1C, 20h
0x18002ee5a  jnz     loc_18002F2DC
0x18002ee60  lea     rax, [rsp+420h+FilePart]
0x18002ee65  mov     r9d, 104h; nBufferLength
0x18002ee6b  mov     [rsp+420h+lpFilePart], rax; lpFilePart
0x18002ee70  xor     r8d, r8d; lpExtension
0x18002ee73  lea     rax, [rbp+320h+Buffer]
0x18002ee7a  mov     rdx, rsi; lpFileName
0x18002ee7d  xor     ecx, ecx; lpPath
0x18002ee7f  mov     [rsp+420h+lpBuffer], rax; lpBuffer
0x18002ee84  call    cs:__imp_SearchPathW
0x18002ee8b  nop     dword ptr [rax+rax+00h]
0x18002ee90  test    eax, eax
0x18002ee92  jz      loc_18002F2CB
0x18002ee98  mov     rax, [rsp+420h+FilePart]
0x18002ee9d  test    rax, rax
0x18002eea0  jnz     short loc_18002EEB3
0x18002eea2  lea     rax, [rbp+320h+Buffer]
0x18002eea9  mov     r15d, ebx
0x18002eeac  mov     [rsp+420h+FilePart], rax
0x18002eeb1  jmp     short loc_18002EEBE
0x18002eeb3  lea     r15, [rbp+320h+Buffer]
0x18002eeba  mov     [rax-2], bx
0x18002eebe  xor     r9d, r9d; wLanguage
0x18002eec1  lea     rdx, Type; "MUI"
0x18002eec8  mov     rcx, rdi; hModule
0x18002eecb  lea     r8d, [r9+1]; lpName
0x18002eecf  call    cs:__imp_FindResourceExW
0x18002eed6  nop     dword ptr [rax+rax+00h]
0x18002eedb  test    rax, rax
0x18002eede  jz      loc_18002F132
0x18002eee4  mov     eax, cs:dword_180049E1C
0x18002eeea  test    al, 4
0x18002eeec  jz      loc_18002F195
0x18002eef2  call    cs:__imp_GetUserDefaultUILanguage
0x18002eef9  nop     dword ptr [rax+rax+00h]
0x18002eefe  mov     esi, 404h
0x18002ef03  mov     r12d, 0C04h
0x18002ef09  movzx   r14d, ax
0x18002ef0d  cmp     ax, si
0x18002ef10  jnz     short loc_18002EF59
0x18002ef12  mov     r9d, 20h ; ' '; cchData
0x18002ef18  lea     r8, [rbp+320h+LCData]; lpLCData
0x18002ef1f  mov     ecx, esi; Locale
0x18002ef21  mov     r14d, r12d
0x18002ef24  lea     edx, [r9-18h]; LCType
0x18002ef28  call    cs:__imp_GetLocaleInfoW
0x18002ef2f  nop     dword ptr [rax+rax+00h]
0x18002ef34  test    eax, eax
0x18002ef36  jz      short loc_18002EF59
0x18002ef38  mov     r8d, 3; MaxCount
0x18002ef3e  lea     rdx, word_18003732C; String2
0x18002ef45  lea     rcx, [rbp+320h+LCData]; String1
0x18002ef4c  call    wcsncmp_0
0x18002ef51  test    eax, eax
0x18002ef53  jz      short loc_18002EF59
0x18002ef55  movzx   r14d, si
0x18002ef59  mov     r12d, 55h ; 'U'
0x18002ef5f  movzx   r9d, r14w
0x18002ef63  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002ef6a  mov     rdx, r12; unsigned __int64
0x18002ef6d  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002ef72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ef77  mov     r9, [rsp+420h+FilePart]
0x18002ef7c  lea     r8, [rsp+420h+var_3E0]
0x18002ef81  mov     rdx, r15
0x18002ef84  mov     rcx, rdi
0x18002ef87  call    LoadMUIFile
0x18002ef8c  mov     rsi, rax
0x18002ef8f  test    rax, rax
0x18002ef92  jnz     loc_18002F291
0x18002ef98  xor     r9d, r9d
0x18002ef9b  lea     r8, [rbp+320h+Name]
0x18002ef9f  lea     rdx, [rsp+420h+var_3E0]
0x18002efa4  movzx   ecx, r14w
0x18002efa8  call    LookupLangID
0x18002efad  test    eax, eax
0x18002efaf  jz      short loc_18002F004
0x18002efb1  mov     edx, 8000000h; dwFlags
0x18002efb6  lea     rcx, [rbp+320h+Name]; lpName
0x18002efba  call    cs:__imp_LocaleNameToLCID
0x18002efc1  nop     dword ptr [rax+rax+00h]
0x18002efc6  test    ax, ax
0x18002efc9  jz      short loc_18002F004
0x18002efcb  movzx   r9d, ax
0x18002efcf  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002efd6  mov     rdx, r12; unsigned __int64
0x18002efd9  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002efde  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002efe3  mov     r9, [rsp+420h+FilePart]
0x18002efe8  lea     r8, [rsp+420h+var_3E0]
0x18002efed  mov     rdx, r15
0x18002eff0  mov     rcx, rdi
0x18002eff3  call    LoadMUIFile
0x18002eff8  mov     rsi, rax
0x18002effb  test    rax, rax
0x18002effe  jnz     loc_18002F291
0x18002f004  mov     eax, 0C04h
0x18002f009  cmp     r14w, ax
0x18002f00d  jnz     short loc_18002F01A
0x18002f00f  mov     r14d, 404h
0x18002f015  jmp     loc_18002EF5F
0x18002f01a  call    cs:__imp_GetSystemDefaultUILanguage
0x18002f021  nop     dword ptr [rax+rax+00h]
0x18002f026  movzx   r12d, ax
0x18002f02a  cmp     r12w, r14w
0x18002f02e  jz      loc_18002F0DA
0x18002f034  mov     r9d, r12d
0x18002f037  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002f03e  mov     edx, 55h ; 'U'; unsigned __int64
0x18002f043  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002f048  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f04d  mov     r9, [rsp+420h+FilePart]
0x18002f052  lea     r8, [rsp+420h+var_3E0]
0x18002f057  mov     rdx, r15
0x18002f05a  mov     rcx, rdi
0x18002f05d  call    LoadMUIFile
0x18002f062  mov     rsi, rax
0x18002f065  test    rax, rax
0x18002f068  jnz     loc_18002F291
0x18002f06e  xor     r9d, r9d
0x18002f071  lea     r8, [rbp+320h+Name]
0x18002f075  lea     rdx, [rsp+420h+var_3E0]
0x18002f07a  movzx   ecx, r12w
0x18002f07e  call    LookupLangID
0x18002f083  test    eax, eax
0x18002f085  jz      short loc_18002F0DA
0x18002f087  mov     edx, 8000000h; dwFlags
0x18002f08c  lea     rcx, [rbp+320h+Name]; lpName
0x18002f090  call    cs:__imp_LocaleNameToLCID
0x18002f097  nop     dword ptr [rax+rax+00h]
0x18002f09c  test    ax, ax
0x18002f09f  jz      short loc_18002F0DA
0x18002f0a1  movzx   r9d, ax
0x18002f0a5  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002f0ac  lea     edx, [rsi+55h]; unsigned __int64
0x18002f0af  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002f0b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f0b9  mov     r9, [rsp+420h+FilePart]
0x18002f0be  lea     r8, [rsp+420h+var_3E0]
0x18002f0c3  mov     rdx, r15
0x18002f0c6  mov     rcx, rdi
0x18002f0c9  call    LoadMUIFile
0x18002f0ce  mov     rsi, rax
0x18002f0d1  test    rax, rax
0x18002f0d4  jnz     loc_18002F291
0x18002f0da  mov     eax, 409h
0x18002f0df  cmp     ax, r14w
0x18002f0e3  jz      short loc_18002F10E
0x18002f0e5  cmp     ax, r12w
0x18002f0e9  jz      short loc_18002F10E
0x18002f0eb  mov     r9, [rsp+420h+FilePart]
0x18002f0f0  lea     r8, aMui0409; "MUI\\0409"
0x18002f0f7  mov     rdx, r15
0x18002f0fa  mov     rcx, rdi
0x18002f0fd  call    LoadMUIFile
0x18002f102  mov     rsi, rax
0x18002f105  test    rax, rax
0x18002f108  jnz     loc_18002F291
0x18002f10e  mov     r9, [rsp+420h+FilePart]
0x18002f113  xor     r8d, r8d
0x18002f116  mov     rdx, r15
0x18002f119  mov     rcx, rdi
0x18002f11c  call    LoadMUIFile
0x18002f121  mov     rsi, rax
0x18002f124  test    rax, rax
0x18002f127  jnz     loc_18002F291
0x18002f12d  mov     rsi, [rsp+420h+var_3E8]
0x18002f132  test    dil, 1
0x18002f136  jz      loc_18002F2C6
0x18002f13c  mov     rcx, rdi; hLibModule
0x18002f13f  call    cs:__imp_FreeLibrary
0x18002f146  nop     dword ptr [rax+rax+00h]
0x18002f14b  call    GetOSType
0x18002f150  test    al, 38h
0x18002f152  jz      loc_18002F2A5
0x18002f158  mov     rax, [rsp+420h+FilePart]
0x18002f15d  lea     r8, aSS; "%s\\%s"
0x18002f164  mov     r9, r15
0x18002f167  mov     [rsp+420h+lpBuffer], rax
0x18002f16c  mov     edx, 104h; unsigned __int64
0x18002f171  lea     rcx, [rbp+320h+Buffer]; unsigned __int16 *
0x18002f178  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f17d  xor     r8d, r8d
0x18002f180  lea     rcx, [rbp+320h+Buffer]
0x18002f187  lea     edx, [r8+1]
0x18002f18b  call    MapMUIFile
0x18002f190  jmp     loc_18002F2C3
0x18002f195  test    al, 3
0x18002f197  jz      short loc_18002F132
0x18002f199  call    GetInstallLanguage
0x18002f19e  movzx   r14d, ax
0x18002f1a2  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002f1a9  mov     r12d, 55h ; 'U'
0x18002f1af  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002f1b4  mov     r9d, r14d
0x18002f1b7  mov     edx, r12d; unsigned __int64
0x18002f1ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f1bf  mov     r9, [rsp+420h+FilePart]
0x18002f1c4  lea     r8, [rsp+420h+var_3E0]
0x18002f1c9  mov     rdx, r15
0x18002f1cc  mov     rcx, rdi
0x18002f1cf  call    LoadMUIFile
0x18002f1d4  mov     rsi, rax
0x18002f1d7  test    rax, rax
0x18002f1da  jnz     loc_18002F291
0x18002f1e0  xor     r9d, r9d
0x18002f1e3  lea     r8, [rbp+320h+Name]
0x18002f1e7  lea     rdx, [rsp+420h+var_3E0]
0x18002f1ec  movzx   ecx, r14w
0x18002f1f0  call    LookupLangID
0x18002f1f5  test    eax, eax
0x18002f1f7  jz      short loc_18002F248
0x18002f1f9  mov     edx, 8000000h; dwFlags
0x18002f1fe  lea     rcx, [rbp+320h+Name]; lpName
0x18002f202  call    cs:__imp_LocaleNameToLCID
0x18002f209  nop     dword ptr [rax+rax+00h]
0x18002f20e  test    ax, ax
0x18002f211  jz      short loc_18002F248
0x18002f213  movzx   r9d, ax
0x18002f217  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002f21e  mov     edx, r12d; unsigned __int64
0x18002f221  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002f226  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002f22b  mov     r9, [rsp+420h+FilePart]
0x18002f230  lea     r8, [rsp+420h+var_3E0]
0x18002f235  mov     rdx, r15
0x18002f238  mov     rcx, rdi
0x18002f23b  call    LoadMUIFile
0x18002f240  mov     rsi, rax
0x18002f243  test    rax, rax
0x18002f246  jnz     short loc_18002F291
0x18002f248  mov     eax, 409h
0x18002f24d  cmp     ax, r14w
0x18002f251  jz      short loc_18002F272
0x18002f253  mov     r9, [rsp+420h+FilePart]
0x18002f258  lea     r8, aMui0409; "MUI\\0409"
0x18002f25f  mov     rdx, r15
0x18002f262  mov     rcx, rdi
0x18002f265  call    LoadMUIFile
0x18002f26a  mov     rsi, rax
0x18002f26d  test    rax, rax
0x18002f270  jnz     short loc_18002F291
0x18002f272  mov     r9, [rsp+420h+FilePart]
0x18002f277  xor     r8d, r8d
0x18002f27a  mov     rdx, r15
0x18002f27d  mov     rcx, rdi
0x18002f280  call    LoadMUIFile
0x18002f285  mov     rsi, rax
0x18002f288  test    rax, rax
0x18002f28b  jz      loc_18002F12D
0x18002f291  mov     rcx, rdi; hLibModule
0x18002f294  call    cs:__imp_FreeLibrary
0x18002f29b  nop     dword ptr [rax+rax+00h]
0x18002f2a0  mov     rax, rsi
0x18002f2a3  jmp     short loc_18002F2DC
0x18002f2a5  call    GetOSType
0x18002f2aa  test    al, 26h
0x18002f2ac  mov     rcx, rsi; lpLibFileName
0x18002f2af  setnz   bl
0x18002f2b2  xor     edx, edx; hFile
0x18002f2b4  mov     r8d, ebx; dwFlags
0x18002f2b7  call    cs:__imp_LoadLibraryExW
0x18002f2be  nop     dword ptr [rax+rax+00h]
0x18002f2c3  mov     rdi, rax
0x18002f2c6  mov     rax, rdi
0x18002f2c9  jmp     short loc_18002F2DC
0x18002f2cb  mov     rcx, rdi; hLibModule
0x18002f2ce  call    cs:__imp_FreeLibrary
0x18002f2d5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
