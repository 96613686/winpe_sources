# LoadMUILibraryW

- ea: `0x18000cba0`
- end: `0x18000d05e`
- name: `LoadMUILibraryW`
- size: `1214`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b1c0`

## callees

- `0x18000c480`
- `0x18000c594`
- `0x18000c6bc`
- `0x18000c730`
- `0x18000c8a4`
- `0x18000c9d0`
- `0x18000cba0`
- `0x18000d196`
- `0x18000d1c0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18000cc8a`
- `KERNEL32!FindResourceExW` at `0x18000cc8a`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18000ccb3`
- `KERNEL32!GetUserDefaultUILanguage` at `0x18000ccb3`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18000cda9`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x18000cda9`
- `KERNEL32!SearchPathW` at `0x18000cc44`
- `KERNEL32!SearchPathW` at `0x18000cc44`
- `KERNEL32!GetLocaleInfoW` at `0x18000cce3`
- `KERNEL32!GetLocaleInfoW` at `0x18000cce3`
- `KERNEL32!FreeLibrary` at `0x18000cf68`
- `KERNEL32!FreeLibrary` at `0x18000cffd`
- `KERNEL32!FreeLibrary` at `0x18000d02c`
- `KERNEL32!FreeLibrary` at `0x18000cf68`
- `KERNEL32!FreeLibrary` at `0x18000cffd`
- `KERNEL32!FreeLibrary` at `0x18000d02c`
- `KERNEL32!LoadLibraryExW` at `0x18000cc01`
- `KERNEL32!LoadLibraryExW` at `0x18000d01b`
- `KERNEL32!LoadLibraryExW` at `0x18000cc01`
- `KERNEL32!LoadLibraryExW` at `0x18000d01b`

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
  WCHAR LCData[32]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_180014918 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_180014918 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_180014918 & 0x20) != 0 )
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
      if ( (dword_180014918 & 4) == 0 )
      {
        if ( (dword_180014918 & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
            v12 = (_WORD)InstallLanguage == 1033;
LABEL_36:
            if ( !v12 )
            {
              LookupLangID(1033, v21, v23, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
LABEL_38:
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
            if ( MUIFile )
            {
LABEL_46:
              FreeLibrary(v6);
              return MUIFile;
            }
          }
        }
        goto LABEL_39;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage != 1028 )
        goto LABEL_15;
      UserDefaultUILanguage = 3076;
      if ( !GetLocaleInfoW(0x404u, 8u, LCData, 32) || !wcsncmp_0(LCData, &String2, 3u) )
        goto LABEL_15;
      while ( 1 )
      {
        UserDefaultUILanguage = 1028;
LABEL_15:
        if ( !(unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
        if ( MUIFile )
          goto LABEL_46;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
        if ( MUIFile )
          goto LABEL_46;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
          if ( MUIFile )
            goto LABEL_46;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              goto LABEL_39;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_46;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_46;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_38;
          v12 = v11 == 1033;
          goto LABEL_36;
        }
      }
    }
    if ( (dword_180014918 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
LABEL_45:
      if ( MUIFile )
        goto LABEL_46;
    }
  }
LABEL_39:
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
0x18000cba0  mov     [rsp-8+arg_8], rbx
0x18000cba5  push    rbp
0x18000cba6  push    rsi
0x18000cba7  push    rdi
0x18000cba8  push    r12
0x18000cbaa  push    r13
0x18000cbac  push    r14
0x18000cbae  push    r15
0x18000cbb0  lea     rbp, [rsp-3B0h]
0x18000cbb8  sub     rsp, 4B0h
0x18000cbbf  mov     rax, cs:__security_cookie
0x18000cbc6  xor     rax, rsp
0x18000cbc9  mov     [rbp+3E0h+var_40], rax
0x18000cbd0  xor     r13d, r13d
0x18000cbd3  movzx   ebx, r8w
0x18000cbd7  mov     [rsp+4E0h+FilePart], r13
0x18000cbdc  mov     r12, rcx
0x18000cbdf  test    rcx, rcx
0x18000cbe2  jz      loc_18000D032
0x18000cbe8  call    GetOSType
0x18000cbed  mov     cs:dword_180014918, eax
0x18000cbf3  xor     edx, edx; hFile
0x18000cbf5  and     eax, 20h
0x18000cbf8  mov     rcx, r12; lpLibFileName
0x18000cbfb  or      eax, 2
0x18000cbfe  mov     r8d, eax; dwFlags
0x18000cc01  call    cs:__imp_LoadLibraryExW
0x18000cc07  mov     rdi, rax
0x18000cc0a  test    rax, rax
0x18000cc0d  jz      loc_18000D032
0x18000cc13  test    byte ptr cs:dword_180014918, 20h
0x18000cc1a  jnz     loc_18000D034
0x18000cc20  lea     rax, [rsp+4E0h+FilePart]
0x18000cc25  mov     r9d, 104h; nBufferLength
0x18000cc2b  mov     [rsp+4E0h+lpFilePart], rax; lpFilePart
0x18000cc30  xor     r8d, r8d; lpExtension
0x18000cc33  lea     rax, [rbp+3E0h+Buffer]
0x18000cc3a  mov     rdx, r12; lpFileName
0x18000cc3d  xor     ecx, ecx; lpPath
0x18000cc3f  mov     [rsp+4E0h+lpBuffer], rax; lpBuffer
0x18000cc44  call    cs:__imp_SearchPathW
0x18000cc4a  test    eax, eax
0x18000cc4c  jz      loc_18000D029
0x18000cc52  mov     rcx, [rsp+4E0h+FilePart]
0x18000cc57  test    rcx, rcx
0x18000cc5a  jnz     short loc_18000CC6D
0x18000cc5c  lea     rax, [rbp+3E0h+Buffer]
0x18000cc63  mov     esi, r13d
0x18000cc66  mov     [rsp+4E0h+FilePart], rax
0x18000cc6b  jmp     short loc_18000CC79
0x18000cc6d  lea     rsi, [rbp+3E0h+Buffer]
0x18000cc74  mov     [rcx-2], r13w
0x18000cc79  xor     r9d, r9d; wLanguage
0x18000cc7c  lea     rdx, Type; "MUI"
0x18000cc83  mov     rcx, rdi; hModule
0x18000cc86  lea     r8d, [r9+1]; lpName
0x18000cc8a  call    cs:__imp_FindResourceExW
0x18000cc90  test    rax, rax
0x18000cc93  jz      loc_18000CF5B
0x18000cc99  test    bx, bx
0x18000cc9c  jnz     loc_18000CFB5
0x18000cca2  mov     eax, cs:dword_180014918
0x18000cca8  test    al, 4
0x18000ccaa  jz      loc_18000CE60
0x18000ccb0  mov     rbx, r13
0x18000ccb3  call    cs:__imp_GetUserDefaultUILanguage
0x18000ccb9  mov     r15d, 404h
0x18000ccbf  movzx   r14d, ax
0x18000ccc3  cmp     ax, r15w
0x18000ccc7  jnz     short loc_18000CD0E
0x18000ccc9  mov     r9d, 20h ; ' '; cchData
0x18000cccf  lea     r8, [rbp+3E0h+LCData]; lpLCData
0x18000ccd6  mov     ecx, r15d; Locale
0x18000ccd9  mov     r14d, 0C04h
0x18000ccdf  lea     edx, [r9-18h]; LCType
0x18000cce3  call    cs:__imp_GetLocaleInfoW
0x18000cce9  test    eax, eax
0x18000cceb  jz      short loc_18000CD0E
0x18000cced  mov     r8d, 3; MaxCount
0x18000ccf3  lea     rdx, String2; String2
0x18000ccfa  lea     rcx, [rbp+3E0h+LCData]; String1
0x18000cd01  call    wcsncmp_0
0x18000cd06  test    eax, eax
0x18000cd08  jz      short loc_18000CD0E
0x18000cd0a  movzx   r14d, r15w
0x18000cd0e  lea     r9, [rbp+3E0h+var_3F0]
0x18000cd12  movzx   ecx, r14w
0x18000cd16  lea     r8, [rbp+3E0h+var_340]
0x18000cd1d  lea     rdx, [rsp+4E0h+var_4A0]
0x18000cd22  call    LookupLangID
0x18000cd27  test    eax, eax
0x18000cd29  jz      loc_18000CFF1
0x18000cd2f  mov     r9, [rsp+4E0h+FilePart]
0x18000cd34  lea     r8, [rsp+4E0h+var_4A0]
0x18000cd39  mov     rdx, rsi
0x18000cd3c  mov     rcx, rdi
0x18000cd3f  call    LoadMUIFile
0x18000cd44  mov     rbx, rax
0x18000cd47  test    rax, rax
0x18000cd4a  jnz     loc_18000CFFA
0x18000cd50  mov     r9, [rsp+4E0h+FilePart]
0x18000cd55  lea     r8, [rbp+3E0h+var_340]
0x18000cd5c  mov     rdx, rsi
0x18000cd5f  mov     rcx, rdi
0x18000cd62  call    LoadMUIFile
0x18000cd67  mov     rbx, rax
0x18000cd6a  test    rax, rax
0x18000cd6d  jnz     loc_18000CFFA
0x18000cd73  cmp     [rbp+3E0h+var_3F0], r13w
0x18000cd78  jz      short loc_18000CD9A
0x18000cd7a  mov     r9, [rsp+4E0h+FilePart]
0x18000cd7f  lea     r8, [rbp+3E0h+var_3F0]
0x18000cd83  mov     rdx, rsi
0x18000cd86  mov     rcx, rdi
0x18000cd89  call    LoadMUIFile
0x18000cd8e  mov     rbx, rax
0x18000cd91  test    rax, rax
0x18000cd94  jnz     loc_18000CFFA
0x18000cd9a  mov     eax, 0C04h
0x18000cd9f  cmp     r14w, ax
0x18000cda3  jz      loc_18000CD0A
0x18000cda9  call    cs:__imp_GetSystemDefaultUILanguage
0x18000cdaf  movzx   r15d, ax
0x18000cdb3  cmp     ax, r14w
0x18000cdb7  jz      loc_18000CE48
0x18000cdbd  lea     r9, [rbp+3E0h+var_3F0]
0x18000cdc1  movzx   ecx, ax
0x18000cdc4  lea     r8, [rbp+3E0h+var_340]
0x18000cdcb  lea     rdx, [rsp+4E0h+var_4A0]
0x18000cdd0  call    LookupLangID
0x18000cdd5  test    eax, eax
0x18000cdd7  jz      loc_18000CF5B
0x18000cddd  mov     r9, [rsp+4E0h+FilePart]
0x18000cde2  lea     r8, [rsp+4E0h+var_4A0]
0x18000cde7  mov     rdx, rsi
0x18000cdea  mov     rcx, rdi
0x18000cded  call    LoadMUIFile
0x18000cdf2  mov     rbx, rax
0x18000cdf5  test    rax, rax
0x18000cdf8  jnz     loc_18000CFFA
0x18000cdfe  mov     r9, [rsp+4E0h+FilePart]
0x18000ce03  lea     r8, [rbp+3E0h+var_340]
0x18000ce0a  mov     rdx, rsi
0x18000ce0d  mov     rcx, rdi
0x18000ce10  call    LoadMUIFile
0x18000ce15  mov     rbx, rax
0x18000ce18  test    rax, rax
0x18000ce1b  jnz     loc_18000CFFA
0x18000ce21  cmp     [rbp+3E0h+var_3F0], r13w
0x18000ce26  jz      short loc_18000CE48
0x18000ce28  mov     r9, [rsp+4E0h+FilePart]
0x18000ce2d  lea     r8, [rbp+3E0h+var_3F0]
0x18000ce31  mov     rdx, rsi
0x18000ce34  mov     rcx, rdi
0x18000ce37  call    LoadMUIFile
0x18000ce3c  mov     rbx, rax
0x18000ce3f  test    rax, rax
0x18000ce42  jnz     loc_18000CFFA
0x18000ce48  mov     ecx, 409h
0x18000ce4d  cmp     cx, r14w
0x18000ce51  jz      loc_18000CF3C
0x18000ce57  cmp     cx, r15w
0x18000ce5b  jmp     loc_18000CF05
0x18000ce60  test    al, 3
0x18000ce62  jz      loc_18000CF5B
0x18000ce68  call    GetInstallLanguage
0x18000ce6d  lea     r9, [rbp+3E0h+var_3F0]
0x18000ce71  movzx   ecx, ax
0x18000ce74  lea     r8, [rbp+3E0h+var_340]
0x18000ce7b  movzx   r14d, ax
0x18000ce7f  lea     rdx, [rsp+4E0h+var_4A0]
0x18000ce84  call    LookupLangID
0x18000ce89  test    eax, eax
0x18000ce8b  jz      loc_18000CF5B
0x18000ce91  mov     r9, [rsp+4E0h+FilePart]
0x18000ce96  lea     r8, [rsp+4E0h+var_4A0]
0x18000ce9b  mov     rdx, rsi
0x18000ce9e  mov     rcx, rdi
0x18000cea1  call    LoadMUIFile
0x18000cea6  mov     rbx, rax
0x18000cea9  test    rax, rax
0x18000ceac  jnz     loc_18000CFFA
0x18000ceb2  mov     r9, [rsp+4E0h+FilePart]
0x18000ceb7  lea     r8, [rbp+3E0h+var_340]
0x18000cebe  mov     rdx, rsi
0x18000cec1  mov     rcx, rdi
0x18000cec4  call    LoadMUIFile
0x18000cec9  mov     rbx, rax
0x18000cecc  test    rax, rax
0x18000cecf  jnz     loc_18000CFFA
0x18000ced5  cmp     [rbp+3E0h+var_3F0], r13w
0x18000ceda  jz      short loc_18000CEFC
0x18000cedc  mov     r9, [rsp+4E0h+FilePart]
0x18000cee1  lea     r8, [rbp+3E0h+var_3F0]
0x18000cee5  mov     rdx, rsi
0x18000cee8  mov     rcx, rdi
0x18000ceeb  call    LoadMUIFile
0x18000cef0  mov     rbx, rax
0x18000cef3  test    rax, rax
0x18000cef6  jnz     loc_18000CFFA
0x18000cefc  mov     ecx, 409h
0x18000cf01  cmp     cx, r14w
0x18000cf05  jz      short loc_18000CF3C
0x18000cf07  xor     r9d, r9d
0x18000cf0a  lea     r8, [rbp+3E0h+var_340]
0x18000cf11  lea     rdx, [rsp+4E0h+var_4A0]
0x18000cf16  call    LookupLangID
0x18000cf1b  mov     r9, [rsp+4E0h+FilePart]
0x18000cf20  lea     r8, [rsp+4E0h+var_4A0]
0x18000cf25  mov     rdx, rsi
0x18000cf28  mov     rcx, rdi
0x18000cf2b  call    LoadMUIFile
0x18000cf30  mov     rbx, rax
0x18000cf33  test    rax, rax
0x18000cf36  jnz     loc_18000CFFA
0x18000cf3c  mov     r9, [rsp+4E0h+FilePart]
0x18000cf41  xor     r8d, r8d
0x18000cf44  mov     rdx, rsi
0x18000cf47  mov     rcx, rdi
0x18000cf4a  call    LoadMUIFile
0x18000cf4f  mov     rbx, rax
0x18000cf52  test    rax, rax
0x18000cf55  jnz     loc_18000CFFA
0x18000cf5b  test    dil, 1
0x18000cf5f  jz      loc_18000D024
0x18000cf65  mov     rcx, rdi; hLibModule
0x18000cf68  call    cs:__imp_FreeLibrary
0x18000cf6e  call    GetOSType
0x18000cf73  test    al, 38h
0x18000cf75  jz      loc_18000D008
0x18000cf7b  mov     rax, [rsp+4E0h+FilePart]
0x18000cf80  lea     r8, aSS; "%s\\%s"
0x18000cf87  mov     r9, rsi
0x18000cf8a  mov     [rsp+4E0h+lpBuffer], rax
0x18000cf8f  mov     edx, 104h; unsigned __int64
0x18000cf94  lea     rcx, [rbp+3E0h+Buffer]; unsigned __int16 *
0x18000cf9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cfa0  xor     r8d, r8d
0x18000cfa3  lea     rcx, [rbp+3E0h+Buffer]
0x18000cfaa  lea     edx, [r8+1]
0x18000cfae  call    MapMUIFile
0x18000cfb3  jmp     short loc_18000D021
0x18000cfb5  test    byte ptr cs:dword_180014918, 7
0x18000cfbc  jz      short loc_18000CF5B
0x18000cfbe  xor     r9d, r9d
0x18000cfc1  lea     r8, [rbp+3E0h+var_340]
0x18000cfc8  lea     rdx, [rsp+4E0h+var_4A0]
0x18000cfcd  movzx   ecx, bx
0x18000cfd0  call    LookupLangID
0x18000cfd5  test    eax, eax
0x18000cfd7  jz      short loc_18000CF5B
0x18000cfd9  mov     r9, [rsp+4E0h+FilePart]
0x18000cfde  lea     r8, [rsp+4E0h+var_4A0]
0x18000cfe3  mov     rdx, rsi
0x18000cfe6  mov     rcx, rdi
0x18000cfe9  call    LoadMUIFile
0x18000cfee  mov     rbx, rax
0x18000cff1  test    rbx, rbx
0x18000cff4  jz      loc_18000CF5B
0x18000cffa  mov     rcx, rdi; hLibModule
0x18000cffd  call    cs:__imp_FreeLibrary
0x18000d003  mov     rax, rbx
0x18000d006  jmp     short loc_18000D034
0x18000d008  call    GetOSType
0x18000d00d  test    al, 26h
0x18000d00f  mov     r8d, r13d
0x18000d012  mov     rcx, r12; lpLibFileName
0x18000d015  setnz   r8b; dwFlags
0x18000d019  xor     edx, edx; hFile
0x18000d01b  call    cs:__imp_LoadLibraryExW
0x18000d021  mov     rdi, rax
0x18000d024  mov     rax, rdi
0x18000d027  jmp     short loc_18000D034
0x18000d029  mov     rcx, rdi; hLibModule
0x18000d02c  call    cs:__imp_FreeLibrary
0x18000d032  xor     eax, eax
0x18000d034  mov     rcx, [rbp+3E0h+var_40]
0x18000d03b  xor     rcx, rsp; StackCookie
0x18000d03e  call    __security_check_cookie
0x18000d043  mov     rbx, [rsp+4E0h+arg_8]
0x18000d04b  add     rsp, 4B0h
0x18000d052  pop     r15
0x18000d054  pop     r14
0x18000d056  pop     r13
0x18000d058  pop     r12
0x18000d05a  pop     rdi
0x18000d05b  pop     rsi
0x18000d05c  pop     rbp
0x18000d05d  retn
```
