# CreateTlgAggregateSession

- ea: `0x140025de0`
- end: `0x140025f10`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140026158`

## callees

- `0x1400119c0`
- `0x140025de0`
- `0x140025f18`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x140025ee1`
- `ntoskrnl!ExAllocateTimer` at `0x140025ee1`
- `ntoskrnl!KeInitializeEvent` at `0x140025e94`
- `ntoskrnl!KeInitializeEvent` at `0x140025e94`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e5e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e5e`

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

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), 0x178u, 0x47417254u);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_9;
  memset(PoolWithTag, 0, 0x178u);
  v5[34] = 0;
  if ( a2 || !a1 )
  {
    v6 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x47417254u);
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
0x140025de0  push    rbx
0x140025de2  push    rbp
0x140025de3  push    rsi
0x140025de4  push    rdi
0x140025de5  sub     rsp, 28h
0x140025de9  mov     al, cl
0x140025deb  mov     dil, cl
0x140025dee  neg     al
0x140025df0  mov     sil, dl
0x140025df3  mov     ebp, 178h
0x140025df8  mov     r8d, 47417254h; Tag
0x140025dfe  sbb     ecx, ecx
0x140025e00  mov     edx, ebp; NumberOfBytes
0x140025e02  and     ecx, 0FFFFFE01h
0x140025e08  add     ecx, 200h; PoolType
0x140025e0e  call    cs:__imp_ExAllocatePoolWithTag
0x140025e15  nop     dword ptr [rax+rax+00h]
0x140025e1a  mov     rbx, rax
0x140025e1d  test    rax, rax
0x140025e20  jz      loc_140025EF9
0x140025e26  mov     r8d, ebp; Size
0x140025e29  xor     edx, edx; Val
0x140025e2b  mov     rcx, rax; void *
0x140025e2e  call    memset
0x140025e33  mov     qword ptr [rbx+110h], 0
0x140025e3e  test    sil, sil
0x140025e41  jnz     short loc_140025E4C
0x140025e43  test    dil, dil
0x140025e46  jnz     loc_140025F03
0x140025e4c  mov     ebp, 40h ; '@'
0x140025e51  mov     r8d, 47417254h; Tag
0x140025e57  mov     edx, ebp; NumberOfBytes
0x140025e59  mov     ecx, 200h; PoolType
0x140025e5e  call    cs:__imp_ExAllocatePoolWithTag
0x140025e65  nop     dword ptr [rax+rax+00h]
0x140025e6a  mov     rdi, rax
0x140025e6d  test    rax, rax
0x140025e70  jz      short loc_140025E7F
0x140025e72  mov     r8d, ebp; Size
0x140025e75  xor     edx, edx; Val
0x140025e77  mov     rcx, rax; void *
0x140025e7a  call    memset
0x140025e7f  mov     [rbx+108h], rdi
0x140025e86  test    rdi, rdi
0x140025e89  jz      short loc_140025EF9
0x140025e8b  lea     rcx, [rdi+20h]; Event
0x140025e8f  xor     r8d, r8d; State
0x140025e92  xor     edx, edx; Type
0x140025e94  call    cs:__imp_KeInitializeEvent
0x140025e9b  nop     dword ptr [rax+rax+00h]
0x140025ea0  mov     rax, [rbx+108h]
0x140025ea7  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140025eae  mov     [rax+10h], rcx
0x140025eb2  mov     [rax+18h], rbx
0x140025eb6  mov     qword ptr [rax], 0
0x140025ebd  xor     eax, eax
0x140025ebf  mov     rcx, [rbx+108h]
0x140025ec6  mov     [rcx+38h], ax
0x140025eca  test    sil, sil
0x140025ecd  jz      short loc_140025F03
0x140025ecf  mov     rdx, [rbx+108h]
0x140025ed6  lea     r8d, [rax+8]
0x140025eda  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140025ee1  call    cs:__imp_ExAllocateTimer
0x140025ee8  nop     dword ptr [rax+rax+00h]
0x140025eed  mov     [rbx+168h], rax
0x140025ef4  test    rax, rax
0x140025ef7  jnz     short loc_140025F03
0x140025ef9  mov     rcx, rbx; P
0x140025efc  call    DestroyAggregateSession
0x140025f01  xor     ebx, ebx
0x140025f03  mov     rax, rbx
0x140025f06  add     rsp, 28h
0x140025f0a  pop     rdi
0x140025f0b  pop     rsi
0x140025f0c  pop     rbp
0x140025f0d  pop     rbx
0x140025f0e  retn
```
