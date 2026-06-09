# CReport::AddFile(_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x180008698`
- end: `0x180008c15`
- name: `?AddFile@CReport@@QEAAJW4_WER_FILE_TYPE@@KPEB_W11@Z`
- size: `1405`
- prototype: `int(CReport *__hidden this, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `16`
- callee_count: `24`
- tags: `file_ops`

## callers

- `0x180009074`
- `0x18001e134`
- `0x180025600`
- `0x180030058`
- `0x180037cb8`
- `0x180044a18`
- `0x18004b858`
- `0x18004d2d4`
- `0x180051270`
- `0x180078f5c`
- `0x18007cd68`
- `0x180083038`
- `0x18008f2ec`
- `0x18008fe08`
- `0x1800909f4`
- `0x180090b54`

## callees

- `0x180004c64`
- `0x180008698`
- `0x18000cf50`
- `0x18000da00`
- `0x1800170b0`
- `0x180018000`
- `0x18001c368`
- `0x18001e0d0`
- `0x18001f3a0`
- `0x180020680`
- `0x18002219c`
- `0x18002d75c`
- `0x18002d8c8`
- `0x18002d99c`
- `0x18002e8f4`
- `0x18003b180`
- `0x180042f4c`
- `0x1800459c0`
- `0x180053300`
- `0x180053d3c`
- `0x180073934`
- `0x180078910`
- `0x18007b324`
- `0x18009b81c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bcf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008bcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008725`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b8e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800087b8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800088a3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800087b8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800088a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008a5e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008a5e`

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
  const wchar_t *v7; // r13
  int *v8; // rdi
  WCHAR *v12; // r12
  signed int FileSizeAndTime; // ebx
  wchar_t *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  DWORD FullPathNameW; // eax
  DWORD v18; // ebx
  DWORD LastError; // eax
  wchar_t *v20; // rcx
  int v21; // edx
  int v22; // r9d
  __int64 unique_for; // rax
  DWORD v24; // eax
  WCHAR *v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  WCHAR *v28; // rsi
  __int64 v29; // rax
  DWORD FileAttributesW; // eax
  size_t *v31; // rdx
  size_t *v32; // rax
  CReport *v33; // rcx
  char v34; // al
  __int64 v35; // rcx
  __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v40; // [rsp+50h] [rbp-B0h] BYREF
  char v41[8]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v42; // [rsp+68h] [rbp-98h]
  CReport *v43; // [rsp+70h] [rbp-90h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  v7 = a5;
  v8 = 0;
  v43 = this;
  v42 = a6;
  v37 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  memset_0(Buffer, 0, 0x208u);
  v12 = 0;
  lpBuffer = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 46576);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  if ( a2 >= 13 || !a4 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    FileSizeAndTime = -2147024809;
    goto LABEL_70;
  }
  if ( !a5 )
    v7 = UtilPathTail(a4);
  FileSizeAndTime = UtilExpandEnvironmentStrings(a4);
  if ( FileSizeAndTime < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v15 = 170;
      v16 = (unsigned int)FileSizeAndTime;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v16);
      goto LABEL_70;
    }
    goto LABEL_70;
  }
  FullPathNameW = GetFullPathNameW(lpFileName[0], 0x104u, Buffer, 0);
  v18 = FullPathNameW;
  if ( !FullPathNameW )
  {
    LastError = GetLastError();
    FileSizeAndTime = ERROR_HR_FROM_WIN32(LastError);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_70;
    v21 = 171;
LABEL_14:
    v22 = (int)lpFileName[0];
    goto LABEL_15;
  }
  if ( FullPathNameW <= 0x104 )
  {
    v25 = Buffer;
  }
  else
  {
    unique_for = utl::make_unique_for_overwrite<wchar_t [0],0>(v41, FullPathNameW);
    utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(&lpBuffer, unique_for);
    utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(v41);
    v12 = lpBuffer;
    if ( !lpBuffer )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
      goto LABEL_21;
    }
    *lpBuffer = 0;
    if ( !GetFullPathNameW(lpFileName[0], v18, v12, 0) )
    {
      v24 = GetLastError();
      FileSizeAndTime = ERROR_HR_FROM_WIN32(v24);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_70;
      v21 = 173;
      goto LABEL_14;
    }
    v25 = v12;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(lpFileName, v25);
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(lpFileName)
    || (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(
                          lpFileName,
                          v26,
                          v27,
                          4) )
  {
    v28 = (WCHAR *)lpFileName[0];
    if ( (a3 & 0x4000000) == 0 && !UtilFileExists(lpFileName[0]) )
    {
      if ( a2 == 12 )
      {
LABEL_44:
        a3 |= 0x10000u;
        goto LABEL_45;
      }
      if ( (a3 & 0x100000) == 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v28);
        FileSizeAndTime = -2147024894;
        goto LABEL_70;
      }
    }
    if ( a2 == 4 )
    {
      FileAttributesW = GetFileAttributesW(v28);
      if ( FileAttributesW != -1 && (FileAttributesW & 0x4000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
        FileSizeAndTime = -2147024846;
        goto LABEL_70;
      }
    }
    else if ( a2 != 3 && a2 != 10 )
    {
      goto LABEL_44;
    }
LABEL_45:
    v29 = utl::make_unique<CReportFile,,0>(&lpBuffer);
    utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::operator=(&v37, v29);
    utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::~unique_ptr<CReportFile,utl::default_delete<CReportFile>>(&lpBuffer);
    v8 = (int *)v37;
    if ( v37 )
    {
      if ( (a3 & 0x8000000) != 0 )
      {
        FileSizeAndTime = GetFileSizeAndTime(v28, (unsigned __int64 *)(v37 + 8), (unsigned __int64 *)(v37 + 16));
        if ( FileSizeAndTime < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_70;
          v21 = 177;
          v22 = (int)v28;
LABEL_15:
          WPP_SF_SD(
            *((_QWORD *)v20 + 2),
            v21,
            (unsigned int)WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
            v22,
            FileSizeAndTime);
          goto LABEL_70;
        }
      }
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              v8 + 28,
                              v28)
        && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              v8 + 36,
                              v28) )
      {
        v31 = (size_t *)&Src;
        if ( v7 )
          v31 = (size_t *)v7;
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                v8 + 20,
                                v31) )
        {
          v32 = (size_t *)v42;
          if ( !v42 )
            v32 = (size_t *)&Src;
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  v8 + 44,
                                  v32) )
          {
            v33 = v43;
            *v8 = a2;
            v8[1] = a3;
            v34 = utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::push_back(
                    (char *)v33 + 5816,
                    &v37);
            v8 = (int *)v37;
            FileSizeAndTime = v34 == 0 ? 0x8007000E : 0;
            goto LABEL_70;
          }
        }
      }
    }
LABEL_21:
    FileSizeAndTime = -2147024882;
    goto LABEL_70;
  }
  FileSizeAndTime = -2147024882;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v15 = 174;
    v16 = 2147942414LL;
    goto LABEL_9;
  }
LABEL_70:
  LeaveCriticalSection(lpCriticalSection);
  if ( v12 )
    HeapFree(g_hWerheap, 0, v12);
  if ( (char *)lpFileName[0] != &v40 )
    HeapFree(g_hWerheap, 0, (LPVOID)lpFileName[0]);
  if ( v8 )
    utl::default_delete<CReportFile>::operator()(v35, v8);
  return (unsigned int)FileSizeAndTime;
}

```

## disassembly

```asm
0x180008698  mov     [rsp-8+arg_8], rbx
0x18000869d  push    rbp
0x18000869e  push    rsi
0x18000869f  push    rdi
0x1800086a0  push    r12
0x1800086a2  push    r13
0x1800086a4  push    r14
0x1800086a6  push    r15
0x1800086a8  lea     rbp, [rsp-1A0h]
0x1800086b0  sub     rsp, 2A0h
0x1800086b7  mov     rax, cs:__security_cookie
0x1800086be  xor     rax, rsp
0x1800086c1  mov     [rbp+1D0h+var_40], rax
0x1800086c8  mov     rax, [rbp+1D0h+arg_28]
0x1800086cf  mov     rsi, rcx
0x1800086d2  mov     r13, [rbp+1D0h+arg_20]
0x1800086d9  xor     edi, edi
0x1800086db  mov     [rsp+2D0h+var_260], rcx
0x1800086e0  mov     rbx, r9
0x1800086e3  lea     rcx, [rsp+2D0h+lpFileName]; void *
0x1800086e8  mov     [rsp+2D0h+var_268], rax
0x1800086ed  mov     [rsp+2D0h+var_2A0], rdi
0x1800086f2  mov     r14d, r8d
0x1800086f5  mov     r15d, edx
0x1800086f8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800086fd  xor     edx, edx; Val
0x1800086ff  lea     rcx, [rbp+1D0h+Buffer]; void *
0x180008703  mov     r8d, 208h; Size
0x180008709  call    memset_0
0x18000870e  lea     rax, [rsi+0B5F0h]
0x180008715  xor     r12d, r12d
0x180008718  mov     rcx, rax; lpCriticalSection
0x18000871b  mov     [rsp+2D0h+lpBuffer], r12
0x180008720  mov     [rsp+2D0h+lpCriticalSection], rax
0x180008725  call    cs:__imp_EnterCriticalSection
0x18000872c  nop     dword ptr [rax+rax+00h]
0x180008731  cmp     r15d, 0Dh
0x180008735  jge     loc_180008B56
0x18000873b  test    rbx, rbx
0x18000873e  jz      loc_180008B56
0x180008744  test    r13, r13
0x180008747  jnz     short loc_180008754
0x180008749  mov     rcx, rbx; wchar_t *
0x18000874c  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x180008751  mov     r13, rax
0x180008754  lea     rdx, [rsp+2D0h+lpFileName]
0x180008759  mov     rcx, rbx; lpSrc
0x18000875c  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180008761  mov     ebx, eax
0x180008763  test    eax, eax
0x180008765  jns     short loc_1800087A5
0x180008767  mov     rcx, cs:WPP_GLOBAL_Control
0x18000876e  lea     rax, WPP_GLOBAL_Control
0x180008775  cmp     rcx, rax
0x180008778  jz      loc_180008B89
0x18000877e  test    byte ptr [rcx+1Ch], 1
0x180008782  jz      loc_180008B89
0x180008788  mov     edx, 0AAh
0x18000878d  mov     r9d, ebx
0x180008790  mov     rcx, [rcx+10h]
0x180008794  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18000879b  call    WPP_SF_d
0x1800087a0  jmp     loc_180008B89
0x1800087a5  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x1800087aa  lea     r8, [rbp+1D0h+Buffer]; lpBuffer
0x1800087ae  mov     esi, 104h
0x1800087b3  xor     r9d, r9d; lpFilePart
0x1800087b6  mov     edx, esi; nBufferLength
0x1800087b8  call    cs:__imp_GetFullPathNameW
0x1800087bf  nop     dword ptr [rax+rax+00h]
0x1800087c4  mov     ebx, eax
0x1800087c6  test    eax, eax
0x1800087c8  jnz     short loc_180008821
0x1800087ca  call    cs:__imp_GetLastError
0x1800087d1  nop     dword ptr [rax+rax+00h]
0x1800087d6  mov     ecx, eax; unsigned int
0x1800087d8  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800087dd  mov     ebx, eax
0x1800087df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087e6  lea     rax, WPP_GLOBAL_Control
0x1800087ed  cmp     rcx, rax
0x1800087f0  jz      loc_180008B89
0x1800087f6  test    byte ptr [rcx+1Ch], 1
0x1800087fa  jz      loc_180008B89
0x180008800  lea     edx, [rsi-59h]
0x180008803  mov     r9, [rsp+2D0h+lpFileName]
0x180008808  mov     rcx, [rcx+10h]
0x18000880c  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180008813  mov     [rsp+2D0h+var_2B0], ebx
0x180008817  call    WPP_SF_SD
0x18000881c  jmp     loc_180008B89
0x180008821  cmp     ebx, esi
0x180008823  jbe     loc_1800088F8
0x180008829  mov     rdx, rbx
0x18000882c  lea     rcx, [rsp+2D0h+var_270]
0x180008831  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180008836  mov     rdx, rax
0x180008839  lea     rcx, [rsp+2D0h+lpBuffer]
0x18000883e  call    ??4?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>>::operator=(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &&)
0x180008843  lea     rcx, [rsp+2D0h+var_270]; void *
0x180008848  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18000884d  mov     r12, [rsp+2D0h+lpBuffer]
0x180008852  test    r12, r12
0x180008855  jnz     short loc_18000888F
0x180008857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000885e  lea     rax, WPP_GLOBAL_Control
0x180008865  cmp     rcx, rax
0x180008868  jz      short loc_180008885
0x18000886a  test    byte ptr [rcx+1Ch], 1
0x18000886e  jz      short loc_180008885
0x180008870  mov     rcx, [rcx+10h]
0x180008874  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18000887b  mov     edx, 0ACh
0x180008880  call    WPP_SF_
0x180008885  mov     ebx, 8007000Eh
0x18000888a  jmp     loc_180008B89
0x18000888f  xor     eax, eax
0x180008891  xor     r9d, r9d; lpFilePart
0x180008894  mov     [r12], ax
0x180008899  mov     r8, r12; lpBuffer
0x18000889c  mov     rcx, [rsp+2D0h+lpFileName]; lpFileName
0x1800088a1  mov     edx, ebx; nBufferLength
0x1800088a3  call    cs:__imp_GetFullPathNameW
0x1800088aa  nop     dword ptr [rax+rax+00h]
0x1800088af  test    eax, eax
0x1800088b1  jnz     short loc_1800088F3
0x1800088b3  call    cs:__imp_GetLastError
0x1800088ba  nop     dword ptr [rax+rax+00h]
0x1800088bf  mov     ecx, eax; unsigned int
0x1800088c1  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800088c6  mov     ebx, eax
0x1800088c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088cf  lea     rax, WPP_GLOBAL_Control
0x1800088d6  cmp     rcx, rax
0x1800088d9  jz      loc_180008B89
0x1800088df  test    byte ptr [rcx+1Ch], 1
0x1800088e3  jz      loc_180008B89
0x1800088e9  mov     edx, 0ADh
0x1800088ee  jmp     loc_180008803
0x1800088f3  mov     rdx, r12
0x1800088f6  jmp     short loc_1800088FC
0x1800088f8  lea     rdx, [rbp+1D0h+Buffer]
0x1800088fc  lea     rcx, [rsp+2D0h+lpFileName]
0x180008901  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008906  lea     rcx, [rsp+2D0h+lpFileName]
0x18000890b  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x180008910  test    al, al
0x180008912  jnz     short loc_18000895E
0x180008914  mov     r9d, 4
0x18000891a  lea     rcx, [rsp+2D0h+lpFileName]
0x18000891f  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
0x180008924  test    al, al
0x180008926  jnz     short loc_18000895E
0x180008928  mov     ebx, 8007000Eh
0x18000892d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008934  lea     rax, WPP_GLOBAL_Control
0x18000893b  cmp     rcx, rax
0x18000893e  jz      loc_180008B89
0x180008944  test    byte ptr [rcx+1Ch], 1
0x180008948  jz      loc_180008B89
0x18000894e  mov     edx, 0AEh
0x180008953  mov     r9d, 8007000Eh
0x180008959  jmp     loc_180008790
0x18000895e  mov     rsi, [rsp+2D0h+lpFileName]
0x180008963  bt      r14d, 1Ah
0x180008968  jb      short loc_1800089BE
0x18000896a  mov     rcx, rsi; lpSrc
0x18000896d  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x180008972  test    al, al
0x180008974  jnz     short loc_1800089BE
0x180008976  cmp     r15d, 0Ch
0x18000897a  jz      short loc_1800089D4
0x18000897c  bt      r14d, 14h
0x180008981  jb      short loc_1800089BE
0x180008983  mov     rcx, cs:WPP_GLOBAL_Control
0x18000898a  lea     rax, WPP_GLOBAL_Control
0x180008991  cmp     rcx, rax
0x180008994  jz      short loc_1800089B4
0x180008996  test    byte ptr [rcx+1Ch], 1
0x18000899a  jz      short loc_1800089B4
0x18000899c  mov     rcx, [rcx+10h]
0x1800089a0  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x1800089a7  mov     edx, 0AFh
0x1800089ac  mov     r9, rsi
0x1800089af  call    WPP_SF_S
0x1800089b4  mov     ebx, 80070002h
0x1800089b9  jmp     loc_180008B89
0x1800089be  cmp     r15d, 4
0x1800089c2  jz      loc_180008A5B
0x1800089c8  cmp     r15d, 3
0x1800089cc  jz      short loc_1800089D9
0x1800089ce  cmp     r15d, 0Ah
0x1800089d2  jz      short loc_1800089D9
0x1800089d4  bts     r14d, 10h
0x1800089d9  lea     rcx, [rsp+2D0h+lpBuffer]
0x1800089de  call    ??$make_unique@VCReportFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@0@XZ; utl::make_unique<CReportFile,,0>(void)
0x1800089e3  mov     rdx, rax
0x1800089e6  lea     rcx, [rsp+2D0h+var_2A0]
0x1800089eb  call    ??4?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::operator=(utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>> &&)
0x1800089f0  lea     rcx, [rsp+2D0h+lpBuffer]
0x1800089f5  call    ??1?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>::~unique_ptr<CReportFile,utl::default_delete<CReportFile>>(void)
0x1800089fa  mov     rdi, [rsp+2D0h+var_2A0]
0x1800089ff  test    rdi, rdi
0x180008a02  jz      loc_180008885
0x180008a08  bt      r14d, 1Bh
0x180008a0d  jnb     loc_180008AB5
0x180008a13  lea     r8, [rdi+10h]; unsigned __int64 *
0x180008a17  mov     rcx, rsi; wchar_t *
0x180008a1a  lea     rdx, [rdi+8]; unsigned __int64 *
0x180008a1e  call    ?GetFileSizeAndTime@@YAJPEB_WPEA_K1@Z; GetFileSizeAndTime(wchar_t const *,unsigned __int64 *,unsigned __int64 *)
0x180008a23  mov     ebx, eax
0x180008a25  test    eax, eax
0x180008a27  jns     loc_180008AB5
0x180008a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a34  lea     rax, WPP_GLOBAL_Control
0x180008a3b  cmp     rcx, rax
0x180008a3e  jz      loc_180008B89
0x180008a44  test    byte ptr [rcx+1Ch], 1
0x180008a48  jz      loc_180008B89
0x180008a4e  mov     edx, 0B1h
0x180008a53  mov     r9, rsi
0x180008a56  jmp     loc_180008808
0x180008a5b  mov     rcx, rsi; lpFileName
0x180008a5e  call    cs:__imp_GetFileAttributesW
0x180008a65  nop     dword ptr [rax+rax+00h]
0x180008a6a  cmp     eax, 0FFFFFFFFh
0x180008a6d  jz      loc_1800089D9
0x180008a73  bt      eax, 0Eh
0x180008a77  jnb     loc_1800089D9
0x180008a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a84  lea     rax, WPP_GLOBAL_Control
0x180008a8b  cmp     rcx, rax
0x180008a8e  jz      short loc_180008AAB
0x180008a90  test    byte ptr [rcx+1Ch], 1
0x180008a94  jz      short loc_180008AAB
0x180008a96  mov     rcx, [rcx+10h]
0x180008a9a  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180008aa1  mov     edx, 0B0h
0x180008aa6  call    WPP_SF_
0x180008aab  mov     ebx, 80070032h
0x180008ab0  jmp     loc_180008B89
0x180008ab5  lea     rcx, [rdi+70h]
0x180008ab9  mov     rdx, rsi
0x180008abc  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008ac1  test    al, al
0x180008ac3  jz      loc_180008885
0x180008ac9  lea     rcx, [rdi+90h]
0x180008ad0  mov     rdx, rsi
0x180008ad3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008ad8  test    al, al
0x180008ada  jz      loc_180008885
0x180008ae0  lea     rbx, Src
0x180008ae7  test    r13, r13
0x180008aea  mov     rdx, rbx
0x180008aed  lea     rcx, [rdi+50h]
0x180008af1  cmovnz  rdx, r13
0x180008af5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008afa  test    al, al
0x180008afc  jz      loc_180008885
0x180008b02  mov     rax, [rsp+2D0h+var_268]
0x180008b07  lea     rcx, [rdi+0B0h]
0x180008b0e  test    rax, rax
0x180008b11  cmovz   rax, rbx
0x180008b15  mov     rdx, rax
0x180008b18  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180008b1d  test    al, al
0x180008b1f  jz      loc_180008885
0x180008b25  mov     rcx, [rsp+2D0h+var_260]
0x180008b2a  lea     rdx, [rsp+2D0h+var_2A0]
0x180008b2f  mov     [rdi], r15d
0x180008b32  add     rcx, 16B8h
0x180008b39  mov     [rdi+4], r14d
0x180008b3d  call    ?push_back@?$vector@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@VCReportFile@@U?$default_delete@VCReportFile@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>,utl::allocator<utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>>>>::push_back(utl::unique_ptr<CReportFile,utl::default_delete<CReportFile>> &&)
0x180008b42  mov     rdi, [rsp+2D0h+var_2A0]
0x180008b47  neg     al
0x180008b49  mov     ebx, 8007000Eh
0x180008b4e  sbb     ecx, ecx
0x180008b50  not     ecx
0x180008b52  and     ebx, ecx
0x180008b54  jmp     short loc_180008B89
0x180008b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b5d  lea     rax, WPP_GLOBAL_Control
0x180008b64  cmp     rcx, rax
0x180008b67  jz      short loc_180008B84
0x180008b69  test    byte ptr [rcx+1Ch], 1
0x180008b6d  jz      short loc_180008B84
0x180008b6f  mov     rcx, [rcx+10h]
0x180008b73  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180008b7a  mov     edx, 0A9h
0x180008b7f  call    WPP_SF_
0x180008b84  mov     ebx, 80070057h
0x180008b89  mov     rcx, [rsp+2D0h+lpCriticalSection]; lpCriticalSection
0x180008b8e  call    cs:__imp_LeaveCriticalSection
0x180008b95  nop     dword ptr [rax+rax+00h]
0x180008b9a  test    r12, r12
0x180008b9d  jz      short loc_180008BB7
0x180008b9f  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180008ba6  mov     r8, r12; lpMem
0x180008ba9  xor     edx, edx; dwFlags
0x180008bab  call    cs:__imp_HeapFree
  ... truncated ...
```
