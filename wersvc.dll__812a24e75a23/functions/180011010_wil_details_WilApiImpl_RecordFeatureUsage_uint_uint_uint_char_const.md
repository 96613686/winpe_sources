# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011010`
- end: `0x180011130`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009aa8`
- `0x18000ad6c`
- `0x18000af70`
- `0x18000b6a0`
- `0x18000b890`
- `0x180011010`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800110e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800110fc`

## string_xrefs

- `0x1800110de`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        goto LABEL_20;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_20:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180047178[25], qword_180047178);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180047178);
  }
}

```

## disassembly

```asm
0x180011010  sub     rsp, 38h
0x180011014  mov     eax, r8d
0x180011017  mov     r8d, edx
0x18001101a  btr     r8d, 1Fh; unsigned __int16
0x18001101f  test    ecx, ecx
0x180011021  jnz     short loc_18001107F
0x180011023  test    eax, eax
0x180011025  jnz     short loc_18001107F
0x180011027  test    r8d, r8d
0x18001102a  jnz     short loc_18001107F
0x18001102c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180011033  jnz     short loc_18001107A
0x180011035  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001103c  test    rax, rax
0x18001103f  jz      short loc_18001104A
0x180011041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011046  test    al, al
0x180011048  jnz     short loc_18001107A
0x18001104a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180011051  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180011056  test    al, al
0x180011058  jz      short loc_18001107A
0x18001105a  mov     rdx, cs:qword_180047178; SRWLock
0x180011061  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180011068  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001106d  mov     rcx, cs:qword_180047178; SRWLock
0x180011074  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180011079  nop
0x18001107a  jmp     loc_18001112B
0x18001107f  bt      r8d, 1Eh
0x180011084  jnb     short loc_18001109C
0x180011086  mov     r9d, eax; unsigned int
0x180011089  mov     edx, ecx; unsigned int
0x18001108b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180011092  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180011097  jmp     loc_18001112B
0x18001109c  test    eax, eax
0x18001109e  jnz     short loc_18001111A
0x1800110a0  cmp     r8d, 0FEh
0x1800110a7  jz      short loc_18001111A
0x1800110a9  mov     [rsp+38h+var_18], 0
0x1800110b2  mov     dword ptr [rsp+38h+var_18], ecx
0x1800110b6  mov     word ptr [rsp+38h+var_18+4], r8w
0x1800110bc  test    edx, edx
0x1800110be  jns     short loc_1800110C6
0x1800110c0  or      word ptr [rsp+38h+var_18+6], 1
0x1800110c6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800110cd  test    rax, rax
0x1800110d0  jnz     short loc_18001110E
0x1800110d2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800110d9  test    rax, rax
0x1800110dc  jnz     short loc_1800110F2
0x1800110de  lea     rcx, Src; "ntdll.dll"
0x1800110e5  call    cs:__imp_GetModuleHandleW
0x1800110eb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800110f2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800110f9  mov     rcx, rax; hModule
0x1800110fc  call    cs:__imp_GetProcAddress
0x180011102  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180011109  test    rax, rax
0x18001110c  jz      short loc_18001112B
0x18001110e  lea     rcx, [rsp+38h+var_18]
0x180011113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011118  jmp     short loc_18001112B
0x18001111a  mov     r9, rax
0x18001111d  mov     edx, ecx
0x18001111f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180011126  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18001112b  add     rsp, 38h
0x18001112f  retn
```
