# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011854`
- end: `0x180011c54`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18001b524`

## callees

- `0x180002280`
- `0x180002f34`
- `0x1800058b4`
- `0x180005eb8`
- `0x1800060ec`
- `0x1800066b0`
- `0x180007344`
- `0x180007824`
- `0x180008110`
- `0x1800081ec`
- `0x1800086d4`
- `0x18001109c`
- `0x180011854`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800118f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800118f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011998`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011ab5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011b86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011998`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011ab5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011b86`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011b43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011b43`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800118d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800118d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011a86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001188d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001188d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ba2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011acc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ba2`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v36[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v36 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v36[0];
  *((_QWORD *)v22 + 3) = v36[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180011854  mov     [rsp-8+arg_10], rbx
0x180011859  push    rbp
0x18001185a  push    rsi
0x18001185b  push    rdi
0x18001185c  push    r14
0x18001185e  push    r15
0x180011860  lea     rbp, [rsp-160h]
0x180011868  sub     rsp, 260h
0x18001186f  mov     rax, cs:__security_cookie
0x180011876  xor     rax, rsp
0x180011879  mov     [rbp+180h+var_30], rax
0x180011880  mov     r15, rdx
0x180011883  mov     qword ptr [rdx], 0
0x18001188a  mov     rbx, rcx
0x18001188d  call    cs:__imp_GetCurrentProcessId
0x180011894  nop     dword ptr [rax+rax+00h]
0x180011899  mov     r14d, 130h
0x18001189f  mov     [rsp+280h+var_258], rbx
0x1800118a4  mov     r9d, eax
0x1800118a7  mov     [rsp+280h+var_260], r14d; int
0x1800118ac  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800118b3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800118b8  lea     edx, [r14-2Ch]; unsigned __int64
0x1800118bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800118c1  mov     r9d, 1F0001h; dwDesiredAccess
0x1800118c7  lea     rdx, [rsp+280h+Name]; lpName
0x1800118cc  xor     r8d, r8d; dwFlags
0x1800118cf  xor     ecx, ecx; lpMutexAttributes
0x1800118d1  call    cs:__imp_CreateMutexExW
0x1800118d8  nop     dword ptr [rax+rax+00h]
0x1800118dd  mov     rbx, rax
0x1800118e0  test    rax, rax
0x1800118e3  jnz     short loc_1800118EF
0x1800118e5  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800118ea  jmp     loc_180011BB4
0x1800118ef  xor     r8d, r8d; bAlertable
0x1800118f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800118f5  mov     rcx, rbx; hHandle
0x1800118f8  call    cs:__imp_WaitForSingleObjectEx
0x1800118ff  nop     dword ptr [rax+rax+00h]
0x180011904  cmp     eax, 102h
0x180011909  jz      short loc_18001191B
0x18001190b  test    eax, 0FFFFFF7Fh
0x180011910  jnz     loc_180011BFF
0x180011916  mov     rdi, rbx
0x180011919  jmp     short loc_18001191D
0x18001191b  xor     edi, edi
0x18001191d  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180011922  mov     [rsp+280h+var_250], 0
0x18001192b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011930  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011935  mov     esi, eax
0x180011937  test    eax, eax
0x180011939  jns     loc_1800119CA
0x18001193f  mov     rcx, [rbp+188h]; this
0x180011946  lea     r8, aWil; "wil"
0x18001194d  mov     r9d, eax; char *
0x180011950  mov     edx, 66h ; 'f'; void *
0x180011955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001195a  mov     rcx, [rbp+188h]; this
0x180011961  lea     r8, aWil; "wil"
0x180011968  mov     r9d, esi; char *
0x18001196b  mov     edx, 6Fh ; 'o'; void *
0x180011970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011975  mov     rcx, [rbp+188h]; this
0x18001197c  lea     r8, aWil; "wil"
0x180011983  mov     r9d, esi; char *
0x180011986  mov     edx, 12Eh; void *
0x18001198b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011990  test    rdi, rdi
0x180011993  jz      short loc_1800119AC
0x180011995  mov     rcx, rdi; hMutex
0x180011998  call    cs:__imp_ReleaseMutex
0x18001199f  nop     dword ptr [rax+rax+00h]
0x1800119a4  test    eax, eax
0x1800119a6  jz      loc_180011C0C
0x1800119ac  mov     rcx, rbx; hObject
0x1800119af  call    cs:__imp_CloseHandle
0x1800119b6  nop     dword ptr [rax+rax+00h]
0x1800119bb  test    eax, eax
0x1800119bd  jz      loc_180011C1E
0x1800119c3  mov     eax, esi
0x1800119c5  jmp     loc_180011BB4
0x1800119ca  mov     rax, [rsp+280h+var_250]
0x1800119cf  lea     rcx, ds:0[rax*4]
0x1800119d7  test    rcx, rcx
0x1800119da  jz      short loc_1800119EA
0x1800119dc  mov     [r15], rcx
0x1800119df  mov     eax, [rcx]
0x1800119e1  inc     eax
0x1800119e3  mov     [rcx], eax
0x1800119e5  jmp     loc_180011B7E
0x1800119ea  mov     rdx, r14; dwBytes
0x1800119ed  mov     qword ptr [r15], 0
0x1800119f4  mov     ecx, 8; dwFlags
0x1800119f9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800119fe  mov     r14, rax
0x180011a01  test    rax, rax
0x180011a04  jnz     short loc_180011A28
0x180011a06  mov     rcx, [rbp+188h]; this
0x180011a0d  lea     r8, aWil; "wil"
0x180011a14  mov     esi, 8007000Eh
0x180011a19  mov     edx, 14Bh; void *
0x180011a1e  mov     r9d, esi; char *
0x180011a21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a26  jmp     short loc_180011A92
0x180011a28  xorps   xmm0, xmm0
0x180011a2b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180011a30  mov     r8, r14; void *
0x180011a33  lea     rcx, [rsp+280h+var_250]; this
0x180011a38  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180011a3e  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180011a43  mov     esi, eax
0x180011a45  test    eax, eax
0x180011a47  jns     loc_180011AE5
0x180011a4d  mov     rcx, [rbp+188h]; this
0x180011a54  lea     r8, aWil; "wil"
0x180011a5b  mov     r9d, eax; char *
0x180011a5e  mov     edx, 14Eh; void *
0x180011a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a68  lea     rcx, [rsp+280h+var_250]; this
0x180011a6d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011a72  call    cs:__imp_GetProcessHeap
0x180011a79  nop     dword ptr [rax+rax+00h]
0x180011a7e  mov     r8, r14; lpMem
0x180011a81  xor     edx, edx; dwFlags
0x180011a83  mov     rcx, rax; hHeap
0x180011a86  call    cs:__imp_HeapFree
0x180011a8d  nop     dword ptr [rax+rax+00h]
0x180011a92  mov     rcx, [rbp+188h]; this
0x180011a99  lea     r8, aWil; "wil"
0x180011aa0  mov     r9d, esi; char *
0x180011aa3  mov     edx, 137h; void *
0x180011aa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011aad  test    rdi, rdi
0x180011ab0  jz      short loc_180011AC9
0x180011ab2  mov     rcx, rdi; hMutex
0x180011ab5  call    cs:__imp_ReleaseMutex
0x180011abc  nop     dword ptr [rax+rax+00h]
0x180011ac1  test    eax, eax
0x180011ac3  jz      loc_180011C30
0x180011ac9  mov     rcx, rbx; hObject
0x180011acc  call    cs:__imp_CloseHandle
0x180011ad3  nop     dword ptr [rax+rax+00h]
0x180011ad8  test    eax, eax
0x180011ada  jz      loc_180011BED
0x180011ae0  jmp     loc_1800119C3
0x180011ae5  mov     rax, [rsp+280h+var_250]
0x180011aea  lea     rcx, [r14+28h]; void *
0x180011aee  mov     [r14+10h], rax
0x180011af2  xor     edx, edx; Val
0x180011af4  mov     rax, [rsp+280h+var_250+8]
0x180011af9  mov     r8d, 108h; Size
0x180011aff  mov     [r14+18h], rax
0x180011b03  mov     dword ptr [r14], 1
0x180011b0a  mov     [r14+8], rbx
0x180011b0e  mov     [rsp+280h+var_250], 0
0x180011b17  mov     [rsp+280h+var_250+8], 0
0x180011b20  call    memset_0
0x180011b25  xor     eax, eax
0x180011b27  lea     rcx, [r14+28h]; this
0x180011b2b  mov     [r14+20h], rax
0x180011b2f  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011b34  lea     rbx, [r14+0E8h]
0x180011b3b  xor     r8d, r8d; Flags
0x180011b3e  mov     rcx, rbx; lpCriticalSection
0x180011b41  xor     edx, edx; dwSpinCount
0x180011b43  call    cs:__imp_InitializeCriticalSectionEx
0x180011b4a  nop     dword ptr [rax+rax+00h]
0x180011b4f  mov     qword ptr [rbx+28h], 0
0x180011b57  lea     rcx, [rsp+280h+var_250]; this
0x180011b5c  mov     qword ptr [rbx+30h], 0
0x180011b64  mov     qword ptr [rbx+38h], 0
0x180011b6c  mov     qword ptr [rbx+40h], 0
0x180011b74  mov     [r15], r14
0x180011b77  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011b7c  xor     ebx, ebx
0x180011b7e  test    rdi, rdi
0x180011b81  jz      short loc_180011B9A
0x180011b83  mov     rcx, rdi; hMutex
0x180011b86  call    cs:__imp_ReleaseMutex
0x180011b8d  nop     dword ptr [rax+rax+00h]
0x180011b92  test    eax, eax
0x180011b94  jz      loc_180011C42
0x180011b9a  test    rbx, rbx
0x180011b9d  jz      short loc_180011BB2
0x180011b9f  mov     rcx, rbx; hObject
0x180011ba2  call    cs:__imp_CloseHandle
0x180011ba9  nop     dword ptr [rax+rax+00h]
0x180011bae  test    eax, eax
0x180011bb0  jz      short loc_180011BDB
0x180011bb2  xor     eax, eax
0x180011bb4  mov     rcx, [rbp+180h+var_30]
0x180011bbb  xor     rcx, rsp; StackCookie
0x180011bbe  call    __security_check_cookie
0x180011bc3  mov     rbx, [rsp+280h+arg_10]
0x180011bcb  add     rsp, 260h
0x180011bd2  pop     r15
0x180011bd4  pop     r14
0x180011bd6  pop     rdi
0x180011bd7  pop     rsi
0x180011bd8  pop     rbp
0x180011bd9  retn
0x180011bdb  mov     rcx, [rbp+188h]; this
0x180011be2  mov     edx, 0A0Bh; void *
0x180011be7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011bed  mov     rcx, [rbp+188h]; this
0x180011bf4  mov     edx, 0A0Bh; void *
0x180011bf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011bff  mov     rcx, [rbp+188h]; this
0x180011c06  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180011c0c  mov     rcx, [rbp+188h]; this
0x180011c13  mov     edx, 0A15h; void *
0x180011c18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c1e  mov     rcx, [rbp+188h]; this
0x180011c25  mov     edx, 0A0Bh; void *
0x180011c2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c30  mov     rcx, [rbp+188h]; this
0x180011c37  mov     edx, 0A15h; void *
0x180011c3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c42  mov     rcx, [rbp+188h]; this
0x180011c49  mov     edx, 0A15h; void *
0x180011c4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
