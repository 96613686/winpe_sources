# CreateExtractionDirectory(ushort *)

- ea: `0x180002c98`
- end: `0x180002e5c`
- name: `?CreateExtractionDirectory@@YAJPEAG@Z`
- size: `452`
- prototype: `__int64 __fastcall(WCHAR *lpPathName, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003ab0`

## callees

- `0x180002c98`
- `0x18000531c`
- `0x180006c3c`
- `0x180006c9c`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180002d1f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180002d1f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180002dee`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180002dee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002da7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002df8`

## pseudocode

```c
__int64 __fastcall CreateExtractionDirectory(WCHAR *lpPathName, unsigned int a2)
{
  int TempDirPath; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  signed int v8; // eax
  signed int v9; // eax
  signed int LastError; // eax
  WCHAR PathName[264]; // [rsp+20h] [rbp-228h] BYREF

  TempDirPath = UtilGetTempDirPath(PathName, a2);
  v4 = TempDirPath;
  if ( TempDirPath >= 0 )
  {
    if ( GetTempFileNameW(PathName, L"WER", 0, lpPathName) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, lpPathName);
      if ( DeleteFileW(lpPathName) )
      {
        if ( CreateDirectoryW(lpPathName, 0) )
          return 0;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)v4;
        v6 = 56;
      }
      else
      {
        v9 = GetLastError();
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return (unsigned int)v4;
        v6 = 55;
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v4;
      v6 = 53;
    }
    v7 = (unsigned int)v4;
    goto LABEL_5;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 52;
    v7 = (unsigned int)TempDirPath;
LABEL_5:
    WPP_SF_d(v5[2], v6, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002c98  mov     [rsp+arg_8], rbx
0x180002c9d  mov     [rsp+arg_10], rsi
0x180002ca2  push    rdi
0x180002ca3  sub     rsp, 240h
0x180002caa  mov     rax, cs:__security_cookie
0x180002cb1  xor     rax, rsp
0x180002cb4  mov     [rsp+248h+var_18], rax
0x180002cbc  mov     rsi, rcx
0x180002cbf  lea     rcx, [rsp+248h+PathName]; String1
0x180002cc4  call    ?UtilGetTempDirPath@@YAJPEAGK@Z; UtilGetTempDirPath(ushort *,ulong)
0x180002cc9  mov     ebx, eax
0x180002ccb  test    eax, eax
0x180002ccd  jns     short loc_180002D0D
0x180002ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd6  lea     rdi, WPP_GLOBAL_Control
0x180002cdd  cmp     rcx, rdi
0x180002ce0  jz      loc_180002E35
0x180002ce6  test    byte ptr [rcx+1Ch], 1
0x180002cea  jz      loc_180002E35
0x180002cf0  mov     edx, 34h ; '4'
0x180002cf5  mov     r9d, eax
0x180002cf8  mov     rcx, [rcx+10h]
0x180002cfc  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180002d03  call    WPP_SF_d
0x180002d08  jmp     loc_180002E35
0x180002d0d  mov     r9, rsi; lpTempFileName
0x180002d10  lea     rdx, PrefixString; "WER"
0x180002d17  xor     r8d, r8d; uUnique
0x180002d1a  lea     rcx, [rsp+248h+PathName]; lpPathName
0x180002d1f  call    cs:__imp_GetTempFileNameW
0x180002d25  test    eax, eax
0x180002d27  jnz     short loc_180002D73
0x180002d29  call    cs:__imp_GetLastError
0x180002d2f  mov     ebx, eax
0x180002d31  test    eax, eax
0x180002d33  jle     short loc_180002D3E
0x180002d35  movzx   ebx, ax
0x180002d38  or      ebx, 80070000h
0x180002d3e  test    ebx, ebx
0x180002d40  mov     eax, 80004005h
0x180002d45  cmovns  ebx, eax
0x180002d48  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d4f  lea     rdi, WPP_GLOBAL_Control
0x180002d56  cmp     rcx, rdi
0x180002d59  jz      loc_180002E35
0x180002d5f  test    byte ptr [rcx+1Ch], 1
0x180002d63  jz      loc_180002E35
0x180002d69  mov     edx, 35h ; '5'
0x180002d6e  mov     r9d, ebx
0x180002d71  jmp     short loc_180002CF8
0x180002d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d7a  lea     rdi, WPP_GLOBAL_Control
0x180002d81  cmp     rcx, rdi
0x180002d84  jz      short loc_180002DA4
0x180002d86  test    byte ptr [rcx+1Ch], 4
0x180002d8a  jz      short loc_180002DA4
0x180002d8c  mov     rcx, [rcx+10h]
0x180002d90  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180002d97  mov     edx, 36h ; '6'
0x180002d9c  mov     r9, rsi
0x180002d9f  call    WPP_SF_S
0x180002da4  mov     rcx, rsi; lpFileName
0x180002da7  call    cs:__imp_DeleteFileW
0x180002dad  test    eax, eax
0x180002daf  jnz     short loc_180002DE9
0x180002db1  call    cs:__imp_GetLastError
0x180002db7  mov     ebx, eax
0x180002db9  test    eax, eax
0x180002dbb  jle     short loc_180002DC6
0x180002dbd  movzx   ebx, ax
0x180002dc0  or      ebx, 80070000h
0x180002dc6  test    ebx, ebx
0x180002dc8  mov     eax, 80004005h
0x180002dcd  cmovns  ebx, eax
0x180002dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dd7  cmp     rcx, rdi
0x180002dda  jz      short loc_180002E35
0x180002ddc  test    byte ptr [rcx+1Ch], 1
0x180002de0  jz      short loc_180002E35
0x180002de2  mov     edx, 37h ; '7'
0x180002de7  jmp     short loc_180002D6E
0x180002de9  xor     edx, edx; lpSecurityAttributes
0x180002deb  mov     rcx, rsi; lpPathName
0x180002dee  call    cs:__imp_CreateDirectoryW
0x180002df4  test    eax, eax
0x180002df6  jnz     short loc_180002E33
0x180002df8  call    cs:__imp_GetLastError
0x180002dfe  mov     ebx, eax
0x180002e00  test    eax, eax
0x180002e02  jle     short loc_180002E0D
0x180002e04  movzx   ebx, ax
0x180002e07  or      ebx, 80070000h
0x180002e0d  test    ebx, ebx
0x180002e0f  mov     eax, 80004005h
0x180002e14  cmovns  ebx, eax
0x180002e17  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e1e  cmp     rcx, rdi
0x180002e21  jz      short loc_180002E35
0x180002e23  test    byte ptr [rcx+1Ch], 1
0x180002e27  jz      short loc_180002E35
0x180002e29  mov     edx, 38h ; '8'
0x180002e2e  jmp     loc_180002D6E
0x180002e33  xor     ebx, ebx
0x180002e35  mov     eax, ebx
0x180002e37  mov     rcx, [rsp+248h+var_18]
0x180002e3f  xor     rcx, rsp; StackCookie
0x180002e42  call    __security_check_cookie
0x180002e47  lea     r11, [rsp+248h+var_8]
0x180002e4f  mov     rbx, [r11+18h]
0x180002e53  mov     rsi, [r11+20h]
0x180002e57  mov     rsp, r11
0x180002e5a  pop     rdi
0x180002e5b  retn
```
