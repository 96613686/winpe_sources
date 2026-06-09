# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003f78`
- end: `0x180004340`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004ef0`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x180003f78`
- `0x180004348`
- `0x180004634`
- `0x180004c88`
- `0x180005768`
- `0x1800059c4`
- `0x1800063b4`
- `0x18000648c`
- `0x18000686c`
- `0x18000687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ff0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ff0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004255`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000426b`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
                    (__int64)v9,
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
0x180003f78  mov     [rsp-8+arg_10], rbx
0x180003f7d  push    rbp
0x180003f7e  push    rsi
0x180003f7f  push    rdi
0x180003f80  push    r14
0x180003f82  push    r15
0x180003f84  lea     rbp, [rsp-160h]
0x180003f8c  sub     rsp, 260h
0x180003f93  mov     rax, cs:__security_cookie
0x180003f9a  xor     rax, rsp
0x180003f9d  mov     [rbp+180h+var_30], rax
0x180003fa4  mov     r15, rdx
0x180003fa7  mov     qword ptr [rdx], 0
0x180003fae  mov     rbx, rcx
0x180003fb1  call    cs:__imp_GetCurrentProcessId
0x180003fb7  mov     r14d, 78h ; 'x'
0x180003fbd  mov     [rsp+280h+var_258], rbx
0x180003fc2  mov     r9d, eax
0x180003fc5  mov     [rsp+280h+var_260], r14d; int
0x180003fca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003fd1  mov     edx, 104h; unsigned __int64
0x180003fd6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003fdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003fe0  mov     r9d, 1F0001h; dwDesiredAccess
0x180003fe6  lea     rdx, [rsp+280h+Name]; lpName
0x180003feb  xor     r8d, r8d; dwFlags
0x180003fee  xor     ecx, ecx; lpMutexAttributes
0x180003ff0  call    cs:__imp_CreateMutexExW
0x180003ff6  mov     rbx, rax
0x180003ff9  test    rax, rax
0x180003ffc  jnz     short loc_180004008
0x180003ffe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004003  jmp     loc_180004277
0x180004008  xor     r8d, r8d; bAlertable
0x18000400b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000400e  mov     rcx, rbx; hHandle
0x180004011  call    cs:__imp_WaitForSingleObjectEx
0x180004017  cmp     eax, 102h
0x18000401c  jz      short loc_18000402E
0x18000401e  test    eax, 0FFFFFF7Fh
0x180004023  jnz     loc_1800042AF
0x180004029  mov     rdi, rbx
0x18000402c  jmp     short loc_180004030
0x18000402e  xor     edi, edi
0x180004030  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004035  mov     [rsp+280h+hObject], 0
0x18000403e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004043  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004048  mov     esi, eax
0x18000404a  test    eax, eax
0x18000404c  jns     short loc_1800040CD
0x18000404e  mov     rcx, [rbp+188h]; this
0x180004055  lea     r8, aWil; "wil"
0x18000405c  mov     r9d, eax; char *
0x18000405f  mov     edx, 66h ; 'f'; void *
0x180004064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004069  mov     rcx, [rbp+188h]; this
0x180004070  lea     r8, aWil; "wil"
0x180004077  mov     r9d, esi; char *
0x18000407a  mov     edx, 6Fh ; 'o'; void *
0x18000407f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004084  mov     rcx, [rbp+188h]; this
0x18000408b  lea     r8, aWil; "wil"
0x180004092  mov     r9d, esi; char *
0x180004095  mov     edx, 12Eh; void *
0x18000409a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000409f  test    rdi, rdi
0x1800040a2  jz      short loc_1800040B5
0x1800040a4  mov     rcx, rdi; hMutex
0x1800040a7  call    cs:__imp_ReleaseMutex
0x1800040ad  test    eax, eax
0x1800040af  jz      loc_1800042BC
0x1800040b5  mov     rcx, rbx; hObject
0x1800040b8  call    cs:__imp_CloseHandle
0x1800040be  test    eax, eax
0x1800040c0  jz      loc_1800042CE
0x1800040c6  mov     eax, esi
0x1800040c8  jmp     loc_180004277
0x1800040cd  mov     rax, [rsp+280h+hObject]
0x1800040d2  lea     rcx, ds:0[rax*4]
0x1800040da  test    rcx, rcx
0x1800040dd  jz      short loc_1800040ED
0x1800040df  mov     [r15], rcx
0x1800040e2  mov     eax, [rcx]
0x1800040e4  inc     eax
0x1800040e6  mov     [rcx], eax
0x1800040e8  jmp     loc_18000424D
0x1800040ed  mov     rdx, r14; dwBytes
0x1800040f0  mov     qword ptr [r15], 0
0x1800040f7  mov     ecx, 8; dwFlags
0x1800040fc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004101  mov     rsi, rax
0x180004104  test    rax, rax
0x180004107  jnz     short loc_18000412F
0x180004109  mov     rcx, [rbp+188h]; this
0x180004110  lea     r8, aWil; "wil"
0x180004117  mov     r14d, 8007000Eh
0x18000411d  mov     edx, 14Bh; void *
0x180004122  mov     r9d, r14d; char *
0x180004125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000412a  jmp     loc_1800041C2
0x18000412f  xorps   xmm0, xmm0
0x180004132  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004138  test    sil, 3
0x18000413c  jnz     loc_1800042E0
0x180004142  mov     r9, rsi
0x180004145  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000414a  shr     r9, 2; unsigned __int64
0x18000414e  lea     rcx, [rsp+280h+hObject]; this
0x180004153  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004158  mov     r14d, eax
0x18000415b  test    eax, eax
0x18000415d  jns     loc_180004209
0x180004163  mov     rcx, [rbp+188h]; this
0x18000416a  lea     r8, aWil; "wil"
0x180004171  mov     r9d, eax; char *
0x180004174  mov     edx, 14Eh; void *
0x180004179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000417e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004183  test    rcx, rcx
0x180004186  jz      short loc_180004196
0x180004188  call    cs:__imp_CloseHandle
0x18000418e  test    eax, eax
0x180004190  jz      loc_1800042E6
0x180004196  mov     rcx, [rsp+280h+hObject]; hObject
0x18000419b  test    rcx, rcx
0x18000419e  jz      short loc_1800041AE
0x1800041a0  call    cs:__imp_CloseHandle
0x1800041a6  test    eax, eax
0x1800041a8  jz      loc_1800042F8
0x1800041ae  call    cs:__imp_GetProcessHeap
0x1800041b4  mov     r8, rsi; lpMem
0x1800041b7  xor     edx, edx; dwFlags
0x1800041b9  mov     rcx, rax; hHeap
0x1800041bc  call    cs:__imp_HeapFree
0x1800041c2  mov     rcx, [rbp+188h]; this
0x1800041c9  lea     r8, aWil; "wil"
0x1800041d0  mov     r9d, r14d; char *
0x1800041d3  mov     edx, 137h; void *
0x1800041d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041dd  test    rdi, rdi
0x1800041e0  jz      short loc_1800041F3
0x1800041e2  mov     rcx, rdi; hMutex
0x1800041e5  call    cs:__imp_ReleaseMutex
0x1800041eb  test    eax, eax
0x1800041ed  jz      loc_18000430A
0x1800041f3  mov     rcx, rbx; hObject
0x1800041f6  call    cs:__imp_CloseHandle
0x1800041fc  test    eax, eax
0x1800041fe  jz      loc_18000431C
0x180004204  mov     eax, r14d
0x180004207  jmp     short loc_180004277
0x180004209  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000420e  xor     edx, edx; Val
0x180004210  mov     dword ptr [rsi], 1
0x180004216  lea     rcx, [rsi+22h]; void *
0x18000421a  mov     [rsi+8], rbx
0x18000421e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004223  lea     r8d, [rdx+56h]; Size
0x180004227  call    memset_0
0x18000422c  xor     edx, edx; Val
0x18000422e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004234  lea     rcx, [rsi+28h]; void *
0x180004238  mov     dword ptr [rsi+24h], 1
0x18000423f  lea     r8d, [rdx+50h]; Size
0x180004243  call    memset_0
0x180004248  xor     ebx, ebx
0x18000424a  mov     [r15], rsi
0x18000424d  test    rdi, rdi
0x180004250  jz      short loc_180004263
0x180004252  mov     rcx, rdi; hMutex
0x180004255  call    cs:__imp_ReleaseMutex
0x18000425b  test    eax, eax
0x18000425d  jz      loc_18000432E
0x180004263  test    rbx, rbx
0x180004266  jz      short loc_180004275
0x180004268  mov     rcx, rbx; hObject
0x18000426b  call    cs:__imp_CloseHandle
0x180004271  test    eax, eax
0x180004273  jz      short loc_18000429D
0x180004275  xor     eax, eax
0x180004277  mov     rcx, [rbp+180h+var_30]
0x18000427e  xor     rcx, rsp; StackCookie
0x180004281  call    __security_check_cookie
0x180004286  mov     rbx, [rsp+280h+arg_10]
0x18000428e  add     rsp, 260h
0x180004295  pop     r15
0x180004297  pop     r14
0x180004299  pop     rdi
0x18000429a  pop     rsi
0x18000429b  pop     rbp
0x18000429c  retn
0x18000429d  mov     rcx, [rbp+188h]; this
0x1800042a4  mov     edx, 0A0Bh; void *
0x1800042a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042af  mov     rcx, [rbp+188h]; this
0x1800042b6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800042bc  mov     rcx, [rbp+188h]; this
0x1800042c3  mov     edx, 0A15h; void *
0x1800042c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042ce  mov     rcx, [rbp+188h]; this
0x1800042d5  mov     edx, 0A0Bh; void *
0x1800042da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800042e6  mov     rcx, [rbp+188h]; this
0x1800042ed  mov     edx, 0A0Bh; void *
0x1800042f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042f8  mov     rcx, [rbp+188h]; this
0x1800042ff  mov     edx, 0A0Bh; void *
0x180004304  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000430a  mov     rcx, [rbp+188h]; this
0x180004311  mov     edx, 0A15h; void *
0x180004316  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000431c  mov     rcx, [rbp+188h]; this
0x180004323  mov     edx, 0A0Bh; void *
0x180004328  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000432e  mov     rcx, [rbp+188h]; this
0x180004335  mov     edx, 0A15h; void *
0x18000433a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
