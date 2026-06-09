# Spinlock<22,1,268435713>::UpdateStatSnapshot(void)

- ea: `0x100477770`
- end: `0x10047785e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BG@$00$0BAAAABAB@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1004748a0`
- `0x100475aa0`
- `0x100476390`
- `0x100476740`
- `0x100476f80`

## callees

- `0x100477770`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100477810`
- `KERNEL32!QueryPerformanceCounter` at `0x100477810`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004777ff`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004777e0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004777e0`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004777f5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004777f5`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100477834`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100477834`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047784d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10047784d`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004777d0`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004777d0`
- `sqldk!SystemThread_TlsIndex` at `0x100477785`
- `sqldk!SystemThread_TlsOffset` at `0x10047778e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004777bf`

## pseudocode

```c
__int64 Spinlock<22,1,268435713>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 22, 1);
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
               22,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               22,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x100477770  mov     [rsp+arg_0], rbx
0x100477775  push    rdi
0x100477776  sub     rsp, 20h
0x10047777a  mov     rdx, gs:58h
0x100477783  xor     edi, edi
0x100477785  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10047778c  mov     ecx, [rax]
0x10047778e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100477795  mov     r8d, [rax]
0x100477798  add     r8, [rdx+rcx*8]
0x10047779c  jz      short loc_1004777BC
0x10047779e  cmp     [r8+110h], r8
0x1004777a5  jnz     short loc_1004777BC
0x1004777a7  mov     rbx, [r8+100h]
0x1004777ae  test    rbx, rbx
0x1004777b1  jz      short loc_1004777BC
0x1004777b3  mov     rbx, [rbx+3E0h]
0x1004777ba  jmp     short loc_1004777BF
0x1004777bc  mov     rbx, rdi
0x1004777bf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004777c6  test    byte ptr [rax], 1
0x1004777c9  jz      short loc_1004777E9
0x1004777cb  test    rbx, rbx
0x1004777ce  jz      short loc_1004777E9
0x1004777d0  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004777d6  movzx   edx, word ptr [rbx+0A0h]
0x1004777dd  mov     rcx, rax
0x1004777e0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004777e6  mov     rdi, rax
0x1004777e9  mov     edx, 16h
0x1004777ee  mov     rcx, rdi
0x1004777f1  lea     r8d, [rdx-15h]
0x1004777f5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x1004777fb  test    al, al
0x1004777fd  jnz     short loc_100477853
0x1004777ff  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100477806  cmp     dword ptr [rcx], 0
0x100477809  jz      short loc_10047781D
0x10047780b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x100477810  call    cs:__imp_QueryPerformanceCounter
0x100477816  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10047781b  jmp     short loc_100477825
0x10047781d  mov     rbx, ds:7FFE0008h
0x100477825  mov     edx, 16h
0x10047782a  mov     r9, rbx
0x10047782d  mov     rcx, rdi
0x100477830  lea     r8d, [rdx-15h]
0x100477834  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10047783a  test    al, al
0x10047783c  jz      short loc_100477853
0x10047783e  mov     edx, 16h
0x100477843  mov     r9, rbx
0x100477846  mov     rcx, rdi
0x100477849  lea     r8d, [rdx-15h]
0x10047784d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100477853  mov     rbx, [rsp+28h+arg_0]
0x100477858  add     rsp, 20h
0x10047785c  pop     rdi
0x10047785d  retn
```
