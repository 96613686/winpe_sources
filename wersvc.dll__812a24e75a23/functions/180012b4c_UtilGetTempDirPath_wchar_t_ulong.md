# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x180012b4c`
- end: `0x180012e8c`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `832`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180012e94`

## callees

- `0x18000113c`
- `0x18000134c`
- `0x1800029d0`
- `0x1800029f4`
- `0x1800127a8`
- `0x180012b4c`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d47`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180012ba2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180012ba2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180012bba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180012bba`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180012b87`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180012b87`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName)
{
  DWORD FileAttributesW; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  signed int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  signed int v8; // ebx
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rbx
  signed int LastError; // eax
  __int64 v12; // rcx
  int v14; // [rsp+30h] [rbp-39h] BYREF
  WCHAR *v15; // [rsp+38h] [rbp-31h] BYREF
  void *Src; // [rsp+40h] [rbp-29h] BYREF
  char *v17; // [rsp+48h] [rbp-21h]
  _WORD v18[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v19[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v20; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+88h] [rbp+1Fh]

  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v14 = v8;
        v20 = &v14;
        v21 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180047000, word_18003F152, 0, 0, 3, v19);
      }
      goto LABEL_36;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0) && !CreateDirectoryW(lpFileName, 0) )
    {
      v5 = GetLastError();
      v8 = v5;
      if ( v5 > 0 )
        v8 = (unsigned __int16)v5 | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
      {
        v14 = v8;
        v15 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          qword_180047018,
          (__int64)&word_18003F10E,
          v6,
          v7,
          (int **)&v15,
          (__int64)&v14);
      }
      *lpFileName = 0;
LABEL_36:
      if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 )
      {
        v12 = qword_180047018 & 8;
        if ( v12 == qword_180047018 )
        {
          v14 = v8;
          v15 = lpFileName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v12,
            (__int64)byte_18003F0A1,
            v6,
            v7,
            (int **)&v15,
            (__int64)&v14);
        }
      }
      return (unsigned int)v8;
    }
    v18[0] = 0;
    Src = v18;
    v17 = (char *)v18;
    if ( (unsigned int)UtilGetFinalPath((int *)lpFileName, (int **)&Src, v3, v4) )
    {
      v9 = (v17 - (_BYTE *)Src) >> 1;
      if ( v9 >= 0x104 )
      {
        *lpFileName = 0;
        v8 = -2147024809;
        if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
        {
          v14 = -2147024809;
          v20 = &v14;
          v21 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_180047000, word_18003F0DA, 0, 0, 3, v19);
        }
        if ( Src != v18 )
          operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_36;
      }
      v10 = v9;
      memcpy_0(lpFileName, Src, v10 * 2);
      lpFileName[v10] = 0;
    }
    if ( Src != v18 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v8 = 0;
    goto LABEL_36;
  }
  if ( (unsigned int)dword_180047000 > 2 && (qword_180047010 & 8) != 0 && (qword_180047018 & 8) == qword_180047018 )
    tlgWriteTransfer_EventWriteTransfer(&dword_180047000, &word_18003F186, 0, 0, 2, v19);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180012b4c  push    rbp
0x180012b4e  push    rbx
0x180012b4f  push    rdi
0x180012b50  push    r14
0x180012b52  lea     rbp, [rsp-3Fh]
0x180012b57  sub     rsp, 0A8h
0x180012b5e  mov     rax, cs:__security_cookie
0x180012b65  xor     rax, rsp
0x180012b68  mov     [rbp+57h+var_30], rax
0x180012b6c  xor     r14d, r14d
0x180012b6f  mov     rdi, rcx
0x180012b72  test    rcx, rcx
0x180012b75  jz      loc_180012E1C
0x180012b7b  mov     [rcx], r14w
0x180012b7f  mov     rdx, rcx
0x180012b82  mov     ecx, 104h
0x180012b87  call    cs:__imp_GetTempPath2W
0x180012b8d  test    eax, eax
0x180012b8f  jz      loc_180012D47
0x180012b95  cmp     [rdi], r14w
0x180012b99  jz      loc_180012D47
0x180012b9f  mov     rcx, rdi; lpFileName
0x180012ba2  call    cs:__imp_GetFileAttributesW
0x180012ba8  cmp     eax, 0FFFFFFFFh
0x180012bab  jz      short loc_180012BB5
0x180012bad  test    al, 10h
0x180012baf  jnz     loc_180012C39
0x180012bb5  xor     edx, edx; lpSecurityAttributes
0x180012bb7  mov     rcx, rdi; lpPathName
0x180012bba  call    cs:__imp_CreateDirectoryW
0x180012bc0  test    eax, eax
0x180012bc2  jnz     short loc_180012C39
0x180012bc4  call    cs:__imp_GetLastError
0x180012bca  mov     ebx, eax
0x180012bcc  test    eax, eax
0x180012bce  jle     short loc_180012BD9
0x180012bd0  movzx   ebx, ax
0x180012bd3  or      ebx, 80070000h
0x180012bd9  test    ebx, ebx
0x180012bdb  mov     eax, 80004005h
0x180012be0  cmovns  ebx, eax
0x180012be3  mov     eax, cs:dword_180047000
0x180012be9  cmp     eax, 2
0x180012bec  jbe     short loc_180012C30
0x180012bee  mov     rcx, cs:qword_180047018
0x180012bf5  mov     rax, cs:qword_180047010
0x180012bfc  test    al, 8
0x180012bfe  jz      short loc_180012C30
0x180012c00  mov     rax, rcx
0x180012c03  and     eax, 8
0x180012c06  cmp     rax, rcx
0x180012c09  jnz     short loc_180012C30
0x180012c0b  lea     rax, [rbp+57h+var_90]
0x180012c0f  mov     [rbp+57h+var_90], ebx
0x180012c12  mov     [rsp+0C0h+var_98], rax
0x180012c17  lea     rdx, word_18003F10E
0x180012c1e  lea     rax, [rbp+57h+var_88]
0x180012c22  mov     [rbp+57h+var_88], rdi
0x180012c26  mov     [rsp+0C0h+var_A0], rax
0x180012c2b  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180012c30  mov     [rdi], r14w
0x180012c34  jmp     loc_180012DCB
0x180012c39  lea     rax, [rbp+57h+var_70]
0x180012c3d  mov     [rbp+57h+var_70], r14w
0x180012c42  mov     [rbp+57h+Src], rax
0x180012c46  lea     rdx, [rbp+57h+Src]
0x180012c4a  lea     rax, [rbp+57h+var_70]
0x180012c4e  mov     rcx, rdi; lpFileName
0x180012c51  mov     [rbp+57h+var_78], rax
0x180012c55  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180012c5a  test    eax, eax
0x180012c5c  jz      loc_180012D25
0x180012c62  mov     rbx, [rbp+57h+var_78]
0x180012c66  sub     rbx, [rbp+57h+Src]
0x180012c6a  sar     rbx, 1
0x180012c6d  cmp     rbx, 104h
0x180012c74  jb      loc_180012D0E
0x180012c7a  mov     [rdi], r14w
0x180012c7e  mov     ebx, 80070057h
0x180012c83  mov     eax, cs:dword_180047000
0x180012c89  cmp     eax, 2
0x180012c8c  jbe     short loc_180012CEC
0x180012c8e  mov     rcx, cs:qword_180047018
0x180012c95  mov     rax, cs:qword_180047010
0x180012c9c  test    al, 8
0x180012c9e  jz      short loc_180012CEC
0x180012ca0  mov     rax, rcx
0x180012ca3  and     eax, 8
0x180012ca6  cmp     rax, rcx
0x180012ca9  jnz     short loc_180012CEC
0x180012cab  lea     rax, [rbp+57h+var_90]
0x180012caf  mov     [rbp+57h+var_90], 80070057h
0x180012cb6  mov     [rbp+57h+var_40], rax
0x180012cba  lea     rdx, word_18003F0DA
0x180012cc1  lea     rax, [rbp+57h+var_60]
0x180012cc5  mov     [rbp+57h+var_38], 4
0x180012ccd  mov     [rsp+0C0h+var_98], rax
0x180012cd2  lea     rcx, dword_180047000
0x180012cd9  xor     r9d, r9d
0x180012cdc  mov     dword ptr [rsp+0C0h+var_A0], 3
0x180012ce4  xor     r8d, r8d
0x180012ce7  call    _tlgWriteTransfer_EventWriteTransfer
0x180012cec  mov     rcx, [rbp+57h+Src]; void *
0x180012cf0  lea     rax, [rbp+57h+var_70]
0x180012cf4  cmp     rcx, rax
0x180012cf7  jz      loc_180012DCB
0x180012cfd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d09  jmp     loc_180012DCB
0x180012d0e  mov     rdx, [rbp+57h+Src]; Src
0x180012d12  add     rbx, rbx
0x180012d15  mov     r8, rbx; Size
0x180012d18  mov     rcx, rdi; void *
0x180012d1b  call    memcpy_0
0x180012d20  mov     [rbx+rdi], r14w
0x180012d25  lea     rax, [rbp+57h+var_70]
0x180012d29  cmp     [rbp+57h+Src], rax
0x180012d2d  jz      short loc_180012D3F
0x180012d2f  mov     rcx, [rbp+57h+Src]; void *
0x180012d33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012d3a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012d3f  mov     ebx, r14d
0x180012d42  jmp     loc_180012DCB
0x180012d47  call    cs:__imp_GetLastError
0x180012d4d  mov     ebx, eax
0x180012d4f  test    eax, eax
0x180012d51  jle     short loc_180012D5C
0x180012d53  movzx   ebx, ax
0x180012d56  or      ebx, 80070000h
0x180012d5c  test    ebx, ebx
0x180012d5e  mov     eax, 80004005h
0x180012d63  cmovns  ebx, eax
0x180012d66  mov     eax, cs:dword_180047000
0x180012d6c  cmp     eax, 2
0x180012d6f  jbe     short loc_180012DCB
0x180012d71  mov     rcx, cs:qword_180047018
0x180012d78  mov     rax, cs:qword_180047010
0x180012d7f  test    al, 8
0x180012d81  jz      short loc_180012DCB
0x180012d83  mov     rax, rcx
0x180012d86  and     eax, 8
0x180012d89  cmp     rax, rcx
0x180012d8c  jnz     short loc_180012DCB
0x180012d8e  lea     rax, [rbp+57h+var_90]
0x180012d92  mov     [rbp+57h+var_90], ebx
0x180012d95  mov     [rbp+57h+var_40], rax
0x180012d99  lea     rdx, word_18003F152
0x180012da0  lea     rax, [rbp+57h+var_60]
0x180012da4  mov     [rbp+57h+var_38], 4
0x180012dac  mov     [rsp+0C0h+var_98], rax
0x180012db1  lea     rcx, dword_180047000
0x180012db8  xor     r9d, r9d
0x180012dbb  mov     dword ptr [rsp+0C0h+var_A0], 3
0x180012dc3  xor     r8d, r8d
0x180012dc6  call    _tlgWriteTransfer_EventWriteTransfer
0x180012dcb  mov     eax, cs:dword_180047000
0x180012dd1  cmp     eax, 2
0x180012dd4  jbe     short loc_180012E18
0x180012dd6  mov     rdx, cs:qword_180047018
0x180012ddd  mov     rax, cs:qword_180047010
0x180012de4  test    al, 8
0x180012de6  jz      short loc_180012E18
0x180012de8  mov     rcx, rdx
0x180012deb  and     ecx, 8
0x180012dee  cmp     rcx, rdx
0x180012df1  jnz     short loc_180012E18
0x180012df3  lea     rax, [rbp+57h+var_90]
0x180012df7  mov     [rbp+57h+var_90], ebx
0x180012dfa  mov     [rsp+0C0h+var_98], rax
0x180012dff  lea     rdx, byte_18003F0A1
0x180012e06  lea     rax, [rbp+57h+var_88]
0x180012e0a  mov     [rbp+57h+var_88], rdi
0x180012e0e  mov     [rsp+0C0h+var_A0], rax
0x180012e13  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180012e18  mov     eax, ebx
0x180012e1a  jmp     short loc_180012E73
0x180012e1c  mov     eax, cs:dword_180047000
0x180012e22  cmp     eax, 2
0x180012e25  jbe     short loc_180012E6E
0x180012e27  mov     rcx, cs:qword_180047018
0x180012e2e  mov     rax, cs:qword_180047010
0x180012e35  test    al, 8
0x180012e37  jz      short loc_180012E6E
0x180012e39  mov     rax, rcx
0x180012e3c  and     eax, 8
0x180012e3f  cmp     rax, rcx
0x180012e42  jnz     short loc_180012E6E
0x180012e44  lea     rax, [rbp+57h+var_60]
0x180012e48  xor     r9d, r9d
0x180012e4b  mov     [rsp+0C0h+var_98], rax
0x180012e50  lea     rdx, word_18003F186
0x180012e57  xor     r8d, r8d
0x180012e5a  mov     dword ptr [rsp+0C0h+var_A0], 2
0x180012e62  lea     rcx, dword_180047000
0x180012e69  call    _tlgWriteTransfer_EventWriteTransfer
0x180012e6e  mov     eax, 80070057h
0x180012e73  mov     rcx, [rbp+57h+var_30]
0x180012e77  xor     rcx, rsp; StackCookie
0x180012e7a  call    __security_check_cookie
0x180012e7f  add     rsp, 0A8h
0x180012e86  pop     r14
0x180012e88  pop     rdi
0x180012e89  pop     rbx
0x180012e8a  pop     rbp
0x180012e8b  retn
```
