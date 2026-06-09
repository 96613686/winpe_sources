# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b794`
- end: `0x18000bb5c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000d07c`

## callees

- `0x18000b794`
- `0x18000bf5c`
- `0x18000c4f0`
- `0x18000ce18`
- `0x18000da6c`
- `0x18000ed74`
- `0x18000f2f4`
- `0x18000f648`
- `0x18000ff0c`
- `0x18000ff1c`
- `0x18001b77a`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b7cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b7cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b8c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b8c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ba71`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b80c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b80c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b82d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b82d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b9ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b9d8`

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
0x18000b794  mov     [rsp-8+arg_10], rbx
0x18000b799  push    rbp
0x18000b79a  push    rsi
0x18000b79b  push    rdi
0x18000b79c  push    r14
0x18000b79e  push    r15
0x18000b7a0  lea     rbp, [rsp-160h]
0x18000b7a8  sub     rsp, 260h
0x18000b7af  mov     rax, cs:__security_cookie
0x18000b7b6  xor     rax, rsp
0x18000b7b9  mov     [rbp+180h+var_30], rax
0x18000b7c0  mov     r15, rdx
0x18000b7c3  mov     qword ptr [rdx], 0
0x18000b7ca  mov     rbx, rcx
0x18000b7cd  call    cs:__imp_GetCurrentProcessId
0x18000b7d3  mov     r14d, 78h ; 'x'
0x18000b7d9  mov     [rsp+280h+var_258], rbx
0x18000b7de  mov     r9d, eax
0x18000b7e1  mov     [rsp+280h+var_260], r14d; int
0x18000b7e6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b7ed  mov     edx, 104h; unsigned __int64
0x18000b7f2  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b7f7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000b7fc  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b802  lea     rdx, [rsp+280h+Name]; lpName
0x18000b807  xor     r8d, r8d; dwFlags
0x18000b80a  xor     ecx, ecx; lpMutexAttributes
0x18000b80c  call    cs:__imp_CreateMutexExW
0x18000b812  mov     rbx, rax
0x18000b815  test    rax, rax
0x18000b818  jnz     short loc_18000B824
0x18000b81a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b81f  jmp     loc_18000BA93
0x18000b824  xor     r8d, r8d; bAlertable
0x18000b827  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000b82a  mov     rcx, rbx; hHandle
0x18000b82d  call    cs:__imp_WaitForSingleObjectEx
0x18000b833  cmp     eax, 102h
0x18000b838  jz      short loc_18000B84A
0x18000b83a  test    eax, 0FFFFFF7Fh
0x18000b83f  jnz     loc_18000BACB
0x18000b845  mov     rdi, rbx
0x18000b848  jmp     short loc_18000B84C
0x18000b84a  xor     edi, edi
0x18000b84c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000b851  mov     [rsp+280h+hObject], 0
0x18000b85a  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b85f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000b864  mov     esi, eax
0x18000b866  test    eax, eax
0x18000b868  jns     short loc_18000B8E9
0x18000b86a  mov     rcx, [rbp+188h]; this
0x18000b871  lea     r8, aWil; "wil"
0x18000b878  mov     r9d, eax; char *
0x18000b87b  mov     edx, 66h ; 'f'; void *
0x18000b880  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b885  mov     rcx, [rbp+188h]; this
0x18000b88c  lea     r8, aWil; "wil"
0x18000b893  mov     r9d, esi; char *
0x18000b896  mov     edx, 6Fh ; 'o'; void *
0x18000b89b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8a0  mov     rcx, [rbp+188h]; this
0x18000b8a7  lea     r8, aWil; "wil"
0x18000b8ae  mov     r9d, esi; char *
0x18000b8b1  mov     edx, 12Eh; void *
0x18000b8b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8bb  test    rdi, rdi
0x18000b8be  jz      short loc_18000B8D1
0x18000b8c0  mov     rcx, rdi; hMutex
0x18000b8c3  call    cs:__imp_ReleaseMutex
0x18000b8c9  test    eax, eax
0x18000b8cb  jz      loc_18000BAD8
0x18000b8d1  mov     rcx, rbx; hObject
0x18000b8d4  call    cs:__imp_CloseHandle
0x18000b8da  test    eax, eax
0x18000b8dc  jz      loc_18000BAEA
0x18000b8e2  mov     eax, esi
0x18000b8e4  jmp     loc_18000BA93
0x18000b8e9  mov     rax, [rsp+280h+hObject]
0x18000b8ee  lea     rcx, ds:0[rax*4]
0x18000b8f6  test    rcx, rcx
0x18000b8f9  jz      short loc_18000B909
0x18000b8fb  mov     [r15], rcx
0x18000b8fe  mov     eax, [rcx]
0x18000b900  inc     eax
0x18000b902  mov     [rcx], eax
0x18000b904  jmp     loc_18000BA69
0x18000b909  mov     rdx, r14; dwBytes
0x18000b90c  mov     qword ptr [r15], 0
0x18000b913  mov     ecx, 8; dwFlags
0x18000b918  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b91d  mov     rsi, rax
0x18000b920  test    rax, rax
0x18000b923  jnz     short loc_18000B94B
0x18000b925  mov     rcx, [rbp+188h]; this
0x18000b92c  lea     r8, aWil; "wil"
0x18000b933  mov     r14d, 8007000Eh
0x18000b939  mov     edx, 14Bh; void *
0x18000b93e  mov     r9d, r14d; char *
0x18000b941  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b946  jmp     loc_18000B9DE
0x18000b94b  xorps   xmm0, xmm0
0x18000b94e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000b954  test    sil, 3
0x18000b958  jnz     loc_18000BAFC
0x18000b95e  mov     r9, rsi
0x18000b961  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000b966  shr     r9, 2; unsigned __int64
0x18000b96a  lea     rcx, [rsp+280h+hObject]; this
0x18000b96f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x18000b974  mov     r14d, eax
0x18000b977  test    eax, eax
0x18000b979  jns     loc_18000BA25
0x18000b97f  mov     rcx, [rbp+188h]; this
0x18000b986  lea     r8, aWil; "wil"
0x18000b98d  mov     r9d, eax; char *
0x18000b990  mov     edx, 14Eh; void *
0x18000b995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b99a  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000b99f  test    rcx, rcx
0x18000b9a2  jz      short loc_18000B9B2
0x18000b9a4  call    cs:__imp_CloseHandle
0x18000b9aa  test    eax, eax
0x18000b9ac  jz      loc_18000BB02
0x18000b9b2  mov     rcx, [rsp+280h+hObject]; hObject
0x18000b9b7  test    rcx, rcx
0x18000b9ba  jz      short loc_18000B9CA
0x18000b9bc  call    cs:__imp_CloseHandle
0x18000b9c2  test    eax, eax
0x18000b9c4  jz      loc_18000BB14
0x18000b9ca  call    cs:__imp_GetProcessHeap
0x18000b9d0  mov     r8, rsi; lpMem
0x18000b9d3  xor     edx, edx; dwFlags
0x18000b9d5  mov     rcx, rax; hHeap
0x18000b9d8  call    cs:__imp_HeapFree
0x18000b9de  mov     rcx, [rbp+188h]; this
0x18000b9e5  lea     r8, aWil; "wil"
0x18000b9ec  mov     r9d, r14d; char *
0x18000b9ef  mov     edx, 137h; void *
0x18000b9f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9f9  test    rdi, rdi
0x18000b9fc  jz      short loc_18000BA0F
0x18000b9fe  mov     rcx, rdi; hMutex
0x18000ba01  call    cs:__imp_ReleaseMutex
0x18000ba07  test    eax, eax
0x18000ba09  jz      loc_18000BB26
0x18000ba0f  mov     rcx, rbx; hObject
0x18000ba12  call    cs:__imp_CloseHandle
0x18000ba18  test    eax, eax
0x18000ba1a  jz      loc_18000BB38
0x18000ba20  mov     eax, r14d
0x18000ba23  jmp     short loc_18000BA93
0x18000ba25  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000ba2a  xor     edx, edx; Val
0x18000ba2c  mov     dword ptr [rsi], 1
0x18000ba32  lea     rcx, [rsi+22h]; void *
0x18000ba36  mov     [rsi+8], rbx
0x18000ba3a  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000ba3f  lea     r8d, [rdx+56h]; Size
0x18000ba43  call    memset_0
0x18000ba48  xor     edx, edx; Val
0x18000ba4a  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000ba50  lea     rcx, [rsi+28h]; void *
0x18000ba54  mov     dword ptr [rsi+24h], 1
0x18000ba5b  lea     r8d, [rdx+50h]; Size
0x18000ba5f  call    memset_0
0x18000ba64  xor     ebx, ebx
0x18000ba66  mov     [r15], rsi
0x18000ba69  test    rdi, rdi
0x18000ba6c  jz      short loc_18000BA7F
0x18000ba6e  mov     rcx, rdi; hMutex
0x18000ba71  call    cs:__imp_ReleaseMutex
0x18000ba77  test    eax, eax
0x18000ba79  jz      loc_18000BB4A
0x18000ba7f  test    rbx, rbx
0x18000ba82  jz      short loc_18000BA91
0x18000ba84  mov     rcx, rbx; hObject
0x18000ba87  call    cs:__imp_CloseHandle
0x18000ba8d  test    eax, eax
0x18000ba8f  jz      short loc_18000BAB9
0x18000ba91  xor     eax, eax
0x18000ba93  mov     rcx, [rbp+180h+var_30]
0x18000ba9a  xor     rcx, rsp; StackCookie
0x18000ba9d  call    __security_check_cookie
0x18000baa2  mov     rbx, [rsp+280h+arg_10]
0x18000baaa  add     rsp, 260h
0x18000bab1  pop     r15
0x18000bab3  pop     r14
0x18000bab5  pop     rdi
0x18000bab6  pop     rsi
0x18000bab7  pop     rbp
0x18000bab8  retn
0x18000bab9  mov     rcx, [rbp+188h]; this
0x18000bac0  mov     edx, 0A0Bh; void *
0x18000bac5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bacb  mov     rcx, [rbp+188h]; this
0x18000bad2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000bad8  mov     rcx, [rbp+188h]; this
0x18000badf  mov     edx, 0A15h; void *
0x18000bae4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000baea  mov     rcx, [rbp+188h]; this
0x18000baf1  mov     edx, 0A0Bh; void *
0x18000baf6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bafc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000bb02  mov     rcx, [rbp+188h]; this
0x18000bb09  mov     edx, 0A0Bh; void *
0x18000bb0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb14  mov     rcx, [rbp+188h]; this
0x18000bb1b  mov     edx, 0A0Bh; void *
0x18000bb20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb26  mov     rcx, [rbp+188h]; this
0x18000bb2d  mov     edx, 0A15h; void *
0x18000bb32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb38  mov     rcx, [rbp+188h]; this
0x18000bb3f  mov     edx, 0A0Bh; void *
0x18000bb44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bb4a  mov     rcx, [rbp+188h]; this
0x18000bb51  mov     edx, 0A15h; void *
0x18000bb56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
