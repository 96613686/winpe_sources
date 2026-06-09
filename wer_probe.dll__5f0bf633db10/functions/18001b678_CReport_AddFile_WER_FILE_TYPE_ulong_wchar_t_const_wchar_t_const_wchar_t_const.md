# CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18001b678`
- end: `0x18001bbbe`
- name: `?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z`
- size: `1350`
- prototype: `int(CReport *__hidden this, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `16`
- callee_count: `24`
- tags: `file_ops`

## callers

- `0x18001b280`
- `0x18001dad8`
- `0x180025b10`
- `0x18002e4b8`
- `0x180035ce0`
- `0x1800433d0`
- `0x180049588`
- `0x18004afd4`
- `0x18004ee3c`
- `0x180075aac`
- `0x180079790`
- `0x18007f560`
- `0x18008b42c`
- `0x18008bf00`
- `0x18008caa4`
- `0x18008cbfc`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000c390`
- `0x180013730`
- `0x180014720`
- `0x18001b678`
- `0x18001bff0`
- `0x18001c00c`
- `0x18001c5ec`
- `0x18001c650`
- `0x18001fe24`
- `0x180021634`
- `0x18002be60`
- `0x18002bf08`
- `0x180038f78`
- `0x1800410e8`
- `0x180042918`
- `0x180050db0`
- `0x1800517cc`
- `0x1800705c0`
- `0x180075484`
- `0x180077da0`
- `0x1800974a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb61`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bb7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b87b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b79e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b87b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b705`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b705`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb4a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b792`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b871`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b792`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001b871`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ba20`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ba20`

## pseudocode

```c
__int64 __fastcall CReport::AddFile(
        CReport *this,
        int a2,
        int a3,
        const wchar_t *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  int *v7; // rdi
  WCHAR *v11; // r12
  signed int FileSizeAndTime; // ebx
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  DWORD FullPathNameW; // eax
  DWORD v17; // ebx
  DWORD LastError; // eax
  wchar_t *v19; // rcx
  int v20; // edx
  int v21; // r9d
  __int64 unique_for; // rax
  DWORD v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  const WCHAR *v26; // rsi
  __int64 v27; // rax
  DWORD FileAttributesW; // eax
  CReport *v29; // rcx
  char v30; // al
  __int64 v31; // rcx
  __int64 v33; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v36; // [rsp+50h] [rbp-B0h] BYREF
  char v37[8]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v38; // [rsp+68h] [rbp-98h]
  CReport *v39; // [rsp+70h] [rbp-90h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  v7 = 0;
  v39 = this;
  v38 = a6;
  v33 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  memset_0(Buffer, 0, 0x208u);
  v11 = 0;
  lpBuffer = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 46576);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  if ( a2 >= 13 || !a4 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 168, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    FileSizeAndTime = -2147024809;
    goto LABEL_64;
  }
  if ( !a5 )
    UtilPathTail(a4);
  FileSizeAndTime = UtilExpandEnvironmentStrings(a4);
  if ( FileSizeAndTime < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 169;
      v15 = (unsigned int)FileSizeAndTime;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v15);
      goto LABEL_64;
    }
    goto LABEL_64;
  }
  FullPathNameW = GetFullPathNameW(lpFileName[0], 0x104u, Buffer, 0);
  v17 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    FileSizeAndTime = ERROR_HR_FROM_WIN32(LastError);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_64;
    v20 = 170;
LABEL_14:
    v21 = (int)lpFileName[0];
    goto LABEL_15;
  }
  if ( FullPathNameW > 0x104 )
  {
    unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(v37, FullPathNameW);
    utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpBuffer, unique_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v37);
    v11 = lpBuffer;
    if ( !lpBuffer )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
      goto LABEL_21;
    }
    *lpBuffer = 0;
    if ( !GetFullPathNameW(lpFileName[0], v17, v11, 0) )
    {
      v23 = GetLastError();
      FileSizeAndTime = ERROR_HR_FROM_WIN32(v23);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_64;
      v20 = 172;
      goto LABEL_14;
    }
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpFileName);
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(lpFileName)
    || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(
                          lpFileName,
                          v24,
                          v25,
                          4) )
  {
    v26 = lpFileName[0];
    if ( (a3 & 0x4000000) == 0 && !UtilFileExists(lpFileName[0]) )
    {
      if ( a2 == 12 )
      {
LABEL_42:
        a3 |= 0x10000u;
        goto LABEL_43;
      }
      if ( (a3 & 0x100000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v26);
        FileSizeAndTime = -2147024894;
        goto LABEL_64;
      }
    }
    if ( a2 == 4 )
    {
      FileAttributesW = GetFileAttributesW(v26);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x4000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
        FileSizeAndTime = -2147024846;
        goto LABEL_64;
      }
    }
    else if ( a2 != 3 && a2 != 10 )
    {
      goto LABEL_42;
    }
LABEL_43:
    v27 = utl::make_unique<CReportFile,,0>(&lpBuffer);
    utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::operator=(&v33, v27);
    utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::~unique_ptr<CReportFile,utl::default_delete<CReportFile>>(&lpBuffer);
    v7 = (int *)v33;
    if ( v33 )
    {
      if ( (a3 & 0x8000000) != 0 )
      {
        FileSizeAndTime = GetFileSizeAndTime(v26, (unsigned __int64 *)(v33 + 8), (unsigned __int64 *)(v33 + 16));
        if ( FileSizeAndTime < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_64;
          v20 = 176;
          v21 = (int)v26;
LABEL_15:
          WPP_SF_SD(
            *((_QWORD *)v19 + 2),
            v20,
            (unsigned int)&WPP_6898268820d636d20e115db2eaa75970_Traceguids,
            v21,
            FileSizeAndTime);
          goto LABEL_64;
        }
      }
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v7 + 28)
        && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v7 + 36)
        && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v7 + 20)
        && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v7 + 44) )
      {
        v29 = v39;
        *v7 = a2;
        v7[1] = a3;
        v30 = utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::push_back(
                (char *)v29 + 5816,
                &v33);
        v7 = (int *)v33;
        FileSizeAndTime = v30 == 0 ? 0x8007000E : 0;
        goto LABEL_64;
      }
    }
LABEL_21:
    FileSizeAndTime = -2147024882;
    goto LABEL_64;
  }
  FileSizeAndTime = -2147024882;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v14 = 173;
    v15 = 2147942414LL;
    goto LABEL_9;
  }
LABEL_64:
  LeaveCriticalSection(lpCriticalSection);
  if ( v11 )
    HeapFree(g_hWerheap, 0, v11);
  if ( (char *)lpFileName[0] != &v36 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpFileName[0]);
  if ( v7 )
    utl::default_delete<CReportFile>::operator()(v31, v7);
  return (unsigned int)FileSizeAndTime;
}

```

## disassembly

```asm
0x18001b678  mov     [rsp-8+arg_8], rbx
0x18001b67d  push    rbp
0x18001b67e  push    rsi
0x18001b67f  push    rdi
0x18001b680  push    r12
0x18001b682  push    r13
0x18001b684  push    r14
0x18001b686  push    r15
0x18001b688  lea     rbp, [rsp-1A0h]
0x18001b690  sub     rsp, 2A0h
0x18001b697  mov     rax, cs:__security_cookie
0x18001b69e  xor     rax, rsp
0x18001b6a1  mov     [rbp+1D0h+var_40], rax
0x18001b6a8  mov     rax, [rbp+1D0h+arg_28]
0x18001b6af  mov     rsi, rcx
0x18001b6b2  mov     r13, [rbp+1D0h+arg_20]
0x18001b6b9  xor     edi, edi
0x18001b6bb  mov     [rsp+2D0h+var_260], rcx
0x18001b6c0  mov     rbx, r9
0x18001b6c3  lea     rcx, [rsp+2D0h+lpFileName]; void *
0x18001b6c8  mov     [rsp+2D0h+var_268], rax
0x18001b6cd  mov     [rsp+2D0h+var_2A0], rdi
0x18001b6d2  mov     r14d, r8d
0x18001b6d5  mov     r15d, edx
0x18001b6d8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18001b6dd  xor     edx, edx; Val
0x18001b6df  lea     rcx, [rbp+1D0h+Buffer]; void *
0x18001b6e3  mov     r8d, 208h; Size
0x18001b6e9  call    memset_0
0x18001b6ee  lea     rax, [rsi+0B5F0h]
0x18001b6f5  xor     r12d, r12d
0x18001b6f8  mov     rcx, rax; lpCriticalSection
0x18001b6fb  mov     [rsp+2D0h+lpBuffer], r12
0x18001b700  mov     [rsp+2D0h+lpCriticalSection], rax
0x18001b705  call    cs:__imp_EnterCriticalSection
0x18001b70b  cmp     r15d, 0Dh
0x18001b70f  jge     loc_18001BB12
0x18001b715  test    rbx, rbx
0x18001b718  jz      loc_18001BB12
0x18001b71e  test    r13, r13
0x18001b721  jnz     short loc_18001B72E
0x18001b723  mov     rcx, rbx; wchar_t *
0x18001b726  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18001b72b  mov     r13, rax
0x18001b72e  lea     rdx, [rsp+2D0h+lpFileName]
0x18001b733  mov     rcx, rbx; lpSrc
0x18001b736  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18001b73b  mov     ebx, eax
0x18001b73d  test    eax, eax
0x18001b73f  jns     short loc_18001B77F
0x18001b741  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b748  lea     rax, WPP_GLOBAL_Control
0x18001b74f  cmp     rcx, rax
0x18001b752  jz      loc_18001BB45
0x18001b758  test    byte ptr [rcx+1Ch], 1
0x18001b75c  jz      loc_18001BB45
0x18001b762  mov     edx, 0A9h
0x18001b767  mov     r9d, ebx
0x18001b76a  mov     rcx, [rcx+10h]
0x18001b76e  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001b775  call    WPP_SF_d
0x18001b77a  jmp     loc_18001BB45
0x18001b77f  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x18001b784  lea     r8, [rbp+1D0h+Buffer]; lpBuffer
0x18001b788  mov     esi, 104h
0x18001b78d  xor     r9d, r9d; lpFilePart
0x18001b790  mov     edx, esi; nBufferLength
0x18001b792  call    cs:__imp_GetFullPathNameW
0x18001b798  mov     ebx, eax
0x18001b79a  test    eax, eax
0x18001b79c  jnz     short loc_18001B7EF
0x18001b79e  call    cs:__imp_GetLastError
0x18001b7a4  mov     ecx, eax; unsigned int
0x18001b7a6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001b7ab  mov     ebx, eax
0x18001b7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7b4  lea     rax, WPP_GLOBAL_Control
0x18001b7bb  cmp     rcx, rax
0x18001b7be  jz      loc_18001BB45
0x18001b7c4  test    byte ptr [rcx+1Ch], 1
0x18001b7c8  jz      loc_18001BB45
0x18001b7ce  lea     edx, [rsi-5Ah]
0x18001b7d1  mov     r9, [rsp+2D0h+lpFileName]
0x18001b7d6  mov     rcx, [rcx+10h]
0x18001b7da  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001b7e1  mov     [rsp+2D0h+var_2B0], ebx
0x18001b7e5  call    WPP_SF_SD
0x18001b7ea  jmp     loc_18001BB45
0x18001b7ef  cmp     ebx, esi
0x18001b7f1  jbe     loc_18001B8BA
0x18001b7f7  mov     rdx, rbx
0x18001b7fa  lea     rcx, [rsp+2D0h+var_270]
0x18001b7ff  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x18001b804  mov     rdx, rax
0x18001b807  lea     rcx, [rsp+2D0h+lpBuffer]
0x18001b80c  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x18001b811  lea     rcx, [rsp+2D0h+var_270]; void *
0x18001b816  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18001b81b  mov     r12, [rsp+2D0h+lpBuffer]
0x18001b820  test    r12, r12
0x18001b823  jnz     short loc_18001B85D
0x18001b825  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b82c  lea     rax, WPP_GLOBAL_Control
0x18001b833  cmp     rcx, rax
0x18001b836  jz      short loc_18001B853
0x18001b838  test    byte ptr [rcx+1Ch], 1
0x18001b83c  jz      short loc_18001B853
0x18001b83e  mov     rcx, [rcx+10h]
0x18001b842  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001b849  mov     edx, 0ABh
0x18001b84e  call    WPP_SF_
0x18001b853  mov     ebx, 8007000Eh
0x18001b858  jmp     loc_18001BB45
0x18001b85d  xor     eax, eax
0x18001b85f  xor     r9d, r9d; lpFilePart
0x18001b862  mov     [r12], ax
0x18001b867  mov     r8, r12; lpBuffer
0x18001b86a  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x18001b86f  mov     edx, ebx; nBufferLength
0x18001b871  call    cs:__imp_GetFullPathNameW
0x18001b877  test    eax, eax
0x18001b879  jnz     short loc_18001B8B5
0x18001b87b  call    cs:__imp_GetLastError
0x18001b881  mov     ecx, eax; unsigned int
0x18001b883  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18001b888  mov     ebx, eax
0x18001b88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b891  lea     rax, WPP_GLOBAL_Control
0x18001b898  cmp     rcx, rax
0x18001b89b  jz      loc_18001BB45
0x18001b8a1  test    byte ptr [rcx+1Ch], 1
0x18001b8a5  jz      loc_18001BB45
0x18001b8ab  mov     edx, 0ACh
0x18001b8b0  jmp     loc_18001B7D1
0x18001b8b5  mov     rdx, r12
0x18001b8b8  jmp     short loc_18001B8BE
0x18001b8ba  lea     rdx, [rbp+1D0h+Buffer]
0x18001b8be  lea     rcx, [rsp+2D0h+lpFileName]
0x18001b8c3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001b8c8  lea     rcx, [rsp+2D0h+lpFileName]
0x18001b8cd  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x18001b8d2  test    al, al
0x18001b8d4  jnz     short loc_18001B920
0x18001b8d6  mov     r9d, 4
0x18001b8dc  lea     rcx, [rsp+2D0h+lpFileName]
0x18001b8e1  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
0x18001b8e6  test    al, al
0x18001b8e8  jnz     short loc_18001B920
0x18001b8ea  mov     ebx, 8007000Eh
0x18001b8ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8f6  lea     rax, WPP_GLOBAL_Control
0x18001b8fd  cmp     rcx, rax
0x18001b900  jz      loc_18001BB45
0x18001b906  test    byte ptr [rcx+1Ch], 1
0x18001b90a  jz      loc_18001BB45
0x18001b910  mov     edx, 0ADh
0x18001b915  mov     r9d, 8007000Eh
0x18001b91b  jmp     loc_18001B76A
0x18001b920  mov     rsi, [rsp+2D0h+lpFileName]
0x18001b925  bt      r14d, 1Ah
0x18001b92a  jb      short loc_18001B980
0x18001b92c  mov     rcx, rsi; lpSrc
0x18001b92f  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x18001b934  test    al, al
0x18001b936  jnz     short loc_18001B980
0x18001b938  cmp     r15d, 0Ch
0x18001b93c  jz      short loc_18001B996
0x18001b93e  bt      r14d, 14h
0x18001b943  jb      short loc_18001B980
0x18001b945  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b94c  lea     rax, WPP_GLOBAL_Control
0x18001b953  cmp     rcx, rax
0x18001b956  jz      short loc_18001B976
0x18001b958  test    byte ptr [rcx+1Ch], 1
0x18001b95c  jz      short loc_18001B976
0x18001b95e  mov     rcx, [rcx+10h]
0x18001b962  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001b969  mov     edx, 0AEh
0x18001b96e  mov     r9, rsi
0x18001b971  call    WPP_SF_S
0x18001b976  mov     ebx, 80070002h
0x18001b97b  jmp     loc_18001BB45
0x18001b980  cmp     r15d, 4
0x18001b984  jz      loc_18001BA1D
0x18001b98a  cmp     r15d, 3
0x18001b98e  jz      short loc_18001B99B
0x18001b990  cmp     r15d, 0Ah
0x18001b994  jz      short loc_18001B99B
0x18001b996  bts     r14d, 10h
0x18001b99b  lea     rcx, [rsp+2D0h+lpBuffer]
0x18001b9a0  call    ??$make_unique@VCReportFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@0@XZ; utl::make_unique<CReportFile,,0>(void)
0x18001b9a5  mov     rdx, rax
0x18001b9a8  lea     rcx, [rsp+2D0h+var_2A0]
0x18001b9ad  call    ??4?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::operator=(utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>> &&)
0x18001b9b2  lea     rcx, [rsp+2D0h+lpBuffer]
0x18001b9b7  call    ??1?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::~unique_ptr<CReportFile,utl::default_delete<CReportFile>>(void)
0x18001b9bc  mov     rdi, [rsp+2D0h+var_2A0]
0x18001b9c1  test    rdi, rdi
0x18001b9c4  jz      loc_18001B853
0x18001b9ca  bt      r14d, 1Bh
0x18001b9cf  jnb     loc_18001BA71
0x18001b9d5  lea     r8, [rdi+10h]; unsigned __int64 *
0x18001b9d9  mov     rcx, rsi; wchar_t *
0x18001b9dc  lea     rdx, [rdi+8]; unsigned __int64 *
0x18001b9e0  call    ?GetFileSizeAndTime@@YAJPEB_WPEA_K1@Z; GetFileSizeAndTime(wchar_t const *,unsigned __int64 *,unsigned __int64 *)
0x18001b9e5  mov     ebx, eax
0x18001b9e7  test    eax, eax
0x18001b9e9  jns     loc_18001BA71
0x18001b9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9f6  lea     rax, WPP_GLOBAL_Control
0x18001b9fd  cmp     rcx, rax
0x18001ba00  jz      loc_18001BB45
0x18001ba06  test    byte ptr [rcx+1Ch], 1
0x18001ba0a  jz      loc_18001BB45
0x18001ba10  mov     edx, 0B0h
0x18001ba15  mov     r9, rsi
0x18001ba18  jmp     loc_18001B7D6
0x18001ba1d  mov     rcx, rsi; lpFileName
0x18001ba20  call    cs:__imp_GetFileAttributesW
0x18001ba26  cmp     eax, 0FFFFFFFFh
0x18001ba29  jz      loc_18001B99B
0x18001ba2f  bt      eax, 0Eh
0x18001ba33  jnb     loc_18001B99B
0x18001ba39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba40  lea     rax, WPP_GLOBAL_Control
0x18001ba47  cmp     rcx, rax
0x18001ba4a  jz      short loc_18001BA67
0x18001ba4c  test    byte ptr [rcx+1Ch], 1
0x18001ba50  jz      short loc_18001BA67
0x18001ba52  mov     rcx, [rcx+10h]
0x18001ba56  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001ba5d  mov     edx, 0AFh
0x18001ba62  call    WPP_SF_
0x18001ba67  mov     ebx, 80070032h
0x18001ba6c  jmp     loc_18001BB45
0x18001ba71  lea     rcx, [rdi+70h]
0x18001ba75  mov     rdx, rsi
0x18001ba78  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001ba7d  test    al, al
0x18001ba7f  jz      loc_18001B853
0x18001ba85  lea     rcx, [rdi+90h]
0x18001ba8c  mov     rdx, rsi
0x18001ba8f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001ba94  test    al, al
0x18001ba96  jz      loc_18001B853
0x18001ba9c  lea     rbx, Src
0x18001baa3  test    r13, r13
0x18001baa6  mov     rdx, rbx
0x18001baa9  lea     rcx, [rdi+50h]
0x18001baad  cmovnz  rdx, r13
0x18001bab1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001bab6  test    al, al
0x18001bab8  jz      loc_18001B853
0x18001babe  mov     rax, [rsp+2D0h+var_268]
0x18001bac3  lea     rcx, [rdi+0B0h]
0x18001baca  test    rax, rax
0x18001bacd  cmovz   rax, rbx
0x18001bad1  mov     rdx, rax
0x18001bad4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x18001bad9  test    al, al
0x18001badb  jz      loc_18001B853
0x18001bae1  mov     rcx, [rsp+2D0h+var_260]
0x18001bae6  lea     rdx, [rsp+2D0h+var_2A0]
0x18001baeb  mov     [rdi], r15d
0x18001baee  add     rcx, 16B8h
0x18001baf5  mov     [rdi+4], r14d
0x18001baf9  call    ?push_back@?$vector@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::push_back(utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>> &&)
0x18001bafe  mov     rdi, [rsp+2D0h+var_2A0]
0x18001bb03  neg     al
0x18001bb05  mov     ebx, 8007000Eh
0x18001bb0a  sbb     ecx, ecx
0x18001bb0c  not     ecx
0x18001bb0e  and     ebx, ecx
0x18001bb10  jmp     short loc_18001BB45
0x18001bb12  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb19  lea     rax, WPP_GLOBAL_Control
0x18001bb20  cmp     rcx, rax
0x18001bb23  jz      short loc_18001BB40
0x18001bb25  test    byte ptr [rcx+1Ch], 1
0x18001bb29  jz      short loc_18001BB40
0x18001bb2b  mov     rcx, [rcx+10h]
0x18001bb2f  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18001bb36  mov     edx, 0A8h
0x18001bb3b  call    WPP_SF_
0x18001bb40  mov     ebx, 80070057h
0x18001bb45  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x18001bb4a  call    cs:__imp_LeaveCriticalSection
0x18001bb50  test    r12, r12
0x18001bb53  jz      short loc_18001BB67
0x18001bb55  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001bb5c  mov     r8, r12; lpMem
0x18001bb5f  xor     edx, edx; dwFlags
0x18001bb61  call    cs:__imp_HeapFree
0x18001bb67  mov     r8, [rsp+2D0h+lpFileName]; lpMem
0x18001bb6c  lea     rax, [rsp+2D0h+var_280]
0x18001bb71  cmp     r8, rax
0x18001bb74  jz      short loc_18001BB85
0x18001bb76  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18001bb7d  xor     edx, edx; dwFlags
0x18001bb7f  call    cs:__imp_HeapFree
  ... truncated ...
```
