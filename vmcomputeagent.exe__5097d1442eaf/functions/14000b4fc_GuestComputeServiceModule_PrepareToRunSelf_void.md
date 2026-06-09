# GuestComputeServiceModule::PrepareToRunSelf(void)

- ea: `0x14000b4fc`
- end: `0x14000b6b5`
- name: `?PrepareToRunSelf@GuestComputeServiceModule@@QEAAXXZ`
- size: `441`
- prototype: `void __fastcall(GuestComputeServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003c76c`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x14000b4fc`
- `0x14000ddac`
- `0x14000ea60`
- `0x140030c28`
- `0x14003348c`
- `0x14004efec`
- `0x1400b2cf0`
- `0x1400b2f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b5df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000b5df`
- `ntdll!RtlSetProcessIsCritical` at `0x14000b5f9`
- `ntdll!RtlSetProcessIsCritical` at `0x14000b5f9`
- `ntdll!NtQuerySystemInformation` at `0x14000b59a`
- `ntdll!NtQuerySystemInformation` at `0x14000b59a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b5c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000b5c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14000b5b4`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x14000b5b4`
- `GNS!GNSModuleInit` at `0x14000b65b`
- `GNS!GNSModuleInit` at `0x14000b65b`

## string_xrefs

- `0x14000b68e`: `onecore\vm\common\vml\VmModules.h`
- `0x14000b56f`: `BreakOnServiceStart`
- `0x14000b6a2`: `onecore\vm\compute\service\guest\exe\guestcomputeservicemodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GuestComputeServiceModule::PrepareToRunSelf(GuestComputeServiceModule *this)
{
  GuestComputeServiceModule *v1; // rdi
  const char *v2; // r9
  HANDLE EventW; // rax
  const char *v4; // r9
  __int64 *started; // rax
  __int64 v6; // rdx
  ComputeService::Communication::BridgeClient *v7; // rsi
  ComputeService::Communication::BridgeClient *v8; // rdi
  int v9; // eax
  unsigned int v10; // [rsp+20h] [rbp-48h]
  HKEY hKey[2]; // [rsp+38h] [rbp-30h] BYREF
  __int16 SystemInformation; // [rsp+48h] [rbp-20h] BYREF
  ComputeService::Communication::BridgeClient *v14; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v1 = this;
    hKey[1] = 0;
    hKey[0] = (HKEY)&ComputeService::ComputeSystemSettingsStore::`vftable';
    if ( ComputeService::MachineLocalSettingsStore::OpenImpl(
           (ComputeService::MachineLocalSettingsStore *)hKey,
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Containers",
           L"Debug",
           0x20019u) )
    {
      LODWORD(v14) = 0;
      ComputeService::MachineLocalSettingsStore::QueryValue(
        (ComputeService::MachineLocalSettingsStore *)hKey,
        L"BreakOnServiceStart",
        (unsigned int *)&v14);
      if ( (_DWORD)v14 )
      {
        SystemInformation = 0;
        NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
        if ( (_BYTE)SystemInformation || NtCurrentPeb()->BeingDebugged )
          DebugBreak();
      }
    }
    if ( hKey[1] )
      RegCloseKey(hKey[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\vm\\compute\\service\\guest\\exe\\guestcomputeservicemodule.cpp",
      v2);
    v1 = this;
  }
  try
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v1 + 11) = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v4);
    RtlSetProcessIsCritical(1u, 0, 0);
    RegisterSupportedOrchestrators();
    started = (__int64 *)CreateAndStartBridgeClient(&v14);
    v6 = *started;
    *started = 0;
    v7 = (ComputeService::Communication::BridgeClient *)*((_QWORD *)v1 + 30);
    *((_QWORD *)v1 + 30) = v6;
    if ( v7 )
    {
      ComputeService::Communication::BridgeClient::~BridgeClient(v7);
      operator delete(v7, 0x140u);
    }
    v8 = v14;
    if ( v14 )
    {
      ComputeService::Communication::BridgeClient::~BridgeClient(v14);
      operator delete(v8, 0x140u);
    }
    v9 = GNSModuleInit();
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\vm\\compute\\service\\guest\\exe\\guestcomputeservicemodule.cpp",
        (const char *)(unsigned int)v9,
        v10);
  }
  catch ( ... )
  {
    GuestComputeServiceModule::CleanUpFromRunSelf(this);
    throw;
  }
}

```

## disassembly

```asm
0x14000b4fc  mov     r11, rsp
0x14000b4ff  mov     [r11+10h], rbx
0x14000b503  mov     [r11+18h], rsi
0x14000b507  push    rdi
0x14000b508  sub     rsp, 60h
0x14000b50c  mov     rax, cs:__security_cookie
0x14000b513  xor     rax, rsp
0x14000b516  mov     [rsp+68h+var_10], rax
0x14000b51b  mov     rdi, rcx
0x14000b51e  mov     [rsp+68h+var_38], rcx
0x14000b523  xorps   xmm0, xmm0
0x14000b526  movups  xmmword ptr [rsp+68h+hKey], xmm0
0x14000b52b  xor     ebx, ebx
0x14000b52d  mov     [r11-28h], rbx
0x14000b531  lea     rax, ??_7ComputeSystemSettingsStore@ComputeService@@6B@; const ComputeService::ComputeSystemSettingsStore::`vftable'
0x14000b538  mov     [r11-30h], rax
0x14000b53c  mov     [rsp+68h+var_48], 20019h; unsigned int
0x14000b544  lea     r9, aDebug; "Debug"
0x14000b54b  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000b552  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x14000b559  lea     rcx, [r11-30h]; this
0x14000b55d  call    ?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z; ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)
0x14000b562  test    al, al
0x14000b564  jz      short loc_14000B5BB
0x14000b566  mov     dword ptr [rsp+68h+var_18], ebx
0x14000b56a  lea     r8, [rsp+68h+var_18]; unsigned int *
0x14000b56f  lea     rdx, aBreakonservice; "BreakOnServiceStart"
0x14000b576  lea     rcx, [rsp+68h+hKey]; this
0x14000b57b  call    ?QueryValue@MachineLocalSettingsStore@ComputeService@@UEBA_NPEBGAEAI@Z; ComputeService::MachineLocalSettingsStore::QueryValue(ushort const *,uint &)
0x14000b580  cmp     dword ptr [rsp+68h+var_18], ebx
0x14000b584  jz      short loc_14000B5BB
0x14000b586  mov     [rsp+68h+SystemInformation], bx
0x14000b58b  xor     r9d, r9d; ReturnLength
0x14000b58e  lea     r8d, [rbx+2]; SystemInformationLength
0x14000b592  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x14000b597  lea     ecx, [rbx+23h]; SystemInformationClass
0x14000b59a  call    cs:__imp_NtQuerySystemInformation
0x14000b5a0  cmp     byte ptr [rsp+68h+SystemInformation], bl
0x14000b5a4  jnz     short loc_14000B5B4
0x14000b5a6  mov     rax, gs:60h
0x14000b5af  cmp     [rax+2], bl
0x14000b5b2  jz      short loc_14000B5BB
0x14000b5b4  call    cs:__imp_DebugBreak
0x14000b5ba  nop
0x14000b5bb  mov     rcx, [rsp+68h+hKey+8]; hKey
0x14000b5c0  test    rcx, rcx
0x14000b5c3  jz      short loc_14000B5CC
0x14000b5c5  call    cs:__imp_RegCloseKey
0x14000b5cb  nop
0x14000b5cc  jmp     short loc_14000B5D5
0x14000b5ce  xor     ebx, ebx
0x14000b5d0  mov     rdi, [rsp+68h+var_38]
0x14000b5d5  xor     r9d, r9d; lpName
0x14000b5d8  xor     r8d, r8d; bInitialState
0x14000b5db  xor     edx, edx; bManualReset
0x14000b5dd  xor     ecx, ecx; lpEventAttributes
0x14000b5df  call    cs:__imp_CreateEventW
0x14000b5e5  mov     [rdi+58h], rax
0x14000b5e9  test    rax, rax
0x14000b5ec  jz      loc_14000B689
0x14000b5f2  xor     r8d, r8d; NeedBreaks
0x14000b5f5  xor     edx, edx; OldValue
0x14000b5f7  mov     cl, 1; NewValue
0x14000b5f9  call    cs:__imp_RtlSetProcessIsCritical
0x14000b5ff  call    ?RegisterSupportedOrchestrators@@YAXXZ; RegisterSupportedOrchestrators(void)
0x14000b604  lea     rcx, [rsp+68h+var_18]
0x14000b609  call    ?CreateAndStartBridgeClient@@YA?AV?$unique_ptr@VBridgeClient@Communication@ComputeService@@U?$default_delete@VBridgeClient@Communication@ComputeService@@@std@@@std@@XZ; CreateAndStartBridgeClient(void)
0x14000b60e  mov     rdx, [rax]
0x14000b611  mov     [rax], rbx
0x14000b614  mov     rsi, [rdi+0F0h]
0x14000b61b  mov     [rdi+0F0h], rdx
0x14000b622  test    rsi, rsi
0x14000b625  jz      short loc_14000B63C
0x14000b627  mov     rcx, rsi; this
0x14000b62a  call    ??1BridgeClient@Communication@ComputeService@@QEAA@XZ; ComputeService::Communication::BridgeClient::~BridgeClient(void)
0x14000b62f  mov     edx, 140h; unsigned __int64
0x14000b634  mov     rcx, rsi; void *
0x14000b637  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b63c  mov     rdi, [rsp+68h+var_18]
0x14000b641  test    rdi, rdi
0x14000b644  jz      short loc_14000B65B
0x14000b646  mov     rcx, rdi; this
0x14000b649  call    ??1BridgeClient@Communication@ComputeService@@QEAA@XZ; ComputeService::Communication::BridgeClient::~BridgeClient(void)
0x14000b64e  mov     edx, 140h; unsigned __int64
0x14000b653  mov     rcx, rdi; void *
0x14000b656  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000b65b  call    cs:__imp_GNSModuleInit
0x14000b661  mov     rcx, [rsp+68h]; this
0x14000b666  test    eax, eax
0x14000b668  js      short loc_14000B69F
0x14000b66a  mov     rcx, [rsp+68h+var_10]
0x14000b66f  xor     rcx, rsp; StackCookie
0x14000b672  call    __security_check_cookie
0x14000b677  lea     r11, [rsp+68h+var_8]
0x14000b67c  mov     rbx, [r11+18h]
0x14000b680  mov     rsi, [r11+20h]
0x14000b684  mov     rsp, r11
0x14000b687  pop     rdi
0x14000b688  retn
0x14000b689  mov     rcx, [rsp+68h]; this
0x14000b68e  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModules.h"
0x14000b695  mov     edx, 744h; void *
0x14000b69a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000b69f  mov     r9d, eax; char *
0x14000b6a2  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\service\\guest\\e"...
0x14000b6a9  mov     edx, 0B4h; void *
0x14000b6ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
