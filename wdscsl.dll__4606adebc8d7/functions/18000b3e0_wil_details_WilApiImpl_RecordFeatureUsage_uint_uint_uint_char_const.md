# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b3e0`
- end: `0x18000b51a`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800053c8`
- `0x180007fec`
- `0x180008698`
- `0x180008a34`
- `0x180008c2c`
- `0x18000b3e0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000b4d8`
- `KERNEL32!GetProcAddress` at `0x18000b4d8`
- `KERNEL32!GetModuleHandleW` at `0x18000b4bb`
- `KERNEL32!GetModuleHandleW` at `0x18000b4bb`

## string_xrefs

- `0x18000b4b4`: `ntdll.dll`

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
0x18000b3e0  sub     rsp, 38h
0x18000b3e4  mov     eax, edx
0x18000b3e6  btr     edx, 1Fh
0x18000b3ea  test    ecx, ecx
0x18000b3ec  jnz     short loc_18000B453
0x18000b3ee  test    r8d, r8d
0x18000b3f1  jnz     short loc_18000B453
0x18000b3f3  test    edx, edx
0x18000b3f5  jnz     short loc_18000B453
0x18000b3f7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18000b3fd  jnz     loc_18000B514
0x18000b403  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b40a  test    rax, rax
0x18000b40d  jz      short loc_18000B41C
0x18000b40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b414  test    al, al
0x18000b416  jnz     loc_18000B514
0x18000b41c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000b423  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b428  test    al, al
0x18000b42a  jz      loc_18000B514
0x18000b430  mov     rdx, cs:SRWLock; SRWLock
0x18000b437  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b43e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000b443  mov     rcx, cs:SRWLock; SRWLock
0x18000b44a  add     rsp, 38h
0x18000b44e  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b453  bt      edx, 1Eh
0x18000b457  jnb     short loc_18000B472
0x18000b459  mov     r9d, r8d; unsigned int
0x18000b45c  movzx   r8d, dx; unsigned __int16
0x18000b460  mov     edx, ecx; unsigned int
0x18000b462  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000b469  add     rsp, 38h
0x18000b46d  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000b472  test    r8d, r8d
0x18000b475  jnz     loc_18000B500
0x18000b47b  cmp     edx, 0FEh
0x18000b481  jz      short loc_18000B500
0x18000b483  and     [rsp+38h+var_18], 0
0x18000b489  mov     dword ptr [rsp+38h+var_18], ecx
0x18000b48d  mov     word ptr [rsp+38h+var_18+4], dx
0x18000b492  test    eax, eax
0x18000b494  jns     short loc_18000B49C
0x18000b496  or      word ptr [rsp+38h+var_18+6], 1
0x18000b49c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b4a3  test    rax, rax
0x18000b4a6  jnz     short loc_18000B4F0
0x18000b4a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4af  test    rax, rax
0x18000b4b2  jnz     short loc_18000B4CE
0x18000b4b4  lea     rcx, ModuleName; "ntdll.dll"
0x18000b4bb  call    cs:__imp_GetModuleHandleW
0x18000b4c2  nop     dword ptr [rax+rax+00h]
0x18000b4c7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4ce  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b4d5  mov     rcx, rax; hModule
0x18000b4d8  call    cs:__imp_GetProcAddress
0x18000b4df  nop     dword ptr [rax+rax+00h]
0x18000b4e4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b4eb  test    rax, rax
0x18000b4ee  jz      short loc_18000B514
0x18000b4f0  lea     rcx, [rsp+38h+var_18]
0x18000b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fa  add     rsp, 38h
0x18000b4fe  retn
0x18000b500  mov     r9d, r8d
0x18000b503  mov     r8d, edx
0x18000b506  mov     edx, ecx
0x18000b508  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000b50f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000b514  add     rsp, 38h
0x18000b518  retn
```
