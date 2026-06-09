# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000b35c`
- end: `0x18000b74d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000b754`

## callees

- `0x1800026d0`
- `0x180003198`
- `0x180004348`
- `0x180004634`
- `0x180004c88`
- `0x180005768`
- `0x1800059c4`
- `0x1800063b4`
- `0x18000648c`
- `0x18000686c`
- `0x18000687c`
- `0x18000ab98`
- `0x18000b35c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b3d3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b3d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b3f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b3f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b48a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b5c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b662`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b48a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b5c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b662`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000b62f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000b62f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b58f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b58f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b59d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b49b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b678`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b49b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b678`

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
  __int64 v23; // r8
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
0x18000b35c  mov     [rsp-8+arg_10], rbx
0x18000b361  push    rbp
0x18000b362  push    rsi
0x18000b363  push    rdi
0x18000b364  push    r14
0x18000b366  push    r15
0x18000b368  lea     rbp, [rsp-160h]
0x18000b370  sub     rsp, 260h
0x18000b377  mov     rax, cs:__security_cookie
0x18000b37e  xor     rax, rsp
0x18000b381  mov     [rbp+180h+var_30], rax
0x18000b388  mov     r15, rdx
0x18000b38b  mov     qword ptr [rdx], 0
0x18000b392  mov     rbx, rcx
0x18000b395  call    cs:__imp_GetCurrentProcessId
0x18000b39b  mov     r14d, 130h
0x18000b3a1  mov     [rsp+280h+var_258], rbx
0x18000b3a6  mov     r9d, eax
0x18000b3a9  mov     [rsp+280h+var_260], r14d; int
0x18000b3ae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b3b5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b3ba  lea     edx, [r14-2Ch]; unsigned __int64
0x18000b3be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b3c3  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b3c9  lea     rdx, [rsp+280h+Name]; lpName
0x18000b3ce  xor     r8d, r8d; dwFlags
0x18000b3d1  xor     ecx, ecx; lpMutexAttributes
0x18000b3d3  call    cs:__imp_CreateMutexExW
0x18000b3d9  mov     rbx, rax
0x18000b3dc  test    rax, rax
0x18000b3df  jnz     short loc_18000B3EB
0x18000b3e1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b3e6  jmp     loc_18000B684
0x18000b3eb  xor     r8d, r8d; bAlertable
0x18000b3ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b3f1  mov     rcx, rbx; hHandle
0x18000b3f4  call    cs:__imp_WaitForSingleObjectEx
0x18000b3fa  cmp     eax, 102h
0x18000b3ff  jz      short loc_18000B411
0x18000b401  test    eax, 0FFFFFF7Fh
0x18000b406  jnz     loc_18000B6CE
0x18000b40c  mov     rdi, rbx
0x18000b40f  jmp     short loc_18000B413
0x18000b411  xor     edi, edi
0x18000b413  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000b418  mov     [rsp+280h+hObject], 0
0x18000b421  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b426  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b42b  mov     esi, eax
0x18000b42d  test    eax, eax
0x18000b42f  jns     short loc_18000B4B0
0x18000b431  mov     rcx, [rbp+188h]; this
0x18000b438  lea     r8, aWil; "wil"
0x18000b43f  mov     r9d, eax; char *
0x18000b442  mov     edx, 66h ; 'f'; void *
0x18000b447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b44c  mov     rcx, [rbp+188h]; this
0x18000b453  lea     r8, aWil; "wil"
0x18000b45a  mov     r9d, esi; char *
0x18000b45d  mov     edx, 6Fh ; 'o'; void *
0x18000b462  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b467  mov     rcx, [rbp+188h]; this
0x18000b46e  lea     r8, aWil; "wil"
0x18000b475  mov     r9d, esi; char *
0x18000b478  mov     edx, 12Eh; void *
0x18000b47d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b482  test    rdi, rdi
0x18000b485  jz      short loc_18000B498
0x18000b487  mov     rcx, rdi; hMutex
0x18000b48a  call    cs:__imp_ReleaseMutex
0x18000b490  test    eax, eax
0x18000b492  jz      loc_18000B6DB
0x18000b498  mov     rcx, rbx; hObject
0x18000b49b  call    cs:__imp_CloseHandle
0x18000b4a1  test    eax, eax
0x18000b4a3  jz      loc_18000B6ED
0x18000b4a9  mov     eax, esi
0x18000b4ab  jmp     loc_18000B684
0x18000b4b0  mov     rax, [rsp+280h+hObject]
0x18000b4b5  lea     rcx, ds:0[rax*4]
0x18000b4bd  test    rcx, rcx
0x18000b4c0  jz      short loc_18000B4D0
0x18000b4c2  mov     [r15], rcx
0x18000b4c5  mov     eax, [rcx]
0x18000b4c7  inc     eax
0x18000b4c9  mov     [rcx], eax
0x18000b4cb  jmp     loc_18000B65A
0x18000b4d0  mov     rdx, r14; dwBytes
0x18000b4d3  mov     qword ptr [r15], 0
0x18000b4da  mov     ecx, 8; dwFlags
0x18000b4df  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b4e4  mov     r14, rax
0x18000b4e7  test    rax, rax
0x18000b4ea  jnz     short loc_18000B511
0x18000b4ec  mov     rcx, [rbp+188h]; this
0x18000b4f3  lea     r8, aWil; "wil"
0x18000b4fa  mov     esi, 8007000Eh
0x18000b4ff  mov     edx, 14Bh; void *
0x18000b504  mov     r9d, esi; char *
0x18000b507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b50c  jmp     loc_18000B5A3
0x18000b511  xorps   xmm0, xmm0
0x18000b514  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000b51a  test    r14b, 3
0x18000b51e  jnz     loc_18000B6FF
0x18000b524  mov     r9, r14
0x18000b527  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000b52c  shr     r9, 2; unsigned __int64
0x18000b530  lea     rcx, [rsp+280h+hObject]; this
0x18000b535  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000b53a  mov     esi, eax
0x18000b53c  test    eax, eax
0x18000b53e  jns     loc_18000B5EA
0x18000b544  mov     rcx, [rbp+188h]; this
0x18000b54b  lea     r8, aWil; "wil"
0x18000b552  mov     r9d, eax; char *
0x18000b555  mov     edx, 14Eh; void *
0x18000b55a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b55f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000b564  test    rcx, rcx
0x18000b567  jz      short loc_18000B577
0x18000b569  call    cs:__imp_CloseHandle
0x18000b56f  test    eax, eax
0x18000b571  jz      loc_18000B705
0x18000b577  mov     rcx, [rsp+280h+hObject]; hObject
0x18000b57c  test    rcx, rcx
0x18000b57f  jz      short loc_18000B58F
0x18000b581  call    cs:__imp_CloseHandle
0x18000b587  test    eax, eax
0x18000b589  jz      loc_18000B717
0x18000b58f  call    cs:__imp_GetProcessHeap
0x18000b595  mov     r8, r14; lpMem
0x18000b598  xor     edx, edx; dwFlags
0x18000b59a  mov     rcx, rax; hHeap
0x18000b59d  call    cs:__imp_HeapFree
0x18000b5a3  mov     rcx, [rbp+188h]; this
0x18000b5aa  lea     r8, aWil; "wil"
0x18000b5b1  mov     r9d, esi; char *
0x18000b5b4  mov     edx, 137h; void *
0x18000b5b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5be  test    rdi, rdi
0x18000b5c1  jz      short loc_18000B5D4
0x18000b5c3  mov     rcx, rdi; hMutex
0x18000b5c6  call    cs:__imp_ReleaseMutex
0x18000b5cc  test    eax, eax
0x18000b5ce  jz      loc_18000B729
0x18000b5d4  mov     rcx, rbx; hObject
0x18000b5d7  call    cs:__imp_CloseHandle
0x18000b5dd  test    eax, eax
0x18000b5df  jz      loc_18000B6BC
0x18000b5e5  jmp     loc_18000B4A9
0x18000b5ea  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000b5ef  lea     rcx, [r14+28h]; void *
0x18000b5f3  mov     dword ptr [r14], 1
0x18000b5fa  xor     edx, edx; Val
0x18000b5fc  mov     [r14+8], rbx
0x18000b600  mov     r8d, 108h; Size
0x18000b606  movdqu  xmmword ptr [r14+10h], xmm0
0x18000b60c  call    memset_0
0x18000b611  xor     eax, eax
0x18000b613  lea     rcx, [r14+28h]; this
0x18000b617  mov     [r14+20h], rax
0x18000b61b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000b620  lea     rbx, [r14+0E8h]
0x18000b627  xor     r8d, r8d; Flags
0x18000b62a  mov     rcx, rbx; lpCriticalSection
0x18000b62d  xor     edx, edx; dwSpinCount
0x18000b62f  call    cs:__imp_InitializeCriticalSectionEx
0x18000b635  mov     qword ptr [rbx+28h], 0
0x18000b63d  mov     qword ptr [rbx+30h], 0
0x18000b645  mov     qword ptr [rbx+38h], 0
0x18000b64d  mov     qword ptr [rbx+40h], 0
0x18000b655  xor     ebx, ebx
0x18000b657  mov     [r15], r14
0x18000b65a  test    rdi, rdi
0x18000b65d  jz      short loc_18000B670
0x18000b65f  mov     rcx, rdi; hMutex
0x18000b662  call    cs:__imp_ReleaseMutex
0x18000b668  test    eax, eax
0x18000b66a  jz      loc_18000B73B
0x18000b670  test    rbx, rbx
0x18000b673  jz      short loc_18000B682
0x18000b675  mov     rcx, rbx; hObject
0x18000b678  call    cs:__imp_CloseHandle
0x18000b67e  test    eax, eax
0x18000b680  jz      short loc_18000B6AA
0x18000b682  xor     eax, eax
0x18000b684  mov     rcx, [rbp+180h+var_30]
0x18000b68b  xor     rcx, rsp; StackCookie
0x18000b68e  call    __security_check_cookie
0x18000b693  mov     rbx, [rsp+280h+arg_10]
0x18000b69b  add     rsp, 260h
0x18000b6a2  pop     r15
0x18000b6a4  pop     r14
0x18000b6a6  pop     rdi
0x18000b6a7  pop     rsi
0x18000b6a8  pop     rbp
0x18000b6a9  retn
0x18000b6aa  mov     rcx, [rbp+188h]; this
0x18000b6b1  mov     edx, 0A0Bh; void *
0x18000b6b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b6bc  mov     rcx, [rbp+188h]; this
0x18000b6c3  mov     edx, 0A0Bh; void *
0x18000b6c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b6ce  mov     rcx, [rbp+188h]; this
0x18000b6d5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000b6db  mov     rcx, [rbp+188h]; this
0x18000b6e2  mov     edx, 0A15h; void *
0x18000b6e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b6ed  mov     rcx, [rbp+188h]; this
0x18000b6f4  mov     edx, 0A0Bh; void *
0x18000b6f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b6ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b705  mov     rcx, [rbp+188h]; this
0x18000b70c  mov     edx, 0A0Bh; void *
0x18000b711  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b717  mov     rcx, [rbp+188h]; this
0x18000b71e  mov     edx, 0A0Bh; void *
0x18000b723  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b729  mov     rcx, [rbp+188h]; this
0x18000b730  mov     edx, 0A15h; void *
0x18000b735  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b73b  mov     rcx, [rbp+188h]; this
0x18000b742  mov     edx, 0A15h; void *
0x18000b747  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
