# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800093dc`
- end: `0x1800097cd`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009aa8`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006134`
- `0x180008414`
- `0x1800093dc`
- `0x1800097d4`
- `0x180009cfc`
- `0x18000a768`
- `0x18000ae30`
- `0x18000cb10`
- `0x18000d324`
- `0x18001140c`
- `0x18001141c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000960f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000961d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000961d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009415`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009415`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000950a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009646`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800096e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000950a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009646`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800096e2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009453`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009453`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800096af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800096af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009474`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000951b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000951b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800095e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800096f8`

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
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
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
0x1800093dc  mov     [rsp-8+arg_10], rbx
0x1800093e1  push    rbp
0x1800093e2  push    rsi
0x1800093e3  push    rdi
0x1800093e4  push    r14
0x1800093e6  push    r15
0x1800093e8  lea     rbp, [rsp-160h]
0x1800093f0  sub     rsp, 260h
0x1800093f7  mov     rax, cs:__security_cookie
0x1800093fe  xor     rax, rsp
0x180009401  mov     [rbp+180h+var_30], rax
0x180009408  mov     r15, rdx
0x18000940b  mov     qword ptr [rdx], 0
0x180009412  mov     rbx, rcx
0x180009415  call    cs:__imp_GetCurrentProcessId
0x18000941b  mov     r14d, 130h
0x180009421  mov     [rsp+280h+var_258], rbx
0x180009426  mov     r9d, eax
0x180009429  mov     [rsp+280h+var_260], r14d; int
0x18000942e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009435  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000943a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000943e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009443  mov     r9d, 1F0001h; dwDesiredAccess
0x180009449  lea     rdx, [rsp+280h+Name]; lpName
0x18000944e  xor     r8d, r8d; dwFlags
0x180009451  xor     ecx, ecx; lpMutexAttributes
0x180009453  call    cs:__imp_CreateMutexExW
0x180009459  mov     rbx, rax
0x18000945c  test    rax, rax
0x18000945f  jnz     short loc_18000946B
0x180009461  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009466  jmp     loc_180009704
0x18000946b  xor     r8d, r8d; bAlertable
0x18000946e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009471  mov     rcx, rbx; hHandle
0x180009474  call    cs:__imp_WaitForSingleObjectEx
0x18000947a  cmp     eax, 102h
0x18000947f  jz      short loc_180009491
0x180009481  test    eax, 0FFFFFF7Fh
0x180009486  jnz     loc_18000974E
0x18000948c  mov     rdi, rbx
0x18000948f  jmp     short loc_180009493
0x180009491  xor     edi, edi
0x180009493  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009498  mov     [rsp+280h+hObject], 0
0x1800094a1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800094a6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800094ab  mov     esi, eax
0x1800094ad  test    eax, eax
0x1800094af  jns     short loc_180009530
0x1800094b1  mov     rcx, [rbp+188h]; this
0x1800094b8  lea     r8, aWil; "wil"
0x1800094bf  mov     r9d, eax; char *
0x1800094c2  mov     edx, 66h ; 'f'; void *
0x1800094c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094cc  mov     rcx, [rbp+188h]; this
0x1800094d3  lea     r8, aWil; "wil"
0x1800094da  mov     r9d, esi; char *
0x1800094dd  mov     edx, 6Fh ; 'o'; void *
0x1800094e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094e7  mov     rcx, [rbp+188h]; this
0x1800094ee  lea     r8, aWil; "wil"
0x1800094f5  mov     r9d, esi; char *
0x1800094f8  mov     edx, 12Eh; void *
0x1800094fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009502  test    rdi, rdi
0x180009505  jz      short loc_180009518
0x180009507  mov     rcx, rdi; hMutex
0x18000950a  call    cs:__imp_ReleaseMutex
0x180009510  test    eax, eax
0x180009512  jz      loc_18000975B
0x180009518  mov     rcx, rbx; hObject
0x18000951b  call    cs:__imp_CloseHandle
0x180009521  test    eax, eax
0x180009523  jz      loc_18000976D
0x180009529  mov     eax, esi
0x18000952b  jmp     loc_180009704
0x180009530  mov     rax, [rsp+280h+hObject]
0x180009535  lea     rcx, ds:0[rax*4]
0x18000953d  test    rcx, rcx
0x180009540  jz      short loc_180009550
0x180009542  mov     [r15], rcx
0x180009545  mov     eax, [rcx]
0x180009547  inc     eax
0x180009549  mov     [rcx], eax
0x18000954b  jmp     loc_1800096DA
0x180009550  mov     rdx, r14; dwBytes
0x180009553  mov     qword ptr [r15], 0
0x18000955a  mov     ecx, 8; dwFlags
0x18000955f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009564  mov     r14, rax
0x180009567  test    rax, rax
0x18000956a  jnz     short loc_180009591
0x18000956c  mov     rcx, [rbp+188h]; this
0x180009573  lea     r8, aWil; "wil"
0x18000957a  mov     esi, 8007000Eh
0x18000957f  mov     edx, 14Bh; void *
0x180009584  mov     r9d, esi; char *
0x180009587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000958c  jmp     loc_180009623
0x180009591  xorps   xmm0, xmm0
0x180009594  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000959a  test    r14b, 3
0x18000959e  jnz     loc_18000977F
0x1800095a4  mov     r9, r14
0x1800095a7  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800095ac  shr     r9, 2; unsigned __int64
0x1800095b0  lea     rcx, [rsp+280h+hObject]; this
0x1800095b5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800095ba  mov     esi, eax
0x1800095bc  test    eax, eax
0x1800095be  jns     loc_18000966A
0x1800095c4  mov     rcx, [rbp+188h]; this
0x1800095cb  lea     r8, aWil; "wil"
0x1800095d2  mov     r9d, eax; char *
0x1800095d5  mov     edx, 14Eh; void *
0x1800095da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095df  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800095e4  test    rcx, rcx
0x1800095e7  jz      short loc_1800095F7
0x1800095e9  call    cs:__imp_CloseHandle
0x1800095ef  test    eax, eax
0x1800095f1  jz      loc_180009785
0x1800095f7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800095fc  test    rcx, rcx
0x1800095ff  jz      short loc_18000960F
0x180009601  call    cs:__imp_CloseHandle
0x180009607  test    eax, eax
0x180009609  jz      loc_180009797
0x18000960f  call    cs:__imp_GetProcessHeap
0x180009615  mov     r8, r14; lpMem
0x180009618  xor     edx, edx; dwFlags
0x18000961a  mov     rcx, rax; hHeap
0x18000961d  call    cs:__imp_HeapFree
0x180009623  mov     rcx, [rbp+188h]; this
0x18000962a  lea     r8, aWil; "wil"
0x180009631  mov     r9d, esi; char *
0x180009634  mov     edx, 137h; void *
0x180009639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000963e  test    rdi, rdi
0x180009641  jz      short loc_180009654
0x180009643  mov     rcx, rdi; hMutex
0x180009646  call    cs:__imp_ReleaseMutex
0x18000964c  test    eax, eax
0x18000964e  jz      loc_1800097A9
0x180009654  mov     rcx, rbx; hObject
0x180009657  call    cs:__imp_CloseHandle
0x18000965d  test    eax, eax
0x18000965f  jz      loc_18000973C
0x180009665  jmp     loc_180009529
0x18000966a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000966f  lea     rcx, [r14+28h]; void *
0x180009673  mov     dword ptr [r14], 1
0x18000967a  xor     edx, edx; Val
0x18000967c  mov     [r14+8], rbx
0x180009680  mov     r8d, 108h; Size
0x180009686  movdqu  xmmword ptr [r14+10h], xmm0
0x18000968c  call    memset_0
0x180009691  xor     eax, eax
0x180009693  lea     rcx, [r14+28h]; this
0x180009697  mov     [r14+20h], rax
0x18000969b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800096a0  lea     rbx, [r14+0E8h]
0x1800096a7  xor     r8d, r8d; Flags
0x1800096aa  mov     rcx, rbx; lpCriticalSection
0x1800096ad  xor     edx, edx; dwSpinCount
0x1800096af  call    cs:__imp_InitializeCriticalSectionEx
0x1800096b5  mov     qword ptr [rbx+28h], 0
0x1800096bd  mov     qword ptr [rbx+30h], 0
0x1800096c5  mov     qword ptr [rbx+38h], 0
0x1800096cd  mov     qword ptr [rbx+40h], 0
0x1800096d5  xor     ebx, ebx
0x1800096d7  mov     [r15], r14
0x1800096da  test    rdi, rdi
0x1800096dd  jz      short loc_1800096F0
0x1800096df  mov     rcx, rdi; hMutex
0x1800096e2  call    cs:__imp_ReleaseMutex
0x1800096e8  test    eax, eax
0x1800096ea  jz      loc_1800097BB
0x1800096f0  test    rbx, rbx
0x1800096f3  jz      short loc_180009702
0x1800096f5  mov     rcx, rbx; hObject
0x1800096f8  call    cs:__imp_CloseHandle
0x1800096fe  test    eax, eax
0x180009700  jz      short loc_18000972A
0x180009702  xor     eax, eax
0x180009704  mov     rcx, [rbp+180h+var_30]
0x18000970b  xor     rcx, rsp; StackCookie
0x18000970e  call    __security_check_cookie
0x180009713  mov     rbx, [rsp+280h+arg_10]
0x18000971b  add     rsp, 260h
0x180009722  pop     r15
0x180009724  pop     r14
0x180009726  pop     rdi
0x180009727  pop     rsi
0x180009728  pop     rbp
0x180009729  retn
0x18000972a  mov     rcx, [rbp+188h]; this
0x180009731  mov     edx, 0A0Bh; void *
0x180009736  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000973c  mov     rcx, [rbp+188h]; this
0x180009743  mov     edx, 0A0Bh; void *
0x180009748  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000974e  mov     rcx, [rbp+188h]; this
0x180009755  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000975b  mov     rcx, [rbp+188h]; this
0x180009762  mov     edx, 0A15h; void *
0x180009767  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000976d  mov     rcx, [rbp+188h]; this
0x180009774  mov     edx, 0A0Bh; void *
0x180009779  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000977f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009785  mov     rcx, [rbp+188h]; this
0x18000978c  mov     edx, 0A0Bh; void *
0x180009791  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009797  mov     rcx, [rbp+188h]; this
0x18000979e  mov     edx, 0A0Bh; void *
0x1800097a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800097a9  mov     rcx, [rbp+188h]; this
0x1800097b0  mov     edx, 0A15h; void *
0x1800097b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800097bb  mov     rcx, [rbp+188h]; this
0x1800097c2  mov     edx, 0A15h; void *
0x1800097c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
