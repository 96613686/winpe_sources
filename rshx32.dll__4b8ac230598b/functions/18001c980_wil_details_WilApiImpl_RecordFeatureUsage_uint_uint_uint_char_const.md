# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18001c980`
- end: `0x18001caab`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18001a518`
- `0x18001b0ec`
- `0x18001b1b0`
- `0x18001b53c`
- `0x18001b6f0`
- `0x18001c980`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ca77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ca60`

## string_xrefs

- `0x18001ca59`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180028820[25], qword_180028820);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180028820);
  }
}

```

## disassembly

```asm
0x18001c980  sub     rsp, 38h
0x18001c984  mov     eax, r8d
0x18001c987  mov     r8d, edx
0x18001c98a  btr     r8d, 1Fh; unsigned __int16
0x18001c98f  test    ecx, ecx
0x18001c991  jnz     short loc_18001C9FA
0x18001c993  test    eax, eax
0x18001c995  jnz     short loc_18001C9FA
0x18001c997  test    r8d, r8d
0x18001c99a  jnz     short loc_18001C9FA
0x18001c99c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18001c9a3  jnz     loc_18001CAA6
0x18001c9a9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c9b0  test    rax, rax
0x18001c9b3  jz      short loc_18001C9C2
0x18001c9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9ba  test    al, al
0x18001c9bc  jnz     loc_18001CAA6
0x18001c9c2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18001c9c9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001c9ce  test    al, al
0x18001c9d0  jz      loc_18001CAA6
0x18001c9d6  mov     rdx, cs:qword_180028820; SRWLock
0x18001c9dd  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001c9e4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001c9e9  mov     rcx, cs:qword_180028820; SRWLock
0x18001c9f0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001c9f5  jmp     loc_18001CAA6
0x18001c9fa  bt      r8d, 1Eh
0x18001c9ff  jnb     short loc_18001CA17
0x18001ca01  mov     edx, ecx; unsigned int
0x18001ca03  mov     r9d, eax; unsigned int
0x18001ca06  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001ca0d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18001ca12  jmp     loc_18001CAA6
0x18001ca17  test    eax, eax
0x18001ca19  jnz     short loc_18001CA95
0x18001ca1b  cmp     r8d, 0FEh
0x18001ca22  jz      short loc_18001CA95
0x18001ca24  mov     [rsp+38h+var_18], 0
0x18001ca2d  mov     dword ptr [rsp+38h+var_18], ecx
0x18001ca31  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001ca37  test    edx, edx
0x18001ca39  jns     short loc_18001CA41
0x18001ca3b  or      word ptr [rsp+38h+var_18+6], 1
0x18001ca41  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001ca48  test    rax, rax
0x18001ca4b  jnz     short loc_18001CA89
0x18001ca4d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ca54  test    rax, rax
0x18001ca57  jnz     short loc_18001CA6D
0x18001ca59  lea     rcx, ModuleName; "ntdll.dll"
0x18001ca60  call    cs:__imp_GetModuleHandleW
0x18001ca66  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001ca6d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001ca74  mov     rcx, rax; hModule
0x18001ca77  call    cs:__imp_GetProcAddress
0x18001ca7d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001ca84  test    rax, rax
0x18001ca87  jz      short loc_18001CAA6
0x18001ca89  lea     rcx, [rsp+38h+var_18]
0x18001ca8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca93  jmp     short loc_18001CAA6
0x18001ca95  mov     edx, ecx
0x18001ca97  mov     r9, rax
0x18001ca9a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001caa1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001caa6  add     rsp, 38h
0x18001caaa  retn
```
