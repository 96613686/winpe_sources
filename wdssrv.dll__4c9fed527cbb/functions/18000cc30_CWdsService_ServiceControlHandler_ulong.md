# CWdsService::ServiceControlHandler(ulong)

- ea: `0x18000cc30`
- end: `0x18000cee1`
- name: `?ServiceControlHandler@CWdsService@@QEAAXK@Z`
- size: `689`
- prototype: `void __fastcall(CWdsService *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000eb10`

## callees

- `0x180003680`
- `0x180008214`
- `0x180008514`
- `0x18000c3b4`
- `0x18000cc30`
- `0x18000e360`
- `0x18000f0dc`
- `0x18001791c`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cea9`
- `KERNEL32!GetLastError` at `0x18000cea9`
- `KERNEL32!LeaveCriticalSection` at `0x18000ccad`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd4b`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd75`
- `KERNEL32!LeaveCriticalSection` at `0x18000ccad`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd4b`
- `KERNEL32!LeaveCriticalSection` at `0x18000cd75`
- `KERNEL32!EnterCriticalSection` at `0x18000cc88`
- `KERNEL32!EnterCriticalSection` at `0x18000cc97`
- `KERNEL32!EnterCriticalSection` at `0x18000cce4`
- `KERNEL32!EnterCriticalSection` at `0x18000cc88`
- `KERNEL32!EnterCriticalSection` at `0x18000cc97`
- `KERNEL32!EnterCriticalSection` at `0x18000cce4`
- `KERNEL32!SetEvent` at `0x18000ce99`
- `KERNEL32!SetEvent` at `0x18000ce99`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cd2e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ce58`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000cd2e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x18000ce58`
- `WdsServerCommonLib!?Reset@CPerfCounters@@QEAAXXZ` at `0x18000cdb2`
- `WdsServerCommonLib!?Reset@CPerfCounters@@QEAAXXZ` at `0x18000cdb2`

## string_xrefs

- `0x18000ce3f`: `Service Paused.`
- `0x18000ce0a`: `Service Resumed.`

## pseudocode

```c
void __fastcall CWdsService::ServiceControlHandler(CWdsService *this, unsigned int a2)
{
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // r14
  void (__fastcall *v7)(__int64, _QWORD); // r13
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  __int64 v9; // r14
  unsigned int v10; // edi
  unsigned int v11; // edi
  unsigned int v12; // edi
  unsigned int v13; // edi
  unsigned int v14; // edi
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  DWORD LastError; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // [rsp+20h] [rbp-48h]
  __int64 v31; // [rsp+28h] [rbp-40h]
  __int64 v32; // [rsp+30h] [rbp-38h]

  if ( a2 == 128 )
  {
    CUdpHandler::UpdateEndpoints((CWdsService *)((char *)this + 1160));
    CUdpPortRange::Initialize((LPCRITICAL_SECTION)((char *)this + 1264));
  }
  else if ( a2 == 132 )
  {
    CWdsService::RegenerateServerDuid(this);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  v4 = *((_QWORD *)this + 8382);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  if ( v4 )
  {
    v5 = *((_QWORD *)this + 8382);
    while ( v5 )
    {
      v6 = v5;
      v5 = *(_QWORD *)(v5 + 272);
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 200));
      if ( a2 == 130 )
      {
        LODWORD(v32) = *(_DWORD *)(v6 + 256);
        LODWORD(v31) = *(_DWORD *)(v6 + 240);
        LODWORD(v30) = *(_DWORD *)(v6 + 32);
        CTrace::Trace(
          (CTrace *)qword_180039310,
          0x20000u,
          L"Wds Provider\n"
           "------------\n"
           "Name: %s\n"
           "Initialization: %u\n"
           "Active Requests: %u\n"
           "Active Packet Allocation: %u\n",
          *(_QWORD *)(v6 + 16),
          v30,
          v31,
          v32);
      }
      v7 = *(void (__fastcall **)(__int64, _QWORD))(v6 + 152);
      v8 = (struct _RTL_CRITICAL_SECTION *)(v6 + 200);
      v9 = *(_QWORD *)(v6 + 160);
      LeaveCriticalSection(v8);
      if ( v7 )
        v7(v9, a2);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 67072));
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 125;
        if ( v13 )
        {
          v14 = v13 - 2;
          if ( v14 )
          {
            if ( v14 == 3 )
              CPerfCounters::Reset((CPerfCounters *)&g_PerfCounters);
          }
          else
          {
            CWdsService::DumpState(this);
          }
        }
        else
        {
          CWdsService::UpdateSettings(this);
        }
      }
      else
      {
        v15 = CWdsService::ChangeState(this, 4, 0, 0);
        if ( !(unsigned int)ElValidateWin32_0(v15, v16, v17, 965) )
        {
          _InterlockedExchange((volatile __int32 *)this + 16812, 0);
          CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Service Resumed.");
        }
      }
    }
    else
    {
      v18 = CWdsService::ChangeState(this, 7, 0, 0);
      if ( !(unsigned int)ElValidateWin32_0(v18, v19, v20, 929) )
      {
        _InterlockedExchange((volatile __int32 *)this + 16812, 1);
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"Service Paused.");
      }
    }
  }
  else
  {
    v21 = CWdsService::ChangeState(this, 3, 0, 0);
    v24 = ElValidateWin32_0(v21, v22, v23, 718);
    if ( !(unsigned int)ElValidateWin32_0(v24, v25, v26, 719) && !SetEvent(*(HANDLE *)this) )
    {
      LastError = GetLastError();
      ElValidateWin32_0(LastError, v28, v29, 727);
    }
  }
}

```

## disassembly

```asm
0x18000cc30  mov     [rsp+arg_0], rbx
0x18000cc35  mov     [rsp+arg_8], rbp
0x18000cc3a  mov     [rsp+arg_10], rsi
0x18000cc3f  push    rdi
0x18000cc40  push    r12
0x18000cc42  push    r13
0x18000cc44  push    r14
0x18000cc46  push    r15
0x18000cc48  sub     rsp, 40h
0x18000cc4c  mov     eax, edx
0x18000cc4e  mov     edi, edx
0x18000cc50  mov     rsi, rcx
0x18000cc53  sub     eax, 80h
0x18000cc58  jz      short loc_18000CC66
0x18000cc5a  cmp     eax, 4
0x18000cc5d  jnz     short loc_18000CC7E
0x18000cc5f  call    ?RegenerateServerDuid@CWdsService@@AEAAKXZ; CWdsService::RegenerateServerDuid(void)
0x18000cc64  jmp     short loc_18000CC7E
0x18000cc66  add     rcx, 488h; this
0x18000cc6d  call    ?UpdateEndpoints@CUdpHandler@@QEAAKXZ; CUdpHandler::UpdateEndpoints(void)
0x18000cc72  lea     rcx, [rsi+4F0h]; lpCriticalSection
0x18000cc79  call    ?Initialize@CUdpPortRange@@QEAAKXZ; CUdpPortRange::Initialize(void)
0x18000cc7e  lea     r15, [rsi+10600h]
0x18000cc85  mov     rcx, r15; lpCriticalSection
0x18000cc88  call    cs:__imp_EnterCriticalSection
0x18000cc8f  nop     dword ptr [rax+rax+00h]
0x18000cc94  mov     rcx, r15; lpCriticalSection
0x18000cc97  call    cs:__imp_EnterCriticalSection
0x18000cc9e  nop     dword ptr [rax+rax+00h]
0x18000cca3  mov     rbx, [rsi+105F0h]
0x18000ccaa  mov     rcx, r15; lpCriticalSection
0x18000ccad  call    cs:__imp_LeaveCriticalSection
0x18000ccb4  nop     dword ptr [rax+rax+00h]
0x18000ccb9  xor     ebp, ebp
0x18000ccbb  test    rbx, rbx
0x18000ccbe  jz      loc_18000CD72
0x18000ccc4  mov     rbx, [rsi+105F0h]
0x18000cccb  jmp     loc_18000CD69
0x18000ccd0  lea     r14, [rbx]
0x18000ccd3  mov     rbx, [rbx+110h]
0x18000ccda  lea     r12, [r14+0C8h]
0x18000cce1  mov     rcx, r12; lpCriticalSection
0x18000cce4  call    cs:__imp_EnterCriticalSection
0x18000cceb  nop     dword ptr [rax+rax+00h]
0x18000ccf0  cmp     edi, 82h
0x18000ccf6  jnz     short loc_18000CD3A
0x18000ccf8  mov     eax, [r14+100h]
0x18000ccff  lea     rcx, qword_180039310
0x18000cd06  mov     edx, [r14+0F0h]
0x18000cd0d  mov     r8d, [r14+20h]
0x18000cd11  mov     r9, [r14+10h]
0x18000cd15  mov     [rsp+68h+var_38], eax
0x18000cd19  mov     dword ptr [rsp+68h+var_40], edx
0x18000cd1d  mov     edx, 20000h
0x18000cd22  mov     dword ptr [rsp+68h+var_48], r8d
0x18000cd27  lea     r8, aWdsProviderNam; "Wds Provider\n------------\nName: %s\nI"...
0x18000cd2e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000cd35  nop     dword ptr [rax+rax+00h]
0x18000cd3a  mov     r13, [r14+98h]
0x18000cd41  mov     rcx, r12; lpCriticalSection
0x18000cd44  mov     r14, [r14+0A0h]
0x18000cd4b  call    cs:__imp_LeaveCriticalSection
0x18000cd52  nop     dword ptr [rax+rax+00h]
0x18000cd57  test    r13, r13
0x18000cd5a  jz      short loc_18000CD69
0x18000cd5c  mov     edx, edi
0x18000cd5e  mov     rcx, r14
0x18000cd61  mov     rax, r13
0x18000cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd69  test    rbx, rbx
0x18000cd6c  jnz     loc_18000CCD0
0x18000cd72  mov     rcx, r15; lpCriticalSection
0x18000cd75  call    cs:__imp_LeaveCriticalSection
0x18000cd7c  nop     dword ptr [rax+rax+00h]
0x18000cd81  sub     edi, 1
0x18000cd84  jz      loc_18000CE66
0x18000cd8a  sub     edi, 1
0x18000cd8d  jz      loc_18000CE13
0x18000cd93  sub     edi, 1
0x18000cd96  jz      short loc_18000CDDD
0x18000cd98  sub     edi, 7Dh ; '}'
0x18000cd9b  jz      short loc_18000CDD0
0x18000cd9d  sub     edi, 2
0x18000cda0  jz      short loc_18000CDC3
0x18000cda2  cmp     edi, 3
0x18000cda5  jnz     loc_18000CEC2
0x18000cdab  lea     rcx, ?g_PerfCounters@@3VCWdsPerfCounters@@A; CWdsPerfCounters g_PerfCounters
0x18000cdb2  call    cs:__imp_?Reset@CPerfCounters@@QEAAXXZ; CPerfCounters::Reset(void)
0x18000cdb9  nop     dword ptr [rax+rax+00h]
0x18000cdbe  jmp     loc_18000CEC2
0x18000cdc3  mov     rcx, rsi; this
0x18000cdc6  call    ?DumpState@CWdsService@@QEAAXXZ; CWdsService::DumpState(void)
0x18000cdcb  jmp     loc_18000CEC2
0x18000cdd0  mov     rcx, rsi; this
0x18000cdd3  call    ?UpdateSettings@CWdsService@@AEAAKXZ; CWdsService::UpdateSettings(void)
0x18000cdd8  jmp     loc_18000CEC2
0x18000cddd  xor     r9d, r9d; unsigned int
0x18000cde0  xor     r8d, r8d; int
0x18000cde3  mov     rcx, rsi; this
0x18000cde6  lea     edx, [r9+4]; unsigned int
0x18000cdea  call    ?ChangeState@CWdsService@@AEAAKKHK@Z; CWdsService::ChangeState(ulong,int,ulong)
0x18000cdef  mov     r9d, 3C5h
0x18000cdf5  mov     ecx, eax
0x18000cdf7  call    ElValidateWin32_0
0x18000cdfc  test    eax, eax
0x18000cdfe  jnz     loc_18000CEC2
0x18000ce04  xchg    ebp, [rsi+106B0h]
0x18000ce0a  lea     r8, aServiceResumed; "Service Resumed."
0x18000ce11  jmp     short loc_18000CE4C
0x18000ce13  xor     r9d, r9d; unsigned int
0x18000ce16  xor     r8d, r8d; int
0x18000ce19  mov     rcx, rsi; this
0x18000ce1c  lea     edx, [r9+7]; unsigned int
0x18000ce20  call    ?ChangeState@CWdsService@@AEAAKKHK@Z; CWdsService::ChangeState(ulong,int,ulong)
0x18000ce25  mov     r9d, 3A1h
0x18000ce2b  mov     ecx, eax
0x18000ce2d  call    ElValidateWin32_0
0x18000ce32  test    eax, eax
0x18000ce34  jnz     loc_18000CEC2
0x18000ce3a  mov     eax, 1
0x18000ce3f  lea     r8, aServicePaused; "Service Paused."
0x18000ce46  xchg    eax, [rsi+106B0h]
0x18000ce4c  mov     edx, 20000h
0x18000ce51  lea     rcx, qword_180039310
0x18000ce58  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000ce5f  nop     dword ptr [rax+rax+00h]
0x18000ce64  jmp     short loc_18000CEC2
0x18000ce66  xor     r9d, r9d; unsigned int
0x18000ce69  xor     r8d, r8d; int
0x18000ce6c  mov     rcx, rsi; this
0x18000ce6f  lea     edx, [r9+3]; unsigned int
0x18000ce73  call    ?ChangeState@CWdsService@@AEAAKKHK@Z; CWdsService::ChangeState(ulong,int,ulong)
0x18000ce78  mov     ecx, eax
0x18000ce7a  mov     r9d, 2CEh
0x18000ce80  call    ElValidateWin32_0
0x18000ce85  mov     r9d, 2CFh
0x18000ce8b  mov     ecx, eax
0x18000ce8d  call    ElValidateWin32_0
0x18000ce92  test    eax, eax
0x18000ce94  jnz     short loc_18000CEC2
0x18000ce96  mov     rcx, [rsi]; hEvent
0x18000ce99  call    cs:__imp_SetEvent
0x18000cea0  nop     dword ptr [rax+rax+00h]
0x18000cea5  test    eax, eax
0x18000cea7  jnz     short loc_18000CEC2
0x18000cea9  call    cs:__imp_GetLastError
0x18000ceb0  nop     dword ptr [rax+rax+00h]
0x18000ceb5  mov     ecx, eax
0x18000ceb7  mov     r9d, 2D7h
0x18000cebd  call    ElValidateWin32_0
0x18000cec2  lea     r11, [rsp+68h+var_28]
0x18000cec7  mov     rbx, [r11+30h]
0x18000cecb  mov     rbp, [r11+38h]
0x18000cecf  mov     rsi, [r11+40h]
0x18000ced3  mov     rsp, r11
0x18000ced6  pop     r15
0x18000ced8  pop     r14
0x18000ceda  pop     r13
0x18000cedc  pop     r12
0x18000cede  pop     rdi
0x18000cedf  retn
```
