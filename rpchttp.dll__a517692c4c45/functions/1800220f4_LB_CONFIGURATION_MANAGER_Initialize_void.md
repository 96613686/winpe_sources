# LB_CONFIGURATION_MANAGER::Initialize(void)

- ea: `0x1800220f4`
- end: `0x180022202`
- name: `?Initialize@LB_CONFIGURATION_MANAGER@@QEAAJXZ`
- size: `270`
- prototype: `__int64 __fastcall(LB_CONFIGURATION_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022208`

## callees

- `0x1800220f4`
- `0x180022770`
- `0x18002305c`
- `0x180023208`
- `0x180023688`
- `0x180024258`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002217e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800221ea`
- `ntdll!RtlLeaveCriticalSection` at `0x18002217e`
- `ntdll!RtlLeaveCriticalSection` at `0x1800221ea`
- `ntdll!RtlEnterCriticalSection` at `0x18002210d`
- `ntdll!RtlEnterCriticalSection` at `0x18002210d`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800221d2`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800221d2`

## pseudocode

```c
__int64 __fastcall LB_CONFIGURATION_MANAGER::Initialize(LB_CONFIGURATION_MANAGER *this)
{
  PRTL_CRITICAL_SECTION v1; // rbx
  LB_RESOURCE_ID_CONFIG_ENTRY *v2; // rdi
  LB_RESOURCE_ID_CONFIG_ENTRY **v3; // rax
  LB_RESOURCE_ID_CONFIG_ENTRY **v4; // rcx
  LB_RESOURCE_ID_CONFIG_ENTRY *v5; // rcx
  int v6; // edx
  unsigned int RegistryInformation; // edi
  struct _RTL_CRITICAL_SECTION *v8; // rcx

  v1 = g_pConfigurationManager;
  RtlEnterCriticalSection(g_pConfigurationManager);
  if ( !LODWORD(v1[1].DebugInfo) )
  {
    McGenEventRegister_EventRegister();
    v2 = *(LB_RESOURCE_ID_CONFIG_ENTRY **)&v1[1].LockCount;
    while ( v2 != (LB_RESOURCE_ID_CONFIG_ENTRY *)&v1[1].LockCount )
    {
      v3 = *(LB_RESOURCE_ID_CONFIG_ENTRY ***)v2;
      if ( *(_QWORD *)v2 )
      {
        v4 = (LB_RESOURCE_ID_CONFIG_ENTRY **)*((_QWORD *)v2 + 1);
        if ( v4 )
        {
          if ( v3[1] != v2 || *v4 != v2 )
            __fastfail(3u);
          *v4 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v3;
          v3[1] = (LB_RESOURCE_ID_CONFIG_ENTRY *)v4;
          *(_QWORD *)v2 = 0;
          *((_QWORD *)v2 + 1) = 0;
        }
      }
      v5 = v2;
      v2 = (LB_RESOURCE_ID_CONFIG_ENTRY *)v3;
      LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(v5);
    }
    RegistryInformation = LB_CONFIGURATION_MANAGER::ReadRegistryInformation(v1);
    v8 = v1;
    if ( RegistryInformation )
      goto LABEL_11;
    RegistryInformation = LB_CONFIGURATION_MANAGER::SubmitPingRequests(v1, v6);
    v8 = v1;
    if ( RegistryInformation )
      goto LABEL_11;
    RegistryInformation = LB_CONFIGURATION_MANAGER::WaitAndComplete(v1, 1);
    if ( RegistryInformation )
    {
LABEL_17:
      v8 = v1;
LABEL_11:
      RtlLeaveCriticalSection(v8);
      return RegistryInformation;
    }
    if ( !CreateTimerQueueTimer(&v1[2].OwningThread, 0, CfgMgrTimerSignal, v1, 0x7530u, 0x7530u, 0x10u) )
    {
      RegistryInformation = 14;
      goto LABEL_17;
    }
    LODWORD(v1[1].DebugInfo) = 1;
  }
  RtlLeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x1800220f4  mov     [rsp+arg_0], rbx
0x1800220f9  mov     [rsp+arg_8], rsi
0x1800220fe  push    rdi
0x1800220ff  sub     rsp, 40h
0x180022103  mov     rbx, cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x18002210a  mov     rcx, rbx; CriticalSection
0x18002210d  call    cs:__imp_RtlEnterCriticalSection
0x180022113  cmp     dword ptr [rbx+28h], 0
0x180022117  jnz     loc_1800221E7
0x18002211d  call    McGenEventRegister_EventRegister
0x180022122  lea     rsi, [rbx+30h]
0x180022126  mov     rdi, [rsi]
0x180022129  jmp     short loc_180022168
0x18002212b  mov     rax, [rdi]
0x18002212e  test    rax, rax
0x180022131  jz      short loc_18002215D
0x180022133  mov     rcx, [rdi+8]
0x180022137  test    rcx, rcx
0x18002213a  jz      short loc_18002215D
0x18002213c  cmp     [rax+8], rdi
0x180022140  jnz     short loc_180022188
0x180022142  cmp     [rcx], rdi
0x180022145  jnz     short loc_180022188
0x180022147  mov     [rcx], rax
0x18002214a  mov     [rax+8], rcx
0x18002214e  mov     qword ptr [rdi], 0
0x180022155  mov     qword ptr [rdi+8], 0
0x18002215d  mov     rcx, rdi; this
0x180022160  mov     rdi, rax
0x180022163  call    ?RemoveLifetimeReference@LB_RESOURCE_ID_CONFIG_ENTRY@@QEAAXXZ; LB_RESOURCE_ID_CONFIG_ENTRY::RemoveLifetimeReference(void)
0x180022168  cmp     rdi, rsi
0x18002216b  jnz     short loc_18002212B
0x18002216d  mov     rcx, rbx; CriticalSection
0x180022170  call    ?ReadRegistryInformation@LB_CONFIGURATION_MANAGER@@QEAAJXZ; LB_CONFIGURATION_MANAGER::ReadRegistryInformation(void)
0x180022175  mov     edi, eax
0x180022177  mov     rcx, rbx; CriticalSection
0x18002217a  test    eax, eax
0x18002217c  jz      short loc_18002218F
0x18002217e  call    cs:__imp_RtlLeaveCriticalSection
0x180022184  mov     eax, edi
0x180022186  jmp     short loc_1800221F2
0x180022188  mov     ecx, 3
0x18002218d  int     29h; Win8: RtlFailFast(ecx)
0x18002218f  call    ?SubmitPingRequests@LB_CONFIGURATION_MANAGER@@AEAAJH@Z; LB_CONFIGURATION_MANAGER::SubmitPingRequests(int)
0x180022194  mov     edi, eax
0x180022196  mov     rcx, rbx; CriticalSection
0x180022199  test    eax, eax
0x18002219b  jnz     short loc_18002217E
0x18002219d  lea     esi, [rax+1]
0x1800221a0  mov     edx, esi; int
0x1800221a2  call    ?WaitAndComplete@LB_CONFIGURATION_MANAGER@@AEAAJH@Z; LB_CONFIGURATION_MANAGER::WaitAndComplete(int)
0x1800221a7  mov     edi, eax
0x1800221a9  test    eax, eax
0x1800221ab  jnz     short loc_1800221DF
0x1800221ad  mov     eax, 7530h
0x1800221b2  mov     [rsp+48h+Flags], 10h; Flags
0x1800221ba  mov     [rsp+48h+Period], eax; Period
0x1800221be  lea     rcx, [rbx+60h]; phNewTimer
0x1800221c2  mov     r9, rbx; Parameter
0x1800221c5  mov     [rsp+48h+DueTime], eax; DueTime
0x1800221c9  lea     r8, ?CfgMgrTimerSignal@@YAXPEAXE@Z; Callback
0x1800221d0  xor     edx, edx; TimerQueue
0x1800221d2  call    cs:__imp_CreateTimerQueueTimer
0x1800221d8  test    eax, eax
0x1800221da  jnz     short loc_1800221E4
0x1800221dc  lea     edi, [rsi+0Dh]
0x1800221df  mov     rcx, rbx
0x1800221e2  jmp     short loc_18002217E
0x1800221e4  mov     [rbx+28h], esi
0x1800221e7  mov     rcx, rbx; CriticalSection
0x1800221ea  call    cs:__imp_RtlLeaveCriticalSection
0x1800221f0  xor     eax, eax
0x1800221f2  mov     rbx, [rsp+48h+arg_0]
0x1800221f7  mov     rsi, [rsp+48h+arg_8]
0x1800221fc  add     rsp, 40h
0x180022200  pop     rdi
0x180022201  retn
```
