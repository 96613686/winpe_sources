# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004b78`
- end: `0x180004f40`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007170`

## callees

- `0x180001e40`
- `0x1800028b4`
- `0x180004b78`
- `0x1800057f0`
- `0x180005f78`
- `0x180006e28`
- `0x180007d28`
- `0x18000a844`
- `0x18000b34c`
- `0x18000b7e8`
- `0x18000c558`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bf0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bf0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004de5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004de5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004bb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004bb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004cb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004da0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e6b`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x180004b78  mov     [rsp-8+arg_10], rbx
0x180004b7d  push    rbp
0x180004b7e  push    rsi
0x180004b7f  push    rdi
0x180004b80  push    r14
0x180004b82  push    r15
0x180004b84  lea     rbp, [rsp-160h]
0x180004b8c  sub     rsp, 260h
0x180004b93  mov     rax, cs:__security_cookie
0x180004b9a  xor     rax, rsp
0x180004b9d  mov     [rbp+180h+var_30], rax
0x180004ba4  mov     r15, rdx
0x180004ba7  mov     qword ptr [rdx], 0
0x180004bae  mov     rbx, rcx
0x180004bb1  call    cs:__imp_GetCurrentProcessId
0x180004bb7  mov     r14d, 78h ; 'x'
0x180004bbd  mov     [rsp+280h+var_258], rbx
0x180004bc2  mov     r9d, eax
0x180004bc5  mov     [rsp+280h+var_260], r14d; int
0x180004bca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004bd1  mov     edx, 104h; unsigned __int64
0x180004bd6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004bdb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004be0  mov     r9d, 1F0001h; dwDesiredAccess
0x180004be6  lea     rdx, [rsp+280h+Name]; lpName
0x180004beb  xor     r8d, r8d; dwFlags
0x180004bee  xor     ecx, ecx; lpMutexAttributes
0x180004bf0  call    cs:__imp_CreateMutexExW
0x180004bf6  mov     rbx, rax
0x180004bf9  test    rax, rax
0x180004bfc  jnz     short loc_180004C08
0x180004bfe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004c03  jmp     loc_180004E77
0x180004c08  xor     r8d, r8d; bAlertable
0x180004c0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004c0e  mov     rcx, rbx; hHandle
0x180004c11  call    cs:__imp_WaitForSingleObjectEx
0x180004c17  cmp     eax, 102h
0x180004c1c  jz      short loc_180004C2E
0x180004c1e  test    eax, 0FFFFFF7Fh
0x180004c23  jnz     loc_180004EAF
0x180004c29  mov     rdi, rbx
0x180004c2c  jmp     short loc_180004C30
0x180004c2e  xor     edi, edi
0x180004c30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004c35  mov     [rsp+280h+hObject], 0
0x180004c3e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180004c43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180004c48  mov     esi, eax
0x180004c4a  test    eax, eax
0x180004c4c  jns     short loc_180004CCD
0x180004c4e  mov     rcx, [rbp+188h]; this
0x180004c55  lea     r8, aWil; "wil"
0x180004c5c  mov     r9d, eax; char *
0x180004c5f  mov     edx, 66h ; 'f'; void *
0x180004c64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c69  mov     rcx, [rbp+188h]; this
0x180004c70  lea     r8, aWil; "wil"
0x180004c77  mov     r9d, esi; char *
0x180004c7a  mov     edx, 6Fh ; 'o'; void *
0x180004c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c84  mov     rcx, [rbp+188h]; this
0x180004c8b  lea     r8, aWil; "wil"
0x180004c92  mov     r9d, esi; char *
0x180004c95  mov     edx, 12Eh; void *
0x180004c9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c9f  test    rdi, rdi
0x180004ca2  jz      short loc_180004CB5
0x180004ca4  mov     rcx, rdi; hMutex
0x180004ca7  call    cs:__imp_ReleaseMutex
0x180004cad  test    eax, eax
0x180004caf  jz      loc_180004EBC
0x180004cb5  mov     rcx, rbx; hObject
0x180004cb8  call    cs:__imp_CloseHandle
0x180004cbe  test    eax, eax
0x180004cc0  jz      loc_180004ECE
0x180004cc6  mov     eax, esi
0x180004cc8  jmp     loc_180004E77
0x180004ccd  mov     rax, [rsp+280h+hObject]
0x180004cd2  lea     rcx, ds:0[rax*4]
0x180004cda  test    rcx, rcx
0x180004cdd  jz      short loc_180004CED
0x180004cdf  mov     [r15], rcx
0x180004ce2  mov     eax, [rcx]
0x180004ce4  inc     eax
0x180004ce6  mov     [rcx], eax
0x180004ce8  jmp     loc_180004E4D
0x180004ced  mov     rdx, r14; dwBytes
0x180004cf0  mov     qword ptr [r15], 0
0x180004cf7  mov     ecx, 8; dwFlags
0x180004cfc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d01  mov     rsi, rax
0x180004d04  test    rax, rax
0x180004d07  jnz     short loc_180004D2F
0x180004d09  mov     rcx, [rbp+188h]; this
0x180004d10  lea     r8, aWil; "wil"
0x180004d17  mov     r14d, 8007000Eh
0x180004d1d  mov     edx, 14Bh; void *
0x180004d22  mov     r9d, r14d; char *
0x180004d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d2a  jmp     loc_180004DC2
0x180004d2f  xorps   xmm0, xmm0
0x180004d32  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004d38  test    sil, 3
0x180004d3c  jnz     loc_180004EE0
0x180004d42  mov     r9, rsi
0x180004d45  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180004d4a  shr     r9, 2; unsigned __int64
0x180004d4e  lea     rcx, [rsp+280h+hObject]; this
0x180004d53  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004d58  mov     r14d, eax
0x180004d5b  test    eax, eax
0x180004d5d  jns     loc_180004E09
0x180004d63  mov     rcx, [rbp+188h]; this
0x180004d6a  lea     r8, aWil; "wil"
0x180004d71  mov     r9d, eax; char *
0x180004d74  mov     edx, 14Eh; void *
0x180004d79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d7e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004d83  test    rcx, rcx
0x180004d86  jz      short loc_180004D96
0x180004d88  call    cs:__imp_CloseHandle
0x180004d8e  test    eax, eax
0x180004d90  jz      loc_180004EE6
0x180004d96  mov     rcx, [rsp+280h+hObject]; hObject
0x180004d9b  test    rcx, rcx
0x180004d9e  jz      short loc_180004DAE
0x180004da0  call    cs:__imp_CloseHandle
0x180004da6  test    eax, eax
0x180004da8  jz      loc_180004EF8
0x180004dae  call    cs:__imp_GetProcessHeap
0x180004db4  mov     r8, rsi; lpMem
0x180004db7  xor     edx, edx; dwFlags
0x180004db9  mov     rcx, rax; hHeap
0x180004dbc  call    cs:__imp_HeapFree
0x180004dc2  mov     rcx, [rbp+188h]; this
0x180004dc9  lea     r8, aWil; "wil"
0x180004dd0  mov     r9d, r14d; char *
0x180004dd3  mov     edx, 137h; void *
0x180004dd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ddd  test    rdi, rdi
0x180004de0  jz      short loc_180004DF3
0x180004de2  mov     rcx, rdi; hMutex
0x180004de5  call    cs:__imp_ReleaseMutex
0x180004deb  test    eax, eax
0x180004ded  jz      loc_180004F0A
0x180004df3  mov     rcx, rbx; hObject
0x180004df6  call    cs:__imp_CloseHandle
0x180004dfc  test    eax, eax
0x180004dfe  jz      loc_180004F1C
0x180004e04  mov     eax, r14d
0x180004e07  jmp     short loc_180004E77
0x180004e09  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004e0e  xor     edx, edx; Val
0x180004e10  mov     dword ptr [rsi], 1
0x180004e16  lea     rcx, [rsi+22h]; void *
0x180004e1a  mov     [rsi+8], rbx
0x180004e1e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004e23  lea     r8d, [rdx+56h]; Size
0x180004e27  call    memset_0
0x180004e2c  xor     edx, edx; Val
0x180004e2e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004e34  lea     rcx, [rsi+28h]; void *
0x180004e38  mov     dword ptr [rsi+24h], 1
0x180004e3f  lea     r8d, [rdx+50h]; Size
0x180004e43  call    memset_0
0x180004e48  xor     ebx, ebx
0x180004e4a  mov     [r15], rsi
0x180004e4d  test    rdi, rdi
0x180004e50  jz      short loc_180004E63
0x180004e52  mov     rcx, rdi; hMutex
0x180004e55  call    cs:__imp_ReleaseMutex
0x180004e5b  test    eax, eax
0x180004e5d  jz      loc_180004F2E
0x180004e63  test    rbx, rbx
0x180004e66  jz      short loc_180004E75
0x180004e68  mov     rcx, rbx; hObject
0x180004e6b  call    cs:__imp_CloseHandle
0x180004e71  test    eax, eax
0x180004e73  jz      short loc_180004E9D
0x180004e75  xor     eax, eax
0x180004e77  mov     rcx, [rbp+180h+var_30]
0x180004e7e  xor     rcx, rsp; StackCookie
0x180004e81  call    __security_check_cookie
0x180004e86  mov     rbx, [rsp+280h+arg_10]
0x180004e8e  add     rsp, 260h
0x180004e95  pop     r15
0x180004e97  pop     r14
0x180004e99  pop     rdi
0x180004e9a  pop     rsi
0x180004e9b  pop     rbp
0x180004e9c  retn
0x180004e9d  mov     rcx, [rbp+188h]; this
0x180004ea4  mov     edx, 0A0Bh; void *
0x180004ea9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eaf  mov     rcx, [rbp+188h]; this
0x180004eb6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004ebc  mov     rcx, [rbp+188h]; this
0x180004ec3  mov     edx, 0A15h; void *
0x180004ec8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ece  mov     rcx, [rbp+188h]; this
0x180004ed5  mov     edx, 0A0Bh; void *
0x180004eda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ee0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004ee6  mov     rcx, [rbp+188h]; this
0x180004eed  mov     edx, 0A0Bh; void *
0x180004ef2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ef8  mov     rcx, [rbp+188h]; this
0x180004eff  mov     edx, 0A0Bh; void *
0x180004f04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f0a  mov     rcx, [rbp+188h]; this
0x180004f11  mov     edx, 0A15h; void *
0x180004f16  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f1c  mov     rcx, [rbp+188h]; this
0x180004f23  mov     edx, 0A0Bh; void *
0x180004f28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f2e  mov     rcx, [rbp+188h]; this
0x180004f35  mov     edx, 0A15h; void *
0x180004f3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
