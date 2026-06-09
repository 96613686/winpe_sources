# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003b94`
- end: `0x140003f32`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004f34`

## callees

- `0x1400015a0`
- `0x140002254`
- `0x140003b94`
- `0x140003ffc`
- `0x140004498`
- `0x140004c88`
- `0x1400058a8`
- `0x140005ed8`
- `0x140006328`
- `0x1400064cc`
- `0x140006ce8`
- `0x140006cf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003c0c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003c0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003dd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003cae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003dd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003e47`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003c2d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003c2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003db5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003db5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003da7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003bcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003bcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003de8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003de8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003e5d`

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
0x140003b94  mov     [rsp-8+arg_10], rbx
0x140003b99  push    rbp
0x140003b9a  push    rsi
0x140003b9b  push    rdi
0x140003b9c  push    r14
0x140003b9e  push    r15
0x140003ba0  lea     rbp, [rsp-160h]
0x140003ba8  sub     rsp, 260h
0x140003baf  mov     rax, cs:__security_cookie
0x140003bb6  xor     rax, rsp
0x140003bb9  mov     [rbp+180h+var_30], rax
0x140003bc0  mov     r15, rdx
0x140003bc3  mov     qword ptr [rdx], 0
0x140003bca  mov     rbx, rcx
0x140003bcd  call    cs:__imp_GetCurrentProcessId
0x140003bd3  mov     r14d, 78h ; 'x'
0x140003bd9  mov     [rsp+280h+var_258], rbx
0x140003bde  mov     r9d, eax
0x140003be1  mov     [rsp+280h+var_260], r14d; int
0x140003be6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003bed  mov     edx, 104h; unsigned __int64
0x140003bf2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003bf7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003bfc  mov     r9d, 1F0001h; dwDesiredAccess
0x140003c02  lea     rdx, [rsp+280h+Name]; lpName
0x140003c07  xor     r8d, r8d; dwFlags
0x140003c0a  xor     ecx, ecx; lpMutexAttributes
0x140003c0c  call    cs:__imp_CreateMutexExW
0x140003c12  mov     rbx, rax
0x140003c15  test    rax, rax
0x140003c18  jnz     short loc_140003C24
0x140003c1a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003c1f  jmp     loc_140003E69
0x140003c24  xor     r8d, r8d; bAlertable
0x140003c27  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003c2a  mov     rcx, rbx; hHandle
0x140003c2d  call    cs:__imp_WaitForSingleObjectEx
0x140003c33  cmp     eax, 102h
0x140003c38  jz      short loc_140003C4A
0x140003c3a  test    eax, 0FFFFFF7Fh
0x140003c3f  jnz     loc_140003EA1
0x140003c45  mov     rdi, rbx
0x140003c48  jmp     short loc_140003C4C
0x140003c4a  xor     edi, edi
0x140003c4c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003c51  mov     [rsp+280h+hObject], 0
0x140003c5a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003c5f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003c64  mov     esi, eax
0x140003c66  test    eax, eax
0x140003c68  jns     short loc_140003CD4
0x140003c6a  mov     rcx, [rbp+188h]; this
0x140003c71  mov     r9d, eax; char *
0x140003c74  mov     edx, 66h ; 'f'; void *
0x140003c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c7e  mov     rcx, [rbp+188h]; this
0x140003c85  mov     r9d, esi; char *
0x140003c88  mov     edx, 6Fh ; 'o'; void *
0x140003c8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c92  mov     rcx, [rbp+188h]; this
0x140003c99  mov     r9d, esi; char *
0x140003c9c  mov     edx, 12Eh; void *
0x140003ca1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003ca6  test    rdi, rdi
0x140003ca9  jz      short loc_140003CBC
0x140003cab  mov     rcx, rdi; hMutex
0x140003cae  call    cs:__imp_ReleaseMutex
0x140003cb4  test    eax, eax
0x140003cb6  jz      loc_140003EAE
0x140003cbc  mov     rcx, rbx; hObject
0x140003cbf  call    cs:__imp_CloseHandle
0x140003cc5  test    eax, eax
0x140003cc7  jz      loc_140003EC0
0x140003ccd  mov     eax, esi
0x140003ccf  jmp     loc_140003E69
0x140003cd4  mov     rax, [rsp+280h+hObject]
0x140003cd9  lea     rcx, ds:0[rax*4]
0x140003ce1  test    rcx, rcx
0x140003ce4  jz      short loc_140003CF4
0x140003ce6  mov     [r15], rcx
0x140003ce9  mov     eax, [rcx]
0x140003ceb  inc     eax
0x140003ced  mov     [rcx], eax
0x140003cef  jmp     loc_140003E3F
0x140003cf4  mov     rdx, r14; dwBytes
0x140003cf7  mov     qword ptr [r15], 0
0x140003cfe  mov     ecx, 8; dwFlags
0x140003d03  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003d08  mov     rsi, rax
0x140003d0b  test    rax, rax
0x140003d0e  jnz     short loc_140003D2F
0x140003d10  mov     rcx, [rbp+188h]; this
0x140003d17  mov     r14d, 8007000Eh
0x140003d1d  mov     r9d, r14d; char *
0x140003d20  mov     edx, 14Bh; void *
0x140003d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003d2a  jmp     loc_140003DBB
0x140003d2f  xorps   xmm0, xmm0
0x140003d32  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003d38  test    sil, 3
0x140003d3c  jnz     loc_140003ED2
0x140003d42  mov     r9, rsi
0x140003d45  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003d4a  shr     r9, 2; unsigned __int64
0x140003d4e  lea     rcx, [rsp+280h+hObject]; this
0x140003d53  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003d58  mov     r14d, eax
0x140003d5b  test    eax, eax
0x140003d5d  jns     loc_140003DFB
0x140003d63  mov     rcx, [rbp+188h]; this
0x140003d6a  mov     r9d, eax; char *
0x140003d6d  mov     edx, 14Eh; void *
0x140003d72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003d77  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003d7c  test    rcx, rcx
0x140003d7f  jz      short loc_140003D8F
0x140003d81  call    cs:__imp_CloseHandle
0x140003d87  test    eax, eax
0x140003d89  jz      loc_140003ED8
0x140003d8f  mov     rcx, [rsp+280h+hObject]; hObject
0x140003d94  test    rcx, rcx
0x140003d97  jz      short loc_140003DA7
0x140003d99  call    cs:__imp_CloseHandle
0x140003d9f  test    eax, eax
0x140003da1  jz      loc_140003EEA
0x140003da7  call    cs:__imp_GetProcessHeap
0x140003dad  mov     r8, rsi; lpMem
0x140003db0  xor     edx, edx; dwFlags
0x140003db2  mov     rcx, rax; hHeap
0x140003db5  call    cs:__imp_HeapFree
0x140003dbb  mov     rcx, [rbp+188h]; this
0x140003dc2  mov     r9d, r14d; char *
0x140003dc5  mov     edx, 137h; void *
0x140003dca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003dcf  test    rdi, rdi
0x140003dd2  jz      short loc_140003DE5
0x140003dd4  mov     rcx, rdi; hMutex
0x140003dd7  call    cs:__imp_ReleaseMutex
0x140003ddd  test    eax, eax
0x140003ddf  jz      loc_140003EFC
0x140003de5  mov     rcx, rbx; hObject
0x140003de8  call    cs:__imp_CloseHandle
0x140003dee  test    eax, eax
0x140003df0  jz      loc_140003F0E
0x140003df6  mov     eax, r14d
0x140003df9  jmp     short loc_140003E69
0x140003dfb  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003e00  xor     edx, edx; Val
0x140003e02  mov     dword ptr [rsi], 1
0x140003e08  lea     rcx, [rsi+22h]; void *
0x140003e0c  mov     [rsi+8], rbx
0x140003e10  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003e15  lea     r8d, [rdx+56h]; Size
0x140003e19  call    memset_0
0x140003e1e  xor     edx, edx; Val
0x140003e20  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003e26  lea     rcx, [rsi+28h]; void *
0x140003e2a  mov     dword ptr [rsi+24h], 1
0x140003e31  lea     r8d, [rdx+50h]; Size
0x140003e35  call    memset_0
0x140003e3a  xor     ebx, ebx
0x140003e3c  mov     [r15], rsi
0x140003e3f  test    rdi, rdi
0x140003e42  jz      short loc_140003E55
0x140003e44  mov     rcx, rdi; hMutex
0x140003e47  call    cs:__imp_ReleaseMutex
0x140003e4d  test    eax, eax
0x140003e4f  jz      loc_140003F20
0x140003e55  test    rbx, rbx
0x140003e58  jz      short loc_140003E67
0x140003e5a  mov     rcx, rbx; hObject
0x140003e5d  call    cs:__imp_CloseHandle
0x140003e63  test    eax, eax
0x140003e65  jz      short loc_140003E8F
0x140003e67  xor     eax, eax
0x140003e69  mov     rcx, [rbp+180h+var_30]
0x140003e70  xor     rcx, rsp; StackCookie
0x140003e73  call    __security_check_cookie
0x140003e78  mov     rbx, [rsp+280h+arg_10]
0x140003e80  add     rsp, 260h
0x140003e87  pop     r15
0x140003e89  pop     r14
0x140003e8b  pop     rdi
0x140003e8c  pop     rsi
0x140003e8d  pop     rbp
0x140003e8e  retn
0x140003e8f  mov     rcx, [rbp+188h]; this
0x140003e96  mov     edx, 0A0Bh; void *
0x140003e9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ea1  mov     rcx, [rbp+188h]; this
0x140003ea8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003eae  mov     rcx, [rbp+188h]; this
0x140003eb5  mov     edx, 0A15h; void *
0x140003eba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ec0  mov     rcx, [rbp+188h]; this
0x140003ec7  mov     edx, 0A0Bh; void *
0x140003ecc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ed2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003ed8  mov     rcx, [rbp+188h]; this
0x140003edf  mov     edx, 0A0Bh; void *
0x140003ee4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003eea  mov     rcx, [rbp+188h]; this
0x140003ef1  mov     edx, 0A0Bh; void *
0x140003ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003efc  mov     rcx, [rbp+188h]; this
0x140003f03  mov     edx, 0A15h; void *
0x140003f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f0e  mov     rcx, [rbp+188h]; this
0x140003f15  mov     edx, 0A0Bh; void *
0x140003f1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003f20  mov     rcx, [rbp+188h]; this
0x140003f27  mov     edx, 0A15h; void *
0x140003f2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
