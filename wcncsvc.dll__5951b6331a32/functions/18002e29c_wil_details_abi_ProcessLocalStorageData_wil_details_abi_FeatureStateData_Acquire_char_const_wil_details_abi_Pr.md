# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18002e29c`
- end: `0x18002e663`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18002e934`

## callees

- `0x18002d514`
- `0x18002e29c`
- `0x18002e66c`
- `0x18002eb90`
- `0x1800301a8`
- `0x180030e88`
- `0x180032864`
- `0x180033200`
- `0x18003360c`
- `0x18003426c`
- `0x18003427c`
- `0x180056df2`
- `0x180056e30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002e545`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18002e545`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002e313`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002e313`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002e334`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002e334`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e3b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e4dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e578`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e3b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e4dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e578`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e49e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e4ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e58e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e3c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e486`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e49e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e4ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e58e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e2d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e2d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e4ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e4ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002e4ba`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
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
0x18002e29c  mov     [rsp-8+arg_10], rbx
0x18002e2a1  push    rbp
0x18002e2a2  push    rsi
0x18002e2a3  push    rdi
0x18002e2a4  push    r14
0x18002e2a6  push    r15
0x18002e2a8  lea     rbp, [rsp-160h]
0x18002e2b0  sub     rsp, 260h
0x18002e2b7  mov     rax, cs:__security_cookie
0x18002e2be  xor     rax, rsp
0x18002e2c1  mov     [rbp+180h+var_30], rax
0x18002e2c8  mov     r15, rdx
0x18002e2cb  mov     qword ptr [rdx], 0
0x18002e2d2  mov     rbx, rcx
0x18002e2d5  call    cs:__imp_GetCurrentProcessId
0x18002e2db  mov     r14d, 130h
0x18002e2e1  mov     [rsp+280h+var_258], rbx
0x18002e2e6  mov     r9d, eax
0x18002e2e9  mov     [rsp+280h+var_260], r14d; int
0x18002e2ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002e2f5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002e2fa  lea     edx, [r14-2Ch]; unsigned __int64
0x18002e2fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e303  mov     r9d, 1F0001h; dwDesiredAccess
0x18002e309  lea     rdx, [rsp+280h+Name]; lpName
0x18002e30e  xor     r8d, r8d; dwFlags
0x18002e311  xor     ecx, ecx; lpMutexAttributes
0x18002e313  call    cs:__imp_CreateMutexExW
0x18002e319  mov     rbx, rax
0x18002e31c  test    rax, rax
0x18002e31f  jnz     short loc_18002E32B
0x18002e321  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002e326  jmp     loc_18002E59A
0x18002e32b  xor     r8d, r8d; bAlertable
0x18002e32e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002e331  mov     rcx, rbx; hHandle
0x18002e334  call    cs:__imp_WaitForSingleObjectEx
0x18002e33a  cmp     eax, 102h
0x18002e33f  jz      short loc_18002E351
0x18002e341  test    eax, 0FFFFFF7Fh
0x18002e346  jnz     loc_18002E5E4
0x18002e34c  mov     rdi, rbx
0x18002e34f  jmp     short loc_18002E353
0x18002e351  xor     edi, edi
0x18002e353  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18002e358  mov     [rsp+280h+hObject], 0
0x18002e361  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002e366  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002e36b  mov     esi, eax
0x18002e36d  test    eax, eax
0x18002e36f  jns     short loc_18002E3DB
0x18002e371  mov     rcx, [rbp+188h]; this
0x18002e378  mov     r9d, eax; char *
0x18002e37b  mov     edx, 66h ; 'f'; void *
0x18002e380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e385  mov     rcx, [rbp+188h]; this
0x18002e38c  mov     r9d, esi; char *
0x18002e38f  mov     edx, 6Fh ; 'o'; void *
0x18002e394  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e399  mov     rcx, [rbp+188h]; this
0x18002e3a0  mov     r9d, esi; char *
0x18002e3a3  mov     edx, 12Eh; void *
0x18002e3a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e3ad  test    rdi, rdi
0x18002e3b0  jz      short loc_18002E3C3
0x18002e3b2  mov     rcx, rdi; hMutex
0x18002e3b5  call    cs:__imp_ReleaseMutex
0x18002e3bb  test    eax, eax
0x18002e3bd  jz      loc_18002E5F1
0x18002e3c3  mov     rcx, rbx; hObject
0x18002e3c6  call    cs:__imp_CloseHandle
0x18002e3cc  test    eax, eax
0x18002e3ce  jz      loc_18002E603
0x18002e3d4  mov     eax, esi
0x18002e3d6  jmp     loc_18002E59A
0x18002e3db  mov     rax, [rsp+280h+hObject]
0x18002e3e0  lea     rcx, ds:0[rax*4]
0x18002e3e8  test    rcx, rcx
0x18002e3eb  jz      short loc_18002E3FB
0x18002e3ed  mov     [r15], rcx
0x18002e3f0  mov     eax, [rcx]
0x18002e3f2  inc     eax
0x18002e3f4  mov     [rcx], eax
0x18002e3f6  jmp     loc_18002E570
0x18002e3fb  mov     rdx, r14; dwBytes
0x18002e3fe  mov     qword ptr [r15], 0
0x18002e405  mov     ecx, 8; dwFlags
0x18002e40a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002e40f  mov     r14, rax
0x18002e412  test    rax, rax
0x18002e415  jnz     short loc_18002E435
0x18002e417  mov     rcx, [rbp+188h]; this
0x18002e41e  mov     esi, 8007000Eh
0x18002e423  mov     r9d, esi; char *
0x18002e426  mov     edx, 14Bh; void *
0x18002e42b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e430  jmp     loc_18002E4C0
0x18002e435  xorps   xmm0, xmm0
0x18002e438  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18002e43e  test    r14b, 3
0x18002e442  jnz     loc_18002E615
0x18002e448  mov     r9, r14
0x18002e44b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18002e450  shr     r9, 2; unsigned __int64
0x18002e454  lea     rcx, [rsp+280h+hObject]; this
0x18002e459  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18002e45e  mov     esi, eax
0x18002e460  test    eax, eax
0x18002e462  jns     loc_18002E500
0x18002e468  mov     rcx, [rbp+188h]; this
0x18002e46f  mov     r9d, eax; char *
0x18002e472  mov     edx, 14Eh; void *
0x18002e477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e47c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18002e481  test    rcx, rcx
0x18002e484  jz      short loc_18002E494
0x18002e486  call    cs:__imp_CloseHandle
0x18002e48c  test    eax, eax
0x18002e48e  jz      loc_18002E61B
0x18002e494  mov     rcx, [rsp+280h+hObject]; hObject
0x18002e499  test    rcx, rcx
0x18002e49c  jz      short loc_18002E4AC
0x18002e49e  call    cs:__imp_CloseHandle
0x18002e4a4  test    eax, eax
0x18002e4a6  jz      loc_18002E62D
0x18002e4ac  call    cs:__imp_GetProcessHeap
0x18002e4b2  mov     r8, r14; lpMem
0x18002e4b5  xor     edx, edx; dwFlags
0x18002e4b7  mov     rcx, rax; hHeap
0x18002e4ba  call    cs:__imp_HeapFree
0x18002e4c0  mov     rcx, [rbp+188h]; this
0x18002e4c7  mov     r9d, esi; char *
0x18002e4ca  mov     edx, 137h; void *
0x18002e4cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4d4  test    rdi, rdi
0x18002e4d7  jz      short loc_18002E4EA
0x18002e4d9  mov     rcx, rdi; hMutex
0x18002e4dc  call    cs:__imp_ReleaseMutex
0x18002e4e2  test    eax, eax
0x18002e4e4  jz      loc_18002E63F
0x18002e4ea  mov     rcx, rbx; hObject
0x18002e4ed  call    cs:__imp_CloseHandle
0x18002e4f3  test    eax, eax
0x18002e4f5  jz      loc_18002E5D2
0x18002e4fb  jmp     loc_18002E3D4
0x18002e500  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18002e505  lea     rcx, [r14+28h]; void *
0x18002e509  mov     dword ptr [r14], 1
0x18002e510  xor     edx, edx; Val
0x18002e512  mov     [r14+8], rbx
0x18002e516  mov     r8d, 108h; Size
0x18002e51c  movdqu  xmmword ptr [r14+10h], xmm0
0x18002e522  call    memset_0
0x18002e527  xor     eax, eax
0x18002e529  lea     rcx, [r14+28h]; this
0x18002e52d  mov     [r14+20h], rax
0x18002e531  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18002e536  lea     rbx, [r14+0E8h]
0x18002e53d  xor     r8d, r8d; Flags
0x18002e540  mov     rcx, rbx; lpCriticalSection
0x18002e543  xor     edx, edx; dwSpinCount
0x18002e545  call    cs:__imp_InitializeCriticalSectionEx
0x18002e54b  mov     qword ptr [rbx+28h], 0
0x18002e553  mov     qword ptr [rbx+30h], 0
0x18002e55b  mov     qword ptr [rbx+38h], 0
0x18002e563  mov     qword ptr [rbx+40h], 0
0x18002e56b  xor     ebx, ebx
0x18002e56d  mov     [r15], r14
0x18002e570  test    rdi, rdi
0x18002e573  jz      short loc_18002E586
0x18002e575  mov     rcx, rdi; hMutex
0x18002e578  call    cs:__imp_ReleaseMutex
0x18002e57e  test    eax, eax
0x18002e580  jz      loc_18002E651
0x18002e586  test    rbx, rbx
0x18002e589  jz      short loc_18002E598
0x18002e58b  mov     rcx, rbx; hObject
0x18002e58e  call    cs:__imp_CloseHandle
0x18002e594  test    eax, eax
0x18002e596  jz      short loc_18002E5C0
0x18002e598  xor     eax, eax
0x18002e59a  mov     rcx, [rbp+180h+var_30]
0x18002e5a1  xor     rcx, rsp; StackCookie
0x18002e5a4  call    __security_check_cookie
0x18002e5a9  mov     rbx, [rsp+280h+arg_10]
0x18002e5b1  add     rsp, 260h
0x18002e5b8  pop     r15
0x18002e5ba  pop     r14
0x18002e5bc  pop     rdi
0x18002e5bd  pop     rsi
0x18002e5be  pop     rbp
0x18002e5bf  retn
0x18002e5c0  mov     rcx, [rbp+188h]; this
0x18002e5c7  mov     edx, 0A0Bh; void *
0x18002e5cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e5d2  mov     rcx, [rbp+188h]; this
0x18002e5d9  mov     edx, 0A0Bh; void *
0x18002e5de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e5e4  mov     rcx, [rbp+188h]; this
0x18002e5eb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002e5f1  mov     rcx, [rbp+188h]; this
0x18002e5f8  mov     edx, 0A15h; void *
0x18002e5fd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e603  mov     rcx, [rbp+188h]; this
0x18002e60a  mov     edx, 0A0Bh; void *
0x18002e60f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e615  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002e61b  mov     rcx, [rbp+188h]; this
0x18002e622  mov     edx, 0A0Bh; void *
0x18002e627  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e62d  mov     rcx, [rbp+188h]; this
0x18002e634  mov     edx, 0A0Bh; void *
0x18002e639  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e63f  mov     rcx, [rbp+188h]; this
0x18002e646  mov     edx, 0A15h; void *
0x18002e64b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002e651  mov     rcx, [rbp+188h]; this
0x18002e658  mov     edx, 0A15h; void *
0x18002e65d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
