# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x18000e8a8`
- end: `0x18000ec5a`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800106f4`
- `0x1800127a8`

## callees

- `0x18000113c`
- `0x1800029d0`
- `0x1800029f4`
- `0x180008dac`
- `0x18000e8a8`
- `0x18000ec60`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb7a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000e9a3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000eb51`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000e9a3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18000eb51`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  signed int FinalPathOnUnmountedVolume; // ebx
  int *v5; // rax
  int *v6; // rcx
  __int16 *v7; // rdx
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v9; // rdi
  signed int LastError; // eax
  WCHAR *v11; // rdx
  LPWSTR v12; // r8
  unsigned __int64 v13; // rax
  DWORD v14; // eax
  int v16; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+34h] [rbp-35h] BYREF
  LPWSTR lpszFilePath; // [rsp+38h] [rbp-31h] BYREF
  WCHAR *v19; // [rsp+40h] [rbp-29h]
  _WORD v20[12]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]
  int *v24; // [rsp+90h] [rbp+27h]
  __int64 v25; // [rsp+98h] [rbp+2Fh]

  lpszFilePath = v20;
  v19 = v20;
  v20[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = &word_18003ED9E;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180047000, v7, 0, 0, 4, v21);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
  v9 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    FinalPathOnUnmountedVolume = LastError;
    if ( LastError == 3 )
    {
      FinalPathOnUnmountedVolume = _werDetail::UtilGetFinalPathOnUnmountedVolume(hFile, a2);
    }
    else
    {
      if ( LastError > 0 )
        FinalPathOnUnmountedVolume = (unsigned __int16)LastError | 0x80070000;
      if ( FinalPathOnUnmountedVolume >= 0 )
        FinalPathOnUnmountedVolume = -2147467259;
      if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180047000, word_18003ED6A, 0, 0, 3, v21);
      }
    }
    goto LABEL_44;
  }
  v11 = v19;
  v12 = lpszFilePath;
  v13 = v19 - lpszFilePath;
  if ( v9 == v13 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180047000, byte_18003ED2D, 0, 0, 3, v21);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &lpszFilePath,
                          v9) )
  {
    v14 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
    v9 = v14;
    if ( !v14 )
    {
      FinalPathOnUnmountedVolume = GetLastError();
      if ( FinalPathOnUnmountedVolume <= 0 )
      {
LABEL_35:
        if ( FinalPathOnUnmountedVolume >= 0 )
          FinalPathOnUnmountedVolume = -2147467259;
        if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_180047000, word_18003ECB2, 0, 0, 3, v21);
        }
        goto LABEL_44;
      }
LABEL_34:
      FinalPathOnUnmountedVolume = (unsigned __int16)FinalPathOnUnmountedVolume | 0x80070000;
      goto LABEL_35;
    }
    v11 = v19;
    v12 = lpszFilePath;
    if ( v14 >= (unsigned __int64)(v19 - lpszFilePath) )
    {
      LOWORD(FinalPathOnUnmountedVolume) = 111;
      goto LABEL_34;
    }
LABEL_41:
    if ( (unsigned int)v9 > (unsigned __int64)(v11 - v12) )
      __int2c();
    v19 = &v12[v9];
    *v19 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = &word_18003ECE6;
    goto LABEL_6;
  }
LABEL_44:
  if ( lpszFilePath != v20 )
    operator delete(lpszFilePath, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x18000e8a8  mov     [rsp-8+arg_10], rbx
0x18000e8ad  mov     [rsp-8+arg_18], rsi
0x18000e8b2  push    rbp
0x18000e8b3  push    rdi
0x18000e8b4  push    r14
0x18000e8b6  lea     rbp, [rsp-47h]
0x18000e8bb  sub     rsp, 0B0h
0x18000e8c2  mov     rax, cs:__security_cookie
0x18000e8c9  xor     rax, rsp
0x18000e8cc  mov     [rbp+57h+var_20], rax
0x18000e8d0  lea     rax, [rbp+57h+var_78]
0x18000e8d4  mov     r14, rdx
0x18000e8d7  mov     [rbp+57h+lpszFilePath], rax
0x18000e8db  mov     rsi, rcx
0x18000e8de  lea     rax, [rbp+57h+var_78]
0x18000e8e2  mov     edi, 105h
0x18000e8e7  mov     [rbp+57h+var_80], rax
0x18000e8eb  lea     rcx, [rbp+57h+lpszFilePath]
0x18000e8ef  xor     eax, eax
0x18000e8f1  mov     edx, edi
0x18000e8f3  mov     [rbp+57h+var_78], ax
0x18000e8f7  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18000e8fc  test    al, al
0x18000e8fe  jnz     loc_18000E98F
0x18000e904  mov     eax, cs:dword_180047000
0x18000e90a  mov     ebx, 8007000Eh
0x18000e90f  cmp     eax, 2
0x18000e912  jbe     loc_18000EC1B
0x18000e918  mov     rcx, cs:qword_180047018
0x18000e91f  mov     rax, cs:qword_180047010
0x18000e926  test    al, 8
0x18000e928  jz      loc_18000EC1B
0x18000e92e  mov     rax, rcx
0x18000e931  and     eax, 8
0x18000e934  cmp     rax, rcx
0x18000e937  jnz     loc_18000EC1B
0x18000e93d  mov     [rbp+57h+var_8C], 8007000Eh
0x18000e944  lea     rax, [rbp+57h+var_8C]
0x18000e948  mov     [rbp+57h+var_90], edi
0x18000e94b  lea     rcx, [rbp+57h+var_90]
0x18000e94f  lea     rdx, word_18003ED9E
0x18000e956  mov     [rbp+57h+var_40], rcx
0x18000e95a  lea     rcx, [rbp+57h+var_60]
0x18000e95e  mov     [rbp+57h+var_30], rax
0x18000e962  mov     eax, 4
0x18000e967  mov     [rsp+0C0h+var_98], rcx
0x18000e96c  mov     [rsp+0C0h+var_A0], eax
0x18000e970  mov     [rbp+57h+var_38], rax
0x18000e974  mov     [rbp+57h+var_28], rax
0x18000e978  xor     r9d, r9d
0x18000e97b  lea     rcx, dword_180047000
0x18000e982  xor     r8d, r8d
0x18000e985  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e98a  jmp     loc_18000EC1B
0x18000e98f  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x18000e993  xor     r9d, r9d; dwFlags
0x18000e996  mov     r8, [rbp+57h+var_80]
0x18000e99a  mov     rcx, rsi; hFile
0x18000e99d  sub     r8, rdx
0x18000e9a0  sar     r8, 1; cchFilePath
0x18000e9a3  call    cs:__imp_GetFinalPathNameByHandleW
0x18000e9a9  mov     edi, eax
0x18000e9ab  test    eax, eax
0x18000e9ad  jnz     loc_18000EA4D
0x18000e9b3  call    cs:__imp_GetLastError
0x18000e9b9  mov     ebx, eax
0x18000e9bb  cmp     eax, 3
0x18000e9be  jnz     short loc_18000E9D2
0x18000e9c0  mov     rdx, r14
0x18000e9c3  mov     rcx, rsi
0x18000e9c6  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18000e9cb  mov     ebx, eax
0x18000e9cd  jmp     loc_18000EC1B
0x18000e9d2  test    eax, eax
0x18000e9d4  jle     short loc_18000E9DF
0x18000e9d6  movzx   ebx, ax
0x18000e9d9  or      ebx, 80070000h
0x18000e9df  test    ebx, ebx
0x18000e9e1  mov     eax, 80004005h
0x18000e9e6  cmovns  ebx, eax
0x18000e9e9  mov     eax, cs:dword_180047000
0x18000e9ef  cmp     eax, 2
0x18000e9f2  jbe     loc_18000EC1B
0x18000e9f8  mov     rcx, cs:qword_180047018
0x18000e9ff  mov     rax, cs:qword_180047010
0x18000ea06  test    al, 8
0x18000ea08  jz      loc_18000EC1B
0x18000ea0e  mov     rax, rcx
0x18000ea11  and     eax, 8
0x18000ea14  cmp     rax, rcx
0x18000ea17  jnz     loc_18000EC1B
0x18000ea1d  lea     rax, [rbp+57h+var_90]
0x18000ea21  mov     [rbp+57h+var_90], ebx
0x18000ea24  mov     [rbp+57h+var_40], rax
0x18000ea28  lea     rdx, word_18003ED6A
0x18000ea2f  lea     rax, [rbp+57h+var_60]
0x18000ea33  mov     [rbp+57h+var_38], 4
0x18000ea3b  mov     [rsp+0C0h+var_98], rax
0x18000ea40  mov     [rsp+0C0h+var_A0], 3
0x18000ea48  jmp     loc_18000E978
0x18000ea4d  mov     rdx, [rbp+57h+var_80]
0x18000ea51  mov     r8, [rbp+57h+lpszFilePath]
0x18000ea55  mov     rax, rdx
0x18000ea58  sub     rax, r8
0x18000ea5b  sar     rax, 1
0x18000ea5e  cmp     rdi, rax
0x18000ea61  jnz     short loc_18000EAD0
0x18000ea63  mov     eax, cs:dword_180047000
0x18000ea69  mov     ebx, 8000FFFFh
0x18000ea6e  cmp     eax, 2
0x18000ea71  jbe     loc_18000EC1B
0x18000ea77  mov     rcx, cs:qword_180047018
0x18000ea7e  mov     rax, cs:qword_180047010
0x18000ea85  test    al, 8
0x18000ea87  jz      loc_18000EC1B
0x18000ea8d  mov     rax, rcx
0x18000ea90  and     eax, 8
0x18000ea93  cmp     rax, rcx
0x18000ea96  jnz     loc_18000EC1B
0x18000ea9c  lea     rax, [rbp+57h+var_90]
0x18000eaa0  mov     [rbp+57h+var_90], 8000FFFFh
0x18000eaa7  mov     [rbp+57h+var_40], rax
0x18000eaab  lea     rdx, byte_18003ED2D
0x18000eab2  lea     rax, [rbp+57h+var_60]
0x18000eab6  mov     [rbp+57h+var_38], 4
0x18000eabe  mov     [rsp+0C0h+var_98], rax
0x18000eac3  mov     [rsp+0C0h+var_A0], 3
0x18000eacb  jmp     loc_18000E978
0x18000ead0  jbe     loc_18000EBF1
0x18000ead6  mov     rdx, rdi
0x18000ead9  lea     rcx, [rbp+57h+lpszFilePath]
0x18000eadd  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18000eae2  test    al, al
0x18000eae4  jnz     short loc_18000EB3D
0x18000eae6  mov     eax, cs:dword_180047000
0x18000eaec  mov     ebx, 8007000Eh
0x18000eaf1  cmp     eax, 2
0x18000eaf4  jbe     loc_18000EC1B
0x18000eafa  mov     rcx, cs:qword_180047018
0x18000eb01  mov     rax, cs:qword_180047010
0x18000eb08  test    al, 8
0x18000eb0a  jz      loc_18000EC1B
0x18000eb10  mov     rax, rcx
0x18000eb13  and     eax, 8
0x18000eb16  cmp     rax, rcx
0x18000eb19  jnz     loc_18000EC1B
0x18000eb1f  mov     [rbp+57h+var_90], 8007000Eh
0x18000eb26  lea     rax, [rbp+57h+var_90]
0x18000eb2a  mov     [rbp+57h+var_8C], edi
0x18000eb2d  lea     rcx, [rbp+57h+var_8C]
0x18000eb31  lea     rdx, word_18003ECE6
0x18000eb38  jmp     loc_18000E956
0x18000eb3d  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x18000eb41  xor     r9d, r9d; dwFlags
0x18000eb44  mov     r8, [rbp+57h+var_80]
0x18000eb48  mov     rcx, rsi; hFile
0x18000eb4b  sub     r8, rdx
0x18000eb4e  sar     r8, 1; cchFilePath
0x18000eb51  call    cs:__imp_GetFinalPathNameByHandleW
0x18000eb57  mov     edi, eax
0x18000eb59  test    eax, eax
0x18000eb5b  jz      short loc_18000EB7A
0x18000eb5d  mov     rdx, [rbp+57h+var_80]
0x18000eb61  mov     r8, [rbp+57h+lpszFilePath]
0x18000eb65  mov     rcx, rdx
0x18000eb68  sub     rcx, r8
0x18000eb6b  sar     rcx, 1
0x18000eb6e  cmp     rdi, rcx
0x18000eb71  jb      short loc_18000EBF1
0x18000eb73  mov     ebx, 6Fh ; 'o'
0x18000eb78  jmp     short loc_18000EB86
0x18000eb7a  call    cs:__imp_GetLastError
0x18000eb80  mov     ebx, eax
0x18000eb82  test    eax, eax
0x18000eb84  jle     short loc_18000EB8F
0x18000eb86  movzx   ebx, bx
0x18000eb89  or      ebx, 80070000h
0x18000eb8f  test    ebx, ebx
0x18000eb91  mov     eax, 80004005h
0x18000eb96  cmovns  ebx, eax
0x18000eb99  mov     eax, cs:dword_180047000
0x18000eb9f  cmp     eax, 2
0x18000eba2  jbe     short loc_18000EC1B
0x18000eba4  mov     rcx, cs:qword_180047018
0x18000ebab  mov     rax, cs:qword_180047010
0x18000ebb2  test    al, 8
0x18000ebb4  jz      short loc_18000EC1B
0x18000ebb6  mov     rax, rcx
0x18000ebb9  and     eax, 8
0x18000ebbc  cmp     rax, rcx
0x18000ebbf  jnz     short loc_18000EC1B
0x18000ebc1  lea     rax, [rbp+57h+var_90]
0x18000ebc5  mov     [rbp+57h+var_90], ebx
0x18000ebc8  mov     [rbp+57h+var_40], rax
0x18000ebcc  lea     rdx, word_18003ECB2
0x18000ebd3  lea     rax, [rbp+57h+var_60]
0x18000ebd7  mov     [rbp+57h+var_38], 4
0x18000ebdf  mov     [rsp+0C0h+var_98], rax
0x18000ebe4  mov     [rsp+0C0h+var_A0], 3
0x18000ebec  jmp     loc_18000E978
0x18000ebf1  sub     rdx, r8
0x18000ebf4  mov     eax, edi
0x18000ebf6  sar     rdx, 1
0x18000ebf9  cmp     rax, rdx
0x18000ebfc  jbe     short loc_18000EC00
0x18000ebfe  int     2Ch; Windows NT - assertion failure
0x18000ec00  lea     rcx, [r8+rdi*2]
0x18000ec04  xor     eax, eax
0x18000ec06  mov     [rbp+57h+var_80], rcx
0x18000ec0a  lea     rdx, [rbp+57h+lpszFilePath]
0x18000ec0e  mov     [rcx], ax
0x18000ec11  mov     rcx, r14
0x18000ec14  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18000ec19  xor     ebx, ebx
0x18000ec1b  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x18000ec1f  lea     rax, [rbp+57h+var_78]
0x18000ec23  cmp     rcx, rax
0x18000ec26  jz      short loc_18000EC34
0x18000ec28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ec2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ec34  mov     eax, ebx
0x18000ec36  mov     rcx, [rbp+57h+var_20]
0x18000ec3a  xor     rcx, rsp; StackCookie
0x18000ec3d  call    __security_check_cookie
0x18000ec42  lea     r11, [rsp+0C0h+var_10]
0x18000ec4a  mov     rbx, [r11+30h]
0x18000ec4e  mov     rsi, [r11+38h]
0x18000ec52  mov     rsp, r11
0x18000ec55  pop     r14
0x18000ec57  pop     rdi
0x18000ec58  pop     rbp
0x18000ec59  retn
```
