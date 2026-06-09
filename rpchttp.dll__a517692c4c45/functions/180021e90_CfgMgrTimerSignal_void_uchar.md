# CfgMgrTimerSignal(void *,uchar)

- ea: `0x180021e90`
- end: `0x180021ecf`
- name: `?CfgMgrTimerSignal@@YAXPEAXE@Z`
- size: `63`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180021e90`
- `0x180022770`
- `0x180023208`
- `0x180023688`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180021e99`
- `KERNEL32!GetCurrentThreadId` at `0x180021e99`

## pseudocode

```c
void __fastcall CfgMgrTimerSignal(PVOID a1)
{
  int v2; // edx

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)a1 + 26, GetCurrentThreadId(), 0) )
  {
    LB_CONFIGURATION_MANAGER::ReadRegistryInformation((PRTL_CRITICAL_SECTION)a1);
    LB_CONFIGURATION_MANAGER::WaitAndComplete((PRTL_CRITICAL_SECTION)a1, 0);
    LB_CONFIGURATION_MANAGER::SubmitPingRequests((PRTL_CRITICAL_SECTION)a1, v2);
    _InterlockedExchange((volatile __int32 *)a1 + 26, 0);
  }
}

```

## disassembly

```asm
0x180021e90  push    rbx
0x180021e92  sub     rsp, 20h
0x180021e96  mov     rbx, rcx
0x180021e99  call    cs:__imp_GetCurrentThreadId
0x180021e9f  mov     edx, eax
0x180021ea1  xor     eax, eax
0x180021ea3  lock cmpxchg [rbx+68h], edx
0x180021ea8  jnz     short loc_180021EC9
0x180021eaa  mov     rcx, rbx; CriticalSection
0x180021ead  call    ?ReadRegistryInformation@LB_CONFIGURATION_MANAGER@@QEAAJXZ; LB_CONFIGURATION_MANAGER::ReadRegistryInformation(void)
0x180021eb2  xor     edx, edx; int
0x180021eb4  mov     rcx, rbx; CriticalSection
0x180021eb7  call    ?WaitAndComplete@LB_CONFIGURATION_MANAGER@@AEAAJH@Z; LB_CONFIGURATION_MANAGER::WaitAndComplete(int)
0x180021ebc  mov     rcx, rbx; CriticalSection
0x180021ebf  call    ?SubmitPingRequests@LB_CONFIGURATION_MANAGER@@AEAAJH@Z; LB_CONFIGURATION_MANAGER::SubmitPingRequests(int)
0x180021ec4  xor     eax, eax
0x180021ec6  xchg    eax, [rbx+68h]
0x180021ec9  add     rsp, 20h
0x180021ecd  pop     rbx
0x180021ece  retn
```
