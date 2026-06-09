# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003a3c`
- end: `0x180003dda`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000526c`

## callees

- `0x180003a3c`
- `0x1800041b0`
- `0x1800046e8`
- `0x180005008`
- `0x180005ce8`
- `0x180007204`
- `0x180007758`
- `0x180007b34`
- `0x1800083ec`
- `0x1800083fc`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ab4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003ab4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ad5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ad5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b56`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003c7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003cef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d05`

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
0x180003a3c  mov     [rsp-8+arg_10], rbx
0x180003a41  push    rbp
0x180003a42  push    rsi
0x180003a43  push    rdi
0x180003a44  push    r14
0x180003a46  push    r15
0x180003a48  lea     rbp, [rsp-160h]
0x180003a50  sub     rsp, 260h
0x180003a57  mov     rax, cs:__security_cookie
0x180003a5e  xor     rax, rsp
0x180003a61  mov     [rbp+180h+var_30], rax
0x180003a68  mov     r15, rdx
0x180003a6b  mov     qword ptr [rdx], 0
0x180003a72  mov     rbx, rcx
0x180003a75  call    cs:__imp_GetCurrentProcessId
0x180003a7b  mov     r14d, 78h ; 'x'
0x180003a81  mov     [rsp+280h+var_258], rbx
0x180003a86  mov     r9d, eax
0x180003a89  mov     [rsp+280h+var_260], r14d; int
0x180003a8e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003a95  mov     edx, 104h; unsigned __int64
0x180003a9a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003a9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003aa4  mov     r9d, 1F0001h; dwDesiredAccess
0x180003aaa  lea     rdx, [rsp+280h+Name]; lpName
0x180003aaf  xor     r8d, r8d; dwFlags
0x180003ab2  xor     ecx, ecx; lpMutexAttributes
0x180003ab4  call    cs:__imp_CreateMutexExW
0x180003aba  mov     rbx, rax
0x180003abd  test    rax, rax
0x180003ac0  jnz     short loc_180003ACC
0x180003ac2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003ac7  jmp     loc_180003D11
0x180003acc  xor     r8d, r8d; bAlertable
0x180003acf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003ad2  mov     rcx, rbx; hHandle
0x180003ad5  call    cs:__imp_WaitForSingleObjectEx
0x180003adb  cmp     eax, 102h
0x180003ae0  jz      short loc_180003AF2
0x180003ae2  test    eax, 0FFFFFF7Fh
0x180003ae7  jnz     loc_180003D49
0x180003aed  mov     rdi, rbx
0x180003af0  jmp     short loc_180003AF4
0x180003af2  xor     edi, edi
0x180003af4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003af9  mov     [rsp+280h+hObject], 0
0x180003b02  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b07  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003b0c  mov     esi, eax
0x180003b0e  test    eax, eax
0x180003b10  jns     short loc_180003B7C
0x180003b12  mov     rcx, [rbp+188h]; this
0x180003b19  mov     r9d, eax; char *
0x180003b1c  mov     edx, 66h ; 'f'; void *
0x180003b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b26  mov     rcx, [rbp+188h]; this
0x180003b2d  mov     r9d, esi; char *
0x180003b30  mov     edx, 6Fh ; 'o'; void *
0x180003b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b3a  mov     rcx, [rbp+188h]; this
0x180003b41  mov     r9d, esi; char *
0x180003b44  mov     edx, 12Eh; void *
0x180003b49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b4e  test    rdi, rdi
0x180003b51  jz      short loc_180003B64
0x180003b53  mov     rcx, rdi; hMutex
0x180003b56  call    cs:__imp_ReleaseMutex
0x180003b5c  test    eax, eax
0x180003b5e  jz      loc_180003D56
0x180003b64  mov     rcx, rbx; hObject
0x180003b67  call    cs:__imp_CloseHandle
0x180003b6d  test    eax, eax
0x180003b6f  jz      loc_180003D68
0x180003b75  mov     eax, esi
0x180003b77  jmp     loc_180003D11
0x180003b7c  mov     rax, [rsp+280h+hObject]
0x180003b81  lea     rcx, ds:0[rax*4]
0x180003b89  test    rcx, rcx
0x180003b8c  jz      short loc_180003B9C
0x180003b8e  mov     [r15], rcx
0x180003b91  mov     eax, [rcx]
0x180003b93  inc     eax
0x180003b95  mov     [rcx], eax
0x180003b97  jmp     loc_180003CE7
0x180003b9c  mov     rdx, r14; dwBytes
0x180003b9f  mov     qword ptr [r15], 0
0x180003ba6  mov     ecx, 8; dwFlags
0x180003bab  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003bb0  mov     rsi, rax
0x180003bb3  test    rax, rax
0x180003bb6  jnz     short loc_180003BD7
0x180003bb8  mov     rcx, [rbp+188h]; this
0x180003bbf  mov     r14d, 8007000Eh
0x180003bc5  mov     r9d, r14d; char *
0x180003bc8  mov     edx, 14Bh; void *
0x180003bcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bd2  jmp     loc_180003C63
0x180003bd7  xorps   xmm0, xmm0
0x180003bda  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003be0  test    sil, 3
0x180003be4  jnz     loc_180003D7A
0x180003bea  mov     r9, rsi
0x180003bed  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003bf2  shr     r9, 2; unsigned __int64
0x180003bf6  lea     rcx, [rsp+280h+hObject]; this
0x180003bfb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003c00  mov     r14d, eax
0x180003c03  test    eax, eax
0x180003c05  jns     loc_180003CA3
0x180003c0b  mov     rcx, [rbp+188h]; this
0x180003c12  mov     r9d, eax; char *
0x180003c15  mov     edx, 14Eh; void *
0x180003c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003c24  test    rcx, rcx
0x180003c27  jz      short loc_180003C37
0x180003c29  call    cs:__imp_CloseHandle
0x180003c2f  test    eax, eax
0x180003c31  jz      loc_180003D80
0x180003c37  mov     rcx, [rsp+280h+hObject]; hObject
0x180003c3c  test    rcx, rcx
0x180003c3f  jz      short loc_180003C4F
0x180003c41  call    cs:__imp_CloseHandle
0x180003c47  test    eax, eax
0x180003c49  jz      loc_180003D92
0x180003c4f  call    cs:__imp_GetProcessHeap
0x180003c55  mov     r8, rsi; lpMem
0x180003c58  xor     edx, edx; dwFlags
0x180003c5a  mov     rcx, rax; hHeap
0x180003c5d  call    cs:__imp_HeapFree
0x180003c63  mov     rcx, [rbp+188h]; this
0x180003c6a  mov     r9d, r14d; char *
0x180003c6d  mov     edx, 137h; void *
0x180003c72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c77  test    rdi, rdi
0x180003c7a  jz      short loc_180003C8D
0x180003c7c  mov     rcx, rdi; hMutex
0x180003c7f  call    cs:__imp_ReleaseMutex
0x180003c85  test    eax, eax
0x180003c87  jz      loc_180003DA4
0x180003c8d  mov     rcx, rbx; hObject
0x180003c90  call    cs:__imp_CloseHandle
0x180003c96  test    eax, eax
0x180003c98  jz      loc_180003DB6
0x180003c9e  mov     eax, r14d
0x180003ca1  jmp     short loc_180003D11
0x180003ca3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003ca8  xor     edx, edx; Val
0x180003caa  mov     dword ptr [rsi], 1
0x180003cb0  lea     rcx, [rsi+22h]; void *
0x180003cb4  mov     [rsi+8], rbx
0x180003cb8  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003cbd  lea     r8d, [rdx+56h]; Size
0x180003cc1  call    memset_0
0x180003cc6  xor     edx, edx; Val
0x180003cc8  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003cce  lea     rcx, [rsi+28h]; void *
0x180003cd2  mov     dword ptr [rsi+24h], 1
0x180003cd9  lea     r8d, [rdx+50h]; Size
0x180003cdd  call    memset_0
0x180003ce2  xor     ebx, ebx
0x180003ce4  mov     [r15], rsi
0x180003ce7  test    rdi, rdi
0x180003cea  jz      short loc_180003CFD
0x180003cec  mov     rcx, rdi; hMutex
0x180003cef  call    cs:__imp_ReleaseMutex
0x180003cf5  test    eax, eax
0x180003cf7  jz      loc_180003DC8
0x180003cfd  test    rbx, rbx
0x180003d00  jz      short loc_180003D0F
0x180003d02  mov     rcx, rbx; hObject
0x180003d05  call    cs:__imp_CloseHandle
0x180003d0b  test    eax, eax
0x180003d0d  jz      short loc_180003D37
0x180003d0f  xor     eax, eax
0x180003d11  mov     rcx, [rbp+180h+var_30]
0x180003d18  xor     rcx, rsp; StackCookie
0x180003d1b  call    __security_check_cookie
0x180003d20  mov     rbx, [rsp+280h+arg_10]
0x180003d28  add     rsp, 260h
0x180003d2f  pop     r15
0x180003d31  pop     r14
0x180003d33  pop     rdi
0x180003d34  pop     rsi
0x180003d35  pop     rbp
0x180003d36  retn
0x180003d37  mov     rcx, [rbp+188h]; this
0x180003d3e  mov     edx, 0A0Bh; void *
0x180003d43  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d49  mov     rcx, [rbp+188h]; this
0x180003d50  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003d56  mov     rcx, [rbp+188h]; this
0x180003d5d  mov     edx, 0A15h; void *
0x180003d62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d68  mov     rcx, [rbp+188h]; this
0x180003d6f  mov     edx, 0A0Bh; void *
0x180003d74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d7a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003d80  mov     rcx, [rbp+188h]; this
0x180003d87  mov     edx, 0A0Bh; void *
0x180003d8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d92  mov     rcx, [rbp+188h]; this
0x180003d99  mov     edx, 0A0Bh; void *
0x180003d9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da4  mov     rcx, [rbp+188h]; this
0x180003dab  mov     edx, 0A15h; void *
0x180003db0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003db6  mov     rcx, [rbp+188h]; this
0x180003dbd  mov     edx, 0A0Bh; void *
0x180003dc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003dc8  mov     rcx, [rbp+188h]; this
0x180003dcf  mov     edx, 0A15h; void *
0x180003dd4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
