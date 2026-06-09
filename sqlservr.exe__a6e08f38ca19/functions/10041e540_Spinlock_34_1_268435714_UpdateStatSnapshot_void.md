# Spinlock<34,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x10041e540`
- end: `0x10041e62e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100412470`
- `0x100416770`
- `0x10041d870`
- `0x100435700`
- `0x1004369a0`
- `0x10043f6a0`

## callees

- `0x10041e540`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10041e5e0`
- `KERNEL32!QueryPerformanceCounter` at `0x10041e5e0`
- `sqldk!SystemThread_TlsOffset` at `0x10041e55e`
- `sqldk!SystemThread_TlsIndex` at `0x10041e555`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041e5a0`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10041e5a0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e5b0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10041e5b0`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10041e604`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10041e604`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e5c5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10041e5c5`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10041e61d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10041e61d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10041e5cf`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041e58f`

## pseudocode

```c
__int64 Spinlock<34,1,268435714>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 34, 1);
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
               34,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               34,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x10041e540  mov     [rsp+arg_0], rbx
0x10041e545  push    rdi
0x10041e546  sub     rsp, 20h
0x10041e54a  mov     rdx, gs:58h
0x10041e553  xor     edi, edi
0x10041e555  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041e55c  mov     ecx, [rax]
0x10041e55e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041e565  mov     r8d, [rax]
0x10041e568  add     r8, [rdx+rcx*8]
0x10041e56c  jz      short loc_10041E58C
0x10041e56e  cmp     [r8+110h], r8
0x10041e575  jnz     short loc_10041E58C
0x10041e577  mov     rbx, [r8+100h]
0x10041e57e  test    rbx, rbx
0x10041e581  jz      short loc_10041E58C
0x10041e583  mov     rbx, [rbx+3E0h]
0x10041e58a  jmp     short loc_10041E58F
0x10041e58c  mov     rbx, rdi
0x10041e58f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10041e596  test    byte ptr [rax], 1
0x10041e599  jz      short loc_10041E5B9
0x10041e59b  test    rbx, rbx
0x10041e59e  jz      short loc_10041E5B9
0x10041e5a0  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10041e5a6  movzx   edx, word ptr [rbx+0A0h]
0x10041e5ad  mov     rcx, rax
0x10041e5b0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10041e5b6  mov     rdi, rax
0x10041e5b9  mov     edx, 22h ; '"'
0x10041e5be  mov     rcx, rdi
0x10041e5c1  lea     r8d, [rdx-21h]
0x10041e5c5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10041e5cb  test    al, al
0x10041e5cd  jnz     short loc_10041E623
0x10041e5cf  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10041e5d6  cmp     dword ptr [rcx], 0
0x10041e5d9  jz      short loc_10041E5ED
0x10041e5db  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10041e5e0  call    cs:__imp_QueryPerformanceCounter
0x10041e5e6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10041e5eb  jmp     short loc_10041E5F5
0x10041e5ed  mov     rbx, ds:7FFE0008h
0x10041e5f5  mov     edx, 22h ; '"'
0x10041e5fa  mov     r9, rbx
0x10041e5fd  mov     rcx, rdi
0x10041e600  lea     r8d, [rdx-21h]
0x10041e604  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10041e60a  test    al, al
0x10041e60c  jz      short loc_10041E623
0x10041e60e  mov     edx, 22h ; '"'
0x10041e613  mov     r9, rbx
0x10041e616  mov     rcx, rdi
0x10041e619  lea     r8d, [rdx-21h]
0x10041e61d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10041e623  mov     rbx, [rsp+28h+arg_0]
0x10041e628  add     rsp, 20h
0x10041e62c  pop     rdi
0x10041e62d  retn
```
