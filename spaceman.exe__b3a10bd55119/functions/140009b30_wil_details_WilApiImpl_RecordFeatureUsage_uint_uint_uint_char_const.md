# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x140009b30`
- end: `0x140009c5b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400060a4`
- `0x140007684`
- `0x1400077ec`
- `0x140007bb4`
- `0x140007d6c`
- `0x140009b30`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009c27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009c27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009c10`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009c10`

## string_xrefs

- `0x140009c09`: `ntdll.dll`

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
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1400140E8[25], qword_1400140E8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1400140E8);
  }
}

```

## disassembly

```asm
0x140009b30  sub     rsp, 38h
0x140009b34  mov     eax, r8d
0x140009b37  mov     r8d, edx
0x140009b3a  btr     r8d, 1Fh; unsigned __int16
0x140009b3f  test    ecx, ecx
0x140009b41  jnz     short loc_140009BAA
0x140009b43  test    eax, eax
0x140009b45  jnz     short loc_140009BAA
0x140009b47  test    r8d, r8d
0x140009b4a  jnz     short loc_140009BAA
0x140009b4c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x140009b53  jnz     loc_140009C56
0x140009b59  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140009b60  test    rax, rax
0x140009b63  jz      short loc_140009B72
0x140009b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b6a  test    al, al
0x140009b6c  jnz     loc_140009C56
0x140009b72  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140009b79  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140009b7e  test    al, al
0x140009b80  jz      loc_140009C56
0x140009b86  mov     rdx, cs:qword_1400140E8; SRWLock
0x140009b8d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140009b94  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x140009b99  mov     rcx, cs:qword_1400140E8; SRWLock
0x140009ba0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140009ba5  jmp     loc_140009C56
0x140009baa  bt      r8d, 1Eh
0x140009baf  jnb     short loc_140009BC7
0x140009bb1  mov     edx, ecx; unsigned int
0x140009bb3  mov     r9d, eax; unsigned int
0x140009bb6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140009bbd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140009bc2  jmp     loc_140009C56
0x140009bc7  test    eax, eax
0x140009bc9  jnz     short loc_140009C45
0x140009bcb  cmp     r8d, 0FEh
0x140009bd2  jz      short loc_140009C45
0x140009bd4  mov     [rsp+38h+var_18], 0
0x140009bdd  mov     dword ptr [rsp+38h+var_18], ecx
0x140009be1  mov     word ptr [rsp+38h+var_18+4], r8w
0x140009be7  test    edx, edx
0x140009be9  jns     short loc_140009BF1
0x140009beb  or      word ptr [rsp+38h+var_18+6], 1
0x140009bf1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140009bf8  test    rax, rax
0x140009bfb  jnz     short loc_140009C39
0x140009bfd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009c04  test    rax, rax
0x140009c07  jnz     short loc_140009C1D
0x140009c09  lea     rcx, ModuleName; "ntdll.dll"
0x140009c10  call    cs:__imp_GetModuleHandleW
0x140009c16  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009c1d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140009c24  mov     rcx, rax; hModule
0x140009c27  call    cs:__imp_GetProcAddress
0x140009c2d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140009c34  test    rax, rax
0x140009c37  jz      short loc_140009C56
0x140009c39  lea     rcx, [rsp+38h+var_18]
0x140009c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c43  jmp     short loc_140009C56
0x140009c45  mov     edx, ecx
0x140009c47  mov     r9, rax
0x140009c4a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x140009c51  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x140009c56  add     rsp, 38h
0x140009c5a  retn
```
