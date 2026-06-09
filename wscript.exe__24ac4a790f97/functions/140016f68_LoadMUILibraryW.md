# LoadMUILibraryW

- ea: `0x140016f68`
- end: `0x140017426`
- name: `LoadMUILibraryW`
- size: `1214`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140014958`

## callees

- `0x140004ca8`
- `0x1400168a0`
- `0x1400169ac`
- `0x140016ad4`
- `0x140016b48`
- `0x140016cbc`
- `0x140016f68`
- `0x140017572`
- `0x1400175a0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x140017052`
- `KERNEL32!FindResourceExW` at `0x140017052`
- `KERNEL32!GetLocaleInfoW` at `0x1400170ab`
- `KERNEL32!GetLocaleInfoW` at `0x1400170ab`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14001707b`
- `KERNEL32!GetUserDefaultUILanguage` at `0x14001707b`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140017171`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x140017171`
- `KERNEL32!FreeLibrary` at `0x140017330`
- `KERNEL32!FreeLibrary` at `0x1400173c5`
- `KERNEL32!FreeLibrary` at `0x1400173f4`
- `KERNEL32!FreeLibrary` at `0x140017330`
- `KERNEL32!FreeLibrary` at `0x1400173c5`
- `KERNEL32!FreeLibrary` at `0x1400173f4`
- `KERNEL32!LoadLibraryExW` at `0x140016fc9`
- `KERNEL32!LoadLibraryExW` at `0x1400173e3`
- `KERNEL32!LoadLibraryExW` at `0x140016fc9`
- `KERNEL32!LoadLibraryExW` at `0x1400173e3`
- `KERNEL32!SearchPathW` at `0x14001700c`
- `KERNEL32!SearchPathW` at `0x14001700c`

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
  dword_140020A48 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_140020A48 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_140020A48 & 0x20) != 0 )
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
      if ( (dword_140020A48 & 4) == 0 )
      {
        if ( (dword_140020A48 & 3) != 0 )
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
      if ( !GetLocaleInfoW(0x404u, 8u, LCData, 32) || !wcsncmp_0(LCData, &word_14001C584, 3u) )
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
    if ( (dword_140020A48 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
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
0x140016f68  mov     [rsp-8+arg_8], rbx
0x140016f6d  push    rbp
0x140016f6e  push    rsi
0x140016f6f  push    rdi
0x140016f70  push    r12
0x140016f72  push    r13
0x140016f74  push    r14
0x140016f76  push    r15
0x140016f78  lea     rbp, [rsp-3B0h]
0x140016f80  sub     rsp, 4B0h
0x140016f87  mov     rax, cs:__security_cookie
0x140016f8e  xor     rax, rsp
0x140016f91  mov     [rbp+3E0h+var_40], rax
0x140016f98  xor     r13d, r13d
0x140016f9b  movzx   ebx, r8w
0x140016f9f  mov     [rsp+4E0h+FilePart], r13
0x140016fa4  mov     r12, rcx
0x140016fa7  test    rcx, rcx
0x140016faa  jz      loc_1400173FA
0x140016fb0  call    GetOSType
0x140016fb5  mov     cs:dword_140020A48, eax
0x140016fbb  xor     edx, edx; hFile
0x140016fbd  and     eax, 20h
0x140016fc0  mov     rcx, r12; lpLibFileName
0x140016fc3  or      eax, 2
0x140016fc6  mov     r8d, eax; dwFlags
0x140016fc9  call    cs:__imp_LoadLibraryExW
0x140016fcf  mov     rdi, rax
0x140016fd2  test    rax, rax
0x140016fd5  jz      loc_1400173FA
0x140016fdb  test    byte ptr cs:dword_140020A48, 20h
0x140016fe2  jnz     loc_1400173FC
0x140016fe8  lea     rax, [rsp+4E0h+FilePart]
0x140016fed  mov     r9d, 104h; nBufferLength
0x140016ff3  mov     [rsp+4E0h+lpFilePart], rax; lpFilePart
0x140016ff8  xor     r8d, r8d; lpExtension
0x140016ffb  lea     rax, [rbp+3E0h+Buffer]
0x140017002  mov     rdx, r12; lpFileName
0x140017005  xor     ecx, ecx; lpPath
0x140017007  mov     [rsp+4E0h+lpBuffer], rax; lpBuffer
0x14001700c  call    cs:__imp_SearchPathW
0x140017012  test    eax, eax
0x140017014  jz      loc_1400173F1
0x14001701a  mov     rcx, [rsp+4E0h+FilePart]
0x14001701f  test    rcx, rcx
0x140017022  jnz     short loc_140017035
0x140017024  lea     rax, [rbp+3E0h+Buffer]
0x14001702b  mov     esi, r13d
0x14001702e  mov     [rsp+4E0h+FilePart], rax
0x140017033  jmp     short loc_140017041
0x140017035  lea     rsi, [rbp+3E0h+Buffer]
0x14001703c  mov     [rcx-2], r13w
0x140017041  xor     r9d, r9d; wLanguage
0x140017044  lea     rdx, Type; "MUI"
0x14001704b  mov     rcx, rdi; hModule
0x14001704e  lea     r8d, [r9+1]; lpName
0x140017052  call    cs:__imp_FindResourceExW
0x140017058  test    rax, rax
0x14001705b  jz      loc_140017323
0x140017061  test    bx, bx
0x140017064  jnz     loc_14001737D
0x14001706a  mov     eax, cs:dword_140020A48
0x140017070  test    al, 4
0x140017072  jz      loc_140017228
0x140017078  mov     rbx, r13
0x14001707b  call    cs:__imp_GetUserDefaultUILanguage
0x140017081  mov     r15d, 404h
0x140017087  movzx   r14d, ax
0x14001708b  cmp     ax, r15w
0x14001708f  jnz     short loc_1400170D6
0x140017091  mov     r9d, 20h ; ' '; cchData
0x140017097  lea     r8, [rbp+3E0h+LCData]; lpLCData
0x14001709e  mov     ecx, r15d; Locale
0x1400170a1  mov     r14d, 0C04h
0x1400170a7  lea     edx, [r9-18h]; LCType
0x1400170ab  call    cs:__imp_GetLocaleInfoW
0x1400170b1  test    eax, eax
0x1400170b3  jz      short loc_1400170D6
0x1400170b5  mov     r8d, 3; MaxCount
0x1400170bb  lea     rdx, word_14001C584; String2
0x1400170c2  lea     rcx, [rbp+3E0h+LCData]; String1
0x1400170c9  call    wcsncmp_0
0x1400170ce  test    eax, eax
0x1400170d0  jz      short loc_1400170D6
0x1400170d2  movzx   r14d, r15w
0x1400170d6  lea     r9, [rbp+3E0h+var_3F0]
0x1400170da  movzx   ecx, r14w
0x1400170de  lea     r8, [rbp+3E0h+var_340]
0x1400170e5  lea     rdx, [rsp+4E0h+var_4A0]
0x1400170ea  call    LookupLangID
0x1400170ef  test    eax, eax
0x1400170f1  jz      loc_1400173B9
0x1400170f7  mov     r9, [rsp+4E0h+FilePart]
0x1400170fc  lea     r8, [rsp+4E0h+var_4A0]
0x140017101  mov     rdx, rsi
0x140017104  mov     rcx, rdi
0x140017107  call    LoadMUIFile
0x14001710c  mov     rbx, rax
0x14001710f  test    rax, rax
0x140017112  jnz     loc_1400173C2
0x140017118  mov     r9, [rsp+4E0h+FilePart]
0x14001711d  lea     r8, [rbp+3E0h+var_340]
0x140017124  mov     rdx, rsi
0x140017127  mov     rcx, rdi
0x14001712a  call    LoadMUIFile
0x14001712f  mov     rbx, rax
0x140017132  test    rax, rax
0x140017135  jnz     loc_1400173C2
0x14001713b  cmp     [rbp+3E0h+var_3F0], r13w
0x140017140  jz      short loc_140017162
0x140017142  mov     r9, [rsp+4E0h+FilePart]
0x140017147  lea     r8, [rbp+3E0h+var_3F0]
0x14001714b  mov     rdx, rsi
0x14001714e  mov     rcx, rdi
0x140017151  call    LoadMUIFile
0x140017156  mov     rbx, rax
0x140017159  test    rax, rax
0x14001715c  jnz     loc_1400173C2
0x140017162  mov     eax, 0C04h
0x140017167  cmp     r14w, ax
0x14001716b  jz      loc_1400170D2
0x140017171  call    cs:__imp_GetSystemDefaultUILanguage
0x140017177  movzx   r15d, ax
0x14001717b  cmp     ax, r14w
0x14001717f  jz      loc_140017210
0x140017185  lea     r9, [rbp+3E0h+var_3F0]
0x140017189  movzx   ecx, ax
0x14001718c  lea     r8, [rbp+3E0h+var_340]
0x140017193  lea     rdx, [rsp+4E0h+var_4A0]
0x140017198  call    LookupLangID
0x14001719d  test    eax, eax
0x14001719f  jz      loc_140017323
0x1400171a5  mov     r9, [rsp+4E0h+FilePart]
0x1400171aa  lea     r8, [rsp+4E0h+var_4A0]
0x1400171af  mov     rdx, rsi
0x1400171b2  mov     rcx, rdi
0x1400171b5  call    LoadMUIFile
0x1400171ba  mov     rbx, rax
0x1400171bd  test    rax, rax
0x1400171c0  jnz     loc_1400173C2
0x1400171c6  mov     r9, [rsp+4E0h+FilePart]
0x1400171cb  lea     r8, [rbp+3E0h+var_340]
0x1400171d2  mov     rdx, rsi
0x1400171d5  mov     rcx, rdi
0x1400171d8  call    LoadMUIFile
0x1400171dd  mov     rbx, rax
0x1400171e0  test    rax, rax
0x1400171e3  jnz     loc_1400173C2
0x1400171e9  cmp     [rbp+3E0h+var_3F0], r13w
0x1400171ee  jz      short loc_140017210
0x1400171f0  mov     r9, [rsp+4E0h+FilePart]
0x1400171f5  lea     r8, [rbp+3E0h+var_3F0]
0x1400171f9  mov     rdx, rsi
0x1400171fc  mov     rcx, rdi
0x1400171ff  call    LoadMUIFile
0x140017204  mov     rbx, rax
0x140017207  test    rax, rax
0x14001720a  jnz     loc_1400173C2
0x140017210  mov     ecx, 409h
0x140017215  cmp     cx, r14w
0x140017219  jz      loc_140017304
0x14001721f  cmp     cx, r15w
0x140017223  jmp     loc_1400172CD
0x140017228  test    al, 3
0x14001722a  jz      loc_140017323
0x140017230  call    GetInstallLanguage
0x140017235  lea     r9, [rbp+3E0h+var_3F0]
0x140017239  movzx   ecx, ax
0x14001723c  lea     r8, [rbp+3E0h+var_340]
0x140017243  movzx   r14d, ax
0x140017247  lea     rdx, [rsp+4E0h+var_4A0]
0x14001724c  call    LookupLangID
0x140017251  test    eax, eax
0x140017253  jz      loc_140017323
0x140017259  mov     r9, [rsp+4E0h+FilePart]
0x14001725e  lea     r8, [rsp+4E0h+var_4A0]
0x140017263  mov     rdx, rsi
0x140017266  mov     rcx, rdi
0x140017269  call    LoadMUIFile
0x14001726e  mov     rbx, rax
0x140017271  test    rax, rax
0x140017274  jnz     loc_1400173C2
0x14001727a  mov     r9, [rsp+4E0h+FilePart]
0x14001727f  lea     r8, [rbp+3E0h+var_340]
0x140017286  mov     rdx, rsi
0x140017289  mov     rcx, rdi
0x14001728c  call    LoadMUIFile
0x140017291  mov     rbx, rax
0x140017294  test    rax, rax
0x140017297  jnz     loc_1400173C2
0x14001729d  cmp     [rbp+3E0h+var_3F0], r13w
0x1400172a2  jz      short loc_1400172C4
0x1400172a4  mov     r9, [rsp+4E0h+FilePart]
0x1400172a9  lea     r8, [rbp+3E0h+var_3F0]
0x1400172ad  mov     rdx, rsi
0x1400172b0  mov     rcx, rdi
0x1400172b3  call    LoadMUIFile
0x1400172b8  mov     rbx, rax
0x1400172bb  test    rax, rax
0x1400172be  jnz     loc_1400173C2
0x1400172c4  mov     ecx, 409h
0x1400172c9  cmp     cx, r14w
0x1400172cd  jz      short loc_140017304
0x1400172cf  xor     r9d, r9d
0x1400172d2  lea     r8, [rbp+3E0h+var_340]
0x1400172d9  lea     rdx, [rsp+4E0h+var_4A0]
0x1400172de  call    LookupLangID
0x1400172e3  mov     r9, [rsp+4E0h+FilePart]
0x1400172e8  lea     r8, [rsp+4E0h+var_4A0]
0x1400172ed  mov     rdx, rsi
0x1400172f0  mov     rcx, rdi
0x1400172f3  call    LoadMUIFile
0x1400172f8  mov     rbx, rax
0x1400172fb  test    rax, rax
0x1400172fe  jnz     loc_1400173C2
0x140017304  mov     r9, [rsp+4E0h+FilePart]
0x140017309  xor     r8d, r8d
0x14001730c  mov     rdx, rsi
0x14001730f  mov     rcx, rdi
0x140017312  call    LoadMUIFile
0x140017317  mov     rbx, rax
0x14001731a  test    rax, rax
0x14001731d  jnz     loc_1400173C2
0x140017323  test    dil, 1
0x140017327  jz      loc_1400173EC
0x14001732d  mov     rcx, rdi; hLibModule
0x140017330  call    cs:__imp_FreeLibrary
0x140017336  call    GetOSType
0x14001733b  test    al, 38h
0x14001733d  jz      loc_1400173D0
0x140017343  mov     rax, [rsp+4E0h+FilePart]
0x140017348  lea     r8, aSS; "%s\\%s"
0x14001734f  mov     r9, rsi
0x140017352  mov     [rsp+4E0h+lpBuffer], rax
0x140017357  mov     edx, 104h; unsigned __int64
0x14001735c  lea     rcx, [rbp+3E0h+Buffer]; unsigned __int16 *
0x140017363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140017368  xor     r8d, r8d
0x14001736b  lea     rcx, [rbp+3E0h+Buffer]
0x140017372  lea     edx, [r8+1]
0x140017376  call    MapMUIFile
0x14001737b  jmp     short loc_1400173E9
0x14001737d  test    byte ptr cs:dword_140020A48, 7
0x140017384  jz      short loc_140017323
0x140017386  xor     r9d, r9d
0x140017389  lea     r8, [rbp+3E0h+var_340]
0x140017390  lea     rdx, [rsp+4E0h+var_4A0]
0x140017395  movzx   ecx, bx
0x140017398  call    LookupLangID
0x14001739d  test    eax, eax
0x14001739f  jz      short loc_140017323
0x1400173a1  mov     r9, [rsp+4E0h+FilePart]
0x1400173a6  lea     r8, [rsp+4E0h+var_4A0]
0x1400173ab  mov     rdx, rsi
0x1400173ae  mov     rcx, rdi
0x1400173b1  call    LoadMUIFile
0x1400173b6  mov     rbx, rax
0x1400173b9  test    rbx, rbx
0x1400173bc  jz      loc_140017323
0x1400173c2  mov     rcx, rdi; hLibModule
0x1400173c5  call    cs:__imp_FreeLibrary
0x1400173cb  mov     rax, rbx
0x1400173ce  jmp     short loc_1400173FC
0x1400173d0  call    GetOSType
0x1400173d5  test    al, 26h
0x1400173d7  mov     r8d, r13d
0x1400173da  mov     rcx, r12; lpLibFileName
0x1400173dd  setnz   r8b; dwFlags
0x1400173e1  xor     edx, edx; hFile
0x1400173e3  call    cs:__imp_LoadLibraryExW
0x1400173e9  mov     rdi, rax
0x1400173ec  mov     rax, rdi
0x1400173ef  jmp     short loc_1400173FC
0x1400173f1  mov     rcx, rdi; hLibModule
0x1400173f4  call    cs:__imp_FreeLibrary
0x1400173fa  xor     eax, eax
0x1400173fc  mov     rcx, [rbp+3E0h+var_40]
0x140017403  xor     rcx, rsp; StackCookie
0x140017406  call    __security_check_cookie
0x14001740b  mov     rbx, [rsp+4E0h+arg_8]
0x140017413  add     rsp, 4B0h
0x14001741a  pop     r15
0x14001741c  pop     r14
0x14001741e  pop     r13
0x140017420  pop     r12
0x140017422  pop     rdi
0x140017423  pop     rsi
0x140017424  pop     rbp
0x140017425  retn
```
