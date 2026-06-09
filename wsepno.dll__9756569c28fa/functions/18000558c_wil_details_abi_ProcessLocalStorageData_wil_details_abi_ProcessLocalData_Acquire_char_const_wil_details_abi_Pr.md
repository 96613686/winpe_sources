# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000558c`
- end: `0x180005954`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007554`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x180003714`
- `0x18000558c`
- `0x180005e08`
- `0x180006d24`
- `0x180007418`
- `0x1800083d0`
- `0x18000a374`
- `0x18000ab28`
- `0x18000b494`
- `0x18000b4a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800055c5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005604`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005604`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005625`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005625`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005869`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800056bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800057f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005869`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000579c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000587f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800056cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000579c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800057b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000580a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000587f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x18000558c  mov     [rsp-8+arg_10], rbx
0x180005591  push    rbp
0x180005592  push    rsi
0x180005593  push    rdi
0x180005594  push    r14
0x180005596  push    r15
0x180005598  lea     rbp, [rsp-160h]
0x1800055a0  sub     rsp, 260h
0x1800055a7  mov     rax, cs:__security_cookie
0x1800055ae  xor     rax, rsp
0x1800055b1  mov     [rbp+180h+var_30], rax
0x1800055b8  mov     r15, rdx
0x1800055bb  mov     qword ptr [rdx], 0
0x1800055c2  mov     rbx, rcx
0x1800055c5  call    cs:__imp_GetCurrentProcessId
0x1800055cb  mov     r14d, 78h ; 'x'
0x1800055d1  mov     [rsp+280h+var_258], rbx
0x1800055d6  mov     r9d, eax
0x1800055d9  mov     [rsp+280h+var_260], r14d; int
0x1800055de  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800055e5  mov     edx, 104h; unsigned __int64
0x1800055ea  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800055ef  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800055f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800055fa  lea     rdx, [rsp+280h+Name]; lpName
0x1800055ff  xor     r8d, r8d; dwFlags
0x180005602  xor     ecx, ecx; lpMutexAttributes
0x180005604  call    cs:__imp_CreateMutexExW
0x18000560a  mov     rbx, rax
0x18000560d  test    rax, rax
0x180005610  jnz     short loc_18000561C
0x180005612  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005617  jmp     loc_18000588B
0x18000561c  xor     r8d, r8d; bAlertable
0x18000561f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005622  mov     rcx, rbx; hHandle
0x180005625  call    cs:__imp_WaitForSingleObjectEx
0x18000562b  cmp     eax, 102h
0x180005630  jz      short loc_180005642
0x180005632  test    eax, 0FFFFFF7Fh
0x180005637  jnz     loc_1800058C3
0x18000563d  mov     rdi, rbx
0x180005640  jmp     short loc_180005644
0x180005642  xor     edi, edi
0x180005644  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005649  mov     [rsp+280h+hObject], 0
0x180005652  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005657  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000565c  mov     esi, eax
0x18000565e  test    eax, eax
0x180005660  jns     short loc_1800056E1
0x180005662  mov     rcx, [rbp+188h]; this
0x180005669  lea     r8, aWil; "wil"
0x180005670  mov     r9d, eax; char *
0x180005673  mov     edx, 66h ; 'f'; void *
0x180005678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000567d  mov     rcx, [rbp+188h]; this
0x180005684  lea     r8, aWil; "wil"
0x18000568b  mov     r9d, esi; char *
0x18000568e  mov     edx, 6Fh ; 'o'; void *
0x180005693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005698  mov     rcx, [rbp+188h]; this
0x18000569f  lea     r8, aWil; "wil"
0x1800056a6  mov     r9d, esi; char *
0x1800056a9  mov     edx, 12Eh; void *
0x1800056ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800056b3  test    rdi, rdi
0x1800056b6  jz      short loc_1800056C9
0x1800056b8  mov     rcx, rdi; hMutex
0x1800056bb  call    cs:__imp_ReleaseMutex
0x1800056c1  test    eax, eax
0x1800056c3  jz      loc_1800058D0
0x1800056c9  mov     rcx, rbx; hObject
0x1800056cc  call    cs:__imp_CloseHandle
0x1800056d2  test    eax, eax
0x1800056d4  jz      loc_1800058E2
0x1800056da  mov     eax, esi
0x1800056dc  jmp     loc_18000588B
0x1800056e1  mov     rax, [rsp+280h+hObject]
0x1800056e6  lea     rcx, ds:0[rax*4]
0x1800056ee  test    rcx, rcx
0x1800056f1  jz      short loc_180005701
0x1800056f3  mov     [r15], rcx
0x1800056f6  mov     eax, [rcx]
0x1800056f8  inc     eax
0x1800056fa  mov     [rcx], eax
0x1800056fc  jmp     loc_180005861
0x180005701  mov     rdx, r14; dwBytes
0x180005704  mov     qword ptr [r15], 0
0x18000570b  mov     ecx, 8; dwFlags
0x180005710  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005715  mov     rsi, rax
0x180005718  test    rax, rax
0x18000571b  jnz     short loc_180005743
0x18000571d  mov     rcx, [rbp+188h]; this
0x180005724  lea     r8, aWil; "wil"
0x18000572b  mov     r14d, 8007000Eh
0x180005731  mov     edx, 14Bh; void *
0x180005736  mov     r9d, r14d; char *
0x180005739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000573e  jmp     loc_1800057D6
0x180005743  xorps   xmm0, xmm0
0x180005746  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000574c  test    sil, 3
0x180005750  jnz     loc_1800058F4
0x180005756  mov     r9, rsi
0x180005759  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000575e  shr     r9, 2; unsigned __int64
0x180005762  lea     rcx, [rsp+280h+hObject]; this
0x180005767  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000576c  mov     r14d, eax
0x18000576f  test    eax, eax
0x180005771  jns     loc_18000581D
0x180005777  mov     rcx, [rbp+188h]; this
0x18000577e  lea     r8, aWil; "wil"
0x180005785  mov     r9d, eax; char *
0x180005788  mov     edx, 14Eh; void *
0x18000578d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005792  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005797  test    rcx, rcx
0x18000579a  jz      short loc_1800057AA
0x18000579c  call    cs:__imp_CloseHandle
0x1800057a2  test    eax, eax
0x1800057a4  jz      loc_1800058FA
0x1800057aa  mov     rcx, [rsp+280h+hObject]; hObject
0x1800057af  test    rcx, rcx
0x1800057b2  jz      short loc_1800057C2
0x1800057b4  call    cs:__imp_CloseHandle
0x1800057ba  test    eax, eax
0x1800057bc  jz      loc_18000590C
0x1800057c2  call    cs:__imp_GetProcessHeap
0x1800057c8  mov     r8, rsi; lpMem
0x1800057cb  xor     edx, edx; dwFlags
0x1800057cd  mov     rcx, rax; hHeap
0x1800057d0  call    cs:__imp_HeapFree
0x1800057d6  mov     rcx, [rbp+188h]; this
0x1800057dd  lea     r8, aWil; "wil"
0x1800057e4  mov     r9d, r14d; char *
0x1800057e7  mov     edx, 137h; void *
0x1800057ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800057f1  test    rdi, rdi
0x1800057f4  jz      short loc_180005807
0x1800057f6  mov     rcx, rdi; hMutex
0x1800057f9  call    cs:__imp_ReleaseMutex
0x1800057ff  test    eax, eax
0x180005801  jz      loc_18000591E
0x180005807  mov     rcx, rbx; hObject
0x18000580a  call    cs:__imp_CloseHandle
0x180005810  test    eax, eax
0x180005812  jz      loc_180005930
0x180005818  mov     eax, r14d
0x18000581b  jmp     short loc_18000588B
0x18000581d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005822  xor     edx, edx; Val
0x180005824  mov     dword ptr [rsi], 1
0x18000582a  lea     rcx, [rsi+22h]; void *
0x18000582e  mov     [rsi+8], rbx
0x180005832  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005837  lea     r8d, [rdx+56h]; Size
0x18000583b  call    memset_0
0x180005840  xor     edx, edx; Val
0x180005842  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005848  lea     rcx, [rsi+28h]; void *
0x18000584c  mov     dword ptr [rsi+24h], 1
0x180005853  lea     r8d, [rdx+50h]; Size
0x180005857  call    memset_0
0x18000585c  xor     ebx, ebx
0x18000585e  mov     [r15], rsi
0x180005861  test    rdi, rdi
0x180005864  jz      short loc_180005877
0x180005866  mov     rcx, rdi; hMutex
0x180005869  call    cs:__imp_ReleaseMutex
0x18000586f  test    eax, eax
0x180005871  jz      loc_180005942
0x180005877  test    rbx, rbx
0x18000587a  jz      short loc_180005889
0x18000587c  mov     rcx, rbx; hObject
0x18000587f  call    cs:__imp_CloseHandle
0x180005885  test    eax, eax
0x180005887  jz      short loc_1800058B1
0x180005889  xor     eax, eax
0x18000588b  mov     rcx, [rbp+180h+var_30]
0x180005892  xor     rcx, rsp; StackCookie
0x180005895  call    __security_check_cookie
0x18000589a  mov     rbx, [rsp+280h+arg_10]
0x1800058a2  add     rsp, 260h
0x1800058a9  pop     r15
0x1800058ab  pop     r14
0x1800058ad  pop     rdi
0x1800058ae  pop     rsi
0x1800058af  pop     rbp
0x1800058b0  retn
0x1800058b1  mov     rcx, [rbp+188h]; this
0x1800058b8  mov     edx, 0A0Bh; void *
0x1800058bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058c3  mov     rcx, [rbp+188h]; this
0x1800058ca  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800058d0  mov     rcx, [rbp+188h]; this
0x1800058d7  mov     edx, 0A15h; void *
0x1800058dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058e2  mov     rcx, [rbp+188h]; this
0x1800058e9  mov     edx, 0A0Bh; void *
0x1800058ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800058f4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800058fa  mov     rcx, [rbp+188h]; this
0x180005901  mov     edx, 0A0Bh; void *
0x180005906  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000590c  mov     rcx, [rbp+188h]; this
0x180005913  mov     edx, 0A0Bh; void *
0x180005918  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000591e  mov     rcx, [rbp+188h]; this
0x180005925  mov     edx, 0A15h; void *
0x18000592a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005930  mov     rcx, [rbp+188h]; this
0x180005937  mov     edx, 0A0Bh; void *
0x18000593c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005942  mov     rcx, [rbp+188h]; this
0x180005949  mov     edx, 0A15h; void *
0x18000594e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
