# Global::GetResourceHandle(void)

- ea: `0x180002d10`
- end: `0x18000318b`
- name: `?GetResourceHandle@Global@@CAPEAUHINSTANCE__@@XZ`
- size: `1147`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180002c48`

## callees

- `0x180002d10`
- `0x18000e79c`
- `0x18000f020`
- `0x180010206`
- `0x180010250`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180002f6b`
- `msvcrt!sprintf_s` at `0x1800030b8`
- `msvcrt!sprintf_s` at `0x180002f6b`
- `msvcrt!sprintf_s` at `0x1800030b8`
- `msvcrt!strcpy_s` at `0x180002eed`
- `msvcrt!strcpy_s` at `0x180002fec`
- `msvcrt!strcpy_s` at `0x180003139`
- `msvcrt!strcpy_s` at `0x180002eed`
- `msvcrt!strcpy_s` at `0x180002fec`
- `msvcrt!strcpy_s` at `0x180003139`
- `KERNEL32!GetLocaleInfoA` at `0x180002dfc`
- `KERNEL32!GetLocaleInfoA` at `0x180003042`
- `KERNEL32!GetLocaleInfoA` at `0x180002dfc`
- `KERNEL32!GetLocaleInfoA` at `0x180003042`
- `KERNEL32!GetLocaleInfoW` at `0x180002d6d`
- `KERNEL32!GetLocaleInfoW` at `0x180002d6d`
- `KERNEL32!LoadLibraryExA` at `0x180002f02`
- `KERNEL32!LoadLibraryExA` at `0x180002f1d`
- `KERNEL32!LoadLibraryExA` at `0x180003001`
- `KERNEL32!LoadLibraryExA` at `0x180003018`
- `KERNEL32!LoadLibraryExA` at `0x18000314e`
- `KERNEL32!LoadLibraryExA` at `0x180003169`
- `KERNEL32!LoadLibraryExA` at `0x180002f02`
- `KERNEL32!LoadLibraryExA` at `0x180002f1d`
- `KERNEL32!LoadLibraryExA` at `0x180003001`
- `KERNEL32!LoadLibraryExA` at `0x180003018`
- `KERNEL32!LoadLibraryExA` at `0x18000314e`
- `KERNEL32!LoadLibraryExA` at `0x180003169`
- `KERNEL32!FreeLibrary` at `0x180002dd9`
- `KERNEL32!FreeLibrary` at `0x180002dd9`
- `KERNEL32!GetUserDefaultLCID` at `0x180002d4b`
- `KERNEL32!GetUserDefaultLCID` at `0x180003023`
- `KERNEL32!GetUserDefaultLCID` at `0x180002d4b`
- `KERNEL32!GetUserDefaultLCID` at `0x180003023`
- `KERNEL32!GetModuleFileNameA` at `0x180002e65`
- `KERNEL32!GetModuleFileNameA` at `0x180002e65`
- `USER32!CharNextA` at `0x180002e8e`
- `USER32!CharNextA` at `0x180002f94`
- `USER32!CharNextA` at `0x1800030e1`
- `USER32!CharNextA` at `0x180002e8e`
- `USER32!CharNextA` at `0x180002f94`
- `USER32!CharNextA` at `0x1800030e1`
- `USER32!LoadStringA` at `0x180002e25`
- `USER32!LoadStringA` at `0x180002e25`

## string_xrefs

- `0x180002e46`: `%s%s.DLL`
- `0x180002f5d`: `%s%s.DLL`
- `0x1800030ad`: `%s%s.DLL`

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
  if ( !Global::g_hResource )
  {
    UserDefaultLCID = GetUserDefaultLCID();
    LCData = 0;
    v2 = UserDefaultLCID;
    if ( GetLocaleInfoW(UserDefaultLCID, 0x20000070u, (LPWSTR)&LCData, 2)
      && LCData == 1
      && Global::g_lResourceBase == 2000
      || Global::g_fWindowsVista
      || (v2 & 0x3FF) == 9 )
    {
      return Global::g_hInstance;
    }
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
      goto LABEL_40;
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
          goto LABEL_39;
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
LABEL_39:
            v15 = GetUserDefaultLCID();
            if ( !GetLocaleInfoA(v15 & 0x3FF | 0x400, 3u, v22, 5) )
            {
LABEL_40:
              result = Global::g_hInstance;
              if ( Global::g_hResource )
                return Global::g_hResource;
              return result;
            }
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
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d10  mov     r11, rsp
0x180002d13  push    rbp
0x180002d14  lea     rbp, [r11-398h]
0x180002d1b  sub     rsp, 490h
0x180002d22  mov     rax, cs:__security_cookie
0x180002d29  xor     rax, rsp
0x180002d2c  mov     [rbp+390h+var_10], rax
0x180002d33  mov     rax, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180002d3a  test    rax, rax
0x180002d3d  jnz     loc_180003081
0x180002d43  mov     [r11+8], rbx
0x180002d47  mov     [r11+20h], r14
0x180002d4b  call    cs:__imp_GetUserDefaultLCID
0x180002d51  mov     r9d, 2; cchData
0x180002d57  mov     [rsp+490h+LCData], 0
0x180002d5f  mov     ecx, eax; Locale
0x180002d61  lea     r8, [rsp+490h+LCData]; lpLCData
0x180002d66  mov     edx, 20000070h; LCType
0x180002d6b  mov     ebx, eax
0x180002d6d  call    cs:__imp_GetLocaleInfoW
0x180002d73  test    eax, eax
0x180002d75  jz      short loc_180002D8E
0x180002d77  cmp     [rsp+490h+LCData], 1
0x180002d7c  jnz     short loc_180002D8E
0x180002d7e  cmp     cs:?g_lResourceBase@Global@@2JA, 7D0h; long Global::g_lResourceBase
0x180002d88  jz      loc_18000317F
0x180002d8e  cmp     cs:?g_fWindowsVista@Global@@2_NA, 0; bool Global::g_fWindowsVista
0x180002d95  jnz     loc_18000317F
0x180002d9b  movzx   eax, bx
0x180002d9e  mov     r14d, 3FFh
0x180002da4  and     ax, r14w
0x180002da8  mov     ecx, 9; HINSTANCE
0x180002dad  cmp     cx, ax
0x180002db0  jz      loc_18000317F
0x180002db6  mov     [rsp+490h+arg_8], rsi
0x180002dbe  mov     edx, ebx; unsigned int
0x180002dc0  mov     [rsp+490h+arg_10], rdi
0x180002dc8  call    ?LoadMUI@@YAPEAUHINSTANCE__@@PEAU1@K@Z; LoadMUI(HINSTANCE__ *,ulong)
0x180002dcd  cmp     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x180002dd4  jnz     short loc_180002DE1
0x180002dd6  mov     rcx, rax; hLibModule
0x180002dd9  call    cs:__imp_FreeLibrary
0x180002ddf  jmp     short loc_180002DEA
0x180002de1  test    rax, rax
0x180002de4  jnz     loc_180003061
0x180002dea  mov     r9d, 5; cchData
0x180002df0  lea     r8, [rsp+490h+var_45C]; lpLCData
0x180002df5  mov     edx, 3; LCType
0x180002dfa  mov     ecx, ebx; Locale
0x180002dfc  call    cs:__imp_GetLocaleInfoA
0x180002e02  test    eax, eax
0x180002e04  jz      loc_18000304C
0x180002e0a  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hInstance
0x180002e11  lea     r8, [rbp+390h+Buffer]; lpBuffer
0x180002e18  mov     edi, 104h
0x180002e1d  mov     edx, 3E9h; uID
0x180002e22  mov     r9d, edi; cchBufferMax
0x180002e25  call    cs:__imp_LoadStringA
0x180002e2b  test    eax, eax
0x180002e2d  jz      loc_18000304C
0x180002e33  lea     rax, [rsp+490h+var_45C]
0x180002e38  mov     edx, edi; unsigned __int64
0x180002e3a  lea     r9, [rbp+390h+Buffer]
0x180002e41  mov     [rsp+20h], rax
0x180002e46  lea     r8, Format; "%s%s.DLL"
0x180002e4d  lea     rcx, [rbp+390h+Source]; char *
0x180002e51  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002e56  mov     rcx, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; hModule
0x180002e5d  lea     rdx, [rsp+490h+Filename]; lpFilename
0x180002e62  mov     r8d, edi; nSize
0x180002e65  call    cs:__imp_GetModuleFileNameA
0x180002e6b  movzx   ecx, [rsp+490h+Filename]
0x180002e70  lea     rbx, [rsp+490h+Filename]
0x180002e75  test    cl, cl
0x180002e77  jz      short loc_180002E9B
0x180002e79  lea     rax, [rsp+490h+Filename]
0x180002e7e  cmp     cl, 5Ch ; '\'
0x180002e81  jnz     short loc_180002E8B
0x180002e83  inc     rax
0x180002e86  mov     rbx, rax
0x180002e89  jmp     short loc_180002E94
0x180002e8b  mov     rcx, rax; lpsz
0x180002e8e  call    cs:__imp_CharNextA
0x180002e94  movzx   ecx, byte ptr [rax]
0x180002e97  test    cl, cl
0x180002e99  jnz     short loc_180002E7E
0x180002e9b  lea     rax, [rsp+490h+Filename]
0x180002ea0  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180002ea7  sub     rbx, rax
0x180002eaa  lea     rcx, [rbp+390h+Source]
0x180002eae  mov     rax, rsi
0x180002eb1  inc     rax
0x180002eb4  cmp     byte ptr [rcx+rax], 0
0x180002eb8  jnz     short loc_180002EB1
0x180002eba  inc     rax
0x180002ebd  add     rax, rbx
0x180002ec0  cmp     rax, rdi
0x180002ec3  ja      short loc_180002EF3
0x180002ec5  mov     r8, rbx; Size
0x180002ec8  lea     rdx, [rsp+490h+Filename]; Src
0x180002ecd  lea     rcx, [rbp+390h+LibFileName]; void *
0x180002ed4  call    memcpy_0
0x180002ed9  mov     rdx, rdi
0x180002edc  lea     rcx, [rbp+390h+LibFileName]
0x180002ee3  sub     rdx, rbx; SizeInBytes
0x180002ee6  lea     r8, [rbp+390h+Source]; Source
0x180002eea  add     rcx, rbx; Destination
0x180002eed  call    cs:__imp_strcpy_s
0x180002ef3  xor     edx, edx; hFile
0x180002ef5  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180002efc  mov     r8d, 60h ; '`'; dwFlags
0x180002f02  call    cs:__imp_LoadLibraryExA
0x180002f08  test    rax, rax
0x180002f0b  jnz     loc_180003061
0x180002f11  xor     edx, edx; hFile
0x180002f13  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180002f17  mov     r8d, 60h ; '`'; dwFlags
0x180002f1d  call    cs:__imp_LoadLibraryExA
0x180002f23  test    rax, rax
0x180002f26  jnz     loc_180003061
0x180002f2c  lea     rcx, [rsp+490h+var_45C]
0x180002f31  mov     rax, rsi
0x180002f34  inc     rax
0x180002f37  cmp     byte ptr [rcx+rax], 0
0x180002f3b  jnz     short loc_180002F34
0x180002f3d  cmp     rax, 2
0x180002f41  jbe     loc_180003023
0x180002f47  lea     rax, [rsp+490h+var_45C]
0x180002f4c  mov     [rsp+490h+var_45C+2], 0
0x180002f51  lea     r9, [rbp+390h+Buffer]
0x180002f58  mov     [rsp+20h], rax
0x180002f5d  lea     r8, Format; "%s%s.DLL"
0x180002f64  mov     rdx, rdi; BufferCount
0x180002f67  lea     rcx, [rbp+390h+Source]; Buffer
0x180002f6b  call    cs:__imp_sprintf_s
0x180002f71  movzx   ecx, [rsp+490h+Filename]
0x180002f76  lea     rbx, [rsp+490h+Filename]
0x180002f7b  test    cl, cl
0x180002f7d  jz      short loc_180002FA1
0x180002f7f  lea     rax, [rsp+490h+Filename]
0x180002f84  cmp     cl, 5Ch ; '\'
0x180002f87  jnz     short loc_180002F91
0x180002f89  inc     rax
0x180002f8c  mov     rbx, rax
0x180002f8f  jmp     short loc_180002F9A
0x180002f91  mov     rcx, rax; lpsz
0x180002f94  call    cs:__imp_CharNextA
0x180002f9a  movzx   ecx, byte ptr [rax]
0x180002f9d  test    cl, cl
0x180002f9f  jnz     short loc_180002F84
0x180002fa1  lea     rax, [rsp+490h+Filename]
0x180002fa6  sub     rbx, rax
0x180002fa9  lea     rcx, [rbp+390h+Source]
0x180002fad  mov     rax, rsi
0x180002fb0  inc     rax
0x180002fb3  cmp     byte ptr [rcx+rax], 0
0x180002fb7  jnz     short loc_180002FB0
0x180002fb9  inc     rax
0x180002fbc  add     rax, rbx
0x180002fbf  cmp     rax, rdi
0x180002fc2  ja      short loc_180002FF2
0x180002fc4  mov     r8, rbx; Size
0x180002fc7  lea     rdx, [rsp+490h+Filename]; Src
0x180002fcc  lea     rcx, [rbp+390h+LibFileName]; void *
0x180002fd3  call    memcpy_0
0x180002fd8  mov     rdx, rdi
0x180002fdb  lea     rcx, [rbp+390h+LibFileName]
0x180002fe2  sub     rdx, rbx; SizeInBytes
0x180002fe5  lea     r8, [rbp+390h+Source]; Source
0x180002fe9  add     rcx, rbx; Destination
0x180002fec  call    cs:__imp_strcpy_s
0x180002ff2  xor     edx, edx; hFile
0x180002ff4  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180002ffb  mov     r8d, 60h ; '`'; dwFlags
0x180003001  call    cs:__imp_LoadLibraryExA
0x180003007  test    rax, rax
0x18000300a  jnz     short loc_180003061
0x18000300c  xor     edx, edx; hFile
0x18000300e  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180003012  mov     r8d, 60h ; '`'; dwFlags
0x180003018  call    cs:__imp_LoadLibraryExA
0x18000301e  test    rax, rax
0x180003021  jnz     short loc_180003061
0x180003023  call    cs:__imp_GetUserDefaultLCID
0x180003029  mov     r9d, 5; cchData
0x18000302f  lea     r8, [rsp+490h+var_45C]; lpLCData
0x180003034  and     eax, r14d
0x180003037  mov     edx, 3; LCType
0x18000303c  bts     eax, 0Ah
0x180003040  mov     ecx, eax; Locale
0x180003042  call    cs:__imp_GetLocaleInfoA
0x180003048  test    eax, eax
0x18000304a  jnz     short loc_180003099
0x18000304c  mov     rcx, cs:?g_hResource@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hResource
0x180003053  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x18000305a  test    rcx, rcx
0x18000305d  cmovnz  rax, rcx
0x180003061  mov     rdi, [rsp+490h+arg_10]
0x180003069  mov     rsi, [rsp+490h+arg_8]
0x180003071  mov     rbx, [rsp+490h+arg_0]
0x180003079  mov     r14, [rsp+490h+arg_18]
0x180003081  mov     rcx, [rbp+390h+var_10]
0x180003088  xor     rcx, rsp; StackCookie
0x18000308b  call    __security_check_cookie
0x180003090  add     rsp, 490h
0x180003097  pop     rbp
0x180003098  retn
0x180003099  lea     rax, [rsp+490h+var_45C]
0x18000309e  mov     rdx, rdi; BufferCount
0x1800030a1  lea     r9, [rbp+390h+Buffer]
0x1800030a8  mov     [rsp+20h], rax
0x1800030ad  lea     r8, Format; "%s%s.DLL"
0x1800030b4  lea     rcx, [rbp+390h+Source]; Buffer
0x1800030b8  call    cs:__imp_sprintf_s
0x1800030be  movzx   ecx, [rsp+490h+Filename]
0x1800030c3  lea     rbx, [rsp+490h+Filename]
0x1800030c8  test    cl, cl
0x1800030ca  jz      short loc_1800030EE
0x1800030cc  lea     rax, [rsp+490h+Filename]
0x1800030d1  cmp     cl, 5Ch ; '\'
0x1800030d4  jnz     short loc_1800030DE
0x1800030d6  inc     rax
0x1800030d9  mov     rbx, rax
0x1800030dc  jmp     short loc_1800030E7
0x1800030de  mov     rcx, rax; lpsz
0x1800030e1  call    cs:__imp_CharNextA
0x1800030e7  movzx   ecx, byte ptr [rax]
0x1800030ea  test    cl, cl
0x1800030ec  jnz     short loc_1800030D1
0x1800030ee  lea     rax, [rsp+490h+Filename]
0x1800030f3  sub     rbx, rax
0x1800030f6  lea     rax, [rbp+390h+Source]
0x1800030fa  cmp     byte ptr [rax+rsi+1], 0
0x1800030ff  lea     rsi, [rsi+1]
0x180003103  jnz     short loc_1800030FA
0x180003105  lea     rax, [rsi+1]
0x180003109  add     rax, rbx
0x18000310c  cmp     rax, rdi
0x18000310f  ja      short loc_18000313F
0x180003111  mov     r8, rbx; Size
0x180003114  lea     rdx, [rsp+490h+Filename]; Src
0x180003119  lea     rcx, [rbp+390h+LibFileName]; void *
0x180003120  call    memcpy_0
0x180003125  sub     rdi, rbx
0x180003128  lea     rcx, [rbp+390h+LibFileName]
0x18000312f  add     rcx, rbx; Destination
0x180003132  lea     r8, [rbp+390h+Source]; Source
0x180003136  mov     rdx, rdi; SizeInBytes
0x180003139  call    cs:__imp_strcpy_s
0x18000313f  xor     edx, edx; hFile
0x180003141  lea     rcx, [rbp+390h+LibFileName]; lpLibFileName
0x180003148  mov     r8d, 60h ; '`'; dwFlags
0x18000314e  call    cs:__imp_LoadLibraryExA
0x180003154  test    rax, rax
0x180003157  jnz     loc_180003061
0x18000315d  xor     edx, edx; hFile
0x18000315f  lea     rcx, [rbp+390h+Source]; lpLibFileName
0x180003163  mov     r8d, 60h ; '`'; dwFlags
0x180003169  call    cs:__imp_LoadLibraryExA
0x18000316f  test    rax, rax
0x180003172  cmovz   rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x18000317a  jmp     loc_180003061
0x18000317f  mov     rax, cs:?g_hInstance@Global@@2PEAUHINSTANCE__@@EA; HINSTANCE__ * Global::g_hInstance
0x180003186  jmp     loc_180003071
```
