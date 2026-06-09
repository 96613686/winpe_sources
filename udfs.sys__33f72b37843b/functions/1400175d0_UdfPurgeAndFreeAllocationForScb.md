# UdfPurgeAndFreeAllocationForScb

- ea: `0x1400175d0`
- end: `0x1400177a3`
- name: `UdfPurgeAndFreeAllocationForScb`
- size: `467`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14001662c`
- `0x1400177ac`

## callees

- `0x14000b128`
- `0x14000b24c`
- `0x14000c974`
- `0x14000ca54`
- `0x14000f8cc`
- `0x140015558`
- `0x140016e98`
- `0x1400175d0`
- `0x1400396b8`
- `0x14003be8c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140017667`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140017667`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400176a9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001de7f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400176a9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001de7f`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017623`
- `ntoskrnl!ExAcquireFastMutex` at `0x140017623`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017648`
- `ntoskrnl!ExReleaseFastMutex` at `0x140017648`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400176e6`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400176e6`

## pseudocode

```c
__int64 __fastcall UdfPurgeAndFreeAllocationForScb(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  char v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]

  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10000000) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      15,
      WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids,
      a2);
  }
  ExAcquireFastMutex(*(PFAST_MUTEX *)(a2 + 48));
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 40) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 296) = 0;
  ExReleaseFastMutex(*(PFAST_MUTEX *)(a2 + 48));
  *(_DWORD *)(a2 + 212) |= 0x200u;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1648LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1704LL) = KeGetCurrentThread();
  UdfMarkDeletedInScbTable(a1, a2);
  *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1704LL) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1648LL));
  UdfReleaseBlockReservation(v4, a2, 0);
  UdfCleanupReservationStructures(a2);
  v5 = *(_QWORD *)(a2 + 424);
  if ( v5 )
  {
    ++*(_DWORD *)(a2 + 204);
    CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(v5 + 8), 0, 0, 0);
    --*(_DWORD *)(a2 + 204);
  }
  if ( *(_DWORD *)(a2 + 376) )
    UdfSeqCacheTruncateDataForFile(a1, a2, 0);
  v6 = *(_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(v6 + 352) && (*(_DWORD *)(v6 + 48) & 0x20000000) == 0 && (*(_BYTE *)(a2 + 212) & 2) == 0 )
  {
    v8 = 0;
    UdfFreeAllocation(a1, a2, a2 + 232, 0, v8, 0);
    LOBYTE(v9) = 0;
    UdfFreeAllocation(a1, a2, a2 + 264, 0, v9, 0);
  }
  UdfUninitializeScbMcb(a2);
  return UdfFreeBlocksForScbFe(a1, a2);
}

```

## disassembly

```asm
0x1400175d0  mov     [rsp+arg_8], rbx
0x1400175d5  mov     [rsp+arg_10], rsi
0x1400175da  mov     [rsp+arg_0], rcx
0x1400175df  push    rdi
0x1400175e0  sub     rsp, 30h
0x1400175e4  mov     rbx, rdx
0x1400175e7  mov     rdi, rcx
0x1400175ea  lea     rax, WPP_GLOBAL_Control
0x1400175f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400175f8  cmp     rcx, rax
0x1400175fb  jz      short loc_14001761F
0x1400175fd  test    dword ptr [rcx+2Ch], 10000000h
0x140017604  jz      short loc_14001761F
0x140017606  mov     edx, 0Fh
0x14001760b  mov     r9, rbx
0x14001760e  lea     r8, WPP_3e271ebed6f63f8fe36d0f7ec1e80eae_Traceguids
0x140017615  mov     rcx, [rcx+18h]
0x140017619  call    WPP_SF_q
0x14001761e  nop
0x14001761f  mov     rcx, [rbx+30h]; FastMutex
0x140017623  call    cs:__imp_ExAcquireFastMutex
0x14001762a  nop     dword ptr [rax+rax+00h]
0x14001762f  xor     esi, esi
0x140017631  mov     [rbx+18h], rsi
0x140017635  mov     [rbx+28h], rsi
0x140017639  mov     [rbx+20h], rsi
0x14001763d  mov     [rbx+128h], rsi
0x140017644  mov     rcx, [rbx+30h]; FastMutex
0x140017648  call    cs:__imp_ExReleaseFastMutex
0x14001764f  nop     dword ptr [rax+rax+00h]
0x140017654  bts     dword ptr [rbx+0D4h], 9
0x14001765c  mov     rcx, [rdi+10h]
0x140017660  add     rcx, 670h; FastMutex
0x140017667  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001766e  nop     dword ptr [rax+rax+00h]
0x140017673  mov     rcx, gs:188h
0x14001767c  mov     rax, [rdi+10h]
0x140017680  mov     [rax+6A8h], rcx
0x140017687  mov     rdx, rbx
0x14001768a  mov     rcx, rdi
0x14001768d  call    UdfMarkDeletedInScbTable
0x140017692  nop
0x140017693  mov     rax, [rdi+10h]
0x140017697  mov     [rax+6A8h], rsi
0x14001769e  mov     rcx, [rdi+10h]
0x1400176a2  add     rcx, 670h; FastMutex
0x1400176a9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400176b0  nop     dword ptr [rax+rax+00h]
0x1400176b5  xor     r8d, r8d
0x1400176b8  mov     rdx, rbx
0x1400176bb  call    UdfReleaseBlockReservation
0x1400176c0  mov     rcx, rbx
0x1400176c3  call    UdfCleanupReservationStructures
0x1400176c8  mov     rcx, [rbx+1A8h]
0x1400176cf  test    rcx, rcx
0x1400176d2  jz      short loc_1400176F8
0x1400176d4  inc     dword ptr [rbx+0CCh]
0x1400176da  add     rcx, 8; SectionObjectPointer
0x1400176de  xor     r9d, r9d; Flags
0x1400176e1  xor     r8d, r8d; Length
0x1400176e4  xor     edx, edx; FileOffset
0x1400176e6  call    cs:__imp_CcPurgeCacheSection
0x1400176ed  nop     dword ptr [rax+rax+00h]
0x1400176f2  dec     dword ptr [rbx+0CCh]
0x1400176f8  cmp     [rbx+178h], esi
0x1400176fe  jz      short loc_14001770E
0x140017700  xor     r8d, r8d
0x140017703  mov     rdx, rbx
0x140017706  mov     rcx, rdi
0x140017709  call    UdfSeqCacheTruncateDataForFile
0x14001770e  mov     rax, [rdi+10h]
0x140017712  cmp     [rax+160h], rsi
0x140017719  jnz     short loc_140017771
0x14001771b  test    dword ptr [rax+30h], 20000000h
0x140017722  setz    cl
0x140017725  test    byte ptr [rbx+0D4h], 2
0x14001772c  setz    al
0x14001772f  test    al, cl
0x140017731  jz      short loc_140017771
0x140017733  lea     r8, [rbx+0E8h]
0x14001773a  mov     [rsp+38h+var_10], rsi
0x14001773f  mov     [rsp+38h+var_18], sil
0x140017744  xor     r9d, r9d
0x140017747  mov     rdx, rbx
0x14001774a  mov     rcx, rdi
0x14001774d  call    UdfFreeAllocation
0x140017752  lea     r8, [rbx+108h]
0x140017759  mov     [rsp+38h+var_10], rsi
0x14001775e  mov     [rsp+38h+var_18], sil
0x140017763  xor     r9d, r9d
0x140017766  mov     rdx, rbx
0x140017769  mov     rcx, rdi
0x14001776c  call    UdfFreeAllocation
0x140017771  mov     rcx, rbx
0x140017774  call    UdfUninitializeScbMcb
0x140017779  mov     rdx, rbx
0x14001777c  mov     rcx, rdi
0x14001777f  call    UdfFreeBlocksForScbFe
0x140017784  jmp     short loc_140017792
0x140017786  mov     rax, [rsp+38h+arg_0]
0x14001778b  mov     dword ptr [rax+18h], 0
0x140017792  mov     rbx, [rsp+38h+arg_8]
0x140017797  mov     rsi, [rsp+38h+arg_10]
0x14001779c  add     rsp, 30h
0x1400177a0  pop     rdi
0x1400177a1  retn
0x14001de58  push    rbp
0x14001de5a  sub     rsp, 30h
0x14001de5e  mov     rbp, rdx
0x14001de61  mov     rcx, [rbp+40h]
0x14001de65  mov     rax, [rcx+10h]
0x14001de69  mov     qword ptr [rax+6A8h], 0
0x14001de74  mov     rcx, [rcx+10h]
0x14001de78  add     rcx, 670h; FastMutex
0x14001de7f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14001de86  nop     dword ptr [rax+rax+00h]
0x14001de8b  nop
0x14001de8c  add     rsp, 30h
0x14001de90  pop     rbp
0x14001de91  retn
0x14001de93  push    rbp
0x14001de95  sub     rsp, 30h
0x14001de99  mov     rbp, rdx
0x14001de9c  mov     rdx, rcx
0x14001de9f  mov     rcx, [rbp+40h]
0x14001dea3  call    UdfExceptionFilter
0x14001dea8  nop
0x14001dea9  add     rsp, 30h
0x14001dead  pop     rbp
0x14001deae  retn
```
