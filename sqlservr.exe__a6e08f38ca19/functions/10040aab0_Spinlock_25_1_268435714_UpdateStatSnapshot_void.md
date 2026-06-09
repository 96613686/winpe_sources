# Spinlock<25,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x10040aab0`
- end: `0x10040ab9e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100409de0`
- `0x10040a080`
- `0x10040a290`
- `0x10040a490`
- `0x10040a550`
- `0x100418d20`

## callees

- `0x10040aab0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040ab50`
- `KERNEL32!QueryPerformanceCounter` at `0x10040ab50`
- `sqldk!SystemThread_TlsOffset` at `0x10040aace`
- `sqldk!SystemThread_TlsIndex` at `0x10040aac5`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ab10`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ab10`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040ab20`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040ab20`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040ab74`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040ab74`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040ab35`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040ab35`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040ab8d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040ab8d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ab3f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040aaff`

## pseudocode

```c
__int64 Spinlock<25,1,268435714>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 25, 1);
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
               25,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               25,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x10040aab0  mov     [rsp+arg_0], rbx
0x10040aab5  push    rdi
0x10040aab6  sub     rsp, 20h
0x10040aaba  mov     rdx, gs:58h
0x10040aac3  xor     edi, edi
0x10040aac5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040aacc  mov     ecx, [rax]
0x10040aace  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040aad5  mov     r8d, [rax]
0x10040aad8  add     r8, [rdx+rcx*8]
0x10040aadc  jz      short loc_10040AAFC
0x10040aade  cmp     [r8+110h], r8
0x10040aae5  jnz     short loc_10040AAFC
0x10040aae7  mov     rbx, [r8+100h]
0x10040aaee  test    rbx, rbx
0x10040aaf1  jz      short loc_10040AAFC
0x10040aaf3  mov     rbx, [rbx+3E0h]
0x10040aafa  jmp     short loc_10040AAFF
0x10040aafc  mov     rbx, rdi
0x10040aaff  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040ab06  test    byte ptr [rax], 1
0x10040ab09  jz      short loc_10040AB29
0x10040ab0b  test    rbx, rbx
0x10040ab0e  jz      short loc_10040AB29
0x10040ab10  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040ab16  movzx   edx, word ptr [rbx+0A0h]
0x10040ab1d  mov     rcx, rax
0x10040ab20  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10040ab26  mov     rdi, rax
0x10040ab29  mov     edx, 19h
0x10040ab2e  mov     rcx, rdi
0x10040ab31  lea     r8d, [rdx-18h]
0x10040ab35  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10040ab3b  test    al, al
0x10040ab3d  jnz     short loc_10040AB93
0x10040ab3f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ab46  cmp     dword ptr [rcx], 0
0x10040ab49  jz      short loc_10040AB5D
0x10040ab4b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10040ab50  call    cs:__imp_QueryPerformanceCounter
0x10040ab56  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10040ab5b  jmp     short loc_10040AB65
0x10040ab5d  mov     rbx, ds:7FFE0008h
0x10040ab65  mov     edx, 19h
0x10040ab6a  mov     r9, rbx
0x10040ab6d  mov     rcx, rdi
0x10040ab70  lea     r8d, [rdx-18h]
0x10040ab74  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040ab7a  test    al, al
0x10040ab7c  jz      short loc_10040AB93
0x10040ab7e  mov     edx, 19h
0x10040ab83  mov     r9, rbx
0x10040ab86  mov     rcx, rdi
0x10040ab89  lea     r8d, [rdx-18h]
0x10040ab8d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040ab93  mov     rbx, [rsp+28h+arg_0]
0x10040ab98  add     rsp, 20h
0x10040ab9c  pop     rdi
0x10040ab9d  retn
```
