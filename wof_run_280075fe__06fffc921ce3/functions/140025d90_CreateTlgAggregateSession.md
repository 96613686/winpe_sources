# CreateTlgAggregateSession

- ea: `0x140025d90`
- end: `0x140025ec0`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140026108`

## callees

- `0x1400119c0`
- `0x140025d90`
- `0x140025ec8`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x140025e91`
- `ntoskrnl!ExAllocateTimer` at `0x140025e91`
- `ntoskrnl!KeInitializeEvent` at `0x140025e44`
- `ntoskrnl!KeInitializeEvent` at `0x140025e44`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025dbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e0e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025dbe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025e0e`

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
0x140025d90  push    rbx
0x140025d92  push    rbp
0x140025d93  push    rsi
0x140025d94  push    rdi
0x140025d95  sub     rsp, 28h
0x140025d99  mov     al, cl
0x140025d9b  mov     dil, cl
0x140025d9e  neg     al
0x140025da0  mov     sil, dl
0x140025da3  mov     ebp, 178h
0x140025da8  mov     r8d, 47417254h; Tag
0x140025dae  sbb     ecx, ecx
0x140025db0  mov     edx, ebp; NumberOfBytes
0x140025db2  and     ecx, 0FFFFFE01h
0x140025db8  add     ecx, 200h; PoolType
0x140025dbe  call    cs:__imp_ExAllocatePoolWithTag
0x140025dc5  nop     dword ptr [rax+rax+00h]
0x140025dca  mov     rbx, rax
0x140025dcd  test    rax, rax
0x140025dd0  jz      loc_140025EA9
0x140025dd6  mov     r8d, ebp; Size
0x140025dd9  xor     edx, edx; Val
0x140025ddb  mov     rcx, rax; void *
0x140025dde  call    memset
0x140025de3  mov     qword ptr [rbx+110h], 0
0x140025dee  test    sil, sil
0x140025df1  jnz     short loc_140025DFC
0x140025df3  test    dil, dil
0x140025df6  jnz     loc_140025EB3
0x140025dfc  mov     ebp, 40h ; '@'
0x140025e01  mov     r8d, 47417254h; Tag
0x140025e07  mov     edx, ebp; NumberOfBytes
0x140025e09  mov     ecx, 200h; PoolType
0x140025e0e  call    cs:__imp_ExAllocatePoolWithTag
0x140025e15  nop     dword ptr [rax+rax+00h]
0x140025e1a  mov     rdi, rax
0x140025e1d  test    rax, rax
0x140025e20  jz      short loc_140025E2F
0x140025e22  mov     r8d, ebp; Size
0x140025e25  xor     edx, edx; Val
0x140025e27  mov     rcx, rax; void *
0x140025e2a  call    memset
0x140025e2f  mov     [rbx+108h], rdi
0x140025e36  test    rdi, rdi
0x140025e39  jz      short loc_140025EA9
0x140025e3b  lea     rcx, [rdi+20h]; Event
0x140025e3f  xor     r8d, r8d; State
0x140025e42  xor     edx, edx; Type
0x140025e44  call    cs:__imp_KeInitializeEvent
0x140025e4b  nop     dword ptr [rax+rax+00h]
0x140025e50  mov     rax, [rbx+108h]
0x140025e57  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x140025e5e  mov     [rax+10h], rcx
0x140025e62  mov     [rax+18h], rbx
0x140025e66  mov     qword ptr [rax], 0
0x140025e6d  xor     eax, eax
0x140025e6f  mov     rcx, [rbx+108h]
0x140025e76  mov     [rcx+38h], ax
0x140025e7a  test    sil, sil
0x140025e7d  jz      short loc_140025EB3
0x140025e7f  mov     rdx, [rbx+108h]
0x140025e86  lea     r8d, [rax+8]
0x140025e8a  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140025e91  call    cs:__imp_ExAllocateTimer
0x140025e98  nop     dword ptr [rax+rax+00h]
0x140025e9d  mov     [rbx+168h], rax
0x140025ea4  test    rax, rax
0x140025ea7  jnz     short loc_140025EB3
0x140025ea9  mov     rcx, rbx; P
0x140025eac  call    DestroyAggregateSession
0x140025eb1  xor     ebx, ebx
0x140025eb3  mov     rax, rbx
0x140025eb6  add     rsp, 28h
0x140025eba  pop     rdi
0x140025ebb  pop     rsi
0x140025ebc  pop     rbp
0x140025ebd  pop     rbx
0x140025ebe  retn
```
