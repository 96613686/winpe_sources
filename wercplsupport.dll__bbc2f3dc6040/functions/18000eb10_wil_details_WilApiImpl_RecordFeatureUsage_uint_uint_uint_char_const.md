# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000eb10`
- end: `0x18000ec3b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000a8ac`
- `0x18000c290`
- `0x18000c760`
- `0x18000cb08`
- `0x18000ccc0`
- `0x18000eb10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec07`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebf0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ebf0`

## string_xrefs

- `0x18000ebe9`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001C068[25], qword_18001C068);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001C068);
  }
}

```

## disassembly

```asm
0x18000eb10  sub     rsp, 38h
0x18000eb14  mov     eax, r8d
0x18000eb17  mov     r8d, edx
0x18000eb1a  btr     r8d, 1Fh; unsigned __int16
0x18000eb1f  test    ecx, ecx
0x18000eb21  jnz     short loc_18000EB8A
0x18000eb23  test    eax, eax
0x18000eb25  jnz     short loc_18000EB8A
0x18000eb27  test    r8d, r8d
0x18000eb2a  jnz     short loc_18000EB8A
0x18000eb2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000eb33  jnz     loc_18000EC36
0x18000eb39  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000eb40  test    rax, rax
0x18000eb43  jz      short loc_18000EB52
0x18000eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb4a  test    al, al
0x18000eb4c  jnz     loc_18000EC36
0x18000eb52  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000eb59  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000eb5e  test    al, al
0x18000eb60  jz      loc_18000EC36
0x18000eb66  mov     rdx, cs:qword_18001C068; SRWLock
0x18000eb6d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000eb74  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000eb79  mov     rcx, cs:qword_18001C068; SRWLock
0x18000eb80  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000eb85  jmp     loc_18000EC36
0x18000eb8a  bt      r8d, 1Eh
0x18000eb8f  jnb     short loc_18000EBA7
0x18000eb91  mov     edx, ecx; unsigned int
0x18000eb93  mov     r9d, eax; unsigned int
0x18000eb96  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000eb9d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000eba2  jmp     loc_18000EC36
0x18000eba7  test    eax, eax
0x18000eba9  jnz     short loc_18000EC25
0x18000ebab  cmp     r8d, 0FEh
0x18000ebb2  jz      short loc_18000EC25
0x18000ebb4  mov     [rsp+38h+var_18], 0
0x18000ebbd  mov     dword ptr [rsp+38h+var_18], ecx
0x18000ebc1  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000ebc7  test    edx, edx
0x18000ebc9  jns     short loc_18000EBD1
0x18000ebcb  or      word ptr [rsp+38h+var_18+6], 1
0x18000ebd1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000ebd8  test    rax, rax
0x18000ebdb  jnz     short loc_18000EC19
0x18000ebdd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebe4  test    rax, rax
0x18000ebe7  jnz     short loc_18000EBFD
0x18000ebe9  lea     rcx, ModuleName; "ntdll.dll"
0x18000ebf0  call    cs:__imp_GetModuleHandleW
0x18000ebf6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebfd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000ec04  mov     rcx, rax; hModule
0x18000ec07  call    cs:__imp_GetProcAddress
0x18000ec0d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000ec14  test    rax, rax
0x18000ec17  jz      short loc_18000EC36
0x18000ec19  lea     rcx, [rsp+38h+var_18]
0x18000ec1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec23  jmp     short loc_18000EC36
0x18000ec25  mov     edx, ecx
0x18000ec27  mov     r9, rax
0x18000ec2a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000ec31  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000ec36  add     rsp, 38h
0x18000ec3a  retn
```
