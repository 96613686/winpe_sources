# LoadMUILibraryW

- ea: `0x18002fd90`
- end: `0x1800302c0`
- name: `LoadMUILibraryW`
- size: `1328`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001f850`
- `0x180021280`

## callees

- `0x180002241`
- `0x180006310`
- `0x18002f668`
- `0x18002f794`
- `0x18002f8c8`
- `0x18002f93c`
- `0x18002faec`
- `0x18002fd90`
- `0x180030390`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1800300f7`
- `KERNEL32!FreeLibrary` at `0x18003024c`
- `KERNEL32!FreeLibrary` at `0x180030286`
- `KERNEL32!FreeLibrary` at `0x1800300f7`
- `KERNEL32!FreeLibrary` at `0x18003024c`
- `KERNEL32!FreeLibrary` at `0x180030286`
- `KERNEL32!LocaleNameToLCID` at `0x18002ff72`
- `KERNEL32!LocaleNameToLCID` at `0x180030048`
- `KERNEL32!LocaleNameToLCID` at `0x1800301ba`
- `KERNEL32!LocaleNameToLCID` at `0x18002ff72`
- `KERNEL32!LocaleNameToLCID` at `0x180030048`
- `KERNEL32!LocaleNameToLCID` at `0x1800301ba`
- `KERNEL32!GetLocaleInfoW` at `0x18002fee0`
- `KERNEL32!GetLocaleInfoW` at `0x18002fee0`
- `KERNEL32!SearchPathW` at `0x18002fe3c`
- `KERNEL32!SearchPathW` at `0x18002fe3c`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18002ffd2`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18002ffd2`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18002feaa`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18002feaa`
- `KERNEL32!FindResourceExW` at `0x18002fe87`
- `KERNEL32!FindResourceExW` at `0x18002fe87`
- `KERNEL32!LoadLibraryExW` at `0x18002fdf3`
- `KERNEL32!LoadLibraryExW` at `0x18003026f`
- `KERNEL32!LoadLibraryExW` at `0x18002fdf3`
- `KERNEL32!LoadLibraryExW` at `0x18003026f`

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
  dword_18004BF0C = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(v4, 0, dword_18004BF0C & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_18004BF0C & 0x20) != 0 )
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
    if ( (dword_18004BF0C & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
      {
        UserDefaultUILanguage = 3076;
        if ( GetLocaleInfoW(0x404u, 8u, LCData, 32) )
        {
          if ( wcsncmp_0(LCData, &word_180039864, 3u) )
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
    if ( (dword_18004BF0C & 3) != 0 )
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
0x18002fd90  mov     [rsp-8+arg_8], rbx
0x18002fd95  mov     [rsp-8+arg_10], rsi
0x18002fd9a  push    rbp
0x18002fd9b  push    rdi
0x18002fd9c  push    r12
0x18002fd9e  push    r14
0x18002fda0  push    r15
0x18002fda2  lea     rbp, [rsp-300h]
0x18002fdaa  sub     rsp, 400h
0x18002fdb1  mov     rax, cs:__security_cookie
0x18002fdb8  xor     rax, rsp
0x18002fdbb  mov     [rbp+320h+var_30], rax
0x18002fdc2  xor     ebx, ebx
0x18002fdc4  mov     [rsp+420h+var_3E8], rcx
0x18002fdc9  mov     [rsp+420h+FilePart], rbx
0x18002fdce  mov     rsi, rcx
0x18002fdd1  test    rcx, rcx
0x18002fdd4  jz      loc_180030292
0x18002fdda  call    GetOSType
0x18002fddf  mov     cs:dword_18004BF0C, eax
0x18002fde5  xor     edx, edx; hFile
0x18002fde7  and     eax, 20h
0x18002fdea  mov     rcx, rsi; lpLibFileName
0x18002fded  or      eax, 2
0x18002fdf0  mov     r8d, eax; dwFlags
0x18002fdf3  call    cs:__imp_LoadLibraryExW
0x18002fdfa  nop     dword ptr [rax+rax+00h]
0x18002fdff  mov     rdi, rax
0x18002fe02  test    rax, rax
0x18002fe05  jz      loc_180030292
0x18002fe0b  test    byte ptr cs:dword_18004BF0C, 20h
0x18002fe12  jnz     loc_180030294
0x18002fe18  lea     rax, [rsp+420h+FilePart]
0x18002fe1d  mov     r9d, 104h; nBufferLength
0x18002fe23  mov     [rsp+420h+lpFilePart], rax; lpFilePart
0x18002fe28  xor     r8d, r8d; lpExtension
0x18002fe2b  lea     rax, [rbp+320h+Buffer]
0x18002fe32  mov     rdx, rsi; lpFileName
0x18002fe35  xor     ecx, ecx; lpPath
0x18002fe37  mov     [rsp+420h+lpBuffer], rax; lpBuffer
0x18002fe3c  call    cs:__imp_SearchPathW
0x18002fe43  nop     dword ptr [rax+rax+00h]
0x18002fe48  test    eax, eax
0x18002fe4a  jz      loc_180030283
0x18002fe50  mov     rax, [rsp+420h+FilePart]
0x18002fe55  test    rax, rax
0x18002fe58  jnz     short loc_18002FE6B
0x18002fe5a  lea     rax, [rbp+320h+Buffer]
0x18002fe61  mov     r15d, ebx
0x18002fe64  mov     [rsp+420h+FilePart], rax
0x18002fe69  jmp     short loc_18002FE76
0x18002fe6b  lea     r15, [rbp+320h+Buffer]
0x18002fe72  mov     [rax-2], bx
0x18002fe76  xor     r9d, r9d; wLanguage
0x18002fe79  lea     rdx, Type; "MUI"
0x18002fe80  mov     rcx, rdi; hModule
0x18002fe83  lea     r8d, [r9+1]; lpName
0x18002fe87  call    cs:__imp_FindResourceExW
0x18002fe8e  nop     dword ptr [rax+rax+00h]
0x18002fe93  test    rax, rax
0x18002fe96  jz      loc_1800300EA
0x18002fe9c  mov     eax, cs:dword_18004BF0C
0x18002fea2  test    al, 4
0x18002fea4  jz      loc_18003014D
0x18002feaa  call    cs:__imp_GetUserDefaultUILanguage
0x18002feb1  nop     dword ptr [rax+rax+00h]
0x18002feb6  mov     esi, 404h
0x18002febb  mov     r12d, 0C04h
0x18002fec1  movzx   r14d, ax
0x18002fec5  cmp     ax, si
0x18002fec8  jnz     short loc_18002FF11
0x18002feca  mov     r9d, 20h ; ' '; cchData
0x18002fed0  lea     r8, [rbp+320h+LCData]; lpLCData
0x18002fed7  mov     ecx, esi; Locale
0x18002fed9  mov     r14d, r12d
0x18002fedc  lea     edx, [r9-18h]; LCType
0x18002fee0  call    cs:__imp_GetLocaleInfoW
0x18002fee7  nop     dword ptr [rax+rax+00h]
0x18002feec  test    eax, eax
0x18002feee  jz      short loc_18002FF11
0x18002fef0  mov     r8d, 3; MaxCount
0x18002fef6  lea     rdx, word_180039864; String2
0x18002fefd  lea     rcx, [rbp+320h+LCData]; String1
0x18002ff04  call    wcsncmp_0
0x18002ff09  test    eax, eax
0x18002ff0b  jz      short loc_18002FF11
0x18002ff0d  movzx   r14d, si
0x18002ff11  mov     r12d, 55h ; 'U'
0x18002ff17  movzx   r9d, r14w
0x18002ff1b  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002ff22  mov     rdx, r12; unsigned __int64
0x18002ff25  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002ff2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ff2f  mov     r9, [rsp+420h+FilePart]
0x18002ff34  lea     r8, [rsp+420h+var_3E0]
0x18002ff39  mov     rdx, r15
0x18002ff3c  mov     rcx, rdi
0x18002ff3f  call    LoadMUIFile
0x18002ff44  mov     rsi, rax
0x18002ff47  test    rax, rax
0x18002ff4a  jnz     loc_180030249
0x18002ff50  xor     r9d, r9d
0x18002ff53  lea     r8, [rbp+320h+Name]
0x18002ff57  lea     rdx, [rsp+420h+var_3E0]
0x18002ff5c  movzx   ecx, r14w
0x18002ff60  call    LookupLangID
0x18002ff65  test    eax, eax
0x18002ff67  jz      short loc_18002FFBC
0x18002ff69  mov     edx, 8000000h; dwFlags
0x18002ff6e  lea     rcx, [rbp+320h+Name]; lpName
0x18002ff72  call    cs:__imp_LocaleNameToLCID
0x18002ff79  nop     dword ptr [rax+rax+00h]
0x18002ff7e  test    ax, ax
0x18002ff81  jz      short loc_18002FFBC
0x18002ff83  movzx   r9d, ax
0x18002ff87  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002ff8e  mov     rdx, r12; unsigned __int64
0x18002ff91  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18002ff96  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ff9b  mov     r9, [rsp+420h+FilePart]
0x18002ffa0  lea     r8, [rsp+420h+var_3E0]
0x18002ffa5  mov     rdx, r15
0x18002ffa8  mov     rcx, rdi
0x18002ffab  call    LoadMUIFile
0x18002ffb0  mov     rsi, rax
0x18002ffb3  test    rax, rax
0x18002ffb6  jnz     loc_180030249
0x18002ffbc  mov     eax, 0C04h
0x18002ffc1  cmp     r14w, ax
0x18002ffc5  jnz     short loc_18002FFD2
0x18002ffc7  mov     r14d, 404h
0x18002ffcd  jmp     loc_18002FF17
0x18002ffd2  call    cs:__imp_GetSystemDefaultUILanguage
0x18002ffd9  nop     dword ptr [rax+rax+00h]
0x18002ffde  movzx   r12d, ax
0x18002ffe2  cmp     r12w, r14w
0x18002ffe6  jz      loc_180030092
0x18002ffec  mov     r9d, r12d
0x18002ffef  lea     r8, aMui04hx; "MUI\\%04hx"
0x18002fff6  mov     edx, 55h ; 'U'; unsigned __int64
0x18002fffb  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x180030000  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030005  mov     r9, [rsp+420h+FilePart]
0x18003000a  lea     r8, [rsp+420h+var_3E0]
0x18003000f  mov     rdx, r15
0x180030012  mov     rcx, rdi
0x180030015  call    LoadMUIFile
0x18003001a  mov     rsi, rax
0x18003001d  test    rax, rax
0x180030020  jnz     loc_180030249
0x180030026  xor     r9d, r9d
0x180030029  lea     r8, [rbp+320h+Name]
0x18003002d  lea     rdx, [rsp+420h+var_3E0]
0x180030032  movzx   ecx, r12w
0x180030036  call    LookupLangID
0x18003003b  test    eax, eax
0x18003003d  jz      short loc_180030092
0x18003003f  mov     edx, 8000000h; dwFlags
0x180030044  lea     rcx, [rbp+320h+Name]; lpName
0x180030048  call    cs:__imp_LocaleNameToLCID
0x18003004f  nop     dword ptr [rax+rax+00h]
0x180030054  test    ax, ax
0x180030057  jz      short loc_180030092
0x180030059  movzx   r9d, ax
0x18003005d  lea     r8, aMui04hx; "MUI\\%04hx"
0x180030064  lea     edx, [rsi+55h]; unsigned __int64
0x180030067  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18003006c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030071  mov     r9, [rsp+420h+FilePart]
0x180030076  lea     r8, [rsp+420h+var_3E0]
0x18003007b  mov     rdx, r15
0x18003007e  mov     rcx, rdi
0x180030081  call    LoadMUIFile
0x180030086  mov     rsi, rax
0x180030089  test    rax, rax
0x18003008c  jnz     loc_180030249
0x180030092  mov     eax, 409h
0x180030097  cmp     ax, r14w
0x18003009b  jz      short loc_1800300C6
0x18003009d  cmp     ax, r12w
0x1800300a1  jz      short loc_1800300C6
0x1800300a3  mov     r9, [rsp+420h+FilePart]
0x1800300a8  lea     r8, aMui0409; "MUI\\0409"
0x1800300af  mov     rdx, r15
0x1800300b2  mov     rcx, rdi
0x1800300b5  call    LoadMUIFile
0x1800300ba  mov     rsi, rax
0x1800300bd  test    rax, rax
0x1800300c0  jnz     loc_180030249
0x1800300c6  mov     r9, [rsp+420h+FilePart]
0x1800300cb  xor     r8d, r8d
0x1800300ce  mov     rdx, r15
0x1800300d1  mov     rcx, rdi
0x1800300d4  call    LoadMUIFile
0x1800300d9  mov     rsi, rax
0x1800300dc  test    rax, rax
0x1800300df  jnz     loc_180030249
0x1800300e5  mov     rsi, [rsp+420h+var_3E8]
0x1800300ea  test    dil, 1
0x1800300ee  jz      loc_18003027E
0x1800300f4  mov     rcx, rdi; hLibModule
0x1800300f7  call    cs:__imp_FreeLibrary
0x1800300fe  nop     dword ptr [rax+rax+00h]
0x180030103  call    GetOSType
0x180030108  test    al, 38h
0x18003010a  jz      loc_18003025D
0x180030110  mov     rax, [rsp+420h+FilePart]
0x180030115  lea     r8, aSS; "%s\\%s"
0x18003011c  mov     r9, r15
0x18003011f  mov     [rsp+420h+lpBuffer], rax
0x180030124  mov     edx, 104h; unsigned __int64
0x180030129  lea     rcx, [rbp+320h+Buffer]; unsigned __int16 *
0x180030130  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030135  xor     r8d, r8d
0x180030138  lea     rcx, [rbp+320h+Buffer]
0x18003013f  lea     edx, [r8+1]
0x180030143  call    MapMUIFile
0x180030148  jmp     loc_18003027B
0x18003014d  test    al, 3
0x18003014f  jz      short loc_1800300EA
0x180030151  call    GetInstallLanguage
0x180030156  movzx   r14d, ax
0x18003015a  lea     r8, aMui04hx; "MUI\\%04hx"
0x180030161  mov     r12d, 55h ; 'U'
0x180030167  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x18003016c  mov     r9d, r14d
0x18003016f  mov     edx, r12d; unsigned __int64
0x180030172  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030177  mov     r9, [rsp+420h+FilePart]
0x18003017c  lea     r8, [rsp+420h+var_3E0]
0x180030181  mov     rdx, r15
0x180030184  mov     rcx, rdi
0x180030187  call    LoadMUIFile
0x18003018c  mov     rsi, rax
0x18003018f  test    rax, rax
0x180030192  jnz     loc_180030249
0x180030198  xor     r9d, r9d
0x18003019b  lea     r8, [rbp+320h+Name]
0x18003019f  lea     rdx, [rsp+420h+var_3E0]
0x1800301a4  movzx   ecx, r14w
0x1800301a8  call    LookupLangID
0x1800301ad  test    eax, eax
0x1800301af  jz      short loc_180030200
0x1800301b1  mov     edx, 8000000h; dwFlags
0x1800301b6  lea     rcx, [rbp+320h+Name]; lpName
0x1800301ba  call    cs:__imp_LocaleNameToLCID
0x1800301c1  nop     dword ptr [rax+rax+00h]
0x1800301c6  test    ax, ax
0x1800301c9  jz      short loc_180030200
0x1800301cb  movzx   r9d, ax
0x1800301cf  lea     r8, aMui04hx; "MUI\\%04hx"
0x1800301d6  mov     edx, r12d; unsigned __int64
0x1800301d9  lea     rcx, [rsp+420h+var_3E0]; unsigned __int16 *
0x1800301de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800301e3  mov     r9, [rsp+420h+FilePart]
0x1800301e8  lea     r8, [rsp+420h+var_3E0]
0x1800301ed  mov     rdx, r15
0x1800301f0  mov     rcx, rdi
0x1800301f3  call    LoadMUIFile
0x1800301f8  mov     rsi, rax
0x1800301fb  test    rax, rax
0x1800301fe  jnz     short loc_180030249
0x180030200  mov     eax, 409h
0x180030205  cmp     ax, r14w
0x180030209  jz      short loc_18003022A
0x18003020b  mov     r9, [rsp+420h+FilePart]
0x180030210  lea     r8, aMui0409; "MUI\\0409"
0x180030217  mov     rdx, r15
0x18003021a  mov     rcx, rdi
0x18003021d  call    LoadMUIFile
0x180030222  mov     rsi, rax
0x180030225  test    rax, rax
0x180030228  jnz     short loc_180030249
0x18003022a  mov     r9, [rsp+420h+FilePart]
0x18003022f  xor     r8d, r8d
0x180030232  mov     rdx, r15
0x180030235  mov     rcx, rdi
0x180030238  call    LoadMUIFile
0x18003023d  mov     rsi, rax
0x180030240  test    rax, rax
0x180030243  jz      loc_1800300E5
0x180030249  mov     rcx, rdi; hLibModule
0x18003024c  call    cs:__imp_FreeLibrary
0x180030253  nop     dword ptr [rax+rax+00h]
0x180030258  mov     rax, rsi
0x18003025b  jmp     short loc_180030294
0x18003025d  call    GetOSType
0x180030262  test    al, 26h
0x180030264  mov     rcx, rsi; lpLibFileName
0x180030267  setnz   bl
0x18003026a  xor     edx, edx; hFile
0x18003026c  mov     r8d, ebx; dwFlags
0x18003026f  call    cs:__imp_LoadLibraryExW
0x180030276  nop     dword ptr [rax+rax+00h]
0x18003027b  mov     rdi, rax
0x18003027e  mov     rax, rdi
0x180030281  jmp     short loc_180030294
0x180030283  mov     rcx, rdi; hLibModule
0x180030286  call    cs:__imp_FreeLibrary
0x18003028d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
