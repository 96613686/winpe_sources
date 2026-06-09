# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003497c`
- end: `0x180034d3f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `963`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180035030`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180033b68`
- `0x180034278`
- `0x18003497c`
- `0x180034d48`
- `0x180035284`
- `0x180035ba8`
- `0x180036888`
- `0x180037ea4`
- `0x180038998`
- `0x180038dfc`
- `0x1800396ec`
- `0x1800396fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800349f3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800349f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034a14`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034a14`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034c4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034c4e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180034c11`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180034c11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034b6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034b6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034b5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800349b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800349b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034c64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034c64`

## string_xrefs

- `0x180034c9d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034cb6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034cdc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034cf5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034d14`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034d2d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  const char *v18; // r9
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  unsigned int v23; // r8d
  _DWORD *v24; // r14
  unsigned int v25; // r8d
  int v26; // eax
  unsigned int v27; // r8d
  HANDLE ProcessHeap; // rax
  const char *v29; // r9
  const char *v30; // r9
  const char *v31; // r9
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36[0]);
  if ( 4 * v36[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_24;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v23, (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v36 = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v36,
          Name,
          v23,
          v21 >> 2);
  v15 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v27, (const char *)(unsigned int)v26, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v25, (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v29);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v30);
    return v15;
  }
  *((_QWORD *)v24 + 2) = v36[0];
  *((_QWORD *)v24 + 3) = v36[1];
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v36[0] = 0;
  v36[1] = 0;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  *a2 = v24;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v36);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v32);
  return 0;
}

```

## disassembly

```asm
0x18003497c  mov     [rsp-8+arg_10], rbx
0x180034981  push    rbp
0x180034982  push    rsi
0x180034983  push    rdi
0x180034984  push    r14
0x180034986  push    r15
0x180034988  lea     rbp, [rsp-160h]
0x180034990  sub     rsp, 260h
0x180034997  mov     rax, cs:__security_cookie
0x18003499e  xor     rax, rsp
0x1800349a1  mov     [rbp+180h+var_30], rax
0x1800349a8  mov     r15, rdx
0x1800349ab  mov     qword ptr [rdx], 0
0x1800349b2  mov     rbx, rcx
0x1800349b5  call    cs:__imp_GetCurrentProcessId
0x1800349bb  mov     r14d, 130h
0x1800349c1  mov     [rsp+280h+var_258], rbx
0x1800349c6  mov     r9d, eax
0x1800349c9  mov     [rsp+280h+var_260], r14d; int
0x1800349ce  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800349d5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800349da  lea     edx, [r14-2Ch]; unsigned __int64
0x1800349de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800349e3  mov     r9d, 1F0001h; dwDesiredAccess
0x1800349e9  lea     rdx, [rsp+280h+Name]; lpName
0x1800349ee  xor     r8d, r8d; dwFlags
0x1800349f1  xor     ecx, ecx; lpMutexAttributes
0x1800349f3  call    cs:__imp_CreateMutexExW
0x1800349f9  mov     rbx, rax
0x1800349fc  test    rax, rax
0x1800349ff  jnz     short loc_180034A0B
0x180034a01  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034a06  jmp     loc_180034C70
0x180034a0b  xor     r8d, r8d; bAlertable
0x180034a0e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180034a11  mov     rcx, rbx; hHandle
0x180034a14  call    cs:__imp_WaitForSingleObjectEx
0x180034a1a  cmp     eax, 102h
0x180034a1f  jz      short loc_180034A31
0x180034a21  test    eax, 0FFFFFF7Fh
0x180034a26  jnz     loc_180034CC8
0x180034a2c  mov     rdi, rbx
0x180034a2f  jmp     short loc_180034A33
0x180034a31  xor     edi, edi
0x180034a33  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180034a38  mov     [rsp+280h+var_250], 0
0x180034a41  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180034a46  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180034a4b  mov     esi, eax
0x180034a4d  test    eax, eax
0x180034a4f  jns     short loc_180034ABB
0x180034a51  mov     rcx, [rbp+188h]; this
0x180034a58  mov     r9d, eax; char *
0x180034a5b  mov     edx, 66h ; 'f'; void *
0x180034a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a65  mov     rcx, [rbp+188h]; this
0x180034a6c  mov     r9d, esi; char *
0x180034a6f  mov     edx, 6Fh ; 'o'; void *
0x180034a74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a79  mov     rcx, [rbp+188h]; this
0x180034a80  mov     r9d, esi; char *
0x180034a83  mov     edx, 12Eh; void *
0x180034a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034a8d  test    rdi, rdi
0x180034a90  jz      short loc_180034AA3
0x180034a92  mov     rcx, rdi; hMutex
0x180034a95  call    cs:__imp_ReleaseMutex
0x180034a9b  test    eax, eax
0x180034a9d  jz      loc_180034CD5
0x180034aa3  mov     rcx, rbx; hObject
0x180034aa6  call    cs:__imp_CloseHandle
0x180034aac  test    eax, eax
0x180034aae  jz      loc_180034CEE
0x180034ab4  mov     eax, esi
0x180034ab6  jmp     loc_180034C70
0x180034abb  mov     rax, [rsp+280h+var_250]
0x180034ac0  lea     rcx, ds:0[rax*4]
0x180034ac8  test    rcx, rcx
0x180034acb  jz      short loc_180034ADB
0x180034acd  mov     [r15], rcx
0x180034ad0  mov     eax, [rcx]
0x180034ad2  inc     eax
0x180034ad4  mov     [rcx], eax
0x180034ad6  jmp     loc_180034C46
0x180034adb  mov     rdx, r14; dwBytes
0x180034ade  mov     qword ptr [r15], 0
0x180034ae5  mov     ecx, 8; dwFlags
0x180034aea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180034aef  mov     r14, rax
0x180034af2  test    rax, rax
0x180034af5  jnz     short loc_180034B12
0x180034af7  mov     rcx, [rbp+188h]; this
0x180034afe  mov     esi, 8007000Eh
0x180034b03  mov     r9d, esi; char *
0x180034b06  mov     edx, 14Bh; void *
0x180034b0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034b10  jmp     short loc_180034B73
0x180034b12  xorps   xmm0, xmm0
0x180034b15  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180034b1b  test    r14b, 3
0x180034b1f  jnz     loc_180034D07
0x180034b25  mov     r9, r14
0x180034b28  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180034b2d  shr     r9, 2; unsigned __int64
0x180034b31  lea     rcx, [rsp+280h+var_250]; this
0x180034b36  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180034b3b  mov     esi, eax
0x180034b3d  test    eax, eax
0x180034b3f  jns     short loc_180034BB3
0x180034b41  mov     rcx, [rbp+188h]; this
0x180034b48  mov     r9d, eax; char *
0x180034b4b  mov     edx, 14Eh; void *
0x180034b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034b55  lea     rcx, [rsp+280h+var_250]; this
0x180034b5a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180034b5f  call    cs:__imp_GetProcessHeap
0x180034b65  mov     r8, r14; lpMem
0x180034b68  xor     edx, edx; dwFlags
0x180034b6a  mov     rcx, rax; hHeap
0x180034b6d  call    cs:__imp_HeapFree
0x180034b73  mov     rcx, [rbp+188h]; this
0x180034b7a  mov     r9d, esi; char *
0x180034b7d  mov     edx, 137h; void *
0x180034b82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034b87  test    rdi, rdi
0x180034b8a  jz      short loc_180034B9D
0x180034b8c  mov     rcx, rdi; hMutex
0x180034b8f  call    cs:__imp_ReleaseMutex
0x180034b95  test    eax, eax
0x180034b97  jz      loc_180034D0D
0x180034b9d  mov     rcx, rbx; hObject
0x180034ba0  call    cs:__imp_CloseHandle
0x180034ba6  test    eax, eax
0x180034ba8  jz      loc_180034CAF
0x180034bae  jmp     loc_180034AB4
0x180034bb3  mov     rax, [rsp+280h+var_250]
0x180034bb8  lea     rcx, [r14+28h]; void *
0x180034bbc  mov     [r14+10h], rax
0x180034bc0  xor     edx, edx; Val
0x180034bc2  mov     rax, [rsp+280h+var_250+8]
0x180034bc7  mov     r8d, 108h; Size
0x180034bcd  mov     [r14+18h], rax
0x180034bd1  mov     dword ptr [r14], 1
0x180034bd8  mov     [r14+8], rbx
0x180034bdc  mov     [rsp+280h+var_250], 0
0x180034be5  mov     [rsp+280h+var_250+8], 0
0x180034bee  call    memset_0
0x180034bf3  xor     eax, eax
0x180034bf5  lea     rcx, [r14+28h]; this
0x180034bf9  mov     [r14+20h], rax
0x180034bfd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180034c02  lea     rbx, [r14+0E8h]
0x180034c09  xor     r8d, r8d; Flags
0x180034c0c  mov     rcx, rbx; lpCriticalSection
0x180034c0f  xor     edx, edx; dwSpinCount
0x180034c11  call    cs:__imp_InitializeCriticalSectionEx
0x180034c17  mov     qword ptr [rbx+28h], 0
0x180034c1f  lea     rcx, [rsp+280h+var_250]; this
0x180034c24  mov     qword ptr [rbx+30h], 0
0x180034c2c  mov     qword ptr [rbx+38h], 0
0x180034c34  mov     qword ptr [rbx+40h], 0
0x180034c3c  mov     [r15], r14
0x180034c3f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180034c44  xor     ebx, ebx
0x180034c46  test    rdi, rdi
0x180034c49  jz      short loc_180034C5C
0x180034c4b  mov     rcx, rdi; hMutex
0x180034c4e  call    cs:__imp_ReleaseMutex
0x180034c54  test    eax, eax
0x180034c56  jz      loc_180034D26
0x180034c5c  test    rbx, rbx
0x180034c5f  jz      short loc_180034C6E
0x180034c61  mov     rcx, rbx; hObject
0x180034c64  call    cs:__imp_CloseHandle
0x180034c6a  test    eax, eax
0x180034c6c  jz      short loc_180034C96
0x180034c6e  xor     eax, eax
0x180034c70  mov     rcx, [rbp+180h+var_30]
0x180034c77  xor     rcx, rsp; StackCookie
0x180034c7a  call    __security_check_cookie
0x180034c7f  mov     rbx, [rsp+280h+arg_10]
0x180034c87  add     rsp, 260h
0x180034c8e  pop     r15
0x180034c90  pop     r14
0x180034c92  pop     rdi
0x180034c93  pop     rsi
0x180034c94  pop     rbp
0x180034c95  retn
0x180034c96  mov     rcx, [rbp+188h]; this
0x180034c9d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034ca4  mov     edx, 0A0Bh; void *
0x180034ca9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034caf  mov     rcx, [rbp+188h]; this
0x180034cb6  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034cbd  mov     edx, 0A0Bh; void *
0x180034cc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034cc8  mov     rcx, [rbp+188h]; this
0x180034ccf  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180034cd5  mov     rcx, [rbp+188h]; this
0x180034cdc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034ce3  mov     edx, 0A15h; void *
0x180034ce8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034cee  mov     rcx, [rbp+188h]; this
0x180034cf5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034cfc  mov     edx, 0A0Bh; void *
0x180034d01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034d07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180034d0d  mov     rcx, [rbp+188h]; this
0x180034d14  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034d1b  mov     edx, 0A15h; void *
0x180034d20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034d26  mov     rcx, [rbp+188h]; this
0x180034d2d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034d34  mov     edx, 0A15h; void *
0x180034d39  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
