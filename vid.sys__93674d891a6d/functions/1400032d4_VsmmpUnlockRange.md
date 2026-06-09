# VsmmpUnlockRange

- ea: `0x1400032d4`
- end: `0x140003436`
- name: `VsmmpUnlockRange`
- size: `354`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003258`
- `0x14001fa80`
- `0x14002ee10`

## callees

- `0x1400032d4`
- `0x1400036ac`
- `0x140003874`
- `0x14000f33c`
- `0x14001fa24`
- `0x14001fa3c`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140003388`
- `ntoskrnl!RtlRbRemoveNode` at `0x140003388`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003405`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003405`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400033a1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400033a1`
- `ntoskrnl!MmUnlockPages` at `0x140003312`
- `ntoskrnl!MmUnlockPages` at `0x1400033b1`
- `ntoskrnl!MmUnlockPages` at `0x140003312`
- `ntoskrnl!MmUnlockPages` at `0x1400033b1`

## pseudocode

```c
__int64 __fastcall VsmmpUnlockRange(__int64 a1)
{
  bool v1; // zf
  struct _MDL *v3; // rcx
  int v4; // eax
  unsigned int Page; // eax
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // r14
  int v11; // ebp
  int v12; // eax
  KIRQL v13; // r15
  void **v14; // rsi

  v1 = *(_QWORD *)(a1 + 40) == 0;
  *(_QWORD *)(a1 + 48) = 0;
  if ( !v1 )
  {
    do
    {
      Page = VsmmpUnlockPrepareForNextPage(a1);
      VsmmMbpLockReleaseFast(*(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 64), Page);
      v7 = *(_QWORD *)(a1 + 48);
      ++*(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 48) = ++v7;
    }
    while ( v7 < *(_QWORD *)(a1 + 40) );
  }
  if ( !*(_BYTE *)(a1 + 16) )
  {
    v3 = *(struct _MDL **)(a1 + 24);
    if ( v3 )
    {
      v4 = *(_DWORD *)(a1 + 32);
      if ( (v4 & 2) != 0 )
      {
        if ( v4 == 3 )
        {
          v13 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(*(_QWORD *)a1 + 12528LL));
          v14 = (void **)(*(_QWORD *)a1 + 12536LL);
          v9 = (unsigned __int64)*v14;
          if ( (*(_BYTE *)(*(_QWORD *)a1 + 12544LL) & 1) != 0 && v9 )
            v9 ^= (unsigned __int64)v14;
          if ( !v9 )
            goto LABEL_16;
          v10 = *(_QWORD *)(a1 + 24);
          v11 = *(_BYTE *)(*(_QWORD *)a1 + 12544LL) & 1;
          do
          {
            v12 = VsmmpCompareHybridLockContext(v10, v9);
            if ( v12 < 0 )
            {
              v8 = *(_QWORD *)v9;
            }
            else
            {
              if ( v12 <= 0 )
                break;
              v8 = *(_QWORD *)(v9 + 8);
            }
            if ( v11 && v8 )
              v9 ^= v8;
            else
              v9 = v8;
          }
          while ( v9 );
          if ( !v9 )
LABEL_16:
            __int2c();
          RtlRbRemoveNode(v14, v9);
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(*(_QWORD *)a1 + 12528LL), v13);
          MmUnlockPages(*(PMDL *)(v9 + 32));
          VsmmpFreeHybridLockContext((PVOID)v9);
        }
        else
        {
          MmUnlockPages(v3);
        }
      }
    }
  }
  return VsmmpUnlockFlushDeferredLockCount(a1);
}

```

## disassembly

```asm
0x1400032d4  push    rbx
0x1400032d6  push    rbp
0x1400032d7  push    rsi
0x1400032d8  push    rdi
0x1400032d9  push    r14
0x1400032db  push    r15
0x1400032dd  sub     rsp, 28h
0x1400032e1  cmp     qword ptr [rcx+28h], 0
0x1400032e6  mov     rdi, rcx
0x1400032e9  mov     qword ptr [rcx+30h], 0
0x1400032f1  ja      short loc_140003334
0x1400032f3  cmp     byte ptr [rdi+10h], 0
0x1400032f7  jnz     short loc_14000331E
0x1400032f9  mov     rcx, [rdi+18h]; MemoryDescriptorList
0x1400032fd  test    rcx, rcx
0x140003300  jz      short loc_14000331E
0x140003302  mov     eax, [rdi+20h]
0x140003305  test    al, 2
0x140003307  jz      short loc_14000331E
0x140003309  cmp     eax, 3
0x14000330c  jz      loc_1400033FB
0x140003312  call    cs:__imp_MmUnlockPages
0x140003319  nop     dword ptr [rax+rax+00h]
0x14000331e  mov     rcx, rdi
0x140003321  call    VsmmpUnlockFlushDeferredLockCount
0x140003326  add     rsp, 28h
0x14000332a  pop     r15
0x14000332c  pop     r14
0x14000332e  pop     rdi
0x14000332f  pop     rsi
0x140003330  pop     rbp
0x140003331  pop     rbx
0x140003332  retn
0x140003334  mov     rcx, rdi
0x140003337  call    VsmmpUnlockPrepareForNextPage
0x14000333c  mov     rdx, [rdi+40h]
0x140003340  mov     r8d, eax
0x140003343  mov     rcx, [rdi+38h]
0x140003347  call    VsmmMbpLockReleaseFast
0x14000334c  mov     rax, [rdi+30h]
0x140003350  inc     qword ptr [rdi+48h]
0x140003354  inc     rax
0x140003357  mov     [rdi+30h], rax
0x14000335b  cmp     rax, [rdi+28h]
0x14000335f  jnb     short loc_1400032F3
0x140003361  jmp     short loc_140003334
0x140003363  mov     rax, [rbx]
0x140003366  test    ebp, ebp
0x140003368  jz      short loc_140003373
0x14000336a  test    rax, rax
0x14000336d  jnz     loc_14000342E
0x140003373  mov     rbx, rax
0x140003376  test    rbx, rbx
0x140003379  jnz     short loc_1400033DD
0x14000337b  test    rbx, rbx
0x14000337e  jnz     short loc_140003382
0x140003380  int     2Ch; Windows NT - assertion failure
0x140003382  mov     rdx, rbx
0x140003385  mov     rcx, rsi
0x140003388  call    cs:__imp_RtlRbRemoveNode
0x14000338f  nop     dword ptr [rax+rax+00h]
0x140003394  mov     rcx, [rdi]
0x140003397  mov     dl, r15b; OldIrql
0x14000339a  add     rcx, 30F0h; SpinLock
0x1400033a1  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400033a8  nop     dword ptr [rax+rax+00h]
0x1400033ad  mov     rcx, [rbx+20h]; MemoryDescriptorList
0x1400033b1  call    cs:__imp_MmUnlockPages
0x1400033b8  nop     dword ptr [rax+rax+00h]
0x1400033bd  mov     rcx, rbx; P
0x1400033c0  call    VsmmpFreeHybridLockContext
0x1400033c5  jmp     loc_14000331E
0x1400033ca  xor     rbx, rsi
0x1400033cd  test    rbx, rbx
0x1400033d0  jz      short loc_140003380
0x1400033d2  movzx   ebp, byte ptr [rsi+8]
0x1400033d6  mov     r14, [rdi+18h]
0x1400033da  and     ebp, 1
0x1400033dd  mov     rdx, rbx
0x1400033e0  mov     rcx, r14
0x1400033e3  call    VsmmpCompareHybridLockContext
0x1400033e8  test    eax, eax
0x1400033ea  js      loc_140003363
0x1400033f0  jle     short loc_14000337B
0x1400033f2  mov     rax, [rbx+8]
0x1400033f6  jmp     loc_140003366
0x1400033fb  mov     rcx, [rdi]
0x1400033fe  add     rcx, 30F0h; SpinLock
0x140003405  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000340c  nop     dword ptr [rax+rax+00h]
0x140003411  mov     rsi, [rdi]
0x140003414  mov     r15b, al
0x140003417  add     rsi, 30F8h
0x14000341e  test    byte ptr [rsi+8], 1
0x140003422  mov     rbx, [rsi]
0x140003425  jz      short loc_1400033CD
0x140003427  test    rbx, rbx
0x14000342a  jnz     short loc_1400033CA
0x14000342c  jmp     short loc_1400033CD
0x14000342e  xor     rbx, rax
0x140003431  jmp     loc_140003376
```
