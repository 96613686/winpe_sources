# LoadMUILibraryW

- ea: `0x1800788a0`
- end: `0x180078d61`
- name: `LoadMUILibraryW`
- size: `1217`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180059b80`

## callees

- `0x180034f88`
- `0x180078138`
- `0x1800781c0`
- `0x1800782e8`
- `0x18007841c`
- `0x180078490`
- `0x180078618`
- `0x1800788a0`
- `0x180079490`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x180078996`
- `KERNEL32!FindResourceExW` at `0x180078996`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800789c5`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800789c5`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180078a89`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180078a89`
- `KERNEL32!SearchPathW` at `0x18007894a`
- `KERNEL32!SearchPathW` at `0x18007894a`
- `KERNEL32!LoadLibraryExW` at `0x180078901`
- `KERNEL32!LoadLibraryExW` at `0x180078d11`
- `KERNEL32!LoadLibraryExW` at `0x180078901`
- `KERNEL32!LoadLibraryExW` at `0x180078d11`
- `KERNEL32!FreeLibrary` at `0x180078c4e`
- `KERNEL32!FreeLibrary` at `0x180078ced`
- `KERNEL32!FreeLibrary` at `0x180078d28`
- `KERNEL32!FreeLibrary` at `0x180078c4e`
- `KERNEL32!FreeLibrary` at `0x180078ced`
- `KERNEL32!FreeLibrary` at `0x180078d28`

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
  dword_1800938C0 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800938C0 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_1800938C0 & 0x20) != 0 )
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
      if ( (dword_1800938C0 & 4) == 0 )
      {
        if ( (dword_1800938C0 & 3) != 0 )
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
    if ( (dword_1800938C0 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
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
0x1800788a0  mov     [rsp-8+arg_8], rbx
0x1800788a5  push    rbp
0x1800788a6  push    rsi
0x1800788a7  push    rdi
0x1800788a8  push    r12
0x1800788aa  push    r13
0x1800788ac  push    r14
0x1800788ae  push    r15
0x1800788b0  lea     rbp, [rsp-370h]
0x1800788b8  sub     rsp, 470h
0x1800788bf  mov     rax, cs:__security_cookie
0x1800788c6  xor     rax, rsp
0x1800788c9  mov     [rbp+3A0h+var_40], rax
0x1800788d0  xor     r13d, r13d
0x1800788d3  movzx   ebx, r8w
0x1800788d7  mov     [rsp+4A0h+FilePart], r13
0x1800788dc  mov     r12, rcx
0x1800788df  test    rcx, rcx
0x1800788e2  jz      loc_180078D34
0x1800788e8  call    GetOSType
0x1800788ed  mov     cs:dword_1800938C0, eax
0x1800788f3  xor     edx, edx; hFile
0x1800788f5  and     eax, 20h
0x1800788f8  mov     rcx, r12; lpLibFileName
0x1800788fb  or      eax, 2
0x1800788fe  mov     r8d, eax; dwFlags
0x180078901  call    cs:__imp_LoadLibraryExW
0x180078908  nop     dword ptr [rax+rax+00h]
0x18007890d  mov     rdi, rax
0x180078910  test    rax, rax
0x180078913  jz      loc_180078D34
0x180078919  test    byte ptr cs:dword_1800938C0, 20h
0x180078920  jnz     loc_180078D36
0x180078926  lea     rax, [rsp+4A0h+FilePart]
0x18007892b  mov     r9d, 104h; nBufferLength
0x180078931  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180078936  xor     r8d, r8d; lpExtension
0x180078939  lea     rax, [rbp+3A0h+Buffer]
0x180078940  mov     rdx, r12; lpFileName
0x180078943  xor     ecx, ecx; lpPath
0x180078945  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x18007894a  call    cs:__imp_SearchPathW
0x180078951  nop     dword ptr [rax+rax+00h]
0x180078956  test    eax, eax
0x180078958  jz      loc_180078D25
0x18007895e  mov     rcx, [rsp+4A0h+FilePart]
0x180078963  test    rcx, rcx
0x180078966  jnz     short loc_180078979
0x180078968  lea     rax, [rbp+3A0h+Buffer]
0x18007896f  mov     esi, r13d
0x180078972  mov     [rsp+4A0h+FilePart], rax
0x180078977  jmp     short loc_180078985
0x180078979  lea     rsi, [rbp+3A0h+Buffer]
0x180078980  mov     [rcx-2], r13w
0x180078985  xor     r9d, r9d; wLanguage
0x180078988  lea     rdx, Type; "MUI"
0x18007898f  mov     rcx, rdi; hModule
0x180078992  lea     r8d, [r9+1]; lpName
0x180078996  call    cs:__imp_FindResourceExW
0x18007899d  nop     dword ptr [rax+rax+00h]
0x1800789a2  test    rax, rax
0x1800789a5  jz      loc_180078C41
0x1800789ab  test    bx, bx
0x1800789ae  jnz     loc_180078CA1
0x1800789b4  mov     eax, cs:dword_1800938C0
0x1800789ba  test    al, 4
0x1800789bc  jz      loc_180078B46
0x1800789c2  mov     rbx, r13
0x1800789c5  call    cs:__imp_GetUserDefaultUILanguage
0x1800789cc  nop     dword ptr [rax+rax+00h]
0x1800789d1  mov     r15d, 404h
0x1800789d7  movzx   r14d, ax
0x1800789db  cmp     ax, r15w
0x1800789df  jnz     short loc_1800789EA
0x1800789e1  call    GetCHTLangauge
0x1800789e6  movzx   r14d, ax
0x1800789ea  lea     r9, [rbp+3A0h+var_3B0]
0x1800789ee  movzx   ecx, r14w
0x1800789f2  lea     r8, [rbp+3A0h+var_300]
0x1800789f9  lea     rdx, [rsp+4A0h+var_460]
0x1800789fe  call    LookupLangID
0x180078a03  test    eax, eax
0x180078a05  jz      loc_180078CE1
0x180078a0b  mov     r9, [rsp+4A0h+FilePart]
0x180078a10  lea     r8, [rsp+4A0h+var_460]
0x180078a15  mov     rdx, rsi
0x180078a18  mov     rcx, rdi
0x180078a1b  call    LoadMUIFile
0x180078a20  mov     rbx, rax
0x180078a23  test    rax, rax
0x180078a26  jnz     loc_180078CEA
0x180078a2c  mov     r9, [rsp+4A0h+FilePart]
0x180078a31  lea     r8, [rbp+3A0h+var_300]
0x180078a38  mov     rdx, rsi
0x180078a3b  mov     rcx, rdi
0x180078a3e  call    LoadMUIFile
0x180078a43  mov     rbx, rax
0x180078a46  test    rax, rax
0x180078a49  jnz     loc_180078CEA
0x180078a4f  cmp     [rbp+3A0h+var_3B0], r13w
0x180078a54  jz      short loc_180078A76
0x180078a56  mov     r9, [rsp+4A0h+FilePart]
0x180078a5b  lea     r8, [rbp+3A0h+var_3B0]
0x180078a5f  mov     rdx, rsi
0x180078a62  mov     rcx, rdi
0x180078a65  call    LoadMUIFile
0x180078a6a  mov     rbx, rax
0x180078a6d  test    rax, rax
0x180078a70  jnz     loc_180078CEA
0x180078a76  mov     eax, 0C04h
0x180078a7b  cmp     r14w, ax
0x180078a7f  jnz     short loc_180078A89
0x180078a81  mov     r14d, r15d
0x180078a84  jmp     loc_1800789EA
0x180078a89  call    cs:__imp_GetSystemDefaultUILanguage
0x180078a90  nop     dword ptr [rax+rax+00h]
0x180078a95  movzx   r15d, ax
0x180078a99  cmp     ax, r14w
0x180078a9d  jz      loc_180078B2E
0x180078aa3  lea     r9, [rbp+3A0h+var_3B0]
0x180078aa7  movzx   ecx, ax
0x180078aaa  lea     r8, [rbp+3A0h+var_300]
0x180078ab1  lea     rdx, [rsp+4A0h+var_460]
0x180078ab6  call    LookupLangID
0x180078abb  test    eax, eax
0x180078abd  jz      loc_180078C41
0x180078ac3  mov     r9, [rsp+4A0h+FilePart]
0x180078ac8  lea     r8, [rsp+4A0h+var_460]
0x180078acd  mov     rdx, rsi
0x180078ad0  mov     rcx, rdi
0x180078ad3  call    LoadMUIFile
0x180078ad8  mov     rbx, rax
0x180078adb  test    rax, rax
0x180078ade  jnz     loc_180078CEA
0x180078ae4  mov     r9, [rsp+4A0h+FilePart]
0x180078ae9  lea     r8, [rbp+3A0h+var_300]
0x180078af0  mov     rdx, rsi
0x180078af3  mov     rcx, rdi
0x180078af6  call    LoadMUIFile
0x180078afb  mov     rbx, rax
0x180078afe  test    rax, rax
0x180078b01  jnz     loc_180078CEA
0x180078b07  cmp     [rbp+3A0h+var_3B0], r13w
0x180078b0c  jz      short loc_180078B2E
0x180078b0e  mov     r9, [rsp+4A0h+FilePart]
0x180078b13  lea     r8, [rbp+3A0h+var_3B0]
0x180078b17  mov     rdx, rsi
0x180078b1a  mov     rcx, rdi
0x180078b1d  call    LoadMUIFile
0x180078b22  mov     rbx, rax
0x180078b25  test    rax, rax
0x180078b28  jnz     loc_180078CEA
0x180078b2e  mov     ecx, 409h
0x180078b33  cmp     cx, r14w
0x180078b37  jz      loc_180078C22
0x180078b3d  cmp     cx, r15w
0x180078b41  jmp     loc_180078BEB
0x180078b46  test    al, 3
0x180078b48  jz      loc_180078C41
0x180078b4e  call    GetInstallLanguage
0x180078b53  lea     r9, [rbp+3A0h+var_3B0]
0x180078b57  movzx   ecx, ax
0x180078b5a  lea     r8, [rbp+3A0h+var_300]
0x180078b61  movzx   r14d, ax
0x180078b65  lea     rdx, [rsp+4A0h+var_460]
0x180078b6a  call    LookupLangID
0x180078b6f  test    eax, eax
0x180078b71  jz      loc_180078C41
0x180078b77  mov     r9, [rsp+4A0h+FilePart]
0x180078b7c  lea     r8, [rsp+4A0h+var_460]
0x180078b81  mov     rdx, rsi
0x180078b84  mov     rcx, rdi
0x180078b87  call    LoadMUIFile
0x180078b8c  mov     rbx, rax
0x180078b8f  test    rax, rax
0x180078b92  jnz     loc_180078CEA
0x180078b98  mov     r9, [rsp+4A0h+FilePart]
0x180078b9d  lea     r8, [rbp+3A0h+var_300]
0x180078ba4  mov     rdx, rsi
0x180078ba7  mov     rcx, rdi
0x180078baa  call    LoadMUIFile
0x180078baf  mov     rbx, rax
0x180078bb2  test    rax, rax
0x180078bb5  jnz     loc_180078CEA
0x180078bbb  cmp     [rbp+3A0h+var_3B0], r13w
0x180078bc0  jz      short loc_180078BE2
0x180078bc2  mov     r9, [rsp+4A0h+FilePart]
0x180078bc7  lea     r8, [rbp+3A0h+var_3B0]
0x180078bcb  mov     rdx, rsi
0x180078bce  mov     rcx, rdi
0x180078bd1  call    LoadMUIFile
0x180078bd6  mov     rbx, rax
0x180078bd9  test    rax, rax
0x180078bdc  jnz     loc_180078CEA
0x180078be2  mov     ecx, 409h
0x180078be7  cmp     cx, r14w
0x180078beb  jz      short loc_180078C22
0x180078bed  xor     r9d, r9d
0x180078bf0  lea     r8, [rbp+3A0h+var_300]
0x180078bf7  lea     rdx, [rsp+4A0h+var_460]
0x180078bfc  call    LookupLangID
0x180078c01  mov     r9, [rsp+4A0h+FilePart]
0x180078c06  lea     r8, [rsp+4A0h+var_460]
0x180078c0b  mov     rdx, rsi
0x180078c0e  mov     rcx, rdi
0x180078c11  call    LoadMUIFile
0x180078c16  mov     rbx, rax
0x180078c19  test    rax, rax
0x180078c1c  jnz     loc_180078CEA
0x180078c22  mov     r9, [rsp+4A0h+FilePart]
0x180078c27  xor     r8d, r8d
0x180078c2a  mov     rdx, rsi
0x180078c2d  mov     rcx, rdi
0x180078c30  call    LoadMUIFile
0x180078c35  mov     rbx, rax
0x180078c38  test    rax, rax
0x180078c3b  jnz     loc_180078CEA
0x180078c41  test    dil, 1
0x180078c45  jz      loc_180078D20
0x180078c4b  mov     rcx, rdi; hLibModule
0x180078c4e  call    cs:__imp_FreeLibrary
0x180078c55  nop     dword ptr [rax+rax+00h]
0x180078c5a  call    GetOSType
0x180078c5f  test    al, 38h
0x180078c61  jz      loc_180078CFE
0x180078c67  mov     rax, [rsp+4A0h+FilePart]
0x180078c6c  lea     r8, aSS; "%s\\%s"
0x180078c73  mov     r9, rsi
0x180078c76  mov     [rsp+4A0h+lpBuffer], rax
0x180078c7b  mov     edx, 104h; unsigned __int64
0x180078c80  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180078c87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078c8c  xor     r8d, r8d
0x180078c8f  lea     rcx, [rbp+3A0h+Buffer]
0x180078c96  lea     edx, [r8+1]
0x180078c9a  call    MapMUIFile
0x180078c9f  jmp     short loc_180078D1D
0x180078ca1  test    byte ptr cs:dword_1800938C0, 7
0x180078ca8  jz      short loc_180078C41
0x180078caa  xor     r9d, r9d
0x180078cad  lea     r8, [rbp+3A0h+var_300]
0x180078cb4  lea     rdx, [rsp+4A0h+var_460]
0x180078cb9  movzx   ecx, bx
0x180078cbc  call    LookupLangID
0x180078cc1  test    eax, eax
0x180078cc3  jz      loc_180078C41
0x180078cc9  mov     r9, [rsp+4A0h+FilePart]
0x180078cce  lea     r8, [rsp+4A0h+var_460]
0x180078cd3  mov     rdx, rsi
0x180078cd6  mov     rcx, rdi
0x180078cd9  call    LoadMUIFile
0x180078cde  mov     rbx, rax
0x180078ce1  test    rbx, rbx
0x180078ce4  jz      loc_180078C41
0x180078cea  mov     rcx, rdi; hLibModule
0x180078ced  call    cs:__imp_FreeLibrary
0x180078cf4  nop     dword ptr [rax+rax+00h]
0x180078cf9  mov     rax, rbx
0x180078cfc  jmp     short loc_180078D36
0x180078cfe  call    GetOSType
0x180078d03  test    al, 26h
0x180078d05  mov     r8d, r13d
0x180078d08  mov     rcx, r12; lpLibFileName
0x180078d0b  setnz   r8b; dwFlags
0x180078d0f  xor     edx, edx; hFile
0x180078d11  call    cs:__imp_LoadLibraryExW
0x180078d18  nop     dword ptr [rax+rax+00h]
0x180078d1d  mov     rdi, rax
0x180078d20  mov     rax, rdi
0x180078d23  jmp     short loc_180078D36
0x180078d25  mov     rcx, rdi; hLibModule
0x180078d28  call    cs:__imp_FreeLibrary
0x180078d2f  nop     dword ptr [rax+rax+00h]
0x180078d34  xor     eax, eax
0x180078d36  mov     rcx, [rbp+3A0h+var_40]
0x180078d3d  xor     rcx, rsp; StackCookie
0x180078d40  call    __security_check_cookie
0x180078d45  mov     rbx, [rsp+4A0h+arg_8]
0x180078d4d  add     rsp, 470h
0x180078d54  pop     r15
0x180078d56  pop     r14
0x180078d58  pop     r13
0x180078d5a  pop     r12
0x180078d5c  pop     rdi
0x180078d5d  pop     rsi
0x180078d5e  pop     rbp
0x180078d5f  retn
```
