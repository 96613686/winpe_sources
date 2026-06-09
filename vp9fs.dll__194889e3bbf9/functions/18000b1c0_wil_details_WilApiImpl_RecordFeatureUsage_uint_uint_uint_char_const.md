# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b1c0`
- end: `0x18000b2fc`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `316`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180004120`
- `0x180007334`
- `0x180008a20`
- `0x180008c38`
- `0x180008fc4`
- `0x1800091c4`
- `0x18000b1c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b2bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b2bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b2a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b2a4`

## string_xrefs

- `0x18000b29d`: `ntdll.dll`

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
        &wil::details::g_featureStateManager,
        (unsigned int)this,
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x18000b1c0  sub     rsp, 38h
0x18000b1c4  mov     rax, cs:__security_cookie
0x18000b1cb  xor     rax, rsp
0x18000b1ce  mov     [rsp+38h+var_10], rax
0x18000b1d3  mov     eax, r8d
0x18000b1d6  mov     r8d, edx
0x18000b1d9  btr     r8d, 1Fh; unsigned __int16
0x18000b1de  test    ecx, ecx
0x18000b1e0  jnz     short loc_18000B23E
0x18000b1e2  test    eax, eax
0x18000b1e4  jnz     short loc_18000B23E
0x18000b1e6  test    r8d, r8d
0x18000b1e9  jnz     short loc_18000B23E
0x18000b1eb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000b1f2  jnz     short loc_18000B239
0x18000b1f4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b1fb  test    rax, rax
0x18000b1fe  jz      short loc_18000B209
0x18000b200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b205  test    al, al
0x18000b207  jnz     short loc_18000B239
0x18000b209  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b210  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b215  test    al, al
0x18000b217  jz      short loc_18000B239
0x18000b219  mov     rdx, cs:SRWLock; SRWLock
0x18000b220  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b227  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b22c  mov     rcx, cs:SRWLock; SRWLock
0x18000b233  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b238  nop
0x18000b239  jmp     loc_18000B2EA
0x18000b23e  bt      r8d, 1Eh
0x18000b243  jnb     short loc_18000B25B
0x18000b245  mov     r9d, eax; unsigned int
0x18000b248  mov     edx, ecx; unsigned int
0x18000b24a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b251  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b256  jmp     loc_18000B2EA
0x18000b25b  test    eax, eax
0x18000b25d  jnz     short loc_18000B2D9
0x18000b25f  cmp     r8d, 0FEh
0x18000b266  jz      short loc_18000B2D9
0x18000b268  mov     [rsp+38h+var_18], 0
0x18000b271  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b275  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000b27b  test    edx, edx
0x18000b27d  jns     short loc_18000B285
0x18000b27f  or      word ptr [rsp+38h+var_18+6], 1
0x18000b285  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b28c  test    rax, rax
0x18000b28f  jnz     short loc_18000B2CD
0x18000b291  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b298  test    rax, rax
0x18000b29b  jnz     short loc_18000B2B1
0x18000b29d  lea     rcx, ModuleName; "ntdll.dll"
0x18000b2a4  call    cs:__imp_GetModuleHandleW
0x18000b2aa  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b2b1  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b2b8  mov     rcx, rax; hModule
0x18000b2bb  call    cs:__imp_GetProcAddress
0x18000b2c1  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b2c8  test    rax, rax
0x18000b2cb  jz      short loc_18000B2EA
0x18000b2cd  lea     rcx, [rsp+38h+var_18]
0x18000b2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d7  jmp     short loc_18000B2EA
0x18000b2d9  mov     r9, rax
0x18000b2dc  mov     edx, ecx
0x18000b2de  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b2e5  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b2ea  mov     rcx, [rsp+38h+var_10]
0x18000b2ef  xor     rcx, rsp; StackCookie
0x18000b2f2  call    __security_check_cookie
0x18000b2f7  add     rsp, 38h
0x18000b2fb  retn
```
