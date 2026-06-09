# UtilLaunchWerManager(wchar_t const * *,ulong,ulong,void *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *,ulong,void * *)

- ea: `0x1800a9b8c`
- end: `0x1800aa126`
- name: `?UtilLaunchWerManager@@YAJPEAPEB_WKKPEAXPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@2KPEAPEAX@Z`
- size: `1434`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, PVOID lpValue)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003bf5c`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180010280`
- `0x1800170b0`
- `0x1800172c0`
- `0x180018000`
- `0x18001c368`
- `0x18001e0d0`
- `0x18001e100`
- `0x180020680`
- `0x180020e08`
- `0x180028760`
- `0x18002e94c`
- `0x180053300`
- `0x180053d3c`
- `0x180064950`
- `0x180068e08`
- `0x1800a9b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a9de2`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800a9de2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a9fa3`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800a9fa3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800aa05f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800aa05f`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a9e5c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a9f0e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a9e5c`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800a9f0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a9c39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800a9c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa0e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa0e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UtilLaunchWerManager(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        PVOID lpValue)
{
  struct _PROC_THREAD_ATTRIBUTE_LIST *v9; // rbx
  __int64 v10; // rsi
  signed int v11; // edi
  unsigned int i; // edi
  _WORD *v13; // r14
  HANDLE hProcess; // rax
  signed int v16; // eax
  __int64 unique_oversize_for; // rax
  signed int v18; // eax
  signed int v19; // eax
  __int64 v20; // r9
  wchar_t *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // eax
  DWORD LastError; // eax
  HANDLE v25; // [rsp+50h] [rbp-B0h] BYREF
  ULONG_PTR Size; // [rsp+58h] [rbp-A8h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+60h] [rbp-A0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpCommandLine[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[16]; // [rsp+A0h] [rbp-60h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v32; // [rsp+118h] [rbp+18h]
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpCommandLine);
  *(_QWORD *)&StartupInfo.cb = 0;
  memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  Size = 0;
  v9 = 0;
  lpAttributeList = 0;
  if ( a5 )
    tlx::unique_any<tlx::file_handle_traits>::reset(a5, 0);
  LODWORD(v10) = 0;
  LODWORD(v25) = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(LastError);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_27;
    v22 = 11;
    v20 = (unsigned int)v11;
    goto LABEL_56;
  }
  v11 = StringCchCatW(Buffer, 0x104u, L"\\wermgr.exe");
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
        (unsigned int)Buffer,
        v11);
    goto LABEL_27;
  }
  v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          lpCommandLine,
          L"\"%ls\" ",
          Buffer);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, Buffer);
    goto LABEL_27;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xE )
    {
      if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) )
      {
        v16 = GetLastError();
        if ( v16 != 122 )
        {
          if ( v16 > 0 )
            v11 = (unsigned __int16)v16 | 0x80070000;
          else
            v11 = v16;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              (unsigned int)v16);
          goto LABEL_26;
        }
      }
      unique_oversize_for = tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(v30, Size);
      utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(
        &lpAttributeList,
        unique_oversize_for);
      utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v30);
      v9 = lpAttributeList;
      if ( !lpAttributeList )
      {
        v11 = -2147024882;
LABEL_26:
        LODWORD(v10) = (_DWORD)v25;
        goto LABEL_27;
      }
      if ( !InitializeProcThreadAttributeList(lpAttributeList, 1u, 0, &Size) )
      {
        v18 = GetLastError();
        v11 = v18;
        if ( v18 > 0 )
          v11 = (unsigned __int16)v18 | 0x80070000;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
            (unsigned int)v11);
        goto LABEL_26;
      }
      LODWORD(v10) = 1;
      if ( UpdateProcThreadAttribute(v9, 0, 0x20002u, lpValue, 8LL * a7, 0, 0) )
      {
        StartupInfo.cb = 112;
        v32 = v9;
        wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
        if ( CreateProcessW(Buffer, lpCommandLine[0], 0, 0, 2, 0x80000u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          v11 = 0;
        }
        else
        {
          v23 = GetLastError();
          v11 = ERROR_HR_FROM_WIN32(v23);
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              (unsigned int)WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
              (unsigned int)Buffer,
              (__int64)lpCommandLine[0],
              v11);
        }
        goto LABEL_27;
      }
      v19 = GetLastError();
      v20 = (unsigned int)v19;
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      else
        v11 = v19;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_27;
      v22 = 16;
LABEL_56:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v20);
      goto LABEL_27;
    }
    v13 = *(_WORD **)(a1 + 8LL * i);
    v10 = 0;
    if ( v13 )
    {
      if ( *v13 )
        break;
    }
LABEL_23:
    ;
  }
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                          lpCommandLine,
                          34) )
  {
    while ( v13[v10] )
    {
      if ( v13[v10] == 34
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               lpCommandLine,
                               92)
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                               lpCommandLine,
                               (unsigned __int16)v13[v10]) )
      {
        v11 = -2147024882;
        goto LABEL_26;
      }
      ++v10;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                            lpCommandLine,
                            (void *)L"\" ") )
      goto LABEL_23;
    v11 = -2147024882;
    LODWORD(v10) = 0;
  }
  else
  {
    v11 = -2147024882;
  }
LABEL_27:
  if ( a5 )
  {
    hProcess = ProcessInformation.hProcess;
    ProcessInformation.hProcess = 0;
    v25 = hProcess;
    tlx::unique_any<tlx::file_handle_traits>::operator=(a5, &v25);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v25);
  }
  if ( (_DWORD)v10 )
    DeleteProcThreadAttributeList(v9);
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&lpAttributeList);
  wer::ProcessInformation::Clear((wer::ProcessInformation *)&ProcessInformation);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpCommandLine);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a9b8c  push    rbp
0x1800a9b8e  push    rbx
0x1800a9b8f  push    rsi
0x1800a9b90  push    rdi
0x1800a9b91  push    r12
0x1800a9b93  push    r13
0x1800a9b95  push    r14
0x1800a9b97  push    r15
0x1800a9b99  lea     rbp, [rsp-248h]
0x1800a9ba1  sub     rsp, 348h
0x1800a9ba8  mov     rax, cs:__security_cookie
0x1800a9baf  xor     rax, rsp
0x1800a9bb2  mov     [rbp+280h+var_50], rax
0x1800a9bb9  mov     r15, rcx
0x1800a9bbc  mov     r13, [rbp+280h+arg_20]
0x1800a9bc3  mov     r12, [rbp+280h+lpValue]
0x1800a9bca  xor     edx, edx; Val
0x1800a9bcc  mov     r8d, 208h; Size
0x1800a9bd2  lea     rcx, [rbp+280h+Buffer]; void *
0x1800a9bd6  call    memset_0
0x1800a9bdb  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a9bdf  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a9be4  nop
0x1800a9be5  xor     r14d, r14d
0x1800a9be8  mov     qword ptr [rbp+280h+StartupInfo.cb], r14
0x1800a9bec  xor     edx, edx; Val
0x1800a9bee  lea     r8d, [r14+68h]; Size
0x1800a9bf2  lea     rcx, [rbp+280h+StartupInfo.lpReserved]; void *
0x1800a9bf6  call    memset_0
0x1800a9bfb  xorps   xmm0, xmm0
0x1800a9bfe  xor     eax, eax
0x1800a9c00  movups  xmmword ptr [rsp+380h+ProcessInformation.hProcess], xmm0
0x1800a9c05  mov     qword ptr [rsp+380h+ProcessInformation.dwProcessId], rax
0x1800a9c0a  mov     [rsp+380h+Size], r14
0x1800a9c0f  mov     ebx, r14d
0x1800a9c12  mov     [rsp+380h+lpAttributeList], rbx
0x1800a9c17  test    r13, r13
0x1800a9c1a  jz      short loc_1800A9C26
0x1800a9c1c  xor     edx, edx
0x1800a9c1e  mov     rcx, r13
0x1800a9c21  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800a9c26  mov     esi, r14d
0x1800a9c29  mov     dword ptr [rsp+380h+var_330], r14d
0x1800a9c2e  mov     edi, 104h
0x1800a9c33  mov     edx, edi; uSize
0x1800a9c35  lea     rcx, [rbp+280h+Buffer]; lpBuffer
0x1800a9c39  call    cs:__imp_GetSystemDirectoryW
0x1800a9c40  nop     dword ptr [rax+rax+00h]
0x1800a9c45  dec     eax
0x1800a9c47  cmp     eax, 102h
0x1800a9c4c  ja      loc_1800AA0E2
0x1800a9c52  lea     r8, aWermgrExe; "\\wermgr.exe"
0x1800a9c59  mov     edx, edi; unsigned __int64
0x1800a9c5b  lea     rcx, [rbp+280h+Buffer]; wchar_t *
0x1800a9c5f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800a9c64  mov     edi, eax
0x1800a9c66  test    eax, eax
0x1800a9c68  jns     short loc_1800A9CAD
0x1800a9c6a  lea     rax, WPP_GLOBAL_Control
0x1800a9c71  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9c78  cmp     rcx, rax
0x1800a9c7b  jz      loc_1800A9DB0
0x1800a9c81  test    byte ptr [rcx+1Ch], 1
0x1800a9c85  jz      loc_1800A9DB0
0x1800a9c8b  mov     edx, 0Ch
0x1800a9c90  mov     dword ptr [rsp+380h+cbSize], edi
0x1800a9c94  lea     r9, [rbp+280h+Buffer]
0x1800a9c98  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a9c9f  mov     rcx, [rcx+10h]
0x1800a9ca3  call    WPP_SF_SD
0x1800a9ca8  jmp     loc_1800A9DB0
0x1800a9cad  lea     r8, [rbp+280h+Buffer]
0x1800a9cb1  lea     rdx, aLs_1; "\"%ls\" "
0x1800a9cb8  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a9cbc  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a9cc1  mov     edi, eax
0x1800a9cc3  test    eax, eax
0x1800a9cc5  jns     short loc_1800A9D06
0x1800a9cc7  lea     rax, WPP_GLOBAL_Control
0x1800a9cce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9cd5  cmp     rcx, rax
0x1800a9cd8  jz      loc_1800A9DB0
0x1800a9cde  test    byte ptr [rcx+1Ch], 1
0x1800a9ce2  jz      loc_1800A9DB0
0x1800a9ce8  mov     edx, 0Dh
0x1800a9ced  lea     r9, [rbp+280h+Buffer]
0x1800a9cf1  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a9cf8  mov     rcx, [rcx+10h]
0x1800a9cfc  call    WPP_SF_S
0x1800a9d01  jmp     loc_1800A9DB0
0x1800a9d06  mov     edi, r14d
0x1800a9d09  mov     ecx, 22h ; '"'
0x1800a9d0e  cmp     edi, 0Eh
0x1800a9d11  jnb     loc_1800A9E4E
0x1800a9d17  mov     eax, edi
0x1800a9d19  mov     r14, [r15+rax*8]
0x1800a9d1d  xor     esi, esi
0x1800a9d1f  test    r14, r14
0x1800a9d22  jz      short loc_1800A9D9F
0x1800a9d24  cmp     [r14], si
0x1800a9d28  jz      short loc_1800A9D9F
0x1800a9d2a  mov     edx, ecx
0x1800a9d2c  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a9d30  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a9d35  test    al, al
0x1800a9d37  jz      loc_1800A9E41
0x1800a9d3d  xor     eax, eax
0x1800a9d3f  cmp     [r14+rsi*2], ax
0x1800a9d44  jz      short loc_1800A9D79
0x1800a9d46  mov     eax, 22h ; '"'
0x1800a9d4b  cmp     [r14+rsi*2], ax
0x1800a9d50  jnz     short loc_1800A9D62
0x1800a9d52  lea     edx, [rax+3Ah]
0x1800a9d55  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a9d59  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a9d5e  test    al, al
0x1800a9d60  jz      short loc_1800A9DA4
0x1800a9d62  movzx   edx, word ptr [r14+rsi*2]
0x1800a9d67  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a9d6b  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a9d70  test    al, al
0x1800a9d72  jz      short loc_1800A9DA4
0x1800a9d74  inc     rsi
0x1800a9d77  jmp     short loc_1800A9D3D
0x1800a9d79  lea     rdx, asc_1800C82BC; "\" "
0x1800a9d80  lea     rcx, [rbp+280h+lpCommandLine]
0x1800a9d84  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a9d89  xor     r14d, r14d
0x1800a9d8c  test    al, al
0x1800a9d8e  jz      loc_1800A9E34
0x1800a9d94  lea     ecx, [r14+22h]
0x1800a9d98  inc     edi
0x1800a9d9a  jmp     loc_1800A9D0E
0x1800a9d9f  xor     r14d, r14d
0x1800a9da2  jmp     short loc_1800A9D98
0x1800a9da4  mov     edi, 8007000Eh
0x1800a9da9  xor     r14d, r14d
0x1800a9dac  mov     esi, dword ptr [rsp+380h+var_330]
0x1800a9db0  test    r13, r13
0x1800a9db3  jz      short loc_1800A9DDB
0x1800a9db5  mov     rax, [rsp+380h+ProcessInformation.hProcess]
0x1800a9dba  mov     [rsp+380h+ProcessInformation.hProcess], r14
0x1800a9dbf  mov     [rsp+380h+var_330], rax
0x1800a9dc4  lea     rdx, [rsp+380h+var_330]
0x1800a9dc9  mov     rcx, r13
0x1800a9dcc  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x1800a9dd1  lea     rcx, [rsp+380h+var_330]
0x1800a9dd6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a9ddb  test    esi, esi
0x1800a9ddd  jz      short loc_1800A9DEF
0x1800a9ddf  mov     rcx, rbx; lpAttributeList
0x1800a9de2  call    cs:__imp_DeleteProcThreadAttributeList
0x1800a9de9  nop     dword ptr [rax+rax+00h]
0x1800a9dee  nop
0x1800a9def  lea     rcx, [rsp+380h+lpAttributeList]; void *
0x1800a9df4  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a9df9  nop
0x1800a9dfa  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800a9dff  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800a9e04  nop
0x1800a9e05  lea     rcx, [rbp+280h+lpCommandLine]; void *
0x1800a9e09  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800a9e0e  mov     eax, edi
0x1800a9e10  mov     rcx, [rbp+280h+var_50]
0x1800a9e17  xor     rcx, rsp; StackCookie
0x1800a9e1a  call    __security_check_cookie
0x1800a9e1f  add     rsp, 348h
0x1800a9e26  pop     r15
0x1800a9e28  pop     r14
0x1800a9e2a  pop     r13
0x1800a9e2c  pop     r12
0x1800a9e2e  pop     rdi
0x1800a9e2f  pop     rsi
0x1800a9e30  pop     rbx
0x1800a9e31  pop     rbp
0x1800a9e32  retn
0x1800a9e34  mov     edi, 8007000Eh
0x1800a9e39  mov     esi, r14d
0x1800a9e3c  jmp     loc_1800A9DB0
0x1800a9e41  mov     edi, 8007000Eh
0x1800a9e46  xor     r14d, r14d
0x1800a9e49  jmp     loc_1800A9DB0
0x1800a9e4e  lea     r9, [rsp+380h+Size]; lpSize
0x1800a9e53  xor     r8d, r8d; dwFlags
0x1800a9e56  lea     edx, [r8+1]; dwAttributeCount
0x1800a9e5a  xor     ecx, ecx; lpAttributeList
0x1800a9e5c  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a9e63  nop     dword ptr [rax+rax+00h]
0x1800a9e68  test    eax, eax
0x1800a9e6a  jnz     short loc_1800A9ECD
0x1800a9e6c  call    cs:__imp_GetLastError
0x1800a9e73  nop     dword ptr [rax+rax+00h]
0x1800a9e78  mov     r9d, eax
0x1800a9e7b  cmp     eax, 7Ah ; 'z'
0x1800a9e7e  jz      short loc_1800A9ECD
0x1800a9e80  test    eax, eax
0x1800a9e82  jg      short loc_1800A9E88
0x1800a9e84  mov     edi, eax
0x1800a9e86  jmp     short loc_1800A9E92
0x1800a9e88  movzx   edi, r9w
0x1800a9e8c  or      edi, 80070000h
0x1800a9e92  lea     rax, WPP_GLOBAL_Control
0x1800a9e99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9ea0  cmp     rcx, rax
0x1800a9ea3  jz      loc_1800A9DAC
0x1800a9ea9  test    byte ptr [rcx+1Ch], 1
0x1800a9ead  jz      loc_1800A9DAC
0x1800a9eb3  mov     edx, 0Eh
0x1800a9eb8  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a9ebf  mov     rcx, [rcx+10h]
0x1800a9ec3  call    WPP_SF_d
0x1800a9ec8  jmp     loc_1800A9DAC
0x1800a9ecd  mov     rdx, [rsp+380h+Size]
0x1800a9ed2  lea     rcx, [rbp+280h+var_2E0]
0x1800a9ed6  call    ??$make_unique_oversize_for_overwrite@U_TOKEN_USER@@$0A@@tlx@@YA?AV?$unique_ptr@U_TOKEN_USER@@U?$generic_delete@U_TOKEN_USER@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_TOKEN_USER,0>(unsigned __int64)
0x1800a9edb  mov     rdx, rax
0x1800a9ede  lea     rcx, [rsp+380h+lpAttributeList]
0x1800a9ee3  call    ??4?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> &&)
0x1800a9ee8  lea     rcx, [rbp+280h+var_2E0]; void *
0x1800a9eec  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800a9ef1  mov     rbx, [rsp+380h+lpAttributeList]
0x1800a9ef6  test    rbx, rbx
0x1800a9ef9  jz      loc_1800AA0D8
0x1800a9eff  lea     r9, [rsp+380h+Size]; lpSize
0x1800a9f04  xor     r8d, r8d; dwFlags
0x1800a9f07  lea     edx, [r8+1]; dwAttributeCount
0x1800a9f0b  mov     rcx, rbx; lpAttributeList
0x1800a9f0e  call    cs:__imp_InitializeProcThreadAttributeList
0x1800a9f15  nop     dword ptr [rax+rax+00h]
0x1800a9f1a  test    eax, eax
0x1800a9f1c  jnz     short loc_1800A9F77
0x1800a9f1e  call    cs:__imp_GetLastError
0x1800a9f25  nop     dword ptr [rax+rax+00h]
0x1800a9f2a  mov     edi, eax
0x1800a9f2c  test    eax, eax
0x1800a9f2e  jle     short loc_1800A9F39
0x1800a9f30  movzx   edi, ax
0x1800a9f33  or      edi, 80070000h
0x1800a9f39  lea     rax, WPP_GLOBAL_Control
0x1800a9f40  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9f47  cmp     rcx, rax
0x1800a9f4a  jz      loc_1800A9DAC
0x1800a9f50  test    byte ptr [rcx+1Ch], 1
0x1800a9f54  jz      loc_1800A9DAC
0x1800a9f5a  mov     edx, 0Fh
0x1800a9f5f  mov     r9d, edi
0x1800a9f62  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800a9f69  mov     rcx, [rcx+10h]
0x1800a9f6d  call    WPP_SF_d
0x1800a9f72  jmp     loc_1800A9DAC
0x1800a9f77  mov     esi, 1
0x1800a9f7c  mov     eax, [rbp+280h+arg_30]
0x1800a9f82  shl     rax, 3
0x1800a9f86  mov     [rsp+380h+lpReturnSize], r14; lpReturnSize
0x1800a9f8b  mov     [rsp+380h+lpPreviousValue], r14; lpPreviousValue
0x1800a9f90  mov     [rsp+380h+cbSize], rax; cbSize
0x1800a9f95  mov     r9, r12; lpValue
0x1800a9f98  xor     edx, edx; dwFlags
0x1800a9f9a  mov     r8d, 20002h; Attribute
0x1800a9fa0  mov     rcx, rbx; lpAttributeList
0x1800a9fa3  call    cs:__imp_UpdateProcThreadAttribute
0x1800a9faa  nop     dword ptr [rax+rax+00h]
0x1800a9faf  test    eax, eax
0x1800a9fb1  jnz     short loc_1800AA00F
0x1800a9fb3  call    cs:__imp_GetLastError
0x1800a9fba  nop     dword ptr [rax+rax+00h]
0x1800a9fbf  mov     r9d, eax
0x1800a9fc2  test    eax, eax
0x1800a9fc4  jg      short loc_1800A9FCA
0x1800a9fc6  mov     edi, eax
0x1800a9fc8  jmp     short loc_1800A9FD4
0x1800a9fca  movzx   edi, r9w
0x1800a9fce  or      edi, 80070000h
0x1800a9fd4  lea     rax, WPP_GLOBAL_Control
0x1800a9fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9fe2  cmp     rcx, rax
0x1800a9fe5  jz      loc_1800A9DB0
0x1800a9feb  test    [rcx+1Ch], sil
0x1800a9fef  jz      loc_1800A9DB0
0x1800a9ff5  mov     edx, 10h
0x1800a9ffa  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x1800aa001  mov     rcx, [rcx+10h]
0x1800aa005  call    WPP_SF_d
0x1800aa00a  jmp     loc_1800A9DB0
0x1800aa00f  mov     [rbp+280h+StartupInfo.cb], 70h ; 'p'
0x1800aa016  mov     [rbp+280h+var_268], rbx
0x1800aa01a  lea     rcx, [rsp+380h+ProcessInformation]; this
0x1800aa01f  call    ?Clear@ProcessInformation@wer@@QEAAXXZ; wer::ProcessInformation::Clear(void)
0x1800aa024  lea     rax, [rsp+380h+ProcessInformation]
0x1800aa029  mov     [rsp+380h+lpProcessInformation], rax; lpProcessInformation
0x1800aa02e  lea     rax, [rbp+280h+StartupInfo]
0x1800aa032  mov     [rsp+380h+lpStartupInfo], rax; lpStartupInfo
0x1800aa037  mov     [rsp+380h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800aa03c  mov     [rsp+380h+lpReturnSize], r14; lpEnvironment
0x1800aa041  mov     dword ptr [rsp+380h+lpPreviousValue], 80000h; dwCreationFlags
0x1800aa049  mov     dword ptr [rsp+380h+cbSize], 2; bInheritHandles
0x1800aa051  xor     r9d, r9d; lpThreadAttributes
0x1800aa054  xor     r8d, r8d; lpProcessAttributes
0x1800aa057  mov     rdx, [rbp+280h+lpCommandLine]; lpCommandLine
0x1800aa05b  lea     rcx, [rbp+280h+Buffer]; lpApplicationName
  ... truncated ...
```
