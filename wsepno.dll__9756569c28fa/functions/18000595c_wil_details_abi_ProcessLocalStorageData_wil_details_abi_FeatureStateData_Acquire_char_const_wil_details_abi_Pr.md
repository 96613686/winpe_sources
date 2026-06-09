# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000595c`
- end: `0x180005d4d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000668c`

## callees

- `0x180001770`
- `0x1800021f4`
- `0x180003714`
- `0x180004a0c`
- `0x18000595c`
- `0x180005e08`
- `0x180006d24`
- `0x180007418`
- `0x1800083d0`
- `0x18000a374`
- `0x18000ab28`
- `0x18000b494`
- `0x18000b4a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005995`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005995`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059d3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005c2f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005c2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800059f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800059f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c62`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a8a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005bc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c78`

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
0x18000595c  mov     [rsp-8+arg_10], rbx
0x180005961  push    rbp
0x180005962  push    rsi
0x180005963  push    rdi
0x180005964  push    r14
0x180005966  push    r15
0x180005968  lea     rbp, [rsp-160h]
0x180005970  sub     rsp, 260h
0x180005977  mov     rax, cs:__security_cookie
0x18000597e  xor     rax, rsp
0x180005981  mov     [rbp+180h+var_30], rax
0x180005988  mov     r15, rdx
0x18000598b  mov     qword ptr [rdx], 0
0x180005992  mov     rbx, rcx
0x180005995  call    cs:__imp_GetCurrentProcessId
0x18000599b  mov     r14d, 130h
0x1800059a1  mov     [rsp+280h+var_258], rbx
0x1800059a6  mov     r9d, eax
0x1800059a9  mov     [rsp+280h+var_260], r14d; int
0x1800059ae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800059b5  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800059ba  lea     edx, [r14-2Ch]; unsigned __int64
0x1800059be  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800059c3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800059c9  lea     rdx, [rsp+280h+Name]; lpName
0x1800059ce  xor     r8d, r8d; dwFlags
0x1800059d1  xor     ecx, ecx; lpMutexAttributes
0x1800059d3  call    cs:__imp_CreateMutexExW
0x1800059d9  mov     rbx, rax
0x1800059dc  test    rax, rax
0x1800059df  jnz     short loc_1800059EB
0x1800059e1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800059e6  jmp     loc_180005C84
0x1800059eb  xor     r8d, r8d; bAlertable
0x1800059ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800059f1  mov     rcx, rbx; hHandle
0x1800059f4  call    cs:__imp_WaitForSingleObjectEx
0x1800059fa  cmp     eax, 102h
0x1800059ff  jz      short loc_180005A11
0x180005a01  test    eax, 0FFFFFF7Fh
0x180005a06  jnz     loc_180005CCE
0x180005a0c  mov     rdi, rbx
0x180005a0f  jmp     short loc_180005A13
0x180005a11  xor     edi, edi
0x180005a13  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005a18  mov     [rsp+280h+hObject], 0
0x180005a21  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005a26  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005a2b  mov     esi, eax
0x180005a2d  test    eax, eax
0x180005a2f  jns     short loc_180005AB0
0x180005a31  mov     rcx, [rbp+188h]; this
0x180005a38  lea     r8, aWil; "wil"
0x180005a3f  mov     r9d, eax; char *
0x180005a42  mov     edx, 66h ; 'f'; void *
0x180005a47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a4c  mov     rcx, [rbp+188h]; this
0x180005a53  lea     r8, aWil; "wil"
0x180005a5a  mov     r9d, esi; char *
0x180005a5d  mov     edx, 6Fh ; 'o'; void *
0x180005a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a67  mov     rcx, [rbp+188h]; this
0x180005a6e  lea     r8, aWil; "wil"
0x180005a75  mov     r9d, esi; char *
0x180005a78  mov     edx, 12Eh; void *
0x180005a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a82  test    rdi, rdi
0x180005a85  jz      short loc_180005A98
0x180005a87  mov     rcx, rdi; hMutex
0x180005a8a  call    cs:__imp_ReleaseMutex
0x180005a90  test    eax, eax
0x180005a92  jz      loc_180005CDB
0x180005a98  mov     rcx, rbx; hObject
0x180005a9b  call    cs:__imp_CloseHandle
0x180005aa1  test    eax, eax
0x180005aa3  jz      loc_180005CED
0x180005aa9  mov     eax, esi
0x180005aab  jmp     loc_180005C84
0x180005ab0  mov     rax, [rsp+280h+hObject]
0x180005ab5  lea     rcx, ds:0[rax*4]
0x180005abd  test    rcx, rcx
0x180005ac0  jz      short loc_180005AD0
0x180005ac2  mov     [r15], rcx
0x180005ac5  mov     eax, [rcx]
0x180005ac7  inc     eax
0x180005ac9  mov     [rcx], eax
0x180005acb  jmp     loc_180005C5A
0x180005ad0  mov     rdx, r14; dwBytes
0x180005ad3  mov     qword ptr [r15], 0
0x180005ada  mov     ecx, 8; dwFlags
0x180005adf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005ae4  mov     r14, rax
0x180005ae7  test    rax, rax
0x180005aea  jnz     short loc_180005B11
0x180005aec  mov     rcx, [rbp+188h]; this
0x180005af3  lea     r8, aWil; "wil"
0x180005afa  mov     esi, 8007000Eh
0x180005aff  mov     edx, 14Bh; void *
0x180005b04  mov     r9d, esi; char *
0x180005b07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b0c  jmp     loc_180005BA3
0x180005b11  xorps   xmm0, xmm0
0x180005b14  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005b1a  test    r14b, 3
0x180005b1e  jnz     loc_180005CFF
0x180005b24  mov     r9, r14
0x180005b27  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180005b2c  shr     r9, 2; unsigned __int64
0x180005b30  lea     rcx, [rsp+280h+hObject]; this
0x180005b35  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005b3a  mov     esi, eax
0x180005b3c  test    eax, eax
0x180005b3e  jns     loc_180005BEA
0x180005b44  mov     rcx, [rbp+188h]; this
0x180005b4b  lea     r8, aWil; "wil"
0x180005b52  mov     r9d, eax; char *
0x180005b55  mov     edx, 14Eh; void *
0x180005b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b5f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005b64  test    rcx, rcx
0x180005b67  jz      short loc_180005B77
0x180005b69  call    cs:__imp_CloseHandle
0x180005b6f  test    eax, eax
0x180005b71  jz      loc_180005D05
0x180005b77  mov     rcx, [rsp+280h+hObject]; hObject
0x180005b7c  test    rcx, rcx
0x180005b7f  jz      short loc_180005B8F
0x180005b81  call    cs:__imp_CloseHandle
0x180005b87  test    eax, eax
0x180005b89  jz      loc_180005D17
0x180005b8f  call    cs:__imp_GetProcessHeap
0x180005b95  mov     r8, r14; lpMem
0x180005b98  xor     edx, edx; dwFlags
0x180005b9a  mov     rcx, rax; hHeap
0x180005b9d  call    cs:__imp_HeapFree
0x180005ba3  mov     rcx, [rbp+188h]; this
0x180005baa  lea     r8, aWil; "wil"
0x180005bb1  mov     r9d, esi; char *
0x180005bb4  mov     edx, 137h; void *
0x180005bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bbe  test    rdi, rdi
0x180005bc1  jz      short loc_180005BD4
0x180005bc3  mov     rcx, rdi; hMutex
0x180005bc6  call    cs:__imp_ReleaseMutex
0x180005bcc  test    eax, eax
0x180005bce  jz      loc_180005D29
0x180005bd4  mov     rcx, rbx; hObject
0x180005bd7  call    cs:__imp_CloseHandle
0x180005bdd  test    eax, eax
0x180005bdf  jz      loc_180005CBC
0x180005be5  jmp     loc_180005AA9
0x180005bea  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005bef  lea     rcx, [r14+28h]; void *
0x180005bf3  mov     dword ptr [r14], 1
0x180005bfa  xor     edx, edx; Val
0x180005bfc  mov     [r14+8], rbx
0x180005c00  mov     r8d, 108h; Size
0x180005c06  movdqu  xmmword ptr [r14+10h], xmm0
0x180005c0c  call    memset_0
0x180005c11  xor     eax, eax
0x180005c13  lea     rcx, [r14+28h]; this
0x180005c17  mov     [r14+20h], rax
0x180005c1b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005c20  lea     rbx, [r14+0E8h]
0x180005c27  xor     r8d, r8d; Flags
0x180005c2a  mov     rcx, rbx; lpCriticalSection
0x180005c2d  xor     edx, edx; dwSpinCount
0x180005c2f  call    cs:__imp_InitializeCriticalSectionEx
0x180005c35  mov     qword ptr [rbx+28h], 0
0x180005c3d  mov     qword ptr [rbx+30h], 0
0x180005c45  mov     qword ptr [rbx+38h], 0
0x180005c4d  mov     qword ptr [rbx+40h], 0
0x180005c55  xor     ebx, ebx
0x180005c57  mov     [r15], r14
0x180005c5a  test    rdi, rdi
0x180005c5d  jz      short loc_180005C70
0x180005c5f  mov     rcx, rdi; hMutex
0x180005c62  call    cs:__imp_ReleaseMutex
0x180005c68  test    eax, eax
0x180005c6a  jz      loc_180005D3B
0x180005c70  test    rbx, rbx
0x180005c73  jz      short loc_180005C82
0x180005c75  mov     rcx, rbx; hObject
0x180005c78  call    cs:__imp_CloseHandle
0x180005c7e  test    eax, eax
0x180005c80  jz      short loc_180005CAA
0x180005c82  xor     eax, eax
0x180005c84  mov     rcx, [rbp+180h+var_30]
0x180005c8b  xor     rcx, rsp; StackCookie
0x180005c8e  call    __security_check_cookie
0x180005c93  mov     rbx, [rsp+280h+arg_10]
0x180005c9b  add     rsp, 260h
0x180005ca2  pop     r15
0x180005ca4  pop     r14
0x180005ca6  pop     rdi
0x180005ca7  pop     rsi
0x180005ca8  pop     rbp
0x180005ca9  retn
0x180005caa  mov     rcx, [rbp+188h]; this
0x180005cb1  mov     edx, 0A0Bh; void *
0x180005cb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cbc  mov     rcx, [rbp+188h]; this
0x180005cc3  mov     edx, 0A0Bh; void *
0x180005cc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cce  mov     rcx, [rbp+188h]; this
0x180005cd5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005cdb  mov     rcx, [rbp+188h]; this
0x180005ce2  mov     edx, 0A15h; void *
0x180005ce7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ced  mov     rcx, [rbp+188h]; this
0x180005cf4  mov     edx, 0A0Bh; void *
0x180005cf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005d05  mov     rcx, [rbp+188h]; this
0x180005d0c  mov     edx, 0A0Bh; void *
0x180005d11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d17  mov     rcx, [rbp+188h]; this
0x180005d1e  mov     edx, 0A0Bh; void *
0x180005d23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d29  mov     rcx, [rbp+188h]; this
0x180005d30  mov     edx, 0A15h; void *
0x180005d35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d3b  mov     rcx, [rbp+188h]; this
0x180005d42  mov     edx, 0A15h; void *
0x180005d47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
