# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ccc0`
- end: `0x18000cde0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005d1c`
- `0x1800097ac`
- `0x1800099b0`
- `0x18000a164`
- `0x18000a360`
- `0x18000ccc0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cdac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cdac`

## string_xrefs

- `0x18000cd8e`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180021110[25], qword_180021110);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180021110);
  }
}

```

## disassembly

```asm
0x18000ccc0  sub     rsp, 38h
0x18000ccc4  mov     eax, r8d
0x18000ccc7  mov     r8d, edx
0x18000ccca  btr     r8d, 1Fh; unsigned __int16
0x18000cccf  test    ecx, ecx
0x18000ccd1  jnz     short loc_18000CD2F
0x18000ccd3  test    eax, eax
0x18000ccd5  jnz     short loc_18000CD2F
0x18000ccd7  test    r8d, r8d
0x18000ccda  jnz     short loc_18000CD2F
0x18000ccdc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000cce3  jnz     short loc_18000CD2A
0x18000cce5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ccec  test    rax, rax
0x18000ccef  jz      short loc_18000CCFA
0x18000ccf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf6  test    al, al
0x18000ccf8  jnz     short loc_18000CD2A
0x18000ccfa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000cd01  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000cd06  test    al, al
0x18000cd08  jz      short loc_18000CD2A
0x18000cd0a  mov     rdx, cs:qword_180021110; SRWLock
0x18000cd11  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000cd18  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000cd1d  mov     rcx, cs:qword_180021110; SRWLock
0x18000cd24  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000cd29  nop
0x18000cd2a  jmp     loc_18000CDDB
0x18000cd2f  bt      r8d, 1Eh
0x18000cd34  jnb     short loc_18000CD4C
0x18000cd36  mov     r9d, eax; unsigned int
0x18000cd39  mov     edx, ecx; unsigned int
0x18000cd3b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000cd42  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000cd47  jmp     loc_18000CDDB
0x18000cd4c  test    eax, eax
0x18000cd4e  jnz     short loc_18000CDCA
0x18000cd50  cmp     r8d, 0FEh
0x18000cd57  jz      short loc_18000CDCA
0x18000cd59  mov     [rsp+38h+var_18], 0
0x18000cd62  mov     dword ptr [rsp+38h+var_18], ecx
0x18000cd66  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000cd6c  test    edx, edx
0x18000cd6e  jns     short loc_18000CD76
0x18000cd70  or      word ptr [rsp+38h+var_18+6], 1
0x18000cd76  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000cd7d  test    rax, rax
0x18000cd80  jnz     short loc_18000CDBE
0x18000cd82  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cd89  test    rax, rax
0x18000cd8c  jnz     short loc_18000CDA2
0x18000cd8e  lea     rcx, ModuleName; "ntdll.dll"
0x18000cd95  call    cs:__imp_GetModuleHandleW
0x18000cd9b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cda2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000cda9  mov     rcx, rax; hModule
0x18000cdac  call    cs:__imp_GetProcAddress
0x18000cdb2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000cdb9  test    rax, rax
0x18000cdbc  jz      short loc_18000CDDB
0x18000cdbe  lea     rcx, [rsp+38h+var_18]
0x18000cdc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdc8  jmp     short loc_18000CDDB
0x18000cdca  mov     r9, rax
0x18000cdcd  mov     edx, ecx
0x18000cdcf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000cdd6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000cddb  add     rsp, 38h
0x18000cddf  retn
```
