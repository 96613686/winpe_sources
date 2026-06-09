# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007474`
- end: `0x1800078b3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1087`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008a9c`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x1800063a8`
- `0x180006b24`
- `0x180007474`
- `0x180008884`
- `0x180008c34`
- `0x180009768`
- `0x18000a8e4`
- `0x18000c294`
- `0x18000cc30`
- `0x18000d128`
- `0x18000e648`
- `0x18000ebb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800074fa`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800074fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007530`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007530`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800075d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800076ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800075d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800076ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800077af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000777e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000777e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800074ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800074ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000770d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000770d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077cb`

## string_xrefs

- `0x18000780b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007824`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000783d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007856`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000786f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007888`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800078a1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rdi
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rsi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // ebx
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  _DWORD *v18; // rax
  _DWORD *v19; // r14
  int v20; // eax
  HANDLE ProcessHeap; // rax
  const char *v22; // r9
  const char *v23; // r9
  HANDLE v24; // rax
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle[0] = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    hHandle,
    Mutex);
  v6 = hHandle[0];
  if ( !hHandle[0] )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle[0], 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hHandle[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hHandle,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v27);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v28);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * (__int64)hHandle[0]);
  if ( 4 * (__int64)hHandle[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v19 = v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)hHandle = 0;
  v20 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)hHandle, Name, v18);
  v14 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v20, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v29);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return v14;
  }
  *((HANDLE *)v19 + 2) = hHandle[0];
  v24 = hHandle[1];
  *((_QWORD *)v19 + 1) = v6;
  v6 = 0;
  *((_QWORD *)v19 + 3) = v24;
  *v19 = 1;
  hHandle[0] = 0;
  hHandle[1] = 0;
  memset_0(v19 + 10, 0, 0x108u);
  *((_QWORD *)v19 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v19 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v19 + 58), 0, 0);
  *((_QWORD *)v19 + 34) = 0;
  *((_QWORD *)v19 + 35) = 0;
  *((_QWORD *)v19 + 36) = 0;
  *((_QWORD *)v19 + 37) = 0;
  *a2 = v19;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return 0;
}

```

## disassembly

```asm
0x180007474  mov     [rsp-8+arg_10], rbx
0x180007479  push    rbp
0x18000747a  push    rsi
0x18000747b  push    rdi
0x18000747c  push    r14
0x18000747e  push    r15
0x180007480  lea     rbp, [rsp-160h]
0x180007488  sub     rsp, 260h
0x18000748f  mov     rax, cs:__security_cookie
0x180007496  xor     rax, rsp
0x180007499  mov     [rbp+180h+var_30], rax
0x1800074a0  mov     r15, rdx
0x1800074a3  mov     qword ptr [rdx], 0
0x1800074aa  mov     rbx, rcx
0x1800074ad  call    cs:__imp_GetCurrentProcessId
0x1800074b4  nop     dword ptr [rax+rax+00h]
0x1800074b9  mov     r14d, 130h
0x1800074bf  mov     [rsp+280h+var_258], rbx
0x1800074c4  mov     r9d, eax
0x1800074c7  mov     [rsp+280h+var_260], r14d; int
0x1800074cc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800074d3  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800074d8  lea     edx, [r14-2Ch]; unsigned __int64
0x1800074dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074e1  mov     r9d, 1F0001h; dwDesiredAccess
0x1800074e7  mov     [rsp+280h+hHandle], 0
0x1800074f0  xor     r8d, r8d; dwFlags
0x1800074f3  lea     rdx, [rsp+280h+Name]; lpName
0x1800074f8  xor     ecx, ecx; lpMutexAttributes
0x1800074fa  call    cs:__imp_CreateMutexExW
0x180007501  nop     dword ptr [rax+rax+00h]
0x180007506  mov     rdx, rax
0x180007509  lea     rcx, [rsp+280h+hHandle]
0x18000750e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007513  mov     rdi, [rsp+280h+hHandle]
0x180007518  test    rdi, rdi
0x18000751b  jnz     short loc_180007527
0x18000751d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007522  jmp     loc_1800077DD
0x180007527  xor     r8d, r8d; bAlertable
0x18000752a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000752d  mov     rcx, rdi; hHandle
0x180007530  call    cs:__imp_WaitForSingleObjectEx
0x180007537  nop     dword ptr [rax+rax+00h]
0x18000753c  cmp     eax, 102h
0x180007541  jz      short loc_180007553
0x180007543  test    eax, 0FFFFFF7Fh
0x180007548  jnz     loc_180007836
0x18000754e  mov     rsi, rdi
0x180007551  jmp     short loc_180007555
0x180007553  xor     esi, esi
0x180007555  lea     r8, [rsp+280h+hHandle]; unsigned __int64 *
0x18000755a  mov     [rsp+280h+hHandle], 0
0x180007563  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007568  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000756d  mov     ebx, eax
0x18000756f  test    eax, eax
0x180007571  jns     loc_180007602
0x180007577  mov     rcx, [rbp+188h]; this
0x18000757e  lea     r8, aWil; "wil"
0x180007585  mov     r9d, eax; char *
0x180007588  mov     edx, 66h ; 'f'; void *
0x18000758d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007592  mov     rcx, [rbp+188h]; this
0x180007599  lea     r8, aWil; "wil"
0x1800075a0  mov     r9d, ebx; char *
0x1800075a3  mov     edx, 6Fh ; 'o'; void *
0x1800075a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075ad  mov     rcx, [rbp+188h]; this
0x1800075b4  lea     r8, aWil; "wil"
0x1800075bb  mov     r9d, ebx; char *
0x1800075be  mov     edx, 12Eh; void *
0x1800075c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075c8  test    rsi, rsi
0x1800075cb  jz      short loc_1800075E4
0x1800075cd  mov     rcx, rsi; hMutex
0x1800075d0  call    cs:__imp_ReleaseMutex
0x1800075d7  nop     dword ptr [rax+rax+00h]
0x1800075dc  test    eax, eax
0x1800075de  jz      loc_18000784F
0x1800075e4  mov     rcx, rdi; hObject
0x1800075e7  call    cs:__imp_CloseHandle
0x1800075ee  nop     dword ptr [rax+rax+00h]
0x1800075f3  test    eax, eax
0x1800075f5  jz      loc_180007868
0x1800075fb  mov     eax, ebx
0x1800075fd  jmp     loc_1800077DD
0x180007602  mov     rax, [rsp+280h+hHandle]
0x180007607  lea     rcx, ds:0[rax*4]
0x18000760f  test    rcx, rcx
0x180007612  jz      short loc_180007622
0x180007614  mov     [r15], rcx
0x180007617  mov     eax, [rcx]
0x180007619  inc     eax
0x18000761b  mov     [rcx], eax
0x18000761d  jmp     loc_1800077A7
0x180007622  mov     rdx, r14; dwBytes
0x180007625  mov     qword ptr [r15], 0
0x18000762c  mov     ecx, 8; dwFlags
0x180007631  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007636  mov     r14, rax
0x180007639  test    rax, rax
0x18000763c  jnz     short loc_180007660
0x18000763e  mov     rcx, [rbp+188h]; this
0x180007645  lea     r8, aWil; "wil"
0x18000764c  mov     ebx, 8007000Eh
0x180007651  mov     edx, 14Bh; void *
0x180007656  mov     r9d, ebx; char *
0x180007659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000765e  jmp     short loc_1800076CA
0x180007660  xorps   xmm0, xmm0
0x180007663  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007668  mov     r8, r14; void *
0x18000766b  lea     rcx, [rsp+280h+hHandle]; this
0x180007670  movdqu  xmmword ptr [rsp+280h+hHandle], xmm0
0x180007676  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000767b  mov     ebx, eax
0x18000767d  test    eax, eax
0x18000767f  jns     loc_180007726
0x180007685  mov     rcx, [rbp+188h]; this
0x18000768c  lea     r8, aWil; "wil"
0x180007693  mov     r9d, eax; char *
0x180007696  mov     edx, 14Eh; void *
0x18000769b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076a0  lea     rcx, [rsp+280h+hHandle]; this
0x1800076a5  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800076aa  call    cs:__imp_GetProcessHeap
0x1800076b1  nop     dword ptr [rax+rax+00h]
0x1800076b6  mov     r8, r14; lpMem
0x1800076b9  xor     edx, edx; dwFlags
0x1800076bb  mov     rcx, rax; hHeap
0x1800076be  call    cs:__imp_HeapFree
0x1800076c5  nop     dword ptr [rax+rax+00h]
0x1800076ca  mov     rcx, [rbp+188h]; this
0x1800076d1  lea     r8, aWil; "wil"
0x1800076d8  mov     r9d, ebx; char *
0x1800076db  mov     edx, 137h; void *
0x1800076e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076e5  test    rsi, rsi
0x1800076e8  jz      short loc_180007701
0x1800076ea  mov     rcx, rsi; hMutex
0x1800076ed  call    cs:__imp_ReleaseMutex
0x1800076f4  nop     dword ptr [rax+rax+00h]
0x1800076f9  test    eax, eax
0x1800076fb  jz      loc_180007881
0x180007701  test    rdi, rdi
0x180007704  jz      loc_1800075FB
0x18000770a  mov     rcx, rdi; hObject
0x18000770d  call    cs:__imp_CloseHandle
0x180007714  nop     dword ptr [rax+rax+00h]
0x180007719  test    eax, eax
0x18000771b  jz      loc_18000781D
0x180007721  jmp     loc_1800075FB
0x180007726  mov     rax, [rsp+280h+hHandle]
0x18000772b  lea     rcx, [r14+28h]; void *
0x18000772f  mov     [r14+10h], rax
0x180007733  xor     edx, edx; Val
0x180007735  mov     rax, [rsp+280h+hHandle+8]
0x18000773a  mov     r8d, 108h; Size
0x180007740  mov     [r14+8], rdi
0x180007744  xor     edi, edi
0x180007746  mov     [r14+18h], rax
0x18000774a  mov     dword ptr [r14], 1
0x180007751  mov     [rsp+280h+hHandle], rdi
0x180007756  mov     [rsp+280h+hHandle+8], rdi
0x18000775b  call    memset_0
0x180007760  xor     eax, eax
0x180007762  lea     rcx, [r14+28h]; this
0x180007766  mov     [r14+20h], rax
0x18000776a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000776f  lea     rbx, [r14+0E8h]
0x180007776  xor     r8d, r8d; Flags
0x180007779  mov     rcx, rbx; lpCriticalSection
0x18000777c  xor     edx, edx; dwSpinCount
0x18000777e  call    cs:__imp_InitializeCriticalSectionEx
0x180007785  nop     dword ptr [rax+rax+00h]
0x18000778a  mov     [rbx+28h], rdi
0x18000778e  lea     rcx, [rsp+280h+hHandle]; this
0x180007793  mov     [rbx+30h], rdi
0x180007797  mov     [rbx+38h], rdi
0x18000779b  mov     [rbx+40h], rdi
0x18000779f  mov     [r15], r14
0x1800077a2  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800077a7  test    rsi, rsi
0x1800077aa  jz      short loc_1800077C3
0x1800077ac  mov     rcx, rsi; hMutex
0x1800077af  call    cs:__imp_ReleaseMutex
0x1800077b6  nop     dword ptr [rax+rax+00h]
0x1800077bb  test    eax, eax
0x1800077bd  jz      loc_18000789A
0x1800077c3  test    rdi, rdi
0x1800077c6  jz      short loc_1800077DB
0x1800077c8  mov     rcx, rdi; hObject
0x1800077cb  call    cs:__imp_CloseHandle
0x1800077d2  nop     dword ptr [rax+rax+00h]
0x1800077d7  test    eax, eax
0x1800077d9  jz      short loc_180007804
0x1800077db  xor     eax, eax
0x1800077dd  mov     rcx, [rbp+180h+var_30]
0x1800077e4  xor     rcx, rsp; StackCookie
0x1800077e7  call    __security_check_cookie
0x1800077ec  mov     rbx, [rsp+280h+arg_10]
0x1800077f4  add     rsp, 260h
0x1800077fb  pop     r15
0x1800077fd  pop     r14
0x1800077ff  pop     rdi
0x180007800  pop     rsi
0x180007801  pop     rbp
0x180007802  retn
0x180007804  mov     rcx, [rbp+188h]; this
0x18000780b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007812  mov     edx, 0A0Bh; void *
0x180007817  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000781d  mov     rcx, [rbp+188h]; this
0x180007824  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000782b  mov     edx, 0A0Bh; void *
0x180007830  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007836  mov     rcx, [rbp+188h]; this
0x18000783d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007844  mov     edx, 0E01h; void *
0x180007849  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000784f  mov     rcx, [rbp+188h]; this
0x180007856  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000785d  mov     edx, 0A15h; void *
0x180007862  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007868  mov     rcx, [rbp+188h]; this
0x18000786f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007876  mov     edx, 0A0Bh; void *
0x18000787b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007881  mov     rcx, [rbp+188h]; this
0x180007888  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000788f  mov     edx, 0A15h; void *
0x180007894  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000789a  mov     rcx, [rbp+188h]; this
0x1800078a1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800078a8  mov     edx, 0A15h; void *
0x1800078ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
