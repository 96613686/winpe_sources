# WdcLegacyReader::Load(ushort const *)

- ea: `0x18002bedc`
- end: `0x18002c20f`
- name: `?Load@WdcLegacyReader@@QEAAJPEBG@Z`
- size: `819`
- prototype: `int(WdcLegacyReader *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180059d08`
- `0x18006bfc0`

## callees

- `0x180008ab0`
- `0x18000b854`
- `0x18002bedc`
- `0x18006b510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c0fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002c0fb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c0bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c0d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c111`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c12f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c14a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c0bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c0d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c111`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c12f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002c14a`
- `KERNEL32!ReadFile` at `0x18002bffb`
- `KERNEL32!ReadFile` at `0x18002c05d`
- `KERNEL32!ReadFile` at `0x18002bffb`
- `KERNEL32!ReadFile` at `0x18002c05d`
- `KERNEL32!CreateFileW` at `0x18002bf5c`
- `KERNEL32!CreateFileW` at `0x18002bf5c`
- `KERNEL32!GetFileSize` at `0x18002bfa3`
- `KERNEL32!GetFileSize` at `0x18002bfa3`
- `KERNEL32!CloseHandle` at `0x18002c1f6`
- `KERNEL32!CloseHandle` at `0x18002c1f6`
- `KERNEL32!GetLastError` at `0x18002bf70`
- `KERNEL32!GetLastError` at `0x18002c005`
- `KERNEL32!GetLastError` at `0x18002c06b`
- `KERNEL32!GetLastError` at `0x18002bf70`
- `KERNEL32!GetLastError` at `0x18002c005`
- `KERNEL32!GetLastError` at `0x18002c06b`

## string_xrefs

- `0x18002bf1c`: `WdcLegacyReader::Load`
- `0x18002c1d6`: `WdcLegacyReader::Load`

## pseudocode

```c
__int64 __fastcall WdcLegacyReader::Load(LPVOID *this, const char *a2, int a3)
{
  int v5; // eax
  signed int v6; // ebx
  char *FileW; // rax
  char *v8; // rsi
  signed int LastError; // eax
  DWORD FileSize; // eax
  const char *v11; // rdx
  int v12; // r8d
  unsigned __int64 v13; // rdi
  void *v14; // rax
  int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  wchar_t *v18; // rdi
  wchar_t *v19; // rax
  wchar_t *v20; // rbp
  wchar_t *v21; // rax
  const char *v22; // rdx
  int v23; // r8d
  WdcLegacyReader *v24; // rax
  WdcLegacyReader **v25; // rdx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-48h]
  __int16 Buffer; // [rsp+80h] [rbp+18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  v5 = WdcLegacyReader::Flush((WdcLegacyReader *)this, a2, a3);
  v6 = v5;
  if ( v5 < 0 )
  {
    dwCreationDisposition[0] = v5;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
      "WdcLegacyReader::Load",
      0,
      L"FAILURE: 0x%08x",
      *(_QWORD *)dwCreationDisposition);
    return (unsigned int)v6;
  }
  FileW = (char *)CreateFileW((LPCWSTR)a2, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v8 = FileW;
  if ( !FileW || FileW == (char *)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_13;
    }
    else
    {
      v6 = -2147467259;
    }
    dwCreationDisposition[0] = v6;
    goto LABEL_3;
  }
LABEL_13:
  FileSize = GetFileSize(v8, 0);
  v13 = FileSize;
  if ( (FileSize & 1) != 0 )
  {
LABEL_14:
    v6 = -2147023266;
    goto LABEL_47;
  }
  v14 = WdcAlloc(FileSize, v11, v12);
  this[3] = v14;
  if ( v14 )
  {
    if ( !ReadFile(v8, &Buffer, 2u, &NumberOfBytesRead, 0) )
    {
      v16 = GetLastError();
      v6 = v16;
      if ( !v16 )
        goto LABEL_44;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( v6 < 0 )
        goto LABEL_45;
    }
    if ( NumberOfBytesRead != 2 || Buffer != -257 )
      goto LABEL_14;
    if ( ReadFile(v8, this[3], v13, &NumberOfBytesRead, 0) )
    {
      v6 = 0;
      goto LABEL_30;
    }
    v17 = GetLastError();
    v6 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v6 = (unsigned __int16)v17 | 0x80070000;
      if ( v6 >= 0 )
      {
LABEL_30:
        if ( NumberOfBytesRead == v13 - 2 )
        {
          *((_WORD *)this[3] + (v13 >> 1) - 1) = 0;
          v18 = wcstok((wchar_t *)this[3], L"<", 0);
          while ( v18 )
          {
            v19 = wcstok(0, L"=\"><\r\n", 0);
            v18 = v19;
            if ( !v19 )
              break;
            if ( !(unsigned int)_o__wcsnicmp(v19, L"PARAM", 5) )
            {
              v20 = wcstok(0, L"\"", 0);
              if ( !v20 )
                goto LABEL_47;
              if ( !wcstok(0, L"\"", 0) )
                goto LABEL_47;
              v21 = wcstok(0, L"\"\r\n", 0);
              v18 = v21;
              if ( !v21 )
                goto LABEL_47;
              if ( *v21 != 62 && *v21 != 47 )
              {
                v24 = (WdcLegacyReader *)WdcAlloc(0x20u, v22, v23);
                if ( !v24 )
                  goto LABEL_16;
                *(_QWORD *)v24 = 0;
                *((_QWORD *)v24 + 1) = 0;
                *((_QWORD *)v24 + 2) = v20;
                *((_QWORD *)v24 + 3) = v18;
                v25 = (WdcLegacyReader **)this[2];
                if ( *v25 != (WdcLegacyReader *)(this + 1) )
                  __fastfail(3u);
                *(_QWORD *)v24 = this + 1;
                *((_QWORD *)v24 + 1) = v25;
                *v25 = v24;
                this[2] = v24;
              }
            }
          }
          goto LABEL_47;
        }
        goto LABEL_14;
      }
LABEL_45:
      v15 = v6;
      goto LABEL_46;
    }
LABEL_44:
    v6 = -2147467259;
    goto LABEL_45;
  }
LABEL_16:
  v15 = -2147024882;
  v6 = -2147024882;
LABEL_46:
  dwCreationDisposition[0] = v15;
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\legacy.cpp",
    "WdcLegacyReader::Load",
    0,
    L"FAILURE: 0x%08x",
    *(_QWORD *)dwCreationDisposition);
LABEL_47:
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002bedc  mov     r11, rsp
0x18002bedf  mov     [r11+8], rbx
0x18002bee3  push    rbp
0x18002bee4  push    rsi
0x18002bee5  push    rdi
0x18002bee6  push    r12
0x18002bee8  push    r14
0x18002beea  sub     rsp, 40h
0x18002beee  xor     eax, eax
0x18002bef0  mov     dword ptr [r11+20h], 0
0x18002bef8  mov     [r11+18h], ax
0x18002befd  mov     rdi, rdx
0x18002bf00  mov     r14, rcx
0x18002bf03  call    ?Flush@WdcLegacyReader@@AEAAJXZ; WdcLegacyReader::Flush(void)
0x18002bf08  mov     ebx, eax
0x18002bf0a  test    eax, eax
0x18002bf0c  jns     short loc_18002BF34
0x18002bf0e  mov     [rsp+68h+dwCreationDisposition], eax
0x18002bf12  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002bf19  xor     r8d, r8d; int
0x18002bf1c  lea     rdx, aWdclegacyreade_0; "WdcLegacyReader::Load"
0x18002bf23  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18002bf2a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002bf2f  jmp     loc_18002C1FC
0x18002bf34  xor     r9d, r9d; lpSecurityAttributes
0x18002bf37  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002bf40  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002bf48  mov     edx, 80000000h; dwDesiredAccess
0x18002bf4d  mov     rcx, rdi; lpFileName
0x18002bf50  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002bf58  lea     r8d, [r9+3]; dwShareMode
0x18002bf5c  call    cs:__imp_CreateFileW
0x18002bf62  mov     rsi, rax
0x18002bf65  mov     r12d, 80070000h
0x18002bf6b  test    rax, rax
0x18002bf6e  jnz     short loc_18002BF98
0x18002bf70  call    cs:__imp_GetLastError
0x18002bf76  mov     ebx, eax
0x18002bf78  test    eax, eax
0x18002bf7a  jz      short loc_18002BF8A
0x18002bf7c  jle     short loc_18002BF84
0x18002bf7e  movzx   ebx, ax
0x18002bf81  or      ebx, r12d
0x18002bf84  test    ebx, ebx
0x18002bf86  jns     short loc_18002BF9E
0x18002bf88  jmp     short loc_18002BF8F
0x18002bf8a  mov     ebx, 80004005h
0x18002bf8f  mov     [rsp+68h+dwCreationDisposition], ebx
0x18002bf93  jmp     loc_18002BF12
0x18002bf98  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002bf9c  jz      short loc_18002BF70
0x18002bf9e  xor     edx, edx; lpFileSizeHigh
0x18002bfa0  mov     rcx, rsi; hFile
0x18002bfa3  call    cs:__imp_GetFileSize
0x18002bfa9  mov     edi, eax
0x18002bfab  test    al, 1
0x18002bfad  jz      short loc_18002BFB9
0x18002bfaf  mov     ebx, 8007065Eh
0x18002bfb4  jmp     loc_18002C1E9
0x18002bfb9  mov     rcx, rdi; dwBytes
0x18002bfbc  mov     rbp, rdi
0x18002bfbf  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002bfc4  mov     [r14+18h], rax
0x18002bfc8  test    rax, rax
0x18002bfcb  jnz     short loc_18002BFD9
0x18002bfcd  mov     eax, 8007000Eh
0x18002bfd2  mov     ebx, eax
0x18002bfd4  jmp     loc_18002C1C8
0x18002bfd9  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002bfe1  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18002bfea  mov     r8d, 2; nNumberOfBytesToRead
0x18002bff0  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18002bff8  mov     rcx, rsi; hFile
0x18002bffb  call    cs:__imp_ReadFile
0x18002c001  test    eax, eax
0x18002c003  jnz     short loc_18002C025
0x18002c005  call    cs:__imp_GetLastError
0x18002c00b  mov     ebx, eax
0x18002c00d  test    eax, eax
0x18002c00f  jz      loc_18002C1C1
0x18002c015  jle     short loc_18002C01D
0x18002c017  movzx   ebx, ax
0x18002c01a  or      ebx, r12d
0x18002c01d  test    ebx, ebx
0x18002c01f  js      loc_18002C1C6
0x18002c025  cmp     [rsp+68h+NumberOfBytesRead], 2
0x18002c02d  jnz     short loc_18002BFAF
0x18002c02f  mov     eax, 0FEFFh
0x18002c034  cmp     ax, [rsp+68h+Buffer]
0x18002c03c  jnz     loc_18002BFAF
0x18002c042  mov     rdx, [r14+18h]; lpBuffer
0x18002c046  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002c04e  mov     r8d, edi; nNumberOfBytesToRead
0x18002c051  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18002c05a  mov     rcx, rsi; hFile
0x18002c05d  call    cs:__imp_ReadFile
0x18002c063  test    eax, eax
0x18002c065  jz      short loc_18002C06B
0x18002c067  xor     ebx, ebx
0x18002c069  jmp     short loc_18002C08B
0x18002c06b  call    cs:__imp_GetLastError
0x18002c071  mov     ebx, eax
0x18002c073  test    eax, eax
0x18002c075  jz      loc_18002C1C1
0x18002c07b  jle     short loc_18002C083
0x18002c07d  movzx   ebx, ax
0x18002c080  or      ebx, r12d
0x18002c083  test    ebx, ebx
0x18002c085  js      loc_18002C1C6
0x18002c08b  mov     eax, [rsp+68h+NumberOfBytesRead]
0x18002c092  lea     rcx, [rdi-2]
0x18002c096  cmp     rax, rcx
0x18002c099  jnz     loc_18002BFAF
0x18002c09f  mov     rcx, [r14+18h]
0x18002c0a3  lea     rdx, Delimiter; "<"
0x18002c0aa  shr     rbp, 1
0x18002c0ad  xor     eax, eax
0x18002c0af  xor     r8d, r8d; Context
0x18002c0b2  mov     [rcx+rbp*2-2], ax
0x18002c0b7  mov     rcx, [r14+18h]; String
0x18002c0bb  call    cs:__imp_wcstok
0x18002c0c1  mov     rdi, rax
0x18002c0c4  test    rdi, rdi
0x18002c0c7  jz      loc_18002C1E9
0x18002c0cd  xor     r8d, r8d; Context
0x18002c0d0  lea     rdx, asc_1800953C0; "=\"><\r\n"
0x18002c0d7  xor     ecx, ecx; String
0x18002c0d9  call    cs:__imp_wcstok
0x18002c0df  mov     rdi, rax
0x18002c0e2  test    rax, rax
0x18002c0e5  jz      loc_18002C1E9
0x18002c0eb  mov     r8d, 5
0x18002c0f1  lea     rdx, aParam; "PARAM"
0x18002c0f8  mov     rcx, rax
0x18002c0fb  call    cs:__imp__o__wcsnicmp
0x18002c101  test    eax, eax
0x18002c103  jnz     short loc_18002C0C4
0x18002c105  xor     r8d, r8d; Context
0x18002c108  lea     rdx, asc_1800953DC; "\""
0x18002c10f  xor     ecx, ecx; String
0x18002c111  call    cs:__imp_wcstok
0x18002c117  mov     rbp, rax
0x18002c11a  test    rax, rax
0x18002c11d  jz      loc_18002C1E9
0x18002c123  xor     r8d, r8d; Context
0x18002c126  lea     rdx, asc_1800953DC; "\""
0x18002c12d  xor     ecx, ecx; String
0x18002c12f  call    cs:__imp_wcstok
0x18002c135  test    rax, rax
0x18002c138  jz      loc_18002C1E9
0x18002c13e  xor     r8d, r8d; Context
0x18002c141  lea     rdx, asc_1800953E0; "\"\r\n"
0x18002c148  xor     ecx, ecx; String
0x18002c14a  call    cs:__imp_wcstok
0x18002c150  mov     rdi, rax
0x18002c153  test    rax, rax
0x18002c156  jz      loc_18002C1E9
0x18002c15c  cmp     word ptr [rax], 3Eh ; '>'
0x18002c160  jz      loc_18002C0C4
0x18002c166  cmp     word ptr [rax], 2Fh ; '/'
0x18002c16a  jz      loc_18002C0C4
0x18002c170  mov     ecx, 20h ; ' '; dwBytes
0x18002c175  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002c17a  test    rax, rax
0x18002c17d  jz      loc_18002BFCD
0x18002c183  mov     qword ptr [rax], 0
0x18002c18a  lea     rcx, [r14+8]
0x18002c18e  mov     qword ptr [rax+8], 0
0x18002c196  mov     [rax+10h], rbp
0x18002c19a  mov     [rax+18h], rdi
0x18002c19e  mov     rdx, [rcx+8]
0x18002c1a2  cmp     [rdx], rcx
0x18002c1a5  jnz     short loc_18002C1BA
0x18002c1a7  mov     [rax], rcx
0x18002c1aa  mov     [rax+8], rdx
0x18002c1ae  mov     [rdx], rax
0x18002c1b1  mov     [rcx+8], rax
0x18002c1b5  jmp     loc_18002C0C4
0x18002c1ba  mov     ecx, 3
0x18002c1bf  int     29h; Win8: RtlFailFast(ecx)
0x18002c1c1  mov     ebx, 80004005h
0x18002c1c6  mov     eax, ebx
0x18002c1c8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002c1cf  mov     [rsp+68h+dwCreationDisposition], eax
0x18002c1d3  xor     r8d, r8d; int
0x18002c1d6  lea     rdx, aWdclegacyreade_0; "WdcLegacyReader::Load"
0x18002c1dd  lea     rcx, aBaseDiagnosisP_12; "base\\diagnosis\\pdui\\perfmon\\mmc\\le"...
0x18002c1e4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002c1e9  lea     rax, [rsi-1]
0x18002c1ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c1f1  ja      short loc_18002C1FC
0x18002c1f3  mov     rcx, rsi; hObject
0x18002c1f6  call    cs:__imp_CloseHandle
0x18002c1fc  mov     eax, ebx
0x18002c1fe  mov     rbx, [rsp+68h+arg_0]
0x18002c203  add     rsp, 40h
0x18002c207  pop     r14
0x18002c209  pop     r12
0x18002c20b  pop     rdi
0x18002c20c  pop     rsi
0x18002c20d  pop     rbp
0x18002c20e  retn
```
