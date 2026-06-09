# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007864`
- end: `0x180007c31`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000881c`

## callees

- `0x1800032e0`
- `0x180003da4`
- `0x1800061b4`
- `0x180006348`
- `0x180007864`
- `0x180007c38`
- `0x180007f54`
- `0x180008478`
- `0x180008c88`
- `0x180009044`
- `0x1800096a4`
- `0x180009d5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000789d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000789d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800078dc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800078dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007993`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ad1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b41`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007993`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007ad1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007b41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078fd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ae2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ae2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b57`

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
0x180007864  mov     [rsp-8+arg_10], rbx
0x180007869  push    rbp
0x18000786a  push    rsi
0x18000786b  push    rdi
0x18000786c  push    r14
0x18000786e  push    r15
0x180007870  lea     rbp, [rsp-160h]
0x180007878  sub     rsp, 260h
0x18000787f  mov     rax, cs:__security_cookie
0x180007886  xor     rax, rsp
0x180007889  mov     [rbp+180h+var_30], rax
0x180007890  mov     r15, rdx
0x180007893  mov     qword ptr [rdx], 0
0x18000789a  mov     rbx, rcx
0x18000789d  call    cs:__imp_GetCurrentProcessId
0x1800078a3  mov     r14d, 78h ; 'x'
0x1800078a9  mov     [rsp+280h+var_258], rbx
0x1800078ae  mov     r9d, eax
0x1800078b1  mov     [rsp+280h+var_260], r14d; int
0x1800078b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800078bd  mov     edx, 104h; unsigned __int64
0x1800078c2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800078c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800078cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800078d2  lea     rdx, [rsp+280h+Name]; lpName
0x1800078d7  xor     r8d, r8d; dwFlags
0x1800078da  xor     ecx, ecx; lpMutexAttributes
0x1800078dc  call    cs:__imp_CreateMutexExW
0x1800078e2  mov     rbx, rax
0x1800078e5  test    rax, rax
0x1800078e8  jnz     short loc_1800078F4
0x1800078ea  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800078ef  jmp     loc_180007B63
0x1800078f4  xor     r8d, r8d; bAlertable
0x1800078f7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800078fa  mov     rcx, rbx; hHandle
0x1800078fd  call    cs:__imp_WaitForSingleObjectEx
0x180007903  cmp     eax, 102h
0x180007908  jz      short loc_18000791A
0x18000790a  test    eax, 0FFFFFF7Fh
0x18000790f  jnz     loc_180007B9B
0x180007915  mov     rdi, rbx
0x180007918  jmp     short loc_18000791C
0x18000791a  xor     edi, edi
0x18000791c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180007921  mov     [rsp+280h+hObject], 0
0x18000792a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000792f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007934  mov     esi, eax
0x180007936  test    eax, eax
0x180007938  jns     short loc_1800079B9
0x18000793a  mov     rcx, [rbp+188h]; this
0x180007941  lea     r8, aWil; "wil"
0x180007948  mov     r9d, eax; char *
0x18000794b  mov     edx, 66h ; 'f'; void *
0x180007950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007955  mov     rcx, [rbp+188h]; this
0x18000795c  lea     r8, aWil; "wil"
0x180007963  mov     r9d, esi; char *
0x180007966  mov     edx, 6Fh ; 'o'; void *
0x18000796b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007970  mov     rcx, [rbp+188h]; this
0x180007977  lea     r8, aWil; "wil"
0x18000797e  mov     r9d, esi; char *
0x180007981  mov     edx, 12Eh; void *
0x180007986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000798b  test    rdi, rdi
0x18000798e  jz      short loc_1800079A1
0x180007990  mov     rcx, rdi; hMutex
0x180007993  call    cs:__imp_ReleaseMutex
0x180007999  test    eax, eax
0x18000799b  jz      loc_180007BAD
0x1800079a1  mov     rcx, rbx; hObject
0x1800079a4  call    cs:__imp_CloseHandle
0x1800079aa  test    eax, eax
0x1800079ac  jz      loc_180007BBF
0x1800079b2  mov     eax, esi
0x1800079b4  jmp     loc_180007B63
0x1800079b9  mov     rax, [rsp+280h+hObject]
0x1800079be  lea     rcx, ds:0[rax*4]
0x1800079c6  test    rcx, rcx
0x1800079c9  jz      short loc_1800079D9
0x1800079cb  mov     [r15], rcx
0x1800079ce  mov     eax, [rcx]
0x1800079d0  inc     eax
0x1800079d2  mov     [rcx], eax
0x1800079d4  jmp     loc_180007B39
0x1800079d9  mov     rdx, r14; dwBytes
0x1800079dc  mov     qword ptr [r15], 0
0x1800079e3  mov     ecx, 8; dwFlags
0x1800079e8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800079ed  mov     rsi, rax
0x1800079f0  test    rax, rax
0x1800079f3  jnz     short loc_180007A1B
0x1800079f5  mov     rcx, [rbp+188h]; this
0x1800079fc  lea     r8, aWil; "wil"
0x180007a03  mov     r14d, 8007000Eh
0x180007a09  mov     edx, 14Bh; void *
0x180007a0e  mov     r9d, r14d; char *
0x180007a11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a16  jmp     loc_180007AAE
0x180007a1b  xorps   xmm0, xmm0
0x180007a1e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180007a24  test    sil, 3
0x180007a28  jnz     loc_180007BD1
0x180007a2e  mov     r9, rsi
0x180007a31  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180007a36  shr     r9, 2; unsigned __int64
0x180007a3a  lea     rcx, [rsp+280h+hObject]; this
0x180007a3f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007a44  mov     r14d, eax
0x180007a47  test    eax, eax
0x180007a49  jns     loc_180007AF5
0x180007a4f  mov     rcx, [rbp+188h]; this
0x180007a56  lea     r8, aWil; "wil"
0x180007a5d  mov     r9d, eax; char *
0x180007a60  mov     edx, 14Eh; void *
0x180007a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a6a  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007a6f  test    rcx, rcx
0x180007a72  jz      short loc_180007A82
0x180007a74  call    cs:__imp_CloseHandle
0x180007a7a  test    eax, eax
0x180007a7c  jz      loc_180007BD7
0x180007a82  mov     rcx, [rsp+280h+hObject]; hObject
0x180007a87  test    rcx, rcx
0x180007a8a  jz      short loc_180007A9A
0x180007a8c  call    cs:__imp_CloseHandle
0x180007a92  test    eax, eax
0x180007a94  jz      loc_180007BE9
0x180007a9a  call    cs:__imp_GetProcessHeap
0x180007aa0  mov     r8, rsi; lpMem
0x180007aa3  xor     edx, edx; dwFlags
0x180007aa5  mov     rcx, rax; hHeap
0x180007aa8  call    cs:__imp_HeapFree
0x180007aae  mov     rcx, [rbp+188h]; this
0x180007ab5  lea     r8, aWil; "wil"
0x180007abc  mov     r9d, r14d; char *
0x180007abf  mov     edx, 137h; void *
0x180007ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ac9  test    rdi, rdi
0x180007acc  jz      short loc_180007ADF
0x180007ace  mov     rcx, rdi; hMutex
0x180007ad1  call    cs:__imp_ReleaseMutex
0x180007ad7  test    eax, eax
0x180007ad9  jz      loc_180007BFB
0x180007adf  mov     rcx, rbx; hObject
0x180007ae2  call    cs:__imp_CloseHandle
0x180007ae8  test    eax, eax
0x180007aea  jz      loc_180007C0D
0x180007af0  mov     eax, r14d
0x180007af3  jmp     short loc_180007B63
0x180007af5  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007afa  xor     edx, edx; Val
0x180007afc  mov     dword ptr [rsi], 1
0x180007b02  lea     rcx, [rsi+22h]; void *
0x180007b06  mov     [rsi+8], rbx
0x180007b0a  movdqu  xmmword ptr [rsi+10h], xmm0
0x180007b0f  lea     r8d, [rdx+56h]; Size
0x180007b13  call    memset_0
0x180007b18  xor     edx, edx; Val
0x180007b1a  mov     word ptr [rsi+20h], 58h ; 'X'
0x180007b20  lea     rcx, [rsi+28h]; void *
0x180007b24  mov     dword ptr [rsi+24h], 1
0x180007b2b  lea     r8d, [rdx+50h]; Size
0x180007b2f  call    memset_0
0x180007b34  xor     ebx, ebx
0x180007b36  mov     [r15], rsi
0x180007b39  test    rdi, rdi
0x180007b3c  jz      short loc_180007B4F
0x180007b3e  mov     rcx, rdi; hMutex
0x180007b41  call    cs:__imp_ReleaseMutex
0x180007b47  test    eax, eax
0x180007b49  jz      loc_180007C1F
0x180007b4f  test    rbx, rbx
0x180007b52  jz      short loc_180007B61
0x180007b54  mov     rcx, rbx; hObject
0x180007b57  call    cs:__imp_CloseHandle
0x180007b5d  test    eax, eax
0x180007b5f  jz      short loc_180007B89
0x180007b61  xor     eax, eax
0x180007b63  mov     rcx, [rbp+180h+var_30]
0x180007b6a  xor     rcx, rsp; StackCookie
0x180007b6d  call    __security_check_cookie
0x180007b72  mov     rbx, [rsp+280h+arg_10]
0x180007b7a  add     rsp, 260h
0x180007b81  pop     r15
0x180007b83  pop     r14
0x180007b85  pop     rdi
0x180007b86  pop     rsi
0x180007b87  pop     rbp
0x180007b88  retn
0x180007b89  mov     rcx, [rbp+188h]; this
0x180007b90  mov     edx, 0A0Bh; void *
0x180007b95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b9b  mov     rcx, [rbp+188h]; this
0x180007ba2  mov     edx, 0E01h; void *
0x180007ba7  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007bad  mov     rcx, [rbp+188h]; this
0x180007bb4  mov     edx, 0A15h; void *
0x180007bb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bbf  mov     rcx, [rbp+188h]; this
0x180007bc6  mov     edx, 0A0Bh; void *
0x180007bcb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bd1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007bd7  mov     rcx, [rbp+188h]; this
0x180007bde  mov     edx, 0A0Bh; void *
0x180007be3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007be9  mov     rcx, [rbp+188h]; this
0x180007bf0  mov     edx, 0A0Bh; void *
0x180007bf5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bfb  mov     rcx, [rbp+188h]; this
0x180007c02  mov     edx, 0A15h; void *
0x180007c07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c0d  mov     rcx, [rbp+188h]; this
0x180007c14  mov     edx, 0A0Bh; void *
0x180007c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007c1f  mov     rcx, [rbp+188h]; this
0x180007c26  mov     edx, 0A15h; void *
0x180007c2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
