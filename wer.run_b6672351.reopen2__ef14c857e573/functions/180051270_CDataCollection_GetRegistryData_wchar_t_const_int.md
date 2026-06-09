# CDataCollection::GetRegistryData(wchar_t const *,int)

- ea: `0x180051270`
- end: `0x1800517a3`
- name: `?GetRegistryData@CDataCollection@@QEAAJPEB_WH@Z`
- size: `1331`
- prototype: `int(CDataCollection *__hidden this, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180044080`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180008298`
- `0x180008698`
- `0x18000da00`
- `0x18001381c`
- `0x1800170b0`
- `0x180018000`
- `0x18001c368`
- `0x180020680`
- `0x18002a758`
- `0x180051270`
- `0x180053300`
- `0x18008ee54`
- `0x18008eefc`
- `0x18008efa4`
- `0x18009106c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800516ee`
- `ntdll!wcschr` at `0x18005149e`
- `ntdll!wcschr` at `0x18005149e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800514bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800514bf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180051483`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180051483`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180051382`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005162e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180051382`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005162e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005172d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005172d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800513fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800513fa`

## string_xrefs

- `0x18005165b`: `registry.txt`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDataCollection::GetRegistryData(CDataCollection *this, const wchar_t *a2, unsigned int a3)
{
  const wchar_t **v5; // r14
  const WCHAR *v6; // rcx
  int TempFile; // eax
  int RegKeyData; // edi
  char *v9; // rbx
  HANDLE FileW; // rax
  int v11; // eax
  wchar_t *v12; // r15
  BOOL v13; // r15d
  __int64 v14; // rax
  unsigned int v15; // r13d
  int v16; // eax
  DWORD LastError; // eax
  const wchar_t *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  __int16 Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h]
  DWORD v26; // [rsp+54h] [rbp-ACh] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  _QWORD v29[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v30[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v31; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v32[24]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR FileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v25 = a3;
  hFile = 0;
  NumberOfBytesWritten = 0;
  Buffer[0] = -257;
  utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v29);
  v26 = 0;
  v30[0] = asc_1800BA7C0;
  v30[1] = 7;
  FileName[0] = 0;
  v5 = (const wchar_t **)((char *)this + 24);
  v6 = (const WCHAR *)*((_QWORD *)this + 3);
  if ( v6 == *((const WCHAR **)this + 4) )
  {
    TempFile = UtilGetTempFile(&hFile, 0, L".reg.txt", FileName);
    RegKeyData = TempFile;
    if ( TempFile < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)TempFile);
      v9 = (char *)hFile;
      goto LABEL_49;
    }
    v9 = (char *)hFile;
    if ( WriteFile(hFile, Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 24, FileName);
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
LABEL_48:
    LastError = GetLastError();
    RegKeyData = ERROR_HR_FROM_WIN32(LastError);
    goto LABEL_49;
  }
  FileW = CreateFileW(v6, 0x40000000u, 1u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  v9 = (char *)hFile;
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, *v5);
    goto LABEL_48;
  }
  v11 = UtilVerifyFilePath(*v5, hFile);
  RegKeyData = v11;
  if ( v11 >= 0 )
  {
    SetFilePointer(v9, 0, 0, 2u);
LABEL_18:
    while ( 1 )
    {
      v12 = wcschr(a2, 0x3Bu);
      if ( !v12 )
        break;
      if ( !WaitForSingleObject(*((HANDLE *)this + 2), 0) )
      {
        RegKeyData = -2145681407;
        goto LABEL_49;
      }
      v27 = a2;
      v28 = v12 - a2;
      v31 = *(_OWORD *)tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(
                         v32,
                         &v27,
                         v30);
      if ( !(unsigned __int8)utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                               v29,
                               &v31) )
      {
        RegKeyData = -2147024882;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
            2147942414LL);
      }
      a2 = v12 + 1;
    }
    v13 = 0;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v27 = a2;
    v28 = (2 * v14) >> 1;
    v31 = *(_OWORD *)tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(
                       v32,
                       &v27,
                       v30);
    if ( !(unsigned __int8)utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
                             v29,
                             &v31) )
    {
      RegKeyData = -2147024882;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147942414LL);
    }
    v15 = v25;
    while ( (_QWORD *)v29[0] != v29 )
    {
      RegKeyData = CDataCollection::GetRegKeyData(this, v29, v15, v9);
      if ( RegKeyData == -2145681407 )
        goto LABEL_49;
      if ( !v13 )
        v13 = RegKeyData >= 0;
      WriteFile(v9, L"\r\n\r\n", 8u, &v26, 0);
    }
    if ( v13 && !*((_DWORD *)this + 14) )
    {
      v16 = CReport::AddFile(*(CReport **)this, WerFileTypeOther, 0x10001u, *v5, L"registry.txt", 0);
      RegKeyData = v16;
      if ( v16 >= 0 )
      {
        *((_DWORD *)this + 14) = 1;
      }
      else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          (unsigned int)*v5,
          v16);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      (unsigned int)v11);
  }
LABEL_49:
  if ( v9 != (char *)-1LL && v9 + 1 != (char *)1 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, 0);
    if ( !*((_DWORD *)this + 14) )
    {
      if ( FileName[0] )
      {
        DeleteFileW(FileName);
        v18 = *v5;
        *((_QWORD *)this + 4) = *((_QWORD *)this + 3);
        *v18 = 0;
      }
    }
  }
  while ( (_QWORD *)v29[0] != v29 )
  {
    v19 = *(_QWORD **)(v29[0] + 8LL);
    v20 = *(_QWORD *)v29[0];
    *v19 = *(_QWORD *)v29[0];
    *(_QWORD *)(v20 + 8) = v19;
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>();
  }
  v29[2] = 0;
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)RegKeyData;
}

```

## disassembly

```asm
0x180051270  mov     [rsp-8+arg_10], rbx
0x180051275  push    rbp
0x180051276  push    rsi
0x180051277  push    rdi
0x180051278  push    r12
0x18005127a  push    r13
0x18005127c  push    r14
0x18005127e  push    r15
0x180051280  lea     rbp, [rsp-1E0h]
0x180051288  sub     rsp, 2E0h
0x18005128f  mov     rax, cs:__security_cookie
0x180051296  xor     rax, rsp
0x180051299  mov     [rbp+210h+var_40], rax
0x1800512a0  mov     [rsp+310h+var_2C0], r8d
0x1800512a5  mov     r13, rdx
0x1800512a8  mov     r12, rcx
0x1800512ab  xor     r15d, r15d
0x1800512ae  mov     [rsp+310h+hFile], r15
0x1800512b3  mov     [rsp+310h+NumberOfBytesWritten], r15d
0x1800512b8  mov     eax, 0FEFFh
0x1800512bd  mov     [rsp+310h+Buffer], ax
0x1800512c2  lea     rcx, [rsp+310h+var_2A0]
0x1800512c7  call    ??0?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800512cc  nop
0x1800512cd  mov     [rsp+310h+var_2BC], r15d
0x1800512d2  lea     rax, asc_1800BA7C0; "\\ \r\n\t\v"
0x1800512d9  mov     [rbp+210h+var_288], rax
0x1800512dd  mov     [rbp+210h+var_280], 7
0x1800512e5  mov     [rbp+210h+FileName], r15w
0x1800512ea  lea     r14, [r12+18h]
0x1800512ef  mov     rcx, [r14]; lpFileName
0x1800512f2  cmp     rcx, [r14+8]
0x1800512f6  jnz     loc_1800513DC
0x1800512fc  mov     [rsp+310h+var_2D8], r15d
0x180051301  mov     dword ptr [rsp+310h+hTemplateFile], 1
0x180051309  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], r15
0x18005130e  lea     r9, [rbp+210h+FileName]
0x180051312  lea     r8, aRegTxt; ".reg.txt"
0x180051319  xor     edx, edx
0x18005131b  lea     rcx, [rsp+310h+hFile]
0x180051320  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180051325  mov     edi, eax
0x180051327  test    eax, eax
0x180051329  jns     short loc_180051365
0x18005132b  lea     rsi, WPP_GLOBAL_Control
0x180051332  mov     rcx, cs:WPP_GLOBAL_Control
0x180051339  cmp     rcx, rsi
0x18005133c  jz      short loc_18005135B
0x18005133e  test    byte ptr [rcx+1Ch], 1
0x180051342  jz      short loc_18005135B
0x180051344  lea     edx, [r15+25h]
0x180051348  mov     r9d, eax
0x18005134b  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180051352  mov     rcx, [rcx+10h]
0x180051356  call    WPP_SF_d
0x18005135b  mov     rbx, [rsp+310h+hFile]
0x180051360  jmp     loc_180051703
0x180051365  mov     [rsp+310h+lpOverlapped], r15; lpOverlapped
0x18005136a  lea     r9, [rsp+310h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18005136f  mov     r8d, 2; nNumberOfBytesToWrite
0x180051375  lea     rdx, [rsp+310h+Buffer]; lpBuffer
0x18005137a  mov     rbx, [rsp+310h+hFile]
0x18005137f  mov     rcx, rbx; hFile
0x180051382  call    cs:__imp_WriteFile
0x180051389  nop     dword ptr [rax+rax+00h]
0x18005138e  test    eax, eax
0x180051390  jnz     short loc_1800513CB
0x180051392  lea     rsi, WPP_GLOBAL_Control
0x180051399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800513a0  cmp     rcx, rsi
0x1800513a3  jz      loc_1800516EE
0x1800513a9  test    byte ptr [rcx+1Ch], 1
0x1800513ad  jz      loc_1800516EE
0x1800513b3  lea     edx, [rax+26h]
0x1800513b6  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800513bd  mov     rcx, [rcx+10h]
0x1800513c1  call    WPP_SF_
0x1800513c6  jmp     loc_1800516EE
0x1800513cb  lea     rdx, [rbp+210h+FileName]
0x1800513cf  mov     rcx, r14
0x1800513d2  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800513d7  jmp     loc_18005148F
0x1800513dc  mov     [rsp+310h+hTemplateFile], r15; hTemplateFile
0x1800513e1  mov     [rsp+310h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800513e6  mov     dword ptr [rsp+310h+lpOverlapped], 3; dwCreationDisposition
0x1800513ee  xor     r9d, r9d; lpSecurityAttributes
0x1800513f1  mov     edx, 40000000h; dwDesiredAccess
0x1800513f6  lea     r8d, [r9+1]; dwShareMode
0x1800513fa  call    cs:__imp_CreateFileW
0x180051401  nop     dword ptr [rax+rax+00h]
0x180051406  mov     rdx, rax
0x180051409  lea     rcx, [rsp+310h+hFile]
0x18005140e  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180051413  mov     rbx, [rsp+310h+hFile]
0x180051418  lea     rax, [rbx+1]
0x18005141c  cmp     rax, 1
0x180051420  jbe     loc_1800516BD
0x180051426  mov     rdx, rbx; void *
0x180051429  mov     rcx, [r14]; wchar_t *
0x18005142c  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180051431  mov     edi, eax
0x180051433  test    eax, eax
0x180051435  jns     short loc_180051475
0x180051437  lea     rsi, WPP_GLOBAL_Control
0x18005143e  mov     rcx, cs:WPP_GLOBAL_Control
0x180051445  cmp     rcx, rsi
0x180051448  jz      loc_180051703
0x18005144e  test    byte ptr [rcx+1Ch], 1
0x180051452  jz      loc_180051703
0x180051458  mov     edx, 28h ; '('
0x18005145d  mov     r9d, eax
0x180051460  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180051467  mov     rcx, [rcx+10h]
0x18005146b  call    WPP_SF_d
0x180051470  jmp     loc_180051703
0x180051475  mov     r9d, 2; dwMoveMethod
0x18005147b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005147e  xor     edx, edx; lDistanceToMove
0x180051480  mov     rcx, rbx; hFile
0x180051483  call    cs:__imp_SetFilePointer
0x18005148a  nop     dword ptr [rax+rax+00h]
0x18005148f  lea     rsi, WPP_GLOBAL_Control
0x180051496  mov     edx, 3Bh ; ';'; Ch
0x18005149b  mov     rcx, r13; Str
0x18005149e  call    cs:__imp_wcschr
0x1800514a5  nop     dword ptr [rax+rax+00h]
0x1800514aa  mov     r15, rax
0x1800514ad  xor     ecx, ecx
0x1800514af  test    rax, rax
0x1800514b2  jz      loc_180051553
0x1800514b8  xor     edx, edx; dwMilliseconds
0x1800514ba  mov     rcx, [r12+10h]; hHandle
0x1800514bf  call    cs:__imp_WaitForSingleObject
0x1800514c6  nop     dword ptr [rax+rax+00h]
0x1800514cb  test    eax, eax
0x1800514cd  jz      short loc_180051549
0x1800514cf  mov     [rsp+310h+var_2B0], r13
0x1800514d4  mov     rcx, r15
0x1800514d7  sub     rcx, r13
0x1800514da  sar     rcx, 1
0x1800514dd  mov     [rsp+310h+var_2A8], rcx
0x1800514e2  lea     r8, [rbp+210h+var_288]
0x1800514e6  lea     rdx, [rsp+310h+var_2B0]
0x1800514eb  lea     rcx, [rbp+210h+var_268]
0x1800514ef  call    ??$trim_view@_WU?$char_traits@_W@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@_W$0A@@tlx@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V12@AEBV12@@Z; tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1800514f4  movups  xmm1, xmmword ptr [rax]
0x1800514f7  movdqu  [rbp+210h+var_278], xmm1
0x1800514fc  lea     rdx, [rbp+210h+var_278]
0x180051500  lea     rcx, [rsp+310h+var_2A0]
0x180051505  call    ??$emplace_back@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@$0A@@?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18005150a  test    al, al
0x18005150c  jnz     short loc_180051540
0x18005150e  mov     edi, 8007000Eh
0x180051513  mov     rcx, cs:WPP_GLOBAL_Control
0x18005151a  cmp     rcx, rsi
0x18005151d  jz      short loc_180051540
0x18005151f  test    byte ptr [rcx+1Ch], 4
0x180051523  jz      short loc_180051540
0x180051525  mov     edx, 29h ; ')'
0x18005152a  mov     r9d, 8007000Eh
0x180051530  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180051537  mov     rcx, [rcx+10h]
0x18005153b  call    WPP_SF_d
0x180051540  lea     r13, [r15+2]
0x180051544  jmp     loc_180051496
0x180051549  mov     edi, 801B8001h
0x18005154e  jmp     loc_180051703
0x180051553  mov     r15d, ecx
0x180051556  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005155a  inc     rax
0x18005155d  cmp     [r13+rax*2+0], cx
0x180051563  jnz     short loc_18005155A
0x180051565  mov     [rsp+310h+var_2B0], r13
0x18005156a  add     rax, rax
0x18005156d  sar     rax, 1
0x180051570  mov     [rsp+310h+var_2A8], rax
0x180051575  lea     r8, [rbp+210h+var_288]
0x180051579  lea     rdx, [rsp+310h+var_2B0]
0x18005157e  lea     rcx, [rbp+210h+var_268]
0x180051582  call    ??$trim_view@_WU?$char_traits@_W@utl@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@2@_W$0A@@tlx@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V12@AEBV12@@Z; tlx::trim_view<wchar_t,utl::char_traits<wchar_t>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,wchar_t,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180051587  movups  xmm1, xmmword ptr [rax]
0x18005158a  movdqu  [rbp+210h+var_278], xmm1
0x18005158f  lea     rdx, [rbp+210h+var_278]
0x180051593  lea     rcx, [rsp+310h+var_2A0]
0x180051598  call    ??$emplace_back@AEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@$0A@@?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA_NAEAV?$basic_string_view@_WU?$char_traits@_W@utl@@@1@@Z; utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::emplace_back<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &)
0x18005159d  test    al, al
0x18005159f  jnz     short loc_1800515D3
0x1800515a1  mov     edi, 8007000Eh
0x1800515a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800515ad  cmp     rcx, rsi
0x1800515b0  jz      short loc_1800515D3
0x1800515b2  test    byte ptr [rcx+1Ch], 4
0x1800515b6  jz      short loc_1800515D3
0x1800515b8  mov     edx, 2Ah ; '*'
0x1800515bd  mov     r9d, 8007000Eh
0x1800515c3  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800515ca  mov     rcx, [rcx+10h]
0x1800515ce  call    WPP_SF_d
0x1800515d3  mov     r13d, [rsp+310h+var_2C0]
0x1800515d8  lea     rax, [rsp+310h+var_2A0]
0x1800515dd  cmp     [rsp+310h+var_2A0], rax
0x1800515e2  jz      short loc_18005163C
0x1800515e4  mov     r9, rbx
0x1800515e7  mov     r8d, r13d
0x1800515ea  lea     rdx, [rsp+310h+var_2A0]
0x1800515ef  mov     rcx, r12
0x1800515f2  call    ?GetRegKeyData@CDataCollection@@AEAAJAEAV?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@HPEAX@Z; CDataCollection::GetRegKeyData(utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,int,void *)
0x1800515f7  mov     edi, eax
0x1800515f9  cmp     eax, 801B8001h
0x1800515fe  jz      loc_180051703
0x180051604  xor     eax, eax
0x180051606  test    r15d, r15d
0x180051609  jnz     short loc_180051614
0x18005160b  mov     r15d, eax
0x18005160e  test    edi, edi
0x180051610  setns   r15b
0x180051614  mov     [rsp+310h+lpOverlapped], rax; lpOverlapped
0x180051619  lea     r9, [rsp+310h+var_2BC]; lpNumberOfBytesWritten
0x18005161e  mov     r8d, 8; nNumberOfBytesToWrite
0x180051624  lea     rdx, asc_1800C5940; "\r\n\r\n"
0x18005162b  mov     rcx, rbx; hFile
0x18005162e  call    cs:__imp_WriteFile
0x180051635  nop     dword ptr [rax+rax+00h]
0x18005163a  jmp     short loc_1800515D8
0x18005163c  xor     r13d, r13d
0x18005163f  test    r15d, r15d
0x180051642  jz      loc_180051706
0x180051648  xor     r15d, r15d
0x18005164b  cmp     [r12+38h], r15d
0x180051650  jnz     loc_180051706
0x180051656  mov     qword ptr [rsp+310h+dwFlagsAndAttributes], r15; wchar_t *
0x18005165b  lea     rax, aRegistryTxt; "registry.txt"
0x180051662  mov     [rsp+310h+lpOverlapped], rax; wchar_t *
0x180051667  mov     r9, [r14]; wchar_t *
0x18005166a  lea     edx, [r13+5]; enum _WER_FILE_TYPE
0x18005166e  mov     r8d, 10001h; unsigned int
0x180051674  mov     rcx, [r12]; this
0x180051678  call    ?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z; CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)
0x18005167d  mov     edi, eax
0x18005167f  test    eax, eax
0x180051681  jns     short loc_1800516B2
0x180051683  mov     rcx, cs:WPP_GLOBAL_Control
0x18005168a  cmp     rcx, rsi
0x18005168d  jz      short loc_180051703
0x18005168f  test    byte ptr [rcx+1Ch], 1
0x180051693  jz      short loc_180051703
0x180051695  lea     edx, [r13+2Bh]
0x180051699  mov     dword ptr [rsp+310h+lpOverlapped], eax
0x18005169d  mov     r9, [r14]
0x1800516a0  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800516a7  mov     rcx, [rcx+10h]
0x1800516ab  call    WPP_SF_SD
0x1800516b0  jmp     short loc_180051706
0x1800516b2  mov     dword ptr [r12+38h], 1
0x1800516bb  jmp     short loc_180051706
0x1800516bd  lea     rsi, WPP_GLOBAL_Control
0x1800516c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516cb  cmp     rcx, rsi
0x1800516ce  jz      short loc_1800516EE
0x1800516d0  test    byte ptr [rcx+1Ch], 1
0x1800516d4  jz      short loc_1800516EE
0x1800516d6  mov     edx, 27h ; '''
0x1800516db  mov     r9, [r14]
0x1800516de  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800516e5  mov     rcx, [rcx+10h]
0x1800516e9  call    WPP_SF_S
0x1800516ee  call    cs:__imp_GetLastError
0x1800516f5  nop     dword ptr [rax+rax+00h]
0x1800516fa  mov     ecx, eax; unsigned int
0x1800516fc  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180051701  mov     edi, eax
0x180051703  xor     r13d, r13d
0x180051706  inc     rbx
0x180051709  cmp     rbx, 1
0x18005170d  jbe     short loc_180051744
0x18005170f  xor     edx, edx
0x180051711  lea     rcx, [rsp+310h+hFile]
0x180051716  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005171b  cmp     [r12+38h], r13d
0x180051720  jnz     short loc_180051744
0x180051722  cmp     [rbp+210h+FileName], r13w
0x180051727  jz      short loc_180051744
0x180051729  lea     rcx, [rbp+210h+FileName]; lpFileName
0x18005172d  call    cs:__imp_DeleteFileW
0x180051734  nop     dword ptr [rax+rax+00h]
0x180051739  mov     rcx, [r14]
0x18005173c  mov     [r14+8], rcx
0x180051740  mov     [rcx], r13w
0x180051744  mov     rdx, [rsp+310h+var_2A0]
0x180051749  lea     rax, [rsp+310h+var_2A0]
0x18005174e  cmp     rdx, rax
0x180051751  jz      short loc_180051768
0x180051753  mov     rcx, [rdx+8]
0x180051757  mov     rax, [rdx]
0x18005175a  mov     [rcx], rax
0x18005175d  mov     [rax+8], rcx
0x180051761  call    ??$_DeleteNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> *)
0x180051766  jmp     short loc_180051744
0x180051768  mov     [rbp+210h+var_290], r13
0x18005176c  lea     rcx, [rsp+310h+hFile]
  ... truncated ...
```
