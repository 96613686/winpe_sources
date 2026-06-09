# Spinlock<48,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x100408f00`
- end: `0x100408fee`
- name: `?UpdateStatSnapshot@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100407490`
- `0x100407e20`
- `0x1004080f0`

## callees

- `0x100408f00`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100408fa0`
- `KERNEL32!QueryPerformanceCounter` at `0x100408fa0`
- `sqldk!SystemThread_TlsOffset` at `0x100408f1e`
- `sqldk!SystemThread_TlsIndex` at `0x100408f15`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408f60`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408f60`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408f70`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408f70`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408fc4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408fc4`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408f85`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408f85`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408fdd`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100408fdd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100408f8f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100408f4f`

## pseudocode

```c
__int64 Spinlock<48,1,268435714>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 48, 1);
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
               48,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               48,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x100408f00  mov     [rsp+arg_0], rbx
0x100408f05  push    rdi
0x100408f06  sub     rsp, 20h
0x100408f0a  mov     rdx, gs:58h
0x100408f13  xor     edi, edi
0x100408f15  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100408f1c  mov     ecx, [rax]
0x100408f1e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408f25  mov     r8d, [rax]
0x100408f28  add     r8, [rdx+rcx*8]
0x100408f2c  jz      short loc_100408F4C
0x100408f2e  cmp     [r8+110h], r8
0x100408f35  jnz     short loc_100408F4C
0x100408f37  mov     rbx, [r8+100h]
0x100408f3e  test    rbx, rbx
0x100408f41  jz      short loc_100408F4C
0x100408f43  mov     rbx, [rbx+3E0h]
0x100408f4a  jmp     short loc_100408F4F
0x100408f4c  mov     rbx, rdi
0x100408f4f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100408f56  test    byte ptr [rax], 1
0x100408f59  jz      short loc_100408F79
0x100408f5b  test    rbx, rbx
0x100408f5e  jz      short loc_100408F79
0x100408f60  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100408f66  movzx   edx, word ptr [rbx+0A0h]
0x100408f6d  mov     rcx, rax
0x100408f70  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100408f76  mov     rdi, rax
0x100408f79  mov     edx, 30h ; '0'
0x100408f7e  mov     rcx, rdi
0x100408f81  lea     r8d, [rdx-2Fh]
0x100408f85  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x100408f8b  test    al, al
0x100408f8d  jnz     short loc_100408FE3
0x100408f8f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100408f96  cmp     dword ptr [rcx], 0
0x100408f99  jz      short loc_100408FAD
0x100408f9b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x100408fa0  call    cs:__imp_QueryPerformanceCounter
0x100408fa6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x100408fab  jmp     short loc_100408FB5
0x100408fad  mov     rbx, ds:7FFE0008h
0x100408fb5  mov     edx, 30h ; '0'
0x100408fba  mov     r9, rbx
0x100408fbd  mov     rcx, rdi
0x100408fc0  lea     r8d, [rdx-2Fh]
0x100408fc4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100408fca  test    al, al
0x100408fcc  jz      short loc_100408FE3
0x100408fce  mov     edx, 30h ; '0'
0x100408fd3  mov     r9, rbx
0x100408fd6  mov     rcx, rdi
0x100408fd9  lea     r8d, [rdx-2Fh]
0x100408fdd  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100408fe3  mov     rbx, [rsp+28h+arg_0]
0x100408fe8  add     rsp, 20h
0x100408fec  pop     rdi
0x100408fed  retn
```
