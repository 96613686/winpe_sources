# WerpMapImageIntoCache(void * *,WERP_IMAGE_CACHE *,wchar_t const *,PE_IMAGE_INFORMATION *)

- ea: `0x180063a2c`
- end: `0x180064006`
- name: `?WerpMapImageIntoCache@@YAJPEAPEAXPEAUWERP_IMAGE_CACHE@@PEB_WPEAUPE_IMAGE_INFORMATION@@@Z`
- size: `1498`
- prototype: `int(void **, struct WERP_IMAGE_CACHE *, const wchar_t *, struct PE_IMAGE_INFORMATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x180046a54`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000db80`
- `0x18000ed68`
- `0x1800170b0`
- `0x18001aab8`
- `0x18001c368`
- `0x18002d180`
- `0x180030ca8`
- `0x1800638e0`
- `0x180063a2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180063f35`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180063f7a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180063f35`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180063f7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063c03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063c03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180063dbb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180063e39`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180063dbb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180063e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063bc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063dfc`
- `ntdll!wcsrchr` at `0x180063f0d`
- `ntdll!wcsrchr` at `0x180063f52`
- `ntdll!wcsrchr` at `0x180063f0d`
- `ntdll!wcsrchr` at `0x180063f52`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063bb5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063bb5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180063c71`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180063c71`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180063c8d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180063c8d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180063b52`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180063b52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063b03`
- `dbghelp!RangeMapFree` at `0x180063da5`
- `dbghelp!RangeMapFree` at `0x180063da5`
- `dbghelp!RangeMapCreate` at `0x180063d8c`
- `dbghelp!RangeMapCreate` at `0x180063d8c`
- `dbghelp!RangeMapAddPeImageSections` at `0x180063dec`
- `dbghelp!RangeMapAddPeImageSections` at `0x180063dec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WerpMapImageIntoCache(
        void **a1,
        struct WERP_IMAGE_CACHE *a2,
        wchar_t *a3,
        struct PE_IMAGE_INFORMATION *a4)
{
  __int64 v8; // rbx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  unsigned int v11; // edi
  HANDLE v12; // rbx
  DWORD v13; // eax
  HANDLE FileMappingW; // r13
  DWORD v15; // eax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  LPVOID v18; // rax
  const void *v19; // rcx
  DWORD v20; // eax
  __int64 v21; // rcx
  int ImageInformation; // edi
  int v23; // eax
  int v24; // eax
  PVOID v25; // rax
  void *v26; // rcx
  DWORD v27; // eax
  DWORD v29; // edx
  unsigned int v30; // edx
  unsigned int v31; // ecx
  __int64 v32; // xmm1_8
  __int64 v33; // rax
  DWORD LowPart; // eax
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  wchar_t *v37; // rax
  wchar_t *v38; // rax
  wchar_t *v39; // rax
  wchar_t *v40; // rax
  _QWORD *v41; // [rsp+40h] [rbp-79h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-71h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-69h] BYREF
  LARGE_INTEGER v44; // [rsp+58h] [rbp-61h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-59h] BYREF
  __int128 v46; // [rsp+68h] [rbp-51h] BYREF
  __int128 v47; // [rsp+78h] [rbp-41h]
  __int64 v48; // [rsp+88h] [rbp-31h]
  __int128 v49; // [rsp+90h] [rbp-29h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-19h]
  LPCWSTR lpFileName[13]; // [rsp+A8h] [rbp-11h] BYREF
  HANDLE v52; // [rsp+120h] [rbp+67h] BYREF

  FileSize.QuadPart = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  PerformanceCount.QuadPart = 0;
  v44.QuadPart = 0;
  *a1 = 0;
  hFile = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(lpFileName)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpFileName,
                           L"\\\\.\\GLOBALROOT")
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           lpFileName,
                           a3) )
  {
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
    return 2147942414LL;
  }
  FileW = CreateFileW(lpFileName[0], 0x80000000, 7u, 0, 3u, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  LastError = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(LastError);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  v12 = hFile;
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
LABEL_40:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
    return v11;
  }
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
    v13 = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(v13);
    goto LABEL_40;
  }
  if ( FileSize.HighPart )
  {
    v11 = -805304060;
    goto LABEL_40;
  }
  if ( FileSize.LowPart < 0x148 )
  {
    v11 = -2147024703;
    goto LABEL_40;
  }
  FileMappingW = CreateFileMappingW(v12, 0, 8u, 0, 0, 0);
  v52 = FileMappingW;
  v15 = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(v15);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, 0);
  if ( (unsigned __int64)FileMappingW + 1 <= 1 )
  {
LABEL_39:
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    goto LABEL_40;
  }
  v16 = HeapAlloc(g_hWerheap, 0, 0x40u);
  v17 = v16;
  if ( v16 )
  {
    *(_OWORD *)v16 = 0;
    v16[2] = 0;
    v16[3] = 0;
    *((_OWORD *)v16 + 2) = 0;
    v16[6] = 0;
    *((_DWORD *)v16 + 14) = 0;
  }
  else
  {
    v17 = 0;
  }
  v41 = v17;
  if ( !v17 )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147024882;
    goto LABEL_40;
  }
  v18 = MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
  v19 = (const void *)v17[2];
  v17[2] = v18;
  if ( v19 )
    UnmapViewOfFile(v19);
  v20 = GetLastError();
  v11 = ERROR_HR_FROM_WIN32(v20);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v52, 0);
  v21 = v17[2];
  if ( !v21 )
  {
LABEL_38:
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    goto LABEL_39;
  }
  v47 = 0;
  *(_QWORD *)&v46 = &PepProtectedCopyMemory;
  *((_QWORD *)&v46 + 1) = v21;
  LODWORD(v47) = FileSize.LowPart;
  v48 = 2;
  ImageInformation = PeReadImageInformation((struct PE_IMAGE_INFORMATION *)&v49, (struct PE_FILE *)&v46);
  if ( ImageInformation < 0 )
  {
    v11 = ImageInformation | 0x10000000;
    goto LABEL_38;
  }
  if ( *(_DWORD *)a4 && *(_DWORD *)a4 != (_DWORD)v49 )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147022995;
    goto LABEL_40;
  }
  v23 = *((_DWORD *)a4 + 1);
  if ( v23 && v23 != DWORD1(v49) )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -2147023434;
    goto LABEL_40;
  }
  v24 = *((_DWORD *)a4 + 2);
  if ( v24 && v24 != DWORD2(v49) )
  {
    utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
    v11 = -805305823;
    goto LABEL_40;
  }
  v25 = RangeMapCreate();
  v26 = (void *)v17[3];
  v17[3] = v25;
  if ( v26 )
    RangeMapFree(v26);
  if ( !v17[3]
    || (QueryPerformanceCounter(&PerformanceCount),
        !RangeMapAddPeImageSections(
           (PVOID)v17[3],
           a3,
           (PVOID)v17[2],
           FileSize.LowPart,
           *((_QWORD *)a4 + 2),
           0,
           0xE0000005)) )
  {
    v27 = GetLastError();
    v11 = ERROR_HR_FROM_WIN32(v27);
    goto LABEL_38;
  }
  QueryPerformanceCounter(&v44);
  v29 = FileSize.LowPart + *((_DWORD *)a2 + 5);
  if ( v29 < FileSize.LowPart )
    v29 = -1;
  if ( FileSize.LowPart < *((_DWORD *)a2 + 4) )
  {
    if ( v29 <= *((_DWORD *)a2 + 4) )
    {
      v31 = 0;
      goto LABEL_49;
    }
    v30 = v29 - *((_DWORD *)a2 + 4);
  }
  else
  {
    ++*((_DWORD *)a2 + 6);
    v30 = 0;
  }
  v31 = WerpFlushImageCache(a2, v30);
LABEL_49:
  v32 = *((_QWORD *)a4 + 2);
  *((_OWORD *)v17 + 2) = *(_OWORD *)a4;
  v17[6] = v32;
  *((_DWORD *)v17 + 14) = FileSize.LowPart;
  *a1 = (void *)v17[3];
  v41 = 0;
  v33 = *(_QWORD *)a2;
  if ( *(struct WERP_IMAGE_CACHE **)(*(_QWORD *)a2 + 8LL) != a2 )
    __fastfail(3u);
  *v17 = v33;
  v17[1] = a2;
  *(_QWORD *)(v33 + 8) = v17;
  *(_QWORD *)a2 = v17;
  LowPart = FileSize.LowPart;
  *((_DWORD *)a2 + 5) += FileSize.LowPart;
  ++*((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 7) += v31;
  *((_QWORD *)a2 + 23) += v44.QuadPart - PerformanceCount.QuadPart;
  v35 = *((_DWORD *)a2 + 9);
  if ( v35 <= *((_DWORD *)a2 + 8) )
    v35 = *((_DWORD *)a2 + 8);
  *((_DWORD *)a2 + 9) = v35;
  v36 = *((_DWORD *)a2 + 10);
  if ( v36 <= *((_DWORD *)a2 + 5) )
    v36 = *((_DWORD *)a2 + 5);
  *((_DWORD *)a2 + 10) = v36;
  if ( !*((_DWORD *)a2 + 11) || LowPart < *((_DWORD *)a2 + 11) )
  {
    *((_DWORD *)a2 + 11) = LowPart;
    v37 = wcsrchr(a3, 0x5Cu);
    if ( v37 )
      v38 = v37 + 1;
    else
      v38 = a3;
    _o_wcsncpy_s((char *)a2 + 52, 32, v38, -1);
    LowPart = FileSize.LowPart;
  }
  if ( LowPart > *((_DWORD *)a2 + 12) )
  {
    *((_DWORD *)a2 + 12) = LowPart;
    v39 = wcsrchr(a3, 0x5Cu);
    if ( v39 )
      v40 = v39 + 1;
    else
      v40 = a3;
    _o_wcsncpy_s((char *)a2 + 116, 32, v40, -1);
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1b05c2b80b7f37aefcd0b72690fdc185_Traceguids, a3);
  utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return 0;
}

```

## disassembly

```asm
0x180063a2c  push    rbp
0x180063a2e  push    rbx
0x180063a2f  push    rsi
0x180063a30  push    rdi
0x180063a31  push    r12
0x180063a33  push    r13
0x180063a35  push    r14
0x180063a37  push    r15
0x180063a39  lea     rbp, [rsp-1Fh]
0x180063a3e  sub     rsp, 0D8h
0x180063a45  mov     r15, r9
0x180063a48  mov     r14, r8
0x180063a4b  mov     rsi, rdx
0x180063a4e  mov     r12, rcx
0x180063a51  xor     r13d, r13d
0x180063a54  mov     qword ptr [rbp+57h+FileSize], r13
0x180063a58  xorps   xmm0, xmm0
0x180063a5b  xor     eax, eax
0x180063a5d  movups  [rbp+57h+var_A8], xmm0
0x180063a61  movups  [rbp+57h+var_98], xmm0
0x180063a65  mov     [rbp+57h+var_88], rax
0x180063a69  movups  [rbp+57h+var_80], xmm0
0x180063a6d  mov     [rbp+57h+var_70], rax
0x180063a71  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x180063a75  mov     qword ptr [rbp+57h+var_B8], r13
0x180063a79  mov     [rcx], r13
0x180063a7c  mov     [rbp+57h+hFile], r13
0x180063a80  lea     rcx, [rbp+57h+lpFileName]; void *
0x180063a84  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180063a89  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180063a8d  inc     rbx
0x180063a90  cmp     [r14+rbx*2], r13w
0x180063a95  jnz     short loc_180063A8D
0x180063a97  lea     rdx, [rbx+0Eh]
0x180063a9b  lea     rcx, [rbp+57h+lpFileName]
0x180063a9f  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x180063aa4  test    al, al
0x180063aa6  jz      loc_180063FD9
0x180063aac  mov     r8d, 0Eh
0x180063ab2  mov     rdx, cs:off_1800B49A8; "\\\\.\\GLOBALROOT"
0x180063ab9  lea     rcx, [rbp+57h+lpFileName]
0x180063abd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180063ac2  test    al, al
0x180063ac4  jz      loc_180063FD9
0x180063aca  mov     r8, rbx
0x180063acd  mov     rdx, r14
0x180063ad0  lea     rcx, [rbp+57h+lpFileName]
0x180063ad4  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180063ad9  test    al, al
0x180063adb  jz      loc_180063FD9
0x180063ae1  mov     [rsp+110h+hTemplateFile], r13; hTemplateFile
0x180063ae6  mov     [rsp+110h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180063aeb  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180063af3  xor     r9d, r9d; lpSecurityAttributes
0x180063af6  mov     edx, 80000000h; dwDesiredAccess
0x180063afb  lea     r8d, [r9+7]; dwShareMode
0x180063aff  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180063b03  call    cs:__imp_CreateFileW
0x180063b0a  nop     dword ptr [rax+rax+00h]
0x180063b0f  mov     rdx, rax
0x180063b12  lea     rcx, [rbp+57h+hFile]
0x180063b16  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180063b1b  call    cs:__imp_GetLastError
0x180063b22  nop     dword ptr [rax+rax+00h]
0x180063b27  mov     ecx, eax; unsigned int
0x180063b29  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063b2e  mov     edi, eax
0x180063b30  lea     rcx, [rbp+57h+lpFileName]; void *
0x180063b34  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180063b39  mov     rbx, [rbp+57h+hFile]
0x180063b3d  lea     rax, [rbx+1]
0x180063b41  cmp     rax, 1
0x180063b45  jbe     loc_180063E25
0x180063b4b  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x180063b4f  mov     rcx, rbx; hFile
0x180063b52  call    cs:__imp_GetFileSizeEx
0x180063b59  nop     dword ptr [rax+rax+00h]
0x180063b5e  test    eax, eax
0x180063b60  jnz     short loc_180063B7C
0x180063b62  call    cs:__imp_GetLastError
0x180063b69  nop     dword ptr [rax+rax+00h]
0x180063b6e  mov     ecx, eax; unsigned int
0x180063b70  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063b75  mov     edi, eax
0x180063b77  jmp     loc_180063E25
0x180063b7c  cmp     dword ptr [rbp+57h+FileSize+4], r13d
0x180063b80  jz      short loc_180063B8C
0x180063b82  mov     edi, 0D0000904h
0x180063b87  jmp     loc_180063E25
0x180063b8c  cmp     dword ptr [rbp+57h+FileSize], 148h
0x180063b93  jnb     short loc_180063B9F
0x180063b95  mov     edi, 800700C1h
0x180063b9a  jmp     loc_180063E25
0x180063b9f  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; lpName
0x180063ba4  mov     [rsp+110h+dwCreationDisposition], r13d; dwMaximumSizeLow
0x180063ba9  xor     r9d, r9d; dwMaximumSizeHigh
0x180063bac  xor     edx, edx; lpFileMappingAttributes
0x180063bae  lea     r8d, [r9+8]; flProtect
0x180063bb2  mov     rcx, rbx; hFile
0x180063bb5  call    cs:__imp_CreateFileMappingW
0x180063bbc  nop     dword ptr [rax+rax+00h]
0x180063bc1  mov     r13, rax
0x180063bc4  mov     [rbp+57h+arg_0], rax
0x180063bc8  call    cs:__imp_GetLastError
0x180063bcf  nop     dword ptr [rax+rax+00h]
0x180063bd4  mov     ecx, eax; unsigned int
0x180063bd6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063bdb  mov     edi, eax
0x180063bdd  xor     edx, edx
0x180063bdf  lea     rcx, [rbp+57h+hFile]
0x180063be3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180063be8  lea     rcx, [r13+1]
0x180063bec  cmp     rcx, 1
0x180063bf0  jbe     loc_180063E1B
0x180063bf6  xor     edx, edx; dwFlags
0x180063bf8  lea     r8d, [rdx+40h]; dwBytes
0x180063bfc  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180063c03  call    cs:__imp_HeapAlloc
0x180063c0a  nop     dword ptr [rax+rax+00h]
0x180063c0f  mov     rbx, rax
0x180063c12  xor     ecx, ecx
0x180063c14  test    rax, rax
0x180063c17  jz      short loc_180063C36
0x180063c19  xorps   xmm0, xmm0
0x180063c1c  movups  xmmword ptr [rax], xmm0
0x180063c1f  mov     [rax+10h], rcx
0x180063c23  mov     [rax+18h], rcx
0x180063c27  xor     eax, eax
0x180063c29  movups  xmmword ptr [rbx+20h], xmm0
0x180063c2d  mov     [rbx+30h], rax
0x180063c31  mov     [rbx+38h], ecx
0x180063c34  jmp     short loc_180063C39
0x180063c36  mov     rbx, rcx
0x180063c39  mov     [rbp+57h+var_D0], rbx
0x180063c3d  test    rbx, rbx
0x180063c40  jnz     short loc_180063C5F
0x180063c42  lea     rcx, [rbp+57h+var_D0]
0x180063c46  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180063c4b  nop
0x180063c4c  lea     rcx, [rbp+57h+arg_0]
0x180063c50  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063c55  mov     edi, 8007000Eh
0x180063c5a  jmp     loc_180063E25
0x180063c5f  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x180063c64  xor     r9d, r9d; dwFileOffsetLow
0x180063c67  xor     r8d, r8d; dwFileOffsetHigh
0x180063c6a  lea     edx, [r9+1]; dwDesiredAccess
0x180063c6e  mov     rcx, r13; hFileMappingObject
0x180063c71  call    cs:__imp_MapViewOfFile
0x180063c78  nop     dword ptr [rax+rax+00h]
0x180063c7d  mov     rcx, [rbx+10h]; lpBaseAddress
0x180063c81  mov     [rbx+10h], rax
0x180063c85  xor     r13d, r13d
0x180063c88  test    rcx, rcx
0x180063c8b  jz      short loc_180063C99
0x180063c8d  call    cs:__imp_UnmapViewOfFile
0x180063c94  nop     dword ptr [rax+rax+00h]
0x180063c99  call    cs:__imp_GetLastError
0x180063ca0  nop     dword ptr [rax+rax+00h]
0x180063ca5  mov     ecx, eax; unsigned int
0x180063ca7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063cac  mov     edi, eax
0x180063cae  xor     edx, edx
0x180063cb0  lea     rcx, [rbp+57h+arg_0]
0x180063cb4  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180063cb9  mov     rcx, [rbx+10h]
0x180063cbd  test    rcx, rcx
0x180063cc0  jz      loc_180063E11
0x180063cc6  xorps   xmm0, xmm0
0x180063cc9  xor     eax, eax
0x180063ccb  movups  [rbp+57h+var_A8], xmm0
0x180063ccf  movups  [rbp+57h+var_98], xmm0
0x180063cd3  mov     [rbp+57h+var_88], rax
0x180063cd7  mov     eax, dword ptr [rbp+57h+FileSize]
0x180063cda  lea     rdx, PepProtectedCopyMemory
0x180063ce1  mov     qword ptr [rbp+57h+var_A8], rdx
0x180063ce5  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180063ce9  mov     dword ptr [rbp+57h+var_98], eax
0x180063cec  mov     dword ptr [rbp+57h+var_88], 2
0x180063cf3  lea     rdx, [rbp+57h+var_A8]; struct PE_FILE *
0x180063cf7  lea     rcx, [rbp+57h+var_80]; struct PE_IMAGE_INFORMATION *
0x180063cfb  call    ?PeReadImageInformation@@YAJPEAUPE_IMAGE_INFORMATION@@PEAUPE_FILE@@@Z; PeReadImageInformation(PE_IMAGE_INFORMATION *,PE_FILE *)
0x180063d00  mov     edi, eax
0x180063d02  test    eax, eax
0x180063d04  jns     short loc_180063D0F
0x180063d06  bts     edi, 1Ch
0x180063d0a  jmp     loc_180063E11
0x180063d0f  mov     eax, [r15]
0x180063d12  test    eax, eax
0x180063d14  jz      short loc_180063D38
0x180063d16  cmp     eax, dword ptr [rbp+57h+var_80]
0x180063d19  jz      short loc_180063D38
0x180063d1b  lea     rcx, [rbp+57h+var_D0]
0x180063d1f  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180063d24  nop
0x180063d25  lea     rcx, [rbp+57h+arg_0]
0x180063d29  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063d2e  mov     edi, 8007076Dh
0x180063d33  jmp     loc_180063E25
0x180063d38  mov     eax, [r15+4]
0x180063d3c  test    eax, eax
0x180063d3e  jz      short loc_180063D62
0x180063d40  cmp     eax, dword ptr [rbp+57h+var_80+4]
0x180063d43  jz      short loc_180063D62
0x180063d45  lea     rcx, [rbp+57h+var_D0]
0x180063d49  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180063d4e  nop
0x180063d4f  lea     rcx, [rbp+57h+arg_0]
0x180063d53  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063d58  mov     edi, 800705B6h
0x180063d5d  jmp     loc_180063E25
0x180063d62  mov     eax, [r15+8]
0x180063d66  test    eax, eax
0x180063d68  jz      short loc_180063D8C
0x180063d6a  cmp     eax, dword ptr [rbp+57h+var_80+8]
0x180063d6d  jz      short loc_180063D8C
0x180063d6f  lea     rcx, [rbp+57h+var_D0]
0x180063d73  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180063d78  nop
0x180063d79  lea     rcx, [rbp+57h+arg_0]
0x180063d7d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063d82  mov     edi, 0D0000221h
0x180063d87  jmp     loc_180063E25
0x180063d8c  call    cs:__imp_RangeMapCreate
0x180063d93  nop     dword ptr [rax+rax+00h]
0x180063d98  mov     rcx, [rbx+18h]; RmapHandle
0x180063d9c  mov     [rbx+18h], rax
0x180063da0  test    rcx, rcx
0x180063da3  jz      short loc_180063DB1
0x180063da5  call    cs:__imp_RangeMapFree
0x180063dac  nop     dword ptr [rax+rax+00h]
0x180063db1  cmp     [rbx+18h], r13
0x180063db5  jz      short loc_180063DFC
0x180063db7  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180063dbb  call    cs:__imp_QueryPerformanceCounter
0x180063dc2  nop     dword ptr [rax+rax+00h]
0x180063dc7  mov     dword ptr [rsp+110h+hTemplateFile], 0E0000005h; MappingFlags
0x180063dcf  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; UserTag
0x180063dd4  mov     rax, [r15+10h]
0x180063dd8  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ImageBase
0x180063ddd  mov     r9d, dword ptr [rbp+57h+FileSize]; MappingBytes
0x180063de1  mov     r8, [rbx+10h]; MappedImage
0x180063de5  mov     rdx, r14; ImageName
0x180063de8  mov     rcx, [rbx+18h]; RmapHandle
0x180063dec  call    cs:__imp_RangeMapAddPeImageSections
0x180063df3  nop     dword ptr [rax+rax+00h]
0x180063df8  test    eax, eax
0x180063dfa  jnz     short loc_180063E35
0x180063dfc  call    cs:__imp_GetLastError
0x180063e03  nop     dword ptr [rax+rax+00h]
0x180063e08  mov     ecx, eax; unsigned int
0x180063e0a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063e0f  mov     edi, eax
0x180063e11  lea     rcx, [rbp+57h+var_D0]
0x180063e15  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180063e1a  nop
0x180063e1b  lea     rcx, [rbp+57h+arg_0]
0x180063e1f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063e24  nop
0x180063e25  lea     rcx, [rbp+57h+hFile]
0x180063e29  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180063e2e  mov     eax, edi
0x180063e30  jmp     loc_180063FF1
0x180063e35  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x180063e39  call    cs:__imp_QueryPerformanceCounter
0x180063e40  nop     dword ptr [rax+rax+00h]
0x180063e45  mov     edx, [rsi+14h]
0x180063e48  mov     rax, qword ptr [rbp+57h+FileSize]
0x180063e4c  add     edx, eax
0x180063e4e  or      ecx, 0FFFFFFFFh
0x180063e51  cmp     edx, eax
0x180063e53  cmovb   edx, ecx
0x180063e56  cmp     eax, [rsi+10h]
0x180063e59  jb      short loc_180063E62
0x180063e5b  inc     dword ptr [rsi+18h]
0x180063e5e  xor     edx, edx
0x180063e60  jmp     short loc_180063E6A
0x180063e62  cmp     edx, [rsi+10h]
0x180063e65  jbe     short loc_180063E76
0x180063e67  sub     edx, [rsi+10h]; unsigned int
0x180063e6a  mov     rcx, rsi; struct WERP_IMAGE_CACHE *
0x180063e6d  call    ?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x180063e72  mov     ecx, eax
0x180063e74  jmp     short loc_180063E79
0x180063e76  mov     ecx, r13d
0x180063e79  movups  xmm0, xmmword ptr [r15]
0x180063e7d  movsd   xmm1, qword ptr [r15+10h]
0x180063e83  movups  xmmword ptr [rbx+20h], xmm0
0x180063e87  movsd   qword ptr [rbx+30h], xmm1
0x180063e8c  mov     eax, dword ptr [rbp+57h+FileSize]
0x180063e8f  mov     [rbx+38h], eax
0x180063e92  mov     rax, [rbx+18h]
0x180063e96  mov     [r12], rax
0x180063e9a  mov     [rbp+57h+var_D0], r13
0x180063e9e  mov     rax, [rsi]
0x180063ea1  cmp     [rax+8], rsi
0x180063ea5  jz      short loc_180063EAE
0x180063ea7  mov     ecx, 3
0x180063eac  int     29h; Win8: RtlFailFast(ecx)
0x180063eae  mov     [rbx], rax
  ... truncated ...
```
