# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18001a148`
- end: `0x18001a50f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18001a518`

## callees

- `0x180003be0`
- `0x180003ec4`
- `0x180004518`
- `0x180004fe8`
- `0x180005230`
- `0x180005684`
- `0x180005710`
- `0x180005acc`
- `0x180005adc`
- `0x180019a58`
- `0x18001a148`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001a1bf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001a1bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001a1e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001a1e0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001a3f1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001a3f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a261`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a388`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a424`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a261`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a388`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001a424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a358`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a366`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a366`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a332`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a43a`

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
0x18001a148  mov     [rsp-8+arg_10], rbx
0x18001a14d  push    rbp
0x18001a14e  push    rsi
0x18001a14f  push    rdi
0x18001a150  push    r14
0x18001a152  push    r15
0x18001a154  lea     rbp, [rsp-160h]
0x18001a15c  sub     rsp, 260h
0x18001a163  mov     rax, cs:__security_cookie
0x18001a16a  xor     rax, rsp
0x18001a16d  mov     [rbp+180h+var_30], rax
0x18001a174  mov     r15, rdx
0x18001a177  mov     qword ptr [rdx], 0
0x18001a17e  mov     rbx, rcx
0x18001a181  call    cs:__imp_GetCurrentProcessId
0x18001a187  mov     r14d, 130h
0x18001a18d  mov     [rsp+280h+var_258], rbx
0x18001a192  mov     r9d, eax
0x18001a195  mov     [rsp+280h+var_260], r14d; int
0x18001a19a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001a1a1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001a1a6  lea     edx, [r14-2Ch]; unsigned __int64
0x18001a1aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a1af  mov     r9d, 1F0001h; dwDesiredAccess
0x18001a1b5  lea     rdx, [rsp+280h+Name]; lpName
0x18001a1ba  xor     r8d, r8d; dwFlags
0x18001a1bd  xor     ecx, ecx; lpMutexAttributes
0x18001a1bf  call    cs:__imp_CreateMutexExW
0x18001a1c5  mov     rbx, rax
0x18001a1c8  test    rax, rax
0x18001a1cb  jnz     short loc_18001A1D7
0x18001a1cd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001a1d2  jmp     loc_18001A446
0x18001a1d7  xor     r8d, r8d; bAlertable
0x18001a1da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a1dd  mov     rcx, rbx; hHandle
0x18001a1e0  call    cs:__imp_WaitForSingleObjectEx
0x18001a1e6  cmp     eax, 102h
0x18001a1eb  jz      short loc_18001A1FD
0x18001a1ed  test    eax, 0FFFFFF7Fh
0x18001a1f2  jnz     loc_18001A490
0x18001a1f8  mov     rdi, rbx
0x18001a1fb  jmp     short loc_18001A1FF
0x18001a1fd  xor     edi, edi
0x18001a1ff  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18001a204  mov     [rsp+280h+hObject], 0
0x18001a20d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001a212  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001a217  mov     esi, eax
0x18001a219  test    eax, eax
0x18001a21b  jns     short loc_18001A287
0x18001a21d  mov     rcx, [rbp+188h]; this
0x18001a224  mov     r9d, eax; char *
0x18001a227  mov     edx, 66h ; 'f'; void *
0x18001a22c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a231  mov     rcx, [rbp+188h]; this
0x18001a238  mov     r9d, esi; char *
0x18001a23b  mov     edx, 6Fh ; 'o'; void *
0x18001a240  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a245  mov     rcx, [rbp+188h]; this
0x18001a24c  mov     r9d, esi; char *
0x18001a24f  mov     edx, 12Eh; void *
0x18001a254  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a259  test    rdi, rdi
0x18001a25c  jz      short loc_18001A26F
0x18001a25e  mov     rcx, rdi; hMutex
0x18001a261  call    cs:__imp_ReleaseMutex
0x18001a267  test    eax, eax
0x18001a269  jz      loc_18001A49D
0x18001a26f  mov     rcx, rbx; hObject
0x18001a272  call    cs:__imp_CloseHandle
0x18001a278  test    eax, eax
0x18001a27a  jz      loc_18001A4AF
0x18001a280  mov     eax, esi
0x18001a282  jmp     loc_18001A446
0x18001a287  mov     rax, [rsp+280h+hObject]
0x18001a28c  lea     rcx, ds:0[rax*4]
0x18001a294  test    rcx, rcx
0x18001a297  jz      short loc_18001A2A7
0x18001a299  mov     [r15], rcx
0x18001a29c  mov     eax, [rcx]
0x18001a29e  inc     eax
0x18001a2a0  mov     [rcx], eax
0x18001a2a2  jmp     loc_18001A41C
0x18001a2a7  mov     rdx, r14; dwBytes
0x18001a2aa  mov     qword ptr [r15], 0
0x18001a2b1  mov     ecx, 8; dwFlags
0x18001a2b6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a2bb  mov     r14, rax
0x18001a2be  test    rax, rax
0x18001a2c1  jnz     short loc_18001A2E1
0x18001a2c3  mov     rcx, [rbp+188h]; this
0x18001a2ca  mov     esi, 8007000Eh
0x18001a2cf  mov     r9d, esi; char *
0x18001a2d2  mov     edx, 14Bh; void *
0x18001a2d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2dc  jmp     loc_18001A36C
0x18001a2e1  xorps   xmm0, xmm0
0x18001a2e4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18001a2ea  test    r14b, 3
0x18001a2ee  jnz     loc_18001A4C1
0x18001a2f4  mov     r9, r14
0x18001a2f7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18001a2fc  shr     r9, 2; unsigned __int64
0x18001a300  lea     rcx, [rsp+280h+hObject]; this
0x18001a305  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001a30a  mov     esi, eax
0x18001a30c  test    eax, eax
0x18001a30e  jns     loc_18001A3AC
0x18001a314  mov     rcx, [rbp+188h]; this
0x18001a31b  mov     r9d, eax; char *
0x18001a31e  mov     edx, 14Eh; void *
0x18001a323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a328  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18001a32d  test    rcx, rcx
0x18001a330  jz      short loc_18001A340
0x18001a332  call    cs:__imp_CloseHandle
0x18001a338  test    eax, eax
0x18001a33a  jz      loc_18001A4C7
0x18001a340  mov     rcx, [rsp+280h+hObject]; hObject
0x18001a345  test    rcx, rcx
0x18001a348  jz      short loc_18001A358
0x18001a34a  call    cs:__imp_CloseHandle
0x18001a350  test    eax, eax
0x18001a352  jz      loc_18001A4D9
0x18001a358  call    cs:__imp_GetProcessHeap
0x18001a35e  mov     r8, r14; lpMem
0x18001a361  xor     edx, edx; dwFlags
0x18001a363  mov     rcx, rax; hHeap
0x18001a366  call    cs:__imp_HeapFree
0x18001a36c  mov     rcx, [rbp+188h]; this
0x18001a373  mov     r9d, esi; char *
0x18001a376  mov     edx, 137h; void *
0x18001a37b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a380  test    rdi, rdi
0x18001a383  jz      short loc_18001A396
0x18001a385  mov     rcx, rdi; hMutex
0x18001a388  call    cs:__imp_ReleaseMutex
0x18001a38e  test    eax, eax
0x18001a390  jz      loc_18001A4EB
0x18001a396  mov     rcx, rbx; hObject
0x18001a399  call    cs:__imp_CloseHandle
0x18001a39f  test    eax, eax
0x18001a3a1  jz      loc_18001A47E
0x18001a3a7  jmp     loc_18001A280
0x18001a3ac  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18001a3b1  lea     rcx, [r14+28h]; void *
0x18001a3b5  mov     dword ptr [r14], 1
0x18001a3bc  xor     edx, edx; Val
0x18001a3be  mov     [r14+8], rbx
0x18001a3c2  mov     r8d, 108h; Size
0x18001a3c8  movdqu  xmmword ptr [r14+10h], xmm0
0x18001a3ce  call    memset_0
0x18001a3d3  xor     eax, eax
0x18001a3d5  lea     rcx, [r14+28h]; this
0x18001a3d9  mov     [r14+20h], rax
0x18001a3dd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001a3e2  lea     rbx, [r14+0E8h]
0x18001a3e9  xor     r8d, r8d; Flags
0x18001a3ec  mov     rcx, rbx; lpCriticalSection
0x18001a3ef  xor     edx, edx; dwSpinCount
0x18001a3f1  call    cs:__imp_InitializeCriticalSectionEx
0x18001a3f7  mov     qword ptr [rbx+28h], 0
0x18001a3ff  mov     qword ptr [rbx+30h], 0
0x18001a407  mov     qword ptr [rbx+38h], 0
0x18001a40f  mov     qword ptr [rbx+40h], 0
0x18001a417  xor     ebx, ebx
0x18001a419  mov     [r15], r14
0x18001a41c  test    rdi, rdi
0x18001a41f  jz      short loc_18001A432
0x18001a421  mov     rcx, rdi; hMutex
0x18001a424  call    cs:__imp_ReleaseMutex
0x18001a42a  test    eax, eax
0x18001a42c  jz      loc_18001A4FD
0x18001a432  test    rbx, rbx
0x18001a435  jz      short loc_18001A444
0x18001a437  mov     rcx, rbx; hObject
0x18001a43a  call    cs:__imp_CloseHandle
0x18001a440  test    eax, eax
0x18001a442  jz      short loc_18001A46C
0x18001a444  xor     eax, eax
0x18001a446  mov     rcx, [rbp+180h+var_30]
0x18001a44d  xor     rcx, rsp; StackCookie
0x18001a450  call    __security_check_cookie
0x18001a455  mov     rbx, [rsp+280h+arg_10]
0x18001a45d  add     rsp, 260h
0x18001a464  pop     r15
0x18001a466  pop     r14
0x18001a468  pop     rdi
0x18001a469  pop     rsi
0x18001a46a  pop     rbp
0x18001a46b  retn
0x18001a46c  mov     rcx, [rbp+188h]; this
0x18001a473  mov     edx, 0A0Bh; void *
0x18001a478  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a47e  mov     rcx, [rbp+188h]; this
0x18001a485  mov     edx, 0A0Bh; void *
0x18001a48a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a490  mov     rcx, [rbp+188h]; this
0x18001a497  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001a49d  mov     rcx, [rbp+188h]; this
0x18001a4a4  mov     edx, 0A15h; void *
0x18001a4a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a4af  mov     rcx, [rbp+188h]; this
0x18001a4b6  mov     edx, 0A0Bh; void *
0x18001a4bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a4c1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001a4c7  mov     rcx, [rbp+188h]; this
0x18001a4ce  mov     edx, 0A0Bh; void *
0x18001a4d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a4d9  mov     rcx, [rbp+188h]; this
0x18001a4e0  mov     edx, 0A0Bh; void *
0x18001a4e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a4eb  mov     rcx, [rbp+188h]; this
0x18001a4f2  mov     edx, 0A15h; void *
0x18001a4f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001a4fd  mov     rcx, [rbp+188h]; this
0x18001a504  mov     edx, 0A15h; void *
0x18001a509  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
