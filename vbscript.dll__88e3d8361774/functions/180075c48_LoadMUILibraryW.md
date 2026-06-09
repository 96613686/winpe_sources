# LoadMUILibraryW

- ea: `0x180075c48`
- end: `0x1800760ce`
- name: `LoadMUILibraryW`
- size: `1158`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800580a8`

## callees

- `0x180030230`
- `0x180075564`
- `0x1800755e4`
- `0x1800756f4`
- `0x18007581c`
- `0x180075890`
- `0x180075a04`
- `0x180075c48`
- `0x1800767a0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x180075d32`
- `KERNEL32!FindResourceExW` at `0x180075d32`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180075d5b`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180075d5b`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180075e19`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180075e19`
- `KERNEL32!SearchPathW` at `0x180075cec`
- `KERNEL32!SearchPathW` at `0x180075cec`
- `KERNEL32!LoadLibraryExW` at `0x180075ca9`
- `KERNEL32!LoadLibraryExW` at `0x18007608b`
- `KERNEL32!LoadLibraryExW` at `0x180075ca9`
- `KERNEL32!LoadLibraryExW` at `0x18007608b`
- `KERNEL32!FreeLibrary` at `0x180075fd8`
- `KERNEL32!FreeLibrary` at `0x18007606d`
- `KERNEL32!FreeLibrary` at `0x18007609c`
- `KERNEL32!FreeLibrary` at `0x180075fd8`
- `KERNEL32!FreeLibrary` at `0x18007606d`
- `KERNEL32!FreeLibrary` at `0x18007609c`

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
  dword_1800908C0 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800908C0 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_1800908C0 & 0x20) != 0 )
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
      if ( (dword_1800908C0 & 4) == 0 )
      {
        if ( (dword_1800908C0 & 3) != 0 )
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
    if ( (dword_1800908C0 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
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
0x180075c48  mov     [rsp-8+arg_8], rbx
0x180075c4d  push    rbp
0x180075c4e  push    rsi
0x180075c4f  push    rdi
0x180075c50  push    r12
0x180075c52  push    r13
0x180075c54  push    r14
0x180075c56  push    r15
0x180075c58  lea     rbp, [rsp-370h]
0x180075c60  sub     rsp, 470h
0x180075c67  mov     rax, cs:__security_cookie
0x180075c6e  xor     rax, rsp
0x180075c71  mov     [rbp+3A0h+var_40], rax
0x180075c78  xor     r13d, r13d
0x180075c7b  movzx   ebx, r8w
0x180075c7f  mov     [rsp+4A0h+FilePart], r13
0x180075c84  mov     r12, rcx
0x180075c87  test    rcx, rcx
0x180075c8a  jz      loc_1800760A2
0x180075c90  call    GetOSType
0x180075c95  mov     cs:dword_1800908C0, eax
0x180075c9b  xor     edx, edx; hFile
0x180075c9d  and     eax, 20h
0x180075ca0  mov     rcx, r12; lpLibFileName
0x180075ca3  or      eax, 2
0x180075ca6  mov     r8d, eax; dwFlags
0x180075ca9  call    cs:__imp_LoadLibraryExW
0x180075caf  mov     rdi, rax
0x180075cb2  test    rax, rax
0x180075cb5  jz      loc_1800760A2
0x180075cbb  test    byte ptr cs:dword_1800908C0, 20h
0x180075cc2  jnz     loc_1800760A4
0x180075cc8  lea     rax, [rsp+4A0h+FilePart]
0x180075ccd  mov     r9d, 104h; nBufferLength
0x180075cd3  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180075cd8  xor     r8d, r8d; lpExtension
0x180075cdb  lea     rax, [rbp+3A0h+Buffer]
0x180075ce2  mov     rdx, r12; lpFileName
0x180075ce5  xor     ecx, ecx; lpPath
0x180075ce7  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180075cec  call    cs:__imp_SearchPathW
0x180075cf2  test    eax, eax
0x180075cf4  jz      loc_180076099
0x180075cfa  mov     rcx, [rsp+4A0h+FilePart]
0x180075cff  test    rcx, rcx
0x180075d02  jnz     short loc_180075D15
0x180075d04  lea     rax, [rbp+3A0h+Buffer]
0x180075d0b  mov     esi, r13d
0x180075d0e  mov     [rsp+4A0h+FilePart], rax
0x180075d13  jmp     short loc_180075D21
0x180075d15  lea     rsi, [rbp+3A0h+Buffer]
0x180075d1c  mov     [rcx-2], r13w
0x180075d21  xor     r9d, r9d; wLanguage
0x180075d24  lea     rdx, Type; "MUI"
0x180075d2b  mov     rcx, rdi; hModule
0x180075d2e  lea     r8d, [r9+1]; lpName
0x180075d32  call    cs:__imp_FindResourceExW
0x180075d38  test    rax, rax
0x180075d3b  jz      loc_180075FCB
0x180075d41  test    bx, bx
0x180075d44  jnz     loc_180076025
0x180075d4a  mov     eax, cs:dword_1800908C0
0x180075d50  test    al, 4
0x180075d52  jz      loc_180075ED0
0x180075d58  mov     rbx, r13
0x180075d5b  call    cs:__imp_GetUserDefaultUILanguage
0x180075d61  mov     r15d, 404h
0x180075d67  movzx   r14d, ax
0x180075d6b  cmp     ax, r15w
0x180075d6f  jnz     short loc_180075D7A
0x180075d71  call    GetCHTLangauge
0x180075d76  movzx   r14d, ax
0x180075d7a  lea     r9, [rbp+3A0h+var_3B0]
0x180075d7e  movzx   ecx, r14w
0x180075d82  lea     r8, [rbp+3A0h+var_300]
0x180075d89  lea     rdx, [rsp+4A0h+var_460]
0x180075d8e  call    LookupLangID
0x180075d93  test    eax, eax
0x180075d95  jz      loc_180076061
0x180075d9b  mov     r9, [rsp+4A0h+FilePart]
0x180075da0  lea     r8, [rsp+4A0h+var_460]
0x180075da5  mov     rdx, rsi
0x180075da8  mov     rcx, rdi
0x180075dab  call    LoadMUIFile
0x180075db0  mov     rbx, rax
0x180075db3  test    rax, rax
0x180075db6  jnz     loc_18007606A
0x180075dbc  mov     r9, [rsp+4A0h+FilePart]
0x180075dc1  lea     r8, [rbp+3A0h+var_300]
0x180075dc8  mov     rdx, rsi
0x180075dcb  mov     rcx, rdi
0x180075dce  call    LoadMUIFile
0x180075dd3  mov     rbx, rax
0x180075dd6  test    rax, rax
0x180075dd9  jnz     loc_18007606A
0x180075ddf  cmp     [rbp+3A0h+var_3B0], r13w
0x180075de4  jz      short loc_180075E06
0x180075de6  mov     r9, [rsp+4A0h+FilePart]
0x180075deb  lea     r8, [rbp+3A0h+var_3B0]
0x180075def  mov     rdx, rsi
0x180075df2  mov     rcx, rdi
0x180075df5  call    LoadMUIFile
0x180075dfa  mov     rbx, rax
0x180075dfd  test    rax, rax
0x180075e00  jnz     loc_18007606A
0x180075e06  mov     eax, 0C04h
0x180075e0b  cmp     r14w, ax
0x180075e0f  jnz     short loc_180075E19
0x180075e11  mov     r14d, r15d
0x180075e14  jmp     loc_180075D7A
0x180075e19  call    cs:__imp_GetSystemDefaultUILanguage
0x180075e1f  movzx   r15d, ax
0x180075e23  cmp     ax, r14w
0x180075e27  jz      loc_180075EB8
0x180075e2d  lea     r9, [rbp+3A0h+var_3B0]
0x180075e31  movzx   ecx, ax
0x180075e34  lea     r8, [rbp+3A0h+var_300]
0x180075e3b  lea     rdx, [rsp+4A0h+var_460]
0x180075e40  call    LookupLangID
0x180075e45  test    eax, eax
0x180075e47  jz      loc_180075FCB
0x180075e4d  mov     r9, [rsp+4A0h+FilePart]
0x180075e52  lea     r8, [rsp+4A0h+var_460]
0x180075e57  mov     rdx, rsi
0x180075e5a  mov     rcx, rdi
0x180075e5d  call    LoadMUIFile
0x180075e62  mov     rbx, rax
0x180075e65  test    rax, rax
0x180075e68  jnz     loc_18007606A
0x180075e6e  mov     r9, [rsp+4A0h+FilePart]
0x180075e73  lea     r8, [rbp+3A0h+var_300]
0x180075e7a  mov     rdx, rsi
0x180075e7d  mov     rcx, rdi
0x180075e80  call    LoadMUIFile
0x180075e85  mov     rbx, rax
0x180075e88  test    rax, rax
0x180075e8b  jnz     loc_18007606A
0x180075e91  cmp     [rbp+3A0h+var_3B0], r13w
0x180075e96  jz      short loc_180075EB8
0x180075e98  mov     r9, [rsp+4A0h+FilePart]
0x180075e9d  lea     r8, [rbp+3A0h+var_3B0]
0x180075ea1  mov     rdx, rsi
0x180075ea4  mov     rcx, rdi
0x180075ea7  call    LoadMUIFile
0x180075eac  mov     rbx, rax
0x180075eaf  test    rax, rax
0x180075eb2  jnz     loc_18007606A
0x180075eb8  mov     ecx, 409h
0x180075ebd  cmp     cx, r14w
0x180075ec1  jz      loc_180075FAC
0x180075ec7  cmp     cx, r15w
0x180075ecb  jmp     loc_180075F75
0x180075ed0  test    al, 3
0x180075ed2  jz      loc_180075FCB
0x180075ed8  call    GetInstallLanguage
0x180075edd  lea     r9, [rbp+3A0h+var_3B0]
0x180075ee1  movzx   ecx, ax
0x180075ee4  lea     r8, [rbp+3A0h+var_300]
0x180075eeb  movzx   r14d, ax
0x180075eef  lea     rdx, [rsp+4A0h+var_460]
0x180075ef4  call    LookupLangID
0x180075ef9  test    eax, eax
0x180075efb  jz      loc_180075FCB
0x180075f01  mov     r9, [rsp+4A0h+FilePart]
0x180075f06  lea     r8, [rsp+4A0h+var_460]
0x180075f0b  mov     rdx, rsi
0x180075f0e  mov     rcx, rdi
0x180075f11  call    LoadMUIFile
0x180075f16  mov     rbx, rax
0x180075f19  test    rax, rax
0x180075f1c  jnz     loc_18007606A
0x180075f22  mov     r9, [rsp+4A0h+FilePart]
0x180075f27  lea     r8, [rbp+3A0h+var_300]
0x180075f2e  mov     rdx, rsi
0x180075f31  mov     rcx, rdi
0x180075f34  call    LoadMUIFile
0x180075f39  mov     rbx, rax
0x180075f3c  test    rax, rax
0x180075f3f  jnz     loc_18007606A
0x180075f45  cmp     [rbp+3A0h+var_3B0], r13w
0x180075f4a  jz      short loc_180075F6C
0x180075f4c  mov     r9, [rsp+4A0h+FilePart]
0x180075f51  lea     r8, [rbp+3A0h+var_3B0]
0x180075f55  mov     rdx, rsi
0x180075f58  mov     rcx, rdi
0x180075f5b  call    LoadMUIFile
0x180075f60  mov     rbx, rax
0x180075f63  test    rax, rax
0x180075f66  jnz     loc_18007606A
0x180075f6c  mov     ecx, 409h
0x180075f71  cmp     cx, r14w
0x180075f75  jz      short loc_180075FAC
0x180075f77  xor     r9d, r9d
0x180075f7a  lea     r8, [rbp+3A0h+var_300]
0x180075f81  lea     rdx, [rsp+4A0h+var_460]
0x180075f86  call    LookupLangID
0x180075f8b  mov     r9, [rsp+4A0h+FilePart]
0x180075f90  lea     r8, [rsp+4A0h+var_460]
0x180075f95  mov     rdx, rsi
0x180075f98  mov     rcx, rdi
0x180075f9b  call    LoadMUIFile
0x180075fa0  mov     rbx, rax
0x180075fa3  test    rax, rax
0x180075fa6  jnz     loc_18007606A
0x180075fac  mov     r9, [rsp+4A0h+FilePart]
0x180075fb1  xor     r8d, r8d
0x180075fb4  mov     rdx, rsi
0x180075fb7  mov     rcx, rdi
0x180075fba  call    LoadMUIFile
0x180075fbf  mov     rbx, rax
0x180075fc2  test    rax, rax
0x180075fc5  jnz     loc_18007606A
0x180075fcb  test    dil, 1
0x180075fcf  jz      loc_180076094
0x180075fd5  mov     rcx, rdi; hLibModule
0x180075fd8  call    cs:__imp_FreeLibrary
0x180075fde  call    GetOSType
0x180075fe3  test    al, 38h
0x180075fe5  jz      loc_180076078
0x180075feb  mov     rax, [rsp+4A0h+FilePart]
0x180075ff0  lea     r8, aSS; "%s\\%s"
0x180075ff7  mov     r9, rsi
0x180075ffa  mov     [rsp+4A0h+lpBuffer], rax
0x180075fff  mov     edx, 104h; unsigned __int64
0x180076004  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x18007600b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076010  xor     r8d, r8d
0x180076013  lea     rcx, [rbp+3A0h+Buffer]
0x18007601a  lea     edx, [r8+1]
0x18007601e  call    MapMUIFile
0x180076023  jmp     short loc_180076091
0x180076025  test    byte ptr cs:dword_1800908C0, 7
0x18007602c  jz      short loc_180075FCB
0x18007602e  xor     r9d, r9d
0x180076031  lea     r8, [rbp+3A0h+var_300]
0x180076038  lea     rdx, [rsp+4A0h+var_460]
0x18007603d  movzx   ecx, bx
0x180076040  call    LookupLangID
0x180076045  test    eax, eax
0x180076047  jz      short loc_180075FCB
0x180076049  mov     r9, [rsp+4A0h+FilePart]
0x18007604e  lea     r8, [rsp+4A0h+var_460]
0x180076053  mov     rdx, rsi
0x180076056  mov     rcx, rdi
0x180076059  call    LoadMUIFile
0x18007605e  mov     rbx, rax
0x180076061  test    rbx, rbx
0x180076064  jz      loc_180075FCB
0x18007606a  mov     rcx, rdi; hLibModule
0x18007606d  call    cs:__imp_FreeLibrary
0x180076073  mov     rax, rbx
0x180076076  jmp     short loc_1800760A4
0x180076078  call    GetOSType
0x18007607d  test    al, 26h
0x18007607f  mov     r8d, r13d
0x180076082  mov     rcx, r12; lpLibFileName
0x180076085  setnz   r8b; dwFlags
0x180076089  xor     edx, edx; hFile
0x18007608b  call    cs:__imp_LoadLibraryExW
0x180076091  mov     rdi, rax
0x180076094  mov     rax, rdi
0x180076097  jmp     short loc_1800760A4
0x180076099  mov     rcx, rdi; hLibModule
0x18007609c  call    cs:__imp_FreeLibrary
0x1800760a2  xor     eax, eax
0x1800760a4  mov     rcx, [rbp+3A0h+var_40]
0x1800760ab  xor     rcx, rsp; StackCookie
0x1800760ae  call    __security_check_cookie
0x1800760b3  mov     rbx, [rsp+4A0h+arg_8]
0x1800760bb  add     rsp, 470h
0x1800760c2  pop     r15
0x1800760c4  pop     r14
0x1800760c6  pop     r13
0x1800760c8  pop     r12
0x1800760ca  pop     rdi
0x1800760cb  pop     rsi
0x1800760cc  pop     rbp
0x1800760cd  retn
```
