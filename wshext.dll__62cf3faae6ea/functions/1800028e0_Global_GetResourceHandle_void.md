# Global::GetResourceHandle(void)

- ea: `0x1800028e0`
- end: `0x180002d5f`
- name: `?GetResourceHandle@Global@@CAPEAUHINSTANCE__@@XZ`
- size: `1151`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002810`

## callees

- `0x1800028e0`
- `0x180005900`
- `0x18000b1c0`
- `0x18000d172`
- `0x18000d1c0`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180002aec`
- `msvcrt!strcpy_s` at `0x180002beb`
- `msvcrt!strcpy_s` at `0x180002d0d`
- `msvcrt!strcpy_s` at `0x180002aec`
- `msvcrt!strcpy_s` at `0x180002beb`
- `msvcrt!strcpy_s` at `0x180002d0d`
- `msvcrt!sprintf_s` at `0x180002b6a`
- `msvcrt!sprintf_s` at `0x180002c72`
- `msvcrt!sprintf_s` at `0x180002b6a`
- `msvcrt!sprintf_s` at `0x180002c72`
- `USER32!LoadStringA` at `0x180002a24`
- `USER32!LoadStringA` at `0x180002a24`
- `USER32!CharNextA` at `0x180002a8d`
- `USER32!CharNextA` at `0x180002b93`
- `USER32!CharNextA` at `0x180002cb5`
- `USER32!CharNextA` at `0x180002a8d`
- `USER32!CharNextA` at `0x180002b93`
- `USER32!CharNextA` at `0x180002cb5`
- `KERNEL32!GetUserDefaultLCID` at `0x18000291b`
- `KERNEL32!GetUserDefaultLCID` at `0x180002c2a`
- `KERNEL32!GetUserDefaultLCID` at `0x18000291b`
- `KERNEL32!GetUserDefaultLCID` at `0x180002c2a`
- `KERNEL32!GetLocaleInfoA` at `0x1800029fb`
- `KERNEL32!GetLocaleInfoA` at `0x180002c49`
- `KERNEL32!GetLocaleInfoA` at `0x1800029fb`
- `KERNEL32!GetLocaleInfoA` at `0x180002c49`
- `KERNEL32!GetLocaleInfoW` at `0x18000293d`
- `KERNEL32!GetLocaleInfoW` at `0x18000293d`
- `KERNEL32!GetModuleFileNameA` at `0x180002a64`
- `KERNEL32!GetModuleFileNameA` at `0x180002a64`
- `KERNEL32!LoadLibraryExA` at `0x180002b01`
- `KERNEL32!LoadLibraryExA` at `0x180002b1c`
- `KERNEL32!LoadLibraryExA` at `0x180002c00`
- `KERNEL32!LoadLibraryExA` at `0x180002c1b`
- `KERNEL32!LoadLibraryExA` at `0x180002d22`
- `KERNEL32!LoadLibraryExA` at `0x180002d39`
- `KERNEL32!LoadLibraryExA` at `0x180002b01`
- `KERNEL32!LoadLibraryExA` at `0x180002b1c`
- `KERNEL32!LoadLibraryExA` at `0x180002c00`
- `KERNEL32!LoadLibraryExA` at `0x180002c1b`
- `KERNEL32!LoadLibraryExA` at `0x180002d22`
- `KERNEL32!LoadLibraryExA` at `0x180002d39`
- `KERNEL32!FreeLibrary` at `0x180002991`
- `KERNEL32!FreeLibrary` at `0x180002991`

## string_xrefs

- `0x180002a45`: `%s%s.DLL`
- `0x180002b5c`: `%s%s.DLL`
- `0x180002c67`: `%s%s.DLL`

## pseudocode

```c
HINSTANCE Global::GetResourceHandle(void)
{
  HINSTANCE result; // rax
  LCID UserDefaultLCID; // eax
  unsigned int v2; // ebx
  CHAR v3; // cl
  CHAR *v4; // rbx
  CHAR *v5; // rax
  __int64 v6; // rsi
  size_t v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  CHAR v10; // cl
  CHAR *v11; // rbx
  CHAR *v12; // rax
  size_t v13; // rbx
  __int64 v14; // rax
  __int16 v15; // ax
  CHAR v16; // cl
  CHAR *v17; // rbx
  CHAR *v18; // rax
  size_t v19; // rbx
  int LCData; // [rsp+38h] [rbp-D0h] BYREF
  CHAR v22[4]; // [rsp+3Ch] [rbp-CCh] BYREF
  CHAR Filename[272]; // [rsp+48h] [rbp-C0h] BYREF
  CHAR Source[272]; // [rsp+158h] [rbp+50h] BYREF
  CHAR LibFileName[272]; // [rsp+268h] [rbp+160h] BYREF
  CHAR Buffer[272]; // [rsp+378h] [rbp+270h] BYREF

  result = Global::g_hResource;
  if ( Global::g_hResource )
    return result;
  UserDefaultLCID = GetUserDefaultLCID();
  LCData = 0;
  v2 = UserDefaultLCID;
  if ( GetLocaleInfoW(UserDefaultLCID, 0x20000070u, (LPWSTR)&LCData, 2) && LCData == 1 )
  {
    if ( Global::g_lResourceBase == 2000 )
      return Global::g_hInstance;
    Global::g_isLanguageBiDi = 1;
  }
  if ( Global::g_fWindowsVista || (v2 & 0x3FF) == 9 )
    return Global::g_hInstance;
  result = LoadMUI((HINSTANCE)9, v2);
  if ( result == Global::g_hInstance )
  {
    FreeLibrary(result);
  }
  else if ( result )
  {
    return result;
  }
  if ( !GetLocaleInfoA(v2, 3u, v22, 5) || !LoadStringA(Global::g_hInstance, 0x3E9u, Buffer, 260) )
  {
LABEL_47:
    result = Global::g_hInstance;
    if ( Global::g_hResource )
      return Global::g_hResource;
    return result;
  }
  StringCchPrintfA(Source, 0x104u, "%s%s.DLL", Buffer, v22);
  GetModuleFileNameA(Global::g_hInstance, Filename, 0x104u);
  v3 = Filename[0];
  v4 = Filename;
  if ( Filename[0] )
  {
    v5 = Filename;
    do
    {
      if ( v3 == 92 )
        v4 = ++v5;
      else
        v5 = CharNextA(v5);
      v3 = *v5;
    }
    while ( *v5 );
  }
  v6 = -1;
  v7 = v4 - Filename;
  v8 = -1;
  do
    ++v8;
  while ( Source[v8] );
  if ( v7 + v8 + 1 <= 0x104 )
  {
    memcpy_0(LibFileName, Filename, v7);
    strcpy_s(&LibFileName[v7], 260 - v7, Source);
  }
  result = LoadLibraryExA(LibFileName, 0, 0x60u);
  if ( !result )
  {
    result = LoadLibraryExA(Source, 0, 0x60u);
    if ( !result )
    {
      v9 = -1;
      do
        ++v9;
      while ( v22[v9] );
      if ( v9 <= 2 )
        goto LABEL_42;
      v22[2] = 0;
      sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v22);
      v10 = Filename[0];
      v11 = Filename;
      if ( Filename[0] )
      {
        v12 = Filename;
        do
        {
          if ( v10 == 92 )
            v11 = ++v12;
          else
            v12 = CharNextA(v12);
          v10 = *v12;
        }
        while ( *v12 );
      }
      v13 = v11 - Filename;
      v14 = -1;
      do
        ++v14;
      while ( Source[v14] );
      if ( v13 + v14 + 1 <= 0x104 )
      {
        memcpy_0(LibFileName, Filename, v13);
        strcpy_s(&LibFileName[v13], 260 - v13, Source);
      }
      result = LoadLibraryExA(LibFileName, 0, 0x60u);
      if ( !result )
      {
        result = LoadLibraryExA(Source, 0, 0x60u);
        if ( !result )
        {
LABEL_42:
          v15 = GetUserDefaultLCID();
          if ( GetLocaleInfoA(v15 & 0x3FF | 0x400, 3u, v22, 5) )
          {
            sprintf_s(Source, 0x104u, "%s%s.DLL", Buffer, v22);
            v16 = Filename[0];
            v17 = Filename;
            if ( Filename[0] )
            {
              v18 = Filename;
              do
              {
                if ( v16 == 92 )
                  v17 = ++v18;
                else
                  v18 = CharNextA(v18);
                v16 = *v18;
              }
              while ( *v18 );
            }
            v19 = v17 - Filename;
            while ( Source[++v6] != 0 )
              ;
            if ( v19 + v6 + 1 <= 0x104 )
            {
              memcpy_0(LibFileName, Filename, v19);
              strcpy_s(&LibFileName[v19], 260 - v19, Source);
            }
            result = LoadLibraryExA(LibFileName, 0, 0x60u);
            if ( !result )
            {
              result = LoadLibraryExA(Source, 0, 0x60u);
              if ( !result )
                return Global::g_hInstance;
            }
            return result;
          }
          goto LABEL_47;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800028e0  mov     r11, rsp
0x1800028e3  push    rbp
0x1800028e4  lea     rbp, [r11-398h]
0x1800028eb  sub     rsp, 490h
0x1800028f2  mov     rax, cs:__security_cookie
0x1800028f9  xor     rax, rsp
0x1800028fc  mov     [rbp+390h+var_10], rax
0x180002903  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x18000290a  test    rax, rax
0x18000290d  jnz     loc_1800029BC
0x180002913  mov     [r11+8], rbx
0x180002917  mov     [r11+20h], r14
0x18000291b  call    cs:__imp_GetUserDefaultLCID
0x180002921  mov     r9d, 2; cchData
0x180002927  mov     [rsp+490h+LCData], 0
0x18000292f  mov     ecx, eax; Locale
0x180002931  lea     r8, [rsp+490h+LCData]; lpLCData
0x180002936  mov     edx, 20000070h; LCType
0x18000293b  mov     ebx, eax
0x18000293d  call    cs:__imp_GetLocaleInfoW
0x180002943  test    eax, eax
0x180002945  jz      short loc_18000294E
0x180002947  cmp     [rsp+490h+LCData], 1
0x18000294c  jz      short loc_180002999
0x18000294e  cmp     cs:?g_fWindowsVista@Global@@2_NA, 0; bool Global::g_fWindowsVista
0x180002955  jnz     short loc_1800029A5
0x180002957  movzx   eax, bx
0x18000295a  mov     r14d, 3FFh
0x180002960  and     ax, r14w
0x180002964  mov     ecx, 9; HINSTANCE
0x180002969  cmp     cx, ax
0x18000296c  jz      short loc_1800029A5
0x18000296e  mov     [rsp+490h+arg_8], rsi
0x180002976  mov     edx, ebx; unsigned int
0x180002978  mov     [rsp+490h+arg_10], rdi
0x180002980  call    ?LoadMUI@@YAPEAUHINSTANCE__@@PEAU1@K@Z; LoadMUI(HINSTANCE__ *,ulong)
0x180002985  cmp     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x18000298c  jnz     short loc_1800029E0
0x18000298e  mov     rcx, rax; hLibModule
0x180002991  call    cs:__imp_FreeLibrary
0x180002997  jmp     short loc_1800029E9
0x180002999  cmp     cs:?g_lResourceBase@Global@@2JA, 7D0h; long Global::g_lResourceBase
0x1800029a3  jnz     short loc_1800029D4
0x1800029a5  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x1800029ac  mov     rbx, [rsp+490h+arg_0]
0x1800029b4  mov     r14, [rsp+490h+arg_18]
0x1800029bc  mov     rcx, [rbp+390h+var_10]
0x1800029c3  xor     rcx, rsp; StackCookie
0x1800029c6  call    __security_check_cookie
0x1800029cb  add     rsp, 490h
0x1800029d2  pop     rbp
0x1800029d3  retn
0x1800029d4  mov     cs:?g_isLanguageBiDi@Global@@2_NA, 1; bool Global::g_isLanguageBiDi
0x1800029db  jmp     loc_18000294E
0x1800029e0  test    rax, rax
0x1800029e3  jnz     loc_180002D4A
0x1800029e9  mov     r9d, 5; cchData
0x1800029ef  lea     r8, [rsp+490h+var_45C]; lpLCData
0x1800029f4  mov     edx, 3; LCType
0x1800029f9  mov     ecx, ebx; Locale
0x1800029fb  call    cs:__imp_GetLocaleInfoA
0x180002a01  test    eax, eax
0x180002a03  jz      loc_180002C98
0x180002a09  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180002a10  lea     r8, [rbp+390h+Buffer]; lpBuffer
0x180002a17  mov     edi, 104h
0x180002a1c  mov     edx, 3E9h; uID
0x180002a21  mov     r9d, edi; cchBufferMax
0x180002a24  call    cs:__imp_LoadStringA
0x180002a2a  test    eax, eax
0x180002a2c  jz      loc_180002C98
0x180002a32  lea     rax, [rsp+490h+var_45C]
0x180002a37  mov     edx, edi; unsigned __int64
0x180002a39  lea     r9, [rbp+390h+Buffer]
0x180002a40  mov     [rsp+20h], rax
0x180002a45  lea     r8, Format; "%s%s.DLL"
0x180002a4c  lea     rcx, [rbp+390h+Source]; char *
0x180002a50  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002a55  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x180002a5c  lea     rdx, [rsp+490h+Filename]; lpFilename
0x180002a61  mov     r8d, edi; nSize
0x180002a64  call    cs:__imp_GetModuleFileNameA
0x180002a6a  movzx   ecx, [rsp+490h+Filename]
0x180002a6f  lea     rbx, [rsp+490h+Filename]
0x180002a74  test    cl, cl
0x180002a76  jz      short loc_180002A9A
0x180002a78  lea     rax, [rsp+490h+Filename]
0x180002a7d  cmp     cl, 5Ch ; '\'
0x180002a80  jnz     short loc_180002A8A
0x180002a82  inc     rax
0x180002a85  mov     rbx, rax
0x180002a88  jmp     short loc_180002A93
0x180002a8a  mov     rcx, rax; lpsz
0x180002a8d  call    cs:__imp_CharNextA
0x180002a93  movzx   ecx, byte ptr [rax]
0x180002a96  test    cl, cl
0x180002a98  jnz     short loc_180002A7D
0x180002a9a  lea     rax, [rsp+490h+Filename]
0x180002a9f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002aa6  sub     rbx, rax
0x180002aa9  lea     rcx, [rbp+390h+Source]
0x180002aad  mov     rax, rsi
0x180002ab0  inc     rax
0x180002ab3  cmp     byte ptr [rcx+rax], 0
0x180002ab7  jnz     short loc_180002AB0
0x180002ab9  inc     rax
0x180002abc  add     rax, rbx
0x180002abf  cmp     rax, rdi
0x180002ac2  ja      short loc_180002AF2
0x180002ac4  mov     r8, rbx; Size
0x180002ac7  lea     rdx, [rsp+490h+Filename]; Src
0x180002acc  lea     rcx, [rbp+390h+LibFileName]; void *
0x180002ad3  call    memcpy_0
0x180002ad8  mov     rdx, rdi
0x180002adb  lea     rcx, [rbp+390h+LibFileName]
0x180002ae2  sub     rdx, rbx; SizeInBytes
0x180002ae5  lea     r8, [rbp+390h+Source]; Source
0x180002ae9  add     rcx, rbx; Destination
0x180002aec  call    cs:__imp_strcpy_s
0x180002af2  xor     edx, edx; hFile
0x180002af4  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180002afb  mov     r8d, 60h ; '`'; dwFlags
0x180002b01  call    cs:__imp_LoadLibraryExA
0x180002b07  test    rax, rax
0x180002b0a  jnz     loc_180002D4A
0x180002b10  xor     edx, edx; hFile
0x180002b12  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180002b16  mov     r8d, 60h ; '`'; dwFlags
0x180002b1c  call    cs:__imp_LoadLibraryExA
0x180002b22  test    rax, rax
0x180002b25  jnz     loc_180002D4A
0x180002b2b  lea     rcx, [rsp+490h+var_45C]
0x180002b30  mov     rax, rsi
0x180002b33  inc     rax
0x180002b36  cmp     byte ptr [rcx+rax], 0
0x180002b3a  jnz     short loc_180002B33
0x180002b3c  cmp     rax, 2
0x180002b40  jbe     loc_180002C2A
0x180002b46  lea     rax, [rsp+490h+var_45C]
0x180002b4b  mov     [rsp+490h+var_45C+2], 0
0x180002b50  lea     r9, [rbp+390h+Buffer]
0x180002b57  mov     [rsp+20h], rax
0x180002b5c  lea     r8, Format; "%s%s.DLL"
0x180002b63  mov     rdx, rdi; BufferCount
0x180002b66  lea     rcx, [rbp+390h+Source]; Buffer
0x180002b6a  call    cs:__imp_sprintf_s
0x180002b70  movzx   ecx, [rsp+490h+Filename]
0x180002b75  lea     rbx, [rsp+490h+Filename]
0x180002b7a  test    cl, cl
0x180002b7c  jz      short loc_180002BA0
0x180002b7e  lea     rax, [rsp+490h+Filename]
0x180002b83  cmp     cl, 5Ch ; '\'
0x180002b86  jnz     short loc_180002B90
0x180002b88  inc     rax
0x180002b8b  mov     rbx, rax
0x180002b8e  jmp     short loc_180002B99
0x180002b90  mov     rcx, rax; lpsz
0x180002b93  call    cs:__imp_CharNextA
0x180002b99  movzx   ecx, byte ptr [rax]
0x180002b9c  test    cl, cl
0x180002b9e  jnz     short loc_180002B83
0x180002ba0  lea     rax, [rsp+490h+Filename]
0x180002ba5  sub     rbx, rax
0x180002ba8  lea     rcx, [rbp+390h+Source]
0x180002bac  mov     rax, rsi
0x180002baf  inc     rax
0x180002bb2  cmp     byte ptr [rcx+rax], 0
0x180002bb6  jnz     short loc_180002BAF
0x180002bb8  inc     rax
0x180002bbb  add     rax, rbx
0x180002bbe  cmp     rax, rdi
0x180002bc1  ja      short loc_180002BF1
0x180002bc3  mov     r8, rbx; Size
0x180002bc6  lea     rdx, [rsp+490h+Filename]; Src
0x180002bcb  lea     rcx, [rbp+390h+LibFileName]; void *
0x180002bd2  call    memcpy_0
0x180002bd7  mov     rdx, rdi
0x180002bda  lea     rcx, [rbp+390h+LibFileName]
0x180002be1  sub     rdx, rbx; SizeInBytes
0x180002be4  lea     r8, [rbp+390h+Source]; Source
0x180002be8  add     rcx, rbx; Destination
0x180002beb  call    cs:__imp_strcpy_s
0x180002bf1  xor     edx, edx; hFile
0x180002bf3  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180002bfa  mov     r8d, 60h ; '`'; dwFlags
0x180002c00  call    cs:__imp_LoadLibraryExA
0x180002c06  test    rax, rax
0x180002c09  jnz     loc_180002D4A
0x180002c0f  xor     edx, edx; hFile
0x180002c11  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180002c15  mov     r8d, 60h ; '`'; dwFlags
0x180002c1b  call    cs:__imp_LoadLibraryExA
0x180002c21  test    rax, rax
0x180002c24  jnz     loc_180002D4A
0x180002c2a  call    cs:__imp_GetUserDefaultLCID
0x180002c30  mov     r9d, 5; cchData
0x180002c36  lea     r8, [rsp+490h+var_45C]; lpLCData
0x180002c3b  and     eax, r14d
0x180002c3e  mov     edx, 3; LCType
0x180002c43  bts     eax, 0Ah
0x180002c47  mov     ecx, eax; Locale
0x180002c49  call    cs:__imp_GetLocaleInfoA
0x180002c4f  test    eax, eax
0x180002c51  jz      short loc_180002C98
0x180002c53  lea     rax, [rsp+490h+var_45C]
0x180002c58  mov     rdx, rdi; BufferCount
0x180002c5b  lea     r9, [rbp+390h+Buffer]
0x180002c62  mov     [rsp+20h], rax
0x180002c67  lea     r8, Format; "%s%s.DLL"
0x180002c6e  lea     rcx, [rbp+390h+Source]; Buffer
0x180002c72  call    cs:__imp_sprintf_s
0x180002c78  movzx   ecx, [rsp+490h+Filename]
0x180002c7d  lea     rbx, [rsp+490h+Filename]
0x180002c82  test    cl, cl
0x180002c84  jz      short loc_180002CC2
0x180002c86  lea     rax, [rsp+490h+Filename]
0x180002c8b  cmp     cl, 5Ch ; '\'
0x180002c8e  jnz     short loc_180002CB2
0x180002c90  inc     rax
0x180002c93  mov     rbx, rax
0x180002c96  jmp     short loc_180002CBB
0x180002c98  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180002c9f  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x180002ca6  test    rcx, rcx
0x180002ca9  cmovnz  rax, rcx
0x180002cad  jmp     loc_180002D4A
0x180002cb2  mov     rcx, rax; lpsz
0x180002cb5  call    cs:__imp_CharNextA
0x180002cbb  movzx   ecx, byte ptr [rax]
0x180002cbe  test    cl, cl
0x180002cc0  jnz     short loc_180002C8B
0x180002cc2  lea     rax, [rsp+490h+Filename]
0x180002cc7  sub     rbx, rax
0x180002cca  lea     rax, [rbp+390h+Source]
0x180002cce  cmp     byte ptr [rax+rsi+1], 0
0x180002cd3  lea     rsi, [rsi+1]
0x180002cd7  jnz     short loc_180002CCE
0x180002cd9  lea     rax, [rsi+1]
0x180002cdd  add     rax, rbx
0x180002ce0  cmp     rax, rdi
0x180002ce3  ja      short loc_180002D13
0x180002ce5  mov     r8, rbx; Size
0x180002ce8  lea     rdx, [rsp+490h+Filename]; Src
0x180002ced  lea     rcx, [rbp+390h+LibFileName]; void *
0x180002cf4  call    memcpy_0
0x180002cf9  sub     rdi, rbx
0x180002cfc  lea     rcx, [rbp+390h+LibFileName]
0x180002d03  add     rcx, rbx; Destination
0x180002d06  lea     r8, [rbp+390h+Source]; Source
0x180002d0a  mov     rdx, rdi; SizeInBytes
0x180002d0d  call    cs:__imp_strcpy_s
0x180002d13  xor     edx, edx; hFile
0x180002d15  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180002d1c  mov     r8d, 60h ; '`'; dwFlags
0x180002d22  call    cs:__imp_LoadLibraryExA
0x180002d28  test    rax, rax
0x180002d2b  jnz     short loc_180002D4A
0x180002d2d  xor     edx, edx; hFile
0x180002d2f  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180002d33  mov     r8d, 60h ; '`'; dwFlags
0x180002d39  call    cs:__imp_LoadLibraryExA
0x180002d3f  test    rax, rax
0x180002d42  cmovz   rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x180002d4a  mov     rdi, [rsp+490h+arg_10]
0x180002d52  mov     rsi, [rsp+490h+arg_8]
0x180002d5a  jmp     loc_1800029AC
```
