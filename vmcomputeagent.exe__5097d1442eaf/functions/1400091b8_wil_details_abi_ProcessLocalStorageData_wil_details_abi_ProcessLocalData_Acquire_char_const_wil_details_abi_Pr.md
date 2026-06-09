# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400091b8`
- end: `0x140009590`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000aae0`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008c8c`
- `0x1400091b8`
- `0x1400099e0`
- `0x140009f8c`
- `0x14000a900`
- `0x14000b6bc`
- `0x14000cef4`
- `0x14000da08`
- `0x14000ddc8`
- `0x14000ea34`
- `0x14000ea44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009251`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009251`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400092e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400093fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009493`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400092e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400093fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009493`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009230`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400093c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400093d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400091f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400091f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400094a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400092f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400094a9`

## string_xrefs

- `0x1400094e2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400094fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009514`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000952d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000954c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009565`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000957e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
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
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
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
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x1400091b8  mov     [rsp-8+arg_10], rbx
0x1400091bd  push    rbp
0x1400091be  push    rsi
0x1400091bf  push    rdi
0x1400091c0  push    r14
0x1400091c2  push    r15
0x1400091c4  lea     rbp, [rsp-160h]
0x1400091cc  sub     rsp, 260h
0x1400091d3  mov     rax, cs:__security_cookie
0x1400091da  xor     rax, rsp
0x1400091dd  mov     [rbp+180h+var_30], rax
0x1400091e4  mov     r15, rdx
0x1400091e7  mov     qword ptr [rdx], 0
0x1400091ee  mov     rbx, rcx
0x1400091f1  call    cs:__imp_GetCurrentProcessId
0x1400091f7  mov     r14d, 78h ; 'x'
0x1400091fd  mov     [rsp+280h+var_258], rbx
0x140009202  mov     r9d, eax
0x140009205  mov     [rsp+280h+var_260], r14d; int
0x14000920a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009211  mov     edx, 104h; unsigned __int64
0x140009216  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000921b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009220  mov     r9d, 1F0001h; dwDesiredAccess
0x140009226  lea     rdx, [rsp+280h+Name]; lpName
0x14000922b  xor     r8d, r8d; dwFlags
0x14000922e  xor     ecx, ecx; lpMutexAttributes
0x140009230  call    cs:__imp_CreateMutexExW
0x140009236  mov     rbx, rax
0x140009239  test    rax, rax
0x14000923c  jnz     short loc_140009248
0x14000923e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009243  jmp     loc_1400094B5
0x140009248  xor     r8d, r8d; bAlertable
0x14000924b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000924e  mov     rcx, rbx; hHandle
0x140009251  call    cs:__imp_WaitForSingleObjectEx
0x140009257  cmp     eax, 102h
0x14000925c  jz      short loc_14000926E
0x14000925e  test    eax, 0FFFFFF7Fh
0x140009263  jnz     loc_1400094F4
0x140009269  mov     rdi, rbx
0x14000926c  jmp     short loc_140009270
0x14000926e  xor     edi, edi
0x140009270  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140009275  mov     [rsp+280h+var_250], 0
0x14000927e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009283  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140009288  mov     esi, eax
0x14000928a  test    eax, eax
0x14000928c  jns     short loc_14000930D
0x14000928e  mov     rcx, [rbp+188h]; this
0x140009295  lea     r8, aWil; "wil"
0x14000929c  mov     r9d, eax; char *
0x14000929f  mov     edx, 66h ; 'f'; void *
0x1400092a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092a9  mov     rcx, [rbp+188h]; this
0x1400092b0  lea     r8, aWil; "wil"
0x1400092b7  mov     r9d, esi; char *
0x1400092ba  mov     edx, 6Fh ; 'o'; void *
0x1400092bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092c4  mov     rcx, [rbp+188h]; this
0x1400092cb  lea     r8, aWil; "wil"
0x1400092d2  mov     r9d, esi; char *
0x1400092d5  mov     edx, 12Eh; void *
0x1400092da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092df  test    rdi, rdi
0x1400092e2  jz      short loc_1400092F5
0x1400092e4  mov     rcx, rdi; hMutex
0x1400092e7  call    cs:__imp_ReleaseMutex
0x1400092ed  test    eax, eax
0x1400092ef  jz      loc_14000950D
0x1400092f5  mov     rcx, rbx; hObject
0x1400092f8  call    cs:__imp_CloseHandle
0x1400092fe  test    eax, eax
0x140009300  jz      loc_140009526
0x140009306  mov     eax, esi
0x140009308  jmp     loc_1400094B5
0x14000930d  mov     rax, [rsp+280h+var_250]
0x140009312  lea     rcx, ds:0[rax*4]
0x14000931a  test    rcx, rcx
0x14000931d  jz      short loc_14000932D
0x14000931f  mov     [r15], rcx
0x140009322  mov     eax, [rcx]
0x140009324  inc     eax
0x140009326  mov     [rcx], eax
0x140009328  jmp     loc_14000948B
0x14000932d  mov     rdx, r14; dwBytes
0x140009330  mov     qword ptr [r15], 0
0x140009337  mov     ecx, 8; dwFlags
0x14000933c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009341  mov     rsi, rax
0x140009344  test    rax, rax
0x140009347  jnz     short loc_14000936C
0x140009349  mov     rcx, [rbp+188h]; this
0x140009350  lea     r8, aWil; "wil"
0x140009357  mov     r14d, 8007000Eh
0x14000935d  mov     edx, 14Bh; void *
0x140009362  mov     r9d, r14d; char *
0x140009365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000936a  jmp     short loc_1400093D9
0x14000936c  xorps   xmm0, xmm0
0x14000936f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140009375  test    sil, 3
0x140009379  jnz     loc_14000953F
0x14000937f  mov     r9, rsi
0x140009382  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140009387  shr     r9, 2; unsigned __int64
0x14000938b  lea     rcx, [rsp+280h+var_250]; this
0x140009390  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140009395  mov     r14d, eax
0x140009398  test    eax, eax
0x14000939a  jns     loc_140009423
0x1400093a0  mov     rcx, [rbp+188h]; this
0x1400093a7  lea     r8, aWil; "wil"
0x1400093ae  mov     r9d, eax; char *
0x1400093b1  mov     edx, 14Eh; void *
0x1400093b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093bb  lea     rcx, [rsp+280h+var_250]; this
0x1400093c0  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400093c5  call    cs:__imp_GetProcessHeap
0x1400093cb  mov     r8, rsi; lpMem
0x1400093ce  xor     edx, edx; dwFlags
0x1400093d0  mov     rcx, rax; hHeap
0x1400093d3  call    cs:__imp_HeapFree
0x1400093d9  mov     rcx, [rbp+188h]; this
0x1400093e0  lea     r8, aWil; "wil"
0x1400093e7  mov     r9d, r14d; char *
0x1400093ea  mov     edx, 137h; void *
0x1400093ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400093f4  test    rdi, rdi
0x1400093f7  jz      short loc_14000940A
0x1400093f9  mov     rcx, rdi; hMutex
0x1400093fc  call    cs:__imp_ReleaseMutex
0x140009402  test    eax, eax
0x140009404  jz      loc_140009545
0x14000940a  mov     rcx, rbx; hObject
0x14000940d  call    cs:__imp_CloseHandle
0x140009413  test    eax, eax
0x140009415  jz      loc_14000955E
0x14000941b  mov     eax, r14d
0x14000941e  jmp     loc_1400094B5
0x140009423  mov     rax, [rsp+280h+var_250]
0x140009428  lea     rcx, [rsi+22h]; void *
0x14000942c  xor     edx, edx; Val
0x14000942e  mov     [rsi+10h], rax
0x140009432  mov     rax, [rsp+280h+var_250+8]
0x140009437  mov     dword ptr [rsi], 1
0x14000943d  mov     [rsi+8], rbx
0x140009441  lea     r8d, [rdx+56h]; Size
0x140009445  mov     [rsp+280h+var_250], 0
0x14000944e  mov     [rsi+18h], rax
0x140009452  mov     [rsp+280h+var_250+8], 0
0x14000945b  call    memset_0
0x140009460  xor     edx, edx; Val
0x140009462  mov     word ptr [rsi+20h], 58h ; 'X'
0x140009468  lea     rcx, [rsi+28h]; void *
0x14000946c  mov     dword ptr [rsi+24h], 1
0x140009473  lea     r8d, [rdx+50h]; Size
0x140009477  call    memset_0
0x14000947c  lea     rcx, [rsp+280h+var_250]; this
0x140009481  mov     [r15], rsi
0x140009484  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140009489  xor     ebx, ebx
0x14000948b  test    rdi, rdi
0x14000948e  jz      short loc_1400094A1
0x140009490  mov     rcx, rdi; hMutex
0x140009493  call    cs:__imp_ReleaseMutex
0x140009499  test    eax, eax
0x14000949b  jz      loc_140009577
0x1400094a1  test    rbx, rbx
0x1400094a4  jz      short loc_1400094B3
0x1400094a6  mov     rcx, rbx; hObject
0x1400094a9  call    cs:__imp_CloseHandle
0x1400094af  test    eax, eax
0x1400094b1  jz      short loc_1400094DB
0x1400094b3  xor     eax, eax
0x1400094b5  mov     rcx, [rbp+180h+var_30]
0x1400094bc  xor     rcx, rsp; StackCookie
0x1400094bf  call    __security_check_cookie
0x1400094c4  mov     rbx, [rsp+280h+arg_10]
0x1400094cc  add     rsp, 260h
0x1400094d3  pop     r15
0x1400094d5  pop     r14
0x1400094d7  pop     rdi
0x1400094d8  pop     rsi
0x1400094d9  pop     rbp
0x1400094da  retn
0x1400094db  mov     rcx, [rbp+188h]; this
0x1400094e2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400094e9  mov     edx, 0A0Bh; void *
0x1400094ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400094f4  mov     rcx, [rbp+188h]; this
0x1400094fb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009502  mov     edx, 0E01h; void *
0x140009507  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000950d  mov     rcx, [rbp+188h]; this
0x140009514  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000951b  mov     edx, 0A15h; void *
0x140009520  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009526  mov     rcx, [rbp+188h]; this
0x14000952d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009534  mov     edx, 0A0Bh; void *
0x140009539  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000953f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009545  mov     rcx, [rbp+188h]; this
0x14000954c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009553  mov     edx, 0A15h; void *
0x140009558  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000955e  mov     rcx, [rbp+188h]; this
0x140009565  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000956c  mov     edx, 0A0Bh; void *
0x140009571  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009577  mov     rcx, [rbp+188h]; this
0x14000957e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009585  mov     edx, 0A15h; void *
0x14000958a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
