# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003f2c`
- end: `0x180004337`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800053c8`

## callees

- `0x1800032a0`
- `0x180003870`
- `0x180003f2c`
- `0x180004e8c`
- `0x180005d08`
- `0x180006608`
- `0x180008344`
- `0x180009a04`
- `0x18000abcc`
- `0x18000b008`
- `0x18000b828`
- `0x18000bae8`
- `0x18000d6d2`
- `0x18000d700`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004170`
- `KERNEL32!HeapFree` at `0x180004170`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180004226`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180004226`
- `KERNEL32!ReleaseMutex` at `0x180004084`
- `KERNEL32!ReleaseMutex` at `0x180004198`
- `KERNEL32!ReleaseMutex` at `0x180004257`
- `KERNEL32!ReleaseMutex` at `0x180004084`
- `KERNEL32!ReleaseMutex` at `0x180004198`
- `KERNEL32!ReleaseMutex` at `0x180004257`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003fff`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003fff`
- `KERNEL32!CloseHandle` at `0x180003fdb`
- `KERNEL32!CloseHandle` at `0x1800040a4`
- `KERNEL32!CloseHandle` at `0x1800041b4`
- `KERNEL32!CloseHandle` at `0x180004273`
- `KERNEL32!CloseHandle` at `0x180003fdb`
- `KERNEL32!CloseHandle` at `0x1800040a4`
- `KERNEL32!CloseHandle` at `0x1800041b4`
- `KERNEL32!CloseHandle` at `0x180004273`
- `KERNEL32!CreateMutexExW` at `0x180003fa9`
- `KERNEL32!CreateMutexExW` at `0x180003fa9`
- `KERNEL32!GetCurrentProcessId` at `0x180003f62`
- `KERNEL32!GetCurrentProcessId` at `0x180003f62`
- `KERNEL32!GetProcessHeap` at `0x18000415c`
- `KERNEL32!GetProcessHeap` at `0x18000415c`

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
0x180003f2c  mov     [rsp-8+arg_10], rbx
0x180003f31  push    rbp
0x180003f32  push    rsi
0x180003f33  push    rdi
0x180003f34  push    r14
0x180003f36  push    r15
0x180003f38  lea     rbp, [rsp-170h]
0x180003f40  sub     rsp, 270h
0x180003f47  mov     rax, cs:__security_cookie
0x180003f4e  xor     rax, rsp
0x180003f51  mov     [rbp+190h+var_30], rax
0x180003f58  and     qword ptr [rdx], 0
0x180003f5c  mov     r15, rdx
0x180003f5f  mov     rbx, rcx
0x180003f62  call    cs:__imp_GetCurrentProcessId
0x180003f69  nop     dword ptr [rax+rax+00h]
0x180003f6e  mov     esi, 130h
0x180003f73  mov     [rsp+290h+var_268], rbx
0x180003f78  mov     r9d, eax
0x180003f7b  mov     [rsp+290h+var_270], esi; int
0x180003f7f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003f86  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180003f8b  lea     edx, [rsi-2Ch]; unsigned __int64
0x180003f8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f93  and     [rsp+290h+hObject], 0
0x180003f99  lea     rdx, [rsp+290h+Name]; lpName
0x180003f9e  mov     r9d, 1F0001h; dwDesiredAccess
0x180003fa4  xor     r8d, r8d; dwFlags
0x180003fa7  xor     ecx, ecx; lpMutexAttributes
0x180003fa9  call    cs:__imp_CreateMutexExW
0x180003fb0  nop     dword ptr [rax+rax+00h]
0x180003fb5  mov     rdx, rax
0x180003fb8  lea     rcx, [rsp+290h+hObject]
0x180003fbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003fc2  mov     rbx, [rsp+290h+hObject]
0x180003fc7  test    rbx, rbx
0x180003fca  jnz     short loc_180003FF6
0x180003fcc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003fd1  mov     edi, eax
0x180003fd3  test    rbx, rbx
0x180003fd6  jz      short loc_180003FEF
0x180003fd8  mov     rcx, rbx; hObject
0x180003fdb  call    cs:__imp_CloseHandle
0x180003fe2  nop     dword ptr [rax+rax+00h]
0x180003fe7  test    eax, eax
0x180003fe9  jz      loc_1800042D0
0x180003fef  mov     eax, edi
0x180003ff1  jmp     loc_180004285
0x180003ff6  xor     r8d, r8d; bAlertable
0x180003ff9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003ffc  mov     rcx, rbx; hHandle
0x180003fff  call    cs:__imp_WaitForSingleObjectEx
0x180004006  nop     dword ptr [rax+rax+00h]
0x18000400b  cmp     eax, 102h
0x180004010  jz      short loc_180004022
0x180004012  test    eax, 0FFFFFF7Fh
0x180004017  jnz     loc_1800042E2
0x18000401d  mov     r14, rbx
0x180004020  jmp     short loc_180004025
0x180004022  xor     r14d, r14d
0x180004025  and     [rsp+290h+var_248], 0
0x18000402b  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180004030  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180004035  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000403a  mov     edi, eax
0x18000403c  test    eax, eax
0x18000403e  jns     short loc_1800040BD
0x180004040  mov     rcx, [rbp+198h]; this
0x180004047  mov     r9d, eax; char *
0x18000404a  mov     edx, 64h ; 'd'; void *
0x18000404f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004054  mov     rcx, [rbp+198h]; this
0x18000405b  mov     r9d, edi; char *
0x18000405e  mov     edx, 6Dh ; 'm'; void *
0x180004063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004068  mov     rcx, [rbp+198h]; this
0x18000406f  mov     r9d, edi; char *
0x180004072  mov     edx, 12Bh; void *
0x180004077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000407c  test    r14, r14
0x18000407f  jz      short loc_180004098
0x180004081  mov     rcx, r14; hMutex
0x180004084  call    cs:__imp_ReleaseMutex
0x18000408b  nop     dword ptr [rax+rax+00h]
0x180004090  test    eax, eax
0x180004092  jz      loc_1800042EF
0x180004098  test    rbx, rbx
0x18000409b  jz      loc_180003FEF
0x1800040a1  mov     rcx, rbx; hObject
0x1800040a4  call    cs:__imp_CloseHandle
0x1800040ab  nop     dword ptr [rax+rax+00h]
0x1800040b0  test    eax, eax
0x1800040b2  jz      loc_1800042BE
0x1800040b8  jmp     loc_180003FEF
0x1800040bd  mov     rax, [rsp+290h+var_248]
0x1800040c2  lea     rcx, ds:0[rax*4]
0x1800040ca  test    rcx, rcx
0x1800040cd  jz      short loc_1800040E5
0x1800040cf  mov     [r15], rcx
0x1800040d2  mov     ecx, [rcx]
0x1800040d4  mov     rax, [r15]
0x1800040d7  inc     ecx
0x1800040d9  mov     rbx, [rsp+290h+hObject]
0x1800040de  mov     [rax], ecx
0x1800040e0  jmp     loc_18000424F
0x1800040e5  and     qword ptr [r15], 0
0x1800040e9  mov     rdx, rsi; dwBytes
0x1800040ec  mov     ecx, 8; dwFlags
0x1800040f1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800040f6  mov     rdi, rax
0x1800040f9  test    rax, rax
0x1800040fc  jnz     short loc_180004119
0x1800040fe  mov     rcx, [rbp+198h]; this
0x180004105  mov     esi, 8007000Eh
0x18000410a  mov     r9d, esi; char *
0x18000410d  mov     edx, 148h; void *
0x180004112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004117  jmp     short loc_18000417C
0x180004119  xorps   xmm0, xmm0
0x18000411c  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004121  mov     r8, rdi; void *
0x180004124  lea     rcx, [rsp+290h+var_258]; this
0x180004129  movdqu  [rsp+290h+var_258], xmm0
0x18000412f  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180004134  mov     esi, eax
0x180004136  test    eax, eax
0x180004138  jns     loc_1800041CF
0x18000413e  mov     rcx, [rbp+198h]; this
0x180004145  mov     r9d, eax; char *
0x180004148  mov     edx, 14Bh; void *
0x18000414d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004152  lea     rcx, [rsp+290h+var_258]; this
0x180004157  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000415c  call    cs:__imp_GetProcessHeap
0x180004163  nop     dword ptr [rax+rax+00h]
0x180004168  mov     r8, rdi; lpMem
0x18000416b  xor     edx, edx; dwFlags
0x18000416d  mov     rcx, rax; hHeap
0x180004170  call    cs:__imp_HeapFree
0x180004177  nop     dword ptr [rax+rax+00h]
0x18000417c  mov     rcx, [rbp+198h]; this
0x180004183  mov     r9d, esi; char *
0x180004186  mov     edx, 134h; void *
0x18000418b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004190  test    r14, r14
0x180004193  jz      short loc_1800041AC
0x180004195  mov     rcx, r14; hMutex
0x180004198  call    cs:__imp_ReleaseMutex
0x18000419f  nop     dword ptr [rax+rax+00h]
0x1800041a4  test    eax, eax
0x1800041a6  jz      loc_180004301
0x1800041ac  test    rbx, rbx
0x1800041af  jz      short loc_1800041C8
0x1800041b1  mov     rcx, rbx; hObject
0x1800041b4  call    cs:__imp_CloseHandle
0x1800041bb  nop     dword ptr [rax+rax+00h]
0x1800041c0  test    eax, eax
0x1800041c2  jz      loc_180004313
0x1800041c8  mov     eax, esi
0x1800041ca  jmp     loc_180004285
0x1800041cf  mov     rax, qword ptr [rsp+290h+var_258]
0x1800041d4  lea     rcx, [rdi+28h]; void *
0x1800041d8  mov     [rdi+10h], rax
0x1800041dc  xor     edx, edx; Val
0x1800041de  mov     rax, qword ptr [rsp+290h+var_258+8]
0x1800041e3  mov     r8d, 108h; Size
0x1800041e9  mov     [rdi+8], rbx
0x1800041ed  xor     ebx, ebx
0x1800041ef  and     qword ptr [rsp+290h+var_258], rbx
0x1800041f4  and     qword ptr [rsp+290h+var_258+8], rbx
0x1800041f9  mov     [rdi+18h], rax
0x1800041fd  mov     dword ptr [rdi], 1
0x180004203  call    memset_0
0x180004208  xor     eax, eax
0x18000420a  lea     rcx, [rdi+28h]; this
0x18000420e  mov     [rdi+20h], rax
0x180004212  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004217  lea     rsi, [rdi+0E8h]
0x18000421e  xor     r8d, r8d; Flags
0x180004221  mov     rcx, rsi; lpCriticalSection
0x180004224  xor     edx, edx; dwSpinCount
0x180004226  call    cs:__imp_InitializeCriticalSectionEx
0x18000422d  nop     dword ptr [rax+rax+00h]
0x180004232  and     [rsi+28h], rbx
0x180004236  lea     rcx, [rsp+290h+var_258]; this
0x18000423b  and     [rsi+30h], rbx
0x18000423f  and     [rsi+38h], rbx
0x180004243  and     [rsi+40h], rbx
0x180004247  mov     [r15], rdi
0x18000424a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000424f  test    r14, r14
0x180004252  jz      short loc_18000426B
0x180004254  mov     rcx, r14; hMutex
0x180004257  call    cs:__imp_ReleaseMutex
0x18000425e  nop     dword ptr [rax+rax+00h]
0x180004263  test    eax, eax
0x180004265  jz      loc_180004325
0x18000426b  test    rbx, rbx
0x18000426e  jz      short loc_180004283
0x180004270  mov     rcx, rbx; hObject
0x180004273  call    cs:__imp_CloseHandle
0x18000427a  nop     dword ptr [rax+rax+00h]
0x18000427f  test    eax, eax
0x180004281  jz      short loc_1800042AC
0x180004283  xor     eax, eax
0x180004285  mov     rcx, [rbp+190h+var_30]
0x18000428c  xor     rcx, rsp; StackCookie
0x18000428f  call    __security_check_cookie
0x180004294  mov     rbx, [rsp+290h+arg_10]
0x18000429c  add     rsp, 270h
0x1800042a3  pop     r15
0x1800042a5  pop     r14
0x1800042a7  pop     rdi
0x1800042a8  pop     rsi
0x1800042a9  pop     rbp
0x1800042aa  retn
0x1800042ac  mov     rcx, [rbp+198h]; this
0x1800042b3  mov     edx, 9CDh; void *
0x1800042b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042be  mov     rcx, [rbp+198h]; this
0x1800042c5  mov     edx, 9CDh; void *
0x1800042ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042d0  mov     rcx, [rbp+198h]; this
0x1800042d7  mov     edx, 9CDh; void *
0x1800042dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042e2  mov     rcx, [rbp+198h]; this
0x1800042e9  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800042ef  mov     rcx, [rbp+198h]; this
0x1800042f6  mov     edx, 9D7h; void *
0x1800042fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004301  mov     rcx, [rbp+198h]; this
0x180004308  mov     edx, 9D7h; void *
0x18000430d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004313  mov     rcx, [rbp+198h]; this
0x18000431a  mov     edx, 9CDh; void *
0x18000431f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004325  mov     rcx, [rbp+198h]; this
0x18000432c  mov     edx, 9D7h; void *
0x180004331  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
