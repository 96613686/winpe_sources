# CWdsService::OnTimer(CTimer<CWdsService> *)

- ea: `0x18000ac40`
- end: `0x18000ad9f`
- name: `?OnTimer@CWdsService@@QEAAXPEAV?$CTimer@VCWdsService@@@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(CWdsService *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000eb30`

## callees

- `0x180003680`
- `0x180008158`
- `0x18000ac40`
- `0x18000e360`
- `0x18000f0dc`
- `0x18001791c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000acc1`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad0c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad35`
- `KERNEL32!LeaveCriticalSection` at `0x18000acc1`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad0c`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad35`
- `KERNEL32!EnterCriticalSection` at `0x18000ac9c`
- `KERNEL32!EnterCriticalSection` at `0x18000acab`
- `KERNEL32!EnterCriticalSection` at `0x18000acef`
- `KERNEL32!EnterCriticalSection` at `0x18000ac9c`
- `KERNEL32!EnterCriticalSection` at `0x18000acab`
- `KERNEL32!EnterCriticalSection` at `0x18000acef`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ac6e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ac6e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ad93`

## string_xrefs

- `0x18000ac5b`: `Updating Server Configuration...`
- `0x18000ad68`: `Service Configuration Updated.`

## pseudocode

```c
void __fastcall CWdsService::OnTimer(CWdsService *this)
{
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *SpinCount; // rsi
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  void (__fastcall *v5)(PRTL_CRITICAL_SECTION_DEBUG, __int64); // r14
  struct _RTL_CRITICAL_SECTION *v6; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8

  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Updating Server Configuration...");
  CUdpHandler::UpdateEndpoints((CWdsService *)((char *)this + 1160));
  CUdpPortRange::Initialize((LPCRITICAL_SECTION)((char *)this + 1264));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  v2 = *((_QWORD *)this + 8382);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  if ( v2 )
  {
    SpinCount = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 8382);
    while ( SpinCount )
    {
      v4 = SpinCount;
      SpinCount = (struct _RTL_CRITICAL_SECTION *)SpinCount[6].SpinCount;
      EnterCriticalSection(v4 + 5);
      v5 = (void (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG, __int64))v4[3].SpinCount;
      v6 = v4 + 5;
      DebugInfo = v4[4].DebugInfo;
      LeaveCriticalSection(v6);
      if ( v5 )
        v5(DebugInfo, 128);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  CWdsService::UpdateSettings(this);
  v8 = CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change((char *)this + 67264);
  ElValidateWin32_0(v8, v9, v10, 1025);
  CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Service Configuration Updated.");
}

```

## disassembly

```asm
0x18000ac40  mov     [rsp+arg_0], rbx
0x18000ac45  mov     [rsp+arg_8], rbp
0x18000ac4a  mov     [rsp+arg_10], rsi
0x18000ac4f  push    rdi
0x18000ac50  push    r14
0x18000ac52  push    r15
0x18000ac54  sub     rsp, 20h
0x18000ac58  mov     rbp, rcx
0x18000ac5b  lea     r8, aUpdatingServer; "Updating Server Configuration..."
0x18000ac62  lea     rcx, qword_180039310
0x18000ac69  mov     edx, 20000h
0x18000ac6e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ac75  nop     dword ptr [rax+rax+00h]
0x18000ac7a  lea     rcx, [rbp+488h]; this
0x18000ac81  call    ?UpdateEndpoints@CUdpHandler@@QEAAKXZ; CUdpHandler::UpdateEndpoints(void)
0x18000ac86  lea     rcx, [rbp+4F0h]; lpCriticalSection
0x18000ac8d  call    ?Initialize@CUdpPortRange@@QEAAKXZ; CUdpPortRange::Initialize(void)
0x18000ac92  lea     r15, [rbp+10600h]
0x18000ac99  mov     rcx, r15; lpCriticalSection
0x18000ac9c  call    cs:__imp_EnterCriticalSection
0x18000aca3  nop     dword ptr [rax+rax+00h]
0x18000aca8  mov     rcx, r15; lpCriticalSection
0x18000acab  call    cs:__imp_EnterCriticalSection
0x18000acb2  nop     dword ptr [rax+rax+00h]
0x18000acb7  mov     rbx, [rbp+105F0h]
0x18000acbe  mov     rcx, r15; lpCriticalSection
0x18000acc1  call    cs:__imp_LeaveCriticalSection
0x18000acc8  nop     dword ptr [rax+rax+00h]
0x18000accd  test    rbx, rbx
0x18000acd0  jz      short loc_18000AD32
0x18000acd2  mov     rsi, [rbp+105F0h]
0x18000acd9  jmp     short loc_18000AD2D
0x18000acdb  lea     rdi, [rsi]
0x18000acde  mov     rsi, [rsi+110h]
0x18000ace5  lea     rbx, [rdi+0C8h]
0x18000acec  mov     rcx, rbx; lpCriticalSection
0x18000acef  call    cs:__imp_EnterCriticalSection
0x18000acf6  nop     dword ptr [rax+rax+00h]
0x18000acfb  mov     r14, [rdi+98h]
0x18000ad02  mov     rcx, rbx; lpCriticalSection
0x18000ad05  mov     rdi, [rdi+0A0h]
0x18000ad0c  call    cs:__imp_LeaveCriticalSection
0x18000ad13  nop     dword ptr [rax+rax+00h]
0x18000ad18  test    r14, r14
0x18000ad1b  jz      short loc_18000AD2D
0x18000ad1d  mov     edx, 80h
0x18000ad22  mov     rcx, rdi
0x18000ad25  mov     rax, r14
0x18000ad28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad2d  test    rsi, rsi
0x18000ad30  jnz     short loc_18000ACDB
0x18000ad32  mov     rcx, r15; lpCriticalSection
0x18000ad35  call    cs:__imp_LeaveCriticalSection
0x18000ad3c  nop     dword ptr [rax+rax+00h]
0x18000ad41  mov     rcx, rbp; this
0x18000ad44  call    ?UpdateSettings@CWdsService@@AEAAKXZ; CWdsService::UpdateSettings(void)
0x18000ad49  mov     edx, [rbp+106B8h]
0x18000ad4f  lea     rcx, [rbp+106C0h]
0x18000ad56  call    ?Change@?$CTimer@V?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@@@QEAAKKK@Z; CTimer<CNetworkChangeMonitor<CInterfaceMonitor>>::Change(ulong,ulong)
0x18000ad5b  mov     ecx, eax
0x18000ad5d  mov     r9d, 401h
0x18000ad63  call    ElValidateWin32_0
0x18000ad68  lea     r8, aServiceConfigu; "Service Configuration Updated."
0x18000ad6f  mov     edx, 20000h
0x18000ad74  lea     rcx, qword_180039310
0x18000ad7b  mov     rbx, [rsp+38h+arg_0]
0x18000ad80  mov     rbp, [rsp+38h+arg_8]
0x18000ad85  mov     rsi, [rsp+38h+arg_10]
0x18000ad8a  add     rsp, 20h
0x18000ad8e  pop     r15
0x18000ad90  pop     r14
0x18000ad92  pop     rdi
0x18000ad93  jmp     cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
```
