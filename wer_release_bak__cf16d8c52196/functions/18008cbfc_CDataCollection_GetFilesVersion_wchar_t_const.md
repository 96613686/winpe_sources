# CDataCollection::GetFilesVersion(wchar_t const *)

- ea: `0x18008cbfc`
- end: `0x18008cf48`
- name: `?GetFilesVersion@CDataCollection@@QEAAJPEB_W@Z`
- size: `844`
- prototype: `__int64 __fastcall(CReport **this, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1800429c0`

## callees

- `0x180004bb4`
- `0x180005e34`
- `0x18000716c`
- `0x180007e10`
- `0x18000bc10`
- `0x18000bc2c`
- `0x18000dad0`
- `0x180014720`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001fe24`
- `0x18002b7a4`
- `0x180050db0`
- `0x18008c510`
- `0x18008c848`
- `0x18008cbfc`
- `0x1800974a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008cec3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cda5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cdde`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cda5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008cdde`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008ceea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008ceea`

## pseudocode

```c
__int64 __fastcall CDataCollection::GetFilesVersion(CReport **this, const wchar_t *a2)
{
  int TempFile; // edi
  LPCWSTR *i; // rbx
  _WORD *v6; // rcx
  char *v7; // rbx
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v16; // [rsp+58h] [rbp-A8h]
  _WORD *v17; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v18; // [rsp+78h] [rbp-88h]
  _QWORD v19[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-50h] BYREF

  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v19);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v17);
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
        v6 = v17;
        v18 = v17;
        *v17 = 0;
        CDataCollection::GetFileVersionInformation(v6, *i, &v17);
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpBuffer, v17, v18 - v17);
      }
    }
  }
  if ( lpBuffer == v16 )
    goto LABEL_36;
  TempFile = UtilGetTempFile(&hFile, 0, L".version.txt", FileName);
  v7 = (char *)hFile;
  if ( TempFile >= 0 )
  {
    if ( WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
    {
      if ( WriteFile(v7, lpBuffer, 2 * ((v16 - (_BYTE *)lpBuffer) >> 1), &NumberOfBytesWritten, 0)
        && NumberOfBytesWritten == 2 * ((v16 - (_BYTE *)lpBuffer) >> 1) )
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
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v17);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(v19);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x18008cbfc  mov     [rsp-8+arg_10], rbx
0x18008cc01  mov     [rsp-8+arg_18], rsi
0x18008cc06  push    rbp
0x18008cc07  push    rdi
0x18008cc08  push    r14
0x18008cc0a  lea     rbp, [rsp-1D0h]
0x18008cc12  sub     rsp, 2D0h
0x18008cc19  mov     rax, cs:__security_cookie
0x18008cc20  xor     rax, rsp
0x18008cc23  mov     [rbp+1E0h+var_20], rax
0x18008cc2a  mov     rbx, rdx
0x18008cc2d  mov     rsi, rcx
0x18008cc30  lea     rcx, [rbp+1E0h+var_250]
0x18008cc34  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18008cc39  nop
0x18008cc3a  lea     rcx, [rsp+2E0h+var_270]; void *
0x18008cc3f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008cc44  nop
0x18008cc45  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x18008cc4a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008cc4f  nop
0x18008cc50  xor     r14d, r14d
0x18008cc53  mov     [rsp+2E0h+hFile], r14
0x18008cc58  mov     eax, 0FEFFh
0x18008cc5d  mov     [rsp+2E0h+Buffer], ax
0x18008cc62  mov     [rsp+2E0h+NumberOfBytesWritten], r14d
0x18008cc67  mov     [rbp+1E0h+FileName], r14w
0x18008cc6c  test    rbx, rbx
0x18008cc6f  jnz     short loc_18008CCA7
0x18008cc71  lea     rax, WPP_GLOBAL_Control
0x18008cc78  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cc7f  cmp     rcx, rax
0x18008cc82  jz      short loc_18008CC9D
0x18008cc84  test    byte ptr [rcx+1Ch], 1
0x18008cc88  jz      short loc_18008CC9D
0x18008cc8a  lea     edx, [rbx+3Ch]
0x18008cc8d  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008cc94  mov     rcx, [rcx+10h]
0x18008cc98  call    WPP_SF_
0x18008cc9d  mov     edi, 80070057h
0x18008cca2  jmp     loc_18008CEF5
0x18008cca7  lea     r8, [rbp+1E0h+var_250]
0x18008ccab  mov     rdx, rbx
0x18008ccae  mov     rcx, rsi
0x18008ccb1  call    ?ExpandMultipleFileList@CDataCollection@@AEAAJPEB_WAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@@Z; CDataCollection::ExpandMultipleFileList(wchar_t const *,utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &)
0x18008ccb6  test    eax, eax
0x18008ccb8  js      short loc_18008CD0B
0x18008ccba  mov     rbx, [rbp+1E0h+var_250]
0x18008ccbe  cmp     rbx, [rbp+1E0h+var_248]
0x18008ccc2  jz      short loc_18008CD0B
0x18008ccc4  mov     rcx, [rbx]; lpSrc
0x18008ccc7  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x18008cccc  test    al, al
0x18008ccce  jz      short loc_18008CD05
0x18008ccd0  mov     rcx, [rsp+2E0h+var_270]
0x18008ccd5  mov     [rsp+2E0h+var_268], rcx
0x18008ccda  mov     [rcx], r14w
0x18008ccde  lea     r8, [rsp+2E0h+var_270]
0x18008cce3  mov     rdx, [rbx]
0x18008cce6  call    ?GetFileVersionInformation@CDataCollection@@AEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CDataCollection::GetFileVersionInformation(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008cceb  mov     r8, [rsp+2E0h+var_268]
0x18008ccf0  mov     rdx, [rsp+2E0h+var_270]
0x18008ccf5  sub     r8, rdx
0x18008ccf8  sar     r8, 1
0x18008ccfb  lea     rcx, [rsp+2E0h+lpBuffer]
0x18008cd00  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18008cd05  add     rbx, 20h ; ' '
0x18008cd09  jmp     short loc_18008CCBE
0x18008cd0b  mov     rax, [rsp+2E0h+var_288]
0x18008cd10  cmp     [rsp+2E0h+lpBuffer], rax
0x18008cd15  jz      loc_18008CEF2
0x18008cd1b  mov     [rsp+2E0h+var_2A8], r14d
0x18008cd20  mov     [rsp+2E0h+var_2B0], 1
0x18008cd28  mov     [rsp+2E0h+var_2B8], r14
0x18008cd2d  lea     r9, [rbp+1E0h+FileName]
0x18008cd31  lea     r8, aVersionTxt; ".version.txt"
0x18008cd38  xor     edx, edx
0x18008cd3a  lea     rcx, [rsp+2E0h+hFile]
0x18008cd3f  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18008cd44  mov     edi, eax
0x18008cd46  mov     rbx, [rsp+2E0h+hFile]
0x18008cd4b  test    eax, eax
0x18008cd4d  jns     short loc_18008CD8D
0x18008cd4f  lea     rax, WPP_GLOBAL_Control
0x18008cd56  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cd5d  cmp     rcx, rax
0x18008cd60  jz      loc_18008CED6
0x18008cd66  test    byte ptr [rcx+1Ch], 1
0x18008cd6a  jz      loc_18008CED6
0x18008cd70  mov     edx, 3Dh ; '='
0x18008cd75  mov     r9d, edi
0x18008cd78  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008cd7f  mov     rcx, [rcx+10h]
0x18008cd83  call    WPP_SF_d
0x18008cd88  jmp     loc_18008CED6
0x18008cd8d  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x18008cd92  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008cd97  mov     r8d, 2; nNumberOfBytesToWrite
0x18008cd9d  lea     rdx, [rsp+2E0h+Buffer]; lpBuffer
0x18008cda2  mov     rcx, rbx; hFile
0x18008cda5  call    cs:__imp_WriteFile
0x18008cdab  test    eax, eax
0x18008cdad  jz      loc_18008CE95
0x18008cdb3  cmp     [rsp+2E0h+NumberOfBytesWritten], 2
0x18008cdb8  jnz     loc_18008CE95
0x18008cdbe  mov     rdx, [rsp+2E0h+lpBuffer]; lpBuffer
0x18008cdc3  mov     r8, [rsp+2E0h+var_288]
0x18008cdc8  sub     r8, rdx
0x18008cdcb  sar     r8, 1
0x18008cdce  add     r8d, r8d; nNumberOfBytesToWrite
0x18008cdd1  mov     [rsp+2E0h+lpOverlapped], r14; lpOverlapped
0x18008cdd6  lea     r9, [rsp+2E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008cddb  mov     rcx, rbx; hFile
0x18008cdde  call    cs:__imp_WriteFile
0x18008cde4  test    eax, eax
0x18008cde6  jz      loc_18008CE75
0x18008cdec  mov     rcx, [rsp+2E0h+var_288]
0x18008cdf1  sub     rcx, [rsp+2E0h+lpBuffer]
0x18008cdf6  sar     rcx, 1
0x18008cdf9  add     rcx, rcx
0x18008cdfc  mov     eax, [rsp+2E0h+NumberOfBytesWritten]
0x18008ce00  cmp     rax, rcx
0x18008ce03  jnz     short loc_18008CE75
0x18008ce05  mov     [rsp+2E0h+var_2B8], r14; wchar_t *
0x18008ce0a  lea     rax, aFileverTxt; "FileVer.txt"
0x18008ce11  mov     [rsp+2E0h+lpOverlapped], rax; wchar_t *
0x18008ce16  lea     r9, [rbp+1E0h+FileName]; wchar_t *
0x18008ce1a  mov     edx, 5; enum _WER_FILE_TYPE
0x18008ce1f  lea     r8d, [rdx-2]; unsigned int
0x18008ce23  mov     rcx, [rsi]; this
0x18008ce26  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18008ce2b  mov     edi, eax
0x18008ce2d  test    eax, eax
0x18008ce2f  jns     loc_18008CEF2
0x18008ce35  lea     rax, WPP_GLOBAL_Control
0x18008ce3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce43  cmp     rcx, rax
0x18008ce46  jz      loc_18008CED6
0x18008ce4c  test    byte ptr [rcx+1Ch], 1
0x18008ce50  jz      loc_18008CED6
0x18008ce56  mov     edx, 40h ; '@'
0x18008ce5b  mov     dword ptr [rsp+2E0h+lpOverlapped], edi
0x18008ce5f  lea     r9, [rbp+1E0h+FileName]
0x18008ce63  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008ce6a  mov     rcx, [rcx+10h]
0x18008ce6e  call    WPP_SF_SD
0x18008ce73  jmp     short loc_18008CED6
0x18008ce75  lea     rax, WPP_GLOBAL_Control
0x18008ce7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ce83  cmp     rcx, rax
0x18008ce86  jz      short loc_18008CEC3
0x18008ce88  test    byte ptr [rcx+1Ch], 1
0x18008ce8c  jz      short loc_18008CEC3
0x18008ce8e  mov     edx, 3Fh ; '?'
0x18008ce93  jmp     short loc_18008CEB3
0x18008ce95  lea     rax, WPP_GLOBAL_Control
0x18008ce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008cea3  cmp     rcx, rax
0x18008cea6  jz      short loc_18008CEC3
0x18008cea8  test    byte ptr [rcx+1Ch], 1
0x18008ceac  jz      short loc_18008CEC3
0x18008ceae  mov     edx, 3Eh ; '>'
0x18008ceb3  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008ceba  mov     rcx, [rcx+10h]
0x18008cebe  call    WPP_SF_
0x18008cec3  call    cs:__imp_GetLastError
0x18008cec9  mov     ecx, eax; unsigned int
0x18008cecb  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008ced0  mov     edi, eax
0x18008ced2  test    eax, eax
0x18008ced4  jns     short loc_18008CEF5
0x18008ced6  inc     rbx
0x18008ced9  cmp     rbx, 1
0x18008cedd  jbe     short loc_18008CEF5
0x18008cedf  cmp     [rbp+1E0h+FileName], r14w
0x18008cee4  jz      short loc_18008CEF5
0x18008cee6  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x18008ceea  call    cs:__imp_DeleteFileW
0x18008cef0  jmp     short loc_18008CEF5
0x18008cef2  mov     edi, r14d
0x18008cef5  lea     rcx, [rsp+2E0h+hFile]
0x18008cefa  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18008ceff  nop
0x18008cf00  lea     rcx, [rsp+2E0h+lpBuffer]; void *
0x18008cf05  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008cf0a  nop
0x18008cf0b  lea     rcx, [rsp+2E0h+var_270]; void *
0x18008cf10  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008cf15  nop
0x18008cf16  lea     rcx, [rbp+1E0h+var_250]
0x18008cf1a  call    ?_Uninit@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_Uninit(void)
0x18008cf1f  mov     eax, edi
0x18008cf21  mov     rcx, [rbp+1E0h+var_20]
0x18008cf28  xor     rcx, rsp; StackCookie
0x18008cf2b  call    __security_check_cookie
0x18008cf30  lea     r11, [rsp+2E0h+var_10]
0x18008cf38  mov     rbx, [r11+30h]
0x18008cf3c  mov     rsi, [r11+38h]
0x18008cf40  mov     rsp, r11
0x18008cf43  pop     r14
0x18008cf45  pop     rdi
0x18008cf46  pop     rbp
0x18008cf47  retn
```
