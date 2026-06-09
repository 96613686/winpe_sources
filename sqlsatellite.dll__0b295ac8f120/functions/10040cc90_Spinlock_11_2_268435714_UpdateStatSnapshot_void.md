# Spinlock<11,2,268435714>::UpdateStatSnapshot(void)

- ea: `0x10040cc90`
- end: `0x10040cd7e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100409790`
- `0x10040af40`
- `0x10040c0e0`
- `0x10040cd90`
- `0x10040ce00`
- `0x100446b10`
- `0x100464e90`
- `0x1004661f0`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x10040cc90`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040cd30`
- `KERNEL32!QueryPerformanceCounter` at `0x10040cd30`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040cd1f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040cd00`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040cd00`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cd15`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cd15`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040cd54`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040cd54`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040cd6d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040cd6d`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ccf0`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ccf0`
- `sqldk!SystemThread_TlsIndex` at `0x10040cca5`
- `sqldk!SystemThread_TlsOffset` at `0x10040ccae`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040ccdf`

## pseudocode

```c
__int64 Spinlock<11,2,268435714>::UpdateStatSnapshot()
{
  struct SpinlockStat *SpinlockStats; // rdi
  __int64 v1; // r8
  __int64 v2; // rbx
  __int64 v3; // rbx
  PerProcessGlobals *SOSProcessGlobals; // rax
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
    SOSProcessGlobals = (PerProcessGlobals *)SOS_OS::GetSOSProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(SOSProcessGlobals, *(_WORD *)(v3 + 160));
  }
  result = SpinlockStat::IsProfiled(SpinlockStats, 11, 1);
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
               11,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               11,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x10040cc90  mov     [rsp+arg_0], rbx
0x10040cc95  push    rdi
0x10040cc96  sub     rsp, 20h
0x10040cc9a  mov     rdx, gs:58h
0x10040cca3  xor     edi, edi
0x10040cca5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040ccac  mov     ecx, [rax]
0x10040ccae  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ccb5  mov     r8d, [rax]
0x10040ccb8  add     r8, [rdx+rcx*8]
0x10040ccbc  jz      short loc_10040CCDC
0x10040ccbe  cmp     [r8+110h], r8
0x10040ccc5  jnz     short loc_10040CCDC
0x10040ccc7  mov     rbx, [r8+100h]
0x10040ccce  test    rbx, rbx
0x10040ccd1  jz      short loc_10040CCDC
0x10040ccd3  mov     rbx, [rbx+3E0h]
0x10040ccda  jmp     short loc_10040CCDF
0x10040ccdc  mov     rbx, rdi
0x10040ccdf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040cce6  test    byte ptr [rax], 1
0x10040cce9  jz      short loc_10040CD09
0x10040cceb  test    rbx, rbx
0x10040ccee  jz      short loc_10040CD09
0x10040ccf0  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040ccf6  movzx   edx, word ptr [rbx+0A0h]
0x10040ccfd  mov     rcx, rax
0x10040cd00  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10040cd06  mov     rdi, rax
0x10040cd09  mov     edx, 0Bh
0x10040cd0e  mov     rcx, rdi
0x10040cd11  lea     r8d, [rdx-0Ah]
0x10040cd15  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10040cd1b  test    al, al
0x10040cd1d  jnz     short loc_10040CD73
0x10040cd1f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040cd26  cmp     dword ptr [rcx], 0
0x10040cd29  jz      short loc_10040CD3D
0x10040cd2b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10040cd30  call    cs:__imp_QueryPerformanceCounter
0x10040cd36  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10040cd3b  jmp     short loc_10040CD45
0x10040cd3d  mov     rbx, ds:7FFE0008h
0x10040cd45  mov     edx, 0Bh
0x10040cd4a  mov     r9, rbx
0x10040cd4d  mov     rcx, rdi
0x10040cd50  lea     r8d, [rdx-0Ah]
0x10040cd54  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040cd5a  test    al, al
0x10040cd5c  jz      short loc_10040CD73
0x10040cd5e  mov     edx, 0Bh
0x10040cd63  mov     r9, rbx
0x10040cd66  mov     rcx, rdi
0x10040cd69  lea     r8d, [rdx-0Ah]
0x10040cd6d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040cd73  mov     rbx, [rsp+28h+arg_0]
0x10040cd78  add     rsp, 20h
0x10040cd7c  pop     rdi
0x10040cd7d  retn
```
