# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005568`
- end: `0x180005959`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180005d1c`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x1800041f8`
- `0x180005568`
- `0x180005a20`
- `0x180006098`
- `0x180008158`
- `0x180009870`
- `0x18000b744`
- `0x18000c364`
- `0x18000c80c`
- `0x18000d1fc`
- `0x18000d20c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000583b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000583b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005696`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000586e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005696`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000586e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005600`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005600`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800055df`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800055df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000578d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005884`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000578d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005884`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000579b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000579b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180005568  mov     [rsp-8+arg_10], rbx
0x18000556d  push    rbp
0x18000556e  push    rsi
0x18000556f  push    rdi
0x180005570  push    r14
0x180005572  push    r15
0x180005574  lea     rbp, [rsp-160h]
0x18000557c  sub     rsp, 260h
0x180005583  mov     rax, cs:__security_cookie
0x18000558a  xor     rax, rsp
0x18000558d  mov     [rbp+180h+var_30], rax
0x180005594  mov     r15, rdx
0x180005597  mov     qword ptr [rdx], 0
0x18000559e  mov     rbx, rcx
0x1800055a1  call    cs:__imp_GetCurrentProcessId
0x1800055a7  mov     r14d, 130h
0x1800055ad  mov     [rsp+280h+var_258], rbx
0x1800055b2  mov     r9d, eax
0x1800055b5  mov     [rsp+280h+var_260], r14d; int
0x1800055ba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800055c1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800055c6  lea     edx, [r14-2Ch]; unsigned __int64
0x1800055ca  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800055cf  mov     r9d, 1F0001h; dwDesiredAccess
0x1800055d5  lea     rdx, [rsp+280h+Name]; lpName
0x1800055da  xor     r8d, r8d; dwFlags
0x1800055dd  xor     ecx, ecx; lpMutexAttributes
0x1800055df  call    cs:__imp_CreateMutexExW
0x1800055e5  mov     rbx, rax
0x1800055e8  test    rax, rax
0x1800055eb  jnz     short loc_1800055F7
0x1800055ed  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800055f2  jmp     loc_180005890
0x1800055f7  xor     r8d, r8d; bAlertable
0x1800055fa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800055fd  mov     rcx, rbx; hHandle
0x180005600  call    cs:__imp_WaitForSingleObjectEx
0x180005606  cmp     eax, 102h
0x18000560b  jz      short loc_18000561D
0x18000560d  test    eax, 0FFFFFF7Fh
0x180005612  jnz     loc_1800058DA
0x180005618  mov     rdi, rbx
0x18000561b  jmp     short loc_18000561F
0x18000561d  xor     edi, edi
0x18000561f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005624  mov     [rsp+280h+hObject], 0
0x18000562d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005632  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005637  mov     esi, eax
0x180005639  test    eax, eax
0x18000563b  jns     short loc_1800056BC
0x18000563d  mov     rcx, [rbp+188h]; this
0x180005644  lea     r8, aWil; "wil"
0x18000564b  mov     r9d, eax; char *
0x18000564e  mov     edx, 66h ; 'f'; void *
0x180005653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005658  mov     rcx, [rbp+188h]; this
0x18000565f  lea     r8, aWil; "wil"
0x180005666  mov     r9d, esi; char *
0x180005669  mov     edx, 6Fh ; 'o'; void *
0x18000566e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005673  mov     rcx, [rbp+188h]; this
0x18000567a  lea     r8, aWil; "wil"
0x180005681  mov     r9d, esi; char *
0x180005684  mov     edx, 12Eh; void *
0x180005689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000568e  test    rdi, rdi
0x180005691  jz      short loc_1800056A4
0x180005693  mov     rcx, rdi; hMutex
0x180005696  call    cs:__imp_ReleaseMutex
0x18000569c  test    eax, eax
0x18000569e  jz      loc_1800058E7
0x1800056a4  mov     rcx, rbx; hObject
0x1800056a7  call    cs:__imp_CloseHandle
0x1800056ad  test    eax, eax
0x1800056af  jz      loc_1800058F9
0x1800056b5  mov     eax, esi
0x1800056b7  jmp     loc_180005890
0x1800056bc  mov     rax, [rsp+280h+hObject]
0x1800056c1  lea     rcx, ds:0[rax*4]
0x1800056c9  test    rcx, rcx
0x1800056cc  jz      short loc_1800056DC
0x1800056ce  mov     [r15], rcx
0x1800056d1  mov     eax, [rcx]
0x1800056d3  inc     eax
0x1800056d5  mov     [rcx], eax
0x1800056d7  jmp     loc_180005866
0x1800056dc  mov     rdx, r14; dwBytes
0x1800056df  mov     qword ptr [r15], 0
0x1800056e6  mov     ecx, 8; dwFlags
0x1800056eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800056f0  mov     r14, rax
0x1800056f3  test    rax, rax
0x1800056f6  jnz     short loc_18000571D
0x1800056f8  mov     rcx, [rbp+188h]; this
0x1800056ff  lea     r8, aWil; "wil"
0x180005706  mov     esi, 8007000Eh
0x18000570b  mov     edx, 14Bh; void *
0x180005710  mov     r9d, esi; char *
0x180005713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005718  jmp     loc_1800057AF
0x18000571d  xorps   xmm0, xmm0
0x180005720  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005726  test    r14b, 3
0x18000572a  jnz     loc_18000590B
0x180005730  mov     r9, r14
0x180005733  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180005738  shr     r9, 2; unsigned __int64
0x18000573c  lea     rcx, [rsp+280h+hObject]; this
0x180005741  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005746  mov     esi, eax
0x180005748  test    eax, eax
0x18000574a  jns     loc_1800057F6
0x180005750  mov     rcx, [rbp+188h]; this
0x180005757  lea     r8, aWil; "wil"
0x18000575e  mov     r9d, eax; char *
0x180005761  mov     edx, 14Eh; void *
0x180005766  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000576b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005770  test    rcx, rcx
0x180005773  jz      short loc_180005783
0x180005775  call    cs:__imp_CloseHandle
0x18000577b  test    eax, eax
0x18000577d  jz      loc_180005911
0x180005783  mov     rcx, [rsp+280h+hObject]; hObject
0x180005788  test    rcx, rcx
0x18000578b  jz      short loc_18000579B
0x18000578d  call    cs:__imp_CloseHandle
0x180005793  test    eax, eax
0x180005795  jz      loc_180005923
0x18000579b  call    cs:__imp_GetProcessHeap
0x1800057a1  mov     r8, r14; lpMem
0x1800057a4  xor     edx, edx; dwFlags
0x1800057a6  mov     rcx, rax; hHeap
0x1800057a9  call    cs:__imp_HeapFree
0x1800057af  mov     rcx, [rbp+188h]; this
0x1800057b6  lea     r8, aWil; "wil"
0x1800057bd  mov     r9d, esi; char *
0x1800057c0  mov     edx, 137h; void *
0x1800057c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057ca  test    rdi, rdi
0x1800057cd  jz      short loc_1800057E0
0x1800057cf  mov     rcx, rdi; hMutex
0x1800057d2  call    cs:__imp_ReleaseMutex
0x1800057d8  test    eax, eax
0x1800057da  jz      loc_180005935
0x1800057e0  mov     rcx, rbx; hObject
0x1800057e3  call    cs:__imp_CloseHandle
0x1800057e9  test    eax, eax
0x1800057eb  jz      loc_1800058C8
0x1800057f1  jmp     loc_1800056B5
0x1800057f6  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800057fb  lea     rcx, [r14+28h]; void *
0x1800057ff  mov     dword ptr [r14], 1
0x180005806  xor     edx, edx; Val
0x180005808  mov     [r14+8], rbx
0x18000580c  mov     r8d, 108h; Size
0x180005812  movdqu  xmmword ptr [r14+10h], xmm0
0x180005818  call    memset_0
0x18000581d  xor     eax, eax
0x18000581f  lea     rcx, [r14+28h]; this
0x180005823  mov     [r14+20h], rax
0x180005827  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000582c  lea     rbx, [r14+0E8h]
0x180005833  xor     r8d, r8d; Flags
0x180005836  mov     rcx, rbx; lpCriticalSection
0x180005839  xor     edx, edx; dwSpinCount
0x18000583b  call    cs:__imp_InitializeCriticalSectionEx
0x180005841  mov     qword ptr [rbx+28h], 0
0x180005849  mov     qword ptr [rbx+30h], 0
0x180005851  mov     qword ptr [rbx+38h], 0
0x180005859  mov     qword ptr [rbx+40h], 0
0x180005861  xor     ebx, ebx
0x180005863  mov     [r15], r14
0x180005866  test    rdi, rdi
0x180005869  jz      short loc_18000587C
0x18000586b  mov     rcx, rdi; hMutex
0x18000586e  call    cs:__imp_ReleaseMutex
0x180005874  test    eax, eax
0x180005876  jz      loc_180005947
0x18000587c  test    rbx, rbx
0x18000587f  jz      short loc_18000588E
0x180005881  mov     rcx, rbx; hObject
0x180005884  call    cs:__imp_CloseHandle
0x18000588a  test    eax, eax
0x18000588c  jz      short loc_1800058B6
0x18000588e  xor     eax, eax
0x180005890  mov     rcx, [rbp+180h+var_30]
0x180005897  xor     rcx, rsp; StackCookie
0x18000589a  call    __security_check_cookie
0x18000589f  mov     rbx, [rsp+280h+arg_10]
0x1800058a7  add     rsp, 260h
0x1800058ae  pop     r15
0x1800058b0  pop     r14
0x1800058b2  pop     rdi
0x1800058b3  pop     rsi
0x1800058b4  pop     rbp
0x1800058b5  retn
0x1800058b6  mov     rcx, [rbp+188h]; this
0x1800058bd  mov     edx, 0A0Bh; void *
0x1800058c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058c8  mov     rcx, [rbp+188h]; this
0x1800058cf  mov     edx, 0A0Bh; void *
0x1800058d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058da  mov     rcx, [rbp+188h]; this
0x1800058e1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800058e7  mov     rcx, [rbp+188h]; this
0x1800058ee  mov     edx, 0A15h; void *
0x1800058f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058f9  mov     rcx, [rbp+188h]; this
0x180005900  mov     edx, 0A0Bh; void *
0x180005905  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000590b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005911  mov     rcx, [rbp+188h]; this
0x180005918  mov     edx, 0A0Bh; void *
0x18000591d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005923  mov     rcx, [rbp+188h]; this
0x18000592a  mov     edx, 0A0Bh; void *
0x18000592f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005935  mov     rcx, [rbp+188h]; this
0x18000593c  mov     edx, 0A15h; void *
0x180005941  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005947  mov     rcx, [rbp+188h]; this
0x18000594e  mov     edx, 0A15h; void *
0x180005953  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
