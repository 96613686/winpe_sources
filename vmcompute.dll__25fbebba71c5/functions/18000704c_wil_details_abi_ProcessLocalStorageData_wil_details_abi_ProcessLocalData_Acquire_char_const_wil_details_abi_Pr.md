# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000704c`
- end: `0x18000746c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1056`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180009d8c`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x180006b24`
- `0x18000704c`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800070d3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800070d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007109`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007109`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007368`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800071a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800072c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007299`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007299`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007384`

## string_xrefs

- `0x1800073c4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073dd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800073f6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000740f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007428`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007441`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000745a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  _QWORD *v18; // rax
  _QWORD *v19; // rsi
  unsigned int v20; // r14d
  int v21; // eax
  HANDLE ProcessHeap; // rax
  const char *v23; // r9
  const char *v24; // r9
  HANDLE v25; // rax
  HANDLE v26; // rax
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v30);
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
  v18 = wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v19 = v18;
  if ( v18 )
  {
    *(_OWORD *)hHandle = 0;
    v21 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)hHandle, Name, v18);
    v20 = v21;
    if ( v21 >= 0 )
    {
      v25 = hHandle[0];
      v19[1] = v6;
      v6 = 0;
      v19[2] = v25;
      v26 = hHandle[1];
      *(_DWORD *)v19 = 1;
      hHandle[0] = 0;
      v19[3] = v26;
      hHandle[1] = 0;
      memset_0((char *)v19 + 34, 0, 0x56u);
      *((_WORD *)v19 + 16) = 88;
      *((_DWORD *)v19 + 9) = 1;
      memset_0(v19 + 5, 0, 0x50u);
      *a2 = v19;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v27);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v21, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v19);
  }
  else
  {
    v20 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v20, v31);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v23);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v24);
  return v20;
}

```

## disassembly

```asm
0x18000704c  mov     [rsp-8+arg_10], rbx
0x180007051  push    rbp
0x180007052  push    rsi
0x180007053  push    rdi
0x180007054  push    r14
0x180007056  push    r15
0x180007058  lea     rbp, [rsp-160h]
0x180007060  sub     rsp, 260h
0x180007067  mov     rax, cs:__security_cookie
0x18000706e  xor     rax, rsp
0x180007071  mov     [rbp+180h+var_30], rax
0x180007078  mov     r15, rdx
0x18000707b  mov     qword ptr [rdx], 0
0x180007082  mov     rbx, rcx
0x180007085  call    cs:__imp_GetCurrentProcessId
0x18000708c  nop     dword ptr [rax+rax+00h]
0x180007091  mov     r14d, 78h ; 'x'
0x180007097  mov     [rsp+280h+var_258], rbx
0x18000709c  mov     r9d, eax
0x18000709f  mov     [rsp+280h+var_260], r14d; int
0x1800070a4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800070ab  mov     edx, 104h; unsigned __int64
0x1800070b0  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800070b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800070ba  mov     r9d, 1F0001h; dwDesiredAccess
0x1800070c0  mov     [rsp+280h+hHandle], 0
0x1800070c9  xor     r8d, r8d; dwFlags
0x1800070cc  lea     rdx, [rsp+280h+Name]; lpName
0x1800070d1  xor     ecx, ecx; lpMutexAttributes
0x1800070d3  call    cs:__imp_CreateMutexExW
0x1800070da  nop     dword ptr [rax+rax+00h]
0x1800070df  mov     rdx, rax
0x1800070e2  lea     rcx, [rsp+280h+hHandle]
0x1800070e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800070ec  mov     rbx, [rsp+280h+hHandle]
0x1800070f1  test    rbx, rbx
0x1800070f4  jnz     short loc_180007100
0x1800070f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800070fb  jmp     loc_180007396
0x180007100  xor     r8d, r8d; bAlertable
0x180007103  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007106  mov     rcx, rbx; hHandle
0x180007109  call    cs:__imp_WaitForSingleObjectEx
0x180007110  nop     dword ptr [rax+rax+00h]
0x180007115  cmp     eax, 102h
0x18000711a  jz      short loc_18000712C
0x18000711c  test    eax, 0FFFFFF7Fh
0x180007121  jnz     loc_1800073D6
0x180007127  mov     rdi, rbx
0x18000712a  jmp     short loc_18000712E
0x18000712c  xor     edi, edi
0x18000712e  lea     r8, [rsp+280h+hHandle]; unsigned __int64 *
0x180007133  mov     [rsp+280h+hHandle], 0
0x18000713c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007141  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007146  mov     esi, eax
0x180007148  test    eax, eax
0x18000714a  jns     loc_1800071DB
0x180007150  mov     rcx, [rbp+188h]; this
0x180007157  lea     r8, aWil; "wil"
0x18000715e  mov     r9d, eax; char *
0x180007161  mov     edx, 66h ; 'f'; void *
0x180007166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000716b  mov     rcx, [rbp+188h]; this
0x180007172  lea     r8, aWil; "wil"
0x180007179  mov     r9d, esi; char *
0x18000717c  mov     edx, 6Fh ; 'o'; void *
0x180007181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007186  mov     rcx, [rbp+188h]; this
0x18000718d  lea     r8, aWil; "wil"
0x180007194  mov     r9d, esi; char *
0x180007197  mov     edx, 12Eh; void *
0x18000719c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071a1  test    rdi, rdi
0x1800071a4  jz      short loc_1800071BD
0x1800071a6  mov     rcx, rdi; hMutex
0x1800071a9  call    cs:__imp_ReleaseMutex
0x1800071b0  nop     dword ptr [rax+rax+00h]
0x1800071b5  test    eax, eax
0x1800071b7  jz      loc_1800073EF
0x1800071bd  mov     rcx, rbx; hObject
0x1800071c0  call    cs:__imp_CloseHandle
0x1800071c7  nop     dword ptr [rax+rax+00h]
0x1800071cc  test    eax, eax
0x1800071ce  jz      loc_180007408
0x1800071d4  mov     eax, esi
0x1800071d6  jmp     loc_180007396
0x1800071db  mov     rax, [rsp+280h+hHandle]
0x1800071e0  lea     rcx, ds:0[rax*4]
0x1800071e8  test    rcx, rcx
0x1800071eb  jz      short loc_1800071FB
0x1800071ed  mov     [r15], rcx
0x1800071f0  mov     eax, [rcx]
0x1800071f2  inc     eax
0x1800071f4  mov     [rcx], eax
0x1800071f6  jmp     loc_180007360
0x1800071fb  mov     rdx, r14; dwBytes
0x1800071fe  mov     qword ptr [r15], 0
0x180007205  mov     ecx, 8; dwFlags
0x18000720a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000720f  mov     rsi, rax
0x180007212  test    rax, rax
0x180007215  jnz     short loc_18000723A
0x180007217  mov     rcx, [rbp+188h]; this
0x18000721e  lea     r8, aWil; "wil"
0x180007225  mov     r14d, 8007000Eh
0x18000722b  mov     edx, 14Bh; void *
0x180007230  mov     r9d, r14d; char *
0x180007233  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007238  jmp     short loc_1800072A5
0x18000723a  xorps   xmm0, xmm0
0x18000723d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007242  mov     r8, rsi; void *
0x180007245  lea     rcx, [rsp+280h+hHandle]; this
0x18000724a  movdqu  xmmword ptr [rsp+280h+hHandle], xmm0
0x180007250  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180007255  mov     r14d, eax
0x180007258  test    eax, eax
0x18000725a  jns     loc_180007300
0x180007260  mov     rcx, [rbp+188h]; this
0x180007267  lea     r8, aWil; "wil"
0x18000726e  mov     r9d, eax; char *
0x180007271  mov     edx, 14Eh; void *
0x180007276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000727b  lea     rcx, [rsp+280h+hHandle]; this
0x180007280  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007285  call    cs:__imp_GetProcessHeap
0x18000728c  nop     dword ptr [rax+rax+00h]
0x180007291  mov     r8, rsi; lpMem
0x180007294  xor     edx, edx; dwFlags
0x180007296  mov     rcx, rax; hHeap
0x180007299  call    cs:__imp_HeapFree
0x1800072a0  nop     dword ptr [rax+rax+00h]
0x1800072a5  mov     rcx, [rbp+188h]; this
0x1800072ac  lea     r8, aWil; "wil"
0x1800072b3  mov     r9d, r14d; char *
0x1800072b6  mov     edx, 137h; void *
0x1800072bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072c0  test    rdi, rdi
0x1800072c3  jz      short loc_1800072DC
0x1800072c5  mov     rcx, rdi; hMutex
0x1800072c8  call    cs:__imp_ReleaseMutex
0x1800072cf  nop     dword ptr [rax+rax+00h]
0x1800072d4  test    eax, eax
0x1800072d6  jz      loc_180007421
0x1800072dc  test    rbx, rbx
0x1800072df  jz      short loc_1800072F8
0x1800072e1  mov     rcx, rbx; hObject
0x1800072e4  call    cs:__imp_CloseHandle
0x1800072eb  nop     dword ptr [rax+rax+00h]
0x1800072f0  test    eax, eax
0x1800072f2  jz      loc_18000743A
0x1800072f8  mov     eax, r14d
0x1800072fb  jmp     loc_180007396
0x180007300  mov     rax, [rsp+280h+hHandle]
0x180007305  lea     rcx, [rsi+22h]; void *
0x180007309  mov     [rsi+8], rbx
0x18000730d  xor     edx, edx; Val
0x18000730f  xor     ebx, ebx
0x180007311  mov     [rsi+10h], rax
0x180007315  mov     rax, [rsp+280h+hHandle+8]
0x18000731a  mov     dword ptr [rsi], 1
0x180007320  mov     [rsp+280h+hHandle], rbx
0x180007325  lea     r8d, [rbx+56h]; Size
0x180007329  mov     [rsi+18h], rax
0x18000732d  mov     [rsp+280h+hHandle+8], rbx
0x180007332  call    memset_0
0x180007337  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000733d  lea     rcx, [rsi+28h]; void *
0x180007341  xor     edx, edx; Val
0x180007343  mov     dword ptr [rsi+24h], 1
0x18000734a  lea     r8d, [rbx+50h]; Size
0x18000734e  call    memset_0
0x180007353  lea     rcx, [rsp+280h+hHandle]; this
0x180007358  mov     [r15], rsi
0x18000735b  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007360  test    rdi, rdi
0x180007363  jz      short loc_18000737C
0x180007365  mov     rcx, rdi; hMutex
0x180007368  call    cs:__imp_ReleaseMutex
0x18000736f  nop     dword ptr [rax+rax+00h]
0x180007374  test    eax, eax
0x180007376  jz      loc_180007453
0x18000737c  test    rbx, rbx
0x18000737f  jz      short loc_180007394
0x180007381  mov     rcx, rbx; hObject
0x180007384  call    cs:__imp_CloseHandle
0x18000738b  nop     dword ptr [rax+rax+00h]
0x180007390  test    eax, eax
0x180007392  jz      short loc_1800073BD
0x180007394  xor     eax, eax
0x180007396  mov     rcx, [rbp+180h+var_30]
0x18000739d  xor     rcx, rsp; StackCookie
0x1800073a0  call    __security_check_cookie
0x1800073a5  mov     rbx, [rsp+280h+arg_10]
0x1800073ad  add     rsp, 260h
0x1800073b4  pop     r15
0x1800073b6  pop     r14
0x1800073b8  pop     rdi
0x1800073b9  pop     rsi
0x1800073ba  pop     rbp
0x1800073bb  retn
0x1800073bd  mov     rcx, [rbp+188h]; this
0x1800073c4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073cb  mov     edx, 0A0Bh; void *
0x1800073d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800073d6  mov     rcx, [rbp+188h]; this
0x1800073dd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073e4  mov     edx, 0E01h; void *
0x1800073e9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800073ef  mov     rcx, [rbp+188h]; this
0x1800073f6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800073fd  mov     edx, 0A15h; void *
0x180007402  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007408  mov     rcx, [rbp+188h]; this
0x18000740f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007416  mov     edx, 0A0Bh; void *
0x18000741b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007421  mov     rcx, [rbp+188h]; this
0x180007428  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000742f  mov     edx, 0A15h; void *
0x180007434  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000743a  mov     rcx, [rbp+188h]; this
0x180007441  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007448  mov     edx, 0A0Bh; void *
0x18000744d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007453  mov     rcx, [rbp+188h]; this
0x18000745a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007461  mov     edx, 0A15h; void *
0x180007466  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
