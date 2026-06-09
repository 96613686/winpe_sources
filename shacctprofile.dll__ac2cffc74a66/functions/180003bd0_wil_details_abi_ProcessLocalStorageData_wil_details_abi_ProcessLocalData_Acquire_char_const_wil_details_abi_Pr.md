# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003bd0`
- end: `0x180003f6e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004a5c`

## callees

- `0x180002230`
- `0x180002b8e`
- `0x180003bd0`
- `0x180003f74`
- `0x1800041b0`
- `0x1800047f8`
- `0x1800052c8`
- `0x180005584`
- `0x180005968`
- `0x1800059f4`
- `0x180005dac`
- `0x180005dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e13`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e13`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003c69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c48`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003de3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003de3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003df1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e99`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x180003bd0  mov     [rsp-8+arg_10], rbx
0x180003bd5  push    rbp
0x180003bd6  push    rsi
0x180003bd7  push    rdi
0x180003bd8  push    r14
0x180003bda  push    r15
0x180003bdc  lea     rbp, [rsp-160h]
0x180003be4  sub     rsp, 260h
0x180003beb  mov     rax, cs:__security_cookie
0x180003bf2  xor     rax, rsp
0x180003bf5  mov     [rbp+180h+var_30], rax
0x180003bfc  mov     r15, rdx
0x180003bff  mov     qword ptr [rdx], 0
0x180003c06  mov     rbx, rcx
0x180003c09  call    cs:__imp_GetCurrentProcessId
0x180003c0f  mov     r14d, 78h ; 'x'
0x180003c15  mov     [rsp+280h+var_258], rbx
0x180003c1a  mov     r9d, eax
0x180003c1d  mov     [rsp+280h+var_260], r14d; int
0x180003c22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c29  mov     edx, 104h; unsigned __int64
0x180003c2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c38  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c3e  lea     rdx, [rsp+280h+Name]; lpName
0x180003c43  xor     r8d, r8d; dwFlags
0x180003c46  xor     ecx, ecx; lpMutexAttributes
0x180003c48  call    cs:__imp_CreateMutexExW
0x180003c4e  mov     rbx, rax
0x180003c51  test    rax, rax
0x180003c54  jnz     short loc_180003C60
0x180003c56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c5b  jmp     loc_180003EA5
0x180003c60  xor     r8d, r8d; bAlertable
0x180003c63  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003c66  mov     rcx, rbx; hHandle
0x180003c69  call    cs:__imp_WaitForSingleObjectEx
0x180003c6f  cmp     eax, 102h
0x180003c74  jz      short loc_180003C86
0x180003c76  test    eax, 0FFFFFF7Fh
0x180003c7b  jnz     loc_180003EDD
0x180003c81  mov     rdi, rbx
0x180003c84  jmp     short loc_180003C88
0x180003c86  xor     edi, edi
0x180003c88  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003c8d  mov     [rsp+280h+hObject], 0
0x180003c96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c9b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ca0  mov     esi, eax
0x180003ca2  test    eax, eax
0x180003ca4  jns     short loc_180003D10
0x180003ca6  mov     rcx, [rbp+188h]; this
0x180003cad  mov     r9d, eax; char *
0x180003cb0  mov     edx, 66h ; 'f'; void *
0x180003cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cba  mov     rcx, [rbp+188h]; this
0x180003cc1  mov     r9d, esi; char *
0x180003cc4  mov     edx, 6Fh ; 'o'; void *
0x180003cc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cce  mov     rcx, [rbp+188h]; this
0x180003cd5  mov     r9d, esi; char *
0x180003cd8  mov     edx, 12Eh; void *
0x180003cdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ce2  test    rdi, rdi
0x180003ce5  jz      short loc_180003CF8
0x180003ce7  mov     rcx, rdi; hMutex
0x180003cea  call    cs:__imp_ReleaseMutex
0x180003cf0  test    eax, eax
0x180003cf2  jz      loc_180003EEA
0x180003cf8  mov     rcx, rbx; hObject
0x180003cfb  call    cs:__imp_CloseHandle
0x180003d01  test    eax, eax
0x180003d03  jz      loc_180003EFC
0x180003d09  mov     eax, esi
0x180003d0b  jmp     loc_180003EA5
0x180003d10  mov     rax, [rsp+280h+hObject]
0x180003d15  lea     rcx, ds:0[rax*4]
0x180003d1d  test    rcx, rcx
0x180003d20  jz      short loc_180003D30
0x180003d22  mov     [r15], rcx
0x180003d25  mov     eax, [rcx]
0x180003d27  inc     eax
0x180003d29  mov     [rcx], eax
0x180003d2b  jmp     loc_180003E7B
0x180003d30  mov     rdx, r14; dwBytes
0x180003d33  mov     qword ptr [r15], 0
0x180003d3a  mov     ecx, 8; dwFlags
0x180003d3f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d44  mov     rsi, rax
0x180003d47  test    rax, rax
0x180003d4a  jnz     short loc_180003D6B
0x180003d4c  mov     rcx, [rbp+188h]; this
0x180003d53  mov     r14d, 8007000Eh
0x180003d59  mov     r9d, r14d; char *
0x180003d5c  mov     edx, 14Bh; void *
0x180003d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d66  jmp     loc_180003DF7
0x180003d6b  xorps   xmm0, xmm0
0x180003d6e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003d74  test    sil, 3
0x180003d78  jnz     loc_180003F0E
0x180003d7e  mov     r9, rsi
0x180003d81  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003d86  shr     r9, 2; unsigned __int64
0x180003d8a  lea     rcx, [rsp+280h+hObject]; this
0x180003d8f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003d94  mov     r14d, eax
0x180003d97  test    eax, eax
0x180003d99  jns     loc_180003E37
0x180003d9f  mov     rcx, [rbp+188h]; this
0x180003da6  mov     r9d, eax; char *
0x180003da9  mov     edx, 14Eh; void *
0x180003dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003db3  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003db8  test    rcx, rcx
0x180003dbb  jz      short loc_180003DCB
0x180003dbd  call    cs:__imp_CloseHandle
0x180003dc3  test    eax, eax
0x180003dc5  jz      loc_180003F14
0x180003dcb  mov     rcx, [rsp+280h+hObject]; hObject
0x180003dd0  test    rcx, rcx
0x180003dd3  jz      short loc_180003DE3
0x180003dd5  call    cs:__imp_CloseHandle
0x180003ddb  test    eax, eax
0x180003ddd  jz      loc_180003F26
0x180003de3  call    cs:__imp_GetProcessHeap
0x180003de9  mov     r8, rsi; lpMem
0x180003dec  xor     edx, edx; dwFlags
0x180003dee  mov     rcx, rax; hHeap
0x180003df1  call    cs:__imp_HeapFree
0x180003df7  mov     rcx, [rbp+188h]; this
0x180003dfe  mov     r9d, r14d; char *
0x180003e01  mov     edx, 137h; void *
0x180003e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e0b  test    rdi, rdi
0x180003e0e  jz      short loc_180003E21
0x180003e10  mov     rcx, rdi; hMutex
0x180003e13  call    cs:__imp_ReleaseMutex
0x180003e19  test    eax, eax
0x180003e1b  jz      loc_180003F38
0x180003e21  mov     rcx, rbx; hObject
0x180003e24  call    cs:__imp_CloseHandle
0x180003e2a  test    eax, eax
0x180003e2c  jz      loc_180003F4A
0x180003e32  mov     eax, r14d
0x180003e35  jmp     short loc_180003EA5
0x180003e37  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e3c  xor     edx, edx; Val
0x180003e3e  mov     dword ptr [rsi], 1
0x180003e44  lea     rcx, [rsi+22h]; void *
0x180003e48  mov     [rsi+8], rbx
0x180003e4c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003e51  lea     r8d, [rdx+56h]; Size
0x180003e55  call    memset_0
0x180003e5a  xor     edx, edx; Val
0x180003e5c  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003e62  lea     rcx, [rsi+28h]; void *
0x180003e66  mov     dword ptr [rsi+24h], 1
0x180003e6d  lea     r8d, [rdx+50h]; Size
0x180003e71  call    memset_0
0x180003e76  xor     ebx, ebx
0x180003e78  mov     [r15], rsi
0x180003e7b  test    rdi, rdi
0x180003e7e  jz      short loc_180003E91
0x180003e80  mov     rcx, rdi; hMutex
0x180003e83  call    cs:__imp_ReleaseMutex
0x180003e89  test    eax, eax
0x180003e8b  jz      loc_180003F5C
0x180003e91  test    rbx, rbx
0x180003e94  jz      short loc_180003EA3
0x180003e96  mov     rcx, rbx; hObject
0x180003e99  call    cs:__imp_CloseHandle
0x180003e9f  test    eax, eax
0x180003ea1  jz      short loc_180003ECB
0x180003ea3  xor     eax, eax
0x180003ea5  mov     rcx, [rbp+180h+var_30]
0x180003eac  xor     rcx, rsp; StackCookie
0x180003eaf  call    __security_check_cookie
0x180003eb4  mov     rbx, [rsp+280h+arg_10]
0x180003ebc  add     rsp, 260h
0x180003ec3  pop     r15
0x180003ec5  pop     r14
0x180003ec7  pop     rdi
0x180003ec8  pop     rsi
0x180003ec9  pop     rbp
0x180003eca  retn
0x180003ecb  mov     rcx, [rbp+188h]; this
0x180003ed2  mov     edx, 0A0Bh; void *
0x180003ed7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003edd  mov     rcx, [rbp+188h]; this
0x180003ee4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003eea  mov     rcx, [rbp+188h]; this
0x180003ef1  mov     edx, 0A15h; void *
0x180003ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003efc  mov     rcx, [rbp+188h]; this
0x180003f03  mov     edx, 0A0Bh; void *
0x180003f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f14  mov     rcx, [rbp+188h]; this
0x180003f1b  mov     edx, 0A0Bh; void *
0x180003f20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f26  mov     rcx, [rbp+188h]; this
0x180003f2d  mov     edx, 0A0Bh; void *
0x180003f32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f38  mov     rcx, [rbp+188h]; this
0x180003f3f  mov     edx, 0A15h; void *
0x180003f44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f4a  mov     rcx, [rbp+188h]; this
0x180003f51  mov     edx, 0A0Bh; void *
0x180003f56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f5c  mov     rcx, [rbp+188h]; this
0x180003f63  mov     edx, 0A15h; void *
0x180003f68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
