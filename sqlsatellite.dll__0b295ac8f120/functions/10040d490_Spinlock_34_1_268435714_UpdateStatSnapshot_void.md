# Spinlock<34,1,268435714>::UpdateStatSnapshot(void)

- ea: `0x10040d490`
- end: `0x10040d57e`
- name: `?UpdateStatSnapshot@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100409790`
- `0x10040af40`
- `0x10040c0e0`
- `0x10041de00`
- `0x10041e0a0`
- `0x100446b10`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x10040d490`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10040d530`
- `KERNEL32!QueryPerformanceCounter` at `0x10040d530`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040d51f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040d500`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040d500`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d515`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d515`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040d554`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040d554`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040d56d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x10040d56d`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d4f0`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d4f0`
- `sqldk!SystemThread_TlsIndex` at `0x10040d4a5`
- `sqldk!SystemThread_TlsOffset` at `0x10040d4ae`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040d4df`

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
0x10040d490  mov     [rsp+arg_0], rbx
0x10040d495  push    rdi
0x10040d496  sub     rsp, 20h
0x10040d49a  mov     rdx, gs:58h
0x10040d4a3  xor     edi, edi
0x10040d4a5  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040d4ac  mov     ecx, [rax]
0x10040d4ae  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040d4b5  mov     r8d, [rax]
0x10040d4b8  add     r8, [rdx+rcx*8]
0x10040d4bc  jz      short loc_10040D4DC
0x10040d4be  cmp     [r8+110h], r8
0x10040d4c5  jnz     short loc_10040D4DC
0x10040d4c7  mov     rbx, [r8+100h]
0x10040d4ce  test    rbx, rbx
0x10040d4d1  jz      short loc_10040D4DC
0x10040d4d3  mov     rbx, [rbx+3E0h]
0x10040d4da  jmp     short loc_10040D4DF
0x10040d4dc  mov     rbx, rdi
0x10040d4df  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x10040d4e6  test    byte ptr [rax], 1
0x10040d4e9  jz      short loc_10040D509
0x10040d4eb  test    rbx, rbx
0x10040d4ee  jz      short loc_10040D509
0x10040d4f0  call    cs:__imp_?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetSOSProcessGlobals(void)
0x10040d4f6  movzx   edx, word ptr [rbx+0A0h]
0x10040d4fd  mov     rcx, rax
0x10040d500  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x10040d506  mov     rdi, rax
0x10040d509  mov     edx, 22h ; '"'
0x10040d50e  mov     rcx, rdi
0x10040d511  lea     r8d, [rdx-21h]
0x10040d515  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10040d51b  test    al, al
0x10040d51d  jnz     short loc_10040D573
0x10040d51f  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040d526  cmp     dword ptr [rcx], 0
0x10040d529  jz      short loc_10040D53D
0x10040d52b  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x10040d530  call    cs:__imp_QueryPerformanceCounter
0x10040d536  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10040d53b  jmp     short loc_10040D545
0x10040d53d  mov     rbx, ds:7FFE0008h
0x10040d545  mov     edx, 22h ; '"'
0x10040d54a  mov     r9, rbx
0x10040d54d  mov     rcx, rdi
0x10040d550  lea     r8d, [rdx-21h]
0x10040d554  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040d55a  test    al, al
0x10040d55c  jz      short loc_10040D573
0x10040d55e  mov     edx, 22h ; '"'
0x10040d563  mov     r9, rbx
0x10040d566  mov     rcx, rdi
0x10040d569  lea     r8d, [rdx-21h]
0x10040d56d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10040d573  mov     rbx, [rsp+28h+arg_0]
0x10040d578  add     rsp, 20h
0x10040d57c  pop     rdi
0x10040d57d  retn
```
