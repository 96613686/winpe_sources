# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000e170`
- end: `0x18000e2aa`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000a7a4`
- `0x18000be0c`
- `0x18000bff0`
- `0x18000c384`
- `0x18000c57c`
- `0x18000e170`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000e268`
- `KERNEL32!GetProcAddress` at `0x18000e268`
- `KERNEL32!GetModuleHandleW` at `0x18000e24b`
- `KERNEL32!GetModuleHandleW` at `0x18000e24b`

## string_xrefs

- `0x18000e244`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18004B3D0[25], qword_18004B3D0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18004B3D0);
  }
}

```

## disassembly

```asm
0x18000e170  sub     rsp, 38h
0x18000e174  mov     eax, edx
0x18000e176  btr     edx, 1Fh
0x18000e17a  test    ecx, ecx
0x18000e17c  jnz     short loc_18000E1E3
0x18000e17e  test    r8d, r8d
0x18000e181  jnz     short loc_18000E1E3
0x18000e183  test    edx, edx
0x18000e185  jnz     short loc_18000E1E3
0x18000e187  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18000e18d  jnz     loc_18000E2A4
0x18000e193  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e19a  test    rax, rax
0x18000e19d  jz      short loc_18000E1AC
0x18000e19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a4  test    al, al
0x18000e1a6  jnz     loc_18000E2A4
0x18000e1ac  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000e1b3  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000e1b8  test    al, al
0x18000e1ba  jz      loc_18000E2A4
0x18000e1c0  mov     rdx, cs:qword_18004B3D0; SRWLock
0x18000e1c7  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000e1ce  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000e1d3  mov     rcx, cs:qword_18004B3D0; SRWLock
0x18000e1da  add     rsp, 38h
0x18000e1de  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000e1e3  bt      edx, 1Eh
0x18000e1e7  jnb     short loc_18000E202
0x18000e1e9  mov     r9d, r8d; unsigned int
0x18000e1ec  movzx   r8d, dx; unsigned __int16
0x18000e1f0  mov     edx, ecx; unsigned int
0x18000e1f2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000e1f9  add     rsp, 38h
0x18000e1fd  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000e202  test    r8d, r8d
0x18000e205  jnz     loc_18000E290
0x18000e20b  cmp     edx, 0FEh
0x18000e211  jz      short loc_18000E290
0x18000e213  and     [rsp+38h+var_18], 0
0x18000e219  mov     dword ptr [rsp+38h+var_18], ecx
0x18000e21d  mov     word ptr [rsp+38h+var_18+4], dx
0x18000e222  test    eax, eax
0x18000e224  jns     short loc_18000E22C
0x18000e226  or      word ptr [rsp+38h+var_18+6], 1
0x18000e22c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e233  test    rax, rax
0x18000e236  jnz     short loc_18000E280
0x18000e238  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e23f  test    rax, rax
0x18000e242  jnz     short loc_18000E25E
0x18000e244  lea     rcx, ModuleName; "ntdll.dll"
0x18000e24b  call    cs:__imp_GetModuleHandleW
0x18000e252  nop     dword ptr [rax+rax+00h]
0x18000e257  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e25e  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e265  mov     rcx, rax; hModule
0x18000e268  call    cs:__imp_GetProcAddress
0x18000e26f  nop     dword ptr [rax+rax+00h]
0x18000e274  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e27b  test    rax, rax
0x18000e27e  jz      short loc_18000E2A4
0x18000e280  lea     rcx, [rsp+38h+var_18]
0x18000e285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e28a  add     rsp, 38h
0x18000e28e  retn
0x18000e290  mov     r9d, r8d
0x18000e293  mov     r8d, edx
0x18000e296  mov     edx, ecx
0x18000e298  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000e29f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000e2a4  add     rsp, 38h
0x18000e2a8  retn
```
