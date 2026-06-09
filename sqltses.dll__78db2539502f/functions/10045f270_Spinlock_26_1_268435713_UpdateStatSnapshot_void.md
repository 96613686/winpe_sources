# Spinlock<26,1,268435713>::UpdateStatSnapshot(void)

- ea: `0x10045f270`
- end: `0x10045f35e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BK@$00$0BAAAABAB@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10045e890`
- `0x10045eb60`
- `0x10045ef60`
- `0x10045f1f0`
- `0x10045f370`

## callees

- `0x10045f270`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10045f310`
- `KERNEL32!QueryPerformanceCounter` at `0x10045f310`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10045f2bf`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10045f2ff`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f2f5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10045f2f5`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10045f334`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10045f334`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10045f34d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10045f34d`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10045f2d0`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10045f2d0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10045f2e0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10045f2e0`
- `sqldk!SystemThread_TlsIndex` at `0x10045f285`
- `sqldk!SystemThread_TlsOffset` at `0x10045f28e`

## pseudocode

```c
__int64 Spinlock<26,1,268435713>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 26, 1);
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
               26,
               1,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               26,
               1,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x10045f270  mov     [rsp+arg_0], rbx
0x10045f275  push    rdi
0x10045f276  sub     rsp, 20h
0x10045f27a  mov     rdx, gs:58h
0x10045f283  xor     edi, edi
0x10045f285  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10045f28c  mov     ecx, [rax]
0x10045f28e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045f295  mov     r8d, [rax]
0x10045f298  add     r8, [rdx+rcx*8]
0x10045f29c  jz      short loc_10045F2BC
0x10045f29e  cmp     [r8+110h], r8
0x10045f2a5  jnz     short loc_10045F2BC
0x10045f2a7  mov     rbx, [r8+100h]
0x10045f2ae  test    rbx, rbx
0x10045f2b1  jz      short loc_10045F2BC
0x10045f2b3  mov     rbx, [rbx+3E0h]
0x10045f2ba  jmp     short loc_10045F2BF
0x10045f2bc  mov     rbx, rdi
0x10045f2bf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10045f2c6  test    byte ptr [rax], 1
0x10045f2c9  jz      short loc_10045F2E9
0x10045f2cb  test    rbx, rbx
0x10045f2ce  jz      short loc_10045F2E9
0x10045f2d0  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10045f2d6  movzx   edx, word ptr [rbx+0A0h]
0x10045f2dd  mov     rcx, rax
0x10045f2e0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10045f2e6  mov     rdi, rax
0x10045f2e9  mov     edx, 1Ah
0x10045f2ee  mov     rcx, rdi
0x10045f2f1  lea     r8d, [rdx-19h]
0x10045f2f5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10045f2fb  test    al, al
0x10045f2fd  jnz     short loc_10045F353
0x10045f2ff  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10045f306  cmp     dword ptr [rcx], 0
0x10045f309  jz      short loc_10045F31D
0x10045f30b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10045f310  call    cs:__imp_QueryPerformanceCounter
0x10045f316  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10045f31b  jmp     short loc_10045F325
0x10045f31d  mov     rbx, ds:7FFE0008h
0x10045f325  mov     edx, 1Ah
0x10045f32a  mov     r9, rbx
0x10045f32d  mov     rcx, rdi
0x10045f330  lea     r8d, [rdx-19h]
0x10045f334  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10045f33a  test    al, al
0x10045f33c  jz      short loc_10045F353
0x10045f33e  mov     edx, 1Ah
0x10045f343  mov     r9, rbx
0x10045f346  mov     rcx, rdi
0x10045f349  lea     r8d, [rdx-19h]
0x10045f34d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10045f353  mov     rbx, [rsp+28h+arg_0]
0x10045f358  add     rsp, 20h
0x10045f35c  pop     rdi
0x10045f35d  retn
```
