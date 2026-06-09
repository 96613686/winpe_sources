# Spinlock<19,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x100408e00`
- end: `0x100408eee`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100408160`
- `0x100409760`
- `0x10040abb0`
- `0x10040ad90`
- `0x10040af70`
- `0x10041e640`

## callees

- `0x100408e00`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100408ea0`
- `KERNEL32!QueryPerformanceCounter` at `0x100408ea0`
- `sqldk!SystemThread_TlsOffset` at `0x100408e1e`
- `sqldk!SystemThread_TlsIndex` at `0x100408e15`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408e60`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408e60`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408e70`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408e70`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408ec4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408ec4`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408e85`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408e85`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408edd`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408edd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100408e8f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100408e4f`

## pseudocode

```c
__int64 Spinlock<19,1,268435714>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 19, 1);
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
               19,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               19,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x100408e00  mov     [rsp+arg_0], rbx
0x100408e05  push    rdi
0x100408e06  sub     rsp, 20h
0x100408e0a  mov     rdx, gs:58h
0x100408e13  xor     edi, edi
0x100408e15  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100408e1c  mov     ecx, [rax]
0x100408e1e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408e25  mov     r8d, [rax]
0x100408e28  add     r8, [rdx+rcx*8]
0x100408e2c  jz      short loc_100408E4C
0x100408e2e  cmp     [r8+110h], r8
0x100408e35  jnz     short loc_100408E4C
0x100408e37  mov     rbx, [r8+100h]
0x100408e3e  test    rbx, rbx
0x100408e41  jz      short loc_100408E4C
0x100408e43  mov     rbx, [rbx+3E0h]
0x100408e4a  jmp     short loc_100408E4F
0x100408e4c  mov     rbx, rdi
0x100408e4f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100408e56  test    byte ptr [rax], 1
0x100408e59  jz      short loc_100408E79
0x100408e5b  test    rbx, rbx
0x100408e5e  jz      short loc_100408E79
0x100408e60  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100408e66  movzx   edx, word ptr [rbx+0A0h]
0x100408e6d  mov     rcx, rax
0x100408e70  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100408e76  mov     rdi, rax
0x100408e79  mov     edx, 13h
0x100408e7e  mov     rcx, rdi
0x100408e81  lea     r8d, [rdx-12h]
0x100408e85  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x100408e8b  test    al, al
0x100408e8d  jnz     short loc_100408EE3
0x100408e8f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100408e96  cmp     dword ptr [rcx], 0
0x100408e99  jz      short loc_100408EAD
0x100408e9b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x100408ea0  call    cs:__imp_QueryPerformanceCounter
0x100408ea6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x100408eab  jmp     short loc_100408EB5
0x100408ead  mov     rbx, ds:7FFE0008h
0x100408eb5  mov     edx, 13h
0x100408eba  mov     r9, rbx
0x100408ebd  mov     rcx, rdi
0x100408ec0  lea     r8d, [rdx-12h]
0x100408ec4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100408eca  test    al, al
0x100408ecc  jz      short loc_100408EE3
0x100408ece  mov     edx, 13h
0x100408ed3  mov     r9, rbx
0x100408ed6  mov     rcx, rdi
0x100408ed9  lea     r8d, [rdx-12h]
0x100408edd  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100408ee3  mov     rbx, [rsp+28h+arg_0]
0x100408ee8  add     rsp, 20h
0x100408eec  pop     rdi
0x100408eed  retn
```
