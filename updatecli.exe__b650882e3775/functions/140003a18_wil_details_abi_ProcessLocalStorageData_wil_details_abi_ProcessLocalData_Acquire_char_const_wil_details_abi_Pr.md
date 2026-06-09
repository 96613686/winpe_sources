# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003a18`
- end: `0x140003de0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400048e0`

## callees

- `0x140002130`
- `0x140002c38`
- `0x140003a18`
- `0x140003de8`
- `0x140004030`
- `0x140004678`
- `0x140005158`
- `0x140005434`
- `0x140005dc0`
- `0x140005e9c`
- `0x14000627c`
- `0x14000628c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003ab1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003ab1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003c85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003c85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cf5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003a90`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003a90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d0b`

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
0x140003a18  mov     [rsp-8+arg_10], rbx
0x140003a1d  push    rbp
0x140003a1e  push    rsi
0x140003a1f  push    rdi
0x140003a20  push    r14
0x140003a22  push    r15
0x140003a24  lea     rbp, [rsp-160h]
0x140003a2c  sub     rsp, 260h
0x140003a33  mov     rax, cs:__security_cookie
0x140003a3a  xor     rax, rsp
0x140003a3d  mov     [rbp+180h+var_30], rax
0x140003a44  mov     r15, rdx
0x140003a47  mov     qword ptr [rdx], 0
0x140003a4e  mov     rbx, rcx
0x140003a51  call    cs:__imp_GetCurrentProcessId
0x140003a57  mov     r14d, 78h ; 'x'
0x140003a5d  mov     [rsp+280h+var_258], rbx
0x140003a62  mov     r9d, eax
0x140003a65  mov     [rsp+280h+var_260], r14d; int
0x140003a6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003a71  mov     edx, 104h; unsigned __int64
0x140003a76  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003a7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003a80  mov     r9d, 1F0001h; dwDesiredAccess
0x140003a86  lea     rdx, [rsp+280h+Name]; lpName
0x140003a8b  xor     r8d, r8d; dwFlags
0x140003a8e  xor     ecx, ecx; lpMutexAttributes
0x140003a90  call    cs:__imp_CreateMutexExW
0x140003a96  mov     rbx, rax
0x140003a99  test    rax, rax
0x140003a9c  jnz     short loc_140003AA8
0x140003a9e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003aa3  jmp     loc_140003D17
0x140003aa8  xor     r8d, r8d; bAlertable
0x140003aab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003aae  mov     rcx, rbx; hHandle
0x140003ab1  call    cs:__imp_WaitForSingleObjectEx
0x140003ab7  cmp     eax, 102h
0x140003abc  jz      short loc_140003ACE
0x140003abe  test    eax, 0FFFFFF7Fh
0x140003ac3  jnz     loc_140003D4F
0x140003ac9  mov     rdi, rbx
0x140003acc  jmp     short loc_140003AD0
0x140003ace  xor     edi, edi
0x140003ad0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003ad5  mov     [rsp+280h+hObject], 0
0x140003ade  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003ae3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003ae8  mov     esi, eax
0x140003aea  test    eax, eax
0x140003aec  jns     short loc_140003B6D
0x140003aee  mov     rcx, [rbp+188h]; this
0x140003af5  lea     r8, aWil; "wil"
0x140003afc  mov     r9d, eax; char *
0x140003aff  mov     edx, 66h ; 'f'; void *
0x140003b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b09  mov     rcx, [rbp+188h]; this
0x140003b10  lea     r8, aWil; "wil"
0x140003b17  mov     r9d, esi; char *
0x140003b1a  mov     edx, 6Fh ; 'o'; void *
0x140003b1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b24  mov     rcx, [rbp+188h]; this
0x140003b2b  lea     r8, aWil; "wil"
0x140003b32  mov     r9d, esi; char *
0x140003b35  mov     edx, 12Eh; void *
0x140003b3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b3f  test    rdi, rdi
0x140003b42  jz      short loc_140003B55
0x140003b44  mov     rcx, rdi; hMutex
0x140003b47  call    cs:__imp_ReleaseMutex
0x140003b4d  test    eax, eax
0x140003b4f  jz      loc_140003D5C
0x140003b55  mov     rcx, rbx; hObject
0x140003b58  call    cs:__imp_CloseHandle
0x140003b5e  test    eax, eax
0x140003b60  jz      loc_140003D6E
0x140003b66  mov     eax, esi
0x140003b68  jmp     loc_140003D17
0x140003b6d  mov     rax, [rsp+280h+hObject]
0x140003b72  lea     rcx, ds:0[rax*4]
0x140003b7a  test    rcx, rcx
0x140003b7d  jz      short loc_140003B8D
0x140003b7f  mov     [r15], rcx
0x140003b82  mov     eax, [rcx]
0x140003b84  inc     eax
0x140003b86  mov     [rcx], eax
0x140003b88  jmp     loc_140003CED
0x140003b8d  mov     rdx, r14; dwBytes
0x140003b90  mov     qword ptr [r15], 0
0x140003b97  mov     ecx, 8; dwFlags
0x140003b9c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003ba1  mov     rsi, rax
0x140003ba4  test    rax, rax
0x140003ba7  jnz     short loc_140003BCF
0x140003ba9  mov     rcx, [rbp+188h]; this
0x140003bb0  lea     r8, aWil; "wil"
0x140003bb7  mov     r14d, 8007000Eh
0x140003bbd  mov     edx, 14Bh; void *
0x140003bc2  mov     r9d, r14d; char *
0x140003bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003bca  jmp     loc_140003C62
0x140003bcf  xorps   xmm0, xmm0
0x140003bd2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003bd8  test    sil, 3
0x140003bdc  jnz     loc_140003D80
0x140003be2  mov     r9, rsi
0x140003be5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003bea  shr     r9, 2; unsigned __int64
0x140003bee  lea     rcx, [rsp+280h+hObject]; this
0x140003bf3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003bf8  mov     r14d, eax
0x140003bfb  test    eax, eax
0x140003bfd  jns     loc_140003CA9
0x140003c03  mov     rcx, [rbp+188h]; this
0x140003c0a  lea     r8, aWil; "wil"
0x140003c11  mov     r9d, eax; char *
0x140003c14  mov     edx, 14Eh; void *
0x140003c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c1e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003c23  test    rcx, rcx
0x140003c26  jz      short loc_140003C36
0x140003c28  call    cs:__imp_CloseHandle
0x140003c2e  test    eax, eax
0x140003c30  jz      loc_140003D86
0x140003c36  mov     rcx, [rsp+280h+hObject]; hObject
0x140003c3b  test    rcx, rcx
0x140003c3e  jz      short loc_140003C4E
0x140003c40  call    cs:__imp_CloseHandle
0x140003c46  test    eax, eax
0x140003c48  jz      loc_140003D98
0x140003c4e  call    cs:__imp_GetProcessHeap
0x140003c54  mov     r8, rsi; lpMem
0x140003c57  xor     edx, edx; dwFlags
0x140003c59  mov     rcx, rax; hHeap
0x140003c5c  call    cs:__imp_HeapFree
0x140003c62  mov     rcx, [rbp+188h]; this
0x140003c69  lea     r8, aWil; "wil"
0x140003c70  mov     r9d, r14d; char *
0x140003c73  mov     edx, 137h; void *
0x140003c78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c7d  test    rdi, rdi
0x140003c80  jz      short loc_140003C93
0x140003c82  mov     rcx, rdi; hMutex
0x140003c85  call    cs:__imp_ReleaseMutex
0x140003c8b  test    eax, eax
0x140003c8d  jz      loc_140003DAA
0x140003c93  mov     rcx, rbx; hObject
0x140003c96  call    cs:__imp_CloseHandle
0x140003c9c  test    eax, eax
0x140003c9e  jz      loc_140003DBC
0x140003ca4  mov     eax, r14d
0x140003ca7  jmp     short loc_140003D17
0x140003ca9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003cae  xor     edx, edx; Val
0x140003cb0  mov     dword ptr [rsi], 1
0x140003cb6  lea     rcx, [rsi+22h]; void *
0x140003cba  mov     [rsi+8], rbx
0x140003cbe  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003cc3  lea     r8d, [rdx+56h]; Size
0x140003cc7  call    memset_0
0x140003ccc  xor     edx, edx; Val
0x140003cce  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003cd4  lea     rcx, [rsi+28h]; void *
0x140003cd8  mov     dword ptr [rsi+24h], 1
0x140003cdf  lea     r8d, [rdx+50h]; Size
0x140003ce3  call    memset_0
0x140003ce8  xor     ebx, ebx
0x140003cea  mov     [r15], rsi
0x140003ced  test    rdi, rdi
0x140003cf0  jz      short loc_140003D03
0x140003cf2  mov     rcx, rdi; hMutex
0x140003cf5  call    cs:__imp_ReleaseMutex
0x140003cfb  test    eax, eax
0x140003cfd  jz      loc_140003DCE
0x140003d03  test    rbx, rbx
0x140003d06  jz      short loc_140003D15
0x140003d08  mov     rcx, rbx; hObject
0x140003d0b  call    cs:__imp_CloseHandle
0x140003d11  test    eax, eax
0x140003d13  jz      short loc_140003D3D
0x140003d15  xor     eax, eax
0x140003d17  mov     rcx, [rbp+180h+var_30]
0x140003d1e  xor     rcx, rsp; StackCookie
0x140003d21  call    __security_check_cookie
0x140003d26  mov     rbx, [rsp+280h+arg_10]
0x140003d2e  add     rsp, 260h
0x140003d35  pop     r15
0x140003d37  pop     r14
0x140003d39  pop     rdi
0x140003d3a  pop     rsi
0x140003d3b  pop     rbp
0x140003d3c  retn
0x140003d3d  mov     rcx, [rbp+188h]; this
0x140003d44  mov     edx, 0A0Bh; void *
0x140003d49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d4f  mov     rcx, [rbp+188h]; this
0x140003d56  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003d5c  mov     rcx, [rbp+188h]; this
0x140003d63  mov     edx, 0A15h; void *
0x140003d68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d6e  mov     rcx, [rbp+188h]; this
0x140003d75  mov     edx, 0A0Bh; void *
0x140003d7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003d86  mov     rcx, [rbp+188h]; this
0x140003d8d  mov     edx, 0A0Bh; void *
0x140003d92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d98  mov     rcx, [rbp+188h]; this
0x140003d9f  mov     edx, 0A0Bh; void *
0x140003da4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003daa  mov     rcx, [rbp+188h]; this
0x140003db1  mov     edx, 0A15h; void *
0x140003db6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003dbc  mov     rcx, [rbp+188h]; this
0x140003dc3  mov     edx, 0A0Bh; void *
0x140003dc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003dce  mov     rcx, [rbp+188h]; this
0x140003dd5  mov     edx, 0A15h; void *
0x140003dda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
