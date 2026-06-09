# VhdmpiActivateIoTracking

- ea: `0x14002fb1c`
- end: `0x14002fc48`
- name: `VhdmpiActivateIoTracking`
- size: `300`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400197f4`
- `0x14001e3b8`
- `0x140049b60`
- `0x1400b1274`
- `0x1400b4950`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x14002fb1c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fbed`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002fbed`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fb93`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002fb93`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002fb5a`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002fb5a`
- `ntoskrnl!KfRaiseIrql` at `0x14002fb6b`
- `ntoskrnl!KfRaiseIrql` at `0x14002fb6b`
- `ntoskrnl!KeLowerIrql` at `0x14002fc03`
- `ntoskrnl!KeLowerIrql` at `0x14002fc03`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002fc12`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002fc12`
- `ntoskrnl!ExRundownCompleted` at `0x14002fc21`
- `ntoskrnl!ExRundownCompleted` at `0x14002fc21`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002fbc8`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14002fbc8`

## pseudocode

```c
__int64 __fastcall VhdmpiActivateIoTracking(PEX_RUNDOWN_REF RunRef, __int64 a2, __int64 a3)
{
  ULONG MaximumProcessorCount; // r15d
  __int64 v5; // rsi
  KIRQL i; // r12
  __int64 v7; // r14
  char *v8; // rcx
  char *v9; // rax
  char *v10; // rdi

  VhdmpiAcquirePassiveLock(&RunRef[1], a2, a3);
  if ( _InterlockedIncrement((volatile signed __int32 *)&RunRef[3]) == 1 )
  {
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v5 = 0;
    for ( i = KfRaiseIrql(2u); (unsigned int)v5 < MaximumProcessorCount; v5 = (unsigned int)(v5 + 1) )
    {
      v7 = 192 * v5;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)VhdPerProcData + 24 * v5);
      v8 = (char *)VhdPerProcData;
      v9 = (char *)VhdPerProcData + 192 * v5 + 24;
      v10 = *(char **)v9;
      while ( v10 != v9 )
      {
        if ( *((PEX_RUNDOWN_REF *)v10 - 46) == &RunRef[-48] && *((_DWORD *)v10 - 6) != 6 )
        {
          *(v10 - 15) = 1;
          ExAcquireRundownProtection(RunRef);
        }
        v8 = (char *)VhdPerProcData;
        v10 = *(char **)v10;
        v9 = (char *)VhdPerProcData + v7 + 24;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v8[v7]);
    }
    KeLowerIrql(i);
    ExWaitForRundownProtectionRelease(RunRef);
    ExRundownCompleted(RunRef);
  }
  return VhdmpiReleasePassiveLock(&RunRef[1]);
}

```

## disassembly

```asm
0x14002fb1c  push    rbx
0x14002fb1e  push    rbp
0x14002fb1f  push    rsi
0x14002fb20  push    rdi
0x14002fb21  push    r12
0x14002fb23  push    r13
0x14002fb25  push    r14
0x14002fb27  push    r15
0x14002fb29  sub     rsp, 28h
0x14002fb2d  mov     rbx, rcx
0x14002fb30  add     rcx, 8
0x14002fb34  call    VhdmpiAcquirePassiveLock
0x14002fb39  mov     eax, 1
0x14002fb3e  lock xadd [rbx+18h], eax
0x14002fb43  inc     eax
0x14002fb45  cmp     eax, 1
0x14002fb48  jnz     loc_14002FC2D
0x14002fb4e  mov     ecx, 0FFFFh; GroupNumber
0x14002fb53  lea     r13, [rbx-180h]
0x14002fb5a  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14002fb61  nop     dword ptr [rax+rax+00h]
0x14002fb66  mov     cl, 2; NewIrql
0x14002fb68  mov     r15d, eax
0x14002fb6b  call    cs:__imp_KfRaiseIrql
0x14002fb72  nop     dword ptr [rax+rax+00h]
0x14002fb77  xor     esi, esi
0x14002fb79  mov     r12b, al
0x14002fb7c  test    r15d, r15d
0x14002fb7f  jz      short loc_14002FC00
0x14002fb81  mov     rcx, cs:VhdPerProcData
0x14002fb88  lea     r14, [rsi+rsi*2]
0x14002fb8c  shl     r14, 6
0x14002fb90  add     rcx, r14; SpinLock
0x14002fb93  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002fb9a  nop     dword ptr [rax+rax+00h]
0x14002fb9f  mov     rcx, cs:VhdPerProcData
0x14002fba6  lea     rax, [rcx+18h]
0x14002fbaa  add     rax, r14
0x14002fbad  mov     rdi, [rax]
0x14002fbb0  jmp     short loc_14002FBE5
0x14002fbb2  cmp     [rdi-170h], r13
0x14002fbb9  jnz     short loc_14002FBD4
0x14002fbbb  cmp     dword ptr [rdi-18h], 6
0x14002fbbf  jz      short loc_14002FBD4
0x14002fbc1  mov     rcx, rbx; RunRef
0x14002fbc4  mov     byte ptr [rdi-0Fh], 1
0x14002fbc8  call    cs:__imp_ExAcquireRundownProtection
0x14002fbcf  nop     dword ptr [rax+rax+00h]
0x14002fbd4  mov     rcx, cs:VhdPerProcData
0x14002fbdb  mov     rdi, [rdi]
0x14002fbde  lea     rax, [rcx+18h]
0x14002fbe2  add     rax, r14
0x14002fbe5  cmp     rdi, rax
0x14002fbe8  jnz     short loc_14002FBB2
0x14002fbea  add     rcx, r14; SpinLock
0x14002fbed  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002fbf4  nop     dword ptr [rax+rax+00h]
0x14002fbf9  inc     esi
0x14002fbfb  cmp     esi, r15d
0x14002fbfe  jb      short loc_14002FB81
0x14002fc00  mov     cl, r12b; NewIrql
0x14002fc03  call    cs:__imp_KeLowerIrql
0x14002fc0a  nop     dword ptr [rax+rax+00h]
0x14002fc0f  mov     rcx, rbx; RunRef
0x14002fc12  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002fc19  nop     dword ptr [rax+rax+00h]
0x14002fc1e  mov     rcx, rbx; RunRef
0x14002fc21  call    cs:__imp_ExRundownCompleted
0x14002fc28  nop     dword ptr [rax+rax+00h]
0x14002fc2d  lea     rcx, [rbx+8]
0x14002fc31  call    VhdmpiReleasePassiveLock
0x14002fc36  add     rsp, 28h
0x14002fc3a  pop     r15
0x14002fc3c  pop     r14
0x14002fc3e  pop     r13
0x14002fc40  pop     r12
0x14002fc42  pop     rdi
0x14002fc43  pop     rsi
0x14002fc44  pop     rbp
0x14002fc45  pop     rbx
0x14002fc46  retn
```
