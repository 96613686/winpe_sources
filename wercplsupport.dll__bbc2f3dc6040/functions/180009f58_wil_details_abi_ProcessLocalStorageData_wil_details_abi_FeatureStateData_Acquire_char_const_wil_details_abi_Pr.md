# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180009f58`
- end: `0x18000a353`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1019`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18000a8ac`

## callees

- `0x180008fb0`
- `0x180009618`
- `0x180009f58`
- `0x18000a410`
- `0x18000aaf0`
- `0x18000b6d4`
- `0x18000c354`
- `0x18000d97c`
- `0x18000dd7c`
- `0x18000e098`
- `0x18000f200`
- `0x18000f210`
- `0x18001218a`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009f91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a08d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a262`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a08d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a262`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ff0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009ff0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a225`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a225`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fcf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009fcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a09e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a278`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a09e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a278`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a179`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a179`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a16b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a16b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag4 *v23; // rcx
  __int64 v24; // r8
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  unsigned int v32; // r8d
  unsigned int v33; // r8d
  wil::details *v34; // [rsp+20h] [rbp-E0h]
  wil::details *v35; // [rsp+20h] [rbp-E0h]
  wil::details *v36; // [rsp+20h] [rbp-E0h]
  wil::details *v37; // [rsp+20h] [rbp-E0h]
  wil::details *v38; // [rsp+20h] [rbp-E0h]
  wil::details *v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+28h] [rbp-D8h]
  int v42; // [rsp+28h] [rbp-D8h]
  int v43; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v44[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v40 = a1;
  LODWORD(v34) = 304;
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
      wil::details::in1diag4::FailFast_Unexpected(retaddr, v10, v11, v12, (const char *)v34);
    v13 = v7;
  }
  v44[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, v44, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    LODWORD(v34) = ValueInternal;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x66,
      v15,
      "wil::details_abi::SemaphoreValue::TryGetValue",
      v34,
      v40);
    LODWORD(v35) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x6F,
      v17,
      "wil::details_abi::SemaphoreValue::TryGetPointer",
      v35,
      v41);
    LODWORD(v36) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x12E,
      v18,
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::Acquire",
      v36,
      v42);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v19,
        "wil::details::ReleaseMutex",
        (const char *)v37);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v20,
        "wil::details::CloseHandle",
        (const char *)v37);
    return v16;
  }
  v21 = (_DWORD *)(4 * v44[0]);
  if ( 4 * v44[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_24;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v15);
  v25 = (_DWORD *)v22;
  if ( !v22 )
  {
    v16 = -2147024882;
    LODWORD(v34) = -2147024882;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14B,
      v24,
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
      v34,
      v40);
    goto LABEL_19;
  }
  *(_OWORD *)v44 = 0;
  if ( (v22 & 3) != 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v23);
  v27 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v44,
          Name,
          v24,
          v22 >> 2);
  v16 = v27;
  if ( v27 < 0 )
  {
    LODWORD(v34) = v27;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14E,
      v28,
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
      v34,
      v40);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v44);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_19:
    LODWORD(v38) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x137,
      v26,
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::Acquire",
      v38,
      v43);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v30,
        "wil::details::ReleaseMutex",
        (const char *)v39);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v31,
        "wil::details::CloseHandle",
        (const char *)v39);
    return v16;
  }
  *((_QWORD *)v25 + 2) = v44[0];
  *((_QWORD *)v25 + 3) = v44[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v7;
  v44[0] = 0;
  v44[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v44);
  v7 = 0;
LABEL_24:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      v32,
      "wil::details::ReleaseMutex",
      (const char *)v34);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v33,
      "wil::details::CloseHandle",
      (const char *)v34);
  return 0;
}

```

## disassembly

```asm
0x180009f58  mov     [rsp-8+arg_10], rbx
0x180009f5d  push    rbp
0x180009f5e  push    rsi
0x180009f5f  push    rdi
0x180009f60  push    r14
0x180009f62  push    r15
0x180009f64  lea     rbp, [rsp-160h]
0x180009f6c  sub     rsp, 260h
0x180009f73  mov     rax, cs:__security_cookie
0x180009f7a  xor     rax, rsp
0x180009f7d  mov     [rbp+180h+var_30], rax
0x180009f84  mov     r15, rdx
0x180009f87  mov     qword ptr [rdx], 0
0x180009f8e  mov     rbx, rcx
0x180009f91  call    cs:__imp_GetCurrentProcessId
0x180009f97  mov     r14d, 130h
0x180009f9d  mov     qword ptr [rsp+280h+var_258], rbx; int
0x180009fa2  mov     r9d, eax
0x180009fa5  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x180009faa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009fb1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009fb6  lea     edx, [r14-2Ch]; unsigned __int64
0x180009fba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009fbf  mov     r9d, 1F0001h; dwDesiredAccess
0x180009fc5  lea     rdx, [rsp+280h+Name]; lpName
0x180009fca  xor     r8d, r8d; dwFlags
0x180009fcd  xor     ecx, ecx; lpMutexAttributes
0x180009fcf  call    cs:__imp_CreateMutexExW
0x180009fd5  mov     rbx, rax
0x180009fd8  test    rax, rax
0x180009fdb  jnz     short loc_180009FE7
0x180009fdd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009fe2  jmp     loc_18000A284
0x180009fe7  xor     r8d, r8d; bAlertable
0x180009fea  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009fed  mov     rcx, rbx; hHandle
0x180009ff0  call    cs:__imp_WaitForSingleObjectEx
0x180009ff6  cmp     eax, 102h
0x180009ffb  jz      short loc_18000A00D
0x180009ffd  test    eax, 0FFFFFF7Fh
0x18000a002  jnz     loc_18000A2DC
0x18000a008  mov     rdi, rbx
0x18000a00b  jmp     short loc_18000A00F
0x18000a00d  xor     edi, edi
0x18000a00f  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18000a014  mov     [rsp+280h+var_250], 0
0x18000a01d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a022  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a027  mov     esi, eax
0x18000a029  test    eax, eax
0x18000a02b  jns     loc_18000A0B3
0x18000a031  mov     rcx, [rbp+188h]; this
0x18000a038  lea     r9, aWilDetailsAbiS_0; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000a03f  mov     edx, 66h ; 'f'; void *
0x18000a044  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x18000a048  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a04d  mov     rcx, [rbp+188h]; this
0x18000a054  lea     r9, aWilDetailsAbiS; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000a05b  mov     edx, 6Fh ; 'o'; void *
0x18000a060  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x18000a064  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a069  mov     rcx, [rbp+188h]; this
0x18000a070  lea     r9, aWilDetailsAbiP_2; "wil::details_abi::ProcessLocalStorageDa"...
0x18000a077  mov     edx, 12Eh; void *
0x18000a07c  mov     dword ptr [rsp+280h+var_260], esi; char *
0x18000a080  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a085  test    rdi, rdi
0x18000a088  jz      short loc_18000A09B
0x18000a08a  mov     rcx, rdi; hMutex
0x18000a08d  call    cs:__imp_ReleaseMutex
0x18000a093  test    eax, eax
0x18000a095  jz      loc_18000A2E9
0x18000a09b  mov     rcx, rbx; hObject
0x18000a09e  call    cs:__imp_CloseHandle
0x18000a0a4  test    eax, eax
0x18000a0a6  jz      loc_18000A302
0x18000a0ac  mov     eax, esi
0x18000a0ae  jmp     loc_18000A284
0x18000a0b3  mov     rax, [rsp+280h+var_250]
0x18000a0b8  lea     rcx, ds:0[rax*4]
0x18000a0c0  test    rcx, rcx
0x18000a0c3  jz      short loc_18000A0D3
0x18000a0c5  mov     [r15], rcx
0x18000a0c8  mov     eax, [rcx]
0x18000a0ca  inc     eax
0x18000a0cc  mov     [rcx], eax
0x18000a0ce  jmp     loc_18000A25A
0x18000a0d3  mov     rdx, r14; dwBytes
0x18000a0d6  mov     qword ptr [r15], 0
0x18000a0dd  mov     ecx, 8; dwFlags
0x18000a0e2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a0e7  mov     r14, rax
0x18000a0ea  test    rax, rax
0x18000a0ed  jnz     short loc_18000A112
0x18000a0ef  mov     rcx, [rbp+188h]; this
0x18000a0f6  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x18000a0fd  mov     esi, 8007000Eh
0x18000a102  mov     edx, 14Bh; void *
0x18000a107  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x18000a10b  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a110  jmp     short loc_18000A17F
0x18000a112  xorps   xmm0, xmm0
0x18000a115  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x18000a11b  test    r14b, 3
0x18000a11f  jnz     loc_18000A31B
0x18000a125  mov     r9, r14
0x18000a128  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000a12d  shr     r9, 2; unsigned __int64
0x18000a131  lea     rcx, [rsp+280h+var_250]; this
0x18000a136  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000a13b  mov     esi, eax
0x18000a13d  test    eax, eax
0x18000a13f  jns     loc_18000A1C7
0x18000a145  mov     rcx, [rbp+188h]; this
0x18000a14c  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x18000a153  mov     edx, 14Eh; void *
0x18000a158  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x18000a15c  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a161  lea     rcx, [rsp+280h+var_250]; this
0x18000a166  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a16b  call    cs:__imp_GetProcessHeap
0x18000a171  mov     r8, r14; lpMem
0x18000a174  xor     edx, edx; dwFlags
0x18000a176  mov     rcx, rax; hHeap
0x18000a179  call    cs:__imp_HeapFree
0x18000a17f  mov     rcx, [rbp+188h]; this
0x18000a186  lea     r9, aWilDetailsAbiP_2; "wil::details_abi::ProcessLocalStorageDa"...
0x18000a18d  mov     edx, 137h; void *
0x18000a192  mov     dword ptr [rsp+280h+var_260], esi; char *
0x18000a196  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x18000a19b  test    rdi, rdi
0x18000a19e  jz      short loc_18000A1B1
0x18000a1a0  mov     rcx, rdi; hMutex
0x18000a1a3  call    cs:__imp_ReleaseMutex
0x18000a1a9  test    eax, eax
0x18000a1ab  jz      loc_18000A321
0x18000a1b1  mov     rcx, rbx; hObject
0x18000a1b4  call    cs:__imp_CloseHandle
0x18000a1ba  test    eax, eax
0x18000a1bc  jz      loc_18000A2C3
0x18000a1c2  jmp     loc_18000A0AC
0x18000a1c7  mov     rax, [rsp+280h+var_250]
0x18000a1cc  lea     rcx, [r14+28h]; void *
0x18000a1d0  mov     [r14+10h], rax
0x18000a1d4  xor     edx, edx; Val
0x18000a1d6  mov     rax, [rsp+280h+var_250+8]
0x18000a1db  mov     r8d, 108h; Size
0x18000a1e1  mov     [r14+18h], rax
0x18000a1e5  mov     dword ptr [r14], 1
0x18000a1ec  mov     [r14+8], rbx
0x18000a1f0  mov     [rsp+280h+var_250], 0
0x18000a1f9  mov     [rsp+280h+var_250+8], 0
0x18000a202  call    memset_0
0x18000a207  xor     eax, eax
0x18000a209  lea     rcx, [r14+28h]; this
0x18000a20d  mov     [r14+20h], rax
0x18000a211  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a216  lea     rbx, [r14+0E8h]
0x18000a21d  xor     r8d, r8d; Flags
0x18000a220  mov     rcx, rbx; lpCriticalSection
0x18000a223  xor     edx, edx; dwSpinCount
0x18000a225  call    cs:__imp_InitializeCriticalSectionEx
0x18000a22b  mov     qword ptr [rbx+28h], 0
0x18000a233  lea     rcx, [rsp+280h+var_250]; this
0x18000a238  mov     qword ptr [rbx+30h], 0
0x18000a240  mov     qword ptr [rbx+38h], 0
0x18000a248  mov     qword ptr [rbx+40h], 0
0x18000a250  mov     [r15], r14
0x18000a253  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a258  xor     ebx, ebx
0x18000a25a  test    rdi, rdi
0x18000a25d  jz      short loc_18000A270
0x18000a25f  mov     rcx, rdi; hMutex
0x18000a262  call    cs:__imp_ReleaseMutex
0x18000a268  test    eax, eax
0x18000a26a  jz      loc_18000A33A
0x18000a270  test    rbx, rbx
0x18000a273  jz      short loc_18000A282
0x18000a275  mov     rcx, rbx; hObject
0x18000a278  call    cs:__imp_CloseHandle
0x18000a27e  test    eax, eax
0x18000a280  jz      short loc_18000A2AA
0x18000a282  xor     eax, eax
0x18000a284  mov     rcx, [rbp+180h+var_30]
0x18000a28b  xor     rcx, rsp; StackCookie
0x18000a28e  call    __security_check_cookie
0x18000a293  mov     rbx, [rsp+280h+arg_10]
0x18000a29b  add     rsp, 260h
0x18000a2a2  pop     r15
0x18000a2a4  pop     r14
0x18000a2a6  pop     rdi
0x18000a2a7  pop     rsi
0x18000a2a8  pop     rbp
0x18000a2a9  retn
0x18000a2aa  mov     rcx, [rbp+188h]; this
0x18000a2b1  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000a2b8  mov     edx, 0A0Bh; void *
0x18000a2bd  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a2c3  mov     rcx, [rbp+188h]; this
0x18000a2ca  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000a2d1  mov     edx, 0A0Bh; void *
0x18000a2d6  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a2dc  mov     rcx, [rbp+188h]; this
0x18000a2e3  call    ?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)
0x18000a2e9  mov     rcx, [rbp+188h]; this
0x18000a2f0  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x18000a2f7  mov     edx, 0A15h; void *
0x18000a2fc  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a302  mov     rcx, [rbp+188h]; this
0x18000a309  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x18000a310  mov     edx, 0A0Bh; void *
0x18000a315  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a31b  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x18000a321  mov     rcx, [rbp+188h]; this
0x18000a328  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x18000a32f  mov     edx, 0A15h; void *
0x18000a334  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x18000a33a  mov     rcx, [rbp+188h]; this
0x18000a341  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x18000a348  mov     edx, 0A15h; void *
0x18000a34d  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
