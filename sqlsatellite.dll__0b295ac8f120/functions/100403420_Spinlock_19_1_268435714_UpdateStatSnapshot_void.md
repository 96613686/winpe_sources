# Spinlock<19,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x100403420`
- end: `0x10040350e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BD@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100403270`
- `0x10040bbb0`
- `0x10040bf30`
- `0x10041d070`
- `0x100421ca0`
- `0x100421e80`
- `0x1004740e0`
- `0x100475c00`
- `0x100476ab0`
- `0x100477010`
- `0x1004771f0`
- `0x1004773d0`
- `0x1004775a0`

## callees

- `0x100403420`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004034c0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004034c0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004034af`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100403490`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100403490`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004034a5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004034a5`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004034e4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004034e4`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004034fd`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004034fd`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100403480`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100403480`
- `sqldk!SystemThread_TlsIndex` at `0x100403435`
- `sqldk!SystemThread_TlsOffset` at `0x10040343e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040346f`

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
0x100403420  mov     [rsp+arg_0], rbx
0x100403425  push    rdi
0x100403426  sub     rsp, 20h
0x10040342a  mov     rdx, gs:58h
0x100403433  xor     edi, edi
0x100403435  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040343c  mov     ecx, [rax]
0x10040343e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100403445  mov     r8d, [rax]
0x100403448  add     r8, [rdx+rcx*8]
0x10040344c  jz      short loc_10040346C
0x10040344e  cmp     [r8+110h], r8
0x100403455  jnz     short loc_10040346C
0x100403457  mov     rbx, [r8+100h]
0x10040345e  test    rbx, rbx
0x100403461  jz      short loc_10040346C
0x100403463  mov     rbx, [rbx+3E0h]
0x10040346a  jmp     short loc_10040346F
0x10040346c  mov     rbx, rdi
0x10040346f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100403476  test    byte ptr [rax], 1
0x100403479  jz      short loc_100403499
0x10040347b  test    rbx, rbx
0x10040347e  jz      short loc_100403499
0x100403480  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100403486  movzx   edx, word ptr [rbx+0A0h]
0x10040348d  mov     rcx, rax
0x100403490  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100403496  mov     rdi, rax
0x100403499  mov     edx, 13h
0x10040349e  mov     rcx, rdi
0x1004034a1  lea     r8d, [rdx-12h]
0x1004034a5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x1004034ab  test    al, al
0x1004034ad  jnz     short loc_100403503
0x1004034af  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004034b6  cmp     dword ptr [rcx], 0
0x1004034b9  jz      short loc_1004034CD
0x1004034bb  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x1004034c0  call    cs:__imp_QueryPerformanceCounter
0x1004034c6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x1004034cb  jmp     short loc_1004034D5
0x1004034cd  mov     rbx, ds:7FFE0008h
0x1004034d5  mov     edx, 13h
0x1004034da  mov     r9, rbx
0x1004034dd  mov     rcx, rdi
0x1004034e0  lea     r8d, [rdx-12h]
0x1004034e4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004034ea  test    al, al
0x1004034ec  jz      short loc_100403503
0x1004034ee  mov     edx, 13h
0x1004034f3  mov     r9, rbx
0x1004034f6  mov     rcx, rdi
0x1004034f9  lea     r8d, [rdx-12h]
0x1004034fd  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100403503  mov     rbx, [rsp+28h+arg_0]
0x100403508  add     rsp, 20h
0x10040350c  pop     rdi
0x10040350d  retn
```
