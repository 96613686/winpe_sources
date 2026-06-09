# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004400`
- end: `0x1800045fa`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `506`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800043b0`

## callees

- `0x180004400`
- `0x180004650`
- `0x180004690`
- `0x1800046e0`
- `0x180004fe0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000455a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800044ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000455a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004597`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000443f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000443f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800045b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000448a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004550`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000448a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800044e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004550`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000447c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004542`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000447c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004542`

## string_xrefs

- `0x1800045c6`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  PTP_TIMER *v3; // rsi
  struct _TP_TIMER *v4; // rbp
  PTP_TIMER *v5; // r14
  struct _TP_TIMER *v6; // rbp
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rbp
  HANDLE v11; // rax
  __int64 v12; // rbx
  FARPROC ProcAddress; // rax
  void *v14; // rbp
  HANDLE v15; // rax
  void *v16; // rcx
  HMODULE NtDllModuleHandle; // rax
  DWORD LastError; // [rsp+6Ch] [rbp+14h]
  DWORD v19; // [rsp+6Ch] [rbp+14h]

  *(_BYTE *)this = 0;
  v3 = (PTP_TIMER *)((char *)this + 48);
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v4 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v4);
    SetLastError(LastError);
  }
  *v3 = 0;
  v5 = (PTP_TIMER *)((char *)this + 56);
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    v19 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v6);
    SetLastError(v19);
  }
  *v5 = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v12 = *((_QWORD *)this + 18);
  if ( v12 )
  {
    ProcAddress = (FARPROC)g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
          ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)ProcAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v12);
    }
  }
  v14 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v14 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *v5 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(*v5);
  if ( *v3 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(*v3);
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x180004400  mov     [rsp+arg_0], rcx
0x180004405  push    rbx
0x180004406  push    rbp
0x180004407  push    rsi
0x180004408  push    rdi
0x180004409  push    r14
0x18000440b  push    r15
0x18000440d  sub     rsp, 28h
0x180004411  mov     rdi, rcx
0x180004414  mov     byte ptr [rcx], 0
0x180004417  lea     rsi, [rcx+30h]
0x18000441b  mov     rbp, [rsi]
0x18000441e  test    rbp, rbp
0x180004421  jz      short loc_180004445
0x180004423  call    cs:__imp_GetLastError
0x180004429  mov     ebx, eax
0x18000442b  mov     byte ptr [rsp+58h+arg_8], 0
0x180004430  mov     dword ptr [rsp+58h+arg_8+4], eax
0x180004434  mov     rcx, rbp; pti
0x180004437  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000443c  nop
0x18000443d  mov     ecx, ebx; dwErrCode
0x18000443f  call    cs:__imp_SetLastError
0x180004445  xor     r15d, r15d
0x180004448  mov     [rsi], r15
0x18000444b  lea     r14, [rdi+38h]
0x18000444f  mov     rbp, [r14]
0x180004452  test    rbp, rbp
0x180004455  jnz     loc_180004597
0x18000445b  mov     [r14], r15
0x18000445e  lea     rax, [rdi+0E8h]
0x180004465  mov     [rsp+58h+arg_8], rax
0x18000446a  mov     [rsp+58h+arg_10], rax
0x18000446f  mov     rbx, [rax+18h]
0x180004473  mov     [rax+18h], r15
0x180004477  test    rbx, rbx
0x18000447a  jz      short loc_180004491
0x18000447c  call    cs:__imp_GetProcessHeap
0x180004482  mov     rcx, rax; hHeap
0x180004485  mov     r8, rbx; lpMem
0x180004488  xor     edx, edx; dwFlags
0x18000448a  call    cs:__imp_HeapFree
0x180004490  nop
0x180004491  lea     rax, [rdi+0E0h]
0x180004498  mov     [rsp+58h+arg_8], rax
0x18000449d  mov     rcx, [rax]; this
0x1800044a0  test    rcx, rcx
0x1800044a3  jz      short loc_1800044AB
0x1800044a5  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800044aa  nop
0x1800044ab  lea     rbx, [rdi+98h]
0x1800044b2  mov     [rsp+58h+arg_8], rbx
0x1800044b7  lea     rax, [rbx+28h]
0x1800044bb  mov     [rsp+58h+arg_10], rax
0x1800044c0  mov     [rsp+58h+arg_18], rax
0x1800044c5  mov     rbp, [rax+18h]
0x1800044c9  mov     [rax+18h], r15
0x1800044cd  test    rbp, rbp
0x1800044d0  jz      short loc_1800044E7
0x1800044d2  call    cs:__imp_GetProcessHeap
0x1800044d8  mov     rcx, rax; hHeap
0x1800044db  mov     r8, rbp; lpMem
0x1800044de  xor     edx, edx; dwFlags
0x1800044e0  call    cs:__imp_HeapFree
0x1800044e6  nop
0x1800044e7  mov     rcx, rbx; lpCriticalSection
0x1800044ea  call    cs:__imp_DeleteCriticalSection
0x1800044f0  nop
0x1800044f1  lea     rax, [rdi+90h]
0x1800044f8  mov     [rsp+58h+arg_8], rax
0x1800044fd  mov     rbx, [rax]
0x180004500  test    rbx, rbx
0x180004503  jz      short loc_18000451E
0x180004505  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x18000450c  test    rax, rax
0x18000450f  jz      loc_1800045BE
0x180004515  mov     rcx, rbx
0x180004518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451d  nop
0x18000451e  lea     rbx, [rdi+48h]
0x180004522  mov     [rsp+58h+arg_8], rbx
0x180004527  lea     rax, [rbx+28h]
0x18000452b  mov     [rsp+58h+arg_10], rax
0x180004530  mov     [rsp+58h+arg_18], rax
0x180004535  mov     rbp, [rax+18h]
0x180004539  mov     [rax+18h], r15
0x18000453d  test    rbp, rbp
0x180004540  jz      short loc_180004557
0x180004542  call    cs:__imp_GetProcessHeap
0x180004548  mov     rcx, rax; hHeap
0x18000454b  mov     r8, rbp; lpMem
0x18000454e  xor     edx, edx; dwFlags
0x180004550  call    cs:__imp_HeapFree
0x180004556  nop
0x180004557  mov     rcx, rbx; lpCriticalSection
0x18000455a  call    cs:__imp_DeleteCriticalSection
0x180004560  nop
0x180004561  mov     [rsp+58h+arg_8], r14
0x180004566  mov     rcx, [r14]; pti
0x180004569  test    rcx, rcx
0x18000456c  jnz     short loc_1800045E8
0x18000456e  mov     [rsp+58h+arg_8], rsi
0x180004573  mov     rcx, [rsi]; pti
0x180004576  test    rcx, rcx
0x180004579  jnz     short loc_1800045F2
0x18000457b  mov     rcx, [rdi+10h]; lpMem
0x18000457f  test    rcx, rcx
0x180004582  jz      short loc_18000458A
0x180004584  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004589  nop
0x18000458a  add     rsp, 28h
0x18000458e  pop     r15
0x180004590  pop     r14
0x180004592  pop     rdi
0x180004593  pop     rsi
0x180004594  pop     rbp
0x180004595  pop     rbx
0x180004596  retn
0x180004597  call    cs:__imp_GetLastError
0x18000459d  mov     ebx, eax
0x18000459f  mov     byte ptr [rsp+58h+arg_8], r15b
0x1800045a4  mov     dword ptr [rsp+58h+arg_8+4], eax
0x1800045a8  mov     rcx, rbp; pti
0x1800045ab  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800045b0  nop
0x1800045b1  mov     ecx, ebx; dwErrCode
0x1800045b3  call    cs:__imp_SetLastError
0x1800045b9  jmp     loc_18000445B
0x1800045be  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x1800045c3  mov     rcx, rax; hModule
0x1800045c6  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800045cd  call    cs:__imp_GetProcAddress
0x1800045d3  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800045da  test    rax, rax
0x1800045dd  jz      loc_18000451E
0x1800045e3  jmp     loc_180004515
0x1800045e8  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800045ed  jmp     loc_18000456E
0x1800045f2  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800045f7  jmp     short loc_18000457B
```
