# Spinlock<25,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x100402820`
- end: `0x10040290e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100401b20`
- `0x100401e80`
- `0x100402080`
- `0x100402920`
- `0x100402990`
- `0x100402a10`
- `0x10040d680`
- `0x10041d520`

## callees

- `0x100402820`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004028c0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004028c0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004028af`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100402890`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100402890`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004028a5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004028a5`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004028e4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004028e4`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004028fd`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004028fd`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100402880`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100402880`
- `sqldk!SystemThread_TlsIndex` at `0x100402835`
- `sqldk!SystemThread_TlsOffset` at `0x10040283e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040286f`

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
0x100402820  mov     [rsp+arg_0], rbx
0x100402825  push    rdi
0x100402826  sub     rsp, 20h
0x10040282a  mov     rdx, gs:58h
0x100402833  xor     edi, edi
0x100402835  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040283c  mov     ecx, [rax]
0x10040283e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100402845  mov     r8d, [rax]
0x100402848  add     r8, [rdx+rcx*8]
0x10040284c  jz      short loc_10040286C
0x10040284e  cmp     [r8+110h], r8
0x100402855  jnz     short loc_10040286C
0x100402857  mov     rbx, [r8+100h]
0x10040285e  test    rbx, rbx
0x100402861  jz      short loc_10040286C
0x100402863  mov     rbx, [rbx+3E0h]
0x10040286a  jmp     short loc_10040286F
0x10040286c  mov     rbx, rdi
0x10040286f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100402876  test    byte ptr [rax], 1
0x100402879  jz      short loc_100402899
0x10040287b  test    rbx, rbx
0x10040287e  jz      short loc_100402899
0x100402880  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100402886  movzx   edx, word ptr [rbx+0A0h]
0x10040288d  mov     rcx, rax
0x100402890  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100402896  mov     rdi, rax
0x100402899  mov     edx, 19h
0x10040289e  mov     rcx, rdi
0x1004028a1  lea     r8d, [rdx-18h]
0x1004028a5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x1004028ab  test    al, al
0x1004028ad  jnz     short loc_100402903
0x1004028af  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004028b6  cmp     dword ptr [rcx], 0
0x1004028b9  jz      short loc_1004028CD
0x1004028bb  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x1004028c0  call    cs:__imp_QueryPerformanceCounter
0x1004028c6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x1004028cb  jmp     short loc_1004028D5
0x1004028cd  mov     rbx, ds:7FFE0008h
0x1004028d5  mov     edx, 19h
0x1004028da  mov     r9, rbx
0x1004028dd  mov     rcx, rdi
0x1004028e0  lea     r8d, [rdx-18h]
0x1004028e4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004028ea  test    al, al
0x1004028ec  jz      short loc_100402903
0x1004028ee  mov     edx, 19h
0x1004028f3  mov     r9, rbx
0x1004028f6  mov     rcx, rdi
0x1004028f9  lea     r8d, [rdx-18h]
0x1004028fd  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100402903  mov     rbx, [rsp+28h+arg_0]
0x100402908  add     rsp, 20h
0x10040290c  pop     rdi
0x10040290d  retn
```
