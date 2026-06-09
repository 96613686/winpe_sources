# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004820`
- end: `0x18000498e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `366`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180028dd0`

## callees

- `0x1800029a0`
- `0x180004820`
- `0x18000cf50`
- `0x18000fa18`
- `0x180010824`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000490e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000490e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800048e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004953`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800048e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004953`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000489c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004949`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000489c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000488e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000493b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000488e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000493b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000484a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000484a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000485f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000485f`

## string_xrefs

- `0x180004907`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // edi
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // edi
  void *v7; // rdi
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  __int64 v12; // rdi
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  void *v15; // rsi
  HANDLE v16; // rax
  struct _TP_TIMER *v17; // rcx
  struct _TP_TIMER *v18; // rcx
  void *v19; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
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
  v15 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v15 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v17 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v17 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v17);
  v18 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v18 )
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v18);
  v19 = (void *)*((_QWORD *)this + 2);
  if ( v19 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v19);
}

```

## disassembly

```asm
0x180004820  push    rbx
0x180004822  push    rbp
0x180004823  push    rsi
0x180004824  push    rdi
0x180004825  sub     rsp, 28h
0x180004829  mov     rbx, rcx
0x18000482c  mov     byte ptr [rcx], 0
0x18000482f  mov     rsi, [rcx+30h]
0x180004833  test    rsi, rsi
0x180004836  jz      short loc_180004850
0x180004838  call    cs:__imp_GetLastError
0x18000483e  mov     edi, eax
0x180004840  mov     rcx, rsi; pti
0x180004843  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180004848  mov     ecx, edi; dwErrCode
0x18000484a  call    cs:__imp_SetLastError
0x180004850  xor     ebp, ebp
0x180004852  mov     [rbx+30h], rbp
0x180004856  mov     rsi, [rbx+38h]
0x18000485a  test    rsi, rsi
0x18000485d  jz      short loc_180004877
0x18000485f  call    cs:__imp_GetLastError
0x180004865  mov     edi, eax
0x180004867  mov     rcx, rsi; pti
0x18000486a  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x18000486f  mov     ecx, edi; dwErrCode
0x180004871  call    cs:__imp_SetLastError
0x180004877  mov     [rbx+38h], rbp
0x18000487b  mov     rdi, [rbx+100h]
0x180004882  mov     [rbx+100h], rbp
0x180004889  test    rdi, rdi
0x18000488c  jz      short loc_1800048A2
0x18000488e  call    cs:__imp_GetProcessHeap
0x180004894  mov     rcx, rax; hHeap
0x180004897  mov     r8, rdi; lpMem
0x18000489a  xor     edx, edx; dwFlags
0x18000489c  call    cs:__imp_HeapFree
0x1800048a2  mov     rcx, [rbx+0E0h]; this
0x1800048a9  test    rcx, rcx
0x1800048ac  jz      short loc_1800048B3
0x1800048ae  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800048b3  mov     rsi, [rbx+0D8h]
0x1800048ba  mov     [rbx+0D8h], rbp
0x1800048c1  test    rsi, rsi
0x1800048c4  jz      short loc_1800048DA
0x1800048c6  call    cs:__imp_GetProcessHeap
0x1800048cc  mov     rcx, rax; hHeap
0x1800048cf  mov     r8, rsi; lpMem
0x1800048d2  xor     edx, edx; dwFlags
0x1800048d4  call    cs:__imp_HeapFree
0x1800048da  lea     rcx, [rbx+98h]; lpCriticalSection
0x1800048e1  call    cs:__imp_DeleteCriticalSection
0x1800048e7  mov     rdi, [rbx+90h]
0x1800048ee  test    rdi, rdi
0x1800048f1  jz      short loc_180004928
0x1800048f3  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800048fa  test    rax, rax
0x1800048fd  jnz     short loc_180004920
0x1800048ff  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180004904  mov     rcx, rax; hModule
0x180004907  lea     rdx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x18000490e  call    cs:__imp_GetProcAddress
0x180004914  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x18000491b  test    rax, rax
0x18000491e  jz      short loc_180004928
0x180004920  mov     rcx, rdi
0x180004923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004928  mov     rsi, [rbx+88h]
0x18000492f  mov     [rbx+88h], rbp
0x180004936  test    rsi, rsi
0x180004939  jz      short loc_18000494F
0x18000493b  call    cs:__imp_GetProcessHeap
0x180004941  mov     rcx, rax; hHeap
0x180004944  mov     r8, rsi; lpMem
0x180004947  xor     edx, edx; dwFlags
0x180004949  call    cs:__imp_HeapFree
0x18000494f  lea     rcx, [rbx+48h]; lpCriticalSection
0x180004953  call    cs:__imp_DeleteCriticalSection
0x180004959  mov     rcx, [rbx+38h]; pti
0x18000495d  test    rcx, rcx
0x180004960  jz      short loc_180004967
0x180004962  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180004967  mov     rcx, [rbx+30h]; pti
0x18000496b  test    rcx, rcx
0x18000496e  jz      short loc_180004976
0x180004970  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x180004975  nop
0x180004976  mov     rcx, [rbx+10h]; lpMem
0x18000497a  test    rcx, rcx
0x18000497d  jz      short loc_180004985
0x18000497f  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004984  nop
0x180004985  add     rsp, 28h
0x180004989  pop     rdi
0x18000498a  pop     rsi
0x18000498b  pop     rbp
0x18000498c  pop     rbx
0x18000498d  retn
```
