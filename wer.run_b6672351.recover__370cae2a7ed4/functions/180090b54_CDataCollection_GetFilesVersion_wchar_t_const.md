# CDataCollection::GetFilesVersion(wchar_t const *)

- ea: `0x180090b54`
- end: `0x180090eb9`
- name: `?GetFilesVersion@CDataCollection@@QEAAJPEB_W@Z`
- size: `869`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x180044080`

## callees

- `0x180004c64`
- `0x180005be8`
- `0x180006a58`
- `0x180007fd8`
- `0x180008298`
- `0x180008698`
- `0x18000cf50`
- `0x18000db80`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x18002d180`
- `0x180053300`
- `0x180090430`
- `0x180090794`
- `0x180090b54`
- `0x18009b81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180090cfd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180090d3c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180090cfd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180090d3c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180090e54`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180090e54`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDataCollection::GetFilesVersion(CReport **this, const wchar_t *a2)
{
  int TempFile; // edi
  LPCWSTR *i; // rbx
  void *v6; // rcx
  char *v7; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v17; // [rsp+58h] [rbp-A8h]
  void *v18[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v19[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v19);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v18);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  hFile = 0;
  Buffer = -257;
  NumberOfBytesWritten = 0;
  FileName[0] = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    TempFile = -2147024809;
    goto LABEL_37;
  }
  if ( (int)CDataCollection::ExpandMultipleFileList(this, a2, v19) >= 0 )
  {
    for ( i = (LPCWSTR *)v19[0]; i != (LPCWSTR *)v19[1]; i += 4 )
    {
      if ( UtilFileExists(*i) )
      {
        v6 = v18[0];
        v18[1] = v18[0];
        *(_WORD *)v18[0] = 0;
        CDataCollection::GetFileVersionInformation(v6, *i, v18);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpBuffer, v18[0]);
      }
    }
  }
  if ( lpBuffer == v17 )
    goto LABEL_36;
  TempFile = UtilGetTempFile(
               (__int64)&hFile,
               0,
               (const size_t *)L".version.txt",
               FileName,
               (__int64)lpOverlapped,
               0,
               1u,
               0);
  v7 = (char *)hFile;
  if ( TempFile >= 0 )
  {
    if ( WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
    {
      if ( WriteFile(v7, lpBuffer, 2 * ((v17 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == 2 * ((v17 - (_BYTE *)lpBuffer) >> 1) )
      {
        TempFile = CReport::AddFile(*this, WerFileTypeOther, 3u, FileName, L"FileVer.txt", 0);
        if ( TempFile < 0 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
              (unsigned int)FileName,
              TempFile);
          goto LABEL_33;
        }
LABEL_36:
        TempFile = 0;
        goto LABEL_37;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 63;
LABEL_31:
        WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v9 = 62;
        goto LABEL_31;
      }
    }
    LastError = GetLastError();
    TempFile = ERROR_HR_FROM_WIN32(LastError);
    if ( TempFile >= 0 )
      goto LABEL_37;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)TempFile);
LABEL_33:
  if ( v7 != (char *)-1LL && v7 + 1 != (char *)1 && FileName[0] )
    DeleteFileW(FileName);
LABEL_37:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpBuffer);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v18);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(v19);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x180090b54  mov     [rsp-8+arg_10], rbx
0x180090b59  mov     [rsp-8+arg_18], rsi
0x180090b5e  push    rbp
0x180090b5f  push    rdi
0x180090b60  push    r14
0x180090b62  lea     rbp, [rsp-1D0h]
0x180090b6a  sub     rsp, 2D0h
0x180090b71  mov     rax, cs:__security_cookie
0x180090b78  xor     rax, rsp
0x180090b7b  mov     [rbp+1E0h+var_20], rax
0x180090b82  mov     rbx, rdx
0x180090b85  mov     rsi, rcx
0x180090b88  lea     rcx, [rbp+1E0h+var_250]
0x180090b8c  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180090b91  nop
0x180090b92  lea     rcx, [rsp+2E0h+var_270]; void *
0x180090b97  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180090b9c  nop
0x180090b9d  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x180090ba2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180090ba7  nop
0x180090ba8  xor     r14d, r14d
0x180090bab  mov     [rsp+2E0h+hFile], r14
0x180090bb0  mov     eax, 0FEFFh
0x180090bb5  mov     [rsp+2E0h+Buffer], ax
0x180090bba  mov     [rsp+2E0h+NumberOfBytesWritten], r14d
0x180090bbf  mov     [rbp+1E0h+FileName], r14w
0x180090bc4  test    rbx, rbx
0x180090bc7  jnz     short loc_180090BFF
0x180090bc9  lea     rax, WPP_GLOBAL_Control
0x180090bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180090bd7  cmp     rcx, rax
0x180090bda  jz      short loc_180090BF5
0x180090bdc  test    byte ptr [rcx+1Ch], 1
0x180090be0  jz      short loc_180090BF5
0x180090be2  lea     edx, [rbx+3Ch]
0x180090be5  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180090bec  mov     rcx, [rcx+10h]
0x180090bf0  call    WPP_SF_
0x180090bf5  mov     edi, 80070057h
0x180090bfa  jmp     loc_180090E65
0x180090bff  lea     r8, [rbp+1E0h+var_250]
0x180090c03  mov     rdx, rbx
0x180090c06  mov     rcx, rsi
0x180090c09  call    ?ExpandMultipleFileList@CDataCollection@@AEAAJPEB_WAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; CDataCollection::ExpandMultipleFileList(wchar_t const *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x180090c0e  test    eax, eax
0x180090c10  js      short loc_180090C63
0x180090c12  mov     rbx, [rbp+1E0h+var_250]
0x180090c16  cmp     rbx, [rbp+1E0h+var_248]
0x180090c1a  jz      short loc_180090C63
0x180090c1c  mov     rcx, [rbx]; lpSrc
0x180090c1f  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x180090c24  test    al, al
0x180090c26  jz      short loc_180090C5D
0x180090c28  mov     rcx, [rsp+2E0h+var_270]
0x180090c2d  mov     [rsp+2E0h+var_268], rcx
0x180090c32  mov     [rcx], r14w
0x180090c36  lea     r8, [rsp+2E0h+var_270]
0x180090c3b  mov     rdx, [rbx]
0x180090c3e  call    ?GetFileVersionInformation@CDataCollection@@AEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CDataCollection::GetFileVersionInformation(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180090c43  mov     r8, [rsp+2E0h+var_268]
0x180090c48  mov     rdx, [rsp+2E0h+var_270]
0x180090c4d  sub     r8, rdx
0x180090c50  sar     r8, 1
0x180090c53  lea     rcx, [rsp+2E0h+lpBuffer]
0x180090c58  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180090c5d  add     rbx, 20h ; ' '
0x180090c61  jmp     short loc_180090C16
0x180090c63  mov     rax, [rsp+2E0h+var_288]
0x180090c68  cmp     [rsp+2E0h+lpBuffer], rax
0x180090c6d  jz      loc_180090E62
0x180090c73  mov     [rsp+2E0h+var_2A8], r14d
0x180090c78  mov     [rsp+2E0h+var_2B0], 1
0x180090c80  mov     [rsp+2E0h+var_2B8], r14
0x180090c85  lea     r9, [rbp+1E0h+FileName]
0x180090c89  lea     r8, aVersionTxt; ".version.txt"
0x180090c90  xor     edx, edx
0x180090c92  lea     rcx, [rsp+2E0h+hFile]
0x180090c97  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180090c9c  mov     edi, eax
0x180090c9e  mov     rbx, [rsp+2E0h+hFile]
0x180090ca3  test    eax, eax
0x180090ca5  jns     short loc_180090CE5
0x180090ca7  lea     rax, WPP_GLOBAL_Control
0x180090cae  mov     rcx, cs:WPP_GLOBAL_Control
0x180090cb5  cmp     rcx, rax
0x180090cb8  jz      loc_180090E40
0x180090cbe  test    byte ptr [rcx+1Ch], 1
0x180090cc2  jz      loc_180090E40
0x180090cc8  mov     edx, 3Dh ; '='
0x180090ccd  mov     r9d, edi
0x180090cd0  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180090cd7  mov     rcx, [rcx+10h]
0x180090cdb  call    WPP_SF_d
0x180090ce0  jmp     loc_180090E40
0x180090ce5  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x180090cea  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180090cef  mov     r8d, 2; nNumberOfBytesToWrite
0x180090cf5  lea     rdx, [rsp+2E0h+Buffer]; lpBuffer
0x180090cfa  mov     rcx, rbx; hFile
0x180090cfd  call    cs:__imp_WriteFile
0x180090d04  nop     dword ptr [rax+rax+00h]
0x180090d09  test    eax, eax
0x180090d0b  jz      loc_180090DF9
0x180090d11  cmp     [rsp+2E0h+NumberOfBytesWritten], 2
0x180090d16  jnz     loc_180090DF9
0x180090d1c  mov     rdx, [rsp+2E0h+lpBuffer]; lpBuffer
0x180090d21  mov     r8, [rsp+2E0h+var_288]
0x180090d26  sub     r8, rdx
0x180090d29  sar     r8, 1
0x180090d2c  add     r8d, r8d; nNumberOfBytesToWrite
0x180090d2f  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x180090d34  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180090d39  mov     rcx, rbx; hFile
0x180090d3c  call    cs:__imp_WriteFile
0x180090d43  nop     dword ptr [rax+rax+00h]
0x180090d48  test    eax, eax
0x180090d4a  jz      loc_180090DD9
0x180090d50  mov     rcx, [rsp+2E0h+var_288]
0x180090d55  sub     rcx, [rsp+2E0h+lpBuffer]
0x180090d5a  sar     rcx, 1
0x180090d5d  add     rcx, rcx
0x180090d60  mov     eax, [rsp+2E0h+NumberOfBytesWritten]
0x180090d64  cmp     rax, rcx
0x180090d67  jnz     short loc_180090DD9
0x180090d69  mov     [rsp+2E0h+var_2B8], r14; wchar_t *
0x180090d6e  lea     rax, aFileverTxt; "FileVer.txt"
0x180090d75  mov     [rsp+2E0h+lpOverlapped], rax; wchar_t *
0x180090d7a  lea     r9, [rbp+1E0h+FileName]; wchar_t *
0x180090d7e  mov     edx, 5; enum _WER_FILE_TYPE
0x180090d83  lea     r8d, [rdx-2]; unsigned int
0x180090d87  mov     rcx, [rsi]; this
0x180090d8a  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x180090d8f  mov     edi, eax
0x180090d91  test    eax, eax
0x180090d93  jns     loc_180090E62
0x180090d99  lea     rax, WPP_GLOBAL_Control
0x180090da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180090da7  cmp     rcx, rax
0x180090daa  jz      loc_180090E40
0x180090db0  test    byte ptr [rcx+1Ch], 1
0x180090db4  jz      loc_180090E40
0x180090dba  mov     edx, 40h ; '@'
0x180090dbf  mov     dword ptr [rsp+2E0h+lpOverlapped], edi
0x180090dc3  lea     r9, [rbp+1E0h+FileName]
0x180090dc7  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180090dce  mov     rcx, [rcx+10h]
0x180090dd2  call    WPP_SF_SD
0x180090dd7  jmp     short loc_180090E40
0x180090dd9  lea     rax, WPP_GLOBAL_Control
0x180090de0  mov     rcx, cs:WPP_GLOBAL_Control
0x180090de7  cmp     rcx, rax
0x180090dea  jz      short loc_180090E27
0x180090dec  test    byte ptr [rcx+1Ch], 1
0x180090df0  jz      short loc_180090E27
0x180090df2  mov     edx, 3Fh ; '?'
0x180090df7  jmp     short loc_180090E17
0x180090df9  lea     rax, WPP_GLOBAL_Control
0x180090e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180090e07  cmp     rcx, rax
0x180090e0a  jz      short loc_180090E27
0x180090e0c  test    byte ptr [rcx+1Ch], 1
0x180090e10  jz      short loc_180090E27
0x180090e12  mov     edx, 3Eh ; '>'
0x180090e17  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180090e1e  mov     rcx, [rcx+10h]
0x180090e22  call    WPP_SF_
0x180090e27  call    cs:__imp_GetLastError
0x180090e2e  nop     dword ptr [rax+rax+00h]
0x180090e33  mov     ecx, eax; unsigned int
0x180090e35  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180090e3a  mov     edi, eax
0x180090e3c  test    eax, eax
0x180090e3e  jns     short loc_180090E65
0x180090e40  inc     rbx
0x180090e43  cmp     rbx, 1
0x180090e47  jbe     short loc_180090E65
0x180090e49  cmp     [rbp+1E0h+FileName], r14w
0x180090e4e  jz      short loc_180090E65
0x180090e50  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x180090e54  call    cs:__imp_DeleteFileW
0x180090e5b  nop     dword ptr [rax+rax+00h]
0x180090e60  jmp     short loc_180090E65
0x180090e62  mov     edi, r14d
0x180090e65  lea     rcx, [rsp+2E0h+hFile]
0x180090e6a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180090e6f  nop
0x180090e70  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x180090e75  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180090e7a  nop
0x180090e7b  lea     rcx, [rsp+2E0h+var_270]; void *
0x180090e80  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180090e85  nop
0x180090e86  lea     rcx, [rbp+1E0h+var_250]
0x180090e8a  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x180090e8f  mov     eax, edi
0x180090e91  mov     rcx, [rbp+1E0h+var_20]
0x180090e98  xor     rcx, rsp; StackCookie
0x180090e9b  call    __security_check_cookie
0x180090ea0  lea     r11, [rsp+2E0h+var_10]
0x180090ea8  mov     rbx, [r11+30h]
0x180090eac  mov     rsi, [r11+38h]
0x180090eb0  mov     rsp, r11
0x180090eb3  pop     r14
0x180090eb5  pop     rdi
0x180090eb6  pop     rbp
0x180090eb7  retn
```
