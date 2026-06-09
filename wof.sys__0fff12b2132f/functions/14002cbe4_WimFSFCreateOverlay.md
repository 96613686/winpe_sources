# WimFSFCreateOverlay

- ea: `0x14002cbe4`
- end: `0x14002ce45`
- name: `WimFSFCreateOverlay`
- size: `609`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const void **, __int64, _OWORD *, int, int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400263f0`
- `0x14002d3d4`
- `0x14003c230`

## callees

- `0x1400116c0`
- `0x1400119c0`
- `0x140022008`
- `0x14002cbe4`

## import_xrefs

- `ntoskrnl!ExRundownCompleted` at `0x14002cd51`
- `ntoskrnl!ExRundownCompleted` at `0x14002cd51`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002cc95`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002cc95`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002cdd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce25`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002cdd8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce25`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002cd98`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ce19`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002cd98`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ce19`
- `ntoskrnl!KeInitializeEvent` at `0x14002cc7e`
- `ntoskrnl!KeInitializeEvent` at `0x14002cc7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ccdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ccdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdc0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cc17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ccc1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cc17`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002ccc1`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002cd41`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002cd41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ccfc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002ccfc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002cd69`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002cd69`

## pseudocode

```c
__int64 __fastcall WimFSFCreateOverlay(
        _QWORD *a1,
        __int64 a2,
        const void **a3,
        __int64 a4,
        _OWORD *a5,
        int a6,
        int a7,
        __int64 a8)
{
  char *PoolWithTag; // rax
  char *v13; // rdi
  __int16 v15; // ax
  PVOID v16; // rax
  struct _EX_RUNDOWN_REF *v17; // rcx
  void *v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx

  a8 = 0;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0xB0u, 0x6F767077u);
  v13 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0xA8u);
  *((_QWORD *)v13 + 1) = v13;
  *(_QWORD *)v13 = v13;
  *((_QWORD *)v13 + 3) = v13 + 16;
  *((_QWORD *)v13 + 2) = v13 + 16;
  *((_DWORD *)v13 + 28) = 1;
  *((_QWORD *)v13 + 15) = 0;
  *((_DWORD *)v13 + 32) = 0;
  KeInitializeEvent((PRKEVENT)(v13 + 136), SynchronizationEvent, 0);
  *((_QWORD *)v13 + 12) = v13 + 168;
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)v13 + 21);
  if ( a3 )
  {
    v15 = *(_WORD *)a3;
    *((_WORD *)v13 + 29) = *(_WORD *)a3;
    *((_WORD *)v13 + 28) = v15;
    v16 = ExAllocatePoolWithTag(PagedPool, *(unsigned __int16 *)a3, 0x66637077u);
    *((_QWORD *)v13 + 8) = v16;
    if ( !v16 )
    {
      ExFreePoolWithTag(v13, 0);
      return 3221225626LL;
    }
    memmove(v16, a3[1], *(unsigned __int16 *)a3);
  }
  KeEnterCriticalRegion();
  *((_QWORD *)v13 + 11) = a4;
  *((_QWORD *)v13 + 13) = 0;
  if ( a5 )
    *(_OWORD *)(v13 + 72) = *a5;
  v17 = (struct _EX_RUNDOWN_REF *)*((_QWORD *)v13 + 12);
  *((_DWORD *)v13 + 13) = a6;
  *((_DWORD *)v13 + 12) = a7;
  ExWaitForRundownProtectionRelease(v17);
  ExRundownCompleted(*((PEX_RUNDOWN_REF *)v13 + 12));
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 - (unsigned int)dword_14001A2FC));
  if ( (int)WimFSFFindOverlayByDataSourceUnsafe(a2, a4, &a8) < 0 )
  {
    v19 = (_QWORD *)(a2 + 8);
    v20 = *(_QWORD *)(a2 + 8);
    if ( *(_QWORD *)(v20 + 8) != a2 + 8 )
      __fastfail(3u);
    *(_QWORD *)v13 = v20;
    *((_QWORD *)v13 + 1) = v19;
    *(_QWORD *)(v20 + 8) = v13;
    *v19 = v13;
    _InterlockedOr((volatile signed __int32 *)v13 + 10, 1u);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 - (unsigned int)dword_14001A2FC));
    KeLeaveCriticalRegion();
    *a1 = v13;
  }
  else
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 - (unsigned int)dword_14001A2FC));
    v18 = (void *)*((_QWORD *)v13 + 8);
    if ( v18 )
      ExFreePoolWithTag(v18, 0);
    ExFreePoolWithTag(v13, 0);
    *a1 = a8;
    KeLeaveCriticalRegion();
  }
  return 0;
}

```

## disassembly

```asm
0x14002cbe4  mov     rax, rsp
0x14002cbe7  push    rbx
0x14002cbe8  push    rbp
0x14002cbe9  push    rsi
0x14002cbea  push    rdi
0x14002cbeb  push    r14
0x14002cbed  push    r15
0x14002cbef  sub     rsp, 28h
0x14002cbf3  mov     r14, r8
0x14002cbf6  mov     qword ptr [rax+40h], 0
0x14002cbfe  mov     rsi, rdx
0x14002cc01  mov     rbp, rcx
0x14002cc04  mov     edx, 0B0h; NumberOfBytes
0x14002cc09  mov     ecx, 200h; PoolType
0x14002cc0e  mov     r8d, 6F767077h; Tag
0x14002cc14  mov     rbx, r9
0x14002cc17  call    cs:__imp_ExAllocatePoolWithTag
0x14002cc1e  nop     dword ptr [rax+rax+00h]
0x14002cc23  mov     rdi, rax
0x14002cc26  test    rax, rax
0x14002cc29  jnz     short loc_14002CC35
0x14002cc2b  mov     eax, 0C000009Ah
0x14002cc30  jmp     loc_14002CE37
0x14002cc35  xor     edx, edx; Val
0x14002cc37  mov     r8d, 0A8h; Size
0x14002cc3d  mov     rcx, rdi; void *
0x14002cc40  call    memset
0x14002cc45  mov     [rdi+8], rdi
0x14002cc49  lea     rax, [rdi+10h]
0x14002cc4d  mov     [rdi], rdi
0x14002cc50  lea     rcx, [rdi+88h]; Event
0x14002cc57  mov     [rax+8], rax
0x14002cc5b  xor     r8d, r8d; State
0x14002cc5e  mov     [rax], rax
0x14002cc61  mov     dword ptr [rdi+70h], 1
0x14002cc68  mov     qword ptr [rdi+78h], 0
0x14002cc70  lea     edx, [r8+1]; Type
0x14002cc74  mov     dword ptr [rdi+80h], 0
0x14002cc7e  call    cs:__imp_KeInitializeEvent
0x14002cc85  nop     dword ptr [rax+rax+00h]
0x14002cc8a  lea     rcx, [rdi+0A8h]; RunRef
0x14002cc91  mov     [rdi+60h], rcx
0x14002cc95  call    cs:__imp_ExInitializeRundownProtection
0x14002cc9c  nop     dword ptr [rax+rax+00h]
0x14002cca1  test    r14, r14
0x14002cca4  jz      short loc_14002CCFC
0x14002cca6  movzx   eax, word ptr [r14]
0x14002ccaa  mov     ecx, 1; PoolType
0x14002ccaf  mov     [rdi+3Ah], ax
0x14002ccb3  mov     r8d, 66637077h; Tag
0x14002ccb9  mov     [rdi+38h], ax
0x14002ccbd  movzx   edx, word ptr [r14]; NumberOfBytes
0x14002ccc1  call    cs:__imp_ExAllocatePoolWithTag
0x14002ccc8  nop     dword ptr [rax+rax+00h]
0x14002cccd  mov     [rdi+40h], rax
0x14002ccd1  test    rax, rax
0x14002ccd4  jnz     short loc_14002CCEC
0x14002ccd6  xor     edx, edx; Tag
0x14002ccd8  mov     rcx, rdi; P
0x14002ccdb  call    cs:__imp_ExFreePoolWithTag
0x14002cce2  nop     dword ptr [rax+rax+00h]
0x14002cce7  jmp     loc_14002CC2B
0x14002ccec  movzx   r8d, word ptr [r14]; Size
0x14002ccf0  mov     rcx, rax; void *
0x14002ccf3  mov     rdx, [r14+8]; Src
0x14002ccf7  call    memmove
0x14002ccfc  call    cs:__imp_KeEnterCriticalRegion
0x14002cd03  nop     dword ptr [rax+rax+00h]
0x14002cd08  mov     rax, [rsp+58h+arg_20]
0x14002cd10  mov     [rdi+58h], rbx
0x14002cd14  mov     qword ptr [rdi+68h], 0
0x14002cd1c  test    rax, rax
0x14002cd1f  jz      short loc_14002CD29
0x14002cd21  movups  xmm0, xmmword ptr [rax]
0x14002cd24  movdqu  xmmword ptr [rdi+48h], xmm0
0x14002cd29  mov     eax, [rsp+58h+arg_28]
0x14002cd30  mov     rcx, [rdi+60h]; RunRef
0x14002cd34  mov     [rdi+34h], eax
0x14002cd37  mov     eax, [rsp+58h+arg_30]
0x14002cd3e  mov     [rdi+30h], eax
0x14002cd41  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002cd48  nop     dword ptr [rax+rax+00h]
0x14002cd4d  mov     rcx, [rdi+60h]; RunRef
0x14002cd51  call    cs:__imp_ExRundownCompleted
0x14002cd58  nop     dword ptr [rax+rax+00h]
0x14002cd5d  mov     eax, cs:dword_14001A2FC
0x14002cd63  mov     rcx, rsi
0x14002cd66  sub     rcx, rax; FastMutex
0x14002cd69  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002cd70  nop     dword ptr [rax+rax+00h]
0x14002cd75  lea     r8, [rsp+58h+arg_38]
0x14002cd7d  mov     rdx, rbx
0x14002cd80  mov     rcx, rsi
0x14002cd83  call    WimFSFFindOverlayByDataSourceUnsafe
0x14002cd88  test    eax, eax
0x14002cd8a  js      short loc_14002CDE6
0x14002cd8c  mov     eax, cs:dword_14001A2FC
0x14002cd92  sub     rsi, rax
0x14002cd95  mov     rcx, rsi; FastMutex
0x14002cd98  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002cd9f  nop     dword ptr [rax+rax+00h]
0x14002cda4  mov     rcx, [rdi+40h]; P
0x14002cda8  test    rcx, rcx
0x14002cdab  jz      short loc_14002CDBB
0x14002cdad  xor     edx, edx; Tag
0x14002cdaf  call    cs:__imp_ExFreePoolWithTag
0x14002cdb6  nop     dword ptr [rax+rax+00h]
0x14002cdbb  xor     edx, edx; Tag
0x14002cdbd  mov     rcx, rdi; P
0x14002cdc0  call    cs:__imp_ExFreePoolWithTag
0x14002cdc7  nop     dword ptr [rax+rax+00h]
0x14002cdcc  mov     rax, [rsp+58h+arg_38]
0x14002cdd4  mov     [rbp+0], rax
0x14002cdd8  call    cs:__imp_KeLeaveCriticalRegion
0x14002cddf  nop     dword ptr [rax+rax+00h]
0x14002cde4  jmp     short loc_14002CE35
0x14002cde6  lea     rax, [rsi+8]
0x14002cdea  mov     rcx, [rax]
0x14002cded  cmp     [rcx+8], rax
0x14002cdf1  jz      short loc_14002CDFA
0x14002cdf3  mov     ecx, 3
0x14002cdf8  int     29h; Win8: RtlFailFast(ecx)
0x14002cdfa  mov     [rdi], rcx
0x14002cdfd  mov     [rdi+8], rax
0x14002ce01  mov     [rcx+8], rdi
0x14002ce05  mov     [rax], rdi
0x14002ce08  lock or dword ptr [rdi+28h], 1
0x14002ce0d  mov     eax, cs:dword_14001A2FC
0x14002ce13  sub     rsi, rax
0x14002ce16  mov     rcx, rsi; FastMutex
0x14002ce19  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002ce20  nop     dword ptr [rax+rax+00h]
0x14002ce25  call    cs:__imp_KeLeaveCriticalRegion
0x14002ce2c  nop     dword ptr [rax+rax+00h]
0x14002ce31  mov     [rbp+0], rdi
0x14002ce35  xor     eax, eax
0x14002ce37  add     rsp, 28h
0x14002ce3b  pop     r15
0x14002ce3d  pop     r14
0x14002ce3f  pop     rdi
0x14002ce40  pop     rsi
0x14002ce41  pop     rbp
0x14002ce42  pop     rbx
0x14002ce43  retn
```
