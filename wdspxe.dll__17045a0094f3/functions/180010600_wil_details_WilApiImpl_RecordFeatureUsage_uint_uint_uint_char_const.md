# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x180010600`
- end: `0x18001073a`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000b0d8`
- `0x18000cd0c`
- `0x18000cef0`
- `0x18000d514`
- `0x18000d70c`
- `0x180010600`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800106f8`
- `KERNEL32!GetProcAddress` at `0x1800106f8`
- `KERNEL32!GetModuleHandleW` at `0x1800106db`
- `KERNEL32!GetModuleHandleW` at `0x1800106db`

## string_xrefs

- `0x1800106d4`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&SRWLock[25], SRWLock);
    wil::details_abi::FeatureStateData::RecordUsage(SRWLock);
  }
}

```

## disassembly

```asm
0x180010600  sub     rsp, 38h
0x180010604  mov     eax, edx
0x180010606  btr     edx, 1Fh
0x18001060a  test    ecx, ecx
0x18001060c  jnz     short loc_180010673
0x18001060e  test    r8d, r8d
0x180010611  jnz     short loc_180010673
0x180010613  test    edx, edx
0x180010615  jnz     short loc_180010673
0x180010617  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18001061d  jnz     loc_180010734
0x180010623  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001062a  test    rax, rax
0x18001062d  jz      short loc_18001063C
0x18001062f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010634  test    al, al
0x180010636  jnz     loc_180010734
0x18001063c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180010643  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180010648  test    al, al
0x18001064a  jz      loc_180010734
0x180010650  mov     rdx, cs:SRWLock; SRWLock
0x180010657  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18001065e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180010663  mov     rcx, cs:SRWLock; SRWLock
0x18001066a  add     rsp, 38h
0x18001066e  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180010673  bt      edx, 1Eh
0x180010677  jnb     short loc_180010692
0x180010679  mov     r9d, r8d; unsigned int
0x18001067c  movzx   r8d, dx; unsigned __int16
0x180010680  mov     edx, ecx; unsigned int
0x180010682  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x180010689  add     rsp, 38h
0x18001068d  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180010692  test    r8d, r8d
0x180010695  jnz     loc_180010720
0x18001069b  cmp     edx, 0FEh
0x1800106a1  jz      short loc_180010720
0x1800106a3  and     [rsp+38h+var_18], 0
0x1800106a9  mov     dword ptr [rsp+38h+var_18], ecx
0x1800106ad  mov     word ptr [rsp+38h+var_18+4], dx
0x1800106b2  test    eax, eax
0x1800106b4  jns     short loc_1800106BC
0x1800106b6  or      word ptr [rsp+38h+var_18+6], 1
0x1800106bc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800106c3  test    rax, rax
0x1800106c6  jnz     short loc_180010710
0x1800106c8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800106cf  test    rax, rax
0x1800106d2  jnz     short loc_1800106EE
0x1800106d4  lea     rcx, ModuleName; "ntdll.dll"
0x1800106db  call    cs:__imp_GetModuleHandleW
0x1800106e2  nop     dword ptr [rax+rax+00h]
0x1800106e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800106ee  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800106f5  mov     rcx, rax; hModule
0x1800106f8  call    cs:__imp_GetProcAddress
0x1800106ff  nop     dword ptr [rax+rax+00h]
0x180010704  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001070b  test    rax, rax
0x18001070e  jz      short loc_180010734
0x180010710  lea     rcx, [rsp+38h+var_18]
0x180010715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001071a  add     rsp, 38h
0x18001071e  retn
0x180010720  mov     r9d, r8d
0x180010723  mov     r8d, edx
0x180010726  mov     edx, ecx
0x180010728  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18001072f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x180010734  add     rsp, 38h
0x180010738  retn
```
