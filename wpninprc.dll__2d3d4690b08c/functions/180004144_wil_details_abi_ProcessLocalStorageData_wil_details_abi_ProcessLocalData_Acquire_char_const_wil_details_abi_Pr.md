# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004144`
- end: `0x1800044e2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004b1c`

## callees

- `0x180001510`
- `0x18000209e`
- `0x180003370`
- `0x180004144`
- `0x1800044e8`
- `0x1800046fc`
- `0x180004998`
- `0x18000502c`
- `0x1800052cc`
- `0x1800055c0`
- `0x180005910`
- `0x180005920`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004365`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000417d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000417d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004331`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000440d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004331`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000440d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800041bc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800041bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000425e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004387`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000425e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004387`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800043f7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800041dd`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x180004144  mov     [rsp-8+arg_10], rbx
0x180004149  push    rbp
0x18000414a  push    rsi
0x18000414b  push    rdi
0x18000414c  push    r14
0x18000414e  push    r15
0x180004150  lea     rbp, [rsp-160h]
0x180004158  sub     rsp, 260h
0x18000415f  mov     rax, cs:__security_cookie
0x180004166  xor     rax, rsp
0x180004169  mov     [rbp+180h+var_30], rax
0x180004170  mov     r15, rdx
0x180004173  mov     qword ptr [rdx], 0
0x18000417a  mov     rbx, rcx
0x18000417d  call    cs:__imp_GetCurrentProcessId
0x180004183  mov     r14d, 78h ; 'x'
0x180004189  mov     [rsp+280h+var_258], rbx
0x18000418e  mov     r9d, eax
0x180004191  mov     [rsp+280h+var_260], r14d; int
0x180004196  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000419d  mov     edx, 104h; unsigned __int64
0x1800041a2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800041a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800041ac  mov     r9d, 1F0001h; dwDesiredAccess
0x1800041b2  lea     rdx, [rsp+280h+Name]; lpName
0x1800041b7  xor     r8d, r8d; dwFlags
0x1800041ba  xor     ecx, ecx; lpMutexAttributes
0x1800041bc  call    cs:__imp_CreateMutexExW
0x1800041c2  mov     rbx, rax
0x1800041c5  test    rax, rax
0x1800041c8  jnz     short loc_1800041D4
0x1800041ca  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800041cf  jmp     loc_180004419
0x1800041d4  xor     r8d, r8d; bAlertable
0x1800041d7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800041da  mov     rcx, rbx; hHandle
0x1800041dd  call    cs:__imp_WaitForSingleObjectEx
0x1800041e3  cmp     eax, 102h
0x1800041e8  jz      short loc_1800041FA
0x1800041ea  test    eax, 0FFFFFF7Fh
0x1800041ef  jnz     loc_180004451
0x1800041f5  mov     rdi, rbx
0x1800041f8  jmp     short loc_1800041FC
0x1800041fa  xor     edi, edi
0x1800041fc  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004201  mov     [rsp+280h+hObject], 0
0x18000420a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000420f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004214  mov     esi, eax
0x180004216  test    eax, eax
0x180004218  jns     short loc_180004284
0x18000421a  mov     rcx, [rbp+188h]; this
0x180004221  mov     r9d, eax; char *
0x180004224  mov     edx, 66h ; 'f'; void *
0x180004229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000422e  mov     rcx, [rbp+188h]; this
0x180004235  mov     r9d, esi; char *
0x180004238  mov     edx, 6Fh ; 'o'; void *
0x18000423d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004242  mov     rcx, [rbp+188h]; this
0x180004249  mov     r9d, esi; char *
0x18000424c  mov     edx, 12Eh; void *
0x180004251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004256  test    rdi, rdi
0x180004259  jz      short loc_18000426C
0x18000425b  mov     rcx, rdi; hMutex
0x18000425e  call    cs:__imp_ReleaseMutex
0x180004264  test    eax, eax
0x180004266  jz      loc_18000445E
0x18000426c  mov     rcx, rbx; hObject
0x18000426f  call    cs:__imp_CloseHandle
0x180004275  test    eax, eax
0x180004277  jz      loc_180004470
0x18000427d  mov     eax, esi
0x18000427f  jmp     loc_180004419
0x180004284  mov     rax, [rsp+280h+hObject]
0x180004289  lea     rcx, ds:0[rax*4]
0x180004291  test    rcx, rcx
0x180004294  jz      short loc_1800042A4
0x180004296  mov     [r15], rcx
0x180004299  mov     eax, [rcx]
0x18000429b  inc     eax
0x18000429d  mov     [rcx], eax
0x18000429f  jmp     loc_1800043EF
0x1800042a4  mov     rdx, r14; dwBytes
0x1800042a7  mov     qword ptr [r15], 0
0x1800042ae  mov     ecx, 8; dwFlags
0x1800042b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800042b8  mov     rsi, rax
0x1800042bb  test    rax, rax
0x1800042be  jnz     short loc_1800042DF
0x1800042c0  mov     rcx, [rbp+188h]; this
0x1800042c7  mov     r14d, 8007000Eh
0x1800042cd  mov     r9d, r14d; char *
0x1800042d0  mov     edx, 14Bh; void *
0x1800042d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042da  jmp     loc_18000436B
0x1800042df  xorps   xmm0, xmm0
0x1800042e2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800042e8  test    sil, 3
0x1800042ec  jnz     loc_180004482
0x1800042f2  mov     r9, rsi
0x1800042f5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800042fa  shr     r9, 2; unsigned __int64
0x1800042fe  lea     rcx, [rsp+280h+hObject]; this
0x180004303  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004308  mov     r14d, eax
0x18000430b  test    eax, eax
0x18000430d  jns     loc_1800043AB
0x180004313  mov     rcx, [rbp+188h]; this
0x18000431a  mov     r9d, eax; char *
0x18000431d  mov     edx, 14Eh; void *
0x180004322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004327  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000432c  test    rcx, rcx
0x18000432f  jz      short loc_18000433F
0x180004331  call    cs:__imp_CloseHandle
0x180004337  test    eax, eax
0x180004339  jz      loc_180004488
0x18000433f  mov     rcx, [rsp+280h+hObject]; hObject
0x180004344  test    rcx, rcx
0x180004347  jz      short loc_180004357
0x180004349  call    cs:__imp_CloseHandle
0x18000434f  test    eax, eax
0x180004351  jz      loc_18000449A
0x180004357  call    cs:__imp_GetProcessHeap
0x18000435d  mov     r8, rsi; lpMem
0x180004360  xor     edx, edx; dwFlags
0x180004362  mov     rcx, rax; hHeap
0x180004365  call    cs:__imp_HeapFree
0x18000436b  mov     rcx, [rbp+188h]; this
0x180004372  mov     r9d, r14d; char *
0x180004375  mov     edx, 137h; void *
0x18000437a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000437f  test    rdi, rdi
0x180004382  jz      short loc_180004395
0x180004384  mov     rcx, rdi; hMutex
0x180004387  call    cs:__imp_ReleaseMutex
0x18000438d  test    eax, eax
0x18000438f  jz      loc_1800044AC
0x180004395  mov     rcx, rbx; hObject
0x180004398  call    cs:__imp_CloseHandle
0x18000439e  test    eax, eax
0x1800043a0  jz      loc_1800044BE
0x1800043a6  mov     eax, r14d
0x1800043a9  jmp     short loc_180004419
0x1800043ab  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800043b0  xor     edx, edx; Val
0x1800043b2  mov     dword ptr [rsi], 1
0x1800043b8  lea     rcx, [rsi+22h]; void *
0x1800043bc  mov     [rsi+8], rbx
0x1800043c0  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800043c5  lea     r8d, [rdx+56h]; Size
0x1800043c9  call    memset_0
0x1800043ce  xor     edx, edx; Val
0x1800043d0  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800043d6  lea     rcx, [rsi+28h]; void *
0x1800043da  mov     dword ptr [rsi+24h], 1
0x1800043e1  lea     r8d, [rdx+50h]; Size
0x1800043e5  call    memset_0
0x1800043ea  xor     ebx, ebx
0x1800043ec  mov     [r15], rsi
0x1800043ef  test    rdi, rdi
0x1800043f2  jz      short loc_180004405
0x1800043f4  mov     rcx, rdi; hMutex
0x1800043f7  call    cs:__imp_ReleaseMutex
0x1800043fd  test    eax, eax
0x1800043ff  jz      loc_1800044D0
0x180004405  test    rbx, rbx
0x180004408  jz      short loc_180004417
0x18000440a  mov     rcx, rbx; hObject
0x18000440d  call    cs:__imp_CloseHandle
0x180004413  test    eax, eax
0x180004415  jz      short loc_18000443F
0x180004417  xor     eax, eax
0x180004419  mov     rcx, [rbp+180h+var_30]
0x180004420  xor     rcx, rsp; StackCookie
0x180004423  call    __security_check_cookie
0x180004428  mov     rbx, [rsp+280h+arg_10]
0x180004430  add     rsp, 260h
0x180004437  pop     r15
0x180004439  pop     r14
0x18000443b  pop     rdi
0x18000443c  pop     rsi
0x18000443d  pop     rbp
0x18000443e  retn
0x18000443f  mov     rcx, [rbp+188h]; this
0x180004446  mov     edx, 0A0Bh; void *
0x18000444b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004451  mov     rcx, [rbp+188h]; this
0x180004458  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000445e  mov     rcx, [rbp+188h]; this
0x180004465  mov     edx, 0A15h; void *
0x18000446a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004470  mov     rcx, [rbp+188h]; this
0x180004477  mov     edx, 0A0Bh; void *
0x18000447c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004482  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004488  mov     rcx, [rbp+188h]; this
0x18000448f  mov     edx, 0A0Bh; void *
0x180004494  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000449a  mov     rcx, [rbp+188h]; this
0x1800044a1  mov     edx, 0A0Bh; void *
0x1800044a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044ac  mov     rcx, [rbp+188h]; this
0x1800044b3  mov     edx, 0A15h; void *
0x1800044b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044be  mov     rcx, [rbp+188h]; this
0x1800044c5  mov     edx, 0A0Bh; void *
0x1800044ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800044d0  mov     rcx, [rbp+188h]; this
0x1800044d7  mov     edx, 0A15h; void *
0x1800044dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
