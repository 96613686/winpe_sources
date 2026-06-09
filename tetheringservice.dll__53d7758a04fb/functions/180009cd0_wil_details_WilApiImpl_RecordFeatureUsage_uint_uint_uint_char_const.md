# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180009cd0`
- end: `0x180009df0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005c44`
- `0x1800070f4`
- `0x1800072f8`
- `0x1800078e4`
- `0x180007ae0`
- `0x180009cd0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009da5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009da5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009dbc`

## string_xrefs

- `0x180009d9e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180041668[25], qword_180041668);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180041668);
  }
}

```

## disassembly

```asm
0x180009cd0  sub     rsp, 38h
0x180009cd4  mov     eax, r8d
0x180009cd7  mov     r8d, edx
0x180009cda  btr     r8d, 1Fh; unsigned __int16
0x180009cdf  test    ecx, ecx
0x180009ce1  jnz     short loc_180009D3F
0x180009ce3  test    eax, eax
0x180009ce5  jnz     short loc_180009D3F
0x180009ce7  test    r8d, r8d
0x180009cea  jnz     short loc_180009D3F
0x180009cec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x180009cf3  jnz     short loc_180009D3A
0x180009cf5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180009cfc  test    rax, rax
0x180009cff  jz      short loc_180009D0A
0x180009d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d06  test    al, al
0x180009d08  jnz     short loc_180009D3A
0x180009d0a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180009d11  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180009d16  test    al, al
0x180009d18  jz      short loc_180009D3A
0x180009d1a  mov     rdx, cs:qword_180041668; SRWLock
0x180009d21  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009d28  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180009d2d  mov     rcx, cs:qword_180041668; SRWLock
0x180009d34  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180009d39  nop
0x180009d3a  jmp     loc_180009DEB
0x180009d3f  bt      r8d, 1Eh
0x180009d44  jnb     short loc_180009D5C
0x180009d46  mov     r9d, eax; unsigned int
0x180009d49  mov     edx, ecx; unsigned int
0x180009d4b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180009d52  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180009d57  jmp     loc_180009DEB
0x180009d5c  test    eax, eax
0x180009d5e  jnz     short loc_180009DDA
0x180009d60  cmp     r8d, 0FEh
0x180009d67  jz      short loc_180009DDA
0x180009d69  mov     [rsp+38h+var_18], 0
0x180009d72  mov     dword ptr [rsp+38h+var_18], ecx
0x180009d76  mov     word ptr [rsp+38h+var_18+4], r8w
0x180009d7c  test    edx, edx
0x180009d7e  jns     short loc_180009D86
0x180009d80  or      word ptr [rsp+38h+var_18+6], 1
0x180009d86  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009d8d  test    rax, rax
0x180009d90  jnz     short loc_180009DCE
0x180009d92  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009d99  test    rax, rax
0x180009d9c  jnz     short loc_180009DB2
0x180009d9e  lea     rcx, ModuleName; "ntdll.dll"
0x180009da5  call    cs:__imp_GetModuleHandleW
0x180009dab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009db2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180009db9  mov     rcx, rax; hModule
0x180009dbc  call    cs:__imp_GetProcAddress
0x180009dc2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180009dc9  test    rax, rax
0x180009dcc  jz      short loc_180009DEB
0x180009dce  lea     rcx, [rsp+38h+var_18]
0x180009dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd8  jmp     short loc_180009DEB
0x180009dda  mov     r9, rax
0x180009ddd  mov     edx, ecx
0x180009ddf  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x180009de6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180009deb  add     rsp, 38h
0x180009def  retn
```
