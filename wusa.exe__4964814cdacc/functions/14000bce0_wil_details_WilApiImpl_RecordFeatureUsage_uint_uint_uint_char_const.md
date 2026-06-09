# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000bce0`
- end: `0x14000be0b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400067f0`
- `0x140008a80`
- `0x140008be0`
- `0x14000954c`
- `0x140009700`
- `0x14000bce0`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000bdd7`
- `KERNEL32!GetProcAddress` at `0x14000bdd7`
- `KERNEL32!GetModuleHandleW` at `0x14000bdc0`
- `KERNEL32!GetModuleHandleW` at `0x14000bdc0`

## string_xrefs

- `0x14000bdb9`: `ntdll.dll`

## pseudocode

```c
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140020028[25], qword_140020028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140020028);
  }
}

```

## disassembly

```asm
0x14000bce0  sub     rsp, 38h
0x14000bce4  mov     eax, r8d
0x14000bce7  mov     r8d, edx
0x14000bcea  btr     r8d, 1Fh; unsigned __int16
0x14000bcef  test    ecx, ecx
0x14000bcf1  jnz     short loc_14000BD5A
0x14000bcf3  test    eax, eax
0x14000bcf5  jnz     short loc_14000BD5A
0x14000bcf7  test    r8d, r8d
0x14000bcfa  jnz     short loc_14000BD5A
0x14000bcfc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000bd03  jnz     loc_14000BE06
0x14000bd09  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000bd10  test    rax, rax
0x14000bd13  jz      short loc_14000BD22
0x14000bd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd1a  test    al, al
0x14000bd1c  jnz     loc_14000BE06
0x14000bd22  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000bd29  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000bd2e  test    al, al
0x14000bd30  jz      loc_14000BE06
0x14000bd36  mov     rdx, cs:qword_140020028; SRWLock
0x14000bd3d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000bd44  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000bd49  mov     rcx, cs:qword_140020028; SRWLock
0x14000bd50  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000bd55  jmp     loc_14000BE06
0x14000bd5a  bt      r8d, 1Eh
0x14000bd5f  jnb     short loc_14000BD77
0x14000bd61  mov     edx, ecx; unsigned int
0x14000bd63  mov     r9d, eax; unsigned int
0x14000bd66  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000bd6d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000bd72  jmp     loc_14000BE06
0x14000bd77  test    eax, eax
0x14000bd79  jnz     short loc_14000BDF5
0x14000bd7b  cmp     r8d, 0FEh
0x14000bd82  jz      short loc_14000BDF5
0x14000bd84  mov     [rsp+38h+var_18], 0
0x14000bd8d  mov     dword ptr [rsp+38h+var_18], ecx
0x14000bd91  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000bd97  test    edx, edx
0x14000bd99  jns     short loc_14000BDA1
0x14000bd9b  or      word ptr [rsp+38h+var_18+6], 1
0x14000bda1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000bda8  test    rax, rax
0x14000bdab  jnz     short loc_14000BDE9
0x14000bdad  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bdb4  test    rax, rax
0x14000bdb7  jnz     short loc_14000BDCD
0x14000bdb9  lea     rcx, ModuleName; "ntdll.dll"
0x14000bdc0  call    cs:__imp_GetModuleHandleW
0x14000bdc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bdcd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000bdd4  mov     rcx, rax; hModule
0x14000bdd7  call    cs:__imp_GetProcAddress
0x14000bddd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000bde4  test    rax, rax
0x14000bde7  jz      short loc_14000BE06
0x14000bde9  lea     rcx, [rsp+38h+var_18]
0x14000bdee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bdf3  jmp     short loc_14000BE06
0x14000bdf5  mov     edx, ecx
0x14000bdf7  mov     r9, rax
0x14000bdfa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000be01  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000be06  add     rsp, 38h
0x14000be0a  retn
```
