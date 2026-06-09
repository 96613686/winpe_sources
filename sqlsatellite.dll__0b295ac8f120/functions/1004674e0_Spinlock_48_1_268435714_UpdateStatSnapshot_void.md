# Spinlock<48,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x1004674e0`
- end: `0x1004675ce`
- name: `?UpdateStatSnapshot@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100466b20`
- `0x1004673f0`
- `0x100467470`

## callees

- `0x1004674e0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100467580`
- `KERNEL32!QueryPerformanceCounter` at `0x100467580`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10046756f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100467550`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100467550`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100467565`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100467565`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004675a4`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004675a4`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004675bd`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004675bd`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100467540`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100467540`
- `sqldk!SystemThread_TlsIndex` at `0x1004674f5`
- `sqldk!SystemThread_TlsOffset` at `0x1004674fe`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10046752f`

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
0x1004674e0  mov     [rsp+arg_0], rbx
0x1004674e5  push    rdi
0x1004674e6  sub     rsp, 20h
0x1004674ea  mov     rdx, gs:58h
0x1004674f3  xor     edi, edi
0x1004674f5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004674fc  mov     ecx, [rax]
0x1004674fe  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100467505  mov     r8d, [rax]
0x100467508  add     r8, [rdx+rcx*8]
0x10046750c  jz      short loc_10046752C
0x10046750e  cmp     [r8+110h], r8
0x100467515  jnz     short loc_10046752C
0x100467517  mov     rbx, [r8+100h]
0x10046751e  test    rbx, rbx
0x100467521  jz      short loc_10046752C
0x100467523  mov     rbx, [rbx+3E0h]
0x10046752a  jmp     short loc_10046752F
0x10046752c  mov     rbx, rdi
0x10046752f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x100467536  test    byte ptr [rax], 1
0x100467539  jz      short loc_100467559
0x10046753b  test    rbx, rbx
0x10046753e  jz      short loc_100467559
0x100467540  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x100467546  movzx   edx, word ptr [rbx+0A0h]
0x10046754d  mov     rcx, rax
0x100467550  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x100467556  mov     rdi, rax
0x100467559  mov     edx, 30h ; '0'
0x10046755e  mov     rcx, rdi
0x100467561  lea     r8d, [rdx-2Fh]
0x100467565  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10046756b  test    al, al
0x10046756d  jnz     short loc_1004675C3
0x10046756f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100467576  cmp     dword ptr [rcx], 0
0x100467579  jz      short loc_10046758D
0x10046757b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x100467580  call    cs:__imp_QueryPerformanceCounter
0x100467586  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10046758b  jmp     short loc_100467595
0x10046758d  mov     rbx, ds:7FFE0008h
0x100467595  mov     edx, 30h ; '0'
0x10046759a  mov     r9, rbx
0x10046759d  mov     rcx, rdi
0x1004675a0  lea     r8d, [rdx-2Fh]
0x1004675a4  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004675aa  test    al, al
0x1004675ac  jz      short loc_1004675C3
0x1004675ae  mov     edx, 30h ; '0'
0x1004675b3  mov     r9, rbx
0x1004675b6  mov     rcx, rdi
0x1004675b9  lea     r8d, [rdx-2Fh]
0x1004675bd  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004675c3  mov     rbx, [rsp+28h+arg_0]
0x1004675c8  add     rsp, 20h
0x1004675cc  pop     rdi
0x1004675cd  retn
```
