# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180011fe0`
- end: `0x180012100`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000b030`
- `0x18000e3e4`
- `0x18000e750`
- `0x18000eb14`
- `0x18000ef64`
- `0x180011fe0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800120b5`
- `KERNEL32!GetModuleHandleW` at `0x1800120b5`
- `KERNEL32!GetProcAddress` at `0x1800120cc`
- `KERNEL32!GetProcAddress` at `0x1800120cc`

## string_xrefs

- `0x1800120ae`: `ntdll.dll`

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
        goto LABEL_20;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800380C8[25], qword_1800380C8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800380C8);
  }
}

```

## disassembly

```asm
0x180011fe0  sub     rsp, 38h
0x180011fe4  mov     eax, r8d
0x180011fe7  mov     r8d, edx
0x180011fea  btr     r8d, 1Fh; unsigned __int16
0x180011fef  test    ecx, ecx
0x180011ff1  jnz     short loc_18001204F
0x180011ff3  test    eax, eax
0x180011ff5  jnz     short loc_18001204F
0x180011ff7  test    r8d, r8d
0x180011ffa  jnz     short loc_18001204F
0x180011ffc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180012003  jnz     short loc_18001204A
0x180012005  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001200c  test    rax, rax
0x18001200f  jz      short loc_18001201A
0x180012011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012016  test    al, al
0x180012018  jnz     short loc_18001204A
0x18001201a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180012021  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180012026  test    al, al
0x180012028  jz      short loc_18001204A
0x18001202a  mov     rdx, cs:qword_1800380C8; SRWLock
0x180012031  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180012038  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18001203d  mov     rcx, cs:qword_1800380C8; SRWLock
0x180012044  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012049  nop
0x18001204a  jmp     loc_1800120FB
0x18001204f  bt      r8d, 1Eh
0x180012054  jnb     short loc_18001206C
0x180012056  mov     r9d, eax; unsigned int
0x180012059  mov     edx, ecx; unsigned int
0x18001205b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180012062  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180012067  jmp     loc_1800120FB
0x18001206c  test    eax, eax
0x18001206e  jnz     short loc_1800120EA
0x180012070  cmp     r8d, 0FEh
0x180012077  jz      short loc_1800120EA
0x180012079  mov     [rsp+38h+var_18], 0
0x180012082  mov     dword ptr [rsp+38h+var_18], ecx
0x180012086  mov     word ptr [rsp+38h+var_18+4], r8w
0x18001208c  test    edx, edx
0x18001208e  jns     short loc_180012096
0x180012090  or      word ptr [rsp+38h+var_18+6], 1
0x180012096  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001209d  test    rax, rax
0x1800120a0  jnz     short loc_1800120DE
0x1800120a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800120a9  test    rax, rax
0x1800120ac  jnz     short loc_1800120C2
0x1800120ae  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800120b5  call    cs:__imp_GetModuleHandleW
0x1800120bb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800120c2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800120c9  mov     rcx, rax; hModule
0x1800120cc  call    cs:__imp_GetProcAddress
0x1800120d2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800120d9  test    rax, rax
0x1800120dc  jz      short loc_1800120FB
0x1800120de  lea     rcx, [rsp+38h+var_18]
0x1800120e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120e8  jmp     short loc_1800120FB
0x1800120ea  mov     r9, rax
0x1800120ed  mov     edx, ecx
0x1800120ef  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800120f6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800120fb  add     rsp, 38h
0x1800120ff  retn
```
