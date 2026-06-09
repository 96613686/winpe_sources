# LoadMUILibraryW

- ea: `0x14003faf0`
- end: `0x14003ff9b`
- name: `LoadMUILibraryW`
- size: `1195`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14003bd1c`

## callees

- `0x140009c78`
- `0x14003f42c`
- `0x14003f534`
- `0x14003f65c`
- `0x14003f6d0`
- `0x14003f844`
- `0x14003faf0`
- `0x140040106`
- `0x140040130`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x14003fc23`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x14003fc23`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003fdfa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ff41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ff70`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003fdfa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ff41`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ff70`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14003fbd3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14003fbd3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003fb4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003ff5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003fb4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003ff5f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14003fb8d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14003fb8d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x14003fbf3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x14003fbf3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x14003fce9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x14003fce9`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rdi
  WCHAR *v6; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR LCData[32]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_140084B54 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_140084B54 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_140084B54 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v5);
    return 0;
  }
  if ( FilePart )
  {
    v6 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v6 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v5, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_140084B54 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage != 1028 )
        goto LABEL_14;
      UserDefaultUILanguage = 3076;
      if ( !GetLocaleInfoW(0x404u, 8u, LCData, 32) || !wcsncmp_0(LCData, &word_14005AF54, 3u) )
        goto LABEL_14;
      while ( 1 )
      {
        UserDefaultUILanguage = 1028;
LABEL_14:
        if ( !(unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
          break;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
        if ( MUIFile )
          goto LABEL_43;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
        if ( MUIFile )
          goto LABEL_43;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
          if ( MUIFile )
            goto LABEL_43;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_43;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
            if ( MUIFile )
              goto LABEL_43;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
              if ( MUIFile )
                goto LABEL_43;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v10 != 1033 )
          {
            LookupLangID(1033, v21, v23, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_43;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
          if ( MUIFile )
            goto LABEL_43;
          break;
        }
      }
    }
    else if ( (dword_140084B54 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart)) != 0
          || v22[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v21, v23, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart)) != 0 )
        {
LABEL_43:
          FreeLibrary(v5);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v5 & 1) != 0 )
  {
    FreeLibrary(v5);
    if ( (GetOSType(v12, v11, v13) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v15, v14, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14003faf0  push    rbp
0x14003faf2  push    rbx
0x14003faf3  push    rsi
0x14003faf4  push    rdi
0x14003faf5  push    r12
0x14003faf7  push    r13
0x14003faf9  push    r14
0x14003fafb  push    r15
0x14003fafd  lea     rbp, [rsp-3B8h]
0x14003fb05  sub     rsp, 4B8h
0x14003fb0c  mov     rax, cs:__security_cookie
0x14003fb13  xor     rax, rsp
0x14003fb16  mov     [rbp+3F0h+var_50], rax
0x14003fb1d  xor     r13d, r13d
0x14003fb20  mov     r12, rcx
0x14003fb23  mov     [rsp+4F0h+FilePart], r13
0x14003fb28  test    rcx, rcx
0x14003fb2b  jz      loc_14003FF76
0x14003fb31  call    GetOSType
0x14003fb36  mov     cs:dword_140084B54, eax
0x14003fb3c  xor     edx, edx; hFile
0x14003fb3e  and     eax, 20h
0x14003fb41  mov     rcx, r12; lpLibFileName
0x14003fb44  or      eax, 2
0x14003fb47  mov     r8d, eax; dwFlags
0x14003fb4a  call    cs:__imp_LoadLibraryExW
0x14003fb50  mov     rdi, rax
0x14003fb53  test    rax, rax
0x14003fb56  jz      loc_14003FF76
0x14003fb5c  test    byte ptr cs:dword_140084B54, 20h
0x14003fb63  jnz     loc_14003FF78
0x14003fb69  lea     rax, [rsp+4F0h+FilePart]
0x14003fb6e  mov     r9d, 104h; nBufferLength
0x14003fb74  mov     [rsp+4F0h+lpFilePart], rax; lpFilePart
0x14003fb79  xor     r8d, r8d; lpExtension
0x14003fb7c  lea     rax, [rbp+3F0h+Buffer]
0x14003fb83  mov     rdx, r12; lpFileName
0x14003fb86  xor     ecx, ecx; lpPath
0x14003fb88  mov     [rsp+4F0h+lpBuffer], rax; lpBuffer
0x14003fb8d  call    cs:__imp_SearchPathW
0x14003fb93  test    eax, eax
0x14003fb95  jz      loc_14003FF6D
0x14003fb9b  mov     rcx, [rsp+4F0h+FilePart]
0x14003fba0  test    rcx, rcx
0x14003fba3  jnz     short loc_14003FBB6
0x14003fba5  lea     rax, [rbp+3F0h+Buffer]
0x14003fbac  mov     esi, r13d
0x14003fbaf  mov     [rsp+4F0h+FilePart], rax
0x14003fbb4  jmp     short loc_14003FBC2
0x14003fbb6  lea     rsi, [rbp+3F0h+Buffer]
0x14003fbbd  mov     [rcx-2], r13w
0x14003fbc2  xor     r9d, r9d; wLanguage
0x14003fbc5  lea     rdx, Type; "MUI"
0x14003fbcc  mov     rcx, rdi; hModule
0x14003fbcf  lea     r8d, [r9+1]; lpName
0x14003fbd3  call    cs:__imp_FindResourceExW
0x14003fbd9  test    rax, rax
0x14003fbdc  jz      loc_14003FDED
0x14003fbe2  mov     eax, cs:dword_140084B54
0x14003fbe8  test    al, 4
0x14003fbea  jz      loc_14003FE4A
0x14003fbf0  mov     rbx, r13
0x14003fbf3  call    cs:__imp_GetUserDefaultUILanguage
0x14003fbf9  mov     r15d, 404h
0x14003fbff  movzx   r14d, ax
0x14003fc03  cmp     ax, r15w
0x14003fc07  jnz     short loc_14003FC4E
0x14003fc09  mov     r9d, 20h ; ' '; cchData
0x14003fc0f  lea     r8, [rbp+3F0h+LCData]; lpLCData
0x14003fc16  mov     ecx, r15d; Locale
0x14003fc19  mov     r14d, 0C04h
0x14003fc1f  lea     edx, [r9-18h]; LCType
0x14003fc23  call    cs:__imp_GetLocaleInfoW
0x14003fc29  test    eax, eax
0x14003fc2b  jz      short loc_14003FC4E
0x14003fc2d  mov     r8d, 3; MaxCount
0x14003fc33  lea     rdx, word_14005AF54; String2
0x14003fc3a  lea     rcx, [rbp+3F0h+LCData]; String1
0x14003fc41  call    wcsncmp_0
0x14003fc46  test    eax, eax
0x14003fc48  jz      short loc_14003FC4E
0x14003fc4a  movzx   r14d, r15w
0x14003fc4e  lea     r9, [rbp+3F0h+var_400]
0x14003fc52  movzx   ecx, r14w
0x14003fc56  lea     r8, [rbp+3F0h+var_350]
0x14003fc5d  lea     rdx, [rsp+4F0h+var_4B0]
0x14003fc62  call    LookupLangID
0x14003fc67  test    eax, eax
0x14003fc69  jz      loc_14003FF35
0x14003fc6f  mov     r9, [rsp+4F0h+FilePart]
0x14003fc74  lea     r8, [rsp+4F0h+var_4B0]
0x14003fc79  mov     rdx, rsi
0x14003fc7c  mov     rcx, rdi
0x14003fc7f  call    LoadMUIFile
0x14003fc84  mov     rbx, rax
0x14003fc87  test    rax, rax
0x14003fc8a  jnz     loc_14003FF3E
0x14003fc90  mov     r9, [rsp+4F0h+FilePart]
0x14003fc95  lea     r8, [rbp+3F0h+var_350]
0x14003fc9c  mov     rdx, rsi
0x14003fc9f  mov     rcx, rdi
0x14003fca2  call    LoadMUIFile
0x14003fca7  mov     rbx, rax
0x14003fcaa  test    rax, rax
0x14003fcad  jnz     loc_14003FF3E
0x14003fcb3  cmp     [rbp+3F0h+var_400], r13w
0x14003fcb8  jz      short loc_14003FCDA
0x14003fcba  mov     r9, [rsp+4F0h+FilePart]
0x14003fcbf  lea     r8, [rbp+3F0h+var_400]
0x14003fcc3  mov     rdx, rsi
0x14003fcc6  mov     rcx, rdi
0x14003fcc9  call    LoadMUIFile
0x14003fcce  mov     rbx, rax
0x14003fcd1  test    rax, rax
0x14003fcd4  jnz     loc_14003FF3E
0x14003fcda  mov     eax, 0C04h
0x14003fcdf  cmp     r14w, ax
0x14003fce3  jz      loc_14003FC4A
0x14003fce9  call    cs:__imp_GetSystemDefaultUILanguage
0x14003fcef  movzx   r15d, ax
0x14003fcf3  cmp     ax, r14w
0x14003fcf7  jz      loc_14003FD88
0x14003fcfd  lea     r9, [rbp+3F0h+var_400]
0x14003fd01  movzx   ecx, ax
0x14003fd04  lea     r8, [rbp+3F0h+var_350]
0x14003fd0b  lea     rdx, [rsp+4F0h+var_4B0]
0x14003fd10  call    LookupLangID
0x14003fd15  test    eax, eax
0x14003fd17  jz      loc_14003FDED
0x14003fd1d  mov     r9, [rsp+4F0h+FilePart]
0x14003fd22  lea     r8, [rsp+4F0h+var_4B0]
0x14003fd27  mov     rdx, rsi
0x14003fd2a  mov     rcx, rdi
0x14003fd2d  call    LoadMUIFile
0x14003fd32  mov     rbx, rax
0x14003fd35  test    rax, rax
0x14003fd38  jnz     loc_14003FF3E
0x14003fd3e  mov     r9, [rsp+4F0h+FilePart]
0x14003fd43  lea     r8, [rbp+3F0h+var_350]
0x14003fd4a  mov     rdx, rsi
0x14003fd4d  mov     rcx, rdi
0x14003fd50  call    LoadMUIFile
0x14003fd55  mov     rbx, rax
0x14003fd58  test    rax, rax
0x14003fd5b  jnz     loc_14003FF3E
0x14003fd61  cmp     [rbp+3F0h+var_400], r13w
0x14003fd66  jz      short loc_14003FD88
0x14003fd68  mov     r9, [rsp+4F0h+FilePart]
0x14003fd6d  lea     r8, [rbp+3F0h+var_400]
0x14003fd71  mov     rdx, rsi
0x14003fd74  mov     rcx, rdi
0x14003fd77  call    LoadMUIFile
0x14003fd7c  mov     rbx, rax
0x14003fd7f  test    rax, rax
0x14003fd82  jnz     loc_14003FF3E
0x14003fd88  mov     ecx, 409h
0x14003fd8d  cmp     cx, r14w
0x14003fd91  jz      short loc_14003FDCE
0x14003fd93  cmp     cx, r15w
0x14003fd97  jz      short loc_14003FDCE
0x14003fd99  xor     r9d, r9d
0x14003fd9c  lea     r8, [rbp+3F0h+var_350]
0x14003fda3  lea     rdx, [rsp+4F0h+var_4B0]
0x14003fda8  call    LookupLangID
0x14003fdad  mov     r9, [rsp+4F0h+FilePart]
0x14003fdb2  lea     r8, [rsp+4F0h+var_4B0]
0x14003fdb7  mov     rdx, rsi
0x14003fdba  mov     rcx, rdi
0x14003fdbd  call    LoadMUIFile
0x14003fdc2  mov     rbx, rax
0x14003fdc5  test    rax, rax
0x14003fdc8  jnz     loc_14003FF3E
0x14003fdce  mov     r9, [rsp+4F0h+FilePart]
0x14003fdd3  xor     r8d, r8d
0x14003fdd6  mov     rdx, rsi
0x14003fdd9  mov     rcx, rdi
0x14003fddc  call    LoadMUIFile
0x14003fde1  mov     rbx, rax
0x14003fde4  test    rax, rax
0x14003fde7  jnz     loc_14003FF3E
0x14003fded  test    dil, 1
0x14003fdf1  jz      loc_14003FF68
0x14003fdf7  mov     rcx, rdi; hLibModule
0x14003fdfa  call    cs:__imp_FreeLibrary
0x14003fe00  call    GetOSType
0x14003fe05  test    al, 38h
0x14003fe07  jz      loc_14003FF4C
0x14003fe0d  mov     rax, [rsp+4F0h+FilePart]
0x14003fe12  lea     r8, aSS; "%s\\%s"
0x14003fe19  mov     r9, rsi
0x14003fe1c  mov     [rsp+4F0h+lpBuffer], rax
0x14003fe21  mov     edx, 104h; unsigned __int64
0x14003fe26  lea     rcx, [rbp+3F0h+Buffer]; unsigned __int16 *
0x14003fe2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003fe32  xor     r8d, r8d
0x14003fe35  lea     rcx, [rbp+3F0h+Buffer]
0x14003fe3c  lea     edx, [r8+1]
0x14003fe40  call    MapMUIFile
0x14003fe45  jmp     loc_14003FF65
0x14003fe4a  test    al, 3
0x14003fe4c  jz      short loc_14003FDED
0x14003fe4e  call    GetInstallLanguage
0x14003fe53  lea     r9, [rbp+3F0h+var_400]
0x14003fe57  movzx   ecx, ax
0x14003fe5a  lea     r8, [rbp+3F0h+var_350]
0x14003fe61  movzx   r14d, ax
0x14003fe65  lea     rdx, [rsp+4F0h+var_4B0]
0x14003fe6a  call    LookupLangID
0x14003fe6f  test    eax, eax
0x14003fe71  jz      loc_14003FDED
0x14003fe77  mov     r9, [rsp+4F0h+FilePart]
0x14003fe7c  lea     r8, [rsp+4F0h+var_4B0]
0x14003fe81  mov     rdx, rsi
0x14003fe84  mov     rcx, rdi
0x14003fe87  call    LoadMUIFile
0x14003fe8c  mov     rbx, rax
0x14003fe8f  test    rax, rax
0x14003fe92  jnz     loc_14003FF3E
0x14003fe98  mov     r9, [rsp+4F0h+FilePart]
0x14003fe9d  lea     r8, [rbp+3F0h+var_350]
0x14003fea4  mov     rdx, rsi
0x14003fea7  mov     rcx, rdi
0x14003feaa  call    LoadMUIFile
0x14003feaf  mov     rbx, rax
0x14003feb2  test    rax, rax
0x14003feb5  jnz     loc_14003FF3E
0x14003febb  cmp     [rbp+3F0h+var_400], r13w
0x14003fec0  jz      short loc_14003FEDE
0x14003fec2  mov     r9, [rsp+4F0h+FilePart]
0x14003fec7  lea     r8, [rbp+3F0h+var_400]
0x14003fecb  mov     rdx, rsi
0x14003fece  mov     rcx, rdi
0x14003fed1  call    LoadMUIFile
0x14003fed6  mov     rbx, rax
0x14003fed9  test    rax, rax
0x14003fedc  jnz     short loc_14003FF3E
0x14003fede  mov     ecx, 409h
0x14003fee3  cmp     cx, r14w
0x14003fee7  jz      short loc_14003FF1A
0x14003fee9  xor     r9d, r9d
0x14003feec  lea     r8, [rbp+3F0h+var_350]
0x14003fef3  lea     rdx, [rsp+4F0h+var_4B0]
0x14003fef8  call    LookupLangID
0x14003fefd  mov     r9, [rsp+4F0h+FilePart]
0x14003ff02  lea     r8, [rsp+4F0h+var_4B0]
0x14003ff07  mov     rdx, rsi
0x14003ff0a  mov     rcx, rdi
0x14003ff0d  call    LoadMUIFile
0x14003ff12  mov     rbx, rax
0x14003ff15  test    rax, rax
0x14003ff18  jnz     short loc_14003FF3E
0x14003ff1a  mov     r9, [rsp+4F0h+FilePart]
0x14003ff1f  xor     r8d, r8d
0x14003ff22  mov     rdx, rsi
0x14003ff25  mov     rcx, rdi
0x14003ff28  call    LoadMUIFile
0x14003ff2d  mov     rbx, rax
0x14003ff30  test    rax, rax
0x14003ff33  jnz     short loc_14003FF3E
0x14003ff35  test    rbx, rbx
0x14003ff38  jz      loc_14003FDED
0x14003ff3e  mov     rcx, rdi; hLibModule
0x14003ff41  call    cs:__imp_FreeLibrary
0x14003ff47  mov     rax, rbx
0x14003ff4a  jmp     short loc_14003FF78
0x14003ff4c  call    GetOSType
0x14003ff51  test    al, 26h
0x14003ff53  mov     r8d, r13d
0x14003ff56  mov     rcx, r12; lpLibFileName
0x14003ff59  setnz   r8b; dwFlags
0x14003ff5d  xor     edx, edx; hFile
0x14003ff5f  call    cs:__imp_LoadLibraryExW
0x14003ff65  mov     rdi, rax
0x14003ff68  mov     rax, rdi
0x14003ff6b  jmp     short loc_14003FF78
0x14003ff6d  mov     rcx, rdi; hLibModule
0x14003ff70  call    cs:__imp_FreeLibrary
0x14003ff76  xor     eax, eax
0x14003ff78  mov     rcx, [rbp+3F0h+var_50]
0x14003ff7f  xor     rcx, rsp; StackCookie
0x14003ff82  call    __security_check_cookie
0x14003ff87  add     rsp, 4B8h
0x14003ff8e  pop     r15
0x14003ff90  pop     r14
0x14003ff92  pop     r13
0x14003ff94  pop     r12
0x14003ff96  pop     rdi
0x14003ff97  pop     rsi
0x14003ff98  pop     rbx
0x14003ff99  pop     rbp
0x14003ff9a  retn
```
