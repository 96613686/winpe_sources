# CreateTlgAggregateSession

- ea: `0x140022a10`
- end: `0x140022b40`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140022d88`

## callees

- `0x1400080c0`
- `0x140022a10`
- `0x140022b48`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140022ac4`
- `ntoskrnl!KeInitializeEvent` at `0x140022ac4`
- `ntoskrnl!ExAllocateTimer` at `0x140022b11`
- `ntoskrnl!ExAllocateTimer` at `0x140022b11`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a3e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a3e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a8e`

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
0x140022a10  push    rbx
0x140022a12  push    rbp
0x140022a13  push    rsi
0x140022a14  push    rdi
0x140022a15  sub     rsp, 28h
0x140022a19  mov     al, cl
0x140022a1b  mov     dil, cl
0x140022a1e  neg     al
0x140022a20  mov     sil, dl
0x140022a23  mov     ebp, 178h
0x140022a28  mov     r8d, 47417254h; Tag
0x140022a2e  sbb     ecx, ecx
0x140022a30  mov     edx, ebp; NumberOfBytes
0x140022a32  and     ecx, 0FFFFFE01h
0x140022a38  add     ecx, 200h; PoolType
0x140022a3e  call    cs:__imp_ExAllocatePoolWithTag
0x140022a45  nop     dword ptr [rax+rax+00h]
0x140022a4a  mov     rbx, rax
0x140022a4d  test    rax, rax
0x140022a50  jz      loc_140022B29
0x140022a56  mov     r8d, ebp; Size
0x140022a59  xor     edx, edx; Val
0x140022a5b  mov     rcx, rax; void *
0x140022a5e  call    memset
0x140022a63  mov     qword ptr [rbx+110h], 0
0x140022a6e  test    sil, sil
0x140022a71  jnz     short loc_140022A7C
0x140022a73  test    dil, dil
0x140022a76  jnz     loc_140022B33
0x140022a7c  mov     ebp, 40h ; '@'
0x140022a81  mov     r8d, 47417254h; Tag
0x140022a87  mov     edx, ebp; NumberOfBytes
0x140022a89  mov     ecx, 200h; PoolType
0x140022a8e  call    cs:__imp_ExAllocatePoolWithTag
0x140022a95  nop     dword ptr [rax+rax+00h]
0x140022a9a  mov     rdi, rax
0x140022a9d  test    rax, rax
0x140022aa0  jz      short loc_140022AAF
0x140022aa2  mov     r8d, ebp; Size
0x140022aa5  xor     edx, edx; Val
0x140022aa7  mov     rcx, rax; void *
0x140022aaa  call    memset
0x140022aaf  mov     [rbx+108h], rdi
0x140022ab6  test    rdi, rdi
0x140022ab9  jz      short loc_140022B29
0x140022abb  lea     rcx, [rdi+20h]; Event
0x140022abf  xor     r8d, r8d; State
0x140022ac2  xor     edx, edx; Type
0x140022ac4  call    cs:__imp_KeInitializeEvent
0x140022acb  nop     dword ptr [rax+rax+00h]
0x140022ad0  mov     rax, [rbx+108h]
0x140022ad7  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140022ade  mov     [rax+10h], rcx
0x140022ae2  mov     [rax+18h], rbx
0x140022ae6  mov     qword ptr [rax], 0
0x140022aed  xor     eax, eax
0x140022aef  mov     rcx, [rbx+108h]
0x140022af6  mov     [rcx+38h], ax
0x140022afa  test    sil, sil
0x140022afd  jz      short loc_140022B33
0x140022aff  mov     rdx, [rbx+108h]
0x140022b06  lea     r8d, [rax+8]
0x140022b0a  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140022b11  call    cs:__imp_ExAllocateTimer
0x140022b18  nop     dword ptr [rax+rax+00h]
0x140022b1d  mov     [rbx+168h], rax
0x140022b24  test    rax, rax
0x140022b27  jnz     short loc_140022B33
0x140022b29  mov     rcx, rbx; P
0x140022b2c  call    DestroyAggregateSession
0x140022b31  xor     ebx, ebx
0x140022b33  mov     rax, rbx
0x140022b36  add     rsp, 28h
0x140022b3a  pop     rdi
0x140022b3b  pop     rsi
0x140022b3c  pop     rbp
0x140022b3d  pop     rbx
0x140022b3e  retn
```
