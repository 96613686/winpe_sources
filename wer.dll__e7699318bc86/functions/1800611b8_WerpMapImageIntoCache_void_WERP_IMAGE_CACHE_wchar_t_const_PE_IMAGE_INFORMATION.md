# WerpMapImageIntoCache(void * *,WERP_IMAGE_CACHE *,wchar_t const *,PE_IMAGE_INFORMATION *)

- ea: `0x1800611b8`
- end: `0x180061716`
- name: `?WerpMapImageIntoCache@@YAJPEAPEAXPEAUWERP_IMAGE_CACHE@@PEB_WPEAUPE_IMAGE_INFORMATION@@@Z`
- size: `1374`
- prototype: `__int64 __fastcall(void **, struct WERP_IMAGE_CACHE *, const wchar_t *, struct PE_IMAGE_INFORMATION *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x180044b14`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000d75c`
- `0x18000dad0`
- `0x180013730`
- `0x180016f98`
- `0x18002b7a4`
- `0x18002f678`
- `0x180061070`
- `0x1800611b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061658`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061691`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061658`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180061691`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006136b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006136b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800614fc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180061568`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800614fc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180061568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800612dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061336`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800613ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061531`
- `ntdll!wcsrchr` at `0x180061636`
- `ntdll!wcsrchr` at `0x18006166f`
- `ntdll!wcsrchr` at `0x180061636`
- `ntdll!wcsrchr` at `0x18006166f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180061329`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180061329`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800613d3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800613d3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800613e9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800613e9`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800612d2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800612d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006128f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006128f`
- `dbghelp!RangeMapFree` at `0x1800614ec`
- `dbghelp!RangeMapFree` at `0x1800614ec`
- `dbghelp!RangeMapCreate` at `0x1800614d9`
- `dbghelp!RangeMapCreate` at `0x1800614d9`
- `dbghelp!RangeMapAddPeImageSections` at `0x180061527`
- `dbghelp!RangeMapAddPeImageSections` at `0x180061527`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WerpMapImageIntoCache(
        void **a1,
        struct WERP_IMAGE_CACHE *a2,
        const wchar_t *a3,
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
  const wchar_t *v38; // rax
  wchar_t *v39; // rax
  const wchar_t *v40; // rax
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
    || !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)lpFileName,
          L"\\\\.\\GLOBALROOT",
          0xEu)
    || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                           lpFileName,
                           a3,
                           v8) )
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
  *(_QWORD *)&v46 = PepProtectedCopyMemory;
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
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1b05c2b80b7f37aefcd0b72690fdc185_Traceguids);
  utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(&v41);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v52);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return 0;
}

```

## disassembly

```asm
0x1800611b8  push    rbp
0x1800611ba  push    rbx
0x1800611bb  push    rsi
0x1800611bc  push    rdi
0x1800611bd  push    r12
0x1800611bf  push    r13
0x1800611c1  push    r14
0x1800611c3  push    r15
0x1800611c5  lea     rbp, [rsp-1Fh]
0x1800611ca  sub     rsp, 0D8h
0x1800611d1  mov     r15, r9
0x1800611d4  mov     r14, r8
0x1800611d7  mov     rsi, rdx
0x1800611da  mov     r12, rcx
0x1800611dd  xor     r13d, r13d
0x1800611e0  mov     qword ptr [rbp+57h+FileSize], r13
0x1800611e4  xorps   xmm0, xmm0
0x1800611e7  xor     eax, eax
0x1800611e9  movups  [rbp+57h+var_A8], xmm0
0x1800611ed  movups  [rbp+57h+var_98], xmm0
0x1800611f1  mov     [rbp+57h+var_88], rax
0x1800611f5  movups  [rbp+57h+var_80], xmm0
0x1800611f9  mov     [rbp+57h+var_70], rax
0x1800611fd  mov     qword ptr [rbp+57h+PerformanceCount], r13
0x180061201  mov     qword ptr [rbp+57h+var_B8], r13
0x180061205  mov     [rcx], r13
0x180061208  mov     [rbp+57h+hFile], r13
0x18006120c  lea     rcx, [rbp+57h+lpFileName]; void *
0x180061210  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180061215  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180061219  inc     rbx
0x18006121c  cmp     [r14+rbx*2], r13w
0x180061221  jnz     short loc_180061219
0x180061223  lea     rdx, [rbx+0Eh]
0x180061227  lea     rcx, [rbp+57h+lpFileName]
0x18006122b  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x180061230  test    al, al
0x180061232  jz      loc_1800616EA
0x180061238  mov     r8d, 0Eh
0x18006123e  mov     rdx, cs:off_1800AF9A8; "\\\\.\\GLOBALROOT"
0x180061245  lea     rcx, [rbp+57h+lpFileName]
0x180061249  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18006124e  test    al, al
0x180061250  jz      loc_1800616EA
0x180061256  mov     r8, rbx
0x180061259  mov     rdx, r14
0x18006125c  lea     rcx, [rbp+57h+lpFileName]
0x180061260  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180061265  test    al, al
0x180061267  jz      loc_1800616EA
0x18006126d  mov     [rsp+110h+hTemplateFile], r13; hTemplateFile
0x180061272  mov     [rsp+110h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180061277  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x18006127f  xor     r9d, r9d; lpSecurityAttributes
0x180061282  mov     edx, 80000000h; dwDesiredAccess
0x180061287  lea     r8d, [r9+7]; dwShareMode
0x18006128b  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18006128f  call    cs:__imp_CreateFileW
0x180061295  mov     rdx, rax
0x180061298  lea     rcx, [rbp+57h+hFile]
0x18006129c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800612a1  call    cs:__imp_GetLastError
0x1800612a7  mov     ecx, eax; unsigned int
0x1800612a9  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800612ae  mov     edi, eax
0x1800612b0  lea     rcx, [rbp+57h+lpFileName]; void *
0x1800612b4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800612b9  mov     rbx, [rbp+57h+hFile]
0x1800612bd  lea     rax, [rbx+1]
0x1800612c1  cmp     rax, 1
0x1800612c5  jbe     loc_180061554
0x1800612cb  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800612cf  mov     rcx, rbx; hFile
0x1800612d2  call    cs:__imp_GetFileSizeEx
0x1800612d8  test    eax, eax
0x1800612da  jnz     short loc_1800612F0
0x1800612dc  call    cs:__imp_GetLastError
0x1800612e2  mov     ecx, eax; unsigned int
0x1800612e4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800612e9  mov     edi, eax
0x1800612eb  jmp     loc_180061554
0x1800612f0  cmp     dword ptr [rbp+57h+FileSize+4], r13d
0x1800612f4  jz      short loc_180061300
0x1800612f6  mov     edi, 0D0000904h
0x1800612fb  jmp     loc_180061554
0x180061300  cmp     dword ptr [rbp+57h+FileSize], 148h
0x180061307  jnb     short loc_180061313
0x180061309  mov     edi, 800700C1h
0x18006130e  jmp     loc_180061554
0x180061313  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; lpName
0x180061318  mov     [rsp+110h+dwCreationDisposition], r13d; dwMaximumSizeLow
0x18006131d  xor     r9d, r9d; dwMaximumSizeHigh
0x180061320  xor     edx, edx; lpFileMappingAttributes
0x180061322  lea     r8d, [r9+8]; flProtect
0x180061326  mov     rcx, rbx; hFile
0x180061329  call    cs:__imp_CreateFileMappingW
0x18006132f  mov     r13, rax
0x180061332  mov     [rbp+57h+arg_0], rax
0x180061336  call    cs:__imp_GetLastError
0x18006133c  mov     ecx, eax; unsigned int
0x18006133e  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180061343  mov     edi, eax
0x180061345  xor     edx, edx
0x180061347  lea     rcx, [rbp+57h+hFile]
0x18006134b  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180061350  lea     rcx, [r13+1]
0x180061354  cmp     rcx, 1
0x180061358  jbe     loc_18006154A
0x18006135e  xor     edx, edx; dwFlags
0x180061360  lea     r8d, [rdx+40h]; dwBytes
0x180061364  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18006136b  call    cs:__imp_HeapAlloc
0x180061371  mov     rbx, rax
0x180061374  xor     ecx, ecx
0x180061376  test    rax, rax
0x180061379  jz      short loc_180061398
0x18006137b  xorps   xmm0, xmm0
0x18006137e  movups  xmmword ptr [rax], xmm0
0x180061381  mov     [rax+10h], rcx
0x180061385  mov     [rax+18h], rcx
0x180061389  xor     eax, eax
0x18006138b  movups  xmmword ptr [rbx+20h], xmm0
0x18006138f  mov     [rbx+30h], rax
0x180061393  mov     [rbx+38h], ecx
0x180061396  jmp     short loc_18006139B
0x180061398  mov     rbx, rcx
0x18006139b  mov     [rbp+57h+var_D0], rbx
0x18006139f  test    rbx, rbx
0x1800613a2  jnz     short loc_1800613C1
0x1800613a4  lea     rcx, [rbp+57h+var_D0]
0x1800613a8  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x1800613ad  nop
0x1800613ae  lea     rcx, [rbp+57h+arg_0]
0x1800613b2  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800613b7  mov     edi, 8007000Eh
0x1800613bc  jmp     loc_180061554
0x1800613c1  mov     qword ptr [rsp+110h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x1800613c6  xor     r9d, r9d; dwFileOffsetLow
0x1800613c9  xor     r8d, r8d; dwFileOffsetHigh
0x1800613cc  lea     edx, [r9+1]; dwDesiredAccess
0x1800613d0  mov     rcx, r13; hFileMappingObject
0x1800613d3  call    cs:__imp_MapViewOfFile
0x1800613d9  mov     rcx, [rbx+10h]; lpBaseAddress
0x1800613dd  mov     [rbx+10h], rax
0x1800613e1  xor     r13d, r13d
0x1800613e4  test    rcx, rcx
0x1800613e7  jz      short loc_1800613EF
0x1800613e9  call    cs:__imp_UnmapViewOfFile
0x1800613ef  call    cs:__imp_GetLastError
0x1800613f5  mov     ecx, eax; unsigned int
0x1800613f7  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800613fc  mov     edi, eax
0x1800613fe  xor     edx, edx
0x180061400  lea     rcx, [rbp+57h+arg_0]
0x180061404  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180061409  mov     rcx, [rbx+10h]
0x18006140d  test    rcx, rcx
0x180061410  jz      loc_180061540
0x180061416  xorps   xmm0, xmm0
0x180061419  xor     eax, eax
0x18006141b  movups  [rbp+57h+var_A8], xmm0
0x18006141f  movups  [rbp+57h+var_98], xmm0
0x180061423  mov     [rbp+57h+var_88], rax
0x180061427  mov     eax, dword ptr [rbp+57h+FileSize]
0x18006142a  lea     rdx, PepProtectedCopyMemory
0x180061431  mov     qword ptr [rbp+57h+var_A8], rdx
0x180061435  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180061439  mov     dword ptr [rbp+57h+var_98], eax
0x18006143c  mov     dword ptr [rbp+57h+var_88], 2
0x180061443  lea     rdx, [rbp+57h+var_A8]; struct PE_FILE *
0x180061447  lea     rcx, [rbp+57h+var_80]; struct PE_IMAGE_INFORMATION *
0x18006144b  call    ?PeReadImageInformation@@YAJPEAUPE_IMAGE_INFORMATION@@PEAUPE_FILE@@@Z; PeReadImageInformation(PE_IMAGE_INFORMATION *,PE_FILE *)
0x180061450  mov     edi, eax
0x180061452  test    eax, eax
0x180061454  jns     short loc_18006145F
0x180061456  bts     edi, 1Ch
0x18006145a  jmp     loc_180061540
0x18006145f  mov     eax, [r15]
0x180061462  test    eax, eax
0x180061464  jz      short loc_180061488
0x180061466  cmp     eax, dword ptr [rbp+57h+var_80]
0x180061469  jz      short loc_180061488
0x18006146b  lea     rcx, [rbp+57h+var_D0]
0x18006146f  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180061474  nop
0x180061475  lea     rcx, [rbp+57h+arg_0]
0x180061479  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006147e  mov     edi, 8007076Dh
0x180061483  jmp     loc_180061554
0x180061488  mov     eax, [r15+4]
0x18006148c  test    eax, eax
0x18006148e  jz      short loc_1800614B2
0x180061490  cmp     eax, dword ptr [rbp+57h+var_80+4]
0x180061493  jz      short loc_1800614B2
0x180061495  lea     rcx, [rbp+57h+var_D0]
0x180061499  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x18006149e  nop
0x18006149f  lea     rcx, [rbp+57h+arg_0]
0x1800614a3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800614a8  mov     edi, 800705B6h
0x1800614ad  jmp     loc_180061554
0x1800614b2  mov     eax, [r15+8]
0x1800614b6  test    eax, eax
0x1800614b8  jz      short loc_1800614D9
0x1800614ba  cmp     eax, dword ptr [rbp+57h+var_80+8]
0x1800614bd  jz      short loc_1800614D9
0x1800614bf  lea     rcx, [rbp+57h+var_D0]
0x1800614c3  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x1800614c8  nop
0x1800614c9  lea     rcx, [rbp+57h+arg_0]
0x1800614cd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800614d2  mov     edi, 0D0000221h
0x1800614d7  jmp     short loc_180061554
0x1800614d9  call    cs:__imp_RangeMapCreate
0x1800614df  mov     rcx, [rbx+18h]; RmapHandle
0x1800614e3  mov     [rbx+18h], rax
0x1800614e7  test    rcx, rcx
0x1800614ea  jz      short loc_1800614F2
0x1800614ec  call    cs:__imp_RangeMapFree
0x1800614f2  cmp     [rbx+18h], r13
0x1800614f6  jz      short loc_180061531
0x1800614f8  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800614fc  call    cs:__imp_QueryPerformanceCounter
0x180061502  mov     dword ptr [rsp+110h+hTemplateFile], 0E0000005h; MappingFlags
0x18006150a  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; UserTag
0x18006150f  mov     rax, [r15+10h]
0x180061513  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; ImageBase
0x180061518  mov     r9d, dword ptr [rbp+57h+FileSize]; MappingBytes
0x18006151c  mov     r8, [rbx+10h]; MappedImage
0x180061520  mov     rdx, r14; ImageName
0x180061523  mov     rcx, [rbx+18h]; RmapHandle
0x180061527  call    cs:__imp_RangeMapAddPeImageSections
0x18006152d  test    eax, eax
0x18006152f  jnz     short loc_180061564
0x180061531  call    cs:__imp_GetLastError
0x180061537  mov     ecx, eax; unsigned int
0x180061539  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006153e  mov     edi, eax
0x180061540  lea     rcx, [rbp+57h+var_D0]
0x180061544  call    ??1?$unique_ptr@UWERP_CACHED_IMAGE@@U?$default_delete@UWERP_CACHED_IMAGE@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>::~unique_ptr<WERP_CACHED_IMAGE,utl::default_delete<WERP_CACHED_IMAGE>>(void)
0x180061549  nop
0x18006154a  lea     rcx, [rbp+57h+arg_0]
0x18006154e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180061553  nop
0x180061554  lea     rcx, [rbp+57h+hFile]
0x180061558  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18006155d  mov     eax, edi
0x18006155f  jmp     loc_180061702
0x180061564  lea     rcx, [rbp+57h+var_B8]; lpPerformanceCount
0x180061568  call    cs:__imp_QueryPerformanceCounter
0x18006156e  mov     edx, [rsi+14h]
0x180061571  mov     rax, qword ptr [rbp+57h+FileSize]
0x180061575  add     edx, eax
0x180061577  or      ecx, 0FFFFFFFFh
0x18006157a  cmp     edx, eax
0x18006157c  cmovb   edx, ecx
0x18006157f  cmp     eax, [rsi+10h]
0x180061582  jb      short loc_18006158B
0x180061584  inc     dword ptr [rsi+18h]
0x180061587  xor     edx, edx
0x180061589  jmp     short loc_180061593
0x18006158b  cmp     edx, [rsi+10h]
0x18006158e  jbe     short loc_18006159F
0x180061590  sub     edx, [rsi+10h]; unsigned int
0x180061593  mov     rcx, rsi; struct WERP_IMAGE_CACHE *
0x180061596  call    ?WerpFlushImageCache@@YAKPEAUWERP_IMAGE_CACHE@@K@Z; WerpFlushImageCache(WERP_IMAGE_CACHE *,ulong)
0x18006159b  mov     ecx, eax
0x18006159d  jmp     short loc_1800615A2
0x18006159f  mov     ecx, r13d
0x1800615a2  movups  xmm0, xmmword ptr [r15]
0x1800615a6  movsd   xmm1, qword ptr [r15+10h]
0x1800615ac  movups  xmmword ptr [rbx+20h], xmm0
0x1800615b0  movsd   qword ptr [rbx+30h], xmm1
0x1800615b5  mov     eax, dword ptr [rbp+57h+FileSize]
0x1800615b8  mov     [rbx+38h], eax
0x1800615bb  mov     rax, [rbx+18h]
0x1800615bf  mov     [r12], rax
0x1800615c3  mov     [rbp+57h+var_D0], r13
0x1800615c7  mov     rax, [rsi]
0x1800615ca  cmp     [rax+8], rsi
0x1800615ce  jz      short loc_1800615D7
0x1800615d0  mov     ecx, 3
0x1800615d5  int     29h; Win8: RtlFailFast(ecx)
0x1800615d7  mov     [rbx], rax
0x1800615da  mov     [rbx+8], rsi
0x1800615de  mov     [rax+8], rbx
0x1800615e2  mov     [rsi], rbx
0x1800615e5  mov     rax, qword ptr [rbp+57h+FileSize]
0x1800615e9  add     [rsi+14h], eax
0x1800615ec  inc     dword ptr [rsi+20h]
0x1800615ef  add     [rsi+1Ch], ecx
0x1800615f2  mov     rcx, qword ptr [rbp+57h+var_B8]
0x1800615f6  sub     rcx, qword ptr [rbp+57h+PerformanceCount]
0x1800615fa  add     [rsi+0B8h], rcx
0x180061601  mov     ecx, [rsi+24h]
0x180061604  cmp     ecx, [rsi+20h]
0x180061607  cmovbe  ecx, [rsi+20h]
0x18006160b  mov     [rsi+24h], ecx
0x18006160e  mov     ecx, [rsi+28h]
0x180061611  cmp     ecx, [rsi+14h]
  ... truncated ...
```
