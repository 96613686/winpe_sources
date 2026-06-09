# WanpRouterLinkDownHandler

- ea: `0x1400110bc`
- end: `0x140011227`
- name: `WanpRouterLinkDownHandler`
- size: `363`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000f9c8`

## callees

- `0x14000f728`
- `0x1400110bc`
- `0x14001404c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011164`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140011164`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400111bb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400111e3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400111bb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400111e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111f6`

## pseudocode

```c
__int64 __fastcall WanpRouterLinkDownHandler(PVOID Entry, KIRQL a2, _QWORD *a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  __int64 v8; // rdx
  _DWORD *v9; // rax
  _DWORD *v10; // rdi

  v3 = *((_QWORD *)Entry + 2);
  v4 = *((_QWORD *)Entry + 1);
  *(_DWORD *)(v3 + 140) = 2;
  *(_DWORD *)(v3 + 144) = 2;
  v8 = MEMORY[0xFFFFF78000000014] / 100000LL;
  *(_QWORD *)(v4 + 200) = MEMORY[0xFFFFF78000000014] / 100000LL;
  *(_QWORD *)(v3 + 40) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry(Entry);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry(Entry);
  if ( *(_DWORD *)(v3 + 136) )
  {
    LOBYTE(v8) = *((_BYTE *)Entry + 4);
    WanpFlushQueuedNetBufferLists(v4, v8);
  }
  v9 = ExAllocateFromNPagedLookasideList(&g_llNotificationBlocks);
  v10 = v9;
  if ( v9 )
  {
    v9[12] = 2;
    v9[14] = *(_DWORD *)(v4 + 360);
    v9[13] = *(_DWORD *)(v3 + 32);
    *((_BYTE *)v9 + 60) = *((_BYTE *)Entry + 4);
    if ( *((_BYTE *)Entry + 4) )
    {
      v9[16] = *((_DWORD *)Entry + 6);
      v9[17] = *((_DWORD *)Entry + 7);
      v9[18] = *((_DWORD *)Entry + 8);
    }
    else
    {
      *((_QWORD *)v9 + 8) = *((_QWORD *)Entry + 6);
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 56));
    KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), a2);
    *a3 = v10;
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 56));
    KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), a2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
    WanpDeleteConnEntry(Entry);
  return 0;
}

```

## disassembly

```asm
0x1400110bc  push    rbx
0x1400110be  push    rbp
0x1400110bf  push    rsi
0x1400110c0  push    rdi
0x1400110c1  push    r14
0x1400110c3  push    r15
0x1400110c5  sub     rsp, 28h
0x1400110c9  mov     rsi, [rcx+10h]
0x1400110cd  mov     eax, 2
0x1400110d2  mov     r14, [rcx+8]
0x1400110d6  mov     bpl, dl
0x1400110d9  mov     r9, 0FFFFF78000000014h
0x1400110e3  mov     r15, r8
0x1400110e6  mov     rbx, rcx
0x1400110e9  mov     [rsi+8Ch], eax
0x1400110ef  mov     [rsi+90h], eax
0x1400110f5  mov     rax, 29F16B11C6D1E109h
0x1400110ff  mov     r9, [r9]
0x140011102  imul    r9
0x140011105  sar     rdx, 0Eh
0x140011109  mov     rax, rdx
0x14001110c  shr     rax, 3Fh
0x140011110  add     rdx, rax
0x140011113  mov     [r14+0C8h], rdx
0x14001111a  or      eax, 0FFFFFFFFh
0x14001111d  mov     qword ptr [rsi+28h], 0
0x140011125  lock xadd [rcx+60h], eax
0x14001112a  cmp     eax, 1
0x14001112d  jnz     short loc_140011134
0x14001112f  call    WanpDeleteConnEntry
0x140011134  or      eax, 0FFFFFFFFh
0x140011137  lock xadd [rbx+60h], eax
0x14001113c  cmp     eax, 1
0x14001113f  jnz     short loc_140011149
0x140011141  mov     rcx, rbx; Entry
0x140011144  call    WanpDeleteConnEntry
0x140011149  cmp     dword ptr [rsi+88h], 0
0x140011150  jbe     short loc_14001115D
0x140011152  mov     dl, [rbx+4]
0x140011155  mov     rcx, r14
0x140011158  call    WanpFlushQueuedNetBufferLists
0x14001115d  lea     rcx, g_llNotificationBlocks; Lookaside
0x140011164  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001116b  nop     dword ptr [rax+rax+00h]
0x140011170  mov     rdi, rax
0x140011173  test    rax, rax
0x140011176  jz      short loc_1400111DF
0x140011178  mov     dword ptr [rax+30h], 2
0x14001117f  mov     ecx, [r14+168h]
0x140011186  mov     [rax+38h], ecx
0x140011189  mov     ecx, [rsi+20h]
0x14001118c  mov     [rax+34h], ecx
0x14001118f  mov     cl, [rbx+4]
0x140011192  mov     [rax+3Ch], cl
0x140011195  cmp     byte ptr [rbx+4], 0
0x140011199  jz      short loc_1400111AF
0x14001119b  mov     eax, [rbx+18h]
0x14001119e  mov     [rdi+40h], eax
0x1400111a1  mov     eax, [rbx+1Ch]
0x1400111a4  mov     [rdi+44h], eax
0x1400111a7  mov     eax, [rbx+20h]
0x1400111aa  mov     [rdi+48h], eax
0x1400111ad  jmp     short loc_1400111B7
0x1400111af  mov     rax, [rbx+30h]
0x1400111b3  mov     [rdi+40h], rax
0x1400111b7  lea     rcx, [rsi+38h]; SpinLock
0x1400111bb  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400111c2  nop     dword ptr [rax+rax+00h]
0x1400111c7  mov     rcx, [rbx+50h]; SpinLock
0x1400111cb  mov     dl, bpl; NewIrql
0x1400111ce  call    cs:__imp_KeReleaseSpinLock
0x1400111d5  nop     dword ptr [rax+rax+00h]
0x1400111da  mov     [r15], rdi
0x1400111dd  jmp     short loc_140011202
0x1400111df  lea     rcx, [rsi+38h]; SpinLock
0x1400111e3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400111ea  nop     dword ptr [rax+rax+00h]
0x1400111ef  mov     rcx, [rbx+50h]; SpinLock
0x1400111f3  mov     dl, bpl; NewIrql
0x1400111f6  call    cs:__imp_KeReleaseSpinLock
0x1400111fd  nop     dword ptr [rax+rax+00h]
0x140011202  or      eax, 0FFFFFFFFh
0x140011205  lock xadd [rbx+60h], eax
0x14001120a  cmp     eax, 1
0x14001120d  jnz     short loc_140011217
0x14001120f  mov     rcx, rbx; Entry
0x140011212  call    WanpDeleteConnEntry
0x140011217  xor     eax, eax
0x140011219  add     rsp, 28h
0x14001121d  pop     r15
0x14001121f  pop     r14
0x140011221  pop     rdi
0x140011222  pop     rsi
0x140011223  pop     rbp
0x140011224  pop     rbx
0x140011225  retn
```
