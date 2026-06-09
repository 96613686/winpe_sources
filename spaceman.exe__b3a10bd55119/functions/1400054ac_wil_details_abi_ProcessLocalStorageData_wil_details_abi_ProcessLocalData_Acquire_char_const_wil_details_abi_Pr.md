# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400054ac`
- end: `0x14000584a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140006dbc`

## callees

- `0x1400054ac`
- `0x140005dd0`
- `0x140006234`
- `0x140006b58`
- `0x140007748`
- `0x1400089e0`
- `0x1400090b0`
- `0x140009838`
- `0x14000a00c`
- `0x14000a01c`
- `0x14000d1be`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005524`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140005524`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400055c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400056ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000575f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400055c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400056ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000575f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005545`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140005545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400054e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400054e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400056cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400056cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400056bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400056bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400055d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400055d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400056b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005775`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x1400054ac  mov     [rsp-8+arg_10], rbx
0x1400054b1  push    rbp
0x1400054b2  push    rsi
0x1400054b3  push    rdi
0x1400054b4  push    r14
0x1400054b6  push    r15
0x1400054b8  lea     rbp, [rsp-160h]
0x1400054c0  sub     rsp, 260h
0x1400054c7  mov     rax, cs:__security_cookie
0x1400054ce  xor     rax, rsp
0x1400054d1  mov     [rbp+180h+var_30], rax
0x1400054d8  mov     r15, rdx
0x1400054db  mov     qword ptr [rdx], 0
0x1400054e2  mov     rbx, rcx
0x1400054e5  call    cs:__imp_GetCurrentProcessId
0x1400054eb  mov     r14d, 78h ; 'x'
0x1400054f1  mov     [rsp+280h+var_258], rbx
0x1400054f6  mov     r9d, eax
0x1400054f9  mov     [rsp+280h+var_260], r14d; int
0x1400054fe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140005505  mov     edx, 104h; unsigned __int64
0x14000550a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000550f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005514  mov     r9d, 1F0001h; dwDesiredAccess
0x14000551a  lea     rdx, [rsp+280h+Name]; lpName
0x14000551f  xor     r8d, r8d; dwFlags
0x140005522  xor     ecx, ecx; lpMutexAttributes
0x140005524  call    cs:__imp_CreateMutexExW
0x14000552a  mov     rbx, rax
0x14000552d  test    rax, rax
0x140005530  jnz     short loc_14000553C
0x140005532  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140005537  jmp     loc_140005781
0x14000553c  xor     r8d, r8d; bAlertable
0x14000553f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005542  mov     rcx, rbx; hHandle
0x140005545  call    cs:__imp_WaitForSingleObjectEx
0x14000554b  cmp     eax, 102h
0x140005550  jz      short loc_140005562
0x140005552  test    eax, 0FFFFFF7Fh
0x140005557  jnz     loc_1400057B9
0x14000555d  mov     rdi, rbx
0x140005560  jmp     short loc_140005564
0x140005562  xor     edi, edi
0x140005564  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140005569  mov     [rsp+280h+hObject], 0
0x140005572  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005577  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000557c  mov     esi, eax
0x14000557e  test    eax, eax
0x140005580  jns     short loc_1400055EC
0x140005582  mov     rcx, [rbp+188h]; this
0x140005589  mov     r9d, eax; char *
0x14000558c  mov     edx, 66h ; 'f'; void *
0x140005591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005596  mov     rcx, [rbp+188h]; this
0x14000559d  mov     r9d, esi; char *
0x1400055a0  mov     edx, 6Fh ; 'o'; void *
0x1400055a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400055aa  mov     rcx, [rbp+188h]; this
0x1400055b1  mov     r9d, esi; char *
0x1400055b4  mov     edx, 12Eh; void *
0x1400055b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400055be  test    rdi, rdi
0x1400055c1  jz      short loc_1400055D4
0x1400055c3  mov     rcx, rdi; hMutex
0x1400055c6  call    cs:__imp_ReleaseMutex
0x1400055cc  test    eax, eax
0x1400055ce  jz      loc_1400057C6
0x1400055d4  mov     rcx, rbx; hObject
0x1400055d7  call    cs:__imp_CloseHandle
0x1400055dd  test    eax, eax
0x1400055df  jz      loc_1400057D8
0x1400055e5  mov     eax, esi
0x1400055e7  jmp     loc_140005781
0x1400055ec  mov     rax, [rsp+280h+hObject]
0x1400055f1  lea     rcx, ds:0[rax*4]
0x1400055f9  test    rcx, rcx
0x1400055fc  jz      short loc_14000560C
0x1400055fe  mov     [r15], rcx
0x140005601  mov     eax, [rcx]
0x140005603  inc     eax
0x140005605  mov     [rcx], eax
0x140005607  jmp     loc_140005757
0x14000560c  mov     rdx, r14; dwBytes
0x14000560f  mov     qword ptr [r15], 0
0x140005616  mov     ecx, 8; dwFlags
0x14000561b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005620  mov     rsi, rax
0x140005623  test    rax, rax
0x140005626  jnz     short loc_140005647
0x140005628  mov     rcx, [rbp+188h]; this
0x14000562f  mov     r14d, 8007000Eh
0x140005635  mov     r9d, r14d; char *
0x140005638  mov     edx, 14Bh; void *
0x14000563d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005642  jmp     loc_1400056D3
0x140005647  xorps   xmm0, xmm0
0x14000564a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140005650  test    sil, 3
0x140005654  jnz     loc_1400057EA
0x14000565a  mov     r9, rsi
0x14000565d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140005662  shr     r9, 2; unsigned __int64
0x140005666  lea     rcx, [rsp+280h+hObject]; this
0x14000566b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140005670  mov     r14d, eax
0x140005673  test    eax, eax
0x140005675  jns     loc_140005713
0x14000567b  mov     rcx, [rbp+188h]; this
0x140005682  mov     r9d, eax; char *
0x140005685  mov     edx, 14Eh; void *
0x14000568a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000568f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140005694  test    rcx, rcx
0x140005697  jz      short loc_1400056A7
0x140005699  call    cs:__imp_CloseHandle
0x14000569f  test    eax, eax
0x1400056a1  jz      loc_1400057F0
0x1400056a7  mov     rcx, [rsp+280h+hObject]; hObject
0x1400056ac  test    rcx, rcx
0x1400056af  jz      short loc_1400056BF
0x1400056b1  call    cs:__imp_CloseHandle
0x1400056b7  test    eax, eax
0x1400056b9  jz      loc_140005802
0x1400056bf  call    cs:__imp_GetProcessHeap
0x1400056c5  mov     r8, rsi; lpMem
0x1400056c8  xor     edx, edx; dwFlags
0x1400056ca  mov     rcx, rax; hHeap
0x1400056cd  call    cs:__imp_HeapFree
0x1400056d3  mov     rcx, [rbp+188h]; this
0x1400056da  mov     r9d, r14d; char *
0x1400056dd  mov     edx, 137h; void *
0x1400056e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400056e7  test    rdi, rdi
0x1400056ea  jz      short loc_1400056FD
0x1400056ec  mov     rcx, rdi; hMutex
0x1400056ef  call    cs:__imp_ReleaseMutex
0x1400056f5  test    eax, eax
0x1400056f7  jz      loc_140005814
0x1400056fd  mov     rcx, rbx; hObject
0x140005700  call    cs:__imp_CloseHandle
0x140005706  test    eax, eax
0x140005708  jz      loc_140005826
0x14000570e  mov     eax, r14d
0x140005711  jmp     short loc_140005781
0x140005713  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140005718  xor     edx, edx; Val
0x14000571a  mov     dword ptr [rsi], 1
0x140005720  lea     rcx, [rsi+22h]; void *
0x140005724  mov     [rsi+8], rbx
0x140005728  movdqu  xmmword ptr [rsi+10h], xmm0
0x14000572d  lea     r8d, [rdx+56h]; Size
0x140005731  call    memset_0
0x140005736  xor     edx, edx; Val
0x140005738  mov     word ptr [rsi+20h], 58h ; 'X'
0x14000573e  lea     rcx, [rsi+28h]; void *
0x140005742  mov     dword ptr [rsi+24h], 1
0x140005749  lea     r8d, [rdx+50h]; Size
0x14000574d  call    memset_0
0x140005752  xor     ebx, ebx
0x140005754  mov     [r15], rsi
0x140005757  test    rdi, rdi
0x14000575a  jz      short loc_14000576D
0x14000575c  mov     rcx, rdi; hMutex
0x14000575f  call    cs:__imp_ReleaseMutex
0x140005765  test    eax, eax
0x140005767  jz      loc_140005838
0x14000576d  test    rbx, rbx
0x140005770  jz      short loc_14000577F
0x140005772  mov     rcx, rbx; hObject
0x140005775  call    cs:__imp_CloseHandle
0x14000577b  test    eax, eax
0x14000577d  jz      short loc_1400057A7
0x14000577f  xor     eax, eax
0x140005781  mov     rcx, [rbp+180h+var_30]
0x140005788  xor     rcx, rsp; StackCookie
0x14000578b  call    __security_check_cookie
0x140005790  mov     rbx, [rsp+280h+arg_10]
0x140005798  add     rsp, 260h
0x14000579f  pop     r15
0x1400057a1  pop     r14
0x1400057a3  pop     rdi
0x1400057a4  pop     rsi
0x1400057a5  pop     rbp
0x1400057a6  retn
0x1400057a7  mov     rcx, [rbp+188h]; this
0x1400057ae  mov     edx, 0A0Bh; void *
0x1400057b3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400057b9  mov     rcx, [rbp+188h]; this
0x1400057c0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400057c6  mov     rcx, [rbp+188h]; this
0x1400057cd  mov     edx, 0A15h; void *
0x1400057d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400057d8  mov     rcx, [rbp+188h]; this
0x1400057df  mov     edx, 0A0Bh; void *
0x1400057e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400057ea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400057f0  mov     rcx, [rbp+188h]; this
0x1400057f7  mov     edx, 0A0Bh; void *
0x1400057fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005802  mov     rcx, [rbp+188h]; this
0x140005809  mov     edx, 0A0Bh; void *
0x14000580e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005814  mov     rcx, [rbp+188h]; this
0x14000581b  mov     edx, 0A15h; void *
0x140005820  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005826  mov     rcx, [rbp+188h]; this
0x14000582d  mov     edx, 0A0Bh; void *
0x140005832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005838  mov     rcx, [rbp+188h]; this
0x14000583f  mov     edx, 0A15h; void *
0x140005844  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
