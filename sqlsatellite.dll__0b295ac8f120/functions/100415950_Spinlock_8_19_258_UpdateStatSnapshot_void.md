# Spinlock<8,19,258>::UpdateStatSnapshot(void)

- ea: `0x100415950`
- end: `0x100415a3e`
- name: `?UpdateStatSnapshot@?$Spinlock@$07$0BD@$0BAC@@@AEAAXXZ`
- size: `238`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x100412320`
- `0x100412790`
- `0x100413220`
- `0x100415880`
- `0x1004700c0`
- `0x100470280`
- `0x100471430`
- `0x100471880`
- `0x100472d40`
- `0x100472f00`
- `0x100474660`
- `0x100475fd0`

## callees

- `0x100415950`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004159f0`
- `KERNEL32!QueryPerformanceCounter` at `0x1004159f0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004159df`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004159c0`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004159c0`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004159d5`
- `sqldk!?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z` at `0x1004159d5`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100415a14`
- `sqldk!?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100415a14`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100415a2d`
- `sqldk!?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100415a2d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004159b0`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004159b0`
- `sqldk!SystemThread_TlsIndex` at `0x100415965`
- `sqldk!SystemThread_TlsOffset` at `0x10041596e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10041599f`

## pseudocode

```c
__int64 Spinlock<8,19,258>::UpdateStatSnapshot()
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
  result = SpinlockStat::IsProfiled(SpinlockStats, 8, 3);
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
               8,
               3,
               (LARGE_INTEGER)v6.QuadPart);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))SpinlockStat::UpdateSnapshot)(
               SpinlockStats,
               8,
               3,
               (LARGE_INTEGER)v6.QuadPart);
  }
  return result;
}

```

## disassembly

```asm
0x100415950  mov     [rsp+arg_0], rbx
0x100415955  push    rdi
0x100415956  sub     rsp, 20h
0x10041595a  mov     rdx, gs:58h
0x100415963  xor     edi, edi
0x100415965  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10041596c  mov     ecx, [rax]
0x10041596e  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100415975  mov     r8d, [rax]
0x100415978  add     r8, [rdx+rcx*8]
0x10041597c  jz      short loc_10041599C
0x10041597e  cmp     [r8+110h], r8
0x100415985  jnz     short loc_10041599C
0x100415987  mov     rbx, [r8+100h]
0x10041598e  test    rbx, rbx
0x100415991  jz      short loc_10041599C
0x100415993  mov     rbx, [rbx+3E0h]
0x10041599a  jmp     short loc_10041599F
0x10041599c  mov     rbx, rdi
0x10041599f  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1004159a6  test    byte ptr [rax], 1
0x1004159a9  jz      short loc_1004159C9
0x1004159ab  test    rbx, rbx
0x1004159ae  jz      short loc_1004159C9
0x1004159b0  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x1004159b6  movzx   edx, word ptr [rbx+0A0h]
0x1004159bd  mov     rcx, rax
0x1004159c0  call    cs:__imp_?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z; PerProcessGlobals::GetSpinlockStats(ushort)
0x1004159c6  mov     rdi, rax
0x1004159c9  mov     edx, 8
0x1004159ce  mov     rcx, rdi
0x1004159d1  lea     r8d, [rdx-5]
0x1004159d5  call    cs:__imp_?IsProfiled@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@@Z; SpinlockStat::IsProfiled(ushort,SPINLOCK_CATEGORY)
0x1004159db  test    al, al
0x1004159dd  jnz     short loc_100415A33
0x1004159df  mov     rcx, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1004159e6  cmp     dword ptr [rcx], 0
0x1004159e9  jz      short loc_1004159FD
0x1004159eb  lea     rcx, [rsp+28h+PerformanceCount]; lpPerformanceCount
0x1004159f0  call    cs:__imp_QueryPerformanceCounter
0x1004159f6  mov     rbx, qword ptr [rsp+28h+PerformanceCount]
0x1004159fb  jmp     short loc_100415A05
0x1004159fd  mov     rbx, ds:7FFE0008h
0x100415a05  mov     edx, 8
0x100415a0a  mov     r9, rbx
0x100415a0d  mov     rcx, rdi
0x100415a10  lea     r8d, [rdx-5]
0x100415a14  call    cs:__imp_?ShouldUpdateSnapshot@SpinlockStat@@QEBA_NGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::ShouldUpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100415a1a  test    al, al
0x100415a1c  jz      short loc_100415A33
0x100415a1e  mov     edx, 8
0x100415a23  mov     r9, rbx
0x100415a26  mov     rcx, rdi
0x100415a29  lea     r8d, [rdx-5]
0x100415a2d  call    cs:__imp_?UpdateSnapshot@SpinlockStat@@QEAAXGW4SPINLOCK_CATEGORY@@V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z; SpinlockStat::UpdateSnapshot(ushort,SPINLOCK_CATEGORY,SOS_Ticks<InterruptTicks<unsigned __int64>,-3>)
0x100415a33  mov     rbx, [rsp+28h+arg_0]
0x100415a38  add     rsp, 20h
0x100415a3c  pop     rdi
0x100415a3d  retn
```
