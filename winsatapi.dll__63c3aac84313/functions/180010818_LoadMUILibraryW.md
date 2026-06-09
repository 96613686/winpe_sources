# LoadMUILibraryW

- ea: `0x180010818`
- end: `0x180010c87`
- name: `LoadMUILibraryW`
- size: `1135`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c150`

## callees

- `0x18001006c`
- `0x180010818`
- `0x180010c90`
- `0x18002d878`
- `0x18002d8f8`
- `0x18002da0c`
- `0x18002da80`
- `0x18002dbf4`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010868`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010c4d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010868`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010c4d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800108f5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800108f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010ae4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010c2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010c5e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010ae4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010c2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010c5e`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180010915`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180010915`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800109d3`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800109d3`
- `KERNEL32!SearchPathW` at `0x1800108af`
- `KERNEL32!SearchPathW` at `0x1800108af`

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
  dword_18004E6A8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(&FileName, 0, dword_18004E6A8 & 0x20 | 2u);
  v4 = result;
  if ( !result )
    return 0;
  if ( (dword_18004E6A8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, &FileName, 0, 0x104u, Buffer, &FilePart) )
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
    if ( (dword_18004E6A8 & 4) != 0 )
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
    else if ( (dword_18004E6A8 & 3) != 0 )
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
      return LoadLibraryExW(&FileName, 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180010818  push    rbp
0x18001081a  push    rbx
0x18001081b  push    rsi
0x18001081c  push    rdi
0x18001081d  push    r12
0x18001081f  push    r14
0x180010821  push    r15
0x180010823  lea     rbp, [rsp-370h]
0x18001082b  sub     rsp, 470h
0x180010832  mov     rax, cs:__security_cookie
0x180010839  xor     rax, rsp
0x18001083c  mov     [rbp+3A0h+var_40], rax
0x180010843  xor     r12d, r12d
0x180010846  mov     [rsp+4A0h+FilePart], r12
0x18001084b  call    GetOSType
0x180010850  mov     cs:dword_18004E6A8, eax
0x180010856  lea     rcx, FileName; lpLibFileName
0x18001085d  and     eax, 20h
0x180010860  xor     edx, edx; hFile
0x180010862  or      eax, 2
0x180010865  mov     r8d, eax; dwFlags
0x180010868  call    cs:__imp_LoadLibraryExW
0x18001086e  mov     rdi, rax
0x180010871  test    rax, rax
0x180010874  jz      loc_180010C64
0x18001087a  test    byte ptr cs:dword_18004E6A8, 20h
0x180010881  jnz     loc_180010C66
0x180010887  lea     rax, [rsp+4A0h+FilePart]
0x18001088c  mov     r9d, 104h; nBufferLength
0x180010892  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180010897  lea     rdx, FileName; lpFileName
0x18001089e  lea     rax, [rbp+3A0h+Buffer]
0x1800108a5  xor     r8d, r8d; lpExtension
0x1800108a8  xor     ecx, ecx; lpPath
0x1800108aa  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x1800108af  call    cs:__imp_SearchPathW
0x1800108b5  test    eax, eax
0x1800108b7  jz      loc_180010C5B
0x1800108bd  mov     rcx, [rsp+4A0h+FilePart]
0x1800108c2  test    rcx, rcx
0x1800108c5  jnz     short loc_1800108D8
0x1800108c7  lea     rax, [rbp+3A0h+Buffer]
0x1800108ce  mov     esi, r12d
0x1800108d1  mov     [rsp+4A0h+FilePart], rax
0x1800108d6  jmp     short loc_1800108E4
0x1800108d8  lea     rsi, [rbp+3A0h+Buffer]
0x1800108df  mov     [rcx-2], r12w
0x1800108e4  xor     r9d, r9d; wLanguage
0x1800108e7  lea     rdx, Type; "MUI"
0x1800108ee  mov     rcx, rdi; hModule
0x1800108f1  lea     r8d, [r9+1]; lpName
0x1800108f5  call    cs:__imp_FindResourceExW
0x1800108fb  test    rax, rax
0x1800108fe  jz      loc_180010AD7
0x180010904  mov     eax, cs:dword_18004E6A8
0x18001090a  test    al, 4
0x18001090c  jz      loc_180010B34
0x180010912  mov     rbx, r12
0x180010915  call    cs:__imp_GetUserDefaultUILanguage
0x18001091b  mov     r15d, 404h
0x180010921  movzx   r14d, ax
0x180010925  cmp     ax, r15w
0x180010929  jnz     short loc_180010934
0x18001092b  call    GetCHTLangauge
0x180010930  movzx   r14d, ax
0x180010934  lea     r9, [rbp+3A0h+var_3B0]
0x180010938  movzx   ecx, r14w
0x18001093c  lea     r8, [rbp+3A0h+var_300]
0x180010943  lea     rdx, [rsp+4A0h+var_460]
0x180010948  call    LookupLangID
0x18001094d  test    eax, eax
0x18001094f  jz      loc_180010C1F
0x180010955  mov     r9, [rsp+4A0h+FilePart]
0x18001095a  lea     r8, [rsp+4A0h+var_460]
0x18001095f  mov     rdx, rsi
0x180010962  mov     rcx, rdi
0x180010965  call    LoadMUIFile
0x18001096a  mov     rbx, rax
0x18001096d  test    rax, rax
0x180010970  jnz     loc_180010C28
0x180010976  mov     r9, [rsp+4A0h+FilePart]
0x18001097b  lea     r8, [rbp+3A0h+var_300]
0x180010982  mov     rdx, rsi
0x180010985  mov     rcx, rdi
0x180010988  call    LoadMUIFile
0x18001098d  mov     rbx, rax
0x180010990  test    rax, rax
0x180010993  jnz     loc_180010C28
0x180010999  cmp     [rbp+3A0h+var_3B0], r12w
0x18001099e  jz      short loc_1800109C0
0x1800109a0  mov     r9, [rsp+4A0h+FilePart]
0x1800109a5  lea     r8, [rbp+3A0h+var_3B0]
0x1800109a9  mov     rdx, rsi
0x1800109ac  mov     rcx, rdi
0x1800109af  call    LoadMUIFile
0x1800109b4  mov     rbx, rax
0x1800109b7  test    rax, rax
0x1800109ba  jnz     loc_180010C28
0x1800109c0  mov     eax, 0C04h
0x1800109c5  cmp     r14w, ax
0x1800109c9  jnz     short loc_1800109D3
0x1800109cb  mov     r14d, r15d
0x1800109ce  jmp     loc_180010934
0x1800109d3  call    cs:__imp_GetSystemDefaultUILanguage
0x1800109d9  movzx   r15d, ax
0x1800109dd  cmp     ax, r14w
0x1800109e1  jz      loc_180010A72
0x1800109e7  lea     r9, [rbp+3A0h+var_3B0]
0x1800109eb  movzx   ecx, ax
0x1800109ee  lea     r8, [rbp+3A0h+var_300]
0x1800109f5  lea     rdx, [rsp+4A0h+var_460]
0x1800109fa  call    LookupLangID
0x1800109ff  test    eax, eax
0x180010a01  jz      loc_180010AD7
0x180010a07  mov     r9, [rsp+4A0h+FilePart]
0x180010a0c  lea     r8, [rsp+4A0h+var_460]
0x180010a11  mov     rdx, rsi
0x180010a14  mov     rcx, rdi
0x180010a17  call    LoadMUIFile
0x180010a1c  mov     rbx, rax
0x180010a1f  test    rax, rax
0x180010a22  jnz     loc_180010C28
0x180010a28  mov     r9, [rsp+4A0h+FilePart]
0x180010a2d  lea     r8, [rbp+3A0h+var_300]
0x180010a34  mov     rdx, rsi
0x180010a37  mov     rcx, rdi
0x180010a3a  call    LoadMUIFile
0x180010a3f  mov     rbx, rax
0x180010a42  test    rax, rax
0x180010a45  jnz     loc_180010C28
0x180010a4b  cmp     [rbp+3A0h+var_3B0], r12w
0x180010a50  jz      short loc_180010A72
0x180010a52  mov     r9, [rsp+4A0h+FilePart]
0x180010a57  lea     r8, [rbp+3A0h+var_3B0]
0x180010a5b  mov     rdx, rsi
0x180010a5e  mov     rcx, rdi
0x180010a61  call    LoadMUIFile
0x180010a66  mov     rbx, rax
0x180010a69  test    rax, rax
0x180010a6c  jnz     loc_180010C28
0x180010a72  mov     ecx, 409h
0x180010a77  cmp     cx, r14w
0x180010a7b  jz      short loc_180010AB8
0x180010a7d  cmp     cx, r15w
0x180010a81  jz      short loc_180010AB8
0x180010a83  xor     r9d, r9d
0x180010a86  lea     r8, [rbp+3A0h+var_300]
0x180010a8d  lea     rdx, [rsp+4A0h+var_460]
0x180010a92  call    LookupLangID
0x180010a97  mov     r9, [rsp+4A0h+FilePart]
0x180010a9c  lea     r8, [rsp+4A0h+var_460]
0x180010aa1  mov     rdx, rsi
0x180010aa4  mov     rcx, rdi
0x180010aa7  call    LoadMUIFile
0x180010aac  mov     rbx, rax
0x180010aaf  test    rax, rax
0x180010ab2  jnz     loc_180010C28
0x180010ab8  mov     r9, [rsp+4A0h+FilePart]
0x180010abd  xor     r8d, r8d
0x180010ac0  mov     rdx, rsi
0x180010ac3  mov     rcx, rdi
0x180010ac6  call    LoadMUIFile
0x180010acb  mov     rbx, rax
0x180010ace  test    rax, rax
0x180010ad1  jnz     loc_180010C28
0x180010ad7  test    dil, 1
0x180010adb  jz      loc_180010C56
0x180010ae1  mov     rcx, rdi; hLibModule
0x180010ae4  call    cs:__imp_FreeLibrary
0x180010aea  call    GetOSType
0x180010aef  test    al, 38h
0x180010af1  jz      loc_180010C36
0x180010af7  mov     rax, [rsp+4A0h+FilePart]
0x180010afc  lea     r8, aSS; "%s\\%s"
0x180010b03  mov     r9, rsi
0x180010b06  mov     [rsp+4A0h+lpBuffer], rax
0x180010b0b  mov     edx, 104h; unsigned __int64
0x180010b10  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180010b17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010b1c  xor     r8d, r8d
0x180010b1f  lea     rcx, [rbp+3A0h+Buffer]
0x180010b26  lea     edx, [r8+1]
0x180010b2a  call    MapMUIFile
0x180010b2f  jmp     loc_180010C53
0x180010b34  test    al, 3
0x180010b36  jz      short loc_180010AD7
0x180010b38  call    GetInstallLanguage
0x180010b3d  lea     r9, [rbp+3A0h+var_3B0]
0x180010b41  movzx   ecx, ax
0x180010b44  lea     r8, [rbp+3A0h+var_300]
0x180010b4b  movzx   r14d, ax
0x180010b4f  lea     rdx, [rsp+4A0h+var_460]
0x180010b54  call    LookupLangID
0x180010b59  test    eax, eax
0x180010b5b  jz      loc_180010AD7
0x180010b61  mov     r9, [rsp+4A0h+FilePart]
0x180010b66  lea     r8, [rsp+4A0h+var_460]
0x180010b6b  mov     rdx, rsi
0x180010b6e  mov     rcx, rdi
0x180010b71  call    LoadMUIFile
0x180010b76  mov     rbx, rax
0x180010b79  test    rax, rax
0x180010b7c  jnz     loc_180010C28
0x180010b82  mov     r9, [rsp+4A0h+FilePart]
0x180010b87  lea     r8, [rbp+3A0h+var_300]
0x180010b8e  mov     rdx, rsi
0x180010b91  mov     rcx, rdi
0x180010b94  call    LoadMUIFile
0x180010b99  mov     rbx, rax
0x180010b9c  test    rax, rax
0x180010b9f  jnz     loc_180010C28
0x180010ba5  cmp     [rbp+3A0h+var_3B0], r12w
0x180010baa  jz      short loc_180010BC8
0x180010bac  mov     r9, [rsp+4A0h+FilePart]
0x180010bb1  lea     r8, [rbp+3A0h+var_3B0]
0x180010bb5  mov     rdx, rsi
0x180010bb8  mov     rcx, rdi
0x180010bbb  call    LoadMUIFile
0x180010bc0  mov     rbx, rax
0x180010bc3  test    rax, rax
0x180010bc6  jnz     short loc_180010C28
0x180010bc8  mov     ecx, 409h
0x180010bcd  cmp     cx, r14w
0x180010bd1  jz      short loc_180010C04
0x180010bd3  xor     r9d, r9d
0x180010bd6  lea     r8, [rbp+3A0h+var_300]
0x180010bdd  lea     rdx, [rsp+4A0h+var_460]
0x180010be2  call    LookupLangID
0x180010be7  mov     r9, [rsp+4A0h+FilePart]
0x180010bec  lea     r8, [rsp+4A0h+var_460]
0x180010bf1  mov     rdx, rsi
0x180010bf4  mov     rcx, rdi
0x180010bf7  call    LoadMUIFile
0x180010bfc  mov     rbx, rax
0x180010bff  test    rax, rax
0x180010c02  jnz     short loc_180010C28
0x180010c04  mov     r9, [rsp+4A0h+FilePart]
0x180010c09  xor     r8d, r8d
0x180010c0c  mov     rdx, rsi
0x180010c0f  mov     rcx, rdi
0x180010c12  call    LoadMUIFile
0x180010c17  mov     rbx, rax
0x180010c1a  test    rax, rax
0x180010c1d  jnz     short loc_180010C28
0x180010c1f  test    rbx, rbx
0x180010c22  jz      loc_180010AD7
0x180010c28  mov     rcx, rdi; hLibModule
0x180010c2b  call    cs:__imp_FreeLibrary
0x180010c31  mov     rax, rbx
0x180010c34  jmp     short loc_180010C66
0x180010c36  call    GetOSType
0x180010c3b  test    al, 26h
0x180010c3d  lea     rcx, FileName; lpLibFileName
0x180010c44  mov     r8d, r12d
0x180010c47  setnz   r8b; dwFlags
0x180010c4b  xor     edx, edx; hFile
0x180010c4d  call    cs:__imp_LoadLibraryExW
0x180010c53  mov     rdi, rax
0x180010c56  mov     rax, rdi
0x180010c59  jmp     short loc_180010C66
0x180010c5b  mov     rcx, rdi; hLibModule
0x180010c5e  call    cs:__imp_FreeLibrary
0x180010c64  xor     eax, eax
0x180010c66  mov     rcx, [rbp+3A0h+var_40]
0x180010c6d  xor     rcx, rsp; StackCookie
0x180010c70  call    __security_check_cookie
0x180010c75  add     rsp, 470h
0x180010c7c  pop     r15
0x180010c7e  pop     r14
0x180010c80  pop     r12
0x180010c82  pop     rdi
0x180010c83  pop     rsi
0x180010c84  pop     rbx
0x180010c85  pop     rbp
0x180010c86  retn
```
