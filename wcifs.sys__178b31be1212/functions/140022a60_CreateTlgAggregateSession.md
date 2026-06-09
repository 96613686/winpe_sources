# CreateTlgAggregateSession

- ea: `0x140022a60`
- end: `0x140022b90`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: `_QWORD *__fastcall(char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140022dd8`

## callees

- `0x1400080c0`
- `0x140022a60`
- `0x140022b98`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140022b14`
- `ntoskrnl!KeInitializeEvent` at `0x140022b14`
- `ntoskrnl!ExAllocateTimer` at `0x140022b61`
- `ntoskrnl!ExAllocateTimer` at `0x140022b61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022ade`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022a8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140022ade`

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
0x140022a60  push    rbx
0x140022a62  push    rbp
0x140022a63  push    rsi
0x140022a64  push    rdi
0x140022a65  sub     rsp, 28h
0x140022a69  mov     al, cl
0x140022a6b  mov     dil, cl
0x140022a6e  neg     al
0x140022a70  mov     sil, dl
0x140022a73  mov     ebp, 178h
0x140022a78  mov     r8d, 47417254h; Tag
0x140022a7e  sbb     ecx, ecx
0x140022a80  mov     edx, ebp; NumberOfBytes
0x140022a82  and     ecx, 0FFFFFE01h
0x140022a88  add     ecx, 200h; PoolType
0x140022a8e  call    cs:__imp_ExAllocatePoolWithTag
0x140022a95  nop     dword ptr [rax+rax+00h]
0x140022a9a  mov     rbx, rax
0x140022a9d  test    rax, rax
0x140022aa0  jz      loc_140022B79
0x140022aa6  mov     r8d, ebp; Size
0x140022aa9  xor     edx, edx; Val
0x140022aab  mov     rcx, rax; void *
0x140022aae  call    memset
0x140022ab3  mov     qword ptr [rbx+110h], 0
0x140022abe  test    sil, sil
0x140022ac1  jnz     short loc_140022ACC
0x140022ac3  test    dil, dil
0x140022ac6  jnz     loc_140022B83
0x140022acc  mov     ebp, 40h ; '@'
0x140022ad1  mov     r8d, 47417254h; Tag
0x140022ad7  mov     edx, ebp; NumberOfBytes
0x140022ad9  mov     ecx, 200h; PoolType
0x140022ade  call    cs:__imp_ExAllocatePoolWithTag
0x140022ae5  nop     dword ptr [rax+rax+00h]
0x140022aea  mov     rdi, rax
0x140022aed  test    rax, rax
0x140022af0  jz      short loc_140022AFF
0x140022af2  mov     r8d, ebp; Size
0x140022af5  xor     edx, edx; Val
0x140022af7  mov     rcx, rax; void *
0x140022afa  call    memset
0x140022aff  mov     [rbx+108h], rdi
0x140022b06  test    rdi, rdi
0x140022b09  jz      short loc_140022B79
0x140022b0b  lea     rcx, [rdi+20h]; Event
0x140022b0f  xor     r8d, r8d; State
0x140022b12  xor     edx, edx; Type
0x140022b14  call    cs:__imp_KeInitializeEvent
0x140022b1b  nop     dword ptr [rax+rax+00h]
0x140022b20  mov     rax, [rbx+108h]
0x140022b27  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140022b2e  mov     [rax+10h], rcx
0x140022b32  mov     [rax+18h], rbx
0x140022b36  mov     qword ptr [rax], 0
0x140022b3d  xor     eax, eax
0x140022b3f  mov     rcx, [rbx+108h]
0x140022b46  mov     [rcx+38h], ax
0x140022b4a  test    sil, sil
0x140022b4d  jz      short loc_140022B83
0x140022b4f  mov     rdx, [rbx+108h]
0x140022b56  lea     r8d, [rax+8]
0x140022b5a  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140022b61  call    cs:__imp_ExAllocateTimer
0x140022b68  nop     dword ptr [rax+rax+00h]
0x140022b6d  mov     [rbx+168h], rax
0x140022b74  test    rax, rax
0x140022b77  jnz     short loc_140022B83
0x140022b79  mov     rcx, rbx; P
0x140022b7c  call    DestroyAggregateSession
0x140022b81  xor     ebx, ebx
0x140022b83  mov     rax, rbx
0x140022b86  add     rsp, 28h
0x140022b8a  pop     rdi
0x140022b8b  pop     rsi
0x140022b8c  pop     rbp
0x140022b8d  pop     rbx
0x140022b8e  retn
```
