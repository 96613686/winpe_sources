# Spinlock<250,3,258>::UpdateStatSnapshot(void)

- ea: `0x100429580`
- end: `0x100429674`
- name: `?UpdateStatSnapshot@?$Spinlock@$0PK@$02$0BAC@@@AEAAXXZ`
- size: `244`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100422190`
- `0x100423750`
- `0x100423a60`
- `0x1004294e0`

## callees

- `0x100429580`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100429622`
- `KERNEL32!QueryPerformanceCounter` at `0x100429622`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100429611`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004295f0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004295f0`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100429607`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x100429607`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100429648`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100429648`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100429663`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100429663`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004295e0`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004295e0`
- `sqldk!SystemThread_TlsIndex` at `0x100429595`
- `sqldk!SystemThread_TlsOffset` at `0x10042959e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004295cf`

## pseudocode

```c
__int64 Spinlock<250,3,258>::UpdateStatSnapshot()
{
  struct SpinlockStat *SpinlockStats; // rdi
  __int64 v1; // r8
  __int64 v2; // rbx
  __int64 v3; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
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
    ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    SpinlockStats = PerProcessGlobals::GetSpinlockStats(ClientProcessGlobals, *(_WORD *)(v3 + 160));
  }
  result = SpinlockStat::IsProfiled(SpinlockStats, 250, 3);
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
               250,
               3,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               250,
               3,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x100429580  mov     [rsp+arg_0], rbx
0x100429585  push    rdi
0x100429586  sub     rsp, 20h
0x10042958a  mov     rdx, gs:58h
0x100429593  xor     edi, edi
0x100429595  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10042959c  mov     ecx, [rax]
0x10042959e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1004295a5  mov     r8d, [rax]
0x1004295a8  add     r8, [rdx+rcx*8]
0x1004295ac  jz      short loc_1004295CC
0x1004295ae  cmp     [r8+110h], r8
0x1004295b5  jnz     short loc_1004295CC
0x1004295b7  mov     rbx, [r8+100h]
0x1004295be  test    rbx, rbx
0x1004295c1  jz      short loc_1004295CC
0x1004295c3  mov     rbx, [rbx+3E0h]
0x1004295ca  jmp     short loc_1004295CF
0x1004295cc  mov     rbx, rdi
0x1004295cf  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004295d6  test    byte ptr [rax], 1
0x1004295d9  jz      short loc_1004295F9
0x1004295db  test    rbx, rbx
0x1004295de  jz      short loc_1004295F9
0x1004295e0  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1004295e6  movzx   edx, word ptr [rbx+0A0h]
0x1004295ed  mov     rcx, rax
0x1004295f0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004295f6  mov     rdi, rax
0x1004295f9  mov     edx, 0FAh
0x1004295fe  mov     r8d, 3
0x100429604  mov     rcx, rdi
0x100429607  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x10042960d  test    al, al
0x10042960f  jnz     short loc_100429669
0x100429611  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x100429618  cmp     dword ptr [rcx], 0
0x10042961b  jz      short loc_10042962F
0x10042961d  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x100429622  call    cs:__imp_QueryPerformanceCounter
0x100429628  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x10042962d  jmp     short loc_100429637
0x10042962f  mov     rbx, ds:7FFE0008h
0x100429637  mov     edx, 0FAh
0x10042963c  mov     r9, rbx
0x10042963f  mov     r8d, 3
0x100429645  mov     rcx, rdi
0x100429648  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x10042964e  test    al, al
0x100429650  jz      short loc_100429669
0x100429652  mov     edx, 0FAh
0x100429657  mov     r9, rbx
0x10042965a  mov     r8d, 3
0x100429660  mov     rcx, rdi
0x100429663  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100429669  mov     rbx, [rsp+28h+arg_0]
0x10042966e  add     rsp, 20h
0x100429672  pop     rdi
0x100429673  retn
```
