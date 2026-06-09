# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005188`
- end: `0x180005555`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006a30`

## callees

- `0x180002590`
- `0x180003088`
- `0x180005188`
- `0x180005958`
- `0x180005e98`
- `0x1800067c8`
- `0x1800071b8`
- `0x180008934`
- `0x1800094bc`
- `0x18000993c`
- `0x18000a20c`
- `0x18000a21c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800053f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005465`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800052b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800053f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005465`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005221`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005221`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005200`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005200`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800052c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005398`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547b`

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
0x180005188  mov     [rsp-8+arg_10], rbx
0x18000518d  push    rbp
0x18000518e  push    rsi
0x18000518f  push    rdi
0x180005190  push    r14
0x180005192  push    r15
0x180005194  lea     rbp, [rsp-160h]
0x18000519c  sub     rsp, 260h
0x1800051a3  mov     rax, cs:__security_cookie
0x1800051aa  xor     rax, rsp
0x1800051ad  mov     [rbp+180h+var_30], rax
0x1800051b4  mov     r15, rdx
0x1800051b7  mov     qword ptr [rdx], 0
0x1800051be  mov     rbx, rcx
0x1800051c1  call    cs:__imp_GetCurrentProcessId
0x1800051c7  mov     r14d, 78h ; 'x'
0x1800051cd  mov     [rsp+280h+var_258], rbx
0x1800051d2  mov     r9d, eax
0x1800051d5  mov     [rsp+280h+var_260], r14d; int
0x1800051da  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800051e1  mov     edx, 104h; unsigned __int64
0x1800051e6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800051eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800051f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800051f6  lea     rdx, [rsp+280h+Name]; lpName
0x1800051fb  xor     r8d, r8d; dwFlags
0x1800051fe  xor     ecx, ecx; lpMutexAttributes
0x180005200  call    cs:__imp_CreateMutexExW
0x180005206  mov     rbx, rax
0x180005209  test    rax, rax
0x18000520c  jnz     short loc_180005218
0x18000520e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005213  jmp     loc_180005487
0x180005218  xor     r8d, r8d; bAlertable
0x18000521b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000521e  mov     rcx, rbx; hHandle
0x180005221  call    cs:__imp_WaitForSingleObjectEx
0x180005227  cmp     eax, 102h
0x18000522c  jz      short loc_18000523E
0x18000522e  test    eax, 0FFFFFF7Fh
0x180005233  jnz     loc_1800054BF
0x180005239  mov     rdi, rbx
0x18000523c  jmp     short loc_180005240
0x18000523e  xor     edi, edi
0x180005240  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005245  mov     [rsp+280h+hObject], 0
0x18000524e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005253  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005258  mov     esi, eax
0x18000525a  test    eax, eax
0x18000525c  jns     short loc_1800052DD
0x18000525e  mov     rcx, [rbp+188h]; this
0x180005265  lea     r8, aWil; "wil"
0x18000526c  mov     r9d, eax; char *
0x18000526f  mov     edx, 66h ; 'f'; void *
0x180005274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005279  mov     rcx, [rbp+188h]; this
0x180005280  lea     r8, aWil; "wil"
0x180005287  mov     r9d, esi; char *
0x18000528a  mov     edx, 6Fh ; 'o'; void *
0x18000528f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005294  mov     rcx, [rbp+188h]; this
0x18000529b  lea     r8, aWil; "wil"
0x1800052a2  mov     r9d, esi; char *
0x1800052a5  mov     edx, 12Eh; void *
0x1800052aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052af  test    rdi, rdi
0x1800052b2  jz      short loc_1800052C5
0x1800052b4  mov     rcx, rdi; hMutex
0x1800052b7  call    cs:__imp_ReleaseMutex
0x1800052bd  test    eax, eax
0x1800052bf  jz      loc_1800054D1
0x1800052c5  mov     rcx, rbx; hObject
0x1800052c8  call    cs:__imp_CloseHandle
0x1800052ce  test    eax, eax
0x1800052d0  jz      loc_1800054E3
0x1800052d6  mov     eax, esi
0x1800052d8  jmp     loc_180005487
0x1800052dd  mov     rax, [rsp+280h+hObject]
0x1800052e2  lea     rcx, ds:0[rax*4]
0x1800052ea  test    rcx, rcx
0x1800052ed  jz      short loc_1800052FD
0x1800052ef  mov     [r15], rcx
0x1800052f2  mov     eax, [rcx]
0x1800052f4  inc     eax
0x1800052f6  mov     [rcx], eax
0x1800052f8  jmp     loc_18000545D
0x1800052fd  mov     rdx, r14; dwBytes
0x180005300  mov     qword ptr [r15], 0
0x180005307  mov     ecx, 8; dwFlags
0x18000530c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005311  mov     rsi, rax
0x180005314  test    rax, rax
0x180005317  jnz     short loc_18000533F
0x180005319  mov     rcx, [rbp+188h]; this
0x180005320  lea     r8, aWil; "wil"
0x180005327  mov     r14d, 8007000Eh
0x18000532d  mov     edx, 14Bh; void *
0x180005332  mov     r9d, r14d; char *
0x180005335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000533a  jmp     loc_1800053D2
0x18000533f  xorps   xmm0, xmm0
0x180005342  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005348  test    sil, 3
0x18000534c  jnz     loc_1800054F5
0x180005352  mov     r9, rsi
0x180005355  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000535a  shr     r9, 2; unsigned __int64
0x18000535e  lea     rcx, [rsp+280h+hObject]; this
0x180005363  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005368  mov     r14d, eax
0x18000536b  test    eax, eax
0x18000536d  jns     loc_180005419
0x180005373  mov     rcx, [rbp+188h]; this
0x18000537a  lea     r8, aWil; "wil"
0x180005381  mov     r9d, eax; char *
0x180005384  mov     edx, 14Eh; void *
0x180005389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000538e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005393  test    rcx, rcx
0x180005396  jz      short loc_1800053A6
0x180005398  call    cs:__imp_CloseHandle
0x18000539e  test    eax, eax
0x1800053a0  jz      loc_1800054FB
0x1800053a6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800053ab  test    rcx, rcx
0x1800053ae  jz      short loc_1800053BE
0x1800053b0  call    cs:__imp_CloseHandle
0x1800053b6  test    eax, eax
0x1800053b8  jz      loc_18000550D
0x1800053be  call    cs:__imp_GetProcessHeap
0x1800053c4  mov     r8, rsi; lpMem
0x1800053c7  xor     edx, edx; dwFlags
0x1800053c9  mov     rcx, rax; hHeap
0x1800053cc  call    cs:__imp_HeapFree
0x1800053d2  mov     rcx, [rbp+188h]; this
0x1800053d9  lea     r8, aWil; "wil"
0x1800053e0  mov     r9d, r14d; char *
0x1800053e3  mov     edx, 137h; void *
0x1800053e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053ed  test    rdi, rdi
0x1800053f0  jz      short loc_180005403
0x1800053f2  mov     rcx, rdi; hMutex
0x1800053f5  call    cs:__imp_ReleaseMutex
0x1800053fb  test    eax, eax
0x1800053fd  jz      loc_18000551F
0x180005403  mov     rcx, rbx; hObject
0x180005406  call    cs:__imp_CloseHandle
0x18000540c  test    eax, eax
0x18000540e  jz      loc_180005531
0x180005414  mov     eax, r14d
0x180005417  jmp     short loc_180005487
0x180005419  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000541e  xor     edx, edx; Val
0x180005420  mov     dword ptr [rsi], 1
0x180005426  lea     rcx, [rsi+22h]; void *
0x18000542a  mov     [rsi+8], rbx
0x18000542e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005433  lea     r8d, [rdx+56h]; Size
0x180005437  call    memset_0
0x18000543c  xor     edx, edx; Val
0x18000543e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005444  lea     rcx, [rsi+28h]; void *
0x180005448  mov     dword ptr [rsi+24h], 1
0x18000544f  lea     r8d, [rdx+50h]; Size
0x180005453  call    memset_0
0x180005458  xor     ebx, ebx
0x18000545a  mov     [r15], rsi
0x18000545d  test    rdi, rdi
0x180005460  jz      short loc_180005473
0x180005462  mov     rcx, rdi; hMutex
0x180005465  call    cs:__imp_ReleaseMutex
0x18000546b  test    eax, eax
0x18000546d  jz      loc_180005543
0x180005473  test    rbx, rbx
0x180005476  jz      short loc_180005485
0x180005478  mov     rcx, rbx; hObject
0x18000547b  call    cs:__imp_CloseHandle
0x180005481  test    eax, eax
0x180005483  jz      short loc_1800054AD
0x180005485  xor     eax, eax
0x180005487  mov     rcx, [rbp+180h+var_30]
0x18000548e  xor     rcx, rsp; StackCookie
0x180005491  call    __security_check_cookie
0x180005496  mov     rbx, [rsp+280h+arg_10]
0x18000549e  add     rsp, 260h
0x1800054a5  pop     r15
0x1800054a7  pop     r14
0x1800054a9  pop     rdi
0x1800054aa  pop     rsi
0x1800054ab  pop     rbp
0x1800054ac  retn
0x1800054ad  mov     rcx, [rbp+188h]; this
0x1800054b4  mov     edx, 0A0Bh; void *
0x1800054b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054bf  mov     rcx, [rbp+188h]; this
0x1800054c6  mov     edx, 0E01h; void *
0x1800054cb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800054d1  mov     rcx, [rbp+188h]; this
0x1800054d8  mov     edx, 0A15h; void *
0x1800054dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054e3  mov     rcx, [rbp+188h]; this
0x1800054ea  mov     edx, 0A0Bh; void *
0x1800054ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800054f5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800054fb  mov     rcx, [rbp+188h]; this
0x180005502  mov     edx, 0A0Bh; void *
0x180005507  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000550d  mov     rcx, [rbp+188h]; this
0x180005514  mov     edx, 0A0Bh; void *
0x180005519  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000551f  mov     rcx, [rbp+188h]; this
0x180005526  mov     edx, 0A15h; void *
0x18000552b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005531  mov     rcx, [rbp+188h]; this
0x180005538  mov     edx, 0A0Bh; void *
0x18000553d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005543  mov     rcx, [rbp+188h]; this
0x18000554a  mov     edx, 0A15h; void *
0x18000554f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
