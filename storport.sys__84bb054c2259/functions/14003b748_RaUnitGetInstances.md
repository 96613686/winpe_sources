# RaUnitGetInstances

- ea: `0x14003b748`
- end: `0x14003b90e`
- name: `RaUnitGetInstances`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003b598`

## callees

- `0x1400172d0`
- `0x14003b748`
- `0x14003c170`
- `0x14003c1ec`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14003b85a`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14003b85a`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003b8bb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003b8bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b7c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b7ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b872`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b7c5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b7ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003b872`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b809`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b825`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b8a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b809`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b825`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003b8a8`

## pseudocode

```c
__int64 __fastcall RaUnitGetInstances(__int64 a1, unsigned int *a2)
{
  __int64 PortData; // rax
  __int64 v5; // rsi
  __int64 v7; // r14
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi
  KSPIN_LOCK *v10; // r12
  KSPIN_LOCK *v11; // rbx
  __int64 *i; // r12
  unsigned int v13; // eax
  struct _KLOCK_QUEUE_HANDLE v14; // [rsp+20h] [rbp-50h] BYREF
  struct _KLOCK_QUEUE_HANDLE v15; // [rsp+38h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v17; // [rsp+B0h] [rbp+40h]
  __int64 v18; // [rsp+C0h] [rbp+50h]

  memset(&v15, 0, sizeof(v15));
  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&v14, 0, sizeof(v14));
  if ( !a1 )
    *a2 = 0;
  PortData = RaidGetPortData(a1, a2);
  v18 = PortData;
  v5 = PortData;
  if ( PortData )
  {
    v7 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(PortData + 24), &LockHandle);
    v8 = *(_QWORD **)(v5 + 8);
    v17 = (_QWORD *)(v5 + 8);
    if ( v8 != (_QWORD *)(v5 + 8) )
    {
      v9 = (_QWORD *)(v5 + 8);
      do
      {
        KeAcquireInStackQueuedSpinLock(v8 + 7, &v15);
        v10 = v8 + 4;
        v11 = (KSPIN_LOCK *)v8[4];
        if ( v11 != v8 + 4 )
        {
          do
          {
            if ( *((_DWORD *)v11 - 16) == 1094997074
              && ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[32]) )
            {
              KeAcquireInStackQueuedSpinLock(v11 + 9, &v14);
              for ( i = (__int64 *)v11[10]; i != (__int64 *)(v11 + 10); i = (__int64 *)*i )
              {
                v13 = *a2;
                if ( a1 )
                {
                  if ( (unsigned int)v7 < v13 && (int)RaUnitAcquireRemoveLock(i - 8, 0, 0) >= 0 )
                  {
                    *(_QWORD *)(a1 + 8 * v7) = i - 8;
                    v7 = (unsigned int)(v7 + 1);
                  }
                }
                else
                {
                  *a2 = v13 + 1;
                }
              }
              KeReleaseInStackQueuedSpinLock(&v14);
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[32]);
              v10 = v8 + 4;
            }
            v11 = (KSPIN_LOCK *)*v11;
          }
          while ( v11 != v10 );
          v9 = v17;
        }
        KeReleaseInStackQueuedSpinLock(&v15);
        v8 = (_QWORD *)*v8;
      }
      while ( v8 != v9 );
      v5 = v18;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    RaidReleasePortData(v5);
    if ( a1 )
      *a2 = v7;
  }
  return 0;
}

```

## disassembly

```asm
0x14003b748  mov     [rsp-38h+arg_8], rbx
0x14003b74d  push    rbp
0x14003b74e  push    rsi
0x14003b74f  push    rdi
0x14003b750  push    r12
0x14003b752  push    r13
0x14003b754  push    r14
0x14003b756  push    r15
0x14003b758  mov     rbp, rsp
0x14003b75b  sub     rsp, 70h
0x14003b75f  xor     eax, eax
0x14003b761  xorps   xmm0, xmm0
0x14003b764  mov     qword ptr [rbp+var_38.OldIrql], rax
0x14003b768  xorps   xmm1, xmm1
0x14003b76b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14003b76f  mov     r15, rdx
0x14003b772  mov     qword ptr [rbp+var_50.OldIrql], rax
0x14003b776  mov     r13, rcx
0x14003b779  movups  xmmword ptr [rbp+var_38.LockQueue.Next], xmm0
0x14003b77d  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm1
0x14003b781  movups  xmmword ptr [rbp+var_50.LockQueue.Next], xmm0
0x14003b785  test    rcx, rcx
0x14003b788  jz      loc_14003B8E0
0x14003b78e  call    RaidGetPortData
0x14003b793  mov     [rbp+arg_10], rax
0x14003b797  mov     rsi, rax
0x14003b79a  test    rax, rax
0x14003b79d  jnz     short loc_14003B7BA
0x14003b79f  mov     rbx, [rsp+70h+arg_8]
0x14003b7a7  xor     eax, eax
0x14003b7a9  add     rsp, 70h
0x14003b7ad  pop     r15
0x14003b7af  pop     r14
0x14003b7b1  pop     r13
0x14003b7b3  pop     r12
0x14003b7b5  pop     rdi
0x14003b7b6  pop     rsi
0x14003b7b7  pop     rbp
0x14003b7b8  retn
0x14003b7ba  lea     rcx, [rax+18h]; SpinLock
0x14003b7be  xor     r14d, r14d
0x14003b7c1  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003b7c5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003b7cc  nop     dword ptr [rax+rax+00h]
0x14003b7d1  lea     rax, [rsi+8]
0x14003b7d5  mov     rdi, [rax]
0x14003b7d8  mov     [rbp+arg_0], rax
0x14003b7dc  cmp     rdi, rax
0x14003b7df  jz      short loc_14003B821
0x14003b7e1  mov     rsi, rax
0x14003b7e4  lea     rcx, [rdi+38h]; SpinLock
0x14003b7e8  lea     rdx, [rbp+var_38]; LockHandle
0x14003b7ec  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003b7f3  nop     dword ptr [rax+rax+00h]
0x14003b7f8  lea     r12, [rdi+20h]
0x14003b7fc  mov     rbx, [r12]
0x14003b800  cmp     rbx, r12
0x14003b803  jnz     short loc_14003B84A
0x14003b805  lea     rcx, [rbp+var_38]; LockHandle
0x14003b809  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003b810  nop     dword ptr [rax+rax+00h]
0x14003b815  mov     rdi, [rdi]
0x14003b818  cmp     rdi, rsi
0x14003b81b  jnz     short loc_14003B7E4
0x14003b81d  mov     rsi, [rbp+arg_10]
0x14003b821  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003b825  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003b82c  nop     dword ptr [rax+rax+00h]
0x14003b831  mov     rcx, rsi
0x14003b834  call    RaidReleasePortData
0x14003b839  test    r13, r13
0x14003b83c  jz      loc_14003B79F
0x14003b842  mov     [r15], r14d
0x14003b845  jmp     loc_14003B79F
0x14003b84a  cmp     dword ptr [rbx-40h], 41445452h
0x14003b851  jnz     short loc_14003B8CB
0x14003b853  mov     rcx, [rbx+100h]; RunRefCacheAware
0x14003b85a  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14003b861  nop     dword ptr [rax+rax+00h]
0x14003b866  test    al, al
0x14003b868  jz      short loc_14003B8CB
0x14003b86a  lea     rcx, [rbx+48h]; SpinLock
0x14003b86e  lea     rdx, [rbp+var_50]; LockHandle
0x14003b872  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003b879  nop     dword ptr [rax+rax+00h]
0x14003b87e  lea     rax, [rbx+50h]
0x14003b882  mov     r12, [rax]
0x14003b885  cmp     r12, rax
0x14003b888  jz      short loc_14003B8A4
0x14003b88a  lea     rsi, [rbx+50h]
0x14003b88e  mov     eax, [r15]
0x14003b891  test    r13, r13
0x14003b894  jnz     short loc_14003B8E7
0x14003b896  inc     eax
0x14003b898  mov     [r15], eax
0x14003b89b  mov     r12, [r12]
0x14003b89f  cmp     r12, rsi
0x14003b8a2  jnz     short loc_14003B88E
0x14003b8a4  lea     rcx, [rbp+var_50]; LockHandle
0x14003b8a8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003b8af  nop     dword ptr [rax+rax+00h]
0x14003b8b4  mov     rcx, [rbx+100h]; RunRefCacheAware
0x14003b8bb  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14003b8c2  nop     dword ptr [rax+rax+00h]
0x14003b8c7  lea     r12, [rdi+20h]
0x14003b8cb  mov     rbx, [rbx]
0x14003b8ce  cmp     rbx, r12
0x14003b8d1  jnz     loc_14003B84A
0x14003b8d7  mov     rsi, [rbp+arg_0]
0x14003b8db  jmp     loc_14003B805
0x14003b8e0  mov     [rdx], eax
0x14003b8e2  jmp     loc_14003B78E
0x14003b8e7  cmp     r14d, eax
0x14003b8ea  jnb     short loc_14003B89B
0x14003b8ec  lea     rcx, [r12-40h]
0x14003b8f1  xor     r8d, r8d
0x14003b8f4  xor     edx, edx
0x14003b8f6  call    RaUnitAcquireRemoveLock
0x14003b8fb  test    eax, eax
0x14003b8fd  js      short loc_14003B89B
0x14003b8ff  lea     rcx, [r12-40h]
0x14003b904  mov     [r13+r14*8+0], rcx
0x14003b909  inc     r14d
0x14003b90c  jmp     short loc_14003B89B
```
