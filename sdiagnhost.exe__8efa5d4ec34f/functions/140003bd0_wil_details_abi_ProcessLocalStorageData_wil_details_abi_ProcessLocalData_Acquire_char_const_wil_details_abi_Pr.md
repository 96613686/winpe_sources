# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003bd0`
- end: `0x140003f6e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400049d0`

## callees

- `0x140001c8f`
- `0x140003bd0`
- `0x140003f74`
- `0x1400041a0`
- `0x140004760`
- `0x140005254`
- `0x14000553c`
- `0x1400068c0`
- `0x14000697c`
- `0x140006e2c`
- `0x140006e3c`
- `0x140007770`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140003c48`
- `KERNEL32!CreateMutexExW` at `0x140003c48`
- `KERNEL32!CloseHandle` at `0x140003cfb`
- `KERNEL32!CloseHandle` at `0x140003dbd`
- `KERNEL32!CloseHandle` at `0x140003dd5`
- `KERNEL32!CloseHandle` at `0x140003e24`
- `KERNEL32!CloseHandle` at `0x140003e99`
- `KERNEL32!CloseHandle` at `0x140003cfb`
- `KERNEL32!CloseHandle` at `0x140003dbd`
- `KERNEL32!CloseHandle` at `0x140003dd5`
- `KERNEL32!CloseHandle` at `0x140003e24`
- `KERNEL32!CloseHandle` at `0x140003e99`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003c69`
- `KERNEL32!WaitForSingleObjectEx` at `0x140003c69`
- `KERNEL32!ReleaseMutex` at `0x140003cea`
- `KERNEL32!ReleaseMutex` at `0x140003e13`
- `KERNEL32!ReleaseMutex` at `0x140003e83`
- `KERNEL32!ReleaseMutex` at `0x140003cea`
- `KERNEL32!ReleaseMutex` at `0x140003e13`
- `KERNEL32!ReleaseMutex` at `0x140003e83`
- `KERNEL32!GetCurrentProcessId` at `0x140003c09`
- `KERNEL32!GetCurrentProcessId` at `0x140003c09`
- `KERNEL32!GetProcessHeap` at `0x140003de3`
- `KERNEL32!GetProcessHeap` at `0x140003de3`
- `KERNEL32!HeapFree` at `0x140003df1`
- `KERNEL32!HeapFree` at `0x140003df1`

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
0x140003bd0  mov     [rsp-8+arg_10], rbx
0x140003bd5  push    rbp
0x140003bd6  push    rsi
0x140003bd7  push    rdi
0x140003bd8  push    r14
0x140003bda  push    r15
0x140003bdc  lea     rbp, [rsp-160h]
0x140003be4  sub     rsp, 260h
0x140003beb  mov     rax, cs:__security_cookie
0x140003bf2  xor     rax, rsp
0x140003bf5  mov     [rbp+180h+var_30], rax
0x140003bfc  mov     r15, rdx
0x140003bff  mov     qword ptr [rdx], 0
0x140003c06  mov     rbx, rcx
0x140003c09  call    cs:__imp_GetCurrentProcessId
0x140003c0f  mov     r14d, 78h ; 'x'
0x140003c15  mov     [rsp+280h+var_258], rbx
0x140003c1a  mov     r9d, eax
0x140003c1d  mov     [rsp+280h+var_260], r14d; int
0x140003c22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003c29  mov     edx, 104h; unsigned __int64
0x140003c2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003c33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003c38  mov     r9d, 1F0001h; dwDesiredAccess
0x140003c3e  lea     rdx, [rsp+280h+Name]; lpName
0x140003c43  xor     r8d, r8d; dwFlags
0x140003c46  xor     ecx, ecx; lpMutexAttributes
0x140003c48  call    cs:__imp_CreateMutexExW
0x140003c4e  mov     rbx, rax
0x140003c51  test    rax, rax
0x140003c54  jnz     short loc_140003C60
0x140003c56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003c5b  jmp     loc_140003EA5
0x140003c60  xor     r8d, r8d; bAlertable
0x140003c63  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003c66  mov     rcx, rbx; hHandle
0x140003c69  call    cs:__imp_WaitForSingleObjectEx
0x140003c6f  cmp     eax, 102h
0x140003c74  jz      short loc_140003C86
0x140003c76  test    eax, 0FFFFFF7Fh
0x140003c7b  jnz     loc_140003EDD
0x140003c81  mov     rdi, rbx
0x140003c84  jmp     short loc_140003C88
0x140003c86  xor     edi, edi
0x140003c88  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003c8d  mov     [rsp+280h+hObject], 0
0x140003c96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003c9b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003ca0  mov     esi, eax
0x140003ca2  test    eax, eax
0x140003ca4  jns     short loc_140003D10
0x140003ca6  mov     rcx, [rbp+188h]; this
0x140003cad  mov     r9d, eax; char *
0x140003cb0  mov     edx, 66h ; 'f'; void *
0x140003cb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003cba  mov     rcx, [rbp+188h]; this
0x140003cc1  mov     r9d, esi; char *
0x140003cc4  mov     edx, 6Fh ; 'o'; void *
0x140003cc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003cce  mov     rcx, [rbp+188h]; this
0x140003cd5  mov     r9d, esi; char *
0x140003cd8  mov     edx, 12Eh; void *
0x140003cdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ce2  test    rdi, rdi
0x140003ce5  jz      short loc_140003CF8
0x140003ce7  mov     rcx, rdi; hMutex
0x140003cea  call    cs:__imp_ReleaseMutex
0x140003cf0  test    eax, eax
0x140003cf2  jz      loc_140003EEA
0x140003cf8  mov     rcx, rbx; hObject
0x140003cfb  call    cs:__imp_CloseHandle
0x140003d01  test    eax, eax
0x140003d03  jz      loc_140003EFC
0x140003d09  mov     eax, esi
0x140003d0b  jmp     loc_140003EA5
0x140003d10  mov     rax, [rsp+280h+hObject]
0x140003d15  lea     rcx, ds:0[rax*4]
0x140003d1d  test    rcx, rcx
0x140003d20  jz      short loc_140003D30
0x140003d22  mov     [r15], rcx
0x140003d25  mov     eax, [rcx]
0x140003d27  inc     eax
0x140003d29  mov     [rcx], eax
0x140003d2b  jmp     loc_140003E7B
0x140003d30  mov     rdx, r14; dwBytes
0x140003d33  mov     qword ptr [r15], 0
0x140003d3a  mov     ecx, 8; dwFlags
0x140003d3f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003d44  mov     rsi, rax
0x140003d47  test    rax, rax
0x140003d4a  jnz     short loc_140003D6B
0x140003d4c  mov     rcx, [rbp+188h]; this
0x140003d53  mov     r14d, 8007000Eh
0x140003d59  mov     r9d, r14d; char *
0x140003d5c  mov     edx, 14Bh; void *
0x140003d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003d66  jmp     loc_140003DF7
0x140003d6b  xorps   xmm0, xmm0
0x140003d6e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003d74  test    sil, 3
0x140003d78  jnz     loc_140003F0E
0x140003d7e  mov     r9, rsi
0x140003d81  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003d86  shr     r9, 2; unsigned __int64
0x140003d8a  lea     rcx, [rsp+280h+hObject]; this
0x140003d8f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003d94  mov     r14d, eax
0x140003d97  test    eax, eax
0x140003d99  jns     loc_140003E37
0x140003d9f  mov     rcx, [rbp+188h]; this
0x140003da6  mov     r9d, eax; char *
0x140003da9  mov     edx, 14Eh; void *
0x140003dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003db3  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003db8  test    rcx, rcx
0x140003dbb  jz      short loc_140003DCB
0x140003dbd  call    cs:__imp_CloseHandle
0x140003dc3  test    eax, eax
0x140003dc5  jz      loc_140003F14
0x140003dcb  mov     rcx, [rsp+280h+hObject]; hObject
0x140003dd0  test    rcx, rcx
0x140003dd3  jz      short loc_140003DE3
0x140003dd5  call    cs:__imp_CloseHandle
0x140003ddb  test    eax, eax
0x140003ddd  jz      loc_140003F26
0x140003de3  call    cs:__imp_GetProcessHeap
0x140003de9  mov     r8, rsi; lpMem
0x140003dec  xor     edx, edx; dwFlags
0x140003dee  mov     rcx, rax; hHeap
0x140003df1  call    cs:__imp_HeapFree
0x140003df7  mov     rcx, [rbp+188h]; this
0x140003dfe  mov     r9d, r14d; char *
0x140003e01  mov     edx, 137h; void *
0x140003e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003e0b  test    rdi, rdi
0x140003e0e  jz      short loc_140003E21
0x140003e10  mov     rcx, rdi; hMutex
0x140003e13  call    cs:__imp_ReleaseMutex
0x140003e19  test    eax, eax
0x140003e1b  jz      loc_140003F38
0x140003e21  mov     rcx, rbx; hObject
0x140003e24  call    cs:__imp_CloseHandle
0x140003e2a  test    eax, eax
0x140003e2c  jz      loc_140003F4A
0x140003e32  mov     eax, r14d
0x140003e35  jmp     short loc_140003EA5
0x140003e37  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003e3c  xor     edx, edx; Val
0x140003e3e  mov     dword ptr [rsi], 1
0x140003e44  lea     rcx, [rsi+22h]; void *
0x140003e48  mov     [rsi+8], rbx
0x140003e4c  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003e51  lea     r8d, [rdx+56h]; Size
0x140003e55  call    memset_0
0x140003e5a  xor     edx, edx; Val
0x140003e5c  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003e62  lea     rcx, [rsi+28h]; void *
0x140003e66  mov     dword ptr [rsi+24h], 1
0x140003e6d  lea     r8d, [rdx+50h]; Size
0x140003e71  call    memset_0
0x140003e76  xor     ebx, ebx
0x140003e78  mov     [r15], rsi
0x140003e7b  test    rdi, rdi
0x140003e7e  jz      short loc_140003E91
0x140003e80  mov     rcx, rdi; hMutex
0x140003e83  call    cs:__imp_ReleaseMutex
0x140003e89  test    eax, eax
0x140003e8b  jz      loc_140003F5C
0x140003e91  test    rbx, rbx
0x140003e94  jz      short loc_140003EA3
0x140003e96  mov     rcx, rbx; hObject
0x140003e99  call    cs:__imp_CloseHandle
0x140003e9f  test    eax, eax
0x140003ea1  jz      short loc_140003ECB
0x140003ea3  xor     eax, eax
0x140003ea5  mov     rcx, [rbp+180h+var_30]
0x140003eac  xor     rcx, rsp; StackCookie
0x140003eaf  call    __security_check_cookie
0x140003eb4  mov     rbx, [rsp+280h+arg_10]
0x140003ebc  add     rsp, 260h
0x140003ec3  pop     r15
0x140003ec5  pop     r14
0x140003ec7  pop     rdi
0x140003ec8  pop     rsi
0x140003ec9  pop     rbp
0x140003eca  retn
0x140003ecb  mov     rcx, [rbp+188h]; this
0x140003ed2  mov     edx, 0A0Bh; void *
0x140003ed7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003edd  mov     rcx, [rbp+188h]; this
0x140003ee4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003eea  mov     rcx, [rbp+188h]; this
0x140003ef1  mov     edx, 0A15h; void *
0x140003ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003efc  mov     rcx, [rbp+188h]; this
0x140003f03  mov     edx, 0A0Bh; void *
0x140003f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003f14  mov     rcx, [rbp+188h]; this
0x140003f1b  mov     edx, 0A0Bh; void *
0x140003f20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f26  mov     rcx, [rbp+188h]; this
0x140003f2d  mov     edx, 0A0Bh; void *
0x140003f32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f38  mov     rcx, [rbp+188h]; this
0x140003f3f  mov     edx, 0A15h; void *
0x140003f44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f4a  mov     rcx, [rbp+188h]; this
0x140003f51  mov     edx, 0A0Bh; void *
0x140003f56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f5c  mov     rcx, [rbp+188h]; this
0x140003f63  mov     edx, 0A15h; void *
0x140003f68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
