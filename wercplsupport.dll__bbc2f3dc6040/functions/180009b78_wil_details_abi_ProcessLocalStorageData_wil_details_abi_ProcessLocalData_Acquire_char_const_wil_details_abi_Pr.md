# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009b78`
- end: `0x180009f50`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000b868`

## callees

- `0x180009618`
- `0x180009b78`
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

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009bb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009cae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009cae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009c11`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009bf0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009bf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d8f`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag4 *v23; // rcx
  __int64 v24; // r8
  _QWORD *v25; // rsi
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  unsigned int v32; // r8d
  unsigned __int64 v33; // rax
  unsigned int v34; // r8d
  unsigned int v35; // r8d
  wil::details *v36; // [rsp+20h] [rbp-E0h]
  wil::details *v37; // [rsp+20h] [rbp-E0h]
  wil::details *v38; // [rsp+20h] [rbp-E0h]
  wil::details *v39; // [rsp+20h] [rbp-E0h]
  wil::details *v40; // [rsp+20h] [rbp-E0h]
  wil::details *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+28h] [rbp-D8h]
  int v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+28h] [rbp-D8h]
  int v45; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v46[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v42 = a1;
  LODWORD(v36) = 120;
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
      wil::details::in1diag4::FailFast_Unexpected(retaddr, v10, v11, v12, (const char *)v36);
    v13 = v7;
  }
  v46[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, v46, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    LODWORD(v36) = ValueInternal;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x66,
      v15,
      "wil::details_abi::SemaphoreValue::TryGetValue",
      v36,
      v42);
    LODWORD(v37) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x6F,
      v17,
      "wil::details_abi::SemaphoreValue::TryGetPointer",
      v37,
      v43);
    LODWORD(v38) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x12E,
      v18,
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
      v38,
      v44);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v19,
        "wil::details::ReleaseMutex",
        (const char *)v39);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v20,
        "wil::details::CloseHandle",
        (const char *)v39);
    return v16;
  }
  v21 = (_DWORD *)(4 * v46[0]);
  if ( 4 * v46[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_24;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v15);
  v25 = (_QWORD *)v22;
  if ( v22 )
  {
    *(_OWORD *)v46 = 0;
    if ( (v22 & 3) != 0 )
      wil::details::in1diag4::_FailFastImmediate_Unexpected(v23);
    v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v46,
            Name,
            v24,
            v22 >> 2);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v25[2] = v46[0];
      v33 = v46[1];
      *(_DWORD *)v25 = 1;
      v25[1] = v7;
      v46[0] = 0;
      v25[3] = v33;
      v46[1] = 0;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      *a2 = v25;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v46);
      v7 = 0;
LABEL_24:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          v34,
          "wil::details::ReleaseMutex",
          (const char *)v36);
      if ( v7 && !CloseHandle(v7) )
        wil::details::in1diag4::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          v35,
          "wil::details::CloseHandle",
          (const char *)v36);
      return 0;
    }
    LODWORD(v36) = v28;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14E,
      v29,
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      v36,
      v42);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v46);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    LODWORD(v36) = -2147024882;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14B,
      v24,
      "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::MakeAndInitialize",
      v36,
      v42);
  }
  LODWORD(v40) = v26;
  wil::details::in1diag4::Return_Hr(
    retaddr,
    (void *)0x137,
    v27,
    "wil::details_abi::ProcessLocalStorageData<struct wil::details_abi::ProcessLocalData>::Acquire",
    v40,
    v45);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      v31,
      "wil::details::ReleaseMutex",
      (const char *)v41);
  if ( !CloseHandle(v7) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v32,
      "wil::details::CloseHandle",
      (const char *)v41);
  return v26;
}

```

## disassembly

```asm
0x180009b78  mov     [rsp-8+arg_10], rbx
0x180009b7d  push    rbp
0x180009b7e  push    rsi
0x180009b7f  push    rdi
0x180009b80  push    r14
0x180009b82  push    r15
0x180009b84  lea     rbp, [rsp-160h]
0x180009b8c  sub     rsp, 260h
0x180009b93  mov     rax, cs:__security_cookie
0x180009b9a  xor     rax, rsp
0x180009b9d  mov     [rbp+180h+var_30], rax
0x180009ba4  mov     r15, rdx
0x180009ba7  mov     qword ptr [rdx], 0
0x180009bae  mov     rbx, rcx
0x180009bb1  call    cs:__imp_GetCurrentProcessId
0x180009bb7  mov     r14d, 78h ; 'x'
0x180009bbd  mov     qword ptr [rsp+280h+var_258], rbx; int
0x180009bc2  mov     r9d, eax
0x180009bc5  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x180009bca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009bd1  mov     edx, 104h; unsigned __int64
0x180009bd6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009bdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009be0  mov     r9d, 1F0001h; dwDesiredAccess
0x180009be6  lea     rdx, [rsp+280h+Name]; lpName
0x180009beb  xor     r8d, r8d; dwFlags
0x180009bee  xor     ecx, ecx; lpMutexAttributes
0x180009bf0  call    cs:__imp_CreateMutexExW
0x180009bf6  mov     rbx, rax
0x180009bf9  test    rax, rax
0x180009bfc  jnz     short loc_180009C08
0x180009bfe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009c03  jmp     loc_180009E81
0x180009c08  xor     r8d, r8d; bAlertable
0x180009c0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009c0e  mov     rcx, rbx; hHandle
0x180009c11  call    cs:__imp_WaitForSingleObjectEx
0x180009c17  cmp     eax, 102h
0x180009c1c  jz      short loc_180009C2E
0x180009c1e  test    eax, 0FFFFFF7Fh
0x180009c23  jnz     loc_180009EC0
0x180009c29  mov     rdi, rbx
0x180009c2c  jmp     short loc_180009C30
0x180009c2e  xor     edi, edi
0x180009c30  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180009c35  mov     [rsp+280h+var_250], 0
0x180009c3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009c43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009c48  mov     esi, eax
0x180009c4a  test    eax, eax
0x180009c4c  jns     loc_180009CD4
0x180009c52  mov     rcx, [rbp+188h]; this
0x180009c59  lea     r9, aWilDetailsAbiS_0; "wil::details_abi::SemaphoreValue::TryGe"...
0x180009c60  mov     edx, 66h ; 'f'; void *
0x180009c65  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x180009c69  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009c6e  mov     rcx, [rbp+188h]; this
0x180009c75  lea     r9, aWilDetailsAbiS; "wil::details_abi::SemaphoreValue::TryGe"...
0x180009c7c  mov     edx, 6Fh ; 'o'; void *
0x180009c81  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x180009c85  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009c8a  mov     rcx, [rbp+188h]; this
0x180009c91  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x180009c98  mov     edx, 12Eh; void *
0x180009c9d  mov     dword ptr [rsp+280h+var_260], esi; char *
0x180009ca1  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009ca6  test    rdi, rdi
0x180009ca9  jz      short loc_180009CBC
0x180009cab  mov     rcx, rdi; hMutex
0x180009cae  call    cs:__imp_ReleaseMutex
0x180009cb4  test    eax, eax
0x180009cb6  jz      loc_180009ECD
0x180009cbc  mov     rcx, rbx; hObject
0x180009cbf  call    cs:__imp_CloseHandle
0x180009cc5  test    eax, eax
0x180009cc7  jz      loc_180009EE6
0x180009ccd  mov     eax, esi
0x180009ccf  jmp     loc_180009E81
0x180009cd4  mov     rax, [rsp+280h+var_250]
0x180009cd9  lea     rcx, ds:0[rax*4]
0x180009ce1  test    rcx, rcx
0x180009ce4  jz      short loc_180009CF4
0x180009ce6  mov     [r15], rcx
0x180009ce9  mov     eax, [rcx]
0x180009ceb  inc     eax
0x180009ced  mov     [rcx], eax
0x180009cef  jmp     loc_180009E57
0x180009cf4  mov     rdx, r14; dwBytes
0x180009cf7  mov     qword ptr [r15], 0
0x180009cfe  mov     ecx, 8; dwFlags
0x180009d03  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009d08  mov     rsi, rax
0x180009d0b  test    rax, rax
0x180009d0e  jnz     short loc_180009D35
0x180009d10  mov     rcx, [rbp+188h]; this
0x180009d17  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x180009d1e  mov     r14d, 8007000Eh
0x180009d24  mov     edx, 14Bh; void *
0x180009d29  mov     dword ptr [rsp+280h+var_260], r14d; wil::details *
0x180009d2e  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009d33  jmp     short loc_180009DA3
0x180009d35  xorps   xmm0, xmm0
0x180009d38  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180009d3e  test    sil, 3
0x180009d42  jnz     loc_180009EFF
0x180009d48  mov     r9, rsi
0x180009d4b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009d50  shr     r9, 2; unsigned __int64
0x180009d54  lea     rcx, [rsp+280h+var_250]; this
0x180009d59  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009d5e  mov     r14d, eax
0x180009d61  test    eax, eax
0x180009d63  jns     loc_180009DEF
0x180009d69  mov     rcx, [rbp+188h]; this
0x180009d70  lea     r9, aWilDetailsAbiP_1; "wil::details_abi::ProcessLocalStorageDa"...
0x180009d77  mov     edx, 14Eh; void *
0x180009d7c  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x180009d80  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009d85  lea     rcx, [rsp+280h+var_250]; this
0x180009d8a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009d8f  call    cs:__imp_GetProcessHeap
0x180009d95  mov     r8, rsi; lpMem
0x180009d98  xor     edx, edx; dwFlags
0x180009d9a  mov     rcx, rax; hHeap
0x180009d9d  call    cs:__imp_HeapFree
0x180009da3  mov     rcx, [rbp+188h]; this
0x180009daa  lea     r9, aWilDetailsAbiP; "wil::details_abi::ProcessLocalStorageDa"...
0x180009db1  mov     edx, 137h; void *
0x180009db6  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x180009dbb  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x180009dc0  test    rdi, rdi
0x180009dc3  jz      short loc_180009DD6
0x180009dc5  mov     rcx, rdi; hMutex
0x180009dc8  call    cs:__imp_ReleaseMutex
0x180009dce  test    eax, eax
0x180009dd0  jz      loc_180009F05
0x180009dd6  mov     rcx, rbx; hObject
0x180009dd9  call    cs:__imp_CloseHandle
0x180009ddf  test    eax, eax
0x180009de1  jz      loc_180009F1E
0x180009de7  mov     eax, r14d
0x180009dea  jmp     loc_180009E81
0x180009def  mov     rax, [rsp+280h+var_250]
0x180009df4  lea     rcx, [rsi+22h]; void *
0x180009df8  xor     edx, edx; Val
0x180009dfa  mov     [rsi+10h], rax
0x180009dfe  mov     rax, [rsp+280h+var_250+8]
0x180009e03  mov     dword ptr [rsi], 1
0x180009e09  mov     [rsi+8], rbx
0x180009e0d  lea     r8d, [rdx+56h]; Size
0x180009e11  mov     [rsp+280h+var_250], 0
0x180009e1a  mov     [rsi+18h], rax
0x180009e1e  mov     [rsp+280h+var_250+8], 0
0x180009e27  call    memset_0
0x180009e2c  xor     edx, edx; Val
0x180009e2e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180009e34  lea     rcx, [rsi+28h]; void *
0x180009e38  mov     dword ptr [rsi+24h], 1
0x180009e3f  lea     r8d, [rdx+50h]; Size
0x180009e43  call    memset_0
0x180009e48  lea     rcx, [rsp+280h+var_250]; this
0x180009e4d  mov     [r15], rsi
0x180009e50  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009e55  xor     ebx, ebx
0x180009e57  test    rdi, rdi
0x180009e5a  jz      short loc_180009E6D
0x180009e5c  mov     rcx, rdi; hMutex
0x180009e5f  call    cs:__imp_ReleaseMutex
0x180009e65  test    eax, eax
0x180009e67  jz      loc_180009F37
0x180009e6d  test    rbx, rbx
0x180009e70  jz      short loc_180009E7F
0x180009e72  mov     rcx, rbx; hObject
0x180009e75  call    cs:__imp_CloseHandle
0x180009e7b  test    eax, eax
0x180009e7d  jz      short loc_180009EA7
0x180009e7f  xor     eax, eax
0x180009e81  mov     rcx, [rbp+180h+var_30]
0x180009e88  xor     rcx, rsp; StackCookie
0x180009e8b  call    __security_check_cookie
0x180009e90  mov     rbx, [rsp+280h+arg_10]
0x180009e98  add     rsp, 260h
0x180009e9f  pop     r15
0x180009ea1  pop     r14
0x180009ea3  pop     rdi
0x180009ea4  pop     rsi
0x180009ea5  pop     rbp
0x180009ea6  retn
0x180009ea7  mov     rcx, [rbp+188h]; this
0x180009eae  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x180009eb5  mov     edx, 0A0Bh; void *
0x180009eba  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009ec0  mov     rcx, [rbp+188h]; this
0x180009ec7  call    ?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)
0x180009ecd  mov     rcx, [rbp+188h]; this
0x180009ed4  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x180009edb  mov     edx, 0A15h; void *
0x180009ee0  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009ee6  mov     rcx, [rbp+188h]; this
0x180009eed  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x180009ef4  mov     edx, 0A0Bh; void *
0x180009ef9  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009eff  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x180009f05  mov     rcx, [rbp+188h]; this
0x180009f0c  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x180009f13  mov     edx, 0A15h; void *
0x180009f18  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009f1e  mov     rcx, [rbp+188h]; this
0x180009f25  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x180009f2c  mov     edx, 0A0Bh; void *
0x180009f31  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x180009f37  mov     rcx, [rbp+188h]; this
0x180009f3e  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x180009f45  mov     edx, 0A15h; void *
0x180009f4a  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
