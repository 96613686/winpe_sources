# LoadMUILibraryW

- ea: `0x18000fc7c`
- end: `0x180010102`
- name: `LoadMUILibraryW`
- size: `1158`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f020`

## callees

- `0x18000f4dc`
- `0x18000f55c`
- `0x18000f670`
- `0x18000f798`
- `0x18000f80c`
- `0x18000f980`
- `0x18000faac`
- `0x18000fc7c`
- `0x180010250`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001000c`
- `KERNEL32!FreeLibrary` at `0x1800100a1`
- `KERNEL32!FreeLibrary` at `0x1800100d0`
- `KERNEL32!FreeLibrary` at `0x18001000c`
- `KERNEL32!FreeLibrary` at `0x1800100a1`
- `KERNEL32!FreeLibrary` at `0x1800100d0`
- `KERNEL32!SearchPathW` at `0x18000fd20`
- `KERNEL32!SearchPathW` at `0x18000fd20`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18000fe4d`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18000fe4d`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18000fd8f`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18000fd8f`
- `KERNEL32!FindResourceExW` at `0x18000fd66`
- `KERNEL32!FindResourceExW` at `0x18000fd66`
- `KERNEL32!LoadLibraryExW` at `0x18000fcdd`
- `KERNEL32!LoadLibraryExW` at `0x1800100bf`
- `KERNEL32!LoadLibraryExW` at `0x18000fcdd`
- `KERNEL32!LoadLibraryExW` at `0x1800100bf`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v6; // rdi
  WCHAR *v7; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v11; // r15
  bool v12; // zf
  __int64 InstallLanguage; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_180018D40 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_180018D40 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_180018D40 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
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
    if ( !LangID )
    {
      if ( (dword_180018D40 & 4) == 0 )
      {
        if ( (dword_180018D40 & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
            v12 = (_WORD)InstallLanguage == 1033;
LABEL_35:
            if ( !v12 )
            {
              LookupLangID(1033, v21, v23, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
LABEL_37:
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
            if ( MUIFile )
            {
LABEL_45:
              FreeLibrary(v6);
              return MUIFile;
            }
          }
        }
        goto LABEL_38;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
          if ( MUIFile )
            goto LABEL_45;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              goto LABEL_38;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_37;
          v12 = v11 == 1033;
          goto LABEL_35;
        }
        UserDefaultUILanguage = 1028;
      }
      goto LABEL_44;
    }
    if ( (dword_180018D40 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
LABEL_44:
      if ( MUIFile )
        goto LABEL_45;
    }
  }
LABEL_38:
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType(v15, v14) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v17, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000fc7c  mov     [rsp-8+arg_8], rbx
0x18000fc81  push    rbp
0x18000fc82  push    rsi
0x18000fc83  push    rdi
0x18000fc84  push    r12
0x18000fc86  push    r13
0x18000fc88  push    r14
0x18000fc8a  push    r15
0x18000fc8c  lea     rbp, [rsp-370h]
0x18000fc94  sub     rsp, 470h
0x18000fc9b  mov     rax, cs:__security_cookie
0x18000fca2  xor     rax, rsp
0x18000fca5  mov     [rbp+3A0h+var_40], rax
0x18000fcac  xor     r13d, r13d
0x18000fcaf  movzx   ebx, r8w
0x18000fcb3  mov     [rsp+4A0h+FilePart], r13
0x18000fcb8  mov     r12, rcx
0x18000fcbb  test    rcx, rcx
0x18000fcbe  jz      loc_1800100D6
0x18000fcc4  call    GetOSType
0x18000fcc9  mov     cs:dword_180018D40, eax
0x18000fccf  xor     edx, edx; hFile
0x18000fcd1  and     eax, 20h
0x18000fcd4  mov     rcx, r12; lpLibFileName
0x18000fcd7  or      eax, 2
0x18000fcda  mov     r8d, eax; dwFlags
0x18000fcdd  call    cs:__imp_LoadLibraryExW
0x18000fce3  mov     rdi, rax
0x18000fce6  test    rax, rax
0x18000fce9  jz      loc_1800100D6
0x18000fcef  test    byte ptr cs:dword_180018D40, 20h
0x18000fcf6  jnz     loc_1800100D8
0x18000fcfc  lea     rax, [rsp+4A0h+FilePart]
0x18000fd01  mov     r9d, 104h; nBufferLength
0x18000fd07  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x18000fd0c  xor     r8d, r8d; lpExtension
0x18000fd0f  lea     rax, [rbp+3A0h+Buffer]
0x18000fd16  mov     rdx, r12; lpFileName
0x18000fd19  xor     ecx, ecx; lpPath
0x18000fd1b  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x18000fd20  call    cs:__imp_SearchPathW
0x18000fd26  test    eax, eax
0x18000fd28  jz      loc_1800100CD
0x18000fd2e  mov     rcx, [rsp+4A0h+FilePart]
0x18000fd33  test    rcx, rcx
0x18000fd36  jnz     short loc_18000FD49
0x18000fd38  lea     rax, [rbp+3A0h+Buffer]
0x18000fd3f  mov     esi, r13d
0x18000fd42  mov     [rsp+4A0h+FilePart], rax
0x18000fd47  jmp     short loc_18000FD55
0x18000fd49  lea     rsi, [rbp+3A0h+Buffer]
0x18000fd50  mov     [rcx-2], r13w
0x18000fd55  xor     r9d, r9d; wLanguage
0x18000fd58  lea     rdx, Type; "MUI"
0x18000fd5f  mov     rcx, rdi; hModule
0x18000fd62  lea     r8d, [r9+1]; lpName
0x18000fd66  call    cs:__imp_FindResourceExW
0x18000fd6c  test    rax, rax
0x18000fd6f  jz      loc_18000FFFF
0x18000fd75  test    bx, bx
0x18000fd78  jnz     loc_180010059
0x18000fd7e  mov     eax, cs:dword_180018D40
0x18000fd84  test    al, 4
0x18000fd86  jz      loc_18000FF04
0x18000fd8c  mov     rbx, r13
0x18000fd8f  call    cs:__imp_GetUserDefaultUILanguage
0x18000fd95  mov     r15d, 404h
0x18000fd9b  movzx   r14d, ax
0x18000fd9f  cmp     ax, r15w
0x18000fda3  jnz     short loc_18000FDAE
0x18000fda5  call    GetCHTLangauge
0x18000fdaa  movzx   r14d, ax
0x18000fdae  lea     r9, [rbp+3A0h+var_3B0]
0x18000fdb2  movzx   ecx, r14w
0x18000fdb6  lea     r8, [rbp+3A0h+var_300]
0x18000fdbd  lea     rdx, [rsp+4A0h+var_460]
0x18000fdc2  call    LookupLangID
0x18000fdc7  test    eax, eax
0x18000fdc9  jz      loc_180010095
0x18000fdcf  mov     r9, [rsp+4A0h+FilePart]
0x18000fdd4  lea     r8, [rsp+4A0h+var_460]
0x18000fdd9  mov     rdx, rsi
0x18000fddc  mov     rcx, rdi
0x18000fddf  call    LoadMUIFile
0x18000fde4  mov     rbx, rax
0x18000fde7  test    rax, rax
0x18000fdea  jnz     loc_18001009E
0x18000fdf0  mov     r9, [rsp+4A0h+FilePart]
0x18000fdf5  lea     r8, [rbp+3A0h+var_300]
0x18000fdfc  mov     rdx, rsi
0x18000fdff  mov     rcx, rdi
0x18000fe02  call    LoadMUIFile
0x18000fe07  mov     rbx, rax
0x18000fe0a  test    rax, rax
0x18000fe0d  jnz     loc_18001009E
0x18000fe13  cmp     [rbp+3A0h+var_3B0], r13w
0x18000fe18  jz      short loc_18000FE3A
0x18000fe1a  mov     r9, [rsp+4A0h+FilePart]
0x18000fe1f  lea     r8, [rbp+3A0h+var_3B0]
0x18000fe23  mov     rdx, rsi
0x18000fe26  mov     rcx, rdi
0x18000fe29  call    LoadMUIFile
0x18000fe2e  mov     rbx, rax
0x18000fe31  test    rax, rax
0x18000fe34  jnz     loc_18001009E
0x18000fe3a  mov     eax, 0C04h
0x18000fe3f  cmp     r14w, ax
0x18000fe43  jnz     short loc_18000FE4D
0x18000fe45  mov     r14d, r15d
0x18000fe48  jmp     loc_18000FDAE
0x18000fe4d  call    cs:__imp_GetSystemDefaultUILanguage
0x18000fe53  movzx   r15d, ax
0x18000fe57  cmp     ax, r14w
0x18000fe5b  jz      loc_18000FEEC
0x18000fe61  lea     r9, [rbp+3A0h+var_3B0]
0x18000fe65  movzx   ecx, ax
0x18000fe68  lea     r8, [rbp+3A0h+var_300]
0x18000fe6f  lea     rdx, [rsp+4A0h+var_460]
0x18000fe74  call    LookupLangID
0x18000fe79  test    eax, eax
0x18000fe7b  jz      loc_18000FFFF
0x18000fe81  mov     r9, [rsp+4A0h+FilePart]
0x18000fe86  lea     r8, [rsp+4A0h+var_460]
0x18000fe8b  mov     rdx, rsi
0x18000fe8e  mov     rcx, rdi
0x18000fe91  call    LoadMUIFile
0x18000fe96  mov     rbx, rax
0x18000fe99  test    rax, rax
0x18000fe9c  jnz     loc_18001009E
0x18000fea2  mov     r9, [rsp+4A0h+FilePart]
0x18000fea7  lea     r8, [rbp+3A0h+var_300]
0x18000feae  mov     rdx, rsi
0x18000feb1  mov     rcx, rdi
0x18000feb4  call    LoadMUIFile
0x18000feb9  mov     rbx, rax
0x18000febc  test    rax, rax
0x18000febf  jnz     loc_18001009E
0x18000fec5  cmp     [rbp+3A0h+var_3B0], r13w
0x18000feca  jz      short loc_18000FEEC
0x18000fecc  mov     r9, [rsp+4A0h+FilePart]
0x18000fed1  lea     r8, [rbp+3A0h+var_3B0]
0x18000fed5  mov     rdx, rsi
0x18000fed8  mov     rcx, rdi
0x18000fedb  call    LoadMUIFile
0x18000fee0  mov     rbx, rax
0x18000fee3  test    rax, rax
0x18000fee6  jnz     loc_18001009E
0x18000feec  mov     ecx, 409h
0x18000fef1  cmp     cx, r14w
0x18000fef5  jz      loc_18000FFE0
0x18000fefb  cmp     cx, r15w
0x18000feff  jmp     loc_18000FFA9
0x18000ff04  test    al, 3
0x18000ff06  jz      loc_18000FFFF
0x18000ff0c  call    GetInstallLanguage
0x18000ff11  lea     r9, [rbp+3A0h+var_3B0]
0x18000ff15  movzx   ecx, ax
0x18000ff18  lea     r8, [rbp+3A0h+var_300]
0x18000ff1f  movzx   r14d, ax
0x18000ff23  lea     rdx, [rsp+4A0h+var_460]
0x18000ff28  call    LookupLangID
0x18000ff2d  test    eax, eax
0x18000ff2f  jz      loc_18000FFFF
0x18000ff35  mov     r9, [rsp+4A0h+FilePart]
0x18000ff3a  lea     r8, [rsp+4A0h+var_460]
0x18000ff3f  mov     rdx, rsi
0x18000ff42  mov     rcx, rdi
0x18000ff45  call    LoadMUIFile
0x18000ff4a  mov     rbx, rax
0x18000ff4d  test    rax, rax
0x18000ff50  jnz     loc_18001009E
0x18000ff56  mov     r9, [rsp+4A0h+FilePart]
0x18000ff5b  lea     r8, [rbp+3A0h+var_300]
0x18000ff62  mov     rdx, rsi
0x18000ff65  mov     rcx, rdi
0x18000ff68  call    LoadMUIFile
0x18000ff6d  mov     rbx, rax
0x18000ff70  test    rax, rax
0x18000ff73  jnz     loc_18001009E
0x18000ff79  cmp     [rbp+3A0h+var_3B0], r13w
0x18000ff7e  jz      short loc_18000FFA0
0x18000ff80  mov     r9, [rsp+4A0h+FilePart]
0x18000ff85  lea     r8, [rbp+3A0h+var_3B0]
0x18000ff89  mov     rdx, rsi
0x18000ff8c  mov     rcx, rdi
0x18000ff8f  call    LoadMUIFile
0x18000ff94  mov     rbx, rax
0x18000ff97  test    rax, rax
0x18000ff9a  jnz     loc_18001009E
0x18000ffa0  mov     ecx, 409h
0x18000ffa5  cmp     cx, r14w
0x18000ffa9  jz      short loc_18000FFE0
0x18000ffab  xor     r9d, r9d
0x18000ffae  lea     r8, [rbp+3A0h+var_300]
0x18000ffb5  lea     rdx, [rsp+4A0h+var_460]
0x18000ffba  call    LookupLangID
0x18000ffbf  mov     r9, [rsp+4A0h+FilePart]
0x18000ffc4  lea     r8, [rsp+4A0h+var_460]
0x18000ffc9  mov     rdx, rsi
0x18000ffcc  mov     rcx, rdi
0x18000ffcf  call    LoadMUIFile
0x18000ffd4  mov     rbx, rax
0x18000ffd7  test    rax, rax
0x18000ffda  jnz     loc_18001009E
0x18000ffe0  mov     r9, [rsp+4A0h+FilePart]
0x18000ffe5  xor     r8d, r8d
0x18000ffe8  mov     rdx, rsi
0x18000ffeb  mov     rcx, rdi
0x18000ffee  call    LoadMUIFile
0x18000fff3  mov     rbx, rax
0x18000fff6  test    rax, rax
0x18000fff9  jnz     loc_18001009E
0x18000ffff  test    dil, 1
0x180010003  jz      loc_1800100C8
0x180010009  mov     rcx, rdi; hLibModule
0x18001000c  call    cs:__imp_FreeLibrary
0x180010012  call    GetOSType
0x180010017  test    al, 38h
0x180010019  jz      loc_1800100AC
0x18001001f  mov     rax, [rsp+4A0h+FilePart]
0x180010024  lea     r8, aSS; "%s\\%s"
0x18001002b  mov     r9, rsi
0x18001002e  mov     [rsp+4A0h+lpBuffer], rax
0x180010033  mov     edx, 104h; unsigned __int64
0x180010038  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x18001003f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010044  xor     r8d, r8d
0x180010047  lea     rcx, [rbp+3A0h+Buffer]
0x18001004e  lea     edx, [r8+1]
0x180010052  call    MapMUIFile
0x180010057  jmp     short loc_1800100C5
0x180010059  test    byte ptr cs:dword_180018D40, 7
0x180010060  jz      short loc_18000FFFF
0x180010062  xor     r9d, r9d
0x180010065  lea     r8, [rbp+3A0h+var_300]
0x18001006c  lea     rdx, [rsp+4A0h+var_460]
0x180010071  movzx   ecx, bx
0x180010074  call    LookupLangID
0x180010079  test    eax, eax
0x18001007b  jz      short loc_18000FFFF
0x18001007d  mov     r9, [rsp+4A0h+FilePart]
0x180010082  lea     r8, [rsp+4A0h+var_460]
0x180010087  mov     rdx, rsi
0x18001008a  mov     rcx, rdi
0x18001008d  call    LoadMUIFile
0x180010092  mov     rbx, rax
0x180010095  test    rbx, rbx
0x180010098  jz      loc_18000FFFF
0x18001009e  mov     rcx, rdi; hLibModule
0x1800100a1  call    cs:__imp_FreeLibrary
0x1800100a7  mov     rax, rbx
0x1800100aa  jmp     short loc_1800100D8
0x1800100ac  call    GetOSType
0x1800100b1  test    al, 26h
0x1800100b3  mov     r8d, r13d
0x1800100b6  mov     rcx, r12; lpLibFileName
0x1800100b9  setnz   r8b; dwFlags
0x1800100bd  xor     edx, edx; hFile
0x1800100bf  call    cs:__imp_LoadLibraryExW
0x1800100c5  mov     rdi, rax
0x1800100c8  mov     rax, rdi
0x1800100cb  jmp     short loc_1800100D8
0x1800100cd  mov     rcx, rdi; hLibModule
0x1800100d0  call    cs:__imp_FreeLibrary
0x1800100d6  xor     eax, eax
0x1800100d8  mov     rcx, [rbp+3A0h+var_40]
0x1800100df  xor     rcx, rsp; StackCookie
0x1800100e2  call    __security_check_cookie
0x1800100e7  mov     rbx, [rsp+4A0h+arg_8]
0x1800100ef  add     rsp, 470h
0x1800100f6  pop     r15
0x1800100f8  pop     r14
0x1800100fa  pop     r13
0x1800100fc  pop     r12
0x1800100fe  pop     rdi
0x1800100ff  pop     rsi
0x180010100  pop     rbp
0x180010101  retn
```
