# WanpRemoveConnections

- ea: `0x1400033f4`
- end: `0x140003533`
- name: `WanpRemoveConnections`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f250`

## callees

- `0x1400033f4`
- `0x14000f834`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000340e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400034b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000340e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400034b2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003479`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400034f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003479`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400034f3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000344c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000344c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000348f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003519`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000348f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003519`

## pseudocode

```c
void __fastcall WanpRemoveConnections(char a1, int a2)
{
  unsigned int v4; // edi
  KIRQL i; // bp
  __int64 v6; // rbx

  v4 = 1;
  for ( i = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock); v4 < g_ulConnTableSize; ++v4 )
  {
    v6 = *((_QWORD *)g_puipConnTable + v4);
    if ( v6 )
    {
      KeAcquireSpinLockAtDpcLevel(*(PKSPIN_LOCK *)(v6 + 80));
      if ( !*(_DWORD *)(v6 + 100) && *(_BYTE *)(v6 + 4) == a1 && *(_DWORD *)(v6 + 268) == a2 )
      {
        KeReleaseSpinLockFromDpcLevel(*(PKSPIN_LOCK *)(v6 + 80));
        KeReleaseSpinLock(&g_rlConnTableLock, i);
        WanpLinkDownIndication(0, v4);
        _InterlockedIncrement(&dword_140009764);
        i = KeAcquireSpinLockRaiseToDpc(&g_rlConnTableLock);
        if ( v4 >= g_ulConnTableSize )
          break;
        if ( *((_QWORD *)g_puipConnTable + v4) == v6 )
        {
          *((_QWORD *)g_puipConnTable + v4) = 0;
          --g_rgulConns[0];
        }
      }
      else
      {
        KeReleaseSpinLockFromDpcLevel(*(PKSPIN_LOCK *)(v6 + 80));
      }
    }
  }
  KeReleaseSpinLock(&g_rlConnTableLock, i);
}

```

## disassembly

```asm
0x1400033f4  push    rbx
0x1400033f6  push    rbp
0x1400033f7  push    rsi
0x1400033f8  push    rdi
0x1400033f9  push    r14
0x1400033fb  push    r15
0x1400033fd  sub     rsp, 28h
0x140003401  mov     r15b, cl
0x140003404  mov     r14d, edx
0x140003407  lea     rcx, g_rlConnTableLock; SpinLock
0x14000340e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003415  nop     dword ptr [rax+rax+00h]
0x14000341a  mov     r8d, cs:g_ulConnTableSize
0x140003421  mov     edi, 1
0x140003426  mov     bpl, al
0x140003429  cmp     r8d, edi
0x14000342c  jbe     loc_14000350F
0x140003432  mov     rcx, cs:g_puipConnTable
0x140003439  mov     esi, edi
0x14000343b  mov     rbx, [rcx+rsi*8]
0x14000343f  test    rbx, rbx
0x140003442  jz      loc_1400034FF
0x140003448  mov     rcx, [rbx+50h]; SpinLock
0x14000344c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003453  nop     dword ptr [rax+rax+00h]
0x140003458  cmp     dword ptr [rbx+64h], 0
0x14000345c  jnz     loc_1400034EF
0x140003462  cmp     [rbx+4], r15b
0x140003466  jnz     loc_1400034EF
0x14000346c  cmp     [rbx+10Ch], r14d
0x140003473  jnz     short loc_1400034EF
0x140003475  mov     rcx, [rbx+50h]; SpinLock
0x140003479  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003480  nop     dword ptr [rax+rax+00h]
0x140003485  mov     dl, bpl; NewIrql
0x140003488  lea     rcx, g_rlConnTableLock; SpinLock
0x14000348f  call    cs:__imp_KeReleaseSpinLock
0x140003496  nop     dword ptr [rax+rax+00h]
0x14000349b  mov     edx, edi
0x14000349d  xor     ecx, ecx
0x14000349f  call    WanpLinkDownIndication
0x1400034a4  lock inc cs:dword_140009764
0x1400034ab  lea     rcx, g_rlConnTableLock; SpinLock
0x1400034b2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400034b9  nop     dword ptr [rax+rax+00h]
0x1400034be  mov     bpl, al
0x1400034c1  mov     eax, cs:g_ulConnTableSize
0x1400034c7  cmp     edi, eax
0x1400034c9  jnb     short loc_14000350F
0x1400034cb  mov     rax, cs:g_puipConnTable
0x1400034d2  cmp     [rax+rsi*8], rbx
0x1400034d6  jnz     short loc_1400034FF
0x1400034d8  mov     rax, cs:g_puipConnTable
0x1400034df  mov     qword ptr [rax+rsi*8], 0
0x1400034e7  dec     cs:g_rgulConns
0x1400034ed  jmp     short loc_1400034FF
0x1400034ef  mov     rcx, [rbx+50h]; SpinLock
0x1400034f3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400034fa  nop     dword ptr [rax+rax+00h]
0x1400034ff  mov     eax, cs:g_ulConnTableSize
0x140003505  inc     edi
0x140003507  cmp     edi, eax
0x140003509  jb      loc_140003432
0x14000350f  mov     dl, bpl; NewIrql
0x140003512  lea     rcx, g_rlConnTableLock; SpinLock
0x140003519  call    cs:__imp_KeReleaseSpinLock
0x140003520  nop     dword ptr [rax+rax+00h]
0x140003525  add     rsp, 28h
0x140003529  pop     r15
0x14000352b  pop     r14
0x14000352d  pop     rdi
0x14000352e  pop     rsi
0x14000352f  pop     rbp
0x140003530  pop     rbx
0x140003531  retn
```
