# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000a04c`
- end: `0x18000a457`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000a7a4`

## callees

- `0x180006310`
- `0x180009508`
- `0x1800099d8`
- `0x18000a04c`
- `0x18000a5c4`
- `0x18000a934`
- `0x18000b1c8`
- `0x18000bf30`
- `0x18000d2c8`
- `0x18000dd90`
- `0x18000e5b8`
- `0x18000e860`
- `0x180030362`
- `0x180030390`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000a0fb`
- `KERNEL32!CloseHandle` at `0x18000a1c4`
- `KERNEL32!CloseHandle` at `0x18000a2d4`
- `KERNEL32!CloseHandle` at `0x18000a393`
- `KERNEL32!CloseHandle` at `0x18000a0fb`
- `KERNEL32!CloseHandle` at `0x18000a1c4`
- `KERNEL32!CloseHandle` at `0x18000a2d4`
- `KERNEL32!CloseHandle` at `0x18000a393`
- `KERNEL32!GetProcessHeap` at `0x18000a27c`
- `KERNEL32!GetProcessHeap` at `0x18000a27c`
- `KERNEL32!HeapFree` at `0x18000a290`
- `KERNEL32!HeapFree` at `0x18000a290`
- `KERNEL32!ReleaseMutex` at `0x18000a1a4`
- `KERNEL32!ReleaseMutex` at `0x18000a2b8`
- `KERNEL32!ReleaseMutex` at `0x18000a377`
- `KERNEL32!ReleaseMutex` at `0x18000a1a4`
- `KERNEL32!ReleaseMutex` at `0x18000a2b8`
- `KERNEL32!ReleaseMutex` at `0x18000a377`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a11f`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000a11f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000a346`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000a346`
- `KERNEL32!GetCurrentProcessId` at `0x18000a082`
- `KERNEL32!GetCurrentProcessId` at `0x18000a082`
- `KERNEL32!CreateMutexExW` at `0x18000a0c9`
- `KERNEL32!CreateMutexExW` at `0x18000a0c9`

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
0x18000a04c  mov     [rsp-8+arg_10], rbx
0x18000a051  push    rbp
0x18000a052  push    rsi
0x18000a053  push    rdi
0x18000a054  push    r14
0x18000a056  push    r15
0x18000a058  lea     rbp, [rsp-170h]
0x18000a060  sub     rsp, 270h
0x18000a067  mov     rax, cs:__security_cookie
0x18000a06e  xor     rax, rsp
0x18000a071  mov     [rbp+190h+var_30], rax
0x18000a078  and     qword ptr [rdx], 0
0x18000a07c  mov     r15, rdx
0x18000a07f  mov     rbx, rcx
0x18000a082  call    cs:__imp_GetCurrentProcessId
0x18000a089  nop     dword ptr [rax+rax+00h]
0x18000a08e  mov     esi, 130h
0x18000a093  mov     [rsp+290h+var_268], rbx
0x18000a098  mov     r9d, eax
0x18000a09b  mov     [rsp+290h+var_270], esi; int
0x18000a09f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a0a6  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a0ab  lea     edx, [rsi-2Ch]; unsigned __int64
0x18000a0ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a0b3  and     [rsp+290h+hObject], 0
0x18000a0b9  lea     rdx, [rsp+290h+Name]; lpName
0x18000a0be  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a0c4  xor     r8d, r8d; dwFlags
0x18000a0c7  xor     ecx, ecx; lpMutexAttributes
0x18000a0c9  call    cs:__imp_CreateMutexExW
0x18000a0d0  nop     dword ptr [rax+rax+00h]
0x18000a0d5  mov     rdx, rax
0x18000a0d8  lea     rcx, [rsp+290h+hObject]
0x18000a0dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a0e2  mov     rbx, [rsp+290h+hObject]
0x18000a0e7  test    rbx, rbx
0x18000a0ea  jnz     short loc_18000A116
0x18000a0ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a0f1  mov     edi, eax
0x18000a0f3  test    rbx, rbx
0x18000a0f6  jz      short loc_18000A10F
0x18000a0f8  mov     rcx, rbx; hObject
0x18000a0fb  call    cs:__imp_CloseHandle
0x18000a102  nop     dword ptr [rax+rax+00h]
0x18000a107  test    eax, eax
0x18000a109  jz      loc_18000A3F0
0x18000a10f  mov     eax, edi
0x18000a111  jmp     loc_18000A3A5
0x18000a116  xor     r8d, r8d; bAlertable
0x18000a119  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a11c  mov     rcx, rbx; hHandle
0x18000a11f  call    cs:__imp_WaitForSingleObjectEx
0x18000a126  nop     dword ptr [rax+rax+00h]
0x18000a12b  cmp     eax, 102h
0x18000a130  jz      short loc_18000A142
0x18000a132  test    eax, 0FFFFFF7Fh
0x18000a137  jnz     loc_18000A402
0x18000a13d  mov     r14, rbx
0x18000a140  jmp     short loc_18000A145
0x18000a142  xor     r14d, r14d
0x18000a145  and     [rsp+290h+var_248], 0
0x18000a14b  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000a150  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a155  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a15a  mov     edi, eax
0x18000a15c  test    eax, eax
0x18000a15e  jns     short loc_18000A1DD
0x18000a160  mov     rcx, [rbp+198h]; this
0x18000a167  mov     r9d, eax; char *
0x18000a16a  mov     edx, 64h ; 'd'; void *
0x18000a16f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a174  mov     rcx, [rbp+198h]; this
0x18000a17b  mov     r9d, edi; char *
0x18000a17e  mov     edx, 6Dh ; 'm'; void *
0x18000a183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a188  mov     rcx, [rbp+198h]; this
0x18000a18f  mov     r9d, edi; char *
0x18000a192  mov     edx, 12Bh; void *
0x18000a197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a19c  test    r14, r14
0x18000a19f  jz      short loc_18000A1B8
0x18000a1a1  mov     rcx, r14; hMutex
0x18000a1a4  call    cs:__imp_ReleaseMutex
0x18000a1ab  nop     dword ptr [rax+rax+00h]
0x18000a1b0  test    eax, eax
0x18000a1b2  jz      loc_18000A40F
0x18000a1b8  test    rbx, rbx
0x18000a1bb  jz      loc_18000A10F
0x18000a1c1  mov     rcx, rbx; hObject
0x18000a1c4  call    cs:__imp_CloseHandle
0x18000a1cb  nop     dword ptr [rax+rax+00h]
0x18000a1d0  test    eax, eax
0x18000a1d2  jz      loc_18000A3DE
0x18000a1d8  jmp     loc_18000A10F
0x18000a1dd  mov     rax, [rsp+290h+var_248]
0x18000a1e2  lea     rcx, ds:0[rax*4]
0x18000a1ea  test    rcx, rcx
0x18000a1ed  jz      short loc_18000A205
0x18000a1ef  mov     [r15], rcx
0x18000a1f2  mov     ecx, [rcx]
0x18000a1f4  mov     rax, [r15]
0x18000a1f7  inc     ecx
0x18000a1f9  mov     rbx, [rsp+290h+hObject]
0x18000a1fe  mov     [rax], ecx
0x18000a200  jmp     loc_18000A36F
0x18000a205  and     qword ptr [r15], 0
0x18000a209  mov     rdx, rsi; dwBytes
0x18000a20c  mov     ecx, 8; dwFlags
0x18000a211  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a216  mov     rdi, rax
0x18000a219  test    rax, rax
0x18000a21c  jnz     short loc_18000A239
0x18000a21e  mov     rcx, [rbp+198h]; this
0x18000a225  mov     esi, 8007000Eh
0x18000a22a  mov     r9d, esi; char *
0x18000a22d  mov     edx, 148h; void *
0x18000a232  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a237  jmp     short loc_18000A29C
0x18000a239  xorps   xmm0, xmm0
0x18000a23c  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a241  mov     r8, rdi; void *
0x18000a244  lea     rcx, [rsp+290h+var_258]; this
0x18000a249  movdqu  [rsp+290h+var_258], xmm0
0x18000a24f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000a254  mov     esi, eax
0x18000a256  test    eax, eax
0x18000a258  jns     loc_18000A2EF
0x18000a25e  mov     rcx, [rbp+198h]; this
0x18000a265  mov     r9d, eax; char *
0x18000a268  mov     edx, 14Bh; void *
0x18000a26d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a272  lea     rcx, [rsp+290h+var_258]; this
0x18000a277  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a27c  call    cs:__imp_GetProcessHeap
0x18000a283  nop     dword ptr [rax+rax+00h]
0x18000a288  mov     r8, rdi; lpMem
0x18000a28b  xor     edx, edx; dwFlags
0x18000a28d  mov     rcx, rax; hHeap
0x18000a290  call    cs:__imp_HeapFree
0x18000a297  nop     dword ptr [rax+rax+00h]
0x18000a29c  mov     rcx, [rbp+198h]; this
0x18000a2a3  mov     r9d, esi; char *
0x18000a2a6  mov     edx, 134h; void *
0x18000a2ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2b0  test    r14, r14
0x18000a2b3  jz      short loc_18000A2CC
0x18000a2b5  mov     rcx, r14; hMutex
0x18000a2b8  call    cs:__imp_ReleaseMutex
0x18000a2bf  nop     dword ptr [rax+rax+00h]
0x18000a2c4  test    eax, eax
0x18000a2c6  jz      loc_18000A421
0x18000a2cc  test    rbx, rbx
0x18000a2cf  jz      short loc_18000A2E8
0x18000a2d1  mov     rcx, rbx; hObject
0x18000a2d4  call    cs:__imp_CloseHandle
0x18000a2db  nop     dword ptr [rax+rax+00h]
0x18000a2e0  test    eax, eax
0x18000a2e2  jz      loc_18000A433
0x18000a2e8  mov     eax, esi
0x18000a2ea  jmp     loc_18000A3A5
0x18000a2ef  mov     rax, qword ptr [rsp+290h+var_258]
0x18000a2f4  lea     rcx, [rdi+28h]; void *
0x18000a2f8  mov     [rdi+10h], rax
0x18000a2fc  xor     edx, edx; Val
0x18000a2fe  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000a303  mov     r8d, 108h; Size
0x18000a309  mov     [rdi+8], rbx
0x18000a30d  xor     ebx, ebx
0x18000a30f  and     qword ptr [rsp+290h+var_258], rbx
0x18000a314  and     qword ptr [rsp+290h+var_258+8], rbx
0x18000a319  mov     [rdi+18h], rax
0x18000a31d  mov     dword ptr [rdi], 1
0x18000a323  call    memset_0
0x18000a328  xor     eax, eax
0x18000a32a  lea     rcx, [rdi+28h]; this
0x18000a32e  mov     [rdi+20h], rax
0x18000a332  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a337  lea     rsi, [rdi+0E8h]
0x18000a33e  xor     r8d, r8d; Flags
0x18000a341  mov     rcx, rsi; lpCriticalSection
0x18000a344  xor     edx, edx; dwSpinCount
0x18000a346  call    cs:__imp_InitializeCriticalSectionEx
0x18000a34d  nop     dword ptr [rax+rax+00h]
0x18000a352  and     [rsi+28h], rbx
0x18000a356  lea     rcx, [rsp+290h+var_258]; this
0x18000a35b  and     [rsi+30h], rbx
0x18000a35f  and     [rsi+38h], rbx
0x18000a363  and     [rsi+40h], rbx
0x18000a367  mov     [r15], rdi
0x18000a36a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000a36f  test    r14, r14
0x18000a372  jz      short loc_18000A38B
0x18000a374  mov     rcx, r14; hMutex
0x18000a377  call    cs:__imp_ReleaseMutex
0x18000a37e  nop     dword ptr [rax+rax+00h]
0x18000a383  test    eax, eax
0x18000a385  jz      loc_18000A445
0x18000a38b  test    rbx, rbx
0x18000a38e  jz      short loc_18000A3A3
0x18000a390  mov     rcx, rbx; hObject
0x18000a393  call    cs:__imp_CloseHandle
0x18000a39a  nop     dword ptr [rax+rax+00h]
0x18000a39f  test    eax, eax
0x18000a3a1  jz      short loc_18000A3CC
0x18000a3a3  xor     eax, eax
0x18000a3a5  mov     rcx, [rbp+190h+var_30]
0x18000a3ac  xor     rcx, rsp; StackCookie
0x18000a3af  call    __security_check_cookie
0x18000a3b4  mov     rbx, [rsp+290h+arg_10]
0x18000a3bc  add     rsp, 270h
0x18000a3c3  pop     r15
0x18000a3c5  pop     r14
0x18000a3c7  pop     rdi
0x18000a3c8  pop     rsi
0x18000a3c9  pop     rbp
0x18000a3ca  retn
0x18000a3cc  mov     rcx, [rbp+198h]; this
0x18000a3d3  mov     edx, 9CDh; void *
0x18000a3d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a3de  mov     rcx, [rbp+198h]; this
0x18000a3e5  mov     edx, 9CDh; void *
0x18000a3ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a3f0  mov     rcx, [rbp+198h]; this
0x18000a3f7  mov     edx, 9CDh; void *
0x18000a3fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a402  mov     rcx, [rbp+198h]; this
0x18000a409  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a40f  mov     rcx, [rbp+198h]; this
0x18000a416  mov     edx, 9D7h; void *
0x18000a41b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a421  mov     rcx, [rbp+198h]; this
0x18000a428  mov     edx, 9D7h; void *
0x18000a42d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a433  mov     rcx, [rbp+198h]; this
0x18000a43a  mov     edx, 9CDh; void *
0x18000a43f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a445  mov     rcx, [rbp+198h]; this
0x18000a44c  mov     edx, 9D7h; void *
0x18000a451  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
