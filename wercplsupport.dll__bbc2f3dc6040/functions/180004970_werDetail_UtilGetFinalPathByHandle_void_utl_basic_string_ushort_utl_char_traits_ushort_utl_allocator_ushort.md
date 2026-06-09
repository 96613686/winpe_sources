# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180004970`
- end: `0x180004d22`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1800045cc`
- `0x180005e04`

## callees

- `0x18000131c`
- `0x180001680`
- `0x180002ad0`
- `0x180004970`
- `0x180004d28`
- `0x180006b64`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004a6b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004c19`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004a6b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180004c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c42`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  int FinalPathOnUnmountedVolume; // ebx
  int *v5; // rax
  int *v6; // rcx
  char *v7; // rdx
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
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = byte_180018913;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, v7, 0, 0, 4, v21);
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
      if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018389, 0, 0, 3, v21);
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
    if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018D83, 0, 0, 3, v21);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
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
        if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_18001C008, byte_180018ADD, 0, 0, 3, v21);
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
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a2,
      &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_18001C008 > 2 && (qword_18001C018 & 8) != 0 && (qword_18001C020 & 8) == qword_18001C020 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = byte_180018A15;
    goto LABEL_6;
  }
LABEL_44:
  if ( lpszFilePath != v20 )
    operator delete(lpszFilePath);
  return (unsigned int)FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x180004970  mov     [rsp-8+arg_10], rbx
0x180004975  mov     [rsp-8+arg_18], rsi
0x18000497a  push    rbp
0x18000497b  push    rdi
0x18000497c  push    r14
0x18000497e  lea     rbp, [rsp-47h]
0x180004983  sub     rsp, 0B0h
0x18000498a  mov     rax, cs:__security_cookie
0x180004991  xor     rax, rsp
0x180004994  mov     [rbp+57h+var_20], rax
0x180004998  lea     rax, [rbp+57h+var_78]
0x18000499c  mov     r14, rdx
0x18000499f  mov     [rbp+57h+lpszFilePath], rax
0x1800049a3  mov     rsi, rcx
0x1800049a6  lea     rax, [rbp+57h+var_78]
0x1800049aa  mov     edi, 105h
0x1800049af  mov     [rbp+57h+var_80], rax
0x1800049b3  lea     rcx, [rbp+57h+lpszFilePath]
0x1800049b7  xor     eax, eax
0x1800049b9  mov     edx, edi
0x1800049bb  mov     [rbp+57h+var_78], ax
0x1800049bf  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x1800049c4  test    al, al
0x1800049c6  jnz     loc_180004A57
0x1800049cc  mov     eax, cs:dword_18001C008
0x1800049d2  mov     ebx, 8007000Eh
0x1800049d7  cmp     eax, 2
0x1800049da  jbe     loc_180004CE3
0x1800049e0  mov     rcx, cs:qword_18001C020
0x1800049e7  mov     rax, cs:qword_18001C018
0x1800049ee  test    al, 8
0x1800049f0  jz      loc_180004CE3
0x1800049f6  mov     rax, rcx
0x1800049f9  and     eax, 8
0x1800049fc  cmp     rax, rcx
0x1800049ff  jnz     loc_180004CE3
0x180004a05  mov     [rbp+57h+var_8C], 8007000Eh
0x180004a0c  lea     rax, [rbp+57h+var_8C]
0x180004a10  mov     [rbp+57h+var_90], edi
0x180004a13  lea     rcx, [rbp+57h+var_90]
0x180004a17  lea     rdx, byte_180018913
0x180004a1e  mov     [rbp+57h+var_40], rcx
0x180004a22  lea     rcx, [rbp+57h+var_60]
0x180004a26  mov     [rbp+57h+var_30], rax
0x180004a2a  mov     eax, 4
0x180004a2f  mov     [rsp+0C0h+var_98], rcx
0x180004a34  mov     [rsp+0C0h+var_A0], eax
0x180004a38  mov     [rbp+57h+var_38], rax
0x180004a3c  mov     [rbp+57h+var_28], rax
0x180004a40  xor     r9d, r9d
0x180004a43  lea     rcx, dword_18001C008
0x180004a4a  xor     r8d, r8d
0x180004a4d  call    _tlgWriteTransfer_EventWriteTransfer
0x180004a52  jmp     loc_180004CE3
0x180004a57  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x180004a5b  xor     r9d, r9d; dwFlags
0x180004a5e  mov     r8, [rbp+57h+var_80]
0x180004a62  mov     rcx, rsi; hFile
0x180004a65  sub     r8, rdx
0x180004a68  sar     r8, 1; cchFilePath
0x180004a6b  call    cs:__imp_GetFinalPathNameByHandleW
0x180004a71  mov     edi, eax
0x180004a73  test    eax, eax
0x180004a75  jnz     loc_180004B15
0x180004a7b  call    cs:__imp_GetLastError
0x180004a81  mov     ebx, eax
0x180004a83  cmp     eax, 3
0x180004a86  jnz     short loc_180004A9A
0x180004a88  mov     rdx, r14
0x180004a8b  mov     rcx, rsi
0x180004a8e  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180004a93  mov     ebx, eax
0x180004a95  jmp     loc_180004CE3
0x180004a9a  test    eax, eax
0x180004a9c  jle     short loc_180004AA7
0x180004a9e  movzx   ebx, ax
0x180004aa1  or      ebx, 80070000h
0x180004aa7  test    ebx, ebx
0x180004aa9  mov     eax, 80004005h
0x180004aae  cmovns  ebx, eax
0x180004ab1  mov     eax, cs:dword_18001C008
0x180004ab7  cmp     eax, 2
0x180004aba  jbe     loc_180004CE3
0x180004ac0  mov     rcx, cs:qword_18001C020
0x180004ac7  mov     rax, cs:qword_18001C018
0x180004ace  test    al, 8
0x180004ad0  jz      loc_180004CE3
0x180004ad6  mov     rax, rcx
0x180004ad9  and     eax, 8
0x180004adc  cmp     rax, rcx
0x180004adf  jnz     loc_180004CE3
0x180004ae5  lea     rax, [rbp+57h+var_90]
0x180004ae9  mov     [rbp+57h+var_90], ebx
0x180004aec  mov     [rbp+57h+var_40], rax
0x180004af0  lea     rdx, byte_180018389
0x180004af7  lea     rax, [rbp+57h+var_60]
0x180004afb  mov     [rbp+57h+var_38], 4
0x180004b03  mov     [rsp+0C0h+var_98], rax
0x180004b08  mov     [rsp+0C0h+var_A0], 3
0x180004b10  jmp     loc_180004A40
0x180004b15  mov     rdx, [rbp+57h+var_80]
0x180004b19  mov     r8, [rbp+57h+lpszFilePath]
0x180004b1d  mov     rax, rdx
0x180004b20  sub     rax, r8
0x180004b23  sar     rax, 1
0x180004b26  cmp     rdi, rax
0x180004b29  jnz     short loc_180004B98
0x180004b2b  mov     eax, cs:dword_18001C008
0x180004b31  mov     ebx, 8000FFFFh
0x180004b36  cmp     eax, 2
0x180004b39  jbe     loc_180004CE3
0x180004b3f  mov     rcx, cs:qword_18001C020
0x180004b46  mov     rax, cs:qword_18001C018
0x180004b4d  test    al, 8
0x180004b4f  jz      loc_180004CE3
0x180004b55  mov     rax, rcx
0x180004b58  and     eax, 8
0x180004b5b  cmp     rax, rcx
0x180004b5e  jnz     loc_180004CE3
0x180004b64  lea     rax, [rbp+57h+var_90]
0x180004b68  mov     [rbp+57h+var_90], 8000FFFFh
0x180004b6f  mov     [rbp+57h+var_40], rax
0x180004b73  lea     rdx, byte_180018D83
0x180004b7a  lea     rax, [rbp+57h+var_60]
0x180004b7e  mov     [rbp+57h+var_38], 4
0x180004b86  mov     [rsp+0C0h+var_98], rax
0x180004b8b  mov     [rsp+0C0h+var_A0], 3
0x180004b93  jmp     loc_180004A40
0x180004b98  jbe     loc_180004CB9
0x180004b9e  mov     rdx, rdi
0x180004ba1  lea     rcx, [rbp+57h+lpszFilePath]
0x180004ba5  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180004baa  test    al, al
0x180004bac  jnz     short loc_180004C05
0x180004bae  mov     eax, cs:dword_18001C008
0x180004bb4  mov     ebx, 8007000Eh
0x180004bb9  cmp     eax, 2
0x180004bbc  jbe     loc_180004CE3
0x180004bc2  mov     rcx, cs:qword_18001C020
0x180004bc9  mov     rax, cs:qword_18001C018
0x180004bd0  test    al, 8
0x180004bd2  jz      loc_180004CE3
0x180004bd8  mov     rax, rcx
0x180004bdb  and     eax, 8
0x180004bde  cmp     rax, rcx
0x180004be1  jnz     loc_180004CE3
0x180004be7  mov     [rbp+57h+var_90], 8007000Eh
0x180004bee  lea     rax, [rbp+57h+var_90]
0x180004bf2  mov     [rbp+57h+var_8C], edi
0x180004bf5  lea     rcx, [rbp+57h+var_8C]
0x180004bf9  lea     rdx, byte_180018A15
0x180004c00  jmp     loc_180004A1E
0x180004c05  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x180004c09  xor     r9d, r9d; dwFlags
0x180004c0c  mov     r8, [rbp+57h+var_80]
0x180004c10  mov     rcx, rsi; hFile
0x180004c13  sub     r8, rdx
0x180004c16  sar     r8, 1; cchFilePath
0x180004c19  call    cs:__imp_GetFinalPathNameByHandleW
0x180004c1f  mov     edi, eax
0x180004c21  test    eax, eax
0x180004c23  jz      short loc_180004C42
0x180004c25  mov     rdx, [rbp+57h+var_80]
0x180004c29  mov     r8, [rbp+57h+lpszFilePath]
0x180004c2d  mov     rcx, rdx
0x180004c30  sub     rcx, r8
0x180004c33  sar     rcx, 1
0x180004c36  cmp     rdi, rcx
0x180004c39  jb      short loc_180004CB9
0x180004c3b  mov     ebx, 6Fh ; 'o'
0x180004c40  jmp     short loc_180004C4E
0x180004c42  call    cs:__imp_GetLastError
0x180004c48  mov     ebx, eax
0x180004c4a  test    eax, eax
0x180004c4c  jle     short loc_180004C57
0x180004c4e  movzx   ebx, bx
0x180004c51  or      ebx, 80070000h
0x180004c57  test    ebx, ebx
0x180004c59  mov     eax, 80004005h
0x180004c5e  cmovns  ebx, eax
0x180004c61  mov     eax, cs:dword_18001C008
0x180004c67  cmp     eax, 2
0x180004c6a  jbe     short loc_180004CE3
0x180004c6c  mov     rcx, cs:qword_18001C020
0x180004c73  mov     rax, cs:qword_18001C018
0x180004c7a  test    al, 8
0x180004c7c  jz      short loc_180004CE3
0x180004c7e  mov     rax, rcx
0x180004c81  and     eax, 8
0x180004c84  cmp     rax, rcx
0x180004c87  jnz     short loc_180004CE3
0x180004c89  lea     rax, [rbp+57h+var_90]
0x180004c8d  mov     [rbp+57h+var_90], ebx
0x180004c90  mov     [rbp+57h+var_40], rax
0x180004c94  lea     rdx, byte_180018ADD
0x180004c9b  lea     rax, [rbp+57h+var_60]
0x180004c9f  mov     [rbp+57h+var_38], 4
0x180004ca7  mov     [rsp+0C0h+var_98], rax
0x180004cac  mov     [rsp+0C0h+var_A0], 3
0x180004cb4  jmp     loc_180004A40
0x180004cb9  sub     rdx, r8
0x180004cbc  mov     eax, edi
0x180004cbe  sar     rdx, 1
0x180004cc1  cmp     rax, rdx
0x180004cc4  jbe     short loc_180004CC8
0x180004cc6  int     2Ch; Windows NT - assertion failure
0x180004cc8  lea     rcx, [r8+rdi*2]
0x180004ccc  xor     eax, eax
0x180004cce  mov     [rbp+57h+var_80], rcx
0x180004cd2  lea     rdx, [rbp+57h+lpszFilePath]
0x180004cd6  mov     [rcx], ax
0x180004cd9  mov     rcx, r14
0x180004cdc  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180004ce1  xor     ebx, ebx
0x180004ce3  mov     rcx, [rbp+57h+lpszFilePath]; Block
0x180004ce7  lea     rax, [rbp+57h+var_78]
0x180004ceb  cmp     rcx, rax
0x180004cee  jz      short loc_180004CFC
0x180004cf0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180004cf7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004cfc  mov     eax, ebx
0x180004cfe  mov     rcx, [rbp+57h+var_20]
0x180004d02  xor     rcx, rsp; StackCookie
0x180004d05  call    __security_check_cookie
0x180004d0a  lea     r11, [rsp+0C0h+var_10]
0x180004d12  mov     rbx, [r11+30h]
0x180004d16  mov     rsi, [r11+38h]
0x180004d1a  mov     rsp, r11
0x180004d1d  pop     r14
0x180004d1f  pop     rdi
0x180004d20  pop     rbp
0x180004d21  retn
```
