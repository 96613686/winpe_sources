# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005198`
- end: `0x180005560`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800085ec`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x180005198`
- `0x180005a20`
- `0x180006098`
- `0x180008158`
- `0x180009870`
- `0x18000b744`
- `0x18000c364`
- `0x18000c80c`
- `0x18000d1fc`
- `0x18000d20c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005405`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005475`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005405`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005231`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005231`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005210`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000548b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053ce`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180005198  mov     [rsp-8+arg_10], rbx
0x18000519d  push    rbp
0x18000519e  push    rsi
0x18000519f  push    rdi
0x1800051a0  push    r14
0x1800051a2  push    r15
0x1800051a4  lea     rbp, [rsp-160h]
0x1800051ac  sub     rsp, 260h
0x1800051b3  mov     rax, cs:__security_cookie
0x1800051ba  xor     rax, rsp
0x1800051bd  mov     [rbp+180h+var_30], rax
0x1800051c4  mov     r15, rdx
0x1800051c7  mov     qword ptr [rdx], 0
0x1800051ce  mov     rbx, rcx
0x1800051d1  call    cs:__imp_GetCurrentProcessId
0x1800051d7  mov     r14d, 78h ; 'x'
0x1800051dd  mov     [rsp+280h+var_258], rbx
0x1800051e2  mov     r9d, eax
0x1800051e5  mov     [rsp+280h+var_260], r14d; int
0x1800051ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800051f1  mov     edx, 104h; unsigned __int64
0x1800051f6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800051fb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180005200  mov     r9d, 1F0001h; dwDesiredAccess
0x180005206  lea     rdx, [rsp+280h+Name]; lpName
0x18000520b  xor     r8d, r8d; dwFlags
0x18000520e  xor     ecx, ecx; lpMutexAttributes
0x180005210  call    cs:__imp_CreateMutexExW
0x180005216  mov     rbx, rax
0x180005219  test    rax, rax
0x18000521c  jnz     short loc_180005228
0x18000521e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005223  jmp     loc_180005497
0x180005228  xor     r8d, r8d; bAlertable
0x18000522b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000522e  mov     rcx, rbx; hHandle
0x180005231  call    cs:__imp_WaitForSingleObjectEx
0x180005237  cmp     eax, 102h
0x18000523c  jz      short loc_18000524E
0x18000523e  test    eax, 0FFFFFF7Fh
0x180005243  jnz     loc_1800054CF
0x180005249  mov     rdi, rbx
0x18000524c  jmp     short loc_180005250
0x18000524e  xor     edi, edi
0x180005250  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005255  mov     [rsp+280h+hObject], 0
0x18000525e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180005263  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180005268  mov     esi, eax
0x18000526a  test    eax, eax
0x18000526c  jns     short loc_1800052ED
0x18000526e  mov     rcx, [rbp+188h]; this
0x180005275  lea     r8, aWil; "wil"
0x18000527c  mov     r9d, eax; char *
0x18000527f  mov     edx, 66h ; 'f'; void *
0x180005284  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005289  mov     rcx, [rbp+188h]; this
0x180005290  lea     r8, aWil; "wil"
0x180005297  mov     r9d, esi; char *
0x18000529a  mov     edx, 6Fh ; 'o'; void *
0x18000529f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052a4  mov     rcx, [rbp+188h]; this
0x1800052ab  lea     r8, aWil; "wil"
0x1800052b2  mov     r9d, esi; char *
0x1800052b5  mov     edx, 12Eh; void *
0x1800052ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052bf  test    rdi, rdi
0x1800052c2  jz      short loc_1800052D5
0x1800052c4  mov     rcx, rdi; hMutex
0x1800052c7  call    cs:__imp_ReleaseMutex
0x1800052cd  test    eax, eax
0x1800052cf  jz      loc_1800054DC
0x1800052d5  mov     rcx, rbx; hObject
0x1800052d8  call    cs:__imp_CloseHandle
0x1800052de  test    eax, eax
0x1800052e0  jz      loc_1800054EE
0x1800052e6  mov     eax, esi
0x1800052e8  jmp     loc_180005497
0x1800052ed  mov     rax, [rsp+280h+hObject]
0x1800052f2  lea     rcx, ds:0[rax*4]
0x1800052fa  test    rcx, rcx
0x1800052fd  jz      short loc_18000530D
0x1800052ff  mov     [r15], rcx
0x180005302  mov     eax, [rcx]
0x180005304  inc     eax
0x180005306  mov     [rcx], eax
0x180005308  jmp     loc_18000546D
0x18000530d  mov     rdx, r14; dwBytes
0x180005310  mov     qword ptr [r15], 0
0x180005317  mov     ecx, 8; dwFlags
0x18000531c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005321  mov     rsi, rax
0x180005324  test    rax, rax
0x180005327  jnz     short loc_18000534F
0x180005329  mov     rcx, [rbp+188h]; this
0x180005330  lea     r8, aWil; "wil"
0x180005337  mov     r14d, 8007000Eh
0x18000533d  mov     edx, 14Bh; void *
0x180005342  mov     r9d, r14d; char *
0x180005345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000534a  jmp     loc_1800053E2
0x18000534f  xorps   xmm0, xmm0
0x180005352  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005358  test    sil, 3
0x18000535c  jnz     loc_180005500
0x180005362  mov     r9, rsi
0x180005365  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000536a  shr     r9, 2; unsigned __int64
0x18000536e  lea     rcx, [rsp+280h+hObject]; this
0x180005373  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180005378  mov     r14d, eax
0x18000537b  test    eax, eax
0x18000537d  jns     loc_180005429
0x180005383  mov     rcx, [rbp+188h]; this
0x18000538a  lea     r8, aWil; "wil"
0x180005391  mov     r9d, eax; char *
0x180005394  mov     edx, 14Eh; void *
0x180005399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000539e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800053a3  test    rcx, rcx
0x1800053a6  jz      short loc_1800053B6
0x1800053a8  call    cs:__imp_CloseHandle
0x1800053ae  test    eax, eax
0x1800053b0  jz      loc_180005506
0x1800053b6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800053bb  test    rcx, rcx
0x1800053be  jz      short loc_1800053CE
0x1800053c0  call    cs:__imp_CloseHandle
0x1800053c6  test    eax, eax
0x1800053c8  jz      loc_180005518
0x1800053ce  call    cs:__imp_GetProcessHeap
0x1800053d4  mov     r8, rsi; lpMem
0x1800053d7  xor     edx, edx; dwFlags
0x1800053d9  mov     rcx, rax; hHeap
0x1800053dc  call    cs:__imp_HeapFree
0x1800053e2  mov     rcx, [rbp+188h]; this
0x1800053e9  lea     r8, aWil; "wil"
0x1800053f0  mov     r9d, r14d; char *
0x1800053f3  mov     edx, 137h; void *
0x1800053f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053fd  test    rdi, rdi
0x180005400  jz      short loc_180005413
0x180005402  mov     rcx, rdi; hMutex
0x180005405  call    cs:__imp_ReleaseMutex
0x18000540b  test    eax, eax
0x18000540d  jz      loc_18000552A
0x180005413  mov     rcx, rbx; hObject
0x180005416  call    cs:__imp_CloseHandle
0x18000541c  test    eax, eax
0x18000541e  jz      loc_18000553C
0x180005424  mov     eax, r14d
0x180005427  jmp     short loc_180005497
0x180005429  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000542e  xor     edx, edx; Val
0x180005430  mov     dword ptr [rsi], 1
0x180005436  lea     rcx, [rsi+22h]; void *
0x18000543a  mov     [rsi+8], rbx
0x18000543e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005443  lea     r8d, [rdx+56h]; Size
0x180005447  call    memset_0
0x18000544c  xor     edx, edx; Val
0x18000544e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005454  lea     rcx, [rsi+28h]; void *
0x180005458  mov     dword ptr [rsi+24h], 1
0x18000545f  lea     r8d, [rdx+50h]; Size
0x180005463  call    memset_0
0x180005468  xor     ebx, ebx
0x18000546a  mov     [r15], rsi
0x18000546d  test    rdi, rdi
0x180005470  jz      short loc_180005483
0x180005472  mov     rcx, rdi; hMutex
0x180005475  call    cs:__imp_ReleaseMutex
0x18000547b  test    eax, eax
0x18000547d  jz      loc_18000554E
0x180005483  test    rbx, rbx
0x180005486  jz      short loc_180005495
0x180005488  mov     rcx, rbx; hObject
0x18000548b  call    cs:__imp_CloseHandle
0x180005491  test    eax, eax
0x180005493  jz      short loc_1800054BD
0x180005495  xor     eax, eax
0x180005497  mov     rcx, [rbp+180h+var_30]
0x18000549e  xor     rcx, rsp; StackCookie
0x1800054a1  call    __security_check_cookie
0x1800054a6  mov     rbx, [rsp+280h+arg_10]
0x1800054ae  add     rsp, 260h
0x1800054b5  pop     r15
0x1800054b7  pop     r14
0x1800054b9  pop     rdi
0x1800054ba  pop     rsi
0x1800054bb  pop     rbp
0x1800054bc  retn
0x1800054bd  mov     rcx, [rbp+188h]; this
0x1800054c4  mov     edx, 0A0Bh; void *
0x1800054c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054cf  mov     rcx, [rbp+188h]; this
0x1800054d6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800054dc  mov     rcx, [rbp+188h]; this
0x1800054e3  mov     edx, 0A15h; void *
0x1800054e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054ee  mov     rcx, [rbp+188h]; this
0x1800054f5  mov     edx, 0A0Bh; void *
0x1800054fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005500  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005506  mov     rcx, [rbp+188h]; this
0x18000550d  mov     edx, 0A0Bh; void *
0x180005512  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005518  mov     rcx, [rbp+188h]; this
0x18000551f  mov     edx, 0A0Bh; void *
0x180005524  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000552a  mov     rcx, [rbp+188h]; this
0x180005531  mov     edx, 0A15h; void *
0x180005536  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000553c  mov     rcx, [rbp+188h]; this
0x180005543  mov     edx, 0A0Bh; void *
0x180005548  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000554e  mov     rcx, [rbp+188h]; this
0x180005555  mov     edx, 0A15h; void *
0x18000555a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
