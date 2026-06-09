# WofCreateTransactionContext

- ea: `0x1400236d4`
- end: `0x140023785`
- name: `WofCreateTransactionContext`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022c28`

## callees

- `0x1400119c0`
- `0x1400236d4`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140023768`
- `ntoskrnl!KeInitializeEvent` at `0x140023768`
- `FLTMGR!FltAllocateContext` at `0x140023706`
- `FLTMGR!FltAllocateContext` at `0x140023706`

## pseudocode

```c
NTSTATUS __fastcall WofCreateTransactionContext(PFLT_CONTEXT *a1)
{
  NTSTATUS result; // eax
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  struct _KEVENT *v5; // rcx
  PFLT_CONTEXT ReturnedContext; // [rsp+48h] [rbp+10h] BYREF

  ReturnedContext = 0;
  result = FltAllocateContext(WofGlobal, 0x20u, 0x60u, (POOL_TYPE)512, &ReturnedContext);
  if ( result >= 0 )
  {
    memset(ReturnedContext, 0, 0x60u);
    v3 = (char *)ReturnedContext + 80;
    *((_QWORD *)ReturnedContext + 11) = (char *)ReturnedContext + 80;
    *v3 = v3;
    v4 = (char *)ReturnedContext + 64;
    *((_QWORD *)ReturnedContext + 9) = (char *)ReturnedContext + 64;
    *v4 = v4;
    v5 = (struct _KEVENT *)ReturnedContext;
    *(_DWORD *)ReturnedContext = 1;
    v5->Header.WaitListHead.Flink = 0;
    LODWORD(v5->Header.WaitListHead.Blink) = 0;
    KeInitializeEvent(v5 + 1, SynchronizationEvent, 0);
    *a1 = ReturnedContext;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400236d4  push    rbx
0x1400236d6  sub     rsp, 30h
0x1400236da  mov     edx, 20h ; ' '; ContextType
0x1400236df  mov     [rsp+38h+arg_8], 0
0x1400236e8  mov     rbx, rcx
0x1400236eb  lea     rax, [rsp+38h+arg_8]
0x1400236f0  mov     rcx, cs:WofGlobal; Filter
0x1400236f7  mov     r9d, 200h; PoolType
0x1400236fd  mov     [rsp+38h+ReturnedContext], rax; ReturnedContext
0x140023702  lea     r8d, [rdx+40h]; ContextSize
0x140023706  call    cs:__imp_FltAllocateContext
0x14002370d  nop     dword ptr [rax+rax+00h]
0x140023712  test    eax, eax
0x140023714  js      short loc_14002377E
0x140023716  mov     rcx, [rsp+38h+arg_8]; void *
0x14002371b  xor     edx, edx; Val
0x14002371d  lea     r8d, [rdx+60h]; Size
0x140023721  call    memset
0x140023726  mov     rax, [rsp+38h+arg_8]
0x14002372b  mov     edx, 1; Type
0x140023730  add     rax, 50h ; 'P'
0x140023734  xor     r8d, r8d; State
0x140023737  mov     [rax+8], rax
0x14002373b  mov     [rax], rax
0x14002373e  mov     rax, [rsp+38h+arg_8]
0x140023743  add     rax, 40h ; '@'
0x140023747  mov     [rax+8], rax
0x14002374b  mov     [rax], rax
0x14002374e  mov     rcx, [rsp+38h+arg_8]
0x140023753  mov     [rcx], edx
0x140023755  mov     qword ptr [rcx+8], 0
0x14002375d  mov     dword ptr [rcx+10h], 0
0x140023764  add     rcx, 18h; Event
0x140023768  call    cs:__imp_KeInitializeEvent
0x14002376f  nop     dword ptr [rax+rax+00h]
0x140023774  mov     rax, [rsp+38h+arg_8]
0x140023779  mov     [rbx], rax
0x14002377c  xor     eax, eax
0x14002377e  add     rsp, 30h
0x140023782  pop     rbx
0x140023783  retn
```
