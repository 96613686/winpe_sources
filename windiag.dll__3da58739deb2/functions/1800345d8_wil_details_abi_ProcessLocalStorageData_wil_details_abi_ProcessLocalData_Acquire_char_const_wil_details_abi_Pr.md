# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800345d8`
- end: `0x180034974`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `924`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180035e10`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x180034278`
- `0x1800345d8`
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

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180034650`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180034650`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034671`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034671`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800346f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800347ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034883`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800346f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800347ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180034883`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800347ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800347bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800347bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034611`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034611`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034899`

## string_xrefs

- `0x1800348d2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800348eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034911`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003492a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034949`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180034962`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned __int64 v31; // rax
  const char *v32; // r9
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v35);
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
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_24;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v23, (const char *)0x8007000ELL, 120);
    goto LABEL_19;
  }
  *(_OWORD *)v37 = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v37,
          Name,
          v23,
          v21 >> 2);
  v15 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v27, (const char *)(unsigned int)v26, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v25, (const char *)v15, v36);
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
  *((_QWORD *)v24 + 2) = v37[0];
  v31 = v37[1];
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v24 + 3) = v31;
  v37[1] = 0;
  memset_0((char *)v24 + 34, 0, 0x56u);
  *((_WORD *)v24 + 16) = 88;
  v24[9] = 1;
  memset_0(v24 + 10, 0, 0x50u);
  *a2 = v24;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v33);
  return 0;
}

```

## disassembly

```asm
0x1800345d8  mov     [rsp-8+arg_10], rbx
0x1800345dd  push    rbp
0x1800345de  push    rsi
0x1800345df  push    rdi
0x1800345e0  push    r14
0x1800345e2  push    r15
0x1800345e4  lea     rbp, [rsp-160h]
0x1800345ec  sub     rsp, 260h
0x1800345f3  mov     rax, cs:__security_cookie
0x1800345fa  xor     rax, rsp
0x1800345fd  mov     [rbp+180h+var_30], rax
0x180034604  mov     r15, rdx
0x180034607  mov     qword ptr [rdx], 0
0x18003460e  mov     rbx, rcx
0x180034611  call    cs:__imp_GetCurrentProcessId
0x180034617  mov     r14d, 78h ; 'x'
0x18003461d  mov     [rsp+280h+var_258], rbx
0x180034622  mov     r9d, eax
0x180034625  mov     [rsp+280h+var_260], r14d; int
0x18003462a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180034631  mov     edx, 104h; unsigned __int64
0x180034636  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003463b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034640  mov     r9d, 1F0001h; dwDesiredAccess
0x180034646  lea     rdx, [rsp+280h+Name]; lpName
0x18003464b  xor     r8d, r8d; dwFlags
0x18003464e  xor     ecx, ecx; lpMutexAttributes
0x180034650  call    cs:__imp_CreateMutexExW
0x180034656  mov     rbx, rax
0x180034659  test    rax, rax
0x18003465c  jnz     short loc_180034668
0x18003465e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034663  jmp     loc_1800348A5
0x180034668  xor     r8d, r8d; bAlertable
0x18003466b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003466e  mov     rcx, rbx; hHandle
0x180034671  call    cs:__imp_WaitForSingleObjectEx
0x180034677  cmp     eax, 102h
0x18003467c  jz      short loc_18003468E
0x18003467e  test    eax, 0FFFFFF7Fh
0x180034683  jnz     loc_1800348FD
0x180034689  mov     rdi, rbx
0x18003468c  jmp     short loc_180034690
0x18003468e  xor     edi, edi
0x180034690  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180034695  mov     [rsp+280h+var_250], 0
0x18003469e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800346a3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800346a8  mov     esi, eax
0x1800346aa  test    eax, eax
0x1800346ac  jns     short loc_180034718
0x1800346ae  mov     rcx, [rbp+188h]; this
0x1800346b5  mov     r9d, eax; char *
0x1800346b8  mov     edx, 66h ; 'f'; void *
0x1800346bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346c2  mov     rcx, [rbp+188h]; this
0x1800346c9  mov     r9d, esi; char *
0x1800346cc  mov     edx, 6Fh ; 'o'; void *
0x1800346d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346d6  mov     rcx, [rbp+188h]; this
0x1800346dd  mov     r9d, esi; char *
0x1800346e0  mov     edx, 12Eh; void *
0x1800346e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346ea  test    rdi, rdi
0x1800346ed  jz      short loc_180034700
0x1800346ef  mov     rcx, rdi; hMutex
0x1800346f2  call    cs:__imp_ReleaseMutex
0x1800346f8  test    eax, eax
0x1800346fa  jz      loc_18003490A
0x180034700  mov     rcx, rbx; hObject
0x180034703  call    cs:__imp_CloseHandle
0x180034709  test    eax, eax
0x18003470b  jz      loc_180034923
0x180034711  mov     eax, esi
0x180034713  jmp     loc_1800348A5
0x180034718  mov     rax, [rsp+280h+var_250]
0x18003471d  lea     rcx, ds:0[rax*4]
0x180034725  test    rcx, rcx
0x180034728  jz      short loc_180034738
0x18003472a  mov     [r15], rcx
0x18003472d  mov     eax, [rcx]
0x18003472f  inc     eax
0x180034731  mov     [rcx], eax
0x180034733  jmp     loc_18003487B
0x180034738  mov     rdx, r14; dwBytes
0x18003473b  mov     qword ptr [r15], 0
0x180034742  mov     ecx, 8; dwFlags
0x180034747  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003474c  mov     r14, rax
0x18003474f  test    rax, rax
0x180034752  jnz     short loc_18003476F
0x180034754  mov     rcx, [rbp+188h]; this
0x18003475b  mov     esi, 8007000Eh
0x180034760  mov     r9d, esi; char *
0x180034763  mov     edx, 14Bh; void *
0x180034768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003476d  jmp     short loc_1800347D0
0x18003476f  xorps   xmm0, xmm0
0x180034772  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180034778  test    r14b, 3
0x18003477c  jnz     loc_18003493C
0x180034782  mov     r9, r14
0x180034785  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18003478a  shr     r9, 2; unsigned __int64
0x18003478e  lea     rcx, [rsp+280h+var_250]; this
0x180034793  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180034798  mov     esi, eax
0x18003479a  test    eax, eax
0x18003479c  jns     short loc_180034810
0x18003479e  mov     rcx, [rbp+188h]; this
0x1800347a5  mov     r9d, eax; char *
0x1800347a8  mov     edx, 14Eh; void *
0x1800347ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347b2  lea     rcx, [rsp+280h+var_250]; this
0x1800347b7  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800347bc  call    cs:__imp_GetProcessHeap
0x1800347c2  mov     r8, r14; lpMem
0x1800347c5  xor     edx, edx; dwFlags
0x1800347c7  mov     rcx, rax; hHeap
0x1800347ca  call    cs:__imp_HeapFree
0x1800347d0  mov     rcx, [rbp+188h]; this
0x1800347d7  mov     r9d, esi; char *
0x1800347da  mov     edx, 137h; void *
0x1800347df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800347e4  test    rdi, rdi
0x1800347e7  jz      short loc_1800347FA
0x1800347e9  mov     rcx, rdi; hMutex
0x1800347ec  call    cs:__imp_ReleaseMutex
0x1800347f2  test    eax, eax
0x1800347f4  jz      loc_180034942
0x1800347fa  mov     rcx, rbx; hObject
0x1800347fd  call    cs:__imp_CloseHandle
0x180034803  test    eax, eax
0x180034805  jz      loc_1800348E4
0x18003480b  jmp     loc_180034711
0x180034810  mov     rax, [rsp+280h+var_250]
0x180034815  lea     rcx, [r14+22h]; void *
0x180034819  xor     edx, edx; Val
0x18003481b  mov     [r14+10h], rax
0x18003481f  mov     rax, [rsp+280h+var_250+8]
0x180034824  mov     dword ptr [r14], 1
0x18003482b  mov     [r14+8], rbx
0x18003482f  lea     r8d, [rdx+56h]; Size
0x180034833  mov     [rsp+280h+var_250], 0
0x18003483c  mov     [r14+18h], rax
0x180034840  mov     [rsp+280h+var_250+8], 0
0x180034849  call    memset_0
0x18003484e  xor     edx, edx; Val
0x180034850  mov     word ptr [r14+20h], 58h ; 'X'
0x180034857  lea     rcx, [r14+28h]; void *
0x18003485b  mov     dword ptr [r14+24h], 1
0x180034863  lea     r8d, [rdx+50h]; Size
0x180034867  call    memset_0
0x18003486c  lea     rcx, [rsp+280h+var_250]; this
0x180034871  mov     [r15], r14
0x180034874  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180034879  xor     ebx, ebx
0x18003487b  test    rdi, rdi
0x18003487e  jz      short loc_180034891
0x180034880  mov     rcx, rdi; hMutex
0x180034883  call    cs:__imp_ReleaseMutex
0x180034889  test    eax, eax
0x18003488b  jz      loc_18003495B
0x180034891  test    rbx, rbx
0x180034894  jz      short loc_1800348A3
0x180034896  mov     rcx, rbx; hObject
0x180034899  call    cs:__imp_CloseHandle
0x18003489f  test    eax, eax
0x1800348a1  jz      short loc_1800348CB
0x1800348a3  xor     eax, eax
0x1800348a5  mov     rcx, [rbp+180h+var_30]
0x1800348ac  xor     rcx, rsp; StackCookie
0x1800348af  call    __security_check_cookie
0x1800348b4  mov     rbx, [rsp+280h+arg_10]
0x1800348bc  add     rsp, 260h
0x1800348c3  pop     r15
0x1800348c5  pop     r14
0x1800348c7  pop     rdi
0x1800348c8  pop     rsi
0x1800348c9  pop     rbp
0x1800348ca  retn
0x1800348cb  mov     rcx, [rbp+188h]; this
0x1800348d2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800348d9  mov     edx, 0A0Bh; void *
0x1800348de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800348e4  mov     rcx, [rbp+188h]; this
0x1800348eb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800348f2  mov     edx, 0A0Bh; void *
0x1800348f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800348fd  mov     rcx, [rbp+188h]; this
0x180034904  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18003490a  mov     rcx, [rbp+188h]; this
0x180034911  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034918  mov     edx, 0A15h; void *
0x18003491d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180034923  mov     rcx, [rbp+188h]; this
0x18003492a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034931  mov     edx, 0A0Bh; void *
0x180034936  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003493c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180034942  mov     rcx, [rbp+188h]; this
0x180034949  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034950  mov     edx, 0A15h; void *
0x180034955  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003495b  mov     rcx, [rbp+188h]; this
0x180034962  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034969  mov     edx, 0A15h; void *
0x18003496e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
