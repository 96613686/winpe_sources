# CreateTlgAggregateSession

- ea: `0x140092374`
- end: `0x1400924a4`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: `_QWORD *__fastcall(char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140092ba4`

## callees

- `0x140045940`
- `0x140092374`
- `0x1400924ac`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x140092475`
- `ntoskrnl!ExAllocateTimer` at `0x140092475`
- `ntoskrnl!KeInitializeEvent` at `0x140092428`
- `ntoskrnl!KeInitializeEvent` at `0x140092428`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400923a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400923f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400923a2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400923f2`

## pseudocode

```c
_QWORD *__fastcall CreateTlgAggregateSession(char a1, char a2)
{
  _QWORD *PoolWithTag; // rax
  _QWORD *v5; // rbx
  char *v6; // rax
  char *v7; // rdi
  _QWORD *v8; // rax
  __int64 Timer; // rax

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : NonPagedPoolNx), 0x178u, 0x47417254u);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_9;
  memset(PoolWithTag, 0, 0x178u);
  v5[34] = 0;
  if ( a2 || !a1 )
  {
    v6 = (char *)ExAllocatePoolWithTag(NonPagedPoolNx, 0x40u, 0x47417254u);
    v7 = v6;
    if ( v6 )
      memset(v6, 0, 0x40u);
    v5[33] = v7;
    if ( !v7 )
      goto LABEL_9;
    KeInitializeEvent((PRKEVENT)(v7 + 32), NotificationEvent, 0);
    v8 = (_QWORD *)v5[33];
    v8[2] = TlgAggregateInternalFlushWorkItemRoutineKernelMode;
    v8[3] = v5;
    *v8 = 0;
    *(_WORD *)(v5[33] + 56LL) = 0;
    if ( a2 )
    {
      Timer = ExAllocateTimer(TlgAggregateInternalFlushTimerCallbackKernelMode, v5[33], 8);
      v5[45] = Timer;
      if ( !Timer )
      {
LABEL_9:
        DestroyAggregateSession(v5);
        return 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140092374  push    rbx
0x140092376  push    rbp
0x140092377  push    rsi
0x140092378  push    rdi
0x140092379  sub     rsp, 28h
0x14009237d  mov     al, cl
0x14009237f  mov     dil, cl
0x140092382  neg     al
0x140092384  mov     sil, dl
0x140092387  mov     ebp, 178h
0x14009238c  mov     r8d, 47417254h; Tag
0x140092392  sbb     ecx, ecx
0x140092394  mov     edx, ebp; NumberOfBytes
0x140092396  and     ecx, 0FFFFFE01h
0x14009239c  add     ecx, 200h; PoolType
0x1400923a2  call    cs:__imp_ExAllocatePoolWithTag
0x1400923a9  nop     dword ptr [rax+rax+00h]
0x1400923ae  mov     rbx, rax
0x1400923b1  test    rax, rax
0x1400923b4  jz      loc_14009248D
0x1400923ba  mov     r8d, ebp; Size
0x1400923bd  xor     edx, edx; Val
0x1400923bf  mov     rcx, rax; void *
0x1400923c2  call    memset
0x1400923c7  mov     qword ptr [rbx+110h], 0
0x1400923d2  test    sil, sil
0x1400923d5  jnz     short loc_1400923E0
0x1400923d7  test    dil, dil
0x1400923da  jnz     loc_140092497
0x1400923e0  mov     ebp, 40h ; '@'
0x1400923e5  mov     r8d, 47417254h; Tag
0x1400923eb  mov     edx, ebp; NumberOfBytes
0x1400923ed  mov     ecx, 200h; PoolType
0x1400923f2  call    cs:__imp_ExAllocatePoolWithTag
0x1400923f9  nop     dword ptr [rax+rax+00h]
0x1400923fe  mov     rdi, rax
0x140092401  test    rax, rax
0x140092404  jz      short loc_140092413
0x140092406  mov     r8d, ebp; Size
0x140092409  xor     edx, edx; Val
0x14009240b  mov     rcx, rax; void *
0x14009240e  call    memset
0x140092413  mov     [rbx+108h], rdi
0x14009241a  test    rdi, rdi
0x14009241d  jz      short loc_14009248D
0x14009241f  lea     rcx, [rdi+20h]; Event
0x140092423  xor     r8d, r8d; State
0x140092426  xor     edx, edx; Type
0x140092428  call    cs:__imp_KeInitializeEvent
0x14009242f  nop     dword ptr [rax+rax+00h]
0x140092434  mov     rax, [rbx+108h]
0x14009243b  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140092442  mov     [rax+10h], rcx
0x140092446  mov     [rax+18h], rbx
0x14009244a  mov     qword ptr [rax], 0
0x140092451  xor     eax, eax
0x140092453  mov     rcx, [rbx+108h]
0x14009245a  mov     [rcx+38h], ax
0x14009245e  test    sil, sil
0x140092461  jz      short loc_140092497
0x140092463  mov     rdx, [rbx+108h]
0x14009246a  lea     r8d, [rax+8]
0x14009246e  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140092475  call    cs:__imp_ExAllocateTimer
0x14009247c  nop     dword ptr [rax+rax+00h]
0x140092481  mov     [rbx+168h], rax
0x140092488  test    rax, rax
0x14009248b  jnz     short loc_140092497
0x14009248d  mov     rcx, rbx; P
0x140092490  call    DestroyAggregateSession
0x140092495  xor     ebx, ebx
0x140092497  mov     rax, rbx
0x14009249a  add     rsp, 28h
0x14009249e  pop     rdi
0x14009249f  pop     rsi
0x1400924a0  pop     rbp
0x1400924a1  pop     rbx
0x1400924a2  retn
```
