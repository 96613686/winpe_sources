# CDataCollection::AddDataCollectionFailure(wchar_t const *)

- ea: `0x180037cb8`
- end: `0x1800380cc`
- name: `?AddDataCollectionFailure@CDataCollection@@QEAAJPEB_W@Z`
- size: `1044`
- prototype: `int(CDataCollection *__hidden this, const wchar_t *)`
- caller_count: `5`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x180009074`
- `0x180037518`
- `0x180037710`
- `0x1800380d4`
- `0x180044080`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180008254`
- `0x180008298`
- `0x180008698`
- `0x18000cf50`
- `0x18000db80`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x180025848`
- `0x18002a758`
- `0x18002dc4c`
- `0x180037cb8`
- `0x180053300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038074`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037fb0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037fee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e7b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037fb0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037fee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037dde`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037dde`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataCollection::AddDataCollectionFailure(CReport **this, const wchar_t *a2)
{
  int FileByIndex; // edi
  unsigned int i; // r11d
  unsigned int v6; // r11d
  struct CReportFile *v7; // rsi
  int v8; // r11d
  HANDLE FileW; // rax
  HANDLE v10; // rbx
  __int64 v11; // r8
  DWORD LastError; // eax
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD v16; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  struct CReportFile *v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[40]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v23[264]; // [rsp+80h] [rbp-80h] BYREF

  hFile = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v22);
  Buffer = -257;
  NumberOfBytesWritten = 0;
  v21 = 0;
  v23[0] = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    FileByIndex = -2147024809;
    goto LABEL_44;
  }
  for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)*this + 728) - *((_QWORD *)*this + 727)) >> 3); i = v8 + 1 )
  {
    FileByIndex = CReport::GetFileByIndex(*this, i, &v21);
    if ( FileByIndex < 0 || (v7 = v21) == 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          v6,
          FileByIndex);
      goto LABEL_44;
    }
    if ( (unsigned __int8)utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            (char *)v21 + 80,
                            L"WERDataCollectionStatus.txt") )
    {
      FileW = CreateFileW(*((LPCWSTR *)v7 + 14), 4u, 1u, 0, 3u, 0x80u, 0);
      tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
      v10 = hFile;
      if ( (unsigned __int64)hFile + 1 <= 1 )
      {
        LastError = GetLastError();
        FileByIndex = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            *((_QWORD *)v7 + 14),
            FileByIndex);
        goto LABEL_44;
      }
      FileByIndex = UtilVerifyFilePath(*((const wchar_t **)v7 + 14), hFile);
      if ( FileByIndex < 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            (unsigned int)FileByIndex);
        goto LABEL_44;
      }
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      WriteFile(v10, a2, 2 * v11, &NumberOfBytesWritten, 0);
LABEL_20:
      FileByIndex = 0;
      goto LABEL_44;
    }
  }
  FileByIndex = UtilGetTempFile(&hFile, 0, L".WERDataCollectionStatus.txt", v23);
  if ( FileByIndex < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v14 = 108;
    goto LABEL_31;
  }
  if ( WriteFile(hFile, &Buffer, 2u, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == 2 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    WriteFile(hFile, a2, 2 * v15, &NumberOfBytesWritten, 0);
    FileByIndex = CReport::AddFile(*this, WerFileTypeOther, 3u, v23, L"WERDataCollectionStatus.txt", 0);
    if ( FileByIndex >= 0 )
      goto LABEL_20;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_44;
    v14 = 110;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)FileByIndex);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
  v16 = GetLastError();
  FileByIndex = ERROR_HR_FROM_WIN32(v16);
LABEL_44:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v22);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)FileByIndex;
}

```

## disassembly

```asm
0x180037cb8  mov     [rsp-8+arg_10], rbx
0x180037cbd  mov     [rsp-8+arg_18], rsi
0x180037cc2  push    rbp
0x180037cc3  push    rdi
0x180037cc4  push    r12
0x180037cc6  push    r14
0x180037cc8  push    r15
0x180037cca  lea     rbp, [rsp-1A0h]
0x180037cd2  sub     rsp, 2A0h
0x180037cd9  mov     rax, cs:__security_cookie
0x180037ce0  xor     rax, rsp
0x180037ce3  mov     [rbp+1C0h+var_30], rax
0x180037cea  mov     r14, rdx
0x180037ced  mov     rbx, rcx
0x180037cf0  xor     r15d, r15d
0x180037cf3  mov     [rsp+2C0h+hFile], r15
0x180037cf8  lea     rcx, [rsp+2C0h+var_268]; void *
0x180037cfd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180037d02  nop
0x180037d03  mov     eax, 0FEFFh
0x180037d08  mov     [rsp+2C0h+Buffer], ax
0x180037d0d  mov     [rsp+2C0h+NumberOfBytesWritten], r15d
0x180037d12  mov     [rsp+2C0h+var_270], r15
0x180037d17  mov     [rbp+1C0h+var_240], r15w
0x180037d1c  test    r14, r14
0x180037d1f  jnz     short loc_180037D58
0x180037d21  lea     rax, WPP_GLOBAL_Control
0x180037d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180037d2f  cmp     rcx, rax
0x180037d32  jz      short loc_180037D4E
0x180037d34  test    byte ptr [rcx+1Ch], 1
0x180037d38  jz      short loc_180037D4E
0x180037d3a  lea     edx, [r15+68h]
0x180037d3e  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180037d45  mov     rcx, [rcx+10h]
0x180037d49  call    WPP_SF_
0x180037d4e  mov     edi, 80070057h
0x180037d53  jmp     loc_180038089
0x180037d58  mov     r11d, r15d
0x180037d5b  lea     r12, aWerdatacollect_0; "WERDataCollectionStatus.txt"
0x180037d62  mov     rcx, [rbx]; this
0x180037d65  mov     rax, [rcx+16C0h]
0x180037d6c  sub     rax, [rcx+16B8h]
0x180037d73  sar     rax, 3
0x180037d77  cmp     r11d, eax
0x180037d7a  jnb     loc_180037F29
0x180037d80  lea     r8, [rsp+2C0h+var_270]; struct CReportFile **
0x180037d85  mov     edx, r11d; unsigned int
0x180037d88  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x180037d8d  mov     edi, eax
0x180037d8f  test    eax, eax
0x180037d91  js      loc_180037EE7
0x180037d97  mov     rsi, [rsp+2C0h+var_270]
0x180037d9c  test    rsi, rsi
0x180037d9f  jz      loc_180037EE7
0x180037da5  lea     rcx, [rsi+50h]
0x180037da9  mov     rdx, r12
0x180037dac  call    ??$?8_WU?$char_traits@_W@utl@@V?$allocator@_W@1@@utl@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@0@PEB_W@Z; utl::operator==<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &,wchar_t const *)
0x180037db1  test    al, al
0x180037db3  jnz     short loc_180037DBA
0x180037db5  inc     r11d
0x180037db8  jmp     short loc_180037D62
0x180037dba  mov     [rsp+2C0h+hTemplateFile], r15; hTemplateFile
0x180037dbf  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180037dc7  mov     [rsp+2C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180037dcf  xor     r9d, r9d; lpSecurityAttributes
0x180037dd2  lea     edx, [r9+4]; dwDesiredAccess
0x180037dd6  lea     r8d, [r9+1]; dwShareMode
0x180037dda  mov     rcx, [rsi+70h]; lpFileName
0x180037dde  call    cs:__imp_CreateFileW
0x180037de5  nop     dword ptr [rax+rax+00h]
0x180037dea  mov     rdx, rax
0x180037ded  lea     rcx, [rsp+2C0h+hFile]
0x180037df2  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180037df7  mov     rbx, [rsp+2C0h+hFile]
0x180037dfc  lea     rax, [rbx+1]
0x180037e00  cmp     rax, 1
0x180037e04  jbe     loc_180037E8F
0x180037e0a  mov     rdx, rbx; void *
0x180037e0d  mov     rcx, [rsi+70h]; wchar_t *
0x180037e11  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180037e16  mov     edi, eax
0x180037e18  test    eax, eax
0x180037e1a  jns     short loc_180037E5A
0x180037e1c  lea     rax, WPP_GLOBAL_Control
0x180037e23  mov     rcx, cs:WPP_GLOBAL_Control
0x180037e2a  cmp     rcx, rax
0x180037e2d  jz      loc_180038089
0x180037e33  test    byte ptr [rcx+1Ch], 1
0x180037e37  jz      loc_180038089
0x180037e3d  mov     edx, 6Bh ; 'k'
0x180037e42  mov     r9d, edi
0x180037e45  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180037e4c  mov     rcx, [rcx+10h]
0x180037e50  call    WPP_SF_d
0x180037e55  jmp     loc_180038089
0x180037e5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037e5e  inc     r8
0x180037e61  cmp     [r14+r8*2], r15w
0x180037e66  jnz     short loc_180037E5E
0x180037e68  add     r8d, r8d; nNumberOfBytesToWrite
0x180037e6b  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180037e70  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037e75  mov     rdx, r14; lpBuffer
0x180037e78  mov     rcx, rbx; hFile
0x180037e7b  call    cs:__imp_WriteFile
0x180037e82  nop     dword ptr [rax+rax+00h]
0x180037e87  mov     edi, r15d
0x180037e8a  jmp     loc_180038089
0x180037e8f  call    cs:__imp_GetLastError
0x180037e96  nop     dword ptr [rax+rax+00h]
0x180037e9b  mov     ecx, eax; unsigned int
0x180037e9d  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180037ea2  mov     edi, eax
0x180037ea4  lea     rax, WPP_GLOBAL_Control
0x180037eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180037eb2  cmp     rcx, rax
0x180037eb5  jz      loc_180038089
0x180037ebb  test    byte ptr [rcx+1Ch], 1
0x180037ebf  jz      loc_180038089
0x180037ec5  mov     edx, 6Ah ; 'j'
0x180037eca  mov     [rsp+2C0h+dwCreationDisposition], edi
0x180037ece  mov     r9, [rsi+70h]
0x180037ed2  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180037ed9  mov     rcx, [rcx+10h]
0x180037edd  call    WPP_SF_SD
0x180037ee2  jmp     loc_180038089
0x180037ee7  lea     rax, WPP_GLOBAL_Control
0x180037eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ef5  cmp     rcx, rax
0x180037ef8  jz      loc_180038089
0x180037efe  test    byte ptr [rcx+1Ch], 1
0x180037f02  jz      loc_180038089
0x180037f08  mov     edx, 69h ; 'i'
0x180037f0d  mov     [rsp+2C0h+dwCreationDisposition], edi
0x180037f11  mov     r9d, r11d
0x180037f14  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180037f1b  mov     rcx, [rcx+10h]
0x180037f1f  call    WPP_SF_Dd
0x180037f24  jmp     loc_180038089
0x180037f29  mov     [rsp+2C0h+var_288], r15d
0x180037f2e  mov     dword ptr [rsp+2C0h+hTemplateFile], 1
0x180037f36  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15
0x180037f3b  lea     r9, [rbp+1C0h+var_240]
0x180037f3f  lea     r8, aWerdatacollect; ".WERDataCollectionStatus.txt"
0x180037f46  xor     edx, edx
0x180037f48  lea     rcx, [rsp+2C0h+hFile]
0x180037f4d  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180037f52  mov     edi, eax
0x180037f54  test    eax, eax
0x180037f56  jns     short loc_180037F96
0x180037f58  lea     rax, WPP_GLOBAL_Control
0x180037f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f66  cmp     rcx, rax
0x180037f69  jz      loc_180038089
0x180037f6f  test    byte ptr [rcx+1Ch], 1
0x180037f73  jz      loc_180038089
0x180037f79  mov     edx, 6Ch ; 'l'
0x180037f7e  mov     r9d, edi
0x180037f81  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180037f88  mov     rcx, [rcx+10h]
0x180037f8c  call    WPP_SF_d
0x180037f91  jmp     loc_180038089
0x180037f96  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180037f9b  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037fa0  mov     r8d, 2; nNumberOfBytesToWrite
0x180037fa6  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x180037fab  mov     rcx, [rsp+2C0h+hFile]; hFile
0x180037fb0  call    cs:__imp_WriteFile
0x180037fb7  nop     dword ptr [rax+rax+00h]
0x180037fbc  test    eax, eax
0x180037fbe  jz      loc_180038046
0x180037fc4  cmp     [rsp+2C0h+NumberOfBytesWritten], 2
0x180037fc9  jnz     short loc_180038046
0x180037fcb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037fcf  inc     r8
0x180037fd2  cmp     [r14+r8*2], r15w
0x180037fd7  jnz     short loc_180037FCF
0x180037fd9  add     r8d, r8d; nNumberOfBytesToWrite
0x180037fdc  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15; lpOverlapped
0x180037fe1  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037fe6  mov     rdx, r14; lpBuffer
0x180037fe9  mov     rcx, [rsp+2C0h+hFile]; hFile
0x180037fee  call    cs:__imp_WriteFile
0x180037ff5  nop     dword ptr [rax+rax+00h]
0x180037ffa  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15; wchar_t *
0x180037fff  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r12; wchar_t *
0x180038004  lea     r9, [rbp+1C0h+var_240]; wchar_t *
0x180038008  mov     edx, 5; enum _WER_FILE_TYPE
0x18003800d  lea     r8d, [rdx-2]; unsigned int
0x180038011  mov     rcx, [rbx]; this
0x180038014  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x180038019  mov     edi, eax
0x18003801b  test    eax, eax
0x18003801d  jns     loc_180037E87
0x180038023  lea     rax, WPP_GLOBAL_Control
0x18003802a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038031  cmp     rcx, rax
0x180038034  jz      short loc_180038089
0x180038036  test    byte ptr [rcx+1Ch], 1
0x18003803a  jz      short loc_180038089
0x18003803c  mov     edx, 6Eh ; 'n'
0x180038041  jmp     loc_180037F7E
0x180038046  lea     rax, WPP_GLOBAL_Control
0x18003804d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038054  cmp     rcx, rax
0x180038057  jz      short loc_180038074
0x180038059  test    byte ptr [rcx+1Ch], 1
0x18003805d  jz      short loc_180038074
0x18003805f  mov     edx, 6Dh ; 'm'
0x180038064  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18003806b  mov     rcx, [rcx+10h]
0x18003806f  call    WPP_SF_
0x180038074  call    cs:__imp_GetLastError
0x18003807b  nop     dword ptr [rax+rax+00h]
0x180038080  mov     ecx, eax; unsigned int
0x180038082  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180038087  mov     edi, eax
0x180038089  lea     rcx, [rsp+2C0h+var_268]; void *
0x18003808e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180038093  nop
0x180038094  lea     rcx, [rsp+2C0h+hFile]
0x180038099  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003809e  mov     eax, edi
0x1800380a0  mov     rcx, [rbp+1C0h+var_30]
0x1800380a7  xor     rcx, rsp; StackCookie
0x1800380aa  call    __security_check_cookie
0x1800380af  lea     r11, [rsp+2C0h+var_20]
0x1800380b7  mov     rbx, [r11+40h]
0x1800380bb  mov     rsi, [r11+48h]
0x1800380bf  mov     rsp, r11
0x1800380c2  pop     r15
0x1800380c4  pop     r14
0x1800380c6  pop     r12
0x1800380c8  pop     rdi
0x1800380c9  pop     rbp
0x1800380ca  retn
```
