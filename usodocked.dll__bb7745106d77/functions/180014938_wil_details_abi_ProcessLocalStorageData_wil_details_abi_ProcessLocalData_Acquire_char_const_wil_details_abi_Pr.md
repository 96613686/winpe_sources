# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180014938`
- end: `0x180014d00`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180016434`

## callees

- `0x180007660`
- `0x18000856c`
- `0x180014938`
- `0x180015114`
- `0x1800157f4`
- `0x180016128`
- `0x180016bd8`
- `0x1800183f4`
- `0x180018f7c`
- `0x1800193fc`
- `0x180019e38`
- `0x180019e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800149d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800149d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800149b0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800149b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014971`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014971`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014bb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c2b`

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
0x180014938  mov     [rsp-8+arg_10], rbx
0x18001493d  push    rbp
0x18001493e  push    rsi
0x18001493f  push    rdi
0x180014940  push    r14
0x180014942  push    r15
0x180014944  lea     rbp, [rsp-160h]
0x18001494c  sub     rsp, 260h
0x180014953  mov     rax, cs:__security_cookie
0x18001495a  xor     rax, rsp
0x18001495d  mov     [rbp+180h+var_30], rax
0x180014964  mov     r15, rdx
0x180014967  mov     qword ptr [rdx], 0
0x18001496e  mov     rbx, rcx
0x180014971  call    cs:__imp_GetCurrentProcessId
0x180014977  mov     r14d, 78h ; 'x'
0x18001497d  mov     [rsp+280h+var_258], rbx
0x180014982  mov     r9d, eax
0x180014985  mov     [rsp+280h+var_260], r14d; int
0x18001498a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180014991  mov     edx, 104h; unsigned __int64
0x180014996  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001499b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800149a0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800149a6  lea     rdx, [rsp+280h+Name]; lpName
0x1800149ab  xor     r8d, r8d; dwFlags
0x1800149ae  xor     ecx, ecx; lpMutexAttributes
0x1800149b0  call    cs:__imp_CreateMutexExW
0x1800149b6  mov     rbx, rax
0x1800149b9  test    rax, rax
0x1800149bc  jnz     short loc_1800149C8
0x1800149be  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800149c3  jmp     loc_180014C37
0x1800149c8  xor     r8d, r8d; bAlertable
0x1800149cb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800149ce  mov     rcx, rbx; hHandle
0x1800149d1  call    cs:__imp_WaitForSingleObjectEx
0x1800149d7  cmp     eax, 102h
0x1800149dc  jz      short loc_1800149EE
0x1800149de  test    eax, 0FFFFFF7Fh
0x1800149e3  jnz     loc_180014C6F
0x1800149e9  mov     rdi, rbx
0x1800149ec  jmp     short loc_1800149F0
0x1800149ee  xor     edi, edi
0x1800149f0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800149f5  mov     [rsp+280h+hObject], 0
0x1800149fe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180014a03  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180014a08  mov     esi, eax
0x180014a0a  test    eax, eax
0x180014a0c  jns     short loc_180014A8D
0x180014a0e  mov     rcx, [rbp+188h]; this
0x180014a15  lea     r8, aWil; "wil"
0x180014a1c  mov     r9d, eax; char *
0x180014a1f  mov     edx, 66h ; 'f'; void *
0x180014a24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a29  mov     rcx, [rbp+188h]; this
0x180014a30  lea     r8, aWil; "wil"
0x180014a37  mov     r9d, esi; char *
0x180014a3a  mov     edx, 6Fh ; 'o'; void *
0x180014a3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a44  mov     rcx, [rbp+188h]; this
0x180014a4b  lea     r8, aWil; "wil"
0x180014a52  mov     r9d, esi; char *
0x180014a55  mov     edx, 12Eh; void *
0x180014a5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a5f  test    rdi, rdi
0x180014a62  jz      short loc_180014A75
0x180014a64  mov     rcx, rdi; hMutex
0x180014a67  call    cs:__imp_ReleaseMutex
0x180014a6d  test    eax, eax
0x180014a6f  jz      loc_180014C7C
0x180014a75  mov     rcx, rbx; hObject
0x180014a78  call    cs:__imp_CloseHandle
0x180014a7e  test    eax, eax
0x180014a80  jz      loc_180014C8E
0x180014a86  mov     eax, esi
0x180014a88  jmp     loc_180014C37
0x180014a8d  mov     rax, [rsp+280h+hObject]
0x180014a92  lea     rcx, ds:0[rax*4]
0x180014a9a  test    rcx, rcx
0x180014a9d  jz      short loc_180014AAD
0x180014a9f  mov     [r15], rcx
0x180014aa2  mov     eax, [rcx]
0x180014aa4  inc     eax
0x180014aa6  mov     [rcx], eax
0x180014aa8  jmp     loc_180014C0D
0x180014aad  mov     rdx, r14; dwBytes
0x180014ab0  mov     qword ptr [r15], 0
0x180014ab7  mov     ecx, 8; dwFlags
0x180014abc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180014ac1  mov     rsi, rax
0x180014ac4  test    rax, rax
0x180014ac7  jnz     short loc_180014AEF
0x180014ac9  mov     rcx, [rbp+188h]; this
0x180014ad0  lea     r8, aWil; "wil"
0x180014ad7  mov     r14d, 8007000Eh
0x180014add  mov     edx, 14Bh; void *
0x180014ae2  mov     r9d, r14d; char *
0x180014ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014aea  jmp     loc_180014B82
0x180014aef  xorps   xmm0, xmm0
0x180014af2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180014af8  test    sil, 3
0x180014afc  jnz     loc_180014CA0
0x180014b02  mov     r9, rsi
0x180014b05  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180014b0a  shr     r9, 2; unsigned __int64
0x180014b0e  lea     rcx, [rsp+280h+hObject]; this
0x180014b13  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180014b18  mov     r14d, eax
0x180014b1b  test    eax, eax
0x180014b1d  jns     loc_180014BC9
0x180014b23  mov     rcx, [rbp+188h]; this
0x180014b2a  lea     r8, aWil; "wil"
0x180014b31  mov     r9d, eax; char *
0x180014b34  mov     edx, 14Eh; void *
0x180014b39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b3e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180014b43  test    rcx, rcx
0x180014b46  jz      short loc_180014B56
0x180014b48  call    cs:__imp_CloseHandle
0x180014b4e  test    eax, eax
0x180014b50  jz      loc_180014CA6
0x180014b56  mov     rcx, [rsp+280h+hObject]; hObject
0x180014b5b  test    rcx, rcx
0x180014b5e  jz      short loc_180014B6E
0x180014b60  call    cs:__imp_CloseHandle
0x180014b66  test    eax, eax
0x180014b68  jz      loc_180014CB8
0x180014b6e  call    cs:__imp_GetProcessHeap
0x180014b74  mov     r8, rsi; lpMem
0x180014b77  xor     edx, edx; dwFlags
0x180014b79  mov     rcx, rax; hHeap
0x180014b7c  call    cs:__imp_HeapFree
0x180014b82  mov     rcx, [rbp+188h]; this
0x180014b89  lea     r8, aWil; "wil"
0x180014b90  mov     r9d, r14d; char *
0x180014b93  mov     edx, 137h; void *
0x180014b98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014b9d  test    rdi, rdi
0x180014ba0  jz      short loc_180014BB3
0x180014ba2  mov     rcx, rdi; hMutex
0x180014ba5  call    cs:__imp_ReleaseMutex
0x180014bab  test    eax, eax
0x180014bad  jz      loc_180014CCA
0x180014bb3  mov     rcx, rbx; hObject
0x180014bb6  call    cs:__imp_CloseHandle
0x180014bbc  test    eax, eax
0x180014bbe  jz      loc_180014CDC
0x180014bc4  mov     eax, r14d
0x180014bc7  jmp     short loc_180014C37
0x180014bc9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180014bce  xor     edx, edx; Val
0x180014bd0  mov     dword ptr [rsi], 1
0x180014bd6  lea     rcx, [rsi+22h]; void *
0x180014bda  mov     [rsi+8], rbx
0x180014bde  movdqu  xmmword ptr [rsi+10h], xmm0
0x180014be3  lea     r8d, [rdx+56h]; Size
0x180014be7  call    memset_0
0x180014bec  xor     edx, edx; Val
0x180014bee  mov     word ptr [rsi+20h], 58h ; 'X'
0x180014bf4  lea     rcx, [rsi+28h]; void *
0x180014bf8  mov     dword ptr [rsi+24h], 1
0x180014bff  lea     r8d, [rdx+50h]; Size
0x180014c03  call    memset_0
0x180014c08  xor     ebx, ebx
0x180014c0a  mov     [r15], rsi
0x180014c0d  test    rdi, rdi
0x180014c10  jz      short loc_180014C23
0x180014c12  mov     rcx, rdi; hMutex
0x180014c15  call    cs:__imp_ReleaseMutex
0x180014c1b  test    eax, eax
0x180014c1d  jz      loc_180014CEE
0x180014c23  test    rbx, rbx
0x180014c26  jz      short loc_180014C35
0x180014c28  mov     rcx, rbx; hObject
0x180014c2b  call    cs:__imp_CloseHandle
0x180014c31  test    eax, eax
0x180014c33  jz      short loc_180014C5D
0x180014c35  xor     eax, eax
0x180014c37  mov     rcx, [rbp+180h+var_30]
0x180014c3e  xor     rcx, rsp; StackCookie
0x180014c41  call    __security_check_cookie
0x180014c46  mov     rbx, [rsp+280h+arg_10]
0x180014c4e  add     rsp, 260h
0x180014c55  pop     r15
0x180014c57  pop     r14
0x180014c59  pop     rdi
0x180014c5a  pop     rsi
0x180014c5b  pop     rbp
0x180014c5c  retn
0x180014c5d  mov     rcx, [rbp+188h]; this
0x180014c64  mov     edx, 0A0Bh; void *
0x180014c69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014c6f  mov     rcx, [rbp+188h]; this
0x180014c76  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180014c7c  mov     rcx, [rbp+188h]; this
0x180014c83  mov     edx, 0A15h; void *
0x180014c88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014c8e  mov     rcx, [rbp+188h]; this
0x180014c95  mov     edx, 0A0Bh; void *
0x180014c9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014ca0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180014ca6  mov     rcx, [rbp+188h]; this
0x180014cad  mov     edx, 0A0Bh; void *
0x180014cb2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014cb8  mov     rcx, [rbp+188h]; this
0x180014cbf  mov     edx, 0A0Bh; void *
0x180014cc4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014cca  mov     rcx, [rbp+188h]; this
0x180014cd1  mov     edx, 0A15h; void *
0x180014cd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014cdc  mov     rcx, [rbp+188h]; this
0x180014ce3  mov     edx, 0A0Bh; void *
0x180014ce8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180014cee  mov     rcx, [rbp+188h]; this
0x180014cf5  mov     edx, 0A15h; void *
0x180014cfa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
