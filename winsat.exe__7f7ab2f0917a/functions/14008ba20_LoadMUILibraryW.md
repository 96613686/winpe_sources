# LoadMUILibraryW

- ea: `0x14008ba20`
- end: `0x14008be8f`
- name: `LoadMUILibraryW`
- size: `1135`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14004fbf0`

## callees

- `0x14001f940`
- `0x14008b33c`
- `0x14008b3bc`
- `0x14008b4d0`
- `0x14008b5f8`
- `0x14008b66c`
- `0x14008b7e0`
- `0x14008ba20`
- `0x140113220`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14008bcec`
- `KERNEL32!FreeLibrary` at `0x14008be33`
- `KERNEL32!FreeLibrary` at `0x14008be66`
- `KERNEL32!FreeLibrary` at `0x14008bcec`
- `KERNEL32!FreeLibrary` at `0x14008be33`
- `KERNEL32!FreeLibrary` at `0x14008be66`
- `KERNEL32!FindResourceExW` at `0x14008bafd`
- `KERNEL32!FindResourceExW` at `0x14008bafd`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14008bb1d`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14008bb1d`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x14008bbdb`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x14008bbdb`
- `KERNEL32!SearchPathW` at `0x14008bab7`
- `KERNEL32!SearchPathW` at `0x14008bab7`
- `KERNEL32!LoadLibraryExW` at `0x14008ba70`
- `KERNEL32!LoadLibraryExW` at `0x14008be55`
- `KERNEL32!LoadLibraryExW` at `0x14008ba70`
- `KERNEL32!LoadLibraryExW` at `0x14008be55`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v4; // rdi
  WCHAR *v5; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  dword_1401CBCC8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(&::pszFullModuleName, 0, dword_1401CBCC8 & 0x20 | 2u);
  v4 = result;
  if ( !result )
    return 0;
  if ( (dword_1401CBCC8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, &::pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v4);
    return 0;
  }
  if ( FilePart )
  {
    v5 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v5 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v4, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_1401CBCC8 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
          if ( MUIFile )
            goto LABEL_41;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v9 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart);
              if ( MUIFile )
                goto LABEL_41;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v9 != 1033 )
          {
            LookupLangID(1033, v20, v22, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart);
          if ( MUIFile )
            goto LABEL_41;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_1401CBCC8 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v22, FilePart)) != 0
          || v21[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v21, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v20, v22, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, v20, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v4, v5, 0, FilePart)) != 0 )
        {
LABEL_41:
          FreeLibrary(v4);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v4 & 1) != 0 )
  {
    FreeLibrary(v4);
    if ( (GetOSType(v11, v10, v12) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v5, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v14, v13, v15);
      return LoadLibraryExW(&::pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14008ba20  push    rbp
0x14008ba22  push    rbx
0x14008ba23  push    rsi
0x14008ba24  push    rdi
0x14008ba25  push    r12
0x14008ba27  push    r14
0x14008ba29  push    r15
0x14008ba2b  lea     rbp, [rsp-370h]
0x14008ba33  sub     rsp, 470h
0x14008ba3a  mov     rax, cs:__security_cookie
0x14008ba41  xor     rax, rsp
0x14008ba44  mov     [rbp+3A0h+var_40], rax
0x14008ba4b  xor     r12d, r12d
0x14008ba4e  mov     [rsp+4A0h+FilePart], r12
0x14008ba53  call    GetOSType
0x14008ba58  mov     cs:dword_1401CBCC8, eax
0x14008ba5e  lea     rcx, pszFullModuleName; lpLibFileName
0x14008ba65  and     eax, 20h
0x14008ba68  xor     edx, edx; hFile
0x14008ba6a  or      eax, 2
0x14008ba6d  mov     r8d, eax; dwFlags
0x14008ba70  call    cs:__imp_LoadLibraryExW
0x14008ba76  mov     rdi, rax
0x14008ba79  test    rax, rax
0x14008ba7c  jz      loc_14008BE6C
0x14008ba82  test    byte ptr cs:dword_1401CBCC8, 20h
0x14008ba89  jnz     loc_14008BE6E
0x14008ba8f  lea     rax, [rsp+4A0h+FilePart]
0x14008ba94  mov     r9d, 104h; nBufferLength
0x14008ba9a  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x14008ba9f  lea     rdx, pszFullModuleName; lpFileName
0x14008baa6  lea     rax, [rbp+3A0h+Buffer]
0x14008baad  xor     r8d, r8d; lpExtension
0x14008bab0  xor     ecx, ecx; lpPath
0x14008bab2  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x14008bab7  call    cs:__imp_SearchPathW
0x14008babd  test    eax, eax
0x14008babf  jz      loc_14008BE63
0x14008bac5  mov     rcx, [rsp+4A0h+FilePart]
0x14008baca  test    rcx, rcx
0x14008bacd  jnz     short loc_14008BAE0
0x14008bacf  lea     rax, [rbp+3A0h+Buffer]
0x14008bad6  mov     esi, r12d
0x14008bad9  mov     [rsp+4A0h+FilePart], rax
0x14008bade  jmp     short loc_14008BAEC
0x14008bae0  lea     rsi, [rbp+3A0h+Buffer]
0x14008bae7  mov     [rcx-2], r12w
0x14008baec  xor     r9d, r9d; wLanguage
0x14008baef  lea     rdx, Type; "MUI"
0x14008baf6  mov     rcx, rdi; hModule
0x14008baf9  lea     r8d, [r9+1]; lpName
0x14008bafd  call    cs:__imp_FindResourceExW
0x14008bb03  test    rax, rax
0x14008bb06  jz      loc_14008BCDF
0x14008bb0c  mov     eax, cs:dword_1401CBCC8
0x14008bb12  test    al, 4
0x14008bb14  jz      loc_14008BD3C
0x14008bb1a  mov     rbx, r12
0x14008bb1d  call    cs:__imp_GetUserDefaultUILanguage
0x14008bb23  mov     r15d, 404h
0x14008bb29  movzx   r14d, ax
0x14008bb2d  cmp     ax, r15w
0x14008bb31  jnz     short loc_14008BB3C
0x14008bb33  call    GetCHTLangauge
0x14008bb38  movzx   r14d, ax
0x14008bb3c  lea     r9, [rbp+3A0h+var_3B0]
0x14008bb40  movzx   ecx, r14w
0x14008bb44  lea     r8, [rbp+3A0h+var_300]
0x14008bb4b  lea     rdx, [rsp+4A0h+var_460]
0x14008bb50  call    LookupLangID
0x14008bb55  test    eax, eax
0x14008bb57  jz      loc_14008BE27
0x14008bb5d  mov     r9, [rsp+4A0h+FilePart]
0x14008bb62  lea     r8, [rsp+4A0h+var_460]
0x14008bb67  mov     rdx, rsi
0x14008bb6a  mov     rcx, rdi
0x14008bb6d  call    LoadMUIFile
0x14008bb72  mov     rbx, rax
0x14008bb75  test    rax, rax
0x14008bb78  jnz     loc_14008BE30
0x14008bb7e  mov     r9, [rsp+4A0h+FilePart]
0x14008bb83  lea     r8, [rbp+3A0h+var_300]
0x14008bb8a  mov     rdx, rsi
0x14008bb8d  mov     rcx, rdi
0x14008bb90  call    LoadMUIFile
0x14008bb95  mov     rbx, rax
0x14008bb98  test    rax, rax
0x14008bb9b  jnz     loc_14008BE30
0x14008bba1  cmp     [rbp+3A0h+var_3B0], r12w
0x14008bba6  jz      short loc_14008BBC8
0x14008bba8  mov     r9, [rsp+4A0h+FilePart]
0x14008bbad  lea     r8, [rbp+3A0h+var_3B0]
0x14008bbb1  mov     rdx, rsi
0x14008bbb4  mov     rcx, rdi
0x14008bbb7  call    LoadMUIFile
0x14008bbbc  mov     rbx, rax
0x14008bbbf  test    rax, rax
0x14008bbc2  jnz     loc_14008BE30
0x14008bbc8  mov     eax, 0C04h
0x14008bbcd  cmp     r14w, ax
0x14008bbd1  jnz     short loc_14008BBDB
0x14008bbd3  mov     r14d, r15d
0x14008bbd6  jmp     loc_14008BB3C
0x14008bbdb  call    cs:__imp_GetSystemDefaultUILanguage
0x14008bbe1  movzx   r15d, ax
0x14008bbe5  cmp     ax, r14w
0x14008bbe9  jz      loc_14008BC7A
0x14008bbef  lea     r9, [rbp+3A0h+var_3B0]
0x14008bbf3  movzx   ecx, ax
0x14008bbf6  lea     r8, [rbp+3A0h+var_300]
0x14008bbfd  lea     rdx, [rsp+4A0h+var_460]
0x14008bc02  call    LookupLangID
0x14008bc07  test    eax, eax
0x14008bc09  jz      loc_14008BCDF
0x14008bc0f  mov     r9, [rsp+4A0h+FilePart]
0x14008bc14  lea     r8, [rsp+4A0h+var_460]
0x14008bc19  mov     rdx, rsi
0x14008bc1c  mov     rcx, rdi
0x14008bc1f  call    LoadMUIFile
0x14008bc24  mov     rbx, rax
0x14008bc27  test    rax, rax
0x14008bc2a  jnz     loc_14008BE30
0x14008bc30  mov     r9, [rsp+4A0h+FilePart]
0x14008bc35  lea     r8, [rbp+3A0h+var_300]
0x14008bc3c  mov     rdx, rsi
0x14008bc3f  mov     rcx, rdi
0x14008bc42  call    LoadMUIFile
0x14008bc47  mov     rbx, rax
0x14008bc4a  test    rax, rax
0x14008bc4d  jnz     loc_14008BE30
0x14008bc53  cmp     [rbp+3A0h+var_3B0], r12w
0x14008bc58  jz      short loc_14008BC7A
0x14008bc5a  mov     r9, [rsp+4A0h+FilePart]
0x14008bc5f  lea     r8, [rbp+3A0h+var_3B0]
0x14008bc63  mov     rdx, rsi
0x14008bc66  mov     rcx, rdi
0x14008bc69  call    LoadMUIFile
0x14008bc6e  mov     rbx, rax
0x14008bc71  test    rax, rax
0x14008bc74  jnz     loc_14008BE30
0x14008bc7a  mov     ecx, 409h
0x14008bc7f  cmp     cx, r14w
0x14008bc83  jz      short loc_14008BCC0
0x14008bc85  cmp     cx, r15w
0x14008bc89  jz      short loc_14008BCC0
0x14008bc8b  xor     r9d, r9d
0x14008bc8e  lea     r8, [rbp+3A0h+var_300]
0x14008bc95  lea     rdx, [rsp+4A0h+var_460]
0x14008bc9a  call    LookupLangID
0x14008bc9f  mov     r9, [rsp+4A0h+FilePart]
0x14008bca4  lea     r8, [rsp+4A0h+var_460]
0x14008bca9  mov     rdx, rsi
0x14008bcac  mov     rcx, rdi
0x14008bcaf  call    LoadMUIFile
0x14008bcb4  mov     rbx, rax
0x14008bcb7  test    rax, rax
0x14008bcba  jnz     loc_14008BE30
0x14008bcc0  mov     r9, [rsp+4A0h+FilePart]
0x14008bcc5  xor     r8d, r8d
0x14008bcc8  mov     rdx, rsi
0x14008bccb  mov     rcx, rdi
0x14008bcce  call    LoadMUIFile
0x14008bcd3  mov     rbx, rax
0x14008bcd6  test    rax, rax
0x14008bcd9  jnz     loc_14008BE30
0x14008bcdf  test    dil, 1
0x14008bce3  jz      loc_14008BE5E
0x14008bce9  mov     rcx, rdi; hLibModule
0x14008bcec  call    cs:__imp_FreeLibrary
0x14008bcf2  call    GetOSType
0x14008bcf7  test    al, 38h
0x14008bcf9  jz      loc_14008BE3E
0x14008bcff  mov     rax, [rsp+4A0h+FilePart]
0x14008bd04  lea     r8, aSS_0; "%s\\%s"
0x14008bd0b  mov     r9, rsi
0x14008bd0e  mov     [rsp+4A0h+lpBuffer], rax
0x14008bd13  mov     edx, 104h; unsigned __int64
0x14008bd18  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x14008bd1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008bd24  xor     r8d, r8d
0x14008bd27  lea     rcx, [rbp+3A0h+Buffer]
0x14008bd2e  lea     edx, [r8+1]
0x14008bd32  call    MapMUIFile
0x14008bd37  jmp     loc_14008BE5B
0x14008bd3c  test    al, 3
0x14008bd3e  jz      short loc_14008BCDF
0x14008bd40  call    GetInstallLanguage
0x14008bd45  lea     r9, [rbp+3A0h+var_3B0]
0x14008bd49  movzx   ecx, ax
0x14008bd4c  lea     r8, [rbp+3A0h+var_300]
0x14008bd53  movzx   r14d, ax
0x14008bd57  lea     rdx, [rsp+4A0h+var_460]
0x14008bd5c  call    LookupLangID
0x14008bd61  test    eax, eax
0x14008bd63  jz      loc_14008BCDF
0x14008bd69  mov     r9, [rsp+4A0h+FilePart]
0x14008bd6e  lea     r8, [rsp+4A0h+var_460]
0x14008bd73  mov     rdx, rsi
0x14008bd76  mov     rcx, rdi
0x14008bd79  call    LoadMUIFile
0x14008bd7e  mov     rbx, rax
0x14008bd81  test    rax, rax
0x14008bd84  jnz     loc_14008BE30
0x14008bd8a  mov     r9, [rsp+4A0h+FilePart]
0x14008bd8f  lea     r8, [rbp+3A0h+var_300]
0x14008bd96  mov     rdx, rsi
0x14008bd99  mov     rcx, rdi
0x14008bd9c  call    LoadMUIFile
0x14008bda1  mov     rbx, rax
0x14008bda4  test    rax, rax
0x14008bda7  jnz     loc_14008BE30
0x14008bdad  cmp     [rbp+3A0h+var_3B0], r12w
0x14008bdb2  jz      short loc_14008BDD0
0x14008bdb4  mov     r9, [rsp+4A0h+FilePart]
0x14008bdb9  lea     r8, [rbp+3A0h+var_3B0]
0x14008bdbd  mov     rdx, rsi
0x14008bdc0  mov     rcx, rdi
0x14008bdc3  call    LoadMUIFile
0x14008bdc8  mov     rbx, rax
0x14008bdcb  test    rax, rax
0x14008bdce  jnz     short loc_14008BE30
0x14008bdd0  mov     ecx, 409h
0x14008bdd5  cmp     cx, r14w
0x14008bdd9  jz      short loc_14008BE0C
0x14008bddb  xor     r9d, r9d
0x14008bdde  lea     r8, [rbp+3A0h+var_300]
0x14008bde5  lea     rdx, [rsp+4A0h+var_460]
0x14008bdea  call    LookupLangID
0x14008bdef  mov     r9, [rsp+4A0h+FilePart]
0x14008bdf4  lea     r8, [rsp+4A0h+var_460]
0x14008bdf9  mov     rdx, rsi
0x14008bdfc  mov     rcx, rdi
0x14008bdff  call    LoadMUIFile
0x14008be04  mov     rbx, rax
0x14008be07  test    rax, rax
0x14008be0a  jnz     short loc_14008BE30
0x14008be0c  mov     r9, [rsp+4A0h+FilePart]
0x14008be11  xor     r8d, r8d
0x14008be14  mov     rdx, rsi
0x14008be17  mov     rcx, rdi
0x14008be1a  call    LoadMUIFile
0x14008be1f  mov     rbx, rax
0x14008be22  test    rax, rax
0x14008be25  jnz     short loc_14008BE30
0x14008be27  test    rbx, rbx
0x14008be2a  jz      loc_14008BCDF
0x14008be30  mov     rcx, rdi; hLibModule
0x14008be33  call    cs:__imp_FreeLibrary
0x14008be39  mov     rax, rbx
0x14008be3c  jmp     short loc_14008BE6E
0x14008be3e  call    GetOSType
0x14008be43  test    al, 26h
0x14008be45  lea     rcx, pszFullModuleName; lpLibFileName
0x14008be4c  mov     r8d, r12d
0x14008be4f  setnz   r8b; dwFlags
0x14008be53  xor     edx, edx; hFile
0x14008be55  call    cs:__imp_LoadLibraryExW
0x14008be5b  mov     rdi, rax
0x14008be5e  mov     rax, rdi
0x14008be61  jmp     short loc_14008BE6E
0x14008be63  mov     rcx, rdi; hLibModule
0x14008be66  call    cs:__imp_FreeLibrary
0x14008be6c  xor     eax, eax
0x14008be6e  mov     rcx, [rbp+3A0h+var_40]
0x14008be75  xor     rcx, rsp; StackCookie
0x14008be78  call    __security_check_cookie
0x14008be7d  add     rsp, 470h
0x14008be84  pop     r15
0x14008be86  pop     r14
0x14008be88  pop     r12
0x14008be8a  pop     rdi
0x14008be8b  pop     rsi
0x14008be8c  pop     rbx
0x14008be8d  pop     rbp
0x14008be8e  retn
```
