# ConfirmFile(ushort *,int)

- ea: `0x18000e780`
- end: `0x18000ed5c`
- name: `?ConfirmFile@@YAHPEAGH@Z`
- size: `1500`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800090e0`
- `0x1800097b0`
- `0x18000a760`
- `0x18000ab90`
- `0x18000b78c`
- `0x180010b20`
- `0x180013af0`

## callees

- `0x1800089c0`
- `0x18000ab10`
- `0x18000e780`
- `0x18000ed70`
- `0x1800358c0`
- `0x180058a60`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000e8d5`
- `SHLWAPI!PathFindFileNameW` at `0x18000e8d5`
- `SHLWAPI!StrChrW` at `0x18000e820`
- `SHLWAPI!StrChrW` at `0x18000e820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e87c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e87c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ea19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ecf5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ed31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ecf5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ed31`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ecc0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ecc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e865`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e924`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e97d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e9d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eb39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eb92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ebeb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ec40`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e865`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e924`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e97d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000e9d6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eb39`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000eb92`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ebeb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ec40`

## string_xrefs

- `0x18000ec06`: `%sSYSTEM32\%s`
- `0x18000ecee`: `MediaPath`
- `0x18000ed25`: `MediaPath`

## pseudocode

```c
__int64 __fastcall ConfirmFile(unsigned __int16 *a1)
{
  WCHAR *v2; // r8
  unsigned __int16 *v3; // rdx
  __int64 v4; // r9
  __int64 v5; // r12
  __int64 v6; // rax
  WCHAR *v7; // rcx
  const WCHAR *v8; // rax
  const unsigned __int16 *v9; // rsi
  unsigned int v10; // ebx
  HANDLE FileW; // rdi
  LPWSTR FileNameW; // r14
  __int64 v14; // rcx
  WCHAR *v15; // rax
  __int64 v16; // r9
  const wchar_t *v17; // rdx
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // rcx
  WCHAR *v21; // r9
  WCHAR *v22; // rcx
  __int64 v23; // rcx
  WCHAR *v24; // rax
  __int64 v25; // r8
  LPWSTR v26; // rcx
  __int64 v27; // rdx
  WCHAR *v28; // r8
  WCHAR *v29; // rcx
  const WCHAR *v30; // rbx
  int v31; // edx
  DWORD Type[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR pszStart[264]; // [rsp+268h] [rbp+160h] BYREF

  if ( *a1 )
  {
    v2 = pszStart;
    v3 = a1;
    v4 = 261;
    v5 = 2147483646;
    v6 = 2147483646;
    do
    {
      if ( !v6 )
        break;
      if ( !*v3 )
        break;
      *v2++ = *v3++;
      --v6;
      --v4;
    }
    while ( v4 );
    v7 = v2 - 1;
    if ( v4 )
      v7 = v2;
    *v7 = 0;
    v8 = StrChrW(pszStart, 0x2Cu);
    v9 = v8;
    if ( v8 && *v8 )
    {
      v30 = v8;
      v9 = CharNextW(v8);
      *v30 = 0;
    }
    v10 = 3;
    FileW = CreateFileW(pszStart, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      FileNameW = PathFindFileNameW(pszStart);
      StringCchPrintfW(FileName, 0x105u, L"%s%s", &g_szCurDir, FileNameW);
      FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        StringCchPrintfW(FileName, 0x105u, L"%s%s", &g_szThemeDir, FileNameW);
        FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          StringCchPrintfW(FileName, 0x105u, L"%s%s", &g_szWinDir, FileNameW);
          FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            phkResult = 0;
            Type[0] = 0;
            Type[1] = 0;
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion", 0, 1u, &phkResult) )
            {
              if ( !RegQueryValueExW(phkResult, L"MediaPath", 0, &Type[1], 0, Type)
                && Type[0] <= 0x208
                && !RegQueryValueExW(phkResult, L"MediaPath", 0, &Type[1], (LPBYTE)FileName, Type)
                && Type[1] == 2 )
              {
                ExpandSZ(FileName, v31);
              }
              RegCloseKey(phkResult);
            }
            v14 = 261;
            v15 = FileName;
            do
            {
              if ( !*v15 )
                break;
              ++v15;
              --v14;
            }
            while ( v14 );
            v16 = 261 - v14;
            if ( v14 )
            {
              v17 = L"\\";
              v19 = v14;
              v18 = v16 == 261;
              v20 = 2147483646;
              v21 = &FileName[v16];
              if ( !v18 )
              {
                do
                {
                  if ( !v20 )
                    break;
                  if ( !*v17 )
                    break;
                  *v21++ = *v17++;
                  --v20;
                  --v19;
                }
                while ( v19 );
              }
              v22 = v21 - 1;
              if ( v19 )
                v22 = v21;
              *v22 = 0;
            }
            v23 = 261;
            v24 = FileName;
            do
            {
              if ( !*v24 )
                break;
              ++v24;
              --v23;
            }
            while ( v23 );
            v25 = 261 - v23;
            if ( v23 )
            {
              v26 = FileNameW;
              v27 = 261 - v25;
              v18 = v25 == 261;
              v28 = &FileName[v25];
              if ( !v18 )
              {
                do
                {
                  if ( !v5 )
                    break;
                  if ( !*v26 )
                    break;
                  *v28++ = *v26++;
                  --v5;
                  --v27;
                }
                while ( v27 );
              }
              v29 = v28 - 1;
              if ( v27 )
                v29 = v28;
              *v29 = 0;
            }
            FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              StringCchPrintfW(FileName, 0x105u, L"%sCURSORS\\%s", &g_szWinDir, FileNameW);
              FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
              if ( FileW == (HANDLE)-1LL )
              {
                StringCchPrintfW(FileName, 0x105u, L"%sSYSTEM\\%s", &g_szWinDir, FileNameW);
                FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
                if ( FileW == (HANDLE)-1LL )
                {
                  StringCchPrintfW(FileName, 0x105u, L"%sSYSTEM32\\%s", &g_szWinDir, FileNameW);
                  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
                  if ( FileW == (HANDLE)-1LL )
                    return v10;
                }
              }
            }
          }
        }
      }
      v10 = 2;
      StringCchCopyW(a1, 0x104u, FileName);
      if ( v9 )
      {
        if ( *v9 )
        {
          StringCchCatW(a1, 0x104u, L",");
          StringCchCatW(a1, 0x104u, v9);
        }
      }
    }
    else
    {
      v10 = 1;
    }
    CloseHandle(FileW);
    return v10;
  }
  return 1;
}

```

## disassembly

```asm
0x18000e780  mov     r11, rsp
0x18000e783  push    rbp
0x18000e784  push    r15
0x18000e786  lea     rbp, [r11-3A8h]
0x18000e78d  sub     rsp, 498h
0x18000e794  mov     rax, cs:__security_cookie
0x18000e79b  xor     rax, rsp
0x18000e79e  mov     [rbp+3A0h+var_30], rax
0x18000e7a5  cmp     word ptr [rcx], 0
0x18000e7a9  mov     r15, rcx
0x18000e7ac  jz      loc_18000ECA6
0x18000e7b2  mov     [r11+10h], rbx
0x18000e7b6  lea     r8, [rbp+3A0h+pszStart]
0x18000e7bd  mov     [r11+18h], rsi
0x18000e7c1  mov     rdx, rcx
0x18000e7c4  mov     [r11+20h], rdi
0x18000e7c8  mov     r9d, 105h
0x18000e7ce  mov     [r11-18h], r12
0x18000e7d2  mov     r12d, 7FFFFFFEh
0x18000e7d8  mov     eax, r12d
0x18000e7db  mov     [r11-20h], r13
0x18000e7df  nop
0x18000e7e0  test    rax, rax
0x18000e7e3  jz      short loc_18000E802
0x18000e7e5  movzx   ecx, word ptr [rdx]
0x18000e7e8  test    cx, cx
0x18000e7eb  jz      short loc_18000E802
0x18000e7ed  mov     [r8], cx
0x18000e7f1  add     rdx, 2
0x18000e7f5  add     r8, 2
0x18000e7f9  dec     rax
0x18000e7fc  sub     r9, 1
0x18000e800  jnz     short loc_18000E7E0
0x18000e802  test    r9, r9
0x18000e805  lea     rcx, [r8-2]
0x18000e809  mov     edx, 2Ch ; ','; wMatch
0x18000e80e  cmovnz  rcx, r8
0x18000e812  xor     r13d, r13d
0x18000e815  mov     [rcx], r13w
0x18000e819  lea     rcx, [rbp+3A0h+pszStart]; pszStart
0x18000e820  call    cs:__imp_StrChrW
0x18000e826  mov     rsi, rax
0x18000e829  test    rax, rax
0x18000e82c  jnz     loc_18000ECB0
0x18000e832  mov     [rsp+30h], r13; hTemplateFile
0x18000e837  lea     rcx, [rbp+3A0h+pszStart]; lpFileName
0x18000e83e  mov     ebx, 3
0x18000e843  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e84b  xor     r9d, r9d; lpSecurityAttributes
0x18000e84e  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000e852  mov     edx, 80000000h; dwDesiredAccess
0x18000e857  mov     [rsp+4A0h+var_20], r14
0x18000e85f  mov     r8d, 1; dwShareMode
0x18000e865  call    cs:__imp_CreateFileW
0x18000e86b  mov     rdi, rax
0x18000e86e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e872  jz      short loc_18000E8CE
0x18000e874  mov     ebx, 1
0x18000e879  mov     rcx, rdi; hObject
0x18000e87c  call    cs:__imp_CloseHandle
0x18000e882  mov     r14, [rsp+4A0h+var_20]
0x18000e88a  mov     eax, ebx
0x18000e88c  mov     rbx, [rsp+4A0h+arg_8]
0x18000e894  mov     r13, [rsp+4A0h+var_18]
0x18000e89c  mov     r12, [rsp+490h]
0x18000e8a4  mov     rdi, [rsp+4A0h+arg_18]
0x18000e8ac  mov     rsi, [rsp+4A0h+arg_10]
0x18000e8b4  mov     rcx, [rbp+3A0h+var_30]
0x18000e8bb  xor     rcx, rsp; StackCookie
0x18000e8be  call    __security_check_cookie
0x18000e8c3  add     rsp, 498h
0x18000e8ca  pop     r15
0x18000e8cc  pop     rbp
0x18000e8cd  retn
0x18000e8ce  lea     rcx, [rbp+3A0h+pszStart]; pszPath
0x18000e8d5  call    cs:__imp_PathFindFileNameW
0x18000e8db  lea     r9, ?g_szCurDir@@3PAGA; ushort near * g_szCurDir
0x18000e8e2  mov     edx, 105h; unsigned __int64
0x18000e8e7  lea     r8, aSS_0; "%s%s"
0x18000e8ee  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax
0x18000e8f3  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000e8f8  mov     r14, rax
0x18000e8fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e900  mov     [rsp+30h], r13; hTemplateFile
0x18000e905  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000e90a  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e912  xor     r9d, r9d; lpSecurityAttributes
0x18000e915  mov     edx, 80000000h; dwDesiredAccess
0x18000e91a  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000e91e  mov     r8d, 1; dwShareMode
0x18000e924  call    cs:__imp_CreateFileW
0x18000e92a  mov     rdi, rax
0x18000e92d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e931  jnz     loc_18000EC53
0x18000e937  lea     r9, ?g_szThemeDir@@3PAGA; ushort near * g_szThemeDir
0x18000e93e  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x18000e943  lea     r8, aSS_0; "%s%s"
0x18000e94a  mov     edx, 105h; unsigned __int64
0x18000e94f  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000e954  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e959  mov     [rsp+30h], r13; hTemplateFile
0x18000e95e  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000e963  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e96b  xor     r9d, r9d; lpSecurityAttributes
0x18000e96e  mov     edx, 80000000h; dwDesiredAccess
0x18000e973  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000e977  mov     r8d, 1; dwShareMode
0x18000e97d  call    cs:__imp_CreateFileW
0x18000e983  mov     rdi, rax
0x18000e986  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e98a  jnz     loc_18000EC53
0x18000e990  lea     r9, ?g_szWinDir@@3PAGA; ushort near * g_szWinDir
0x18000e997  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x18000e99c  lea     r8, aSS_0; "%s%s"
0x18000e9a3  mov     edx, 105h; unsigned __int64
0x18000e9a8  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000e9ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e9b2  mov     [rsp+30h], r13; hTemplateFile
0x18000e9b7  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000e9bc  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000e9c4  xor     r9d, r9d; lpSecurityAttributes
0x18000e9c7  mov     edx, 80000000h; dwDesiredAccess
0x18000e9cc  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000e9d0  mov     r8d, 1; dwShareMode
0x18000e9d6  call    cs:__imp_CreateFileW
0x18000e9dc  mov     rdi, rax
0x18000e9df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e9e3  jnz     loc_18000EC53
0x18000e9e9  lea     rax, [rsp+4A0h+phkResult]
0x18000e9ee  mov     [rsp+4A0h+phkResult], r13
0x18000e9f3  mov     r9d, 1; samDesired
0x18000e9f9  mov     qword ptr [rsp+4A0h+dwCreationDisposition], rax; phkResult
0x18000e9fe  xor     r8d, r8d; ulOptions
0x18000ea01  mov     [rsp+4A0h+Type], r13d
0x18000ea06  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ea0d  mov     [rsp+4A0h+Type+4], r13d
0x18000ea12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ea19  call    cs:__imp_RegOpenKeyExW
0x18000ea1f  test    eax, eax
0x18000ea21  jz      loc_18000ECD2
0x18000ea27  mov     ecx, 105h
0x18000ea2c  lea     rax, [rsp+4A0h+FileName]
0x18000ea31  cmp     [rax], r13w
0x18000ea35  jz      short loc_18000EA41
0x18000ea37  add     rax, 2
0x18000ea3b  sub     rcx, 1
0x18000ea3f  jnz     short loc_18000EA31
0x18000ea41  mov     r9d, 105h
0x18000ea47  sub     r9, rcx
0x18000ea4a  test    rcx, rcx
0x18000ea4d  cmovz   r9, r13
0x18000ea51  jz      short loc_18000EAA1
0x18000ea53  mov     r8d, 105h
0x18000ea59  lea     rdx, Control; "\\"
0x18000ea60  sub     r8, r9
0x18000ea63  mov     rcx, r12
0x18000ea66  lea     r9, [rsp+r9*2+4A0h+FileName]
0x18000ea6b  jz      short loc_18000EA92
0x18000ea6d  nop     dword ptr [rax]
0x18000ea70  test    rcx, rcx
0x18000ea73  jz      short loc_18000EA92
0x18000ea75  movzx   eax, word ptr [rdx]
0x18000ea78  test    ax, ax
0x18000ea7b  jz      short loc_18000EA92
0x18000ea7d  mov     [r9], ax
0x18000ea81  add     rdx, 2
0x18000ea85  add     r9, 2
0x18000ea89  dec     rcx
0x18000ea8c  sub     r8, 1
0x18000ea90  jnz     short loc_18000EA70
0x18000ea92  test    r8, r8
0x18000ea95  lea     rcx, [r9-2]
0x18000ea99  cmovnz  rcx, r9
0x18000ea9d  mov     [rcx], r13w
0x18000eaa1  mov     ecx, 105h
0x18000eaa6  lea     rax, [rsp+4A0h+FileName]
0x18000eaab  nop     dword ptr [rax+rax+00h]
0x18000eab0  cmp     [rax], r13w
0x18000eab4  jz      short loc_18000EAC0
0x18000eab6  add     rax, 2
0x18000eaba  sub     rcx, 1
0x18000eabe  jnz     short loc_18000EAB0
0x18000eac0  mov     r8d, 105h
0x18000eac6  sub     r8, rcx
0x18000eac9  test    rcx, rcx
0x18000eacc  cmovz   r8, r13
0x18000ead0  jz      short loc_18000EB15
0x18000ead2  mov     edx, 105h
0x18000ead7  mov     rcx, r14
0x18000eada  sub     rdx, r8
0x18000eadd  lea     r8, [rsp+r8*2+4A0h+FileName]
0x18000eae2  jz      short loc_18000EB06
0x18000eae4  test    r12, r12
0x18000eae7  jz      short loc_18000EB06
0x18000eae9  movzx   eax, word ptr [rcx]
0x18000eaec  test    ax, ax
0x18000eaef  jz      short loc_18000EB06
0x18000eaf1  mov     [r8], ax
0x18000eaf5  add     rcx, 2
0x18000eaf9  add     r8, 2
0x18000eafd  dec     r12
0x18000eb00  sub     rdx, 1
0x18000eb04  jnz     short loc_18000EAE4
0x18000eb06  test    rdx, rdx
0x18000eb09  lea     rcx, [r8-2]
0x18000eb0d  cmovnz  rcx, r8
0x18000eb11  mov     [rcx], r13w
0x18000eb15  mov     [rsp+30h], r13; hTemplateFile
0x18000eb1a  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000eb1f  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000eb27  xor     r9d, r9d; lpSecurityAttributes
0x18000eb2a  mov     edx, 80000000h; dwDesiredAccess
0x18000eb2f  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000eb33  mov     r8d, 1; dwShareMode
0x18000eb39  call    cs:__imp_CreateFileW
0x18000eb3f  mov     rdi, rax
0x18000eb42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000eb46  jnz     loc_18000EC53
0x18000eb4c  lea     r9, ?g_szWinDir@@3PAGA; ushort near * g_szWinDir
0x18000eb53  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x18000eb58  lea     r8, aScursorsS; "%sCURSORS\\%s"
0x18000eb5f  mov     edx, 105h; unsigned __int64
0x18000eb64  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000eb69  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000eb6e  mov     [rsp+30h], r13; hTemplateFile
0x18000eb73  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000eb78  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000eb80  xor     r9d, r9d; lpSecurityAttributes
0x18000eb83  mov     edx, 80000000h; dwDesiredAccess
0x18000eb88  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000eb8c  mov     r8d, 1; dwShareMode
0x18000eb92  call    cs:__imp_CreateFileW
0x18000eb98  mov     rdi, rax
0x18000eb9b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000eb9f  jnz     loc_18000EC53
0x18000eba5  lea     r9, ?g_szWinDir@@3PAGA; ushort near * g_szWinDir
0x18000ebac  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x18000ebb1  lea     r8, aSsystemS; "%sSYSTEM\\%s"
0x18000ebb8  mov     edx, 105h; unsigned __int64
0x18000ebbd  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000ebc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ebc7  mov     [rsp+30h], r13; hTemplateFile
0x18000ebcc  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000ebd1  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000ebd9  xor     r9d, r9d; lpSecurityAttributes
0x18000ebdc  mov     edx, 80000000h; dwDesiredAccess
0x18000ebe1  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000ebe5  mov     r8d, 1; dwShareMode
0x18000ebeb  call    cs:__imp_CreateFileW
0x18000ebf1  mov     rdi, rax
0x18000ebf4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ebf8  jnz     short loc_18000EC53
0x18000ebfa  lea     r9, ?g_szWinDir@@3PAGA; ushort near * g_szWinDir
0x18000ec01  mov     qword ptr [rsp+4A0h+dwCreationDisposition], r14
0x18000ec06  lea     r8, aSsystem32S; "%sSYSTEM32\\%s"
0x18000ec0d  mov     edx, 105h; unsigned __int64
0x18000ec12  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000ec17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ec1c  mov     [rsp+30h], r13; hTemplateFile
0x18000ec21  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18000ec26  mov     [rsp+4A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000ec2e  xor     r9d, r9d; lpSecurityAttributes
0x18000ec31  mov     edx, 80000000h; dwDesiredAccess
0x18000ec36  mov     [rsp+4A0h+dwCreationDisposition], ebx; dwCreationDisposition
0x18000ec3a  mov     r8d, 1; dwShareMode
0x18000ec40  call    cs:__imp_CreateFileW
0x18000ec46  mov     rdi, rax
0x18000ec49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ec4d  jz      loc_18000E882
0x18000ec53  lea     r8, [rsp+4A0h+FileName]; unsigned __int16 *
0x18000ec58  mov     edx, 104h; unsigned __int64
0x18000ec5d  mov     rcx, r15; unsigned __int16 *
0x18000ec60  mov     ebx, 2
0x18000ec65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ec6a  test    rsi, rsi
0x18000ec6d  jz      loc_18000E879
0x18000ec73  cmp     [rsi], r13w
0x18000ec77  jz      loc_18000E879
0x18000ec7d  lea     r8, pszSrch; ","
0x18000ec84  mov     edx, 104h; unsigned __int64
0x18000ec89  mov     rcx, r15; unsigned __int16 *
0x18000ec8c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ec91  mov     r8, rsi; unsigned __int16 *
0x18000ec94  mov     edx, 104h; unsigned __int64
0x18000ec99  mov     rcx, r15; unsigned __int16 *
0x18000ec9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eca1  jmp     loc_18000E879
0x18000eca6  mov     eax, 1
0x18000ecab  jmp     loc_18000E8B4
0x18000ecb0  cmp     [rax], r13w
0x18000ecb4  jz      loc_18000E832
0x18000ecba  mov     rcx, rax; lpsz
0x18000ecbd  mov     rbx, rax
0x18000ecc0  call    cs:__imp_CharNextW
0x18000ecc6  mov     rsi, rax
0x18000ecc9  mov     [rbx], r13w
0x18000eccd  jmp     loc_18000E832
0x18000ecd2  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x18000ecd7  lea     rax, [rsp+4A0h+Type]
0x18000ecdc  mov     qword ptr [rsp+4A0h+dwFlagsAndAttributes], rax; lpcbData
  ... truncated ...
```
