# VsmmpUnlockRange

- ea: `0x140003314`
- end: `0x140003476`
- name: `VsmmpUnlockRange`
- size: `354`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003298`
- `0x14001d260`
- `0x14002ec10`

## callees

- `0x140003314`
- `0x1400036ec`
- `0x1400038b0`
- `0x14000f498`
- `0x14001d204`
- `0x14001d21c`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x1400033c8`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400033c8`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003445`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003445`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400033e1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400033e1`
- `ntoskrnl!MmUnlockPages` at `0x140003352`
- `ntoskrnl!MmUnlockPages` at `0x1400033f1`
- `ntoskrnl!MmUnlockPages` at `0x140003352`
- `ntoskrnl!MmUnlockPages` at `0x1400033f1`

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
0x140003314  push    rbx
0x140003316  push    rbp
0x140003317  push    rsi
0x140003318  push    rdi
0x140003319  push    r14
0x14000331b  push    r15
0x14000331d  sub     rsp, 28h
0x140003321  cmp     qword ptr [rcx+28h], 0
0x140003326  mov     rdi, rcx
0x140003329  mov     qword ptr [rcx+30h], 0
0x140003331  ja      short loc_140003374
0x140003333  cmp     byte ptr [rdi+10h], 0
0x140003337  jnz     short loc_14000335E
0x140003339  mov     rcx, [rdi+18h]; MemoryDescriptorList
0x14000333d  test    rcx, rcx
0x140003340  jz      short loc_14000335E
0x140003342  mov     eax, [rdi+20h]
0x140003345  test    al, 2
0x140003347  jz      short loc_14000335E
0x140003349  cmp     eax, 3
0x14000334c  jz      loc_14000343B
0x140003352  call    cs:__imp_MmUnlockPages
0x140003359  nop     dword ptr [rax+rax+00h]
0x14000335e  mov     rcx, rdi
0x140003361  call    VsmmpUnlockFlushDeferredLockCount
0x140003366  add     rsp, 28h
0x14000336a  pop     r15
0x14000336c  pop     r14
0x14000336e  pop     rdi
0x14000336f  pop     rsi
0x140003370  pop     rbp
0x140003371  pop     rbx
0x140003372  retn
0x140003374  mov     rcx, rdi
0x140003377  call    VsmmpUnlockPrepareForNextPage
0x14000337c  mov     rdx, [rdi+40h]
0x140003380  mov     r8d, eax
0x140003383  mov     rcx, [rdi+38h]
0x140003387  call    VsmmMbpLockReleaseFast
0x14000338c  mov     rax, [rdi+30h]
0x140003390  inc     qword ptr [rdi+48h]
0x140003394  inc     rax
0x140003397  mov     [rdi+30h], rax
0x14000339b  cmp     rax, [rdi+28h]
0x14000339f  jnb     short loc_140003333
0x1400033a1  jmp     short loc_140003374
0x1400033a3  mov     rax, [rbx]
0x1400033a6  test    ebp, ebp
0x1400033a8  jz      short loc_1400033B3
0x1400033aa  test    rax, rax
0x1400033ad  jnz     loc_14000346E
0x1400033b3  mov     rbx, rax
0x1400033b6  test    rbx, rbx
0x1400033b9  jnz     short loc_14000341D
0x1400033bb  test    rbx, rbx
0x1400033be  jnz     short loc_1400033C2
0x1400033c0  int     2Ch; Windows NT - assertion failure
0x1400033c2  mov     rdx, rbx
0x1400033c5  mov     rcx, rsi
0x1400033c8  call    cs:__imp_RtlRbRemoveNode
0x1400033cf  nop     dword ptr [rax+rax+00h]
0x1400033d4  mov     rcx, [rdi]
0x1400033d7  mov     dl, r15b; OldIrql
0x1400033da  add     rcx, 30F0h; SpinLock
0x1400033e1  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400033e8  nop     dword ptr [rax+rax+00h]
0x1400033ed  mov     rcx, [rbx+20h]; MemoryDescriptorList
0x1400033f1  call    cs:__imp_MmUnlockPages
0x1400033f8  nop     dword ptr [rax+rax+00h]
0x1400033fd  mov     rcx, rbx; P
0x140003400  call    VsmmpFreeHybridLockContext
0x140003405  jmp     loc_14000335E
0x14000340a  xor     rbx, rsi
0x14000340d  test    rbx, rbx
0x140003410  jz      short loc_1400033C0
0x140003412  movzx   ebp, byte ptr [rsi+8]
0x140003416  mov     r14, [rdi+18h]
0x14000341a  and     ebp, 1
0x14000341d  mov     rdx, rbx
0x140003420  mov     rcx, r14
0x140003423  call    VsmmpCompareHybridLockContext
0x140003428  test    eax, eax
0x14000342a  js      loc_1400033A3
0x140003430  jle     short loc_1400033BB
0x140003432  mov     rax, [rbx+8]
0x140003436  jmp     loc_1400033A6
0x14000343b  mov     rcx, [rdi]
0x14000343e  add     rcx, 30F0h; SpinLock
0x140003445  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000344c  nop     dword ptr [rax+rax+00h]
0x140003451  mov     rsi, [rdi]
0x140003454  mov     r15b, al
0x140003457  add     rsi, 30F8h
0x14000345e  test    byte ptr [rsi+8], 1
0x140003462  mov     rbx, [rsi]
0x140003465  jz      short loc_14000340D
0x140003467  test    rbx, rbx
0x14000346a  jnz     short loc_14000340A
0x14000346c  jmp     short loc_14000340D
0x14000346e  xor     rbx, rax
0x140003471  jmp     loc_1400033B6
```
