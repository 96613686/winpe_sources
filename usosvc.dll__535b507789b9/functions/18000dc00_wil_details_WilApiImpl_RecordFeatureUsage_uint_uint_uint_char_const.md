# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000dc00`
- end: `0x18000dd20`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000b754`
- `0x18000c35c`
- `0x18000c420`
- `0x18000c7d0`
- `0x18000c954`
- `0x18000dc00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dcec`

## string_xrefs

- `0x18000dcce`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800150A0[25], qword_1800150A0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800150A0);
  }
}

```

## disassembly

```asm
0x18000dc00  sub     rsp, 38h
0x18000dc04  mov     eax, r8d
0x18000dc07  mov     r8d, edx
0x18000dc0a  btr     r8d, 1Fh; unsigned __int16
0x18000dc0f  test    ecx, ecx
0x18000dc11  jnz     short loc_18000DC6F
0x18000dc13  test    eax, eax
0x18000dc15  jnz     short loc_18000DC6F
0x18000dc17  test    r8d, r8d
0x18000dc1a  jnz     short loc_18000DC6F
0x18000dc1c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000dc23  jnz     short loc_18000DC6A
0x18000dc25  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000dc2c  test    rax, rax
0x18000dc2f  jz      short loc_18000DC3A
0x18000dc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc36  test    al, al
0x18000dc38  jnz     short loc_18000DC6A
0x18000dc3a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000dc41  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000dc46  test    al, al
0x18000dc48  jz      short loc_18000DC6A
0x18000dc4a  mov     rdx, cs:qword_1800150A0; SRWLock
0x18000dc51  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000dc58  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000dc5d  mov     rcx, cs:qword_1800150A0; SRWLock
0x18000dc64  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000dc69  nop
0x18000dc6a  jmp     loc_18000DD1B
0x18000dc6f  bt      r8d, 1Eh
0x18000dc74  jnb     short loc_18000DC8C
0x18000dc76  mov     r9d, eax; unsigned int
0x18000dc79  mov     edx, ecx; unsigned int
0x18000dc7b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000dc82  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000dc87  jmp     loc_18000DD1B
0x18000dc8c  test    eax, eax
0x18000dc8e  jnz     short loc_18000DD0A
0x18000dc90  cmp     r8d, 0FEh
0x18000dc97  jz      short loc_18000DD0A
0x18000dc99  mov     [rsp+38h+var_18], 0
0x18000dca2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000dca6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000dcac  test    edx, edx
0x18000dcae  jns     short loc_18000DCB6
0x18000dcb0  or      word ptr [rsp+38h+var_18+6], 1
0x18000dcb6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000dcbd  test    rax, rax
0x18000dcc0  jnz     short loc_18000DCFE
0x18000dcc2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dcc9  test    rax, rax
0x18000dccc  jnz     short loc_18000DCE2
0x18000dcce  lea     rcx, ModuleName; "ntdll.dll"
0x18000dcd5  call    cs:__imp_GetModuleHandleW
0x18000dcdb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000dce2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000dce9  mov     rcx, rax; hModule
0x18000dcec  call    cs:__imp_GetProcAddress
0x18000dcf2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000dcf9  test    rax, rax
0x18000dcfc  jz      short loc_18000DD1B
0x18000dcfe  lea     rcx, [rsp+38h+var_18]
0x18000dd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd08  jmp     short loc_18000DD1B
0x18000dd0a  mov     r9, rax
0x18000dd0d  mov     edx, ecx
0x18000dd0f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000dd16  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000dd1b  add     rsp, 38h
0x18000dd1f  retn
```
