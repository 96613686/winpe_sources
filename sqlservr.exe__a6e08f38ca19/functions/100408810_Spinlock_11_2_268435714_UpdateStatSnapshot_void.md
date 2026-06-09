# Spinlock<11,2,268435714>::UpdateStatSnapshot(void)

- ea: `0x100408810`
- end: `0x1004088fe`
- name: `?UpdateStatSnapshot@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100404e50`
- `0x100405100`
- `0x100406750`
- `0x100408080`
- `0x100412470`
- `0x100413d90`
- `0x100416770`
- `0x10041d870`
- `0x10041f860`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x100408810`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004088b0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004088b0`
- `sqldk!SystemThread_TlsOffset` at `0x10040882e`
- `sqldk!SystemThread_TlsIndex` at `0x100408825`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408870`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100408870`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408880`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100408880`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004088d4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004088d4`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408895`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100408895`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004088ed`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004088ed`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040889f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040885f`

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
0x100408810  mov     [rsp+arg_0], rbx
0x100408815  push    rdi
0x100408816  sub     rsp, 20h
0x10040881a  mov     rdx, gs:58h
0x100408823  xor     edi, edi
0x100408825  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040882c  mov     ecx, [rax]
0x10040882e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100408835  mov     r8d, [rax]
0x100408838  add     r8, [rdx+rcx*8]
0x10040883c  jz      short loc_10040885C
0x10040883e  cmp     [r8+110h], r8
0x100408845  jnz     short loc_10040885C
0x100408847  mov     rbx, [r8+100h]
0x10040884e  test    rbx, rbx
0x100408851  jz      short loc_10040885C
0x100408853  mov     rbx, [rbx+3E0h]
0x10040885a  jmp     short loc_10040885F
0x10040885c  mov     rbx, rdi
0x10040885f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100408866  test    byte ptr [rax], 1
0x100408869  jz      short loc_100408889
0x10040886b  test    rbx, rbx
0x10040886e  jz      short loc_100408889
0x100408870  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100408876  movzx   edx, word ptr [rbx+0A0h]
0x10040887d  mov     rcx, rax
0x100408880  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100408886  mov     rdi, rax
0x100408889  mov     edx, 0Bh
0x10040888e  mov     rcx, rdi
0x100408891  lea     r8d, [rdx-0Ah]
0x100408895  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10040889b  test    al, al
0x10040889d  jnz     short loc_1004088F3
0x10040889f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004088a6  cmp     dword ptr [rcx], 0
0x1004088a9  jz      short loc_1004088BD
0x1004088ab  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x1004088b0  call    cs:__imp_QueryPerformanceCounter
0x1004088b6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x1004088bb  jmp     short loc_1004088C5
0x1004088bd  mov     rbx, ds:7FFE0008h
0x1004088c5  mov     edx, 0Bh
0x1004088ca  mov     r9, rbx
0x1004088cd  mov     rcx, rdi
0x1004088d0  lea     r8d, [rdx-0Ah]
0x1004088d4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004088da  test    al, al
0x1004088dc  jz      short loc_1004088F3
0x1004088de  mov     edx, 0Bh
0x1004088e3  mov     r9, rbx
0x1004088e6  mov     rcx, rdi
0x1004088e9  lea     r8d, [rdx-0Ah]
0x1004088ed  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004088f3  mov     rbx, [rsp+28h+arg_0]
0x1004088f8  add     rsp, 20h
0x1004088fc  pop     rdi
0x1004088fd  retn
```
