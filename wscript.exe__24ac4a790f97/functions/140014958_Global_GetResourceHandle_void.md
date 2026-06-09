# Global::GetResourceHandle(void)

- ea: `0x140014958`
- end: `0x140014dd2`
- name: `?GetResourceHandle@Global@@CAPEAUHINSTANCE__@@XZ`
- size: `1146`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140014dd8`

## callees

- `0x140006744`
- `0x140014958`
- `0x140016f68`
- `0x140017542`
- `0x1400175a0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x140014b5f`
- `msvcrt!strcpy_s` at `0x140014c62`
- `msvcrt!strcpy_s` at `0x140014d6b`
- `msvcrt!strcpy_s` at `0x140014b5f`
- `msvcrt!strcpy_s` at `0x140014c62`
- `msvcrt!strcpy_s` at `0x140014d6b`
- `msvcrt!sprintf_s` at `0x140014be3`
- `msvcrt!sprintf_s` at `0x140014cee`
- `msvcrt!sprintf_s` at `0x140014be3`
- `msvcrt!sprintf_s` at `0x140014cee`
- `KERNEL32!GetModuleFileNameA` at `0x140014adc`
- `KERNEL32!GetModuleFileNameA` at `0x140014adc`
- `KERNEL32!GetUserDefaultLCID` at `0x14001498f`
- `KERNEL32!GetUserDefaultLCID` at `0x140014ca1`
- `KERNEL32!GetUserDefaultLCID` at `0x14001498f`
- `KERNEL32!GetUserDefaultLCID` at `0x140014ca1`
- `KERNEL32!GetLocaleInfoA` at `0x140014a65`
- `KERNEL32!GetLocaleInfoA` at `0x140014cc1`
- `KERNEL32!GetLocaleInfoA` at `0x140014a65`
- `KERNEL32!GetLocaleInfoA` at `0x140014cc1`
- `KERNEL32!GetLocaleInfoW` at `0x1400149b1`
- `KERNEL32!GetLocaleInfoW` at `0x1400149b1`
- `KERNEL32!GetModuleFileNameW` at `0x140014a17`
- `KERNEL32!GetModuleFileNameW` at `0x140014a17`
- `KERNEL32!LoadLibraryExA` at `0x140014b77`
- `KERNEL32!LoadLibraryExA` at `0x140014b92`
- `KERNEL32!LoadLibraryExA` at `0x140014c74`
- `KERNEL32!LoadLibraryExA` at `0x140014c8f`
- `KERNEL32!LoadLibraryExA` at `0x140014d7d`
- `KERNEL32!LoadLibraryExA` at `0x140014d94`
- `KERNEL32!LoadLibraryExA` at `0x140014b77`
- `KERNEL32!LoadLibraryExA` at `0x140014b92`
- `KERNEL32!LoadLibraryExA` at `0x140014c74`
- `KERNEL32!LoadLibraryExA` at `0x140014c8f`
- `KERNEL32!LoadLibraryExA` at `0x140014d7d`
- `KERNEL32!LoadLibraryExA` at `0x140014d94`
- `KERNEL32!FreeLibrary` at `0x140014a43`
- `KERNEL32!FreeLibrary` at `0x140014a43`
- `USER32!LoadStringA` at `0x140014a9f`
- `USER32!LoadStringA` at `0x140014a9f`
- `USER32!CharNextA` at `0x140014b04`
- `USER32!CharNextA` at `0x140014c0b`
- `USER32!CharNextA` at `0x140014d16`
- `USER32!CharNextA` at `0x140014b04`
- `USER32!CharNextA` at `0x140014c0b`
- `USER32!CharNextA` at `0x140014d16`

## string_xrefs

- `0x140014abd`: `%s%s.DLL`
- `0x140014bd5`: `%s%s.DLL`
- `0x140014ce3`: `%s%s.DLL`

## pseudocode

```c
HINSTANCE Global::GetResourceHandle(void)
{
  HINSTANCE result; // rax
  LCID UserDefaultLCID; // eax
  LCID v2; // esi
  HINSTANCE MUILibraryW; // rbx
  CHAR v4; // cl
  CHAR *v5; // rbx
  CHAR *v6; // rax
  size_t v7; // rbx
  __int64 v8; // rsi
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  CHAR v11; // cl
  CHAR *v12; // rbx
  CHAR *v13; // rax
  size_t v14; // rbx
  __int64 v15; // rax
  __int16 v16; // ax
  CHAR v17; // cl
  CHAR *v18; // rbx
  CHAR *v19; // rax
  size_t v20; // rbx
  WCHAR LCData[2]; // [rsp+30h] [rbp-D0h] BYREF
  CHAR v22[12]; // [rsp+34h] [rbp-CCh] BYREF
  CHAR sz[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR Source[272]; // [rsp+150h] [rbp+50h] BYREF
  CHAR LibFileName[272]; // [rsp+260h] [rbp+160h] BYREF
  CHAR Buffer[272]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR Filename[264]; // [rsp+480h] [rbp+380h] BYREF

  result = Global::g_hResource;
  if ( Global::g_hResource )
    return result;
  UserDefaultLCID = GetUserDefaultLCID();
  *(_DWORD *)LCData = 0;
  v2 = UserDefaultLCID;
  if ( GetLocaleInfoW(UserDefaultLCID, 0x20000070u, LCData, 2) && *(_DWORD *)LCData == 1 )
  {
    if ( Global::g_lResourceBase == 2000 )
      return Global::g_hInstance;
    Global::g_isLanguageBiDi = 1;
  }
  if ( Global::g_fWindowsVista || (v2 & 0x3FF) == 9 )
    return Global::g_hInstance;
  MUILibraryW = 0;
  if ( GetModuleFileNameW(Global::g_hInstance, Filename, 0x104u) )
    MUILibraryW = LoadMUILibraryW(Filename, 8u, v2);
  if ( MUILibraryW == Global::g_hInstance )
  {
    FreeLibrary(MUILibraryW);
  }
  else if ( MUILibraryW )
  {
    return MUILibraryW;
  }
  if ( GetLocaleInfoA(v2, 3u, v22, 5) && LoadStringA(Global::g_hInstance, 0x3E9u, Buffer, 260) )
  {
    StringCchPrintfA(Source, 0x104u, "%s%s.DLL", Buffer, v22);
    GetModuleFileNameA(Global::g_hInstance, sz, 0x104u);
    v4 = sz[0];
    v5 = sz;
    if ( sz[0] )
    {
      v6 = sz;
      do
      {
        if ( v4 == 92 )
          v5 = ++v6;
        else
          v6 = CharNextA(v6);
        v4 = *v6;
      }
      while ( *v6 );
    }
    v7 = v5 - sz;
    v8 = -1;
    v9 = -1;
    do
      ++v9;
    while ( Source[v9] );
    if ( v7 + v9 + 1 <= 0x104 )
    {
      memcpy_0(LibFileName, sz, v7);
      strcpy_s(&LibFileName[v7], 260 - v7, Source);
    }
    MUILibraryW = LoadLibraryExA(LibFileName, 0, 0x60u);
    if ( MUILibraryW )
      return MUILibraryW;
    MUILibraryW = LoadLibraryExA(Source, 0, 0x60u);
    if ( MUILibraryW )
      return MUILibraryW;
    v10 = -1;
    do
      ++v10;
    while ( v22[v10] );
    if ( v10 > 2 )
    {
      v22[2] = 0;
      sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v22);
      v11 = sz[0];
      v12 = sz;
      if ( sz[0] )
      {
        v13 = sz;
        do
        {
          if ( v11 == 92 )
            v12 = ++v13;
          else
            v13 = CharNextA(v13);
          v11 = *v13;
        }
        while ( *v13 );
      }
      v14 = v12 - sz;
      v15 = -1;
      do
        ++v15;
      while ( Source[v15] );
      if ( v14 + v15 + 1 <= 0x104 )
      {
        memcpy_0(LibFileName, sz, v14);
        strcpy_s(&LibFileName[v14], 260 - v14, Source);
      }
      MUILibraryW = LoadLibraryExA(LibFileName, 0, 0x60u);
      if ( MUILibraryW )
        return MUILibraryW;
      MUILibraryW = LoadLibraryExA(Source, 0, 0x60u);
      if ( MUILibraryW )
        return MUILibraryW;
    }
    v16 = GetUserDefaultLCID();
    if ( GetLocaleInfoA(v16 & 0x3FF | 0x400, 3u, v22, 5) )
    {
      sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v22);
      v17 = sz[0];
      v18 = sz;
      if ( sz[0] )
      {
        v19 = sz;
        do
        {
          if ( v17 == 92 )
            v18 = ++v19;
          else
            v19 = CharNextA(v19);
          v17 = *v19;
        }
        while ( *v19 );
      }
      v20 = v18 - sz;
      do
        ++v8;
      while ( Source[v8] );
      if ( v20 + v8 + 1 <= 0x104 )
      {
        memcpy_0(LibFileName, sz, v20);
        strcpy_s(&LibFileName[v20], 260 - v20, Source);
      }
      MUILibraryW = LoadLibraryExA(LibFileName, 0, 0x60u);
      if ( !MUILibraryW )
      {
        MUILibraryW = LoadLibraryExA(Source, 0, 0x60u);
        if ( !MUILibraryW )
          return Global::g_hInstance;
      }
      return MUILibraryW;
    }
  }
  result = Global::g_hInstance;
  if ( Global::g_hResource )
    return Global::g_hResource;
  return result;
}

```

## disassembly

```asm
0x140014958  push    rbp
0x14001495a  push    rbx
0x14001495b  push    rsi
0x14001495c  push    rdi
0x14001495d  push    r15
0x14001495f  lea     rbp, [rsp-5A0h]
0x140014967  sub     rsp, 6A0h
0x14001496e  mov     rax, cs:__security_cookie
0x140014975  xor     rax, rsp
0x140014978  mov     [rbp+5C0h+var_30], rax
0x14001497f  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x140014986  test    rax, rax
0x140014989  jnz     loc_140014DB5
0x14001498f  call    cs:__imp_GetUserDefaultLCID
0x140014995  mov     r9d, 2; cchData
0x14001499b  mov     dword ptr [rsp+6C0h+LCData], 0
0x1400149a3  mov     ecx, eax; Locale
0x1400149a5  lea     r8, [rsp+6C0h+LCData]; lpLCData
0x1400149aa  mov     edx, 20000070h; LCType
0x1400149af  mov     esi, eax
0x1400149b1  call    cs:__imp_GetLocaleInfoW
0x1400149b7  test    eax, eax
0x1400149b9  jz      short loc_1400149D9
0x1400149bb  cmp     dword ptr [rsp+6C0h+LCData], 1
0x1400149c0  jnz     short loc_1400149D9
0x1400149c2  cmp     cs:?g_lResourceBase@Global@@2JA, 7D0h; long Global::g_lResourceBase
0x1400149cc  jz      loc_140014DAE
0x1400149d2  mov     cs:?g_isLanguageBiDi@Global@@2_NA, 1; bool Global::g_isLanguageBiDi
0x1400149d9  cmp     cs:?g_fWindowsVista@Global@@2_NA, 0; bool Global::g_fWindowsVista
0x1400149e0  jnz     loc_140014DAE
0x1400149e6  mov     ecx, 3FFh
0x1400149eb  movzx   eax, si
0x1400149ee  and     ax, cx
0x1400149f1  mov     ecx, 9
0x1400149f6  cmp     cx, ax
0x1400149f9  jz      loc_140014DAE
0x1400149ff  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x140014a06  lea     rdx, [rbp+5C0h+Filename]; lpFilename
0x140014a0d  mov     edi, 104h
0x140014a12  xor     ebx, ebx
0x140014a14  mov     r8d, edi; nSize
0x140014a17  call    cs:__imp_GetModuleFileNameW
0x140014a1d  test    eax, eax
0x140014a1f  jz      short loc_140014A37
0x140014a21  movzx   r8d, si; LangID
0x140014a25  lea     edx, [rbx+8]; dwLangConvention
0x140014a28  lea     rcx, [rbp+5C0h+Filename]; pszFullModuleName
0x140014a2f  call    LoadMUILibraryW
0x140014a34  mov     rbx, rax
0x140014a37  cmp     rbx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140014a3e  jnz     short loc_140014A4B
0x140014a40  mov     rcx, rbx; hLibModule
0x140014a43  call    cs:__imp_FreeLibrary
0x140014a49  jmp     short loc_140014A54
0x140014a4b  test    rbx, rbx
0x140014a4e  jnz     loc_140014DA9
0x140014a54  mov     r9d, 5; cchData
0x140014a5a  lea     r8, [rsp+6C0h+var_68C]; lpLCData
0x140014a5f  mov     ecx, esi; Locale
0x140014a61  lea     edx, [r9-2]; LCType
0x140014a65  call    cs:__imp_GetLocaleInfoA
0x140014a6b  test    eax, eax
0x140014a6d  jnz     short loc_140014A89
0x140014a6f  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x140014a76  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140014a7d  test    rcx, rcx
0x140014a80  cmovnz  rax, rcx
0x140014a84  jmp     loc_140014DB5
0x140014a89  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x140014a90  lea     r8, [rbp+5C0h+Buffer]; lpBuffer
0x140014a97  mov     r9d, edi; cchBufferMax
0x140014a9a  mov     edx, 3E9h; uID
0x140014a9f  call    cs:__imp_LoadStringA
0x140014aa5  test    eax, eax
0x140014aa7  jz      short loc_140014A6F
0x140014aa9  lea     rax, [rsp+6C0h+var_68C]
0x140014aae  mov     rdx, rdi; unsigned __int64
0x140014ab1  lea     r9, [rbp+5C0h+Buffer]
0x140014ab8  mov     [rsp+6C0h+var_6A0], rax
0x140014abd  lea     r8, aSSDll; "%s%s.DLL"
0x140014ac4  lea     rcx, [rbp+5C0h+Source]; char *
0x140014ac8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140014acd  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x140014ad4  lea     rdx, [rsp+6C0h+sz]; lpFilename
0x140014ad9  mov     r8d, edi; nSize
0x140014adc  call    cs:__imp_GetModuleFileNameA
0x140014ae2  mov     cl, [rsp+6C0h+sz]
0x140014ae6  lea     rbx, [rsp+6C0h+sz]
0x140014aeb  test    cl, cl
0x140014aed  jz      short loc_140014B10
0x140014aef  lea     rax, [rsp+6C0h+sz]
0x140014af4  cmp     cl, 5Ch ; '\'
0x140014af7  jnz     short loc_140014B01
0x140014af9  inc     rax
0x140014afc  mov     rbx, rax
0x140014aff  jmp     short loc_140014B0A
0x140014b01  mov     rcx, rax; lpsz
0x140014b04  call    cs:__imp_CharNextA
0x140014b0a  mov     cl, [rax]
0x140014b0c  test    cl, cl
0x140014b0e  jnz     short loc_140014AF4
0x140014b10  lea     rax, [rsp+6C0h+sz]
0x140014b15  sub     rbx, rax
0x140014b18  lea     rcx, [rbp+5C0h+Source]
0x140014b1c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140014b20  mov     rax, rsi
0x140014b23  inc     rax
0x140014b26  cmp     byte ptr [rcx+rax], 0
0x140014b2a  jnz     short loc_140014B23
0x140014b2c  inc     rax
0x140014b2f  add     rax, rbx
0x140014b32  cmp     rax, rdi
0x140014b35  ja      short loc_140014B65
0x140014b37  mov     r8, rbx; Size
0x140014b3a  lea     rdx, [rsp+6C0h+sz]; Src
0x140014b3f  lea     rcx, [rbp+5C0h+LibFileName]; void *
0x140014b46  call    memcpy_0
0x140014b4b  mov     rdx, rdi
0x140014b4e  lea     rcx, [rbp+5C0h+LibFileName]
0x140014b55  sub     rdx, rbx; SizeInBytes
0x140014b58  lea     r8, [rbp+5C0h+Source]; Source
0x140014b5c  add     rcx, rbx; Destination
0x140014b5f  call    cs:__imp_strcpy_s
0x140014b65  mov     r15d, 60h ; '`'
0x140014b6b  lea     rcx, [rbp+5C0h+LibFileName]; lpLibFileName
0x140014b72  mov     r8d, r15d; dwFlags
0x140014b75  xor     edx, edx; hFile
0x140014b77  call    cs:__imp_LoadLibraryExA
0x140014b7d  mov     rbx, rax
0x140014b80  test    rax, rax
0x140014b83  jnz     loc_140014DA9
0x140014b89  mov     r8d, r15d; dwFlags
0x140014b8c  lea     rcx, [rbp+5C0h+Source]; lpLibFileName
0x140014b90  xor     edx, edx; hFile
0x140014b92  call    cs:__imp_LoadLibraryExA
0x140014b98  mov     rbx, rax
0x140014b9b  test    rax, rax
0x140014b9e  jnz     loc_140014DA9
0x140014ba4  lea     rcx, [rsp+6C0h+var_68C]
0x140014ba9  mov     rax, rsi
0x140014bac  inc     rax
0x140014baf  cmp     byte ptr [rcx+rax], 0
0x140014bb3  jnz     short loc_140014BAC
0x140014bb5  cmp     rax, 2
0x140014bb9  jbe     loc_140014CA1
0x140014bbf  lea     rax, [rsp+6C0h+var_68C]
0x140014bc4  mov     [rsp+6C0h+var_68A], 0
0x140014bc9  lea     r9, [rbp+5C0h+Buffer]
0x140014bd0  mov     [rsp+6C0h+var_6A0], rax
0x140014bd5  lea     r8, aSSDll; "%s%s.DLL"
0x140014bdc  mov     rdx, rdi; BufferCount
0x140014bdf  lea     rcx, [rbp+5C0h+Source]; Buffer
0x140014be3  call    cs:__imp_sprintf_s
0x140014be9  mov     cl, [rsp+6C0h+sz]
0x140014bed  lea     rbx, [rsp+6C0h+sz]
0x140014bf2  test    cl, cl
0x140014bf4  jz      short loc_140014C17
0x140014bf6  lea     rax, [rsp+6C0h+sz]
0x140014bfb  cmp     cl, 5Ch ; '\'
0x140014bfe  jnz     short loc_140014C08
0x140014c00  inc     rax
0x140014c03  mov     rbx, rax
0x140014c06  jmp     short loc_140014C11
0x140014c08  mov     rcx, rax; lpsz
0x140014c0b  call    cs:__imp_CharNextA
0x140014c11  mov     cl, [rax]
0x140014c13  test    cl, cl
0x140014c15  jnz     short loc_140014BFB
0x140014c17  lea     rax, [rsp+6C0h+sz]
0x140014c1c  sub     rbx, rax
0x140014c1f  lea     rcx, [rbp+5C0h+Source]
0x140014c23  mov     rax, rsi
0x140014c26  inc     rax
0x140014c29  cmp     byte ptr [rcx+rax], 0
0x140014c2d  jnz     short loc_140014C26
0x140014c2f  inc     rax
0x140014c32  add     rax, rbx
0x140014c35  cmp     rax, rdi
0x140014c38  ja      short loc_140014C68
0x140014c3a  mov     r8, rbx; Size
0x140014c3d  lea     rdx, [rsp+6C0h+sz]; Src
0x140014c42  lea     rcx, [rbp+5C0h+LibFileName]; void *
0x140014c49  call    memcpy_0
0x140014c4e  mov     rdx, rdi
0x140014c51  lea     rcx, [rbp+5C0h+LibFileName]
0x140014c58  sub     rdx, rbx; SizeInBytes
0x140014c5b  lea     r8, [rbp+5C0h+Source]; Source
0x140014c5f  add     rcx, rbx; Destination
0x140014c62  call    cs:__imp_strcpy_s
0x140014c68  mov     r8d, r15d; dwFlags
0x140014c6b  lea     rcx, [rbp+5C0h+LibFileName]; lpLibFileName
0x140014c72  xor     edx, edx; hFile
0x140014c74  call    cs:__imp_LoadLibraryExA
0x140014c7a  mov     rbx, rax
0x140014c7d  test    rax, rax
0x140014c80  jnz     loc_140014DA9
0x140014c86  mov     r8d, r15d; dwFlags
0x140014c89  lea     rcx, [rbp+5C0h+Source]; lpLibFileName
0x140014c8d  xor     edx, edx; hFile
0x140014c8f  call    cs:__imp_LoadLibraryExA
0x140014c95  mov     rbx, rax
0x140014c98  test    rax, rax
0x140014c9b  jnz     loc_140014DA9
0x140014ca1  call    cs:__imp_GetUserDefaultLCID
0x140014ca7  mov     r9d, 5; cchData
0x140014cad  lea     r8, [rsp+6C0h+var_68C]; lpLCData
0x140014cb2  and     eax, 3FFh
0x140014cb7  bts     eax, 0Ah
0x140014cbb  mov     ecx, eax; Locale
0x140014cbd  lea     edx, [r9-2]; LCType
0x140014cc1  call    cs:__imp_GetLocaleInfoA
0x140014cc7  test    eax, eax
0x140014cc9  jz      loc_140014A6F
0x140014ccf  lea     rax, [rsp+6C0h+var_68C]
0x140014cd4  mov     rdx, rdi; BufferCount
0x140014cd7  lea     r9, [rbp+5C0h+Buffer]
0x140014cde  mov     [rsp+6C0h+var_6A0], rax
0x140014ce3  lea     r8, aSSDll; "%s%s.DLL"
0x140014cea  lea     rcx, [rbp+5C0h+Source]; Buffer
0x140014cee  call    cs:__imp_sprintf_s
0x140014cf4  mov     cl, [rsp+6C0h+sz]
0x140014cf8  lea     rbx, [rsp+6C0h+sz]
0x140014cfd  test    cl, cl
0x140014cff  jz      short loc_140014D22
0x140014d01  lea     rax, [rsp+6C0h+sz]
0x140014d06  cmp     cl, 5Ch ; '\'
0x140014d09  jnz     short loc_140014D13
0x140014d0b  inc     rax
0x140014d0e  mov     rbx, rax
0x140014d11  jmp     short loc_140014D1C
0x140014d13  mov     rcx, rax; lpsz
0x140014d16  call    cs:__imp_CharNextA
0x140014d1c  mov     cl, [rax]
0x140014d1e  test    cl, cl
0x140014d20  jnz     short loc_140014D06
0x140014d22  lea     rax, [rsp+6C0h+sz]
0x140014d27  sub     rbx, rax
0x140014d2a  lea     rax, [rbp+5C0h+Source]
0x140014d2e  inc     rsi
0x140014d31  cmp     byte ptr [rax+rsi], 0
0x140014d35  jnz     short loc_140014D2E
0x140014d37  lea     rax, [rsi+1]
0x140014d3b  add     rax, rbx
0x140014d3e  cmp     rax, rdi
0x140014d41  ja      short loc_140014D71
0x140014d43  mov     r8, rbx; Size
0x140014d46  lea     rdx, [rsp+6C0h+sz]; Src
0x140014d4b  lea     rcx, [rbp+5C0h+LibFileName]; void *
0x140014d52  call    memcpy_0
0x140014d57  sub     rdi, rbx
0x140014d5a  lea     rcx, [rbp+5C0h+LibFileName]
0x140014d61  add     rcx, rbx; Destination
0x140014d64  lea     r8, [rbp+5C0h+Source]; Source
0x140014d68  mov     rdx, rdi; SizeInBytes
0x140014d6b  call    cs:__imp_strcpy_s
0x140014d71  mov     r8d, r15d; dwFlags
0x140014d74  lea     rcx, [rbp+5C0h+LibFileName]; lpLibFileName
0x140014d7b  xor     edx, edx; hFile
0x140014d7d  call    cs:__imp_LoadLibraryExA
0x140014d83  mov     rbx, rax
0x140014d86  test    rax, rax
0x140014d89  jnz     short loc_140014DA9
0x140014d8b  mov     r8d, r15d; dwFlags
0x140014d8e  lea     rcx, [rbp+5C0h+Source]; lpLibFileName
0x140014d92  xor     edx, edx; hFile
0x140014d94  call    cs:__imp_LoadLibraryExA
0x140014d9a  mov     rbx, rax
0x140014d9d  test    rax, rax
0x140014da0  jnz     short loc_140014DA9
0x140014da2  mov     rbx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140014da9  mov     rax, rbx
0x140014dac  jmp     short loc_140014DB5
0x140014dae  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x140014db5  mov     rcx, [rbp+5C0h+var_30]
0x140014dbc  xor     rcx, rsp; StackCookie
0x140014dbf  call    __security_check_cookie
0x140014dc4  add     rsp, 6A0h
0x140014dcb  pop     r15
0x140014dcd  pop     rdi
0x140014dce  pop     rsi
0x140014dcf  pop     rbx
0x140014dd0  pop     rbp
0x140014dd1  retn
```
