# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140010b80`
- end: `0x140010fa5`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1061`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400112c0`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140008ea8`
- `0x14000a070`
- `0x14000a6dc`
- `0x14000d7c8`
- `0x14000fe64`
- `0x140010414`
- `0x140010b80`
- `0x140010fac`
- `0x140011450`
- `0x140011a34`
- `0x14001410c`
- `0x1400148d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010bb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010bb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010cdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010eca`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140010bf7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140010bf7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010c18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140010c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010cca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010df5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010eb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010cca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010df5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010eb4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140010e77`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140010e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010db6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010dc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010dc4`

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
  __int64 v17; // r8
  __int64 v18; // r8
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag4 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  HANDLE ProcessHeap; // rax
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  __int64 v29; // r8
  wil::details *v30; // [rsp+20h] [rbp-E0h]
  wil::details *v31; // [rsp+20h] [rbp-E0h]
  wil::details *v32; // [rsp+20h] [rbp-E0h]
  wil::details *v33; // [rsp+20h] [rbp-E0h]
  wil::details *v34; // [rsp+20h] [rbp-E0h]
  wil::details *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+28h] [rbp-D8h]
  int v38; // [rsp+28h] [rbp-D8h]
  int v39; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v40[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v36 = a1;
  LODWORD(v30) = 304;
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
      wil::details::in1diag4::FailFast_Unexpected(retaddr, v10, v11, v12, (const char *)v30);
    v13 = v7;
  }
  v40[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, v40, (bool *)v12);
  v16 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    LODWORD(v30) = ValueInternal;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetValue",
      v30,
      v36);
    LODWORD(v31) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"wil",
      "wil::details_abi::SemaphoreValue::TryGetPointer",
      v31,
      v37);
    LODWORD(v32) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::Acquire",
      v32,
      v38);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v17,
        "wil::details::ReleaseMutex",
        (const char *)v33);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v18,
        "wil::details::CloseHandle",
        (const char *)v33);
    return v16;
  }
  v19 = (_DWORD *)(4 * v40[0]);
  if ( 4 * v40[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_24;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v15);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v16 = -2147024882;
    LODWORD(v30) = -2147024882;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
      v30,
      v36);
    goto LABEL_19;
  }
  *(_OWORD *)v40 = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v40,
          Name,
          v22,
          v20 >> 2);
  v16 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v30) = v24;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::MakeAndInitialize",
      v30,
      v36);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v40);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
LABEL_19:
    LODWORD(v34) = v16;
    wil::details::in1diag4::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"wil",
      "wil::details_abi::ProcessLocalStorageData<class wil::details_abi::FeatureStateData>::Acquire",
      v34,
      v39);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        v26,
        "wil::details::ReleaseMutex",
        (const char *)v35);
    if ( !CloseHandle(v7) )
      wil::details::in1diag4::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v27,
        "wil::details::CloseHandle",
        (const char *)v35);
    return v16;
  }
  *((_QWORD *)v23 + 2) = v40[0];
  *((_QWORD *)v23 + 3) = v40[1];
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v7;
  v40[0] = 0;
  v40[1] = 0;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  *a2 = v23;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v40);
  v7 = 0;
LABEL_24:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      v28,
      "wil::details::ReleaseMutex",
      (const char *)v30);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag4::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v29,
      "wil::details::CloseHandle",
      (const char *)v30);
  return 0;
}

```

## disassembly

```asm
0x140010b80  mov     [rsp-8+arg_10], rbx
0x140010b85  push    rbp
0x140010b86  push    rsi
0x140010b87  push    rdi
0x140010b88  push    r14
0x140010b8a  push    r15
0x140010b8c  lea     rbp, [rsp-160h]
0x140010b94  sub     rsp, 260h
0x140010b9b  mov     rax, cs:__security_cookie
0x140010ba2  xor     rax, rsp
0x140010ba5  mov     [rbp+180h+var_30], rax
0x140010bac  mov     r15, rdx
0x140010baf  mov     qword ptr [rdx], 0
0x140010bb6  mov     rbx, rcx
0x140010bb9  call    cs:__imp_GetCurrentProcessId
0x140010bbf  mov     r14d, 130h
0x140010bc5  mov     qword ptr [rsp+280h+var_258], rbx; int
0x140010bca  mov     r9d, eax
0x140010bcd  mov     dword ptr [rsp+280h+var_260], r14d; char *
0x140010bd2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140010bd9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140010bde  lea     edx, [r14-2Ch]; unsigned __int64
0x140010be2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140010be7  mov     r9d, 1F0001h; dwDesiredAccess
0x140010bed  lea     rdx, [rsp+280h+Name]; lpName
0x140010bf2  xor     r8d, r8d; dwFlags
0x140010bf5  xor     ecx, ecx; lpMutexAttributes
0x140010bf7  call    cs:__imp_CreateMutexExW
0x140010bfd  mov     rbx, rax
0x140010c00  test    rax, rax
0x140010c03  jnz     short loc_140010C0F
0x140010c05  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140010c0a  jmp     loc_140010ED6
0x140010c0f  xor     r8d, r8d; bAlertable
0x140010c12  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140010c15  mov     rcx, rbx; hHandle
0x140010c18  call    cs:__imp_WaitForSingleObjectEx
0x140010c1e  cmp     eax, 102h
0x140010c23  jz      short loc_140010C35
0x140010c25  test    eax, 0FFFFFF7Fh
0x140010c2a  jnz     loc_140010F2E
0x140010c30  mov     rdi, rbx
0x140010c33  jmp     short loc_140010C37
0x140010c35  xor     edi, edi
0x140010c37  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x140010c3c  mov     [rsp+280h+var_250], 0
0x140010c45  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140010c4a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140010c4f  mov     esi, eax
0x140010c51  test    eax, eax
0x140010c53  jns     loc_140010CF0
0x140010c59  mov     rcx, [rbp+188h]; this
0x140010c60  lea     r9, aWilDetailsAbiS_0; "wil::details_abi::SemaphoreValue::TryGe"...
0x140010c67  lea     r8, aWil; "wil"
0x140010c6e  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x140010c72  mov     edx, 66h ; 'f'; void *
0x140010c77  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010c7c  mov     rcx, [rbp+188h]; this
0x140010c83  lea     r9, aWilDetailsAbiS; "wil::details_abi::SemaphoreValue::TryGe"...
0x140010c8a  lea     r8, aWil; "wil"
0x140010c91  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x140010c95  mov     edx, 6Fh ; 'o'; void *
0x140010c9a  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010c9f  mov     rcx, [rbp+188h]; this
0x140010ca6  lea     r9, aWilDetailsAbiP_2; "wil::details_abi::ProcessLocalStorageDa"...
0x140010cad  lea     r8, aWil; "wil"
0x140010cb4  mov     dword ptr [rsp+280h+var_260], esi; char *
0x140010cb8  mov     edx, 12Eh; void *
0x140010cbd  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010cc2  test    rdi, rdi
0x140010cc5  jz      short loc_140010CD8
0x140010cc7  mov     rcx, rdi; hMutex
0x140010cca  call    cs:__imp_ReleaseMutex
0x140010cd0  test    eax, eax
0x140010cd2  jz      loc_140010F3B
0x140010cd8  mov     rcx, rbx; hObject
0x140010cdb  call    cs:__imp_CloseHandle
0x140010ce1  test    eax, eax
0x140010ce3  jz      loc_140010F54
0x140010ce9  mov     eax, esi
0x140010ceb  jmp     loc_140010ED6
0x140010cf0  mov     rax, [rsp+280h+var_250]
0x140010cf5  lea     rcx, ds:0[rax*4]
0x140010cfd  test    rcx, rcx
0x140010d00  jz      short loc_140010D10
0x140010d02  mov     [r15], rcx
0x140010d05  mov     eax, [rcx]
0x140010d07  inc     eax
0x140010d09  mov     [rcx], eax
0x140010d0b  jmp     loc_140010EAC
0x140010d10  mov     rdx, r14; dwBytes
0x140010d13  mov     qword ptr [r15], 0
0x140010d1a  mov     ecx, 8; dwFlags
0x140010d1f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140010d24  mov     r14, rax
0x140010d27  test    rax, rax
0x140010d2a  jnz     short loc_140010D56
0x140010d2c  mov     rcx, [rbp+188h]; this
0x140010d33  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x140010d3a  mov     esi, 8007000Eh
0x140010d3f  lea     r8, aWil; "wil"
0x140010d46  mov     edx, 14Bh; void *
0x140010d4b  mov     dword ptr [rsp+280h+var_260], esi; wil::details *
0x140010d4f  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010d54  jmp     short loc_140010DCA
0x140010d56  xorps   xmm0, xmm0
0x140010d59  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x140010d5f  test    r14b, 3
0x140010d63  jnz     loc_140010F6D
0x140010d69  mov     r9, r14
0x140010d6c  lea     rdx, [rsp+280h+Name]; wchar_t *
0x140010d71  shr     r9, 2; unsigned __int64
0x140010d75  lea     rcx, [rsp+280h+var_250]; this
0x140010d7a  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x140010d7f  mov     esi, eax
0x140010d81  test    eax, eax
0x140010d83  jns     loc_140010E19
0x140010d89  mov     rcx, [rbp+188h]; this
0x140010d90  lea     r9, aWilDetailsAbiP_0; "wil::details_abi::ProcessLocalStorageDa"...
0x140010d97  lea     r8, aWil; "wil"
0x140010d9e  mov     dword ptr [rsp+280h+var_260], eax; wil::details *
0x140010da2  mov     edx, 14Eh; void *
0x140010da7  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010dac  lea     rcx, [rsp+280h+var_250]; this
0x140010db1  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140010db6  call    cs:__imp_GetProcessHeap
0x140010dbc  mov     r8, r14; lpMem
0x140010dbf  xor     edx, edx; dwFlags
0x140010dc1  mov     rcx, rax; hHeap
0x140010dc4  call    cs:__imp_HeapFree
0x140010dca  mov     rcx, [rbp+188h]; this
0x140010dd1  lea     r9, aWilDetailsAbiP_2; "wil::details_abi::ProcessLocalStorageDa"...
0x140010dd8  lea     r8, aWil; "wil"
0x140010ddf  mov     dword ptr [rsp+280h+var_260], esi; char *
0x140010de3  mov     edx, 137h; void *
0x140010de8  call    ?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z; wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)
0x140010ded  test    rdi, rdi
0x140010df0  jz      short loc_140010E03
0x140010df2  mov     rcx, rdi; hMutex
0x140010df5  call    cs:__imp_ReleaseMutex
0x140010dfb  test    eax, eax
0x140010dfd  jz      loc_140010F73
0x140010e03  mov     rcx, rbx; hObject
0x140010e06  call    cs:__imp_CloseHandle
0x140010e0c  test    eax, eax
0x140010e0e  jz      loc_140010F15
0x140010e14  jmp     loc_140010CE9
0x140010e19  mov     rax, [rsp+280h+var_250]
0x140010e1e  lea     rcx, [r14+28h]; void *
0x140010e22  mov     [r14+10h], rax
0x140010e26  xor     edx, edx; Val
0x140010e28  mov     rax, [rsp+280h+var_250+8]
0x140010e2d  mov     r8d, 108h; Size
0x140010e33  mov     [r14+18h], rax
0x140010e37  mov     dword ptr [r14], 1
0x140010e3e  mov     [r14+8], rbx
0x140010e42  mov     [rsp+280h+var_250], 0
0x140010e4b  mov     [rsp+280h+var_250+8], 0
0x140010e54  call    memset_0
0x140010e59  xor     eax, eax
0x140010e5b  lea     rcx, [r14+28h]; this
0x140010e5f  mov     [r14+20h], rax
0x140010e63  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140010e68  lea     rbx, [r14+0E8h]
0x140010e6f  xor     r8d, r8d; Flags
0x140010e72  mov     rcx, rbx; lpCriticalSection
0x140010e75  xor     edx, edx; dwSpinCount
0x140010e77  call    cs:__imp_InitializeCriticalSectionEx
0x140010e7d  mov     qword ptr [rbx+28h], 0
0x140010e85  lea     rcx, [rsp+280h+var_250]; this
0x140010e8a  mov     qword ptr [rbx+30h], 0
0x140010e92  mov     qword ptr [rbx+38h], 0
0x140010e9a  mov     qword ptr [rbx+40h], 0
0x140010ea2  mov     [r15], r14
0x140010ea5  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140010eaa  xor     ebx, ebx
0x140010eac  test    rdi, rdi
0x140010eaf  jz      short loc_140010EC2
0x140010eb1  mov     rcx, rdi; hMutex
0x140010eb4  call    cs:__imp_ReleaseMutex
0x140010eba  test    eax, eax
0x140010ebc  jz      loc_140010F8C
0x140010ec2  test    rbx, rbx
0x140010ec5  jz      short loc_140010ED4
0x140010ec7  mov     rcx, rbx; hObject
0x140010eca  call    cs:__imp_CloseHandle
0x140010ed0  test    eax, eax
0x140010ed2  jz      short loc_140010EFC
0x140010ed4  xor     eax, eax
0x140010ed6  mov     rcx, [rbp+180h+var_30]
0x140010edd  xor     rcx, rsp; StackCookie
0x140010ee0  call    __security_check_cookie
0x140010ee5  mov     rbx, [rsp+280h+arg_10]
0x140010eed  add     rsp, 260h
0x140010ef4  pop     r15
0x140010ef6  pop     r14
0x140010ef8  pop     rdi
0x140010ef9  pop     rsi
0x140010efa  pop     rbp
0x140010efb  retn
0x140010efc  mov     rcx, [rbp+188h]; this
0x140010f03  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010f0a  mov     edx, 0A0Bh; void *
0x140010f0f  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010f15  mov     rcx, [rbp+188h]; this
0x140010f1c  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010f23  mov     edx, 0A0Bh; void *
0x140010f28  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010f2e  mov     rcx, [rbp+188h]; this
0x140010f35  call    ?FailFast_Unexpected@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::FailFast_Unexpected(void *,uint,char const *,char const *)
0x140010f3b  mov     rcx, [rbp+188h]; this
0x140010f42  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010f49  mov     edx, 0A15h; void *
0x140010f4e  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010f54  mov     rcx, [rbp+188h]; this
0x140010f5b  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140010f62  mov     edx, 0A0Bh; void *
0x140010f67  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010f6d  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x140010f73  mov     rcx, [rbp+188h]; this
0x140010f7a  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010f81  mov     edx, 0A15h; void *
0x140010f86  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
0x140010f8c  mov     rcx, [rbp+188h]; this
0x140010f93  lea     r9, aWilDetailsRele; "wil::details::ReleaseMutex"
0x140010f9a  mov     edx, 0A15h; void *
0x140010f9f  call    ?_FailFast_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_FailFast_GetLastError(void *,uint,char const *,char const *)
```
