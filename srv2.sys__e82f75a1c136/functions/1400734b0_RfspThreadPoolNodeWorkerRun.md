# RfspThreadPoolNodeWorkerRun

- ea: `0x1400734b0`
- end: `0x14007366e`
- name: `RfspThreadPoolNodeWorkerRun`
- size: `446`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140038490`
- `0x1400734b0`
- `0x140073680`

## import_xrefs

- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400734ed`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400735c6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400734ed`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400735c6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073523`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400735f6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140073523`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400735f6`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140073565`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x140073565`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140073656`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140073656`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007362a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007362a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400735a7`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400735a7`
- `ntoskrnl!KeSetPriorityThread` at `0x140073546`
- `ntoskrnl!KeSetPriorityThread` at `0x140073546`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140073616`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140073616`

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
0x1400734b0  mov     [rsp+arg_8], rbx
0x1400734b5  push    rdi
0x1400734b6  sub     rsp, 50h
0x1400734ba  mov     rax, cs:__security_cookie
0x1400734c1  xor     rax, rsp
0x1400734c4  mov     [rsp+58h+var_18], rax
0x1400734c9  mov     rbx, rcx
0x1400734cc  xorps   xmm0, xmm0
0x1400734cf  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x1400734d4  mov     rax, gs:188h
0x1400734dd  mov     edi, 88h
0x1400734e2  mov     [rcx+18h], rax
0x1400734e6  mov     rcx, [rcx+10h]
0x1400734ea  add     rcx, rdi; Mutex
0x1400734ed  call    cs:__imp_KeAcquireGuardedMutex
0x1400734f4  nop     dword ptr [rax+rax+00h]
0x1400734f9  mov     rax, [rbx+10h]
0x1400734fd  add     rax, 78h ; 'x'
0x140073501  mov     rcx, [rax+8]
0x140073505  cmp     [rcx], rax
0x140073508  jnz     loc_140073667
0x14007350e  mov     [rbx+8], rcx
0x140073512  mov     [rbx], rax
0x140073515  mov     [rcx], rbx
0x140073518  mov     [rax+8], rbx
0x14007351c  mov     rcx, [rbx+10h]
0x140073520  add     rcx, rdi; Mutex
0x140073523  call    cs:__imp_KeReleaseGuardedMutex
0x14007352a  nop     dword ptr [rax+rax+00h]
0x14007352f  mov     rax, [rbx+10h]
0x140073533  mov     rcx, gs:188h; Thread
0x14007353c  mov     rdx, [rax+0D8h]
0x140073543  mov     edx, [rdx+8]; Priority
0x140073546  call    cs:__imp_KeSetPriorityThread
0x14007354d  nop     dword ptr [rax+rax+00h]
0x140073552  mov     rcx, [rbx+10h]
0x140073556  lea     rdx, [rsp+58h+Affinity]; Affinity
0x14007355b  xor     r8d, r8d; Count
0x14007355e  movzx   ecx, word ptr [rcx+0E8h]; NodeNumber
0x140073565  call    cs:__imp_KeQueryNodeActiveAffinity
0x14007356c  nop     dword ptr [rax+rax+00h]
0x140073571  cmp     [rsp+58h+Affinity.Mask], 0
0x140073577  jnz     loc_14007364F
0x14007357d  mov     rax, [rbx+10h]
0x140073581  mov     rcx, [rax+0D8h]
0x140073588  mov     r8, [rcx+10h]; Size
0x14007358c  test    r8, r8
0x14007358f  jz      short loc_1400735B7
0x140073591  xor     r9d, r9d; Wait
0x140073594  mov     [rsp+58h+Context], 0; Context
0x14007359d  mov     rdx, rbx; Parameter
0x1400735a0  lea     rcx, RfspThreadPoolNodeWorkerProcessWorkItems; Callout
0x1400735a7  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1400735ae  nop     dword ptr [rax+rax+00h]
0x1400735b3  test    eax, eax
0x1400735b5  jns     short loc_1400735BF
0x1400735b7  mov     rcx, rbx; Parameter
0x1400735ba  call    RfspThreadPoolNodeWorkerProcessWorkItems
0x1400735bf  mov     rcx, [rbx+10h]
0x1400735c3  add     rcx, rdi; Mutex
0x1400735c6  call    cs:__imp_KeAcquireGuardedMutex
0x1400735cd  nop     dword ptr [rax+rax+00h]
0x1400735d2  mov     rcx, [rbx]
0x1400735d5  cmp     [rcx+8], rbx
0x1400735d9  jnz     loc_140073667
0x1400735df  mov     rax, [rbx+8]
0x1400735e3  cmp     [rax], rbx
0x1400735e6  jnz     short loc_140073667
0x1400735e8  mov     [rax], rcx
0x1400735eb  mov     [rcx+8], rax
0x1400735ef  mov     rcx, [rbx+10h]
0x1400735f3  add     rcx, rdi; Mutex
0x1400735f6  call    cs:__imp_KeReleaseGuardedMutex
0x1400735fd  nop     dword ptr [rax+rax+00h]
0x140073602  mov     rax, [rbx+10h]
0x140073606  lock dec word ptr [rax+40h]
0x14007360b  mov     rcx, [rbx+10h]
0x14007360f  add     rcx, 0D0h; RunRef
0x140073616  call    cs:__imp_ExReleaseRundownProtection
0x14007361d  nop     dword ptr [rax+rax+00h]
0x140073622  mov     edx, 5266534Ch; Tag
0x140073627  mov     rcx, rbx; P
0x14007362a  call    cs:__imp_ExFreePoolWithTag
0x140073631  nop     dword ptr [rax+rax+00h]
0x140073636  mov     rcx, [rsp+58h+var_18]
0x14007363b  xor     rcx, rsp; StackCookie
0x14007363e  call    __security_check_cookie
0x140073643  mov     rbx, [rsp+58h+arg_8]
0x140073648  add     rsp, 50h
0x14007364c  pop     rdi
0x14007364d  retn
0x14007364f  xor     edx, edx; PreviousAffinity
0x140073651  lea     rcx, [rsp+58h+Affinity]; Affinity
0x140073656  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14007365d  nop     dword ptr [rax+rax+00h]
0x140073662  jmp     loc_14007357D
0x140073667  mov     ecx, 3
0x14007366c  int     29h; Win8: RtlFailFast(ecx)
```
