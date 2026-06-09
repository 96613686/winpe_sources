# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140010778`
- end: `0x140010b7a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1026`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140011c9c`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140008ea8`
- `0x14000a070`
- `0x14000a6dc`
- `0x14000d7c8`
- `0x140010414`
- `0x140010778`
- `0x140010fac`
- `0x140011450`
- `0x140011a34`
- `0x14001410c`
- `0x1400148d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400107b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400107b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400108d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010a03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010a9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400108d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010a03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010a9f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400107f0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400107f0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010811`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010811`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400108c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400109f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010a89`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400108c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400109f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010a89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400109b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400109c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400109c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        int a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  void *v13; // rdi
  int ValueInternal; // eax
  unsigned __int64 v15; // r8
  unsigned int v16; // esi
  __int64 v17; // r8
  __int64 v18; // r8
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag4 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  HANDLE ProcessHeap; // rax
  __int64 v27; // r8
  __int64 v28; // r8
  unsigned __int64 v29; // rax
  __int64 v30; // r8
  __int64 v31; // r8
  wil::details *v32; // [rsp+20h] [rbp-E0h]
  wil::details *v33; // [rsp+20h] [rbp-E0h]
  wil::details *v34; // [rsp+20h] [rbp-E0h]
  wil::details *v35; // [rsp+20h] [rbp-E0h]
  wil::details *v36; // [rsp+20h] [rbp-E0h]
  wil::details *v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v38 = a1;
  LODWORD(v32) = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag4::FailFast_Unexpected(retaddr, v10, v11, v12, (const char *)v32);
    v13 = v7;
  }
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, v42, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    LODWORD(v32) = ValueInternal;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetValue",
      v32,
      v38);
    LODWORD(v33) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetPointer",
      v33,
      v39);
    LODWORD(v34) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
      v34,
      v40);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v17,
        "wil::details::ReleaseMutex",
        (const char *)v35);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v18,
        "wil::details::CloseHandle",
        (const char *)v35);
    return v16;
  }
  v19 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_24;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v15);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)v42 = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag4::_FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v42,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v23[2] = v42[0];
      v29 = v42[1];
      *(_DWORD *)v23 = 1;
      v23[1] = v7;
      v42[0] = 0;
      v23[3] = v29;
      v42[1] = 0;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      *a2 = v23;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
      v7 = 0;
LABEL_24:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          v30,
          "wil::details::ReleaseMutex",
          (const char *)v32);
      if ( v7 && !CloseHandle(v7) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v31,
          "wil::details::CloseHandle",
          (const char *)v32);
      return 0;
    }
    LODWORD(v32) = v25;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      v32,
      v38);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    LODWORD(v32) = -2147024882;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      v32,
      v38);
  }
  LODWORD(v36) = v24;
  wil::details::in1diag4::Return_Hr(
    retaddr,
    (void *)0x137,
    (unsigned int)"wil",
    "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
    v36,
    v41);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      v27,
      "wil::details::ReleaseMutex",
      (const char *)v37);
  if ( !CloseHandle(v7) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v28,
      "wil::details::CloseHandle",
      (const char *)v37);
  return v24;
}

```

## disassembly

```asm
0x140010778  mov     [rsp-8+arg_10], rbx
0x14001077d  push    rbp
0x14001077e  push    rsi
0x14001077f  push    rdi
0x140010780  push    r14
0x140010782  push    r15
0x140010784  lea     rbp, [rsp-160h]
0x14001078c  sub     rsp, 260h
0x140010793  mov     rax, cs:__security_cookie
0x14001079a  xor     rax, rsp
0x14001079d  mov     [rbp+180h+var_30], rax
0x1400107a4  mov     r15, rdx
0x1400107a7  mov     qword ptr [rdx], 0
0x1400107ae  mov     rbx, rcx
0x1400107b1  call    cs:__imp_GetCurrentProcessId
0x1400107b7  mov     r14d, 78h ; 'x'
0x1400107bd  mov     qword ptr [rsp+280h+var_258], rbx; int
0x1400107c2  mov     r9d, eax
0x1400107c5  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x1400107ca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400107d1  mov     edx, 104h; unsigned __int64
0x1400107d6  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400107db  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400107e0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400107e6  lea     rdx, [rsp+280h+Name]; lpName
0x1400107eb  xor     r8d, r8d; dwFlags
0x1400107ee  xor     ecx, ecx; lpMutexAttributes
0x1400107f0  call    cs:__imp_CreateMutexExW
0x1400107f6  mov     rbx, rax
0x1400107f9  test    rax, rax
0x1400107fc  jnz     short loc_140010808
0x1400107fe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010803  jmp     loc_140010AAB
0x140010808  xor     r8d, r8d; bAlertable
0x14001080b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001080e  mov     rcx, rbx; hHandle
0x140010811  call    cs:__imp_WaitForSingleObjectEx
0x140010817  cmp     eax, 102h
0x14001081c  jz      short loc_14001082E
0x14001081e  test    eax, 0FFFFFF7Fh
0x140010823  jnz     loc_140010AEA
0x140010829  mov     rdi, rbx
0x14001082c  jmp     short loc_140010830
0x14001082e  xor     edi, edi
0x140010830  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140010835  mov     [rsp+280h+var_250], 0
0x14001083e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140010843  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140010848  mov     esi, eax
0x14001084a  test    eax, eax
0x14001084c  jns     loc_1400108E9
0x140010852  mov     rcx, [rbp+188h]; this
0x140010859  lea     r9, aWilDetailsAbiS_0; "wil::details_abi::SemaphoreValue::TryGe"...
0x140010860  lea     r8, aWil; "wil"
0x140010867  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x14001086b  mov     edx, 66h ; 'f'; void *
0x140010870  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010875  mov     rcx, [rbp+188h]; this
0x14001087c  lea     r9, aWilDetailsAbiS; "wil::details_abi::SemaphoreValue::TryGe"...
0x140010883  lea     r8, aWil; "wil"
0x14001088a  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x14001088e  mov     edx, 6Fh ; 'o'; void *
0x140010893  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010898  mov     rcx, [rbp+188h]; this
0x14001089f  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x1400108a6  lea     r8, aWil; "wil"
0x1400108ad  mov     dword ptr [rsp+280h+var_260], esi; char *
0x1400108b1  mov     edx, 12Eh; void *
0x1400108b6  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x1400108bb  test    rdi, rdi
0x1400108be  jz      short loc_1400108D1
0x1400108c0  mov     rcx, rdi; hMutex
0x1400108c3  call    cs:__imp_ReleaseMutex
0x1400108c9  test    eax, eax
0x1400108cb  jz      loc_140010AF7
0x1400108d1  mov     rcx, rbx; hObject
0x1400108d4  call    cs:__imp_CloseHandle
0x1400108da  test    eax, eax
0x1400108dc  jz      loc_140010B10
0x1400108e2  mov     eax, esi
0x1400108e4  jmp     loc_140010AAB
0x1400108e9  mov     rax, [rsp+280h+var_250]
0x1400108ee  lea     rcx, ds:0[rax*4]
0x1400108f6  test    rcx, rcx
0x1400108f9  jz      short loc_140010909
0x1400108fb  mov     [r15], rcx
0x1400108fe  mov     eax, [rcx]
0x140010900  inc     eax
0x140010902  mov     [rcx], eax
0x140010904  jmp     loc_140010A81
0x140010909  mov     rdx, r14; dwBytes
0x14001090c  mov     qword ptr [r15], 0
0x140010913  mov     ecx, 8; dwFlags
0x140010918  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001091d  mov     rsi, rax
0x140010920  test    rax, rax
0x140010923  jnz     short loc_140010951
0x140010925  mov     rcx, [rbp+188h]; this
0x14001092c  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x140010933  mov     r14d, 8007000Eh
0x140010939  lea     r8, aWil; "wil"
0x140010940  mov     edx, 14Bh; void *
0x140010945  mov     dword ptr [rsp+280h+var_260], r14d; wil::details *
0x14001094a  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x14001094f  jmp     short loc_1400109C6
0x140010951  xorps   xmm0, xmm0
0x140010954  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14001095a  test    sil, 3
0x14001095e  jnz     loc_140010B29
0x140010964  mov     r9, rsi
0x140010967  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14001096c  shr     r9, 2; unsigned __int64
0x140010970  lea     rcx, [rsp+280h+var_250]; this
0x140010975  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14001097a  mov     r14d, eax
0x14001097d  test    eax, eax
0x14001097f  jns     loc_140010A19
0x140010985  mov     rcx, [rbp+188h]; this
0x14001098c  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x140010993  lea     r8, aWil; "wil"
0x14001099a  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x14001099e  mov     edx, 14Eh; void *
0x1400109a3  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x1400109a8  lea     rcx, [rsp+280h+var_250]; this
0x1400109ad  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1400109b2  call    cs:__imp_GetProcessHeap
0x1400109b8  mov     r8, rsi; lpMem
0x1400109bb  xor     edx, edx; dwFlags
0x1400109bd  mov     rcx, rax; hHeap
0x1400109c0  call    cs:__imp_HeapFree
0x1400109c6  mov     rcx, [rbp+188h]; this
0x1400109cd  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x1400109d4  lea     r8, aWil; "wil"
0x1400109db  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x1400109e0  mov     edx, 137h; void *
0x1400109e5  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x1400109ea  test    rdi, rdi
0x1400109ed  jz      short loc_140010A00
0x1400109ef  mov     rcx, rdi; hMutex
0x1400109f2  call    cs:__imp_ReleaseMutex
0x1400109f8  test    eax, eax
0x1400109fa  jz      loc_140010B2F
0x140010a00  mov     rcx, rbx; hObject
0x140010a03  call    cs:__imp_CloseHandle
0x140010a09  test    eax, eax
0x140010a0b  jz      loc_140010B48
0x140010a11  mov     eax, r14d
0x140010a14  jmp     loc_140010AAB
0x140010a19  mov     rax, [rsp+280h+var_250]
0x140010a1e  lea     rcx, [rsi+22h]; void *
0x140010a22  xor     edx, edx; Val
0x140010a24  mov     [rsi+10h], rax
0x140010a28  mov     rax, [rsp+280h+var_250+8]
0x140010a2d  mov     dword ptr [rsi], 1
0x140010a33  mov     [rsi+8], rbx
0x140010a37  lea     r8d, [rdx+56h]; Size
0x140010a3b  mov     [rsp+280h+var_250], 0
0x140010a44  mov     [rsi+18h], rax
0x140010a48  mov     [rsp+280h+var_250+8], 0
0x140010a51  call    memset_0
0x140010a56  xor     edx, edx; Val
0x140010a58  mov     word ptr [rsi+20h], 58h ; 'X'
0x140010a5e  lea     rcx, [rsi+28h]; void *
0x140010a62  mov     dword ptr [rsi+24h], 1
0x140010a69  lea     r8d, [rdx+50h]; Size
0x140010a6d  call    memset_0
0x140010a72  lea     rcx, [rsp+280h+var_250]; this
0x140010a77  mov     [r15], rsi
0x140010a7a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140010a7f  xor     ebx, ebx
0x140010a81  test    rdi, rdi
0x140010a84  jz      short loc_140010A97
0x140010a86  mov     rcx, rdi; hMutex
0x140010a89  call    cs:__imp_ReleaseMutex
0x140010a8f  test    eax, eax
0x140010a91  jz      loc_140010B61
0x140010a97  test    rbx, rbx
0x140010a9a  jz      short loc_140010AA9
0x140010a9c  mov     rcx, rbx; hObject
0x140010a9f  call    cs:__imp_CloseHandle
0x140010aa5  test    eax, eax
0x140010aa7  jz      short loc_140010AD1
0x140010aa9  xor     eax, eax
0x140010aab  mov     rcx, [rbp+180h+var_30]
0x140010ab2  xor     rcx, rsp; StackCookie
0x140010ab5  call    __security_check_cookie
0x140010aba  mov     rbx, [rsp+280h+arg_10]
0x140010ac2  add     rsp, 260h
0x140010ac9  pop     r15
0x140010acb  pop     r14
0x140010acd  pop     rdi
0x140010ace  pop     rsi
0x140010acf  pop     rbp
0x140010ad0  retn
0x140010ad1  mov     rcx, [rbp+188h]; this
0x140010ad8  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010adf  mov     edx, 0A0Bh; void *
0x140010ae4  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010aea  mov     rcx, [rbp+188h]; this
0x140010af1  call    ?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)
0x140010af7  mov     rcx, [rbp+188h]; this
0x140010afe  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010b05  mov     edx, 0A15h; void *
0x140010b0a  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010b10  mov     rcx, [rbp+188h]; this
0x140010b17  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010b1e  mov     edx, 0A0Bh; void *
0x140010b23  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010b29  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x140010b2f  mov     rcx, [rbp+188h]; this
0x140010b36  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010b3d  mov     edx, 0A15h; void *
0x140010b42  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010b48  mov     rcx, [rbp+188h]; this
0x140010b4f  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010b56  mov     edx, 0A0Bh; void *
0x140010b5b  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010b61  mov     rcx, [rbp+188h]; this
0x140010b68  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010b6f  mov     edx, 0A15h; void *
0x140010b74  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
