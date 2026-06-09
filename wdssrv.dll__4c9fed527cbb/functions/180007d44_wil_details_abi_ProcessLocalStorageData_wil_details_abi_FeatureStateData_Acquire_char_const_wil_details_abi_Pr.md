# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180007d44`
- end: `0x18000814f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1035`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008644`

## callees

- `0x180006f88`
- `0x180007648`
- `0x180007d44`
- `0x180008288`
- `0x1800088b4`
- `0x180009508`
- `0x18000ada8`
- `0x18000cb0c`
- `0x18000d9dc`
- `0x18000dec0`
- `0x18000eac4`
- `0x18000ee68`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180007df3`
- `KERNEL32!CloseHandle` at `0x180007ebc`
- `KERNEL32!CloseHandle` at `0x180007fcc`
- `KERNEL32!CloseHandle` at `0x18000808b`
- `KERNEL32!CloseHandle` at `0x180007df3`
- `KERNEL32!CloseHandle` at `0x180007ebc`
- `KERNEL32!CloseHandle` at `0x180007fcc`
- `KERNEL32!CloseHandle` at `0x18000808b`
- `KERNEL32!GetProcessHeap` at `0x180007f74`
- `KERNEL32!GetProcessHeap` at `0x180007f74`
- `KERNEL32!HeapFree` at `0x180007f88`
- `KERNEL32!HeapFree` at `0x180007f88`
- `KERNEL32!ReleaseMutex` at `0x180007e9c`
- `KERNEL32!ReleaseMutex` at `0x180007fb0`
- `KERNEL32!ReleaseMutex` at `0x18000806f`
- `KERNEL32!ReleaseMutex` at `0x180007e9c`
- `KERNEL32!ReleaseMutex` at `0x180007fb0`
- `KERNEL32!ReleaseMutex` at `0x18000806f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007e17`
- `KERNEL32!WaitForSingleObjectEx` at `0x180007e17`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000803e`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18000803e`
- `KERNEL32!GetCurrentProcessId` at `0x180007d7a`
- `KERNEL32!GetCurrentProcessId` at `0x180007d7a`
- `KERNEL32!CreateMutexExW` at `0x180007dc1`
- `KERNEL32!CreateMutexExW` at `0x180007dc1`

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
0x180007d44  mov     [rsp-8+arg_10], rbx
0x180007d49  push    rbp
0x180007d4a  push    rsi
0x180007d4b  push    rdi
0x180007d4c  push    r14
0x180007d4e  push    r15
0x180007d50  lea     rbp, [rsp-170h]
0x180007d58  sub     rsp, 270h
0x180007d5f  mov     rax, cs:__security_cookie
0x180007d66  xor     rax, rsp
0x180007d69  mov     [rbp+190h+var_30], rax
0x180007d70  and     qword ptr [rdx], 0
0x180007d74  mov     r15, rdx
0x180007d77  mov     rbx, rcx
0x180007d7a  call    cs:__imp_GetCurrentProcessId
0x180007d81  nop     dword ptr [rax+rax+00h]
0x180007d86  mov     esi, 130h
0x180007d8b  mov     [rsp+290h+var_268], rbx
0x180007d90  mov     r9d, eax
0x180007d93  mov     [rsp+290h+var_270], esi; int
0x180007d97  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007d9e  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180007da3  lea     edx, [rsi-2Ch]; unsigned __int64
0x180007da6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007dab  and     [rsp+290h+hObject], 0
0x180007db1  lea     rdx, [rsp+290h+Name]; lpName
0x180007db6  mov     r9d, 1F0001h; dwDesiredAccess
0x180007dbc  xor     r8d, r8d; dwFlags
0x180007dbf  xor     ecx, ecx; lpMutexAttributes
0x180007dc1  call    cs:__imp_CreateMutexExW
0x180007dc8  nop     dword ptr [rax+rax+00h]
0x180007dcd  mov     rdx, rax
0x180007dd0  lea     rcx, [rsp+290h+hObject]
0x180007dd5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007dda  mov     rbx, [rsp+290h+hObject]
0x180007ddf  test    rbx, rbx
0x180007de2  jnz     short loc_180007E0E
0x180007de4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180007de9  mov     edi, eax
0x180007deb  test    rbx, rbx
0x180007dee  jz      short loc_180007E07
0x180007df0  mov     rcx, rbx; hObject
0x180007df3  call    cs:__imp_CloseHandle
0x180007dfa  nop     dword ptr [rax+rax+00h]
0x180007dff  test    eax, eax
0x180007e01  jz      loc_1800080E8
0x180007e07  mov     eax, edi
0x180007e09  jmp     loc_18000809D
0x180007e0e  xor     r8d, r8d; bAlertable
0x180007e11  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007e14  mov     rcx, rbx; hHandle
0x180007e17  call    cs:__imp_WaitForSingleObjectEx
0x180007e1e  nop     dword ptr [rax+rax+00h]
0x180007e23  cmp     eax, 102h
0x180007e28  jz      short loc_180007E3A
0x180007e2a  test    eax, 0FFFFFF7Fh
0x180007e2f  jnz     loc_1800080FA
0x180007e35  mov     r14, rbx
0x180007e38  jmp     short loc_180007E3D
0x180007e3a  xor     r14d, r14d
0x180007e3d  and     [rsp+290h+var_248], 0
0x180007e43  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x180007e48  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x180007e4d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180007e52  mov     edi, eax
0x180007e54  test    eax, eax
0x180007e56  jns     short loc_180007ED5
0x180007e58  mov     rcx, [rbp+198h]; this
0x180007e5f  mov     r9d, eax; char *
0x180007e62  mov     edx, 64h ; 'd'; void *
0x180007e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e6c  mov     rcx, [rbp+198h]; this
0x180007e73  mov     r9d, edi; char *
0x180007e76  mov     edx, 6Dh ; 'm'; void *
0x180007e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e80  mov     rcx, [rbp+198h]; this
0x180007e87  mov     r9d, edi; char *
0x180007e8a  mov     edx, 12Bh; void *
0x180007e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e94  test    r14, r14
0x180007e97  jz      short loc_180007EB0
0x180007e99  mov     rcx, r14; hMutex
0x180007e9c  call    cs:__imp_ReleaseMutex
0x180007ea3  nop     dword ptr [rax+rax+00h]
0x180007ea8  test    eax, eax
0x180007eaa  jz      loc_180008107
0x180007eb0  test    rbx, rbx
0x180007eb3  jz      loc_180007E07
0x180007eb9  mov     rcx, rbx; hObject
0x180007ebc  call    cs:__imp_CloseHandle
0x180007ec3  nop     dword ptr [rax+rax+00h]
0x180007ec8  test    eax, eax
0x180007eca  jz      loc_1800080D6
0x180007ed0  jmp     loc_180007E07
0x180007ed5  mov     rax, [rsp+290h+var_248]
0x180007eda  lea     rcx, ds:0[rax*4]
0x180007ee2  test    rcx, rcx
0x180007ee5  jz      short loc_180007EFD
0x180007ee7  mov     [r15], rcx
0x180007eea  mov     ecx, [rcx]
0x180007eec  mov     rax, [r15]
0x180007eef  inc     ecx
0x180007ef1  mov     rbx, [rsp+290h+hObject]
0x180007ef6  mov     [rax], ecx
0x180007ef8  jmp     loc_180008067
0x180007efd  and     qword ptr [r15], 0
0x180007f01  mov     rdx, rsi; dwBytes
0x180007f04  mov     ecx, 8; dwFlags
0x180007f09  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007f0e  mov     rdi, rax
0x180007f11  test    rax, rax
0x180007f14  jnz     short loc_180007F31
0x180007f16  mov     rcx, [rbp+198h]; this
0x180007f1d  mov     esi, 8007000Eh
0x180007f22  mov     r9d, esi; char *
0x180007f25  mov     edx, 148h; void *
0x180007f2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f2f  jmp     short loc_180007F94
0x180007f31  xorps   xmm0, xmm0
0x180007f34  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180007f39  mov     r8, rdi; void *
0x180007f3c  lea     rcx, [rsp+290h+var_258]; this
0x180007f41  movdqu  [rsp+290h+var_258], xmm0
0x180007f47  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180007f4c  mov     esi, eax
0x180007f4e  test    eax, eax
0x180007f50  jns     loc_180007FE7
0x180007f56  mov     rcx, [rbp+198h]; this
0x180007f5d  mov     r9d, eax; char *
0x180007f60  mov     edx, 14Bh; void *
0x180007f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f6a  lea     rcx, [rsp+290h+var_258]; this
0x180007f6f  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007f74  call    cs:__imp_GetProcessHeap
0x180007f7b  nop     dword ptr [rax+rax+00h]
0x180007f80  mov     r8, rdi; lpMem
0x180007f83  xor     edx, edx; dwFlags
0x180007f85  mov     rcx, rax; hHeap
0x180007f88  call    cs:__imp_HeapFree
0x180007f8f  nop     dword ptr [rax+rax+00h]
0x180007f94  mov     rcx, [rbp+198h]; this
0x180007f9b  mov     r9d, esi; char *
0x180007f9e  mov     edx, 134h; void *
0x180007fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007fa8  test    r14, r14
0x180007fab  jz      short loc_180007FC4
0x180007fad  mov     rcx, r14; hMutex
0x180007fb0  call    cs:__imp_ReleaseMutex
0x180007fb7  nop     dword ptr [rax+rax+00h]
0x180007fbc  test    eax, eax
0x180007fbe  jz      loc_180008119
0x180007fc4  test    rbx, rbx
0x180007fc7  jz      short loc_180007FE0
0x180007fc9  mov     rcx, rbx; hObject
0x180007fcc  call    cs:__imp_CloseHandle
0x180007fd3  nop     dword ptr [rax+rax+00h]
0x180007fd8  test    eax, eax
0x180007fda  jz      loc_18000812B
0x180007fe0  mov     eax, esi
0x180007fe2  jmp     loc_18000809D
0x180007fe7  mov     rax, qword ptr [rsp+290h+var_258]
0x180007fec  lea     rcx, [rdi+28h]; void *
0x180007ff0  mov     [rdi+10h], rax
0x180007ff4  xor     edx, edx; Val
0x180007ff6  mov     rax, qword ptr [rsp+290h+var_258+8]
0x180007ffb  mov     r8d, 108h; Size
0x180008001  mov     [rdi+8], rbx
0x180008005  xor     ebx, ebx
0x180008007  and     qword ptr [rsp+290h+var_258], rbx
0x18000800c  and     qword ptr [rsp+290h+var_258+8], rbx
0x180008011  mov     [rdi+18h], rax
0x180008015  mov     dword ptr [rdi], 1
0x18000801b  call    memset_0
0x180008020  xor     eax, eax
0x180008022  lea     rcx, [rdi+28h]; this
0x180008026  mov     [rdi+20h], rax
0x18000802a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000802f  lea     rsi, [rdi+0E8h]
0x180008036  xor     r8d, r8d; Flags
0x180008039  mov     rcx, rsi; lpCriticalSection
0x18000803c  xor     edx, edx; dwSpinCount
0x18000803e  call    cs:__imp_InitializeCriticalSectionEx
0x180008045  nop     dword ptr [rax+rax+00h]
0x18000804a  and     [rsi+28h], rbx
0x18000804e  lea     rcx, [rsp+290h+var_258]; this
0x180008053  and     [rsi+30h], rbx
0x180008057  and     [rsi+38h], rbx
0x18000805b  and     [rsi+40h], rbx
0x18000805f  mov     [r15], rdi
0x180008062  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180008067  test    r14, r14
0x18000806a  jz      short loc_180008083
0x18000806c  mov     rcx, r14; hMutex
0x18000806f  call    cs:__imp_ReleaseMutex
0x180008076  nop     dword ptr [rax+rax+00h]
0x18000807b  test    eax, eax
0x18000807d  jz      loc_18000813D
0x180008083  test    rbx, rbx
0x180008086  jz      short loc_18000809B
0x180008088  mov     rcx, rbx; hObject
0x18000808b  call    cs:__imp_CloseHandle
0x180008092  nop     dword ptr [rax+rax+00h]
0x180008097  test    eax, eax
0x180008099  jz      short loc_1800080C4
0x18000809b  xor     eax, eax
0x18000809d  mov     rcx, [rbp+190h+var_30]
0x1800080a4  xor     rcx, rsp; StackCookie
0x1800080a7  call    __security_check_cookie
0x1800080ac  mov     rbx, [rsp+290h+arg_10]
0x1800080b4  add     rsp, 270h
0x1800080bb  pop     r15
0x1800080bd  pop     r14
0x1800080bf  pop     rdi
0x1800080c0  pop     rsi
0x1800080c1  pop     rbp
0x1800080c2  retn
0x1800080c4  mov     rcx, [rbp+198h]; this
0x1800080cb  mov     edx, 9CDh; void *
0x1800080d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800080d6  mov     rcx, [rbp+198h]; this
0x1800080dd  mov     edx, 9CDh; void *
0x1800080e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800080e8  mov     rcx, [rbp+198h]; this
0x1800080ef  mov     edx, 9CDh; void *
0x1800080f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800080fa  mov     rcx, [rbp+198h]; this
0x180008101  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008107  mov     rcx, [rbp+198h]; this
0x18000810e  mov     edx, 9D7h; void *
0x180008113  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008119  mov     rcx, [rbp+198h]; this
0x180008120  mov     edx, 9D7h; void *
0x180008125  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000812b  mov     rcx, [rbp+198h]; this
0x180008132  mov     edx, 9CDh; void *
0x180008137  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000813d  mov     rcx, [rbp+198h]; this
0x180008144  mov     edx, 9D7h; void *
0x180008149  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
