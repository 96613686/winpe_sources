# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000f970`
- end: `0x18000fab7`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `327`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x18000c344`
- `0x18000d9a0`
- `0x18000dbb4`
- `0x18000def4`
- `0x18000e0f4`
- `0x18000f970`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa76`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000fa76`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fa5f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000fa5f`

## string_xrefs

- `0x18000fa58`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        a2,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002B0E8[25], qword_18002B0E8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002B0E8);
  }
}

```

## disassembly

```asm
0x18000f970  sub     rsp, 38h
0x18000f974  mov     rax, cs:__security_cookie
0x18000f97b  xor     rax, rsp
0x18000f97e  mov     [rsp+38h+var_10], rax
0x18000f983  mov     eax, r8d
0x18000f986  mov     r8d, edx
0x18000f989  btr     r8d, 1Fh; unsigned __int16
0x18000f98e  test    ecx, ecx
0x18000f990  jnz     short loc_18000F9F9
0x18000f992  test    eax, eax
0x18000f994  jnz     short loc_18000F9F9
0x18000f996  test    r8d, r8d
0x18000f999  jnz     short loc_18000F9F9
0x18000f99b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000f9a2  jnz     loc_18000FAA5
0x18000f9a8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000f9af  test    rax, rax
0x18000f9b2  jz      short loc_18000F9C1
0x18000f9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9b9  test    al, al
0x18000f9bb  jnz     loc_18000FAA5
0x18000f9c1  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000f9c8  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000f9cd  test    al, al
0x18000f9cf  jz      loc_18000FAA5
0x18000f9d5  mov     rdx, cs:qword_18002B0E8; SRWLock
0x18000f9dc  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000f9e3  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000f9e8  mov     rcx, cs:qword_18002B0E8; SRWLock
0x18000f9ef  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000f9f4  jmp     loc_18000FAA5
0x18000f9f9  bt      r8d, 1Eh
0x18000f9fe  jnb     short loc_18000FA16
0x18000fa00  mov     edx, ecx; unsigned int
0x18000fa02  mov     r9d, eax; unsigned int
0x18000fa05  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000fa0c  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000fa11  jmp     loc_18000FAA5
0x18000fa16  test    eax, eax
0x18000fa18  jnz     short loc_18000FA94
0x18000fa1a  cmp     r8d, 0FEh
0x18000fa21  jz      short loc_18000FA94
0x18000fa23  mov     [rsp+38h+var_18], 0
0x18000fa2c  mov     dword ptr [rsp+38h+var_18], ecx
0x18000fa30  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000fa36  test    edx, edx
0x18000fa38  jns     short loc_18000FA40
0x18000fa3a  or      word ptr [rsp+38h+var_18+6], 1
0x18000fa40  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000fa47  test    rax, rax
0x18000fa4a  jnz     short loc_18000FA88
0x18000fa4c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fa53  test    rax, rax
0x18000fa56  jnz     short loc_18000FA6C
0x18000fa58  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000fa5f  call    cs:__imp_GetModuleHandleW
0x18000fa65  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fa6c  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000fa73  mov     rcx, rax; hModule
0x18000fa76  call    cs:__imp_GetProcAddress
0x18000fa7c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000fa83  test    rax, rax
0x18000fa86  jz      short loc_18000FAA5
0x18000fa88  lea     rcx, [rsp+38h+var_18]
0x18000fa8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa92  jmp     short loc_18000FAA5
0x18000fa94  mov     edx, ecx
0x18000fa96  mov     r9, rax
0x18000fa99  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000faa0  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000faa5  mov     rcx, [rsp+38h+var_10]
0x18000faaa  xor     rcx, rsp; StackCookie
0x18000faad  call    __security_check_cookie
0x18000fab2  add     rsp, 38h
0x18000fab6  retn
```
