# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006af8`
- end: `0x180006ef5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007334`

## callees

- `0x180004120`
- `0x180004c80`
- `0x180005cd0`
- `0x180006af8`
- `0x180006f54`
- `0x1800074e0`
- `0x180007e18`
- `0x180008aec`
- `0x180009fe4`
- `0x18000aae4`
- `0x18000aeac`
- `0x18000b75c`
- `0x18000b76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006c26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d62`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006dfe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006c26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d62`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006dfe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006dcb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006dcb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006b6f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006b6f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006b90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006b90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006b31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006b31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e14`

## string_xrefs

- `0x180006e71`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180006af8  mov     [rsp-8+arg_10], rbx
0x180006afd  push    rbp
0x180006afe  push    rsi
0x180006aff  push    rdi
0x180006b00  push    r14
0x180006b02  push    r15
0x180006b04  lea     rbp, [rsp-160h]
0x180006b0c  sub     rsp, 260h
0x180006b13  mov     rax, cs:__security_cookie
0x180006b1a  xor     rax, rsp
0x180006b1d  mov     [rbp+180h+var_30], rax
0x180006b24  mov     r15, rdx
0x180006b27  mov     qword ptr [rdx], 0
0x180006b2e  mov     rbx, rcx
0x180006b31  call    cs:__imp_GetCurrentProcessId
0x180006b37  mov     r14d, 130h
0x180006b3d  mov     [rsp+280h+var_258], rbx
0x180006b42  mov     r9d, eax
0x180006b45  mov     [rsp+280h+var_260], r14d; int
0x180006b4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006b51  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006b56  lea     edx, [r14-2Ch]; unsigned __int64
0x180006b5a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006b5f  mov     r9d, 1F0001h; dwDesiredAccess
0x180006b65  lea     rdx, [rsp+280h+Name]; lpName
0x180006b6a  xor     r8d, r8d; dwFlags
0x180006b6d  xor     ecx, ecx; lpMutexAttributes
0x180006b6f  call    cs:__imp_CreateMutexExW
0x180006b75  mov     rbx, rax
0x180006b78  test    rax, rax
0x180006b7b  jnz     short loc_180006B87
0x180006b7d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006b82  jmp     loc_180006E20
0x180006b87  xor     r8d, r8d; bAlertable
0x180006b8a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006b8d  mov     rcx, rbx; hHandle
0x180006b90  call    cs:__imp_WaitForSingleObjectEx
0x180006b96  cmp     eax, 102h
0x180006b9b  jz      short loc_180006BAD
0x180006b9d  test    eax, 0FFFFFF7Fh
0x180006ba2  jnz     loc_180006E6A
0x180006ba8  mov     rdi, rbx
0x180006bab  jmp     short loc_180006BAF
0x180006bad  xor     edi, edi
0x180006baf  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006bb4  mov     [rsp+280h+hObject], 0
0x180006bbd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006bc2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006bc7  mov     esi, eax
0x180006bc9  test    eax, eax
0x180006bcb  jns     short loc_180006C4C
0x180006bcd  mov     rcx, [rbp+188h]; this
0x180006bd4  lea     r8, aWil; "wil"
0x180006bdb  mov     r9d, eax; char *
0x180006bde  mov     edx, 66h ; 'f'; void *
0x180006be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006be8  mov     rcx, [rbp+188h]; this
0x180006bef  lea     r8, aWil; "wil"
0x180006bf6  mov     r9d, esi; char *
0x180006bf9  mov     edx, 6Fh ; 'o'; void *
0x180006bfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c03  mov     rcx, [rbp+188h]; this
0x180006c0a  lea     r8, aWil; "wil"
0x180006c11  mov     r9d, esi; char *
0x180006c14  mov     edx, 12Eh; void *
0x180006c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c1e  test    rdi, rdi
0x180006c21  jz      short loc_180006C34
0x180006c23  mov     rcx, rdi; hMutex
0x180006c26  call    cs:__imp_ReleaseMutex
0x180006c2c  test    eax, eax
0x180006c2e  jz      loc_180006E83
0x180006c34  mov     rcx, rbx; hObject
0x180006c37  call    cs:__imp_CloseHandle
0x180006c3d  test    eax, eax
0x180006c3f  jz      loc_180006E95
0x180006c45  mov     eax, esi
0x180006c47  jmp     loc_180006E20
0x180006c4c  mov     rax, [rsp+280h+hObject]
0x180006c51  lea     rcx, ds:0[rax*4]
0x180006c59  test    rcx, rcx
0x180006c5c  jz      short loc_180006C6C
0x180006c5e  mov     [r15], rcx
0x180006c61  mov     eax, [rcx]
0x180006c63  inc     eax
0x180006c65  mov     [rcx], eax
0x180006c67  jmp     loc_180006DF6
0x180006c6c  mov     rdx, r14; dwBytes
0x180006c6f  mov     qword ptr [r15], 0
0x180006c76  mov     ecx, 8; dwFlags
0x180006c7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006c80  mov     r14, rax
0x180006c83  test    rax, rax
0x180006c86  jnz     short loc_180006CAD
0x180006c88  mov     rcx, [rbp+188h]; this
0x180006c8f  lea     r8, aWil; "wil"
0x180006c96  mov     esi, 8007000Eh
0x180006c9b  mov     edx, 14Bh; void *
0x180006ca0  mov     r9d, esi; char *
0x180006ca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ca8  jmp     loc_180006D3F
0x180006cad  xorps   xmm0, xmm0
0x180006cb0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006cb6  test    r14b, 3
0x180006cba  jnz     loc_180006EA7
0x180006cc0  mov     r9, r14
0x180006cc3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006cc8  shr     r9, 2; unsigned __int64
0x180006ccc  lea     rcx, [rsp+280h+hObject]; this
0x180006cd1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006cd6  mov     esi, eax
0x180006cd8  test    eax, eax
0x180006cda  jns     loc_180006D86
0x180006ce0  mov     rcx, [rbp+188h]; this
0x180006ce7  lea     r8, aWil; "wil"
0x180006cee  mov     r9d, eax; char *
0x180006cf1  mov     edx, 14Eh; void *
0x180006cf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cfb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006d00  test    rcx, rcx
0x180006d03  jz      short loc_180006D13
0x180006d05  call    cs:__imp_CloseHandle
0x180006d0b  test    eax, eax
0x180006d0d  jz      loc_180006EAD
0x180006d13  mov     rcx, [rsp+280h+hObject]; hObject
0x180006d18  test    rcx, rcx
0x180006d1b  jz      short loc_180006D2B
0x180006d1d  call    cs:__imp_CloseHandle
0x180006d23  test    eax, eax
0x180006d25  jz      loc_180006EBF
0x180006d2b  call    cs:__imp_GetProcessHeap
0x180006d31  mov     r8, r14; lpMem
0x180006d34  xor     edx, edx; dwFlags
0x180006d36  mov     rcx, rax; hHeap
0x180006d39  call    cs:__imp_HeapFree
0x180006d3f  mov     rcx, [rbp+188h]; this
0x180006d46  lea     r8, aWil; "wil"
0x180006d4d  mov     r9d, esi; char *
0x180006d50  mov     edx, 137h; void *
0x180006d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d5a  test    rdi, rdi
0x180006d5d  jz      short loc_180006D70
0x180006d5f  mov     rcx, rdi; hMutex
0x180006d62  call    cs:__imp_ReleaseMutex
0x180006d68  test    eax, eax
0x180006d6a  jz      loc_180006ED1
0x180006d70  mov     rcx, rbx; hObject
0x180006d73  call    cs:__imp_CloseHandle
0x180006d79  test    eax, eax
0x180006d7b  jz      loc_180006E58
0x180006d81  jmp     loc_180006C45
0x180006d86  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006d8b  lea     rcx, [r14+28h]; void *
0x180006d8f  mov     dword ptr [r14], 1
0x180006d96  xor     edx, edx; Val
0x180006d98  mov     [r14+8], rbx
0x180006d9c  mov     r8d, 108h; Size
0x180006da2  movdqu  xmmword ptr [r14+10h], xmm0
0x180006da8  call    memset_0
0x180006dad  xor     eax, eax
0x180006daf  lea     rcx, [r14+28h]; this
0x180006db3  mov     [r14+20h], rax
0x180006db7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006dbc  lea     rbx, [r14+0E8h]
0x180006dc3  xor     r8d, r8d; Flags
0x180006dc6  mov     rcx, rbx; lpCriticalSection
0x180006dc9  xor     edx, edx; dwSpinCount
0x180006dcb  call    cs:__imp_InitializeCriticalSectionEx
0x180006dd1  mov     qword ptr [rbx+28h], 0
0x180006dd9  mov     qword ptr [rbx+30h], 0
0x180006de1  mov     qword ptr [rbx+38h], 0
0x180006de9  mov     qword ptr [rbx+40h], 0
0x180006df1  xor     ebx, ebx
0x180006df3  mov     [r15], r14
0x180006df6  test    rdi, rdi
0x180006df9  jz      short loc_180006E0C
0x180006dfb  mov     rcx, rdi; hMutex
0x180006dfe  call    cs:__imp_ReleaseMutex
0x180006e04  test    eax, eax
0x180006e06  jz      loc_180006EE3
0x180006e0c  test    rbx, rbx
0x180006e0f  jz      short loc_180006E1E
0x180006e11  mov     rcx, rbx; hObject
0x180006e14  call    cs:__imp_CloseHandle
0x180006e1a  test    eax, eax
0x180006e1c  jz      short loc_180006E46
0x180006e1e  xor     eax, eax
0x180006e20  mov     rcx, [rbp+180h+var_30]
0x180006e27  xor     rcx, rsp; StackCookie
0x180006e2a  call    __security_check_cookie
0x180006e2f  mov     rbx, [rsp+280h+arg_10]
0x180006e37  add     rsp, 260h
0x180006e3e  pop     r15
0x180006e40  pop     r14
0x180006e42  pop     rdi
0x180006e43  pop     rsi
0x180006e44  pop     rbp
0x180006e45  retn
0x180006e46  mov     rcx, [rbp+188h]; this
0x180006e4d  mov     edx, 0A0Bh; void *
0x180006e52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e58  mov     rcx, [rbp+188h]; this
0x180006e5f  mov     edx, 0A0Bh; void *
0x180006e64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e6a  mov     rcx, [rbp+188h]; this
0x180006e71  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006e78  mov     edx, 0E01h; void *
0x180006e7d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006e83  mov     rcx, [rbp+188h]; this
0x180006e8a  mov     edx, 0A15h; void *
0x180006e8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e95  mov     rcx, [rbp+188h]; this
0x180006e9c  mov     edx, 0A0Bh; void *
0x180006ea1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ea7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006ead  mov     rcx, [rbp+188h]; this
0x180006eb4  mov     edx, 0A0Bh; void *
0x180006eb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ebf  mov     rcx, [rbp+188h]; this
0x180006ec6  mov     edx, 0A0Bh; void *
0x180006ecb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ed1  mov     rcx, [rbp+188h]; this
0x180006ed8  mov     edx, 0A15h; void *
0x180006edd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ee3  mov     rcx, [rbp+188h]; this
0x180006eea  mov     edx, 0A15h; void *
0x180006eef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
