# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180007eb0`
- end: `0x180007fdb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004494`
- `0x180005c24`
- `0x180005e28`
- `0x1800063a4`
- `0x180006590`
- `0x180007eb0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f90`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007f90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fa7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007fa7`

## string_xrefs

- `0x180007f89`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18002D0F8[25], qword_18002D0F8);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18002D0F8);
  }
}

```

## disassembly

```asm
0x180007eb0  sub     rsp, 38h
0x180007eb4  mov     eax, r8d
0x180007eb7  mov     r8d, edx
0x180007eba  btr     r8d, 1Fh; unsigned __int16
0x180007ebf  test    ecx, ecx
0x180007ec1  jnz     short loc_180007F2A
0x180007ec3  test    eax, eax
0x180007ec5  jnz     short loc_180007F2A
0x180007ec7  test    r8d, r8d
0x180007eca  jnz     short loc_180007F2A
0x180007ecc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180007ed3  jnz     loc_180007FD6
0x180007ed9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180007ee0  test    rax, rax
0x180007ee3  jz      short loc_180007EF2
0x180007ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eea  test    al, al
0x180007eec  jnz     loc_180007FD6
0x180007ef2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180007ef9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180007efe  test    al, al
0x180007f00  jz      loc_180007FD6
0x180007f06  mov     rdx, cs:qword_18002D0F8; SRWLock
0x180007f0d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180007f14  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180007f19  mov     rcx, cs:qword_18002D0F8; SRWLock
0x180007f20  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180007f25  jmp     loc_180007FD6
0x180007f2a  bt      r8d, 1Eh
0x180007f2f  jnb     short loc_180007F47
0x180007f31  mov     edx, ecx; unsigned int
0x180007f33  mov     r9d, eax; unsigned int
0x180007f36  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180007f3d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180007f42  jmp     loc_180007FD6
0x180007f47  test    eax, eax
0x180007f49  jnz     short loc_180007FC5
0x180007f4b  cmp     r8d, 0FEh
0x180007f52  jz      short loc_180007FC5
0x180007f54  mov     [rsp+38h+var_18], 0
0x180007f5d  mov     dword ptr [rsp+38h+var_18], ecx
0x180007f61  mov     word ptr [rsp+38h+var_18+4], r8w
0x180007f67  test    edx, edx
0x180007f69  jns     short loc_180007F71
0x180007f6b  or      word ptr [rsp+38h+var_18+6], 1
0x180007f71  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180007f78  test    rax, rax
0x180007f7b  jnz     short loc_180007FB9
0x180007f7d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007f84  test    rax, rax
0x180007f87  jnz     short loc_180007F9D
0x180007f89  lea     rcx, ModuleName; "ntdll.dll"
0x180007f90  call    cs:__imp_GetModuleHandleW
0x180007f96  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007f9d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180007fa4  mov     rcx, rax; hModule
0x180007fa7  call    cs:__imp_GetProcAddress
0x180007fad  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007fb4  test    rax, rax
0x180007fb7  jz      short loc_180007FD6
0x180007fb9  lea     rcx, [rsp+38h+var_18]
0x180007fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc3  jmp     short loc_180007FD6
0x180007fc5  mov     edx, ecx
0x180007fc7  mov     r9, rax
0x180007fca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180007fd1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180007fd6  add     rsp, 38h
0x180007fda  retn
```
