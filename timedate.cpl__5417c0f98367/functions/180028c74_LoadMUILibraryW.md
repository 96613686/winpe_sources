# LoadMUILibraryW

- ea: `0x180028c74`
- end: `0x180028e4d`
- name: `LoadMUILibraryW`
- size: `473`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800275e8`

## callees

- `0x180008a0c`
- `0x18002871c`
- `0x180028844`
- `0x1800288b8`
- `0x180028a30`
- `0x180028c74`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028da1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028db4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028e1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028da1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028db4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180028e1e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028cd0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028e0d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028cd0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028e0d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180028d50`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180028d50`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180028d10`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180028d10`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rbx
  WCHAR *v6; // rsi
  HINSTANCE MUIFile; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[176]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v19[176]; // [rsp+300h] [rbp+200h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_18003B180 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_18003B180 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_18003B180 & 0x20) != 0 )
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
  if ( FindResourceExW(v5, L"MUI", (LPCWSTR)1, 0)
    && (dword_18003B180 & 7) != 0
    && (unsigned int)LookupLangID(1024, v17, v19, 0)
    && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v17, FilePart)) != 0 )
  {
    FreeLibrary(v5);
    return MUIFile;
  }
  else
  {
    if ( ((unsigned __int8)v5 & 1) != 0 )
    {
      FreeLibrary(v5);
      if ( (GetOSType(v9, v8, v10) & 0x38) != 0 )
      {
        StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
        return (HINSTANCE)MapMUIFile(Buffer, 1);
      }
      else
      {
        OSType = GetOSType(v12, v11, v13);
        return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x180028c74  mov     [rsp-8+arg_8], rbx
0x180028c79  mov     [rsp-8+arg_10], rsi
0x180028c7e  push    rbp
0x180028c7f  push    rdi
0x180028c80  push    r14
0x180028c82  lea     rbp, [rsp-2C0h]
0x180028c8a  sub     rsp, 3C0h
0x180028c91  mov     rax, cs:__security_cookie
0x180028c98  xor     rax, rsp
0x180028c9b  mov     [rbp+2D0h+var_20], rax
0x180028ca2  mov     [rsp+3D0h+FilePart], 0
0x180028cab  mov     rdi, rcx
0x180028cae  test    rcx, rcx
0x180028cb1  jz      loc_180028E24
0x180028cb7  call    GetOSType
0x180028cbc  mov     cs:dword_18003B180, eax
0x180028cc2  xor     edx, edx; hFile
0x180028cc4  and     eax, 20h
0x180028cc7  mov     rcx, rdi; lpLibFileName
0x180028cca  or      eax, 2
0x180028ccd  mov     r8d, eax; dwFlags
0x180028cd0  call    cs:__imp_LoadLibraryExW
0x180028cd6  mov     rbx, rax
0x180028cd9  test    rax, rax
0x180028cdc  jz      loc_180028E24
0x180028ce2  test    byte ptr cs:dword_18003B180, 20h
0x180028ce9  jnz     loc_180028E26
0x180028cef  lea     rax, [rsp+3D0h+FilePart]
0x180028cf4  mov     r9d, 104h; nBufferLength
0x180028cfa  mov     [rsp+3D0h+lpFilePart], rax; lpFilePart
0x180028cff  xor     r8d, r8d; lpExtension
0x180028d02  lea     rax, [rbp+2D0h+Buffer]
0x180028d06  mov     rdx, rdi; lpFileName
0x180028d09  xor     ecx, ecx; lpPath
0x180028d0b  mov     [rsp+3D0h+lpBuffer], rax; lpBuffer
0x180028d10  call    cs:__imp_SearchPathW
0x180028d16  test    eax, eax
0x180028d18  jz      loc_180028E1B
0x180028d1e  mov     rcx, [rsp+3D0h+FilePart]
0x180028d23  test    rcx, rcx
0x180028d26  jnz     short loc_180028D35
0x180028d28  lea     rax, [rbp+2D0h+Buffer]
0x180028d2c  xor     esi, esi
0x180028d2e  mov     [rsp+3D0h+FilePart], rax
0x180028d33  jmp     short loc_180028D3F
0x180028d35  xor     eax, eax
0x180028d37  lea     rsi, [rbp+2D0h+Buffer]
0x180028d3b  mov     [rcx-2], ax
0x180028d3f  xor     r9d, r9d; wLanguage
0x180028d42  lea     rdx, aMui; "MUI"
0x180028d49  mov     rcx, rbx; hModule
0x180028d4c  lea     r8d, [r9+1]; lpName
0x180028d50  call    cs:__imp_FindResourceExW
0x180028d56  test    rax, rax
0x180028d59  jz      short loc_180028DAC
0x180028d5b  test    byte ptr cs:dword_18003B180, 7
0x180028d62  jz      short loc_180028DAC
0x180028d64  mov     ecx, 400h
0x180028d69  lea     r8, [rbp+2D0h+var_D0]
0x180028d70  xor     r9d, r9d
0x180028d73  lea     rdx, [rsp+3D0h+var_390]
0x180028d78  call    LookupLangID
0x180028d7d  test    eax, eax
0x180028d7f  jz      short loc_180028DAC
0x180028d81  mov     r9, [rsp+3D0h+FilePart]
0x180028d86  lea     r8, [rsp+3D0h+var_390]
0x180028d8b  mov     rdx, rsi
0x180028d8e  mov     rcx, rbx
0x180028d91  call    LoadMUIFile
0x180028d96  mov     r14, rax
0x180028d99  test    rax, rax
0x180028d9c  jz      short loc_180028DAC
0x180028d9e  mov     rcx, rbx; hLibModule
0x180028da1  call    cs:__imp_FreeLibrary
0x180028da7  mov     rax, r14
0x180028daa  jmp     short loc_180028E26
0x180028dac  test    bl, 1
0x180028daf  jz      short loc_180028E16
0x180028db1  mov     rcx, rbx; hLibModule
0x180028db4  call    cs:__imp_FreeLibrary
0x180028dba  call    GetOSType
0x180028dbf  test    al, 38h
0x180028dc1  jz      short loc_180028DF7
0x180028dc3  mov     rax, [rsp+3D0h+FilePart]
0x180028dc8  lea     r8, aSS; "%s\\%s"
0x180028dcf  mov     r9, rsi
0x180028dd2  mov     [rsp+3D0h+lpBuffer], rax
0x180028dd7  mov     edx, 104h; unsigned __int64
0x180028ddc  lea     rcx, [rbp+2D0h+Buffer]; unsigned __int16 *
0x180028de0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028de5  xor     r8d, r8d
0x180028de8  lea     rcx, [rbp+2D0h+Buffer]
0x180028dec  lea     edx, [r8+1]
0x180028df0  call    MapMUIFile
0x180028df5  jmp     short loc_180028E13
0x180028df7  call    GetOSType
0x180028dfc  test    al, 26h
0x180028dfe  mov     r8d, 0
0x180028e04  mov     rcx, rdi; lpLibFileName
0x180028e07  setnz   r8b; dwFlags
0x180028e0b  xor     edx, edx; hFile
0x180028e0d  call    cs:__imp_LoadLibraryExW
0x180028e13  mov     rbx, rax
0x180028e16  mov     rax, rbx
0x180028e19  jmp     short loc_180028E26
0x180028e1b  mov     rcx, rbx; hLibModule
0x180028e1e  call    cs:__imp_FreeLibrary
0x180028e24  xor     eax, eax
0x180028e26  mov     rcx, [rbp+2D0h+var_20]
0x180028e2d  xor     rcx, rsp; StackCookie
0x180028e30  call    __security_check_cookie
0x180028e35  lea     r11, [rsp+3D0h+var_10]
0x180028e3d  mov     rbx, [r11+28h]
0x180028e41  mov     rsi, [r11+30h]
0x180028e45  mov     rsp, r11
0x180028e48  pop     r14
0x180028e4a  pop     rdi
0x180028e4b  pop     rbp
0x180028e4c  retn
```
