# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a5fc`
- end: `0x18000aa07`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000b0d8`

## callees

- `0x180009a4c`
- `0x180009f7c`
- `0x18000a5fc`
- `0x18000aa10`
- `0x18000b268`
- `0x18000bc24`
- `0x18000ce30`
- `0x18000ea18`
- `0x18000fce4`
- `0x180010120`
- `0x180010a48`
- `0x180010d18`
- `0x180011a62`
- `0x180011a90`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000a632`
- `KERNEL32!GetCurrentProcessId` at `0x18000a632`
- `KERNEL32!CreateMutexExW` at `0x18000a679`
- `KERNEL32!CreateMutexExW` at `0x18000a679`
- `KERNEL32!GetProcessHeap` at `0x18000a82c`
- `KERNEL32!GetProcessHeap` at `0x18000a82c`
- `KERNEL32!HeapFree` at `0x18000a840`
- `KERNEL32!HeapFree` at `0x18000a840`
- `KERNEL32!CloseHandle` at `0x18000a6ab`
- `KERNEL32!CloseHandle` at `0x18000a774`
- `KERNEL32!CloseHandle` at `0x18000a884`
- `KERNEL32!CloseHandle` at `0x18000a943`
- `KERNEL32!CloseHandle` at `0x18000a6ab`
- `KERNEL32!CloseHandle` at `0x18000a774`
- `KERNEL32!CloseHandle` at `0x18000a884`
- `KERNEL32!CloseHandle` at `0x18000a943`
- `KERNEL32!ReleaseMutex` at `0x18000a754`
- `KERNEL32!ReleaseMutex` at `0x18000a868`
- `KERNEL32!ReleaseMutex` at `0x18000a927`
- `KERNEL32!ReleaseMutex` at `0x18000a754`
- `KERNEL32!ReleaseMutex` at `0x18000a868`
- `KERNEL32!ReleaseMutex` at `0x18000a927`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a6cf`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a6cf`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000a8f6`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000a8f6`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  unsigned int v7; // edi
  DWORD v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // r9
  void *v13; // r14
  int ValueInternal; // eax
  unsigned __int64 v15; // r8
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  HANDLE v23; // rbx
  char *v24; // rax
  unsigned int v25; // r8d
  char *v26; // rdi
  unsigned int v27; // esi
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hObject = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hObject,
    Mutex);
  v6 = hObject;
  if ( !hObject )
    return (unsigned int)wil::details::GetLastErrorFailHr(v5);
  v9 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v6;
  }
  v46 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v10, &v46, (bool *)v12);
  v7 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v15, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v7, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v7, v42);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v18, v19);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v20, v21);
    }
    return v7;
  }
  v22 = (_DWORD *)(4 * v46);
  if ( 4 * v46 )
  {
    *a2 = v22;
    v23 = hObject;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_26;
  }
  *a2 = 0;
  v24 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v15);
  v26 = v24;
  if ( v24 )
  {
    v45 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v45,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      *((_QWORD *)v26 + 2) = v45;
      v36 = *((_QWORD *)&v45 + 1);
      *((_QWORD *)v26 + 1) = v6;
      v23 = 0;
      v45 = 0u;
      *((_QWORD *)v26 + 3) = v36;
      *(_DWORD *)v26 = 1;
      memset_0(v26 + 40, 0, 0x108u);
      *((_QWORD *)v26 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 232), 0, 0);
      *((_QWORD *)v26 + 34) = 0;
      *((_QWORD *)v26 + 35) = 0;
      *((_QWORD *)v26 + 36) = 0;
      *((_QWORD *)v26 + 37) = 0;
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
LABEL_26:
      if ( v13 && !ReleaseMutex(v13) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v37, v38);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v45);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v43);
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18000a5fc  mov     [rsp-8+arg_10], rbx
0x18000a601  push    rbp
0x18000a602  push    rsi
0x18000a603  push    rdi
0x18000a604  push    r14
0x18000a606  push    r15
0x18000a608  lea     rbp, [rsp-170h]
0x18000a610  sub     rsp, 270h
0x18000a617  mov     rax, cs:__security_cookie
0x18000a61e  xor     rax, rsp
0x18000a621  mov     [rbp+190h+var_30], rax
0x18000a628  and     qword ptr [rdx], 0
0x18000a62c  mov     r15, rdx
0x18000a62f  mov     rbx, rcx
0x18000a632  call    cs:__imp_GetCurrentProcessId
0x18000a639  nop     dword ptr [rax+rax+00h]
0x18000a63e  mov     esi, 130h
0x18000a643  mov     [rsp+290h+var_268], rbx
0x18000a648  mov     r9d, eax
0x18000a64b  mov     [rsp+290h+var_270], esi; int
0x18000a64f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a656  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a65b  lea     edx, [rsi-2Ch]; unsigned __int64
0x18000a65e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a663  and     [rsp+290h+hObject], 0
0x18000a669  lea     rdx, [rsp+290h+Name]; lpName
0x18000a66e  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a674  xor     r8d, r8d; dwFlags
0x18000a677  xor     ecx, ecx; lpMutexAttributes
0x18000a679  call    cs:__imp_CreateMutexExW
0x18000a680  nop     dword ptr [rax+rax+00h]
0x18000a685  mov     rdx, rax
0x18000a688  lea     rcx, [rsp+290h+hObject]
0x18000a68d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a692  mov     rbx, [rsp+290h+hObject]
0x18000a697  test    rbx, rbx
0x18000a69a  jnz     short loc_18000A6C6
0x18000a69c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a6a1  mov     edi, eax
0x18000a6a3  test    rbx, rbx
0x18000a6a6  jz      short loc_18000A6BF
0x18000a6a8  mov     rcx, rbx; hObject
0x18000a6ab  call    cs:__imp_CloseHandle
0x18000a6b2  nop     dword ptr [rax+rax+00h]
0x18000a6b7  test    eax, eax
0x18000a6b9  jz      loc_18000A9A0
0x18000a6bf  mov     eax, edi
0x18000a6c1  jmp     loc_18000A955
0x18000a6c6  xor     r8d, r8d; bAlertable
0x18000a6c9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a6cc  mov     rcx, rbx; hHandle
0x18000a6cf  call    cs:__imp_WaitForSingleObjectEx
0x18000a6d6  nop     dword ptr [rax+rax+00h]
0x18000a6db  cmp     eax, 102h
0x18000a6e0  jz      short loc_18000A6F2
0x18000a6e2  test    eax, 0FFFFFF7Fh
0x18000a6e7  jnz     loc_18000A9B2
0x18000a6ed  mov     r14, rbx
0x18000a6f0  jmp     short loc_18000A6F5
0x18000a6f2  xor     r14d, r14d
0x18000a6f5  and     [rsp+290h+var_248], 0
0x18000a6fb  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000a700  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a705  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a70a  mov     edi, eax
0x18000a70c  test    eax, eax
0x18000a70e  jns     short loc_18000A78D
0x18000a710  mov     rcx, [rbp+198h]; this
0x18000a717  mov     r9d, eax; char *
0x18000a71a  mov     edx, 64h ; 'd'; void *
0x18000a71f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a724  mov     rcx, [rbp+198h]; this
0x18000a72b  mov     r9d, edi; char *
0x18000a72e  mov     edx, 6Dh ; 'm'; void *
0x18000a733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a738  mov     rcx, [rbp+198h]; this
0x18000a73f  mov     r9d, edi; char *
0x18000a742  mov     edx, 12Bh; void *
0x18000a747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a74c  test    r14, r14
0x18000a74f  jz      short loc_18000A768
0x18000a751  mov     rcx, r14; hMutex
0x18000a754  call    cs:__imp_ReleaseMutex
0x18000a75b  nop     dword ptr [rax+rax+00h]
0x18000a760  test    eax, eax
0x18000a762  jz      loc_18000A9BF
0x18000a768  test    rbx, rbx
0x18000a76b  jz      loc_18000A6BF
0x18000a771  mov     rcx, rbx; hObject
0x18000a774  call    cs:__imp_CloseHandle
0x18000a77b  nop     dword ptr [rax+rax+00h]
0x18000a780  test    eax, eax
0x18000a782  jz      loc_18000A98E
0x18000a788  jmp     loc_18000A6BF
0x18000a78d  mov     rax, [rsp+290h+var_248]
0x18000a792  lea     rcx, ds:0[rax*4]
0x18000a79a  test    rcx, rcx
0x18000a79d  jz      short loc_18000A7B5
0x18000a79f  mov     [r15], rcx
0x18000a7a2  mov     ecx, [rcx]
0x18000a7a4  mov     rax, [r15]
0x18000a7a7  inc     ecx
0x18000a7a9  mov     rbx, [rsp+290h+hObject]
0x18000a7ae  mov     [rax], ecx
0x18000a7b0  jmp     loc_18000A91F
0x18000a7b5  and     qword ptr [r15], 0
0x18000a7b9  mov     rdx, rsi; dwBytes
0x18000a7bc  mov     ecx, 8; dwFlags
0x18000a7c1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a7c6  mov     rdi, rax
0x18000a7c9  test    rax, rax
0x18000a7cc  jnz     short loc_18000A7E9
0x18000a7ce  mov     rcx, [rbp+198h]; this
0x18000a7d5  mov     esi, 8007000Eh
0x18000a7da  mov     r9d, esi; char *
0x18000a7dd  mov     edx, 148h; void *
0x18000a7e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7e7  jmp     short loc_18000A84C
0x18000a7e9  xorps   xmm0, xmm0
0x18000a7ec  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a7f1  mov     r8, rdi; void *
0x18000a7f4  lea     rcx, [rsp+290h+var_258]; this
0x18000a7f9  movdqu  [rsp+290h+var_258], xmm0
0x18000a7ff  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000a804  mov     esi, eax
0x18000a806  test    eax, eax
0x18000a808  jns     loc_18000A89F
0x18000a80e  mov     rcx, [rbp+198h]; this
0x18000a815  mov     r9d, eax; char *
0x18000a818  mov     edx, 14Bh; void *
0x18000a81d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a822  lea     rcx, [rsp+290h+var_258]; this
0x18000a827  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a82c  call    cs:__imp_GetProcessHeap
0x18000a833  nop     dword ptr [rax+rax+00h]
0x18000a838  mov     r8, rdi; lpMem
0x18000a83b  xor     edx, edx; dwFlags
0x18000a83d  mov     rcx, rax; hHeap
0x18000a840  call    cs:__imp_HeapFree
0x18000a847  nop     dword ptr [rax+rax+00h]
0x18000a84c  mov     rcx, [rbp+198h]; this
0x18000a853  mov     r9d, esi; char *
0x18000a856  mov     edx, 134h; void *
0x18000a85b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a860  test    r14, r14
0x18000a863  jz      short loc_18000A87C
0x18000a865  mov     rcx, r14; hMutex
0x18000a868  call    cs:__imp_ReleaseMutex
0x18000a86f  nop     dword ptr [rax+rax+00h]
0x18000a874  test    eax, eax
0x18000a876  jz      loc_18000A9D1
0x18000a87c  test    rbx, rbx
0x18000a87f  jz      short loc_18000A898
0x18000a881  mov     rcx, rbx; hObject
0x18000a884  call    cs:__imp_CloseHandle
0x18000a88b  nop     dword ptr [rax+rax+00h]
0x18000a890  test    eax, eax
0x18000a892  jz      loc_18000A9E3
0x18000a898  mov     eax, esi
0x18000a89a  jmp     loc_18000A955
0x18000a89f  mov     rax, qword ptr [rsp+290h+var_258]
0x18000a8a4  lea     rcx, [rdi+28h]; void *
0x18000a8a8  mov     [rdi+10h], rax
0x18000a8ac  xor     edx, edx; Val
0x18000a8ae  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000a8b3  mov     r8d, 108h; Size
0x18000a8b9  mov     [rdi+8], rbx
0x18000a8bd  xor     ebx, ebx
0x18000a8bf  and     qword ptr [rsp+290h+var_258], rbx
0x18000a8c4  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000a8c9  mov     [rdi+18h], rax
0x18000a8cd  mov     dword ptr [rdi], 1
0x18000a8d3  call    memset_0
0x18000a8d8  xor     eax, eax
0x18000a8da  lea     rcx, [rdi+28h]; this
0x18000a8de  mov     [rdi+20h], rax
0x18000a8e2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a8e7  lea     rsi, [rdi+0E8h]
0x18000a8ee  xor     r8d, r8d; Flags
0x18000a8f1  mov     rcx, rsi; lpCriticalSection
0x18000a8f4  xor     edx, edx; dwSpinCount
0x18000a8f6  call    cs:__imp_InitializeCriticalSectionEx
0x18000a8fd  nop     dword ptr [rax+rax+00h]
0x18000a902  and     [rsi+28h], rbx
0x18000a906  lea     rcx, [rsp+290h+var_258]; this
0x18000a90b  and     [rsi+30h], rbx
0x18000a90f  and     [rsi+38h], rbx
0x18000a913  and     [rsi+40h], rbx
0x18000a917  mov     [r15], rdi
0x18000a91a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a91f  test    r14, r14
0x18000a922  jz      short loc_18000A93B
0x18000a924  mov     rcx, r14; hMutex
0x18000a927  call    cs:__imp_ReleaseMutex
0x18000a92e  nop     dword ptr [rax+rax+00h]
0x18000a933  test    eax, eax
0x18000a935  jz      loc_18000A9F5
0x18000a93b  test    rbx, rbx
0x18000a93e  jz      short loc_18000A953
0x18000a940  mov     rcx, rbx; hObject
0x18000a943  call    cs:__imp_CloseHandle
0x18000a94a  nop     dword ptr [rax+rax+00h]
0x18000a94f  test    eax, eax
0x18000a951  jz      short loc_18000A97C
0x18000a953  xor     eax, eax
0x18000a955  mov     rcx, [rbp+190h+var_30]
0x18000a95c  xor     rcx, rsp; StackCookie
0x18000a95f  call    __security_check_cookie
0x18000a964  mov     rbx, [rsp+290h+arg_10]
0x18000a96c  add     rsp, 270h
0x18000a973  pop     r15
0x18000a975  pop     r14
0x18000a977  pop     rdi
0x18000a978  pop     rsi
0x18000a979  pop     rbp
0x18000a97a  retn
0x18000a97c  mov     rcx, [rbp+198h]; this
0x18000a983  mov     edx, 9CDh; void *
0x18000a988  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a98e  mov     rcx, [rbp+198h]; this
0x18000a995  mov     edx, 9CDh; void *
0x18000a99a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9a0  mov     rcx, [rbp+198h]; this
0x18000a9a7  mov     edx, 9CDh; void *
0x18000a9ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9b2  mov     rcx, [rbp+198h]; this
0x18000a9b9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a9bf  mov     rcx, [rbp+198h]; this
0x18000a9c6  mov     edx, 9D7h; void *
0x18000a9cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9d1  mov     rcx, [rbp+198h]; this
0x18000a9d8  mov     edx, 9D7h; void *
0x18000a9dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9e3  mov     rcx, [rbp+198h]; this
0x18000a9ea  mov     edx, 9CDh; void *
0x18000a9ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a9f5  mov     rcx, [rbp+198h]; this
0x18000a9fc  mov     edx, 9D7h; void *
0x18000aa01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
