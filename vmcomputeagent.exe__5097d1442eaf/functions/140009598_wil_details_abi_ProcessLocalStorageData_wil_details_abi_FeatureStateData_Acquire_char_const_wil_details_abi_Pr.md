# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140009598`
- end: `0x140009995`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140009de0`

## callees

- `0x140005360`
- `0x140006098`
- `0x140008568`
- `0x140008c8c`
- `0x140009598`
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

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009630`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009630`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400096c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400097d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009898`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400096c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400097d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009898`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000960f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000960f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000985b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14000985b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400095d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400095d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400098ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400096d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400097ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400098ae`

## string_xrefs

- `0x1400098e7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009900`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009919`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009932`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000994b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000996a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140009983`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
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
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x140009598  mov     [rsp-8+arg_10], rbx
0x14000959d  push    rbp
0x14000959e  push    rsi
0x14000959f  push    rdi
0x1400095a0  push    r14
0x1400095a2  push    r15
0x1400095a4  lea     rbp, [rsp-160h]
0x1400095ac  sub     rsp, 260h
0x1400095b3  mov     rax, cs:__security_cookie
0x1400095ba  xor     rax, rsp
0x1400095bd  mov     [rbp+180h+var_30], rax
0x1400095c4  mov     r15, rdx
0x1400095c7  mov     qword ptr [rdx], 0
0x1400095ce  mov     rbx, rcx
0x1400095d1  call    cs:__imp_GetCurrentProcessId
0x1400095d7  mov     r14d, 130h
0x1400095dd  mov     [rsp+280h+var_258], rbx
0x1400095e2  mov     r9d, eax
0x1400095e5  mov     [rsp+280h+var_260], r14d; int
0x1400095ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400095f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400095f6  lea     edx, [r14-2Ch]; unsigned __int64
0x1400095fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400095ff  mov     r9d, 1F0001h; dwDesiredAccess
0x140009605  lea     rdx, [rsp+280h+Name]; lpName
0x14000960a  xor     r8d, r8d; dwFlags
0x14000960d  xor     ecx, ecx; lpMutexAttributes
0x14000960f  call    cs:__imp_CreateMutexExW
0x140009615  mov     rbx, rax
0x140009618  test    rax, rax
0x14000961b  jnz     short loc_140009627
0x14000961d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009622  jmp     loc_1400098BA
0x140009627  xor     r8d, r8d; bAlertable
0x14000962a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000962d  mov     rcx, rbx; hHandle
0x140009630  call    cs:__imp_WaitForSingleObjectEx
0x140009636  cmp     eax, 102h
0x14000963b  jz      short loc_14000964D
0x14000963d  test    eax, 0FFFFFF7Fh
0x140009642  jnz     loc_140009912
0x140009648  mov     rdi, rbx
0x14000964b  jmp     short loc_14000964F
0x14000964d  xor     edi, edi
0x14000964f  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140009654  mov     [rsp+280h+var_250], 0
0x14000965d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140009662  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140009667  mov     esi, eax
0x140009669  test    eax, eax
0x14000966b  jns     short loc_1400096EC
0x14000966d  mov     rcx, [rbp+188h]; this
0x140009674  lea     r8, aWil; "wil"
0x14000967b  mov     r9d, eax; char *
0x14000967e  mov     edx, 66h ; 'f'; void *
0x140009683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009688  mov     rcx, [rbp+188h]; this
0x14000968f  lea     r8, aWil; "wil"
0x140009696  mov     r9d, esi; char *
0x140009699  mov     edx, 6Fh ; 'o'; void *
0x14000969e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400096a3  mov     rcx, [rbp+188h]; this
0x1400096aa  lea     r8, aWil; "wil"
0x1400096b1  mov     r9d, esi; char *
0x1400096b4  mov     edx, 12Eh; void *
0x1400096b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400096be  test    rdi, rdi
0x1400096c1  jz      short loc_1400096D4
0x1400096c3  mov     rcx, rdi; hMutex
0x1400096c6  call    cs:__imp_ReleaseMutex
0x1400096cc  test    eax, eax
0x1400096ce  jz      loc_14000992B
0x1400096d4  mov     rcx, rbx; hObject
0x1400096d7  call    cs:__imp_CloseHandle
0x1400096dd  test    eax, eax
0x1400096df  jz      loc_140009944
0x1400096e5  mov     eax, esi
0x1400096e7  jmp     loc_1400098BA
0x1400096ec  mov     rax, [rsp+280h+var_250]
0x1400096f1  lea     rcx, ds:0[rax*4]
0x1400096f9  test    rcx, rcx
0x1400096fc  jz      short loc_14000970C
0x1400096fe  mov     [r15], rcx
0x140009701  mov     eax, [rcx]
0x140009703  inc     eax
0x140009705  mov     [rcx], eax
0x140009707  jmp     loc_140009890
0x14000970c  mov     rdx, r14; dwBytes
0x14000970f  mov     qword ptr [r15], 0
0x140009716  mov     ecx, 8; dwFlags
0x14000971b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009720  mov     r14, rax
0x140009723  test    rax, rax
0x140009726  jnz     short loc_14000974A
0x140009728  mov     rcx, [rbp+188h]; this
0x14000972f  lea     r8, aWil; "wil"
0x140009736  mov     esi, 8007000Eh
0x14000973b  mov     edx, 14Bh; void *
0x140009740  mov     r9d, esi; char *
0x140009743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009748  jmp     short loc_1400097B6
0x14000974a  xorps   xmm0, xmm0
0x14000974d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140009753  test    r14b, 3
0x140009757  jnz     loc_14000995D
0x14000975d  mov     r9, r14
0x140009760  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140009765  shr     r9, 2; unsigned __int64
0x140009769  lea     rcx, [rsp+280h+var_250]; this
0x14000976e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140009773  mov     esi, eax
0x140009775  test    eax, eax
0x140009777  jns     loc_1400097FD
0x14000977d  mov     rcx, [rbp+188h]; this
0x140009784  lea     r8, aWil; "wil"
0x14000978b  mov     r9d, eax; char *
0x14000978e  mov     edx, 14Eh; void *
0x140009793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009798  lea     rcx, [rsp+280h+var_250]; this
0x14000979d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400097a2  call    cs:__imp_GetProcessHeap
0x1400097a8  mov     r8, r14; lpMem
0x1400097ab  xor     edx, edx; dwFlags
0x1400097ad  mov     rcx, rax; hHeap
0x1400097b0  call    cs:__imp_HeapFree
0x1400097b6  mov     rcx, [rbp+188h]; this
0x1400097bd  lea     r8, aWil; "wil"
0x1400097c4  mov     r9d, esi; char *
0x1400097c7  mov     edx, 137h; void *
0x1400097cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400097d1  test    rdi, rdi
0x1400097d4  jz      short loc_1400097E7
0x1400097d6  mov     rcx, rdi; hMutex
0x1400097d9  call    cs:__imp_ReleaseMutex
0x1400097df  test    eax, eax
0x1400097e1  jz      loc_140009963
0x1400097e7  mov     rcx, rbx; hObject
0x1400097ea  call    cs:__imp_CloseHandle
0x1400097f0  test    eax, eax
0x1400097f2  jz      loc_1400098F9
0x1400097f8  jmp     loc_1400096E5
0x1400097fd  mov     rax, [rsp+280h+var_250]
0x140009802  lea     rcx, [r14+28h]; void *
0x140009806  mov     [r14+10h], rax
0x14000980a  xor     edx, edx; Val
0x14000980c  mov     rax, [rsp+280h+var_250+8]
0x140009811  mov     r8d, 108h; Size
0x140009817  mov     [r14+18h], rax
0x14000981b  mov     dword ptr [r14], 1
0x140009822  mov     [r14+8], rbx
0x140009826  mov     [rsp+280h+var_250], 0
0x14000982f  mov     [rsp+280h+var_250+8], 0
0x140009838  call    memset_0
0x14000983d  xor     eax, eax
0x14000983f  lea     rcx, [r14+28h]; this
0x140009843  mov     [r14+20h], rax
0x140009847  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000984c  lea     rbx, [r14+0E8h]
0x140009853  xor     r8d, r8d; Flags
0x140009856  mov     rcx, rbx; lpCriticalSection
0x140009859  xor     edx, edx; dwSpinCount
0x14000985b  call    cs:__imp_InitializeCriticalSectionEx
0x140009861  mov     qword ptr [rbx+28h], 0
0x140009869  lea     rcx, [rsp+280h+var_250]; this
0x14000986e  mov     qword ptr [rbx+30h], 0
0x140009876  mov     qword ptr [rbx+38h], 0
0x14000987e  mov     qword ptr [rbx+40h], 0
0x140009886  mov     [r15], r14
0x140009889  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14000988e  xor     ebx, ebx
0x140009890  test    rdi, rdi
0x140009893  jz      short loc_1400098A6
0x140009895  mov     rcx, rdi; hMutex
0x140009898  call    cs:__imp_ReleaseMutex
0x14000989e  test    eax, eax
0x1400098a0  jz      loc_14000997C
0x1400098a6  test    rbx, rbx
0x1400098a9  jz      short loc_1400098B8
0x1400098ab  mov     rcx, rbx; hObject
0x1400098ae  call    cs:__imp_CloseHandle
0x1400098b4  test    eax, eax
0x1400098b6  jz      short loc_1400098E0
0x1400098b8  xor     eax, eax
0x1400098ba  mov     rcx, [rbp+180h+var_30]
0x1400098c1  xor     rcx, rsp; StackCookie
0x1400098c4  call    __security_check_cookie
0x1400098c9  mov     rbx, [rsp+280h+arg_10]
0x1400098d1  add     rsp, 260h
0x1400098d8  pop     r15
0x1400098da  pop     r14
0x1400098dc  pop     rdi
0x1400098dd  pop     rsi
0x1400098de  pop     rbp
0x1400098df  retn
0x1400098e0  mov     rcx, [rbp+188h]; this
0x1400098e7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400098ee  mov     edx, 0A0Bh; void *
0x1400098f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400098f9  mov     rcx, [rbp+188h]; this
0x140009900  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009907  mov     edx, 0A0Bh; void *
0x14000990c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009912  mov     rcx, [rbp+188h]; this
0x140009919  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009920  mov     edx, 0E01h; void *
0x140009925  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14000992b  mov     rcx, [rbp+188h]; this
0x140009932  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009939  mov     edx, 0A15h; void *
0x14000993e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009944  mov     rcx, [rbp+188h]; this
0x14000994b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009952  mov     edx, 0A0Bh; void *
0x140009957  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000995d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140009963  mov     rcx, [rbp+188h]; this
0x14000996a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009971  mov     edx, 0A15h; void *
0x140009976  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000997c  mov     rcx, [rbp+188h]; this
0x140009983  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000998a  mov     edx, 0A15h; void *
0x14000998f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
