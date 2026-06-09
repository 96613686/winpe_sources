# RfspThreadPoolNodeWorkerRun

- ea: `0x140073500`
- end: `0x1400736be`
- name: `RfspThreadPoolNodeWorkerRun`
- size: `446`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140038490`
- `0x140073500`
- `0x1400736d0`

## import_xrefs

- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007353d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073616`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007353d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140073616`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073573`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073646`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073573`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073646`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400735b5`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400735b5`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400736a6`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400736a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007367a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007367a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400735f7`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400735f7`
- `ntoskrnl!KeSetPriorityThread` at `0x140073596`
- `ntoskrnl!KeSetPriorityThread` at `0x140073596`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140073666`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140073666`

## pseudocode

```c
void __fastcall RfspThreadPoolNodeWorkerRun(__int64 *P)
{
  __int64 v2; // rax
  __int64 **v3; // rcx
  SIZE_T v4; // r8
  _QWORD *v5; // rcx
  PVOID *v6; // rax
  struct _GROUP_AFFINITY Affinity; // [rsp+30h] [rbp-28h] BYREF

  Affinity = 0;
  P[3] = (__int64)KeGetCurrentThread();
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(P[2] + 136));
  v2 = P[2] + 120;
  v3 = *(__int64 ***)(P[2] + 128);
  if ( *v3 != (__int64 *)v2 )
    goto LABEL_10;
  P[1] = (__int64)v3;
  *P = v2;
  *v3 = P;
  *(_QWORD *)(v2 + 8) = P;
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(P[2] + 136));
  KeSetPriorityThread(KeGetCurrentThread(), *(_DWORD *)(*(_QWORD *)(P[2] + 216) + 8LL));
  KeQueryNodeActiveAffinity(*(_WORD *)(P[2] + 232), &Affinity, 0);
  if ( Affinity.Mask )
    KeSetSystemGroupAffinityThread(&Affinity, 0);
  v4 = *(_QWORD *)(*(_QWORD *)(P[2] + 216) + 16LL);
  if ( !v4
    || KeExpandKernelStackAndCalloutEx((PEXPAND_STACK_CALLOUT)RfspThreadPoolNodeWorkerProcessWorkItems, P, v4, 0, 0) < 0 )
  {
    RfspThreadPoolNodeWorkerProcessWorkItems(P);
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(P[2] + 136));
  v5 = (_QWORD *)*P;
  if ( *(__int64 **)(*P + 8) != P || (v6 = (PVOID *)P[1], *v6 != P) )
LABEL_10:
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(P[2] + 136));
  _InterlockedDecrement16((volatile signed __int16 *)(P[2] + 64));
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(P[2] + 208));
  ExFreePoolWithTag(P, 0x5266534Cu);
}

```

## disassembly

```asm
0x140073500  mov     [rsp+arg_8], rbx
0x140073505  push    rdi
0x140073506  sub     rsp, 50h
0x14007350a  mov     rax, cs:__security_cookie
0x140073511  xor     rax, rsp
0x140073514  mov     [rsp+58h+var_18], rax
0x140073519  mov     rbx, rcx
0x14007351c  xorps   xmm0, xmm0
0x14007351f  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x140073524  mov     rax, gs:188h
0x14007352d  mov     edi, 88h
0x140073532  mov     [rcx+18h], rax
0x140073536  mov     rcx, [rcx+10h]
0x14007353a  add     rcx, rdi; Mutex
0x14007353d  call    cs:__imp_KeAcquireGuardedMutex
0x140073544  nop     dword ptr [rax+rax+00h]
0x140073549  mov     rax, [rbx+10h]
0x14007354d  add     rax, 78h ; 'x'
0x140073551  mov     rcx, [rax+8]
0x140073555  cmp     [rcx], rax
0x140073558  jnz     loc_1400736B7
0x14007355e  mov     [rbx+8], rcx
0x140073562  mov     [rbx], rax
0x140073565  mov     [rcx], rbx
0x140073568  mov     [rax+8], rbx
0x14007356c  mov     rcx, [rbx+10h]
0x140073570  add     rcx, rdi; Mutex
0x140073573  call    cs:__imp_KeReleaseGuardedMutex
0x14007357a  nop     dword ptr [rax+rax+00h]
0x14007357f  mov     rax, [rbx+10h]
0x140073583  mov     rcx, gs:188h; Thread
0x14007358c  mov     rdx, [rax+0D8h]
0x140073593  mov     edx, [rdx+8]; Priority
0x140073596  call    cs:__imp_KeSetPriorityThread
0x14007359d  nop     dword ptr [rax+rax+00h]
0x1400735a2  mov     rcx, [rbx+10h]
0x1400735a6  lea     rdx, [rsp+58h+Affinity]; Affinity
0x1400735ab  xor     r8d, r8d; Count
0x1400735ae  movzx   ecx, word ptr [rcx+0E8h]; NodeNumber
0x1400735b5  call    cs:__imp_KeQueryNodeActiveAffinity
0x1400735bc  nop     dword ptr [rax+rax+00h]
0x1400735c1  cmp     [rsp+58h+Affinity.Mask], 0
0x1400735c7  jnz     loc_14007369F
0x1400735cd  mov     rax, [rbx+10h]
0x1400735d1  mov     rcx, [rax+0D8h]
0x1400735d8  mov     r8, [rcx+10h]; Size
0x1400735dc  test    r8, r8
0x1400735df  jz      short loc_140073607
0x1400735e1  xor     r9d, r9d; Wait
0x1400735e4  mov     [rsp+58h+Context], 0; Context
0x1400735ed  mov     rdx, rbx; Parameter
0x1400735f0  lea     rcx, RfspThreadPoolNodeWorkerProcessWorkItems; Callout
0x1400735f7  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1400735fe  nop     dword ptr [rax+rax+00h]
0x140073603  test    eax, eax
0x140073605  jns     short loc_14007360F
0x140073607  mov     rcx, rbx; Parameter
0x14007360a  call    RfspThreadPoolNodeWorkerProcessWorkItems
0x14007360f  mov     rcx, [rbx+10h]
0x140073613  add     rcx, rdi; Mutex
0x140073616  call    cs:__imp_KeAcquireGuardedMutex
0x14007361d  nop     dword ptr [rax+rax+00h]
0x140073622  mov     rcx, [rbx]
0x140073625  cmp     [rcx+8], rbx
0x140073629  jnz     loc_1400736B7
0x14007362f  mov     rax, [rbx+8]
0x140073633  cmp     [rax], rbx
0x140073636  jnz     short loc_1400736B7
0x140073638  mov     [rax], rcx
0x14007363b  mov     [rcx+8], rax
0x14007363f  mov     rcx, [rbx+10h]
0x140073643  add     rcx, rdi; Mutex
0x140073646  call    cs:__imp_KeReleaseGuardedMutex
0x14007364d  nop     dword ptr [rax+rax+00h]
0x140073652  mov     rax, [rbx+10h]
0x140073656  lock dec word ptr [rax+40h]
0x14007365b  mov     rcx, [rbx+10h]
0x14007365f  add     rcx, 0D0h; RunRef
0x140073666  call    cs:__imp_ExReleaseRundownProtection
0x14007366d  nop     dword ptr [rax+rax+00h]
0x140073672  mov     edx, 5266534Ch; Tag
0x140073677  mov     rcx, rbx; P
0x14007367a  call    cs:__imp_ExFreePoolWithTag
0x140073681  nop     dword ptr [rax+rax+00h]
0x140073686  mov     rcx, [rsp+58h+var_18]
0x14007368b  xor     rcx, rsp; StackCookie
0x14007368e  call    __security_check_cookie
0x140073693  mov     rbx, [rsp+58h+arg_8]
0x140073698  add     rsp, 50h
0x14007369c  pop     rdi
0x14007369d  retn
0x14007369f  xor     edx, edx; PreviousAffinity
0x1400736a1  lea     rcx, [rsp+58h+Affinity]; Affinity
0x1400736a6  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1400736ad  nop     dword ptr [rax+rax+00h]
0x1400736b2  jmp     loc_1400735CD
0x1400736b7  mov     ecx, 3
0x1400736bc  int     29h; Win8: RtlFailFast(ecx)
```
