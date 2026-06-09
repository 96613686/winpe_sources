# Spinlock<475,19,258>::UpdateStatSnapshot(void)

- ea: `0x10047f570`
- end: `0x10047f664`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BNL@$0BD@$0BAC@@@AEAAXXZ`
- size: `244`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10047f0e0`
- `0x10047f2a0`
- `0x10047f320`
- `0x10047f500`

## callees

- `0x10047f570`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10047f612`
- `KERNEL32!QueryPerformanceCounter` at `0x10047f612`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10047f601`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f5e0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f5e0`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f5f7`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f5f7`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047f638`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047f638`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047f653`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047f653`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f5d0`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f5d0`
- `sqldk!SystemThread_TlsIndex` at `0x10047f585`
- `sqldk!SystemThread_TlsOffset` at `0x10047f58e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047f5bf`

## pseudocode

```c
__int64 Spinlock<475,19,258>::UpdateStatSnapshot()
{
  struct SpinlockStat *SpinlockStats; // rdi
  __int64 v1; // r8
  __int64 v2; // rbx
  __int64 v3; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  __int64 result; // rax
  LARGE_INTEGER v6; // rbx
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+10h] BYREF

  SpinlockStats = 0;
  v1 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( v1 && *(_QWORD *)(v1 + 272) == v1 && (v2 = *(_QWORD *)(v1 + 256)) != 0 )
    v3 = *(_QWORD *)(v2 + 992);
  else
    v3 = 0;
  if ( (SOS_PublicGlobals::sm_osStats & 1) != 0 && v3 )
  {
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(ClientProcessGlobals, *(_WORD *)(v3 + 160));
  }
  result = SpinlockStat::IsProfiled(SpinlockStats, 475, 3);
  if ( !(_BYTE)result )
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      QueryPerformanceCounter(&PerformanceCount);
      v6 = PerformanceCount;
    }
    else
    {
      v6.QuadPart = MEMORY[0x7FFE0008];
    }
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::ShouldUpdateSnapshot)(
               SpinlockStats,
               475,
               3,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               475,
               3,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x10047f570  mov     [rsp+arg_0], rbx
0x10047f575  push    rdi
0x10047f576  sub     rsp, 20h
0x10047f57a  mov     rdx, gs:58h
0x10047f583  xor     edi, edi
0x10047f585  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047f58c  mov     ecx, [rax]
0x10047f58e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10047f595  mov     r8d, [rax]
0x10047f598  add     r8, [rdx+rcx*8]
0x10047f59c  jz      short loc_10047F5BC
0x10047f59e  cmp     [r8+110h], r8
0x10047f5a5  jnz     short loc_10047F5BC
0x10047f5a7  mov     rbx, [r8+100h]
0x10047f5ae  test    rbx, rbx
0x10047f5b1  jz      short loc_10047F5BC
0x10047f5b3  mov     rbx, [rbx+3E0h]
0x10047f5ba  jmp     short loc_10047F5BF
0x10047f5bc  mov     rbx, rdi
0x10047f5bf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10047f5c6  test    byte ptr [rax], 1
0x10047f5c9  jz      short loc_10047F5E9
0x10047f5cb  test    rbx, rbx
0x10047f5ce  jz      short loc_10047F5E9
0x10047f5d0  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10047f5d6  movzx   edx, word ptr [rbx+0A0h]
0x10047f5dd  mov     rcx, rax
0x10047f5e0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10047f5e6  mov     rdi, rax
0x10047f5e9  mov     edx, 1DBh
0x10047f5ee  mov     r8d, 3
0x10047f5f4  mov     rcx, rdi
0x10047f5f7  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10047f5fd  test    al, al
0x10047f5ff  jnz     short loc_10047F659
0x10047f601  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10047f608  cmp     dword ptr [rcx], 0
0x10047f60b  jz      short loc_10047F61F
0x10047f60d  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10047f612  call    cs:__imp_QueryPerformanceCounter
0x10047f618  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10047f61d  jmp     short loc_10047F627
0x10047f61f  mov     rbx, ds:7FFE0008h
0x10047f627  mov     edx, 1DBh
0x10047f62c  mov     r9, rbx
0x10047f62f  mov     r8d, 3
0x10047f635  mov     rcx, rdi
0x10047f638  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10047f63e  test    al, al
0x10047f640  jz      short loc_10047F659
0x10047f642  mov     edx, 1DBh
0x10047f647  mov     r9, rbx
0x10047f64a  mov     r8d, 3
0x10047f650  mov     rcx, rdi
0x10047f653  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10047f659  mov     rbx, [rsp+28h+arg_0]
0x10047f65e  add     rsp, 20h
0x10047f662  pop     rdi
0x10047f663  retn
```
