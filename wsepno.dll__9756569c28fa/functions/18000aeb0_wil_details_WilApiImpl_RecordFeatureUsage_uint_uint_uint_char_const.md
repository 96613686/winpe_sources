# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000aeb0`
- end: `0x18000afd0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000668c`
- `0x18000830c`
- `0x180008aac`
- `0x1800091f4`
- `0x1800093f0`
- `0x18000aeb0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000af9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000af85`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000af85`

## string_xrefs

- `0x18000af7e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v4; // r8
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v3 = a3;
  v4 = (unsigned int)a2;
  LODWORD(v4) = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || (_DWORD)v3 || (_DWORD)v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        v3);
    }
    else if ( (_DWORD)v3 || (_DWORD)v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        v3);
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180015078[25], qword_180015078);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180015078);
  }
}

```

## disassembly

```asm
0x18000aeb0  sub     rsp, 38h
0x18000aeb4  mov     eax, r8d
0x18000aeb7  mov     r8d, edx
0x18000aeba  btr     r8d, 1Fh; unsigned __int16
0x18000aebf  test    ecx, ecx
0x18000aec1  jnz     short loc_18000AF1F
0x18000aec3  test    eax, eax
0x18000aec5  jnz     short loc_18000AF1F
0x18000aec7  test    r8d, r8d
0x18000aeca  jnz     short loc_18000AF1F
0x18000aecc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000aed3  jnz     short loc_18000AF1A
0x18000aed5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000aedc  test    rax, rax
0x18000aedf  jz      short loc_18000AEEA
0x18000aee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee6  test    al, al
0x18000aee8  jnz     short loc_18000AF1A
0x18000aeea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000aef1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000aef6  test    al, al
0x18000aef8  jz      short loc_18000AF1A
0x18000aefa  mov     rdx, cs:qword_180015078; SRWLock
0x18000af01  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000af08  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000af0d  mov     rcx, cs:qword_180015078; SRWLock
0x18000af14  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000af19  nop
0x18000af1a  jmp     loc_18000AFCB
0x18000af1f  bt      r8d, 1Eh
0x18000af24  jnb     short loc_18000AF3C
0x18000af26  mov     r9d, eax; unsigned int
0x18000af29  mov     edx, ecx; unsigned int
0x18000af2b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000af32  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000af37  jmp     loc_18000AFCB
0x18000af3c  test    eax, eax
0x18000af3e  jnz     short loc_18000AFBA
0x18000af40  cmp     r8d, 0FEh
0x18000af47  jz      short loc_18000AFBA
0x18000af49  mov     [rsp+38h+var_18], 0
0x18000af52  mov     dword ptr [rsp+38h+var_18], ecx
0x18000af56  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000af5c  test    edx, edx
0x18000af5e  jns     short loc_18000AF66
0x18000af60  or      word ptr [rsp+38h+var_18+6], 1
0x18000af66  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000af6d  test    rax, rax
0x18000af70  jnz     short loc_18000AFAE
0x18000af72  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af79  test    rax, rax
0x18000af7c  jnz     short loc_18000AF92
0x18000af7e  lea     rcx, ModuleName; "ntdll.dll"
0x18000af85  call    cs:__imp_GetModuleHandleW
0x18000af8b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000af92  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000af99  mov     rcx, rax; hModule
0x18000af9c  call    cs:__imp_GetProcAddress
0x18000afa2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000afa9  test    rax, rax
0x18000afac  jz      short loc_18000AFCB
0x18000afae  lea     rcx, [rsp+38h+var_18]
0x18000afb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb8  jmp     short loc_18000AFCB
0x18000afba  mov     r9, rax
0x18000afbd  mov     edx, ecx
0x18000afbf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000afc6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000afcb  add     rsp, 38h
0x18000afcf  retn
```
