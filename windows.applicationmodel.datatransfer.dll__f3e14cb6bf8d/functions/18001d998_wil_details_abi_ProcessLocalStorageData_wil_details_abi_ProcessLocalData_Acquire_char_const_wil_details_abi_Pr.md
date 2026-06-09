# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001d998`
- end: `0x18001dd64`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `972`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180034b5c`

## callees

- `0x180002ad0`
- `0x18000346c`
- `0x180018128`
- `0x18001d998`
- `0x180023474`
- `0x180026250`
- `0x180031454`
- `0x18003d9b8`
- `0x180048954`
- `0x18004eb30`
- `0x18004f148`
- `0x180052f18`
- `0x180052f28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001da10`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001da10`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001da31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001da31`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dbdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dc73`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dbdc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001dc73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d9d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d9d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dba5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc89`

## string_xrefs

- `0x18001dcc2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001dce8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001dd01`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001dd20`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001dd39`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001dd52`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _QWORD *v22; // rsi
  unsigned int v23; // r14d
  int v24; // eax
  HANDLE ProcessHeap; // rax
  const char *v26; // r9
  const char *v27; // r9
  unsigned __int64 v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v34, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v31);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v32);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = (_QWORD *)v19;
  if ( v19 )
  {
    *(_OWORD *)v34 = 0;
    if ( (v19 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
    v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v34,
            Name,
            v21,
            v19 >> 2);
    v23 = v24;
    if ( v24 >= 0 )
    {
      v22[2] = v34[0];
      v28 = v34[1];
      *(_DWORD *)v22 = 1;
      v22[1] = v6;
      v34[0] = 0;
      v22[3] = v28;
      v34[1] = 0;
      memset_0((char *)v22 + 34, 0, 0x56u);
      *((_WORD *)v22 + 16) = 88;
      *((_DWORD *)v22 + 9) = 1;
      memset_0(v22 + 5, 0, 0x50u);
      *a2 = v22;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
      v6 = 0;
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v29);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v30);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
  }
  else
  {
    v23 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v23, v33);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return v23;
}

```

## disassembly

```asm
0x18001d998  mov     [rsp-8+arg_10], rbx
0x18001d99d  push    rbp
0x18001d99e  push    rsi
0x18001d99f  push    rdi
0x18001d9a0  push    r14
0x18001d9a2  push    r15
0x18001d9a4  lea     rbp, [rsp-160h]
0x18001d9ac  sub     rsp, 260h
0x18001d9b3  mov     rax, cs:__security_cookie
0x18001d9ba  xor     rax, rsp
0x18001d9bd  mov     [rbp+180h+var_30], rax
0x18001d9c4  mov     r15, rdx
0x18001d9c7  mov     qword ptr [rdx], 0
0x18001d9ce  mov     rbx, rcx
0x18001d9d1  call    cs:__imp_GetCurrentProcessId
0x18001d9d7  mov     r14d, 78h ; 'x'
0x18001d9dd  mov     [rsp+280h+var_258], rbx
0x18001d9e2  mov     r9d, eax
0x18001d9e5  mov     [rsp+280h+var_260], r14d; int
0x18001d9ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001d9f1  mov     edx, 104h; unsigned __int64
0x18001d9f6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001d9fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001da00  mov     r9d, 1F0001h; dwDesiredAccess
0x18001da06  lea     rdx, [rsp+280h+Name]; lpName
0x18001da0b  xor     r8d, r8d; dwFlags
0x18001da0e  xor     ecx, ecx; lpMutexAttributes
0x18001da10  call    cs:__imp_CreateMutexExW
0x18001da16  mov     rbx, rax
0x18001da19  test    rax, rax
0x18001da1c  jnz     short loc_18001DA28
0x18001da1e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001da23  jmp     loc_18001DC95
0x18001da28  xor     r8d, r8d; bAlertable
0x18001da2b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001da2e  mov     rcx, rbx; hHandle
0x18001da31  call    cs:__imp_WaitForSingleObjectEx
0x18001da37  cmp     eax, 102h
0x18001da3c  jz      short loc_18001DA4E
0x18001da3e  test    eax, 0FFFFFF7Fh
0x18001da43  jnz     loc_18001DCD4
0x18001da49  mov     rdi, rbx
0x18001da4c  jmp     short loc_18001DA50
0x18001da4e  xor     edi, edi
0x18001da50  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18001da55  mov     [rsp+280h+var_250], 0
0x18001da5e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001da63  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001da68  mov     esi, eax
0x18001da6a  test    eax, eax
0x18001da6c  jns     short loc_18001DAED
0x18001da6e  mov     rcx, [rbp+188h]; this
0x18001da75  lea     r8, aWil; "wil"
0x18001da7c  mov     r9d, eax; char *
0x18001da7f  mov     edx, 66h ; 'f'; void *
0x18001da84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da89  mov     rcx, [rbp+188h]; this
0x18001da90  lea     r8, aWil; "wil"
0x18001da97  mov     r9d, esi; char *
0x18001da9a  mov     edx, 6Fh ; 'o'; void *
0x18001da9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001daa4  mov     rcx, [rbp+188h]; this
0x18001daab  lea     r8, aWil; "wil"
0x18001dab2  mov     r9d, esi; char *
0x18001dab5  mov     edx, 12Eh; void *
0x18001daba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dabf  test    rdi, rdi
0x18001dac2  jz      short loc_18001DAD5
0x18001dac4  mov     rcx, rdi; hMutex
0x18001dac7  call    cs:__imp_ReleaseMutex
0x18001dacd  test    eax, eax
0x18001dacf  jz      loc_18001DCE1
0x18001dad5  mov     rcx, rbx; hObject
0x18001dad8  call    cs:__imp_CloseHandle
0x18001dade  test    eax, eax
0x18001dae0  jz      loc_18001DCFA
0x18001dae6  mov     eax, esi
0x18001dae8  jmp     loc_18001DC95
0x18001daed  mov     rax, [rsp+280h+var_250]
0x18001daf2  lea     rcx, ds:0[rax*4]
0x18001dafa  test    rcx, rcx
0x18001dafd  jz      short loc_18001DB0D
0x18001daff  mov     [r15], rcx
0x18001db02  mov     eax, [rcx]
0x18001db04  inc     eax
0x18001db06  mov     [rcx], eax
0x18001db08  jmp     loc_18001DC6B
0x18001db0d  mov     rdx, r14; dwBytes
0x18001db10  mov     qword ptr [r15], 0
0x18001db17  mov     ecx, 8; dwFlags
0x18001db1c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001db21  mov     rsi, rax
0x18001db24  test    rax, rax
0x18001db27  jnz     short loc_18001DB4C
0x18001db29  mov     rcx, [rbp+188h]; this
0x18001db30  lea     r8, aWil; "wil"
0x18001db37  mov     r14d, 8007000Eh
0x18001db3d  mov     edx, 14Bh; void *
0x18001db42  mov     r9d, r14d; char *
0x18001db45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db4a  jmp     short loc_18001DBB9
0x18001db4c  xorps   xmm0, xmm0
0x18001db4f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18001db55  test    sil, 3
0x18001db59  jnz     loc_18001DD13
0x18001db5f  mov     r9, rsi
0x18001db62  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18001db67  shr     r9, 2; unsigned __int64
0x18001db6b  lea     rcx, [rsp+280h+var_250]; this
0x18001db70  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001db75  mov     r14d, eax
0x18001db78  test    eax, eax
0x18001db7a  jns     loc_18001DC03
0x18001db80  mov     rcx, [rbp+188h]; this
0x18001db87  lea     r8, aWil; "wil"
0x18001db8e  mov     r9d, eax; char *
0x18001db91  mov     edx, 14Eh; void *
0x18001db96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db9b  lea     rcx, [rsp+280h+var_250]; this
0x18001dba0  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001dba5  call    cs:__imp_GetProcessHeap
0x18001dbab  mov     r8, rsi; lpMem
0x18001dbae  xor     edx, edx; dwFlags
0x18001dbb0  mov     rcx, rax; hHeap
0x18001dbb3  call    cs:__imp_HeapFree
0x18001dbb9  mov     rcx, [rbp+188h]; this
0x18001dbc0  lea     r8, aWil; "wil"
0x18001dbc7  mov     r9d, r14d; char *
0x18001dbca  mov     edx, 137h; void *
0x18001dbcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbd4  test    rdi, rdi
0x18001dbd7  jz      short loc_18001DBEA
0x18001dbd9  mov     rcx, rdi; hMutex
0x18001dbdc  call    cs:__imp_ReleaseMutex
0x18001dbe2  test    eax, eax
0x18001dbe4  jz      loc_18001DD19
0x18001dbea  mov     rcx, rbx; hObject
0x18001dbed  call    cs:__imp_CloseHandle
0x18001dbf3  test    eax, eax
0x18001dbf5  jz      loc_18001DD32
0x18001dbfb  mov     eax, r14d
0x18001dbfe  jmp     loc_18001DC95
0x18001dc03  mov     rax, [rsp+280h+var_250]
0x18001dc08  lea     rcx, [rsi+22h]; void *
0x18001dc0c  xor     edx, edx; Val
0x18001dc0e  mov     [rsi+10h], rax
0x18001dc12  mov     rax, [rsp+280h+var_250+8]
0x18001dc17  mov     dword ptr [rsi], 1
0x18001dc1d  mov     [rsi+8], rbx
0x18001dc21  lea     r8d, [rdx+56h]; Size
0x18001dc25  mov     [rsp+280h+var_250], 0
0x18001dc2e  mov     [rsi+18h], rax
0x18001dc32  mov     [rsp+280h+var_250+8], 0
0x18001dc3b  call    memset_0
0x18001dc40  xor     edx, edx; Val
0x18001dc42  mov     word ptr [rsi+20h], 58h ; 'X'
0x18001dc48  lea     rcx, [rsi+28h]; void *
0x18001dc4c  mov     dword ptr [rsi+24h], 1
0x18001dc53  lea     r8d, [rdx+50h]; Size
0x18001dc57  call    memset_0
0x18001dc5c  lea     rcx, [rsp+280h+var_250]; this
0x18001dc61  mov     [r15], rsi
0x18001dc64  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18001dc69  xor     ebx, ebx
0x18001dc6b  test    rdi, rdi
0x18001dc6e  jz      short loc_18001DC81
0x18001dc70  mov     rcx, rdi; hMutex
0x18001dc73  call    cs:__imp_ReleaseMutex
0x18001dc79  test    eax, eax
0x18001dc7b  jz      loc_18001DD4B
0x18001dc81  test    rbx, rbx
0x18001dc84  jz      short loc_18001DC93
0x18001dc86  mov     rcx, rbx; hObject
0x18001dc89  call    cs:__imp_CloseHandle
0x18001dc8f  test    eax, eax
0x18001dc91  jz      short loc_18001DCBB
0x18001dc93  xor     eax, eax
0x18001dc95  mov     rcx, [rbp+180h+var_30]
0x18001dc9c  xor     rcx, rsp; StackCookie
0x18001dc9f  call    __security_check_cookie
0x18001dca4  mov     rbx, [rsp+280h+arg_10]
0x18001dcac  add     rsp, 260h
0x18001dcb3  pop     r15
0x18001dcb5  pop     r14
0x18001dcb7  pop     rdi
0x18001dcb8  pop     rsi
0x18001dcb9  pop     rbp
0x18001dcba  retn
0x18001dcbb  mov     rcx, [rbp+188h]; this
0x18001dcc2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dcc9  mov     edx, 0A0Bh; void *
0x18001dcce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dcd4  mov     rcx, [rbp+188h]; this
0x18001dcdb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001dce1  mov     rcx, [rbp+188h]; this
0x18001dce8  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dcef  mov     edx, 0A15h; void *
0x18001dcf4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dcfa  mov     rcx, [rbp+188h]; this
0x18001dd01  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dd08  mov     edx, 0A0Bh; void *
0x18001dd0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dd13  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001dd19  mov     rcx, [rbp+188h]; this
0x18001dd20  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dd27  mov     edx, 0A15h; void *
0x18001dd2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dd32  mov     rcx, [rbp+188h]; this
0x18001dd39  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dd40  mov     edx, 0A0Bh; void *
0x18001dd45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dd4b  mov     rcx, [rbp+188h]; this
0x18001dd52  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dd59  mov     edx, 0A15h; void *
0x18001dd5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
