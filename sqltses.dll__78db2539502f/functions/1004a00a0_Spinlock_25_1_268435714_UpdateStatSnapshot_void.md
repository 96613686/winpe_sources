# Spinlock<25,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x1004a00a0`
- end: `0x1004a018e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10049fb80`

## callees

- `0x1004a00a0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004a0140`
- `KERNEL32!QueryPerformanceCounter` at `0x1004a0140`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004a00ef`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004a012f`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004a0125`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004a0125`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004a0164`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004a0164`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004a017d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x1004a017d`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a0100`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004a0100`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004a0110`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004a0110`
- `sqldk!SystemThread_TlsIndex` at `0x1004a00b5`
- `sqldk!SystemThread_TlsOffset` at `0x1004a00be`

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
0x1004a00a0  mov     [rsp+arg_0], rbx
0x1004a00a5  push    rdi
0x1004a00a6  sub     rsp, 20h
0x1004a00aa  mov     rdx, gs:58h
0x1004a00b3  xor     edi, edi
0x1004a00b5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004a00bc  mov     ecx, [rax]
0x1004a00be  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004a00c5  mov     r8d, [rax]
0x1004a00c8  add     r8, [rdx+rcx*8]
0x1004a00cc  jz      short loc_1004A00EC
0x1004a00ce  cmp     [r8+110h], r8
0x1004a00d5  jnz     short loc_1004A00EC
0x1004a00d7  mov     rbx, [r8+100h]
0x1004a00de  test    rbx, rbx
0x1004a00e1  jz      short loc_1004A00EC
0x1004a00e3  mov     rbx, [rbx+3E0h]
0x1004a00ea  jmp     short loc_1004A00EF
0x1004a00ec  mov     rbx, rdi
0x1004a00ef  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004a00f6  test    byte ptr [rax], 1
0x1004a00f9  jz      short loc_1004A0119
0x1004a00fb  test    rbx, rbx
0x1004a00fe  jz      short loc_1004A0119
0x1004a0100  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x1004a0106  movzx   edx, word ptr [rbx+0A0h]
0x1004a010d  mov     rcx, rax
0x1004a0110  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004a0116  mov     rdi, rax
0x1004a0119  mov     edx, 19h
0x1004a011e  mov     rcx, rdi
0x1004a0121  lea     r8d, [rdx-18h]
0x1004a0125  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x1004a012b  test    al, al
0x1004a012d  jnz     short loc_1004A0183
0x1004a012f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004a0136  cmp     dword ptr [rcx], 0
0x1004a0139  jz      short loc_1004A014D
0x1004a013b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x1004a0140  call    cs:__imp_QueryPerformanceCounter
0x1004a0146  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x1004a014b  jmp     short loc_1004A0155
0x1004a014d  mov     rbx, ds:7FFE0008h
0x1004a0155  mov     edx, 19h
0x1004a015a  mov     r9, rbx
0x1004a015d  mov     rcx, rdi
0x1004a0160  lea     r8d, [rdx-18h]
0x1004a0164  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a016a  test    al, al
0x1004a016c  jz      short loc_1004A0183
0x1004a016e  mov     edx, 19h
0x1004a0173  mov     r9, rbx
0x1004a0176  mov     rcx, rdi
0x1004a0179  lea     r8d, [rdx-18h]
0x1004a017d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x1004a0183  mov     rbx, [rsp+28h+arg_0]
0x1004a0188  add     rsp, 20h
0x1004a018c  pop     rdi
0x1004a018d  retn
```
