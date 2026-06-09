# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800041f0`
- end: `0x1800045b7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004b04`

## callees

- `0x180001670`
- `0x180001fa4`
- `0x180003540`
- `0x1800041f0`
- `0x180004830`
- `0x180004d58`
- `0x180005678`
- `0x180006678`
- `0x180007b90`
- `0x18000805c`
- `0x180008434`
- `0x180008d08`
- `0x180008d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004309`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004430`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800044cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004309`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004430`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800044cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004288`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004288`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004499`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004499`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004267`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004267`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000440e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000440e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004400`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004229`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000431a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000431a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800043f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044e2`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1800041f0  mov     [rsp-8+arg_10], rbx
0x1800041f5  push    rbp
0x1800041f6  push    rsi
0x1800041f7  push    rdi
0x1800041f8  push    r14
0x1800041fa  push    r15
0x1800041fc  lea     rbp, [rsp-160h]
0x180004204  sub     rsp, 260h
0x18000420b  mov     rax, cs:__security_cookie
0x180004212  xor     rax, rsp
0x180004215  mov     [rbp+180h+var_30], rax
0x18000421c  mov     r15, rdx
0x18000421f  mov     qword ptr [rdx], 0
0x180004226  mov     rbx, rcx
0x180004229  call    cs:__imp_GetCurrentProcessId
0x18000422f  mov     r14d, 130h
0x180004235  mov     [rsp+280h+var_258], rbx
0x18000423a  mov     r9d, eax
0x18000423d  mov     [rsp+280h+var_260], r14d; int
0x180004242  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004249  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000424e  lea     edx, [r14-2Ch]; unsigned __int64
0x180004252  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004257  mov     r9d, 1F0001h; dwDesiredAccess
0x18000425d  lea     rdx, [rsp+280h+Name]; lpName
0x180004262  xor     r8d, r8d; dwFlags
0x180004265  xor     ecx, ecx; lpMutexAttributes
0x180004267  call    cs:__imp_CreateMutexExW
0x18000426d  mov     rbx, rax
0x180004270  test    rax, rax
0x180004273  jnz     short loc_18000427F
0x180004275  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000427a  jmp     loc_1800044EE
0x18000427f  xor     r8d, r8d; bAlertable
0x180004282  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004285  mov     rcx, rbx; hHandle
0x180004288  call    cs:__imp_WaitForSingleObjectEx
0x18000428e  cmp     eax, 102h
0x180004293  jz      short loc_1800042A5
0x180004295  test    eax, 0FFFFFF7Fh
0x18000429a  jnz     loc_180004538
0x1800042a0  mov     rdi, rbx
0x1800042a3  jmp     short loc_1800042A7
0x1800042a5  xor     edi, edi
0x1800042a7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800042ac  mov     [rsp+280h+hObject], 0
0x1800042b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800042ba  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800042bf  mov     esi, eax
0x1800042c1  test    eax, eax
0x1800042c3  jns     short loc_18000432F
0x1800042c5  mov     rcx, [rbp+188h]; this
0x1800042cc  mov     r9d, eax; char *
0x1800042cf  mov     edx, 66h ; 'f'; void *
0x1800042d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042d9  mov     rcx, [rbp+188h]; this
0x1800042e0  mov     r9d, esi; char *
0x1800042e3  mov     edx, 6Fh ; 'o'; void *
0x1800042e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800042ed  mov     rcx, [rbp+188h]; this
0x1800042f4  mov     r9d, esi; char *
0x1800042f7  mov     edx, 12Eh; void *
0x1800042fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004301  test    rdi, rdi
0x180004304  jz      short loc_180004317
0x180004306  mov     rcx, rdi; hMutex
0x180004309  call    cs:__imp_ReleaseMutex
0x18000430f  test    eax, eax
0x180004311  jz      loc_180004545
0x180004317  mov     rcx, rbx; hObject
0x18000431a  call    cs:__imp_CloseHandle
0x180004320  test    eax, eax
0x180004322  jz      loc_180004557
0x180004328  mov     eax, esi
0x18000432a  jmp     loc_1800044EE
0x18000432f  mov     rax, [rsp+280h+hObject]
0x180004334  lea     rcx, ds:0[rax*4]
0x18000433c  test    rcx, rcx
0x18000433f  jz      short loc_18000434F
0x180004341  mov     [r15], rcx
0x180004344  mov     eax, [rcx]
0x180004346  inc     eax
0x180004348  mov     [rcx], eax
0x18000434a  jmp     loc_1800044C4
0x18000434f  mov     rdx, r14; dwBytes
0x180004352  mov     qword ptr [r15], 0
0x180004359  mov     ecx, 8; dwFlags
0x18000435e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004363  mov     r14, rax
0x180004366  test    rax, rax
0x180004369  jnz     short loc_180004389
0x18000436b  mov     rcx, [rbp+188h]; this
0x180004372  mov     esi, 8007000Eh
0x180004377  mov     r9d, esi; char *
0x18000437a  mov     edx, 14Bh; void *
0x18000437f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004384  jmp     loc_180004414
0x180004389  xorps   xmm0, xmm0
0x18000438c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004392  test    r14b, 3
0x180004396  jnz     loc_180004569
0x18000439c  mov     r9, r14
0x18000439f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800043a4  shr     r9, 2; unsigned __int64
0x1800043a8  lea     rcx, [rsp+280h+hObject]; this
0x1800043ad  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800043b2  mov     esi, eax
0x1800043b4  test    eax, eax
0x1800043b6  jns     loc_180004454
0x1800043bc  mov     rcx, [rbp+188h]; this
0x1800043c3  mov     r9d, eax; char *
0x1800043c6  mov     edx, 14Eh; void *
0x1800043cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043d0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800043d5  test    rcx, rcx
0x1800043d8  jz      short loc_1800043E8
0x1800043da  call    cs:__imp_CloseHandle
0x1800043e0  test    eax, eax
0x1800043e2  jz      loc_18000456F
0x1800043e8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800043ed  test    rcx, rcx
0x1800043f0  jz      short loc_180004400
0x1800043f2  call    cs:__imp_CloseHandle
0x1800043f8  test    eax, eax
0x1800043fa  jz      loc_180004581
0x180004400  call    cs:__imp_GetProcessHeap
0x180004406  mov     r8, r14; lpMem
0x180004409  xor     edx, edx; dwFlags
0x18000440b  mov     rcx, rax; hHeap
0x18000440e  call    cs:__imp_HeapFree
0x180004414  mov     rcx, [rbp+188h]; this
0x18000441b  mov     r9d, esi; char *
0x18000441e  mov     edx, 137h; void *
0x180004423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004428  test    rdi, rdi
0x18000442b  jz      short loc_18000443E
0x18000442d  mov     rcx, rdi; hMutex
0x180004430  call    cs:__imp_ReleaseMutex
0x180004436  test    eax, eax
0x180004438  jz      loc_180004593
0x18000443e  mov     rcx, rbx; hObject
0x180004441  call    cs:__imp_CloseHandle
0x180004447  test    eax, eax
0x180004449  jz      loc_180004526
0x18000444f  jmp     loc_180004328
0x180004454  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004459  lea     rcx, [r14+28h]; void *
0x18000445d  mov     dword ptr [r14], 1
0x180004464  xor     edx, edx; Val
0x180004466  mov     [r14+8], rbx
0x18000446a  mov     r8d, 108h; Size
0x180004470  movdqu  xmmword ptr [r14+10h], xmm0
0x180004476  call    memset_0
0x18000447b  xor     eax, eax
0x18000447d  lea     rcx, [r14+28h]; this
0x180004481  mov     [r14+20h], rax
0x180004485  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000448a  lea     rbx, [r14+0E8h]
0x180004491  xor     r8d, r8d; Flags
0x180004494  mov     rcx, rbx; lpCriticalSection
0x180004497  xor     edx, edx; dwSpinCount
0x180004499  call    cs:__imp_InitializeCriticalSectionEx
0x18000449f  mov     qword ptr [rbx+28h], 0
0x1800044a7  mov     qword ptr [rbx+30h], 0
0x1800044af  mov     qword ptr [rbx+38h], 0
0x1800044b7  mov     qword ptr [rbx+40h], 0
0x1800044bf  xor     ebx, ebx
0x1800044c1  mov     [r15], r14
0x1800044c4  test    rdi, rdi
0x1800044c7  jz      short loc_1800044DA
0x1800044c9  mov     rcx, rdi; hMutex
0x1800044cc  call    cs:__imp_ReleaseMutex
0x1800044d2  test    eax, eax
0x1800044d4  jz      loc_1800045A5
0x1800044da  test    rbx, rbx
0x1800044dd  jz      short loc_1800044EC
0x1800044df  mov     rcx, rbx; hObject
0x1800044e2  call    cs:__imp_CloseHandle
0x1800044e8  test    eax, eax
0x1800044ea  jz      short loc_180004514
0x1800044ec  xor     eax, eax
0x1800044ee  mov     rcx, [rbp+180h+var_30]
0x1800044f5  xor     rcx, rsp; StackCookie
0x1800044f8  call    __security_check_cookie
0x1800044fd  mov     rbx, [rsp+280h+arg_10]
0x180004505  add     rsp, 260h
0x18000450c  pop     r15
0x18000450e  pop     r14
0x180004510  pop     rdi
0x180004511  pop     rsi
0x180004512  pop     rbp
0x180004513  retn
0x180004514  mov     rcx, [rbp+188h]; this
0x18000451b  mov     edx, 0A0Bh; void *
0x180004520  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004526  mov     rcx, [rbp+188h]; this
0x18000452d  mov     edx, 0A0Bh; void *
0x180004532  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004538  mov     rcx, [rbp+188h]; this
0x18000453f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004545  mov     rcx, [rbp+188h]; this
0x18000454c  mov     edx, 0A15h; void *
0x180004551  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004557  mov     rcx, [rbp+188h]; this
0x18000455e  mov     edx, 0A0Bh; void *
0x180004563  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004569  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000456f  mov     rcx, [rbp+188h]; this
0x180004576  mov     edx, 0A0Bh; void *
0x18000457b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004581  mov     rcx, [rbp+188h]; this
0x180004588  mov     edx, 0A0Bh; void *
0x18000458d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004593  mov     rcx, [rbp+188h]; this
0x18000459a  mov     edx, 0A15h; void *
0x18000459f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045a5  mov     rcx, [rbp+188h]; this
0x1800045ac  mov     edx, 0A15h; void *
0x1800045b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
