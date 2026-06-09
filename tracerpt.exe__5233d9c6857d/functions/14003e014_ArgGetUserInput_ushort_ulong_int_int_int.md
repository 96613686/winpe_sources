# ArgGetUserInput(ushort *,ulong,int,int,int *)

- ea: `0x14003e014`
- end: `0x14003e32b`
- name: `?ArgGetUserInput@@YAJPEAGKHHPEAH@Z`
- size: `791`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, int, int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003db38`

## callees

- `0x14003d254`
- `0x14003d7b8`
- `0x14003e014`
- `0x14003e334`
- `0x140040130`

## import_xrefs

- `msvcrt!wprintf` at `0x14003e280`
- `msvcrt!wprintf` at `0x14003e2b2`
- `msvcrt!wprintf` at `0x14003e280`
- `msvcrt!wprintf` at `0x14003e2b2`
- `msvcrt!_getmbcp` at `0x14003e186`
- `msvcrt!_getmbcp` at `0x14003e186`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14003e1a5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14003e1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e07a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e0e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e1e5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003e13a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003e1d7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003e13a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14003e1d7`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003e05e`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14003e05e`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x14003e206`
- `api-ms-win-core-console-l1-1-0!ReadConsoleW` at `0x14003e206`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x14003e0a7`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x14003e0a7`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14003e0da`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14003e2e3`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14003e0da`
- `api-ms-win-core-console-l1-1-0!SetConsoleMode` at `0x14003e2e3`

## pseudocode

```c
__int64 __fastcall ArgGetUserInput(unsigned __int16 *a1)
{
  unsigned __int64 v2; // rsi
  HANDLE StdHandle; // r14
  signed int LastError; // eax
  signed int v5; // edi
  signed int v6; // ebx
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  __int64 v10; // r9
  UINT v11; // eax
  signed int v12; // eax
  CHAR Buffer[4]; // [rsp+30h] [rbp-30h] BYREF
  WCHAR WideCharStr[2]; // [rsp+34h] [rbp-2Ch] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-28h] BYREF
  DWORD Mode; // [rsp+3Ch] [rbp-24h] BYREF
  __int128 v18; // [rsp+40h] [rbp-20h]
  int v19; // [rsp+50h] [rbp-10h]

  WideCharStr[0] = 0;
  Buffer[0] = 0;
  v18 = 0;
  v19 = 0;
  v2 = 0;
  NumberOfBytesRead = 0;
  Mode = 0;
  StdHandle = GetStdHandle(0xFFFFFFF6);
  if ( (((unsigned __int64)StdHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( !LastError )
    {
      v5 = -2147467259;
LABEL_6:
      v6 = v5;
      goto LABEL_55;
    }
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_6;
  }
  if ( !GetConsoleMode(StdHandle, &Mode) )
  {
    v7 = GetLastError();
    v6 = v7;
    if ( !v7 )
    {
LABEL_54:
      v6 = -2147467259;
      goto LABEL_55;
    }
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 < 0 )
      goto LABEL_55;
  }
  if ( SetConsoleMode(StdHandle, Mode & 0xFFFFFFF9) )
  {
    v6 = 0;
LABEL_19:
    v5 = -2147467259;
    while ( !(unsigned int)ArgIsConsole(StdHandle) )
    {
      if ( !ReadFile(StdHandle, Buffer, 1u, &NumberOfBytesRead, 0) )
      {
        v9 = GetLastError();
        v6 = v9;
        if ( !v9 )
          goto LABEL_6;
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        if ( v6 < 0 )
          goto LABEL_55;
        goto LABEL_39;
      }
      if ( !NumberOfBytesRead )
      {
        WideCharStr[0] = 10;
        v10 = 13;
        goto LABEL_40;
      }
      v11 = _getmbcp();
      if ( !MultiByteToWideChar(v11, 0, Buffer, 1, WideCharStr, 1) )
        WideCharStr[0] = 0;
      v10 = 13;
      if ( WideCharStr[0] == 13 )
      {
        if ( ReadFile(StdHandle, Buffer, 1u, &NumberOfBytesRead, 0) )
        {
          v6 = 0;
        }
        else
        {
          v12 = GetLastError();
          v6 = v12;
          if ( v12 )
          {
            if ( v12 > 0 )
              v6 = (unsigned __int16)v12 | 0x80070000;
          }
          else
          {
            v6 = -2147467259;
          }
        }
        goto LABEL_39;
      }
LABEL_40:
      switch ( WideCharStr[0] )
      {
        case 3u:
          v6 = -2147023673;
          goto LABEL_55;
        case 8u:
          if ( v2 )
          {
            a1[v2--] = 0;
            wprintf(L"%c %c", 8, 8, 13);
          }
          break;
        case 0xAu:
        case 0xDu:
          ArgPrintEx(0, L"\n");
          goto LABEL_55;
        case 0x1Bu:
          for ( ; v2; --v2 )
            wprintf(L"%c %c", 8, 8, v10);
          break;
        default:
          if ( v2 < 0x3FF )
          {
            a1[v2++] = WideCharStr[0];
            ArgPrintf(L"%1!c!", WideCharStr[0], 10, 13);
          }
          break;
      }
    }
    ReadConsoleW(StdHandle, WideCharStr, 1u, &NumberOfBytesRead, 0);
LABEL_39:
    v10 = 13;
    goto LABEL_40;
  }
  v8 = GetLastError();
  v6 = v8;
  if ( !v8 )
    goto LABEL_54;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80070000;
  if ( v6 >= 0 )
    goto LABEL_19;
LABEL_55:
  if ( Mode )
    SetConsoleMode(StdHandle, Mode);
  if ( v2 < 0x400 )
  {
    a1[v2] = 0;
  }
  else if ( v6 >= 0 )
  {
    return (unsigned int)-2147024774;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003e014  mov     [rsp-28h+arg_8], rbx
0x14003e019  mov     [rsp-28h+arg_10], rsi
0x14003e01e  push    rbp
0x14003e01f  push    rdi
0x14003e020  push    r13
0x14003e022  push    r14
0x14003e024  push    r15
0x14003e026  mov     rbp, rsp
0x14003e029  sub     rsp, 60h
0x14003e02d  mov     rax, cs:__security_cookie
0x14003e034  xor     rax, rsp
0x14003e037  mov     [rbp+var_8], rax
0x14003e03b  xor     eax, eax
0x14003e03d  mov     r15, rcx
0x14003e040  xorps   xmm0, xmm0
0x14003e043  mov     [rbp+WideCharStr], ax
0x14003e047  mov     ecx, 0FFFFFFF6h; nStdHandle
0x14003e04c  mov     [rbp+Buffer], al
0x14003e04f  movups  [rbp+var_20], xmm0
0x14003e053  mov     [rbp+var_10], eax
0x14003e056  xor     esi, esi
0x14003e058  mov     [rbp+NumberOfBytesRead], eax
0x14003e05b  mov     [rbp+Mode], eax
0x14003e05e  call    cs:__imp_GetStdHandle
0x14003e064  mov     r14, rax
0x14003e067  mov     r13d, 80070000h
0x14003e06d  lea     rcx, [rax+1]
0x14003e071  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14003e078  jnz     short loc_14003E0A0
0x14003e07a  call    cs:__imp_GetLastError
0x14003e080  mov     edi, eax
0x14003e082  test    eax, eax
0x14003e084  jz      short loc_14003E099
0x14003e086  jle     short loc_14003E08E
0x14003e088  movzx   edi, ax
0x14003e08b  or      edi, r13d
0x14003e08e  test    edi, edi
0x14003e090  jns     short loc_14003E0A0
0x14003e092  mov     ebx, edi
0x14003e094  jmp     loc_14003E2D9
0x14003e099  mov     edi, 80004005h
0x14003e09e  jmp     short loc_14003E092
0x14003e0a0  lea     rdx, [rbp+Mode]; lpMode
0x14003e0a4  mov     rcx, r14; hConsoleHandle
0x14003e0a7  call    cs:__imp_GetConsoleMode
0x14003e0ad  test    eax, eax
0x14003e0af  jnz     short loc_14003E0D1
0x14003e0b1  call    cs:__imp_GetLastError
0x14003e0b7  mov     ebx, eax
0x14003e0b9  test    eax, eax
0x14003e0bb  jz      loc_14003E2D4
0x14003e0c1  jle     short loc_14003E0C9
0x14003e0c3  movzx   ebx, ax
0x14003e0c6  or      ebx, r13d
0x14003e0c9  test    ebx, ebx
0x14003e0cb  js      loc_14003E2D9
0x14003e0d1  mov     edx, [rbp+Mode]
0x14003e0d4  mov     rcx, r14; hConsoleHandle
0x14003e0d7  and     edx, 0FFFFFFF9h; dwMode
0x14003e0da  call    cs:__imp_SetConsoleMode
0x14003e0e0  test    eax, eax
0x14003e0e2  jz      short loc_14003E0E8
0x14003e0e4  xor     ebx, ebx
0x14003e0e6  jmp     short loc_14003E108
0x14003e0e8  call    cs:__imp_GetLastError
0x14003e0ee  mov     ebx, eax
0x14003e0f0  test    eax, eax
0x14003e0f2  jz      loc_14003E2D4
0x14003e0f8  jle     short loc_14003E100
0x14003e0fa  movzx   ebx, ax
0x14003e0fd  or      ebx, r13d
0x14003e100  test    ebx, ebx
0x14003e102  js      loc_14003E2D9
0x14003e108  mov     edi, 80004005h
0x14003e10d  mov     r13d, 1
0x14003e113  mov     rcx, r14; hConsoleHandle
0x14003e116  call    ?ArgIsConsole@@YAHPEAX@Z; ArgIsConsole(void *)
0x14003e11b  mov     [rsp+60h+lpOverlapped], 0; pInputControl
0x14003e124  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfCharsRead
0x14003e128  mov     r8d, r13d; nNumberOfCharsToRead
0x14003e12b  mov     rcx, r14; hConsoleInput
0x14003e12e  test    eax, eax
0x14003e130  jnz     loc_14003E202
0x14003e136  lea     rdx, [rbp+Buffer]; lpBuffer
0x14003e13a  call    cs:__imp_ReadFile
0x14003e140  test    eax, eax
0x14003e142  jnz     short loc_14003E16C
0x14003e144  call    cs:__imp_GetLastError
0x14003e14a  mov     ebx, eax
0x14003e14c  test    eax, eax
0x14003e14e  jz      loc_14003E092
0x14003e154  jle     short loc_14003E15F
0x14003e156  movzx   ebx, ax
0x14003e159  or      ebx, 80070000h
0x14003e15f  test    ebx, ebx
0x14003e161  js      loc_14003E2D9
0x14003e167  jmp     loc_14003E20C
0x14003e16c  cmp     [rbp+NumberOfBytesRead], 0
0x14003e170  jnz     short loc_14003E186
0x14003e172  mov     r8d, 0Ah
0x14003e178  mov     [rbp+WideCharStr], r8w
0x14003e17d  lea     r9d, [r8+3]
0x14003e181  jmp     loc_14003E218
0x14003e186  call    cs:__imp__getmbcp
0x14003e18c  mov     [rsp+60h+cchWideChar], r13d; cchWideChar
0x14003e191  lea     r8, [rbp+Buffer]; lpMultiByteStr
0x14003e195  mov     ecx, eax; CodePage
0x14003e197  mov     r9d, r13d; cbMultiByte
0x14003e19a  lea     rax, [rbp+WideCharStr]
0x14003e19e  xor     edx, edx; dwFlags
0x14003e1a0  mov     [rsp+60h+lpOverlapped], rax; lpWideCharStr
0x14003e1a5  call    cs:__imp_MultiByteToWideChar
0x14003e1ab  test    eax, eax
0x14003e1ad  jnz     short loc_14003E1B3
0x14003e1af  mov     [rbp+WideCharStr], ax
0x14003e1b3  mov     r9d, 0Dh
0x14003e1b9  cmp     r9w, [rbp+WideCharStr]
0x14003e1be  jnz     short loc_14003E212
0x14003e1c0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14003e1c4  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x14003e1cd  mov     r8d, r13d; nNumberOfBytesToRead
0x14003e1d0  lea     rdx, [rbp+Buffer]; lpBuffer
0x14003e1d4  mov     rcx, r14; hFile
0x14003e1d7  call    cs:__imp_ReadFile
0x14003e1dd  test    eax, eax
0x14003e1df  jz      short loc_14003E1E5
0x14003e1e1  xor     ebx, ebx
0x14003e1e3  jmp     short loc_14003E20C
0x14003e1e5  call    cs:__imp_GetLastError
0x14003e1eb  mov     ebx, eax
0x14003e1ed  test    eax, eax
0x14003e1ef  jz      short loc_14003E1FE
0x14003e1f1  jle     short loc_14003E20C
0x14003e1f3  movzx   ebx, ax
0x14003e1f6  or      ebx, 80070000h
0x14003e1fc  jmp     short loc_14003E20C
0x14003e1fe  mov     ebx, edi
0x14003e200  jmp     short loc_14003E20C
0x14003e202  lea     rdx, [rbp+WideCharStr]; lpBuffer
0x14003e206  call    cs:__imp_ReadConsoleW
0x14003e20c  mov     r9d, 0Dh
0x14003e212  mov     r8d, 0Ah
0x14003e218  movzx   ecx, [rbp+WideCharStr]
0x14003e21c  mov     eax, ecx
0x14003e21e  cmp     ecx, 3
0x14003e221  jz      loc_14003E2CD
0x14003e227  mov     edx, 8
0x14003e22c  cmp     eax, edx
0x14003e22e  jz      short loc_14003E295
0x14003e230  cmp     eax, r8d
0x14003e233  jz      loc_14003E2BD
0x14003e239  cmp     eax, r9d
0x14003e23c  jz      short loc_14003E2BD
0x14003e23e  cmp     eax, 1Bh
0x14003e241  jz      short loc_14003E26D
0x14003e243  cmp     rsi, 3FFh
0x14003e24a  jnb     loc_14003E113
0x14003e250  mov     [r15+rsi*2], cx
0x14003e255  add     rsi, r13
0x14003e258  movzx   edx, [rbp+WideCharStr]
0x14003e25c  lea     rcx, a1C; "%1!c!"
0x14003e263  call    ?ArgPrintf@@YAJPEBGZZ; ArgPrintf(ushort const *,...)
0x14003e268  jmp     loc_14003E113
0x14003e26d  test    rsi, rsi
0x14003e270  jz      loc_14003E113
0x14003e276  mov     r8d, edx
0x14003e279  lea     rcx, aCC; "%c %c"
0x14003e280  call    cs:__imp_wprintf
0x14003e286  mov     edx, 8
0x14003e28b  sub     rsi, r13
0x14003e28e  jnz     short loc_14003E276
0x14003e290  jmp     loc_14003E113
0x14003e295  test    rsi, rsi
0x14003e298  jz      loc_14003E113
0x14003e29e  xor     eax, eax
0x14003e2a0  lea     rcx, aCC; "%c %c"
0x14003e2a7  mov     [r15+rsi*2], ax
0x14003e2ac  mov     r8d, edx
0x14003e2af  sub     rsi, r13
0x14003e2b2  call    cs:__imp_wprintf
0x14003e2b8  jmp     loc_14003E113
0x14003e2bd  lea     rdx, asc_140059298; "\n"
0x14003e2c4  xor     ecx, ecx; unsigned int *
0x14003e2c6  call    ?ArgPrintEx@@YAJPEAKPEBG@Z; ArgPrintEx(ulong *,ushort const *)
0x14003e2cb  jmp     short loc_14003E2D9
0x14003e2cd  mov     ebx, 800704C7h
0x14003e2d2  jmp     short loc_14003E2D9
0x14003e2d4  mov     ebx, 80004005h
0x14003e2d9  mov     edx, [rbp+Mode]; dwMode
0x14003e2dc  test    edx, edx
0x14003e2de  jz      short loc_14003E2E9
0x14003e2e0  mov     rcx, r14; hConsoleHandle
0x14003e2e3  call    cs:__imp_SetConsoleMode
0x14003e2e9  cmp     rsi, 400h
0x14003e2f0  jb      short loc_14003E2FD
0x14003e2f2  test    ebx, ebx
0x14003e2f4  js      short loc_14003E304
0x14003e2f6  mov     ebx, 8007007Ah
0x14003e2fb  jmp     short loc_14003E304
0x14003e2fd  xor     ecx, ecx
0x14003e2ff  mov     [r15+rsi*2], cx
0x14003e304  mov     eax, ebx
0x14003e306  mov     rcx, [rbp+var_8]
0x14003e30a  xor     rcx, rsp; StackCookie
0x14003e30d  call    __security_check_cookie
0x14003e312  lea     r11, [rsp+60h+var_s0]
0x14003e317  mov     rbx, [r11+38h]
0x14003e31b  mov     rsi, [r11+40h]
0x14003e31f  mov     rsp, r11
0x14003e322  pop     r15
0x14003e324  pop     r14
0x14003e326  pop     r13
0x14003e328  pop     rdi
0x14003e329  pop     rbp
0x14003e32a  retn
```
