# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000c5c4`
- end: `0x18000c9ba`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000c9c0`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x1800061b4`
- `0x180006348`
- `0x180007c38`
- `0x180007f54`
- `0x180008478`
- `0x180008c88`
- `0x180009044`
- `0x1800096a4`
- `0x180009d5c`
- `0x18000bdfc`
- `0x18000c5c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000c5fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c63b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000c63b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c82e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c8ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c6f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c82e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000c8ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c65c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000c65c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000c897`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000c897`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c83f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c83f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8e0`

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
  bool v9; // dl
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
  bool v23; // r8
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x18000c5c4  mov     [rsp-8+arg_10], rbx
0x18000c5c9  push    rbp
0x18000c5ca  push    rsi
0x18000c5cb  push    rdi
0x18000c5cc  push    r14
0x18000c5ce  push    r15
0x18000c5d0  lea     rbp, [rsp-160h]
0x18000c5d8  sub     rsp, 260h
0x18000c5df  mov     rax, cs:__security_cookie
0x18000c5e6  xor     rax, rsp
0x18000c5e9  mov     [rbp+180h+var_30], rax
0x18000c5f0  mov     r15, rdx
0x18000c5f3  mov     qword ptr [rdx], 0
0x18000c5fa  mov     rbx, rcx
0x18000c5fd  call    cs:__imp_GetCurrentProcessId
0x18000c603  mov     r14d, 130h
0x18000c609  mov     [rsp+280h+var_258], rbx
0x18000c60e  mov     r9d, eax
0x18000c611  mov     [rsp+280h+var_260], r14d; int
0x18000c616  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000c61d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c622  lea     edx, [r14-2Ch]; unsigned __int64
0x18000c626  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c62b  mov     r9d, 1F0001h; dwDesiredAccess
0x18000c631  lea     rdx, [rsp+280h+Name]; lpName
0x18000c636  xor     r8d, r8d; dwFlags
0x18000c639  xor     ecx, ecx; lpMutexAttributes
0x18000c63b  call    cs:__imp_CreateMutexExW
0x18000c641  mov     rbx, rax
0x18000c644  test    rax, rax
0x18000c647  jnz     short loc_18000C653
0x18000c649  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c64e  jmp     loc_18000C8EC
0x18000c653  xor     r8d, r8d; bAlertable
0x18000c656  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000c659  mov     rcx, rbx; hHandle
0x18000c65c  call    cs:__imp_WaitForSingleObjectEx
0x18000c662  cmp     eax, 102h
0x18000c667  jz      short loc_18000C679
0x18000c669  test    eax, 0FFFFFF7Fh
0x18000c66e  jnz     loc_18000C936
0x18000c674  mov     rdi, rbx
0x18000c677  jmp     short loc_18000C67B
0x18000c679  xor     edi, edi
0x18000c67b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000c680  mov     [rsp+280h+hObject], 0
0x18000c689  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c68e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000c693  mov     esi, eax
0x18000c695  test    eax, eax
0x18000c697  jns     short loc_18000C718
0x18000c699  mov     rcx, [rbp+188h]; this
0x18000c6a0  lea     r8, aWil; "wil"
0x18000c6a7  mov     r9d, eax; char *
0x18000c6aa  mov     edx, 66h ; 'f'; void *
0x18000c6af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6b4  mov     rcx, [rbp+188h]; this
0x18000c6bb  lea     r8, aWil; "wil"
0x18000c6c2  mov     r9d, esi; char *
0x18000c6c5  mov     edx, 6Fh ; 'o'; void *
0x18000c6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6cf  mov     rcx, [rbp+188h]; this
0x18000c6d6  lea     r8, aWil; "wil"
0x18000c6dd  mov     r9d, esi; char *
0x18000c6e0  mov     edx, 12Eh; void *
0x18000c6e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6ea  test    rdi, rdi
0x18000c6ed  jz      short loc_18000C700
0x18000c6ef  mov     rcx, rdi; hMutex
0x18000c6f2  call    cs:__imp_ReleaseMutex
0x18000c6f8  test    eax, eax
0x18000c6fa  jz      loc_18000C948
0x18000c700  mov     rcx, rbx; hObject
0x18000c703  call    cs:__imp_CloseHandle
0x18000c709  test    eax, eax
0x18000c70b  jz      loc_18000C95A
0x18000c711  mov     eax, esi
0x18000c713  jmp     loc_18000C8EC
0x18000c718  mov     rax, [rsp+280h+hObject]
0x18000c71d  lea     rcx, ds:0[rax*4]
0x18000c725  test    rcx, rcx
0x18000c728  jz      short loc_18000C738
0x18000c72a  mov     [r15], rcx
0x18000c72d  mov     eax, [rcx]
0x18000c72f  inc     eax
0x18000c731  mov     [rcx], eax
0x18000c733  jmp     loc_18000C8C2
0x18000c738  mov     rdx, r14; dwBytes
0x18000c73b  mov     qword ptr [r15], 0
0x18000c742  mov     ecx, 8; dwFlags
0x18000c747  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c74c  mov     r14, rax
0x18000c74f  test    rax, rax
0x18000c752  jnz     short loc_18000C779
0x18000c754  mov     rcx, [rbp+188h]; this
0x18000c75b  lea     r8, aWil; "wil"
0x18000c762  mov     esi, 8007000Eh
0x18000c767  mov     edx, 14Bh; void *
0x18000c76c  mov     r9d, esi; char *
0x18000c76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c774  jmp     loc_18000C80B
0x18000c779  xorps   xmm0, xmm0
0x18000c77c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000c782  test    r14b, 3
0x18000c786  jnz     loc_18000C96C
0x18000c78c  mov     r9, r14
0x18000c78f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000c794  shr     r9, 2; unsigned __int64
0x18000c798  lea     rcx, [rsp+280h+hObject]; this
0x18000c79d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000c7a2  mov     esi, eax
0x18000c7a4  test    eax, eax
0x18000c7a6  jns     loc_18000C852
0x18000c7ac  mov     rcx, [rbp+188h]; this
0x18000c7b3  lea     r8, aWil; "wil"
0x18000c7ba  mov     r9d, eax; char *
0x18000c7bd  mov     edx, 14Eh; void *
0x18000c7c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7c7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000c7cc  test    rcx, rcx
0x18000c7cf  jz      short loc_18000C7DF
0x18000c7d1  call    cs:__imp_CloseHandle
0x18000c7d7  test    eax, eax
0x18000c7d9  jz      loc_18000C972
0x18000c7df  mov     rcx, [rsp+280h+hObject]; hObject
0x18000c7e4  test    rcx, rcx
0x18000c7e7  jz      short loc_18000C7F7
0x18000c7e9  call    cs:__imp_CloseHandle
0x18000c7ef  test    eax, eax
0x18000c7f1  jz      loc_18000C984
0x18000c7f7  call    cs:__imp_GetProcessHeap
0x18000c7fd  mov     r8, r14; lpMem
0x18000c800  xor     edx, edx; dwFlags
0x18000c802  mov     rcx, rax; hHeap
0x18000c805  call    cs:__imp_HeapFree
0x18000c80b  mov     rcx, [rbp+188h]; this
0x18000c812  lea     r8, aWil; "wil"
0x18000c819  mov     r9d, esi; char *
0x18000c81c  mov     edx, 137h; void *
0x18000c821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c826  test    rdi, rdi
0x18000c829  jz      short loc_18000C83C
0x18000c82b  mov     rcx, rdi; hMutex
0x18000c82e  call    cs:__imp_ReleaseMutex
0x18000c834  test    eax, eax
0x18000c836  jz      loc_18000C996
0x18000c83c  mov     rcx, rbx; hObject
0x18000c83f  call    cs:__imp_CloseHandle
0x18000c845  test    eax, eax
0x18000c847  jz      loc_18000C924
0x18000c84d  jmp     loc_18000C711
0x18000c852  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000c857  lea     rcx, [r14+28h]; void *
0x18000c85b  mov     dword ptr [r14], 1
0x18000c862  xor     edx, edx; Val
0x18000c864  mov     [r14+8], rbx
0x18000c868  mov     r8d, 108h; Size
0x18000c86e  movdqu  xmmword ptr [r14+10h], xmm0
0x18000c874  call    memset_0
0x18000c879  xor     eax, eax
0x18000c87b  lea     rcx, [r14+28h]; this
0x18000c87f  mov     [r14+20h], rax
0x18000c883  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000c888  lea     rbx, [r14+0E8h]
0x18000c88f  xor     r8d, r8d; Flags
0x18000c892  mov     rcx, rbx; lpCriticalSection
0x18000c895  xor     edx, edx; dwSpinCount
0x18000c897  call    cs:__imp_InitializeCriticalSectionEx
0x18000c89d  mov     qword ptr [rbx+28h], 0
0x18000c8a5  mov     qword ptr [rbx+30h], 0
0x18000c8ad  mov     qword ptr [rbx+38h], 0
0x18000c8b5  mov     qword ptr [rbx+40h], 0
0x18000c8bd  xor     ebx, ebx
0x18000c8bf  mov     [r15], r14
0x18000c8c2  test    rdi, rdi
0x18000c8c5  jz      short loc_18000C8D8
0x18000c8c7  mov     rcx, rdi; hMutex
0x18000c8ca  call    cs:__imp_ReleaseMutex
0x18000c8d0  test    eax, eax
0x18000c8d2  jz      loc_18000C9A8
0x18000c8d8  test    rbx, rbx
0x18000c8db  jz      short loc_18000C8EA
0x18000c8dd  mov     rcx, rbx; hObject
0x18000c8e0  call    cs:__imp_CloseHandle
0x18000c8e6  test    eax, eax
0x18000c8e8  jz      short loc_18000C912
0x18000c8ea  xor     eax, eax
0x18000c8ec  mov     rcx, [rbp+180h+var_30]
0x18000c8f3  xor     rcx, rsp; StackCookie
0x18000c8f6  call    __security_check_cookie
0x18000c8fb  mov     rbx, [rsp+280h+arg_10]
0x18000c903  add     rsp, 260h
0x18000c90a  pop     r15
0x18000c90c  pop     r14
0x18000c90e  pop     rdi
0x18000c90f  pop     rsi
0x18000c910  pop     rbp
0x18000c911  retn
0x18000c912  mov     rcx, [rbp+188h]; this
0x18000c919  mov     edx, 0A0Bh; void *
0x18000c91e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c924  mov     rcx, [rbp+188h]; this
0x18000c92b  mov     edx, 0A0Bh; void *
0x18000c930  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c936  mov     rcx, [rbp+188h]; this
0x18000c93d  mov     edx, 0E01h; void *
0x18000c942  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000c948  mov     rcx, [rbp+188h]; this
0x18000c94f  mov     edx, 0A15h; void *
0x18000c954  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c95a  mov     rcx, [rbp+188h]; this
0x18000c961  mov     edx, 0A0Bh; void *
0x18000c966  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c96c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c972  mov     rcx, [rbp+188h]; this
0x18000c979  mov     edx, 0A0Bh; void *
0x18000c97e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c984  mov     rcx, [rbp+188h]; this
0x18000c98b  mov     edx, 0A0Bh; void *
0x18000c990  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c996  mov     rcx, [rbp+188h]; this
0x18000c99d  mov     edx, 0A15h; void *
0x18000c9a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c9a8  mov     rcx, [rbp+188h]; this
0x18000c9af  mov     edx, 0A15h; void *
0x18000c9b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
