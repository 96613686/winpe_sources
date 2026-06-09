# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180033d40`
- end: `0x180033e60`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18002e934`
- `0x180030dc4`
- `0x180030fc8`
- `0x1800316e4`
- `0x1800318e0`
- `0x180033d40`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033e2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033e2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033e15`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180033e15`

## string_xrefs

- `0x180033e0e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180074110[25], qword_180074110);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180074110);
  }
}

```

## disassembly

```asm
0x180033d40  sub     rsp, 38h
0x180033d44  mov     eax, r8d
0x180033d47  mov     r8d, edx
0x180033d4a  btr     r8d, 1Fh; unsigned __int16
0x180033d4f  test    ecx, ecx
0x180033d51  jnz     short loc_180033DAF
0x180033d53  test    eax, eax
0x180033d55  jnz     short loc_180033DAF
0x180033d57  test    r8d, r8d
0x180033d5a  jnz     short loc_180033DAF
0x180033d5c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180033d63  jnz     short loc_180033DAA
0x180033d65  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180033d6c  test    rax, rax
0x180033d6f  jz      short loc_180033D7A
0x180033d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d76  test    al, al
0x180033d78  jnz     short loc_180033DAA
0x180033d7a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180033d81  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180033d86  test    al, al
0x180033d88  jz      short loc_180033DAA
0x180033d8a  mov     rdx, cs:qword_180074110; SRWLock
0x180033d91  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180033d98  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180033d9d  mov     rcx, cs:qword_180074110; SRWLock
0x180033da4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180033da9  nop
0x180033daa  jmp     loc_180033E5B
0x180033daf  bt      r8d, 1Eh
0x180033db4  jnb     short loc_180033DCC
0x180033db6  mov     r9d, eax; unsigned int
0x180033db9  mov     edx, ecx; unsigned int
0x180033dbb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180033dc2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180033dc7  jmp     loc_180033E5B
0x180033dcc  test    eax, eax
0x180033dce  jnz     short loc_180033E4A
0x180033dd0  cmp     r8d, 0FEh
0x180033dd7  jz      short loc_180033E4A
0x180033dd9  mov     [rsp+38h+var_18], 0
0x180033de2  mov     dword ptr [rsp+38h+var_18], ecx
0x180033de6  mov     word ptr [rsp+38h+var_18+4], r8w
0x180033dec  test    edx, edx
0x180033dee  jns     short loc_180033DF6
0x180033df0  or      word ptr [rsp+38h+var_18+6], 1
0x180033df6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180033dfd  test    rax, rax
0x180033e00  jnz     short loc_180033E3E
0x180033e02  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180033e09  test    rax, rax
0x180033e0c  jnz     short loc_180033E22
0x180033e0e  lea     rcx, ModuleName; "ntdll.dll"
0x180033e15  call    cs:__imp_GetModuleHandleW
0x180033e1b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180033e22  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180033e29  mov     rcx, rax; hModule
0x180033e2c  call    cs:__imp_GetProcAddress
0x180033e32  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180033e39  test    rax, rax
0x180033e3c  jz      short loc_180033E5B
0x180033e3e  lea     rcx, [rsp+38h+var_18]
0x180033e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e48  jmp     short loc_180033E5B
0x180033e4a  mov     r9, rax
0x180033e4d  mov     edx, ecx
0x180033e4f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180033e56  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180033e5b  add     rsp, 38h
0x180033e5f  retn
```
