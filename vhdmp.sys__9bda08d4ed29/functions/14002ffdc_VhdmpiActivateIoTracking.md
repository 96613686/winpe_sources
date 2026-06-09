# VhdmpiActivateIoTracking

- ea: `0x14002ffdc`
- end: `0x140030108`
- name: `VhdmpiActivateIoTracking`
- size: `300`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140019c14`
- `0x14001e7d8`
- `0x140049f50`
- `0x1400b1274`
- `0x1400b4950`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x14002ffdc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400300ad`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400300ad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030053`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140030053`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14003001a`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14003001a`
- `ntoskrnl!KfRaiseIrql` at `0x14003002b`
- `ntoskrnl!KfRaiseIrql` at `0x14003002b`
- `ntoskrnl!KeLowerIrql` at `0x1400300c3`
- `ntoskrnl!KeLowerIrql` at `0x1400300c3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400300d2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400300d2`
- `ntoskrnl!ExRundownCompleted` at `0x1400300e1`
- `ntoskrnl!ExRundownCompleted` at `0x1400300e1`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140030088`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140030088`

## pseudocode

```c
__int64 __fastcall VhdmpiActivateIoTracking(PEX_RUNDOWN_REF RunRef)
{
  ULONG MaximumProcessorCount; // r15d
  __int64 v3; // rsi
  KIRQL i; // r12
  __int64 v5; // r14
  char *v6; // rcx
  char *v7; // rax
  char *v8; // rdi

  VhdmpiAcquirePassiveLock(&RunRef[1]);
  if ( _InterlockedIncrement((volatile signed __int32 *)&RunRef[3]) == 1 )
  {
    MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
    v3 = 0;
    for ( i = KfRaiseIrql(2u); (unsigned int)v3 < MaximumProcessorCount; v3 = (unsigned int)(v3 + 1) )
    {
      v5 = 192 * v3;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)VhdPerProcData + 24 * v3);
      v6 = (char *)VhdPerProcData;
      v7 = (char *)VhdPerProcData + 192 * v3 + 24;
      v8 = *(char **)v7;
      while ( v8 != v7 )
      {
        if ( *((PEX_RUNDOWN_REF *)v8 - 46) == &RunRef[-48] && *((_DWORD *)v8 - 6) != 6 )
        {
          *(v8 - 15) = 1;
          ExAcquireRundownProtection(RunRef);
        }
        v6 = (char *)VhdPerProcData;
        v8 = *(char **)v8;
        v7 = (char *)VhdPerProcData + v5 + 24;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v6[v5]);
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
0x14002ffdc  push    rbx
0x14002ffde  push    rbp
0x14002ffdf  push    rsi
0x14002ffe0  push    rdi
0x14002ffe1  push    r12
0x14002ffe3  push    r13
0x14002ffe5  push    r14
0x14002ffe7  push    r15
0x14002ffe9  sub     rsp, 28h
0x14002ffed  mov     rbx, rcx
0x14002fff0  add     rcx, 8
0x14002fff4  call    VhdmpiAcquirePassiveLock
0x14002fff9  mov     eax, 1
0x14002fffe  lock xadd [rbx+18h], eax
0x140030003  inc     eax
0x140030005  cmp     eax, 1
0x140030008  jnz     loc_1400300ED
0x14003000e  mov     ecx, 0FFFFh; GroupNumber
0x140030013  lea     r13, [rbx-180h]
0x14003001a  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140030021  nop     dword ptr [rax+rax+00h]
0x140030026  mov     cl, 2; NewIrql
0x140030028  mov     r15d, eax
0x14003002b  call    cs:__imp_KfRaiseIrql
0x140030032  nop     dword ptr [rax+rax+00h]
0x140030037  xor     esi, esi
0x140030039  mov     r12b, al
0x14003003c  test    r15d, r15d
0x14003003f  jz      short loc_1400300C0
0x140030041  mov     rcx, cs:VhdPerProcData
0x140030048  lea     r14, [rsi+rsi*2]
0x14003004c  shl     r14, 6
0x140030050  add     rcx, r14; SpinLock
0x140030053  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14003005a  nop     dword ptr [rax+rax+00h]
0x14003005f  mov     rcx, cs:VhdPerProcData
0x140030066  lea     rax, [rcx+18h]
0x14003006a  add     rax, r14
0x14003006d  mov     rdi, [rax]
0x140030070  jmp     short loc_1400300A5
0x140030072  cmp     [rdi-170h], r13
0x140030079  jnz     short loc_140030094
0x14003007b  cmp     dword ptr [rdi-18h], 6
0x14003007f  jz      short loc_140030094
0x140030081  mov     rcx, rbx; RunRef
0x140030084  mov     byte ptr [rdi-0Fh], 1
0x140030088  call    cs:__imp_ExAcquireRundownProtection
0x14003008f  nop     dword ptr [rax+rax+00h]
0x140030094  mov     rcx, cs:VhdPerProcData
0x14003009b  mov     rdi, [rdi]
0x14003009e  lea     rax, [rcx+18h]
0x1400300a2  add     rax, r14
0x1400300a5  cmp     rdi, rax
0x1400300a8  jnz     short loc_140030072
0x1400300aa  add     rcx, r14; SpinLock
0x1400300ad  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400300b4  nop     dword ptr [rax+rax+00h]
0x1400300b9  inc     esi
0x1400300bb  cmp     esi, r15d
0x1400300be  jb      short loc_140030041
0x1400300c0  mov     cl, r12b; NewIrql
0x1400300c3  call    cs:__imp_KeLowerIrql
0x1400300ca  nop     dword ptr [rax+rax+00h]
0x1400300cf  mov     rcx, rbx; RunRef
0x1400300d2  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400300d9  nop     dword ptr [rax+rax+00h]
0x1400300de  mov     rcx, rbx; RunRef
0x1400300e1  call    cs:__imp_ExRundownCompleted
0x1400300e8  nop     dword ptr [rax+rax+00h]
0x1400300ed  lea     rcx, [rbx+8]
0x1400300f1  call    VhdmpiReleasePassiveLock
0x1400300f6  add     rsp, 28h
0x1400300fa  pop     r15
0x1400300fc  pop     r14
0x1400300fe  pop     r13
0x140030100  pop     r12
0x140030102  pop     rdi
0x140030103  pop     rsi
0x140030104  pop     rbp
0x140030105  pop     rbx
0x140030106  retn
```
