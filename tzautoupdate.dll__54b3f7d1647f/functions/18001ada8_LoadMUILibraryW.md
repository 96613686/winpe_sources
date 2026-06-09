# LoadMUILibraryW

- ea: `0x18001ada8`
- end: `0x18001af81`
- name: `LoadMUILibraryW`
- size: `473`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180019758`

## callees

- `0x180008ff0`
- `0x18001a850`
- `0x18001a978`
- `0x18001a9ec`
- `0x18001ab64`
- `0x18001ada8`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aed5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aee8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001af52`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aed5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aee8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001af52`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ae04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001af41`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ae04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001af41`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ae84`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ae84`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18001ae44`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18001ae44`

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
  dword_180031820 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_180031820 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_180031820 & 0x20) != 0 )
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
    && (dword_180031820 & 7) != 0
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
0x18001ada8  mov     [rsp-8+arg_8], rbx
0x18001adad  mov     [rsp-8+arg_10], rsi
0x18001adb2  push    rbp
0x18001adb3  push    rdi
0x18001adb4  push    r14
0x18001adb6  lea     rbp, [rsp-2C0h]
0x18001adbe  sub     rsp, 3C0h
0x18001adc5  mov     rax, cs:__security_cookie
0x18001adcc  xor     rax, rsp
0x18001adcf  mov     [rbp+2D0h+var_20], rax
0x18001add6  mov     [rsp+3D0h+FilePart], 0
0x18001addf  mov     rdi, rcx
0x18001ade2  test    rcx, rcx
0x18001ade5  jz      loc_18001AF58
0x18001adeb  call    GetOSType
0x18001adf0  mov     cs:dword_180031820, eax
0x18001adf6  xor     edx, edx; hFile
0x18001adf8  and     eax, 20h
0x18001adfb  mov     rcx, rdi; lpLibFileName
0x18001adfe  or      eax, 2
0x18001ae01  mov     r8d, eax; dwFlags
0x18001ae04  call    cs:__imp_LoadLibraryExW
0x18001ae0a  mov     rbx, rax
0x18001ae0d  test    rax, rax
0x18001ae10  jz      loc_18001AF58
0x18001ae16  test    byte ptr cs:dword_180031820, 20h
0x18001ae1d  jnz     loc_18001AF5A
0x18001ae23  lea     rax, [rsp+3D0h+FilePart]
0x18001ae28  mov     r9d, 104h; nBufferLength
0x18001ae2e  mov     [rsp+3D0h+lpFilePart], rax; lpFilePart
0x18001ae33  xor     r8d, r8d; lpExtension
0x18001ae36  lea     rax, [rbp+2D0h+Buffer]
0x18001ae3a  mov     rdx, rdi; lpFileName
0x18001ae3d  xor     ecx, ecx; lpPath
0x18001ae3f  mov     [rsp+3D0h+lpBuffer], rax; lpBuffer
0x18001ae44  call    cs:__imp_SearchPathW
0x18001ae4a  test    eax, eax
0x18001ae4c  jz      loc_18001AF4F
0x18001ae52  mov     rcx, [rsp+3D0h+FilePart]
0x18001ae57  test    rcx, rcx
0x18001ae5a  jnz     short loc_18001AE69
0x18001ae5c  lea     rax, [rbp+2D0h+Buffer]
0x18001ae60  xor     esi, esi
0x18001ae62  mov     [rsp+3D0h+FilePart], rax
0x18001ae67  jmp     short loc_18001AE73
0x18001ae69  xor     eax, eax
0x18001ae6b  lea     rsi, [rbp+2D0h+Buffer]
0x18001ae6f  mov     [rcx-2], ax
0x18001ae73  xor     r9d, r9d; wLanguage
0x18001ae76  lea     rdx, Type; "MUI"
0x18001ae7d  mov     rcx, rbx; hModule
0x18001ae80  lea     r8d, [r9+1]; lpName
0x18001ae84  call    cs:__imp_FindResourceExW
0x18001ae8a  test    rax, rax
0x18001ae8d  jz      short loc_18001AEE0
0x18001ae8f  test    byte ptr cs:dword_180031820, 7
0x18001ae96  jz      short loc_18001AEE0
0x18001ae98  mov     ecx, 400h
0x18001ae9d  lea     r8, [rbp+2D0h+var_D0]
0x18001aea4  xor     r9d, r9d
0x18001aea7  lea     rdx, [rsp+3D0h+var_390]
0x18001aeac  call    LookupLangID
0x18001aeb1  test    eax, eax
0x18001aeb3  jz      short loc_18001AEE0
0x18001aeb5  mov     r9, [rsp+3D0h+FilePart]
0x18001aeba  lea     r8, [rsp+3D0h+var_390]
0x18001aebf  mov     rdx, rsi
0x18001aec2  mov     rcx, rbx
0x18001aec5  call    LoadMUIFile
0x18001aeca  mov     r14, rax
0x18001aecd  test    rax, rax
0x18001aed0  jz      short loc_18001AEE0
0x18001aed2  mov     rcx, rbx; hLibModule
0x18001aed5  call    cs:__imp_FreeLibrary
0x18001aedb  mov     rax, r14
0x18001aede  jmp     short loc_18001AF5A
0x18001aee0  test    bl, 1
0x18001aee3  jz      short loc_18001AF4A
0x18001aee5  mov     rcx, rbx; hLibModule
0x18001aee8  call    cs:__imp_FreeLibrary
0x18001aeee  call    GetOSType
0x18001aef3  test    al, 38h
0x18001aef5  jz      short loc_18001AF2B
0x18001aef7  mov     rax, [rsp+3D0h+FilePart]
0x18001aefc  lea     r8, aSS; "%s\\%s"
0x18001af03  mov     r9, rsi
0x18001af06  mov     [rsp+3D0h+lpBuffer], rax
0x18001af0b  mov     edx, 104h; unsigned __int64
0x18001af10  lea     rcx, [rbp+2D0h+Buffer]; unsigned __int16 *
0x18001af14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001af19  xor     r8d, r8d
0x18001af1c  lea     rcx, [rbp+2D0h+Buffer]
0x18001af20  lea     edx, [r8+1]
0x18001af24  call    MapMUIFile
0x18001af29  jmp     short loc_18001AF47
0x18001af2b  call    GetOSType
0x18001af30  test    al, 26h
0x18001af32  mov     r8d, 0
0x18001af38  mov     rcx, rdi; lpLibFileName
0x18001af3b  setnz   r8b; dwFlags
0x18001af3f  xor     edx, edx; hFile
0x18001af41  call    cs:__imp_LoadLibraryExW
0x18001af47  mov     rbx, rax
0x18001af4a  mov     rax, rbx
0x18001af4d  jmp     short loc_18001AF5A
0x18001af4f  mov     rcx, rbx; hLibModule
0x18001af52  call    cs:__imp_FreeLibrary
0x18001af58  xor     eax, eax
0x18001af5a  mov     rcx, [rbp+2D0h+var_20]
0x18001af61  xor     rcx, rsp; StackCookie
0x18001af64  call    __security_check_cookie
0x18001af69  lea     r11, [rsp+3D0h+var_10]
0x18001af71  mov     rbx, [r11+28h]
0x18001af75  mov     rsi, [r11+30h]
0x18001af79  mov     rsp, r11
0x18001af7c  pop     r14
0x18001af7e  pop     rdi
0x18001af7f  pop     rbp
0x18001af80  retn
```
