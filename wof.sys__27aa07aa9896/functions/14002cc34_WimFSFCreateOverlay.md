# WimFSFCreateOverlay

- ea: `0x14002cc34`
- end: `0x14002ce95`
- name: `WimFSFCreateOverlay`
- size: `609`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140026440`
- `0x14002d424`
- `0x14003c280`

## callees

- `0x1400116c0`
- `0x1400119c0`
- `0x140022008`
- `0x14002cc34`

## import_xrefs

- `ntoskrnl!ExRundownCompleted` at `0x14002cda1`
- `ntoskrnl!ExRundownCompleted` at `0x14002cda1`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002cce5`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14002cce5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002ce75`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002cde8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ce69`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002cde8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14002ce69`
- `ntoskrnl!KeInitializeEvent` at `0x14002ccce`
- `ntoskrnl!KeInitializeEvent` at `0x14002ccce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cd2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce10`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cc67`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cd11`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cc67`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002cd11`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002cd91`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002cd91`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002cd4c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002cd4c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002cdb9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002cdb9`

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
0x14002cc34  mov     rax, rsp
0x14002cc37  push    rbx
0x14002cc38  push    rbp
0x14002cc39  push    rsi
0x14002cc3a  push    rdi
0x14002cc3b  push    r14
0x14002cc3d  push    r15
0x14002cc3f  sub     rsp, 28h
0x14002cc43  mov     r14, r8
0x14002cc46  mov     qword ptr [rax+40h], 0
0x14002cc4e  mov     rsi, rdx
0x14002cc51  mov     rbp, rcx
0x14002cc54  mov     edx, 0B0h; NumberOfBytes
0x14002cc59  mov     ecx, 200h; PoolType
0x14002cc5e  mov     r8d, 6F767077h; Tag
0x14002cc64  mov     rbx, r9
0x14002cc67  call    cs:__imp_ExAllocatePoolWithTag
0x14002cc6e  nop     dword ptr [rax+rax+00h]
0x14002cc73  mov     rdi, rax
0x14002cc76  test    rax, rax
0x14002cc79  jnz     short loc_14002CC85
0x14002cc7b  mov     eax, 0C000009Ah
0x14002cc80  jmp     loc_14002CE87
0x14002cc85  xor     edx, edx; Val
0x14002cc87  mov     r8d, 0A8h; Size
0x14002cc8d  mov     rcx, rdi; void *
0x14002cc90  call    memset
0x14002cc95  mov     [rdi+8], rdi
0x14002cc99  lea     rax, [rdi+10h]
0x14002cc9d  mov     [rdi], rdi
0x14002cca0  lea     rcx, [rdi+88h]; Event
0x14002cca7  mov     [rax+8], rax
0x14002ccab  xor     r8d, r8d; State
0x14002ccae  mov     [rax], rax
0x14002ccb1  mov     dword ptr [rdi+70h], 1
0x14002ccb8  mov     qword ptr [rdi+78h], 0
0x14002ccc0  lea     edx, [r8+1]; Type
0x14002ccc4  mov     dword ptr [rdi+80h], 0
0x14002ccce  call    cs:__imp_KeInitializeEvent
0x14002ccd5  nop     dword ptr [rax+rax+00h]
0x14002ccda  lea     rcx, [rdi+0A8h]; RunRef
0x14002cce1  mov     [rdi+60h], rcx
0x14002cce5  call    cs:__imp_ExInitializeRundownProtection
0x14002ccec  nop     dword ptr [rax+rax+00h]
0x14002ccf1  test    r14, r14
0x14002ccf4  jz      short loc_14002CD4C
0x14002ccf6  movzx   eax, word ptr [r14]
0x14002ccfa  mov     ecx, 1; PoolType
0x14002ccff  mov     [rdi+3Ah], ax
0x14002cd03  mov     r8d, 66637077h; Tag
0x14002cd09  mov     [rdi+38h], ax
0x14002cd0d  movzx   edx, word ptr [r14]; NumberOfBytes
0x14002cd11  call    cs:__imp_ExAllocatePoolWithTag
0x14002cd18  nop     dword ptr [rax+rax+00h]
0x14002cd1d  mov     [rdi+40h], rax
0x14002cd21  test    rax, rax
0x14002cd24  jnz     short loc_14002CD3C
0x14002cd26  xor     edx, edx; Tag
0x14002cd28  mov     rcx, rdi; P
0x14002cd2b  call    cs:__imp_ExFreePoolWithTag
0x14002cd32  nop     dword ptr [rax+rax+00h]
0x14002cd37  jmp     loc_14002CC7B
0x14002cd3c  movzx   r8d, word ptr [r14]; Size
0x14002cd40  mov     rcx, rax; void *
0x14002cd43  mov     rdx, [r14+8]; Src
0x14002cd47  call    memmove
0x14002cd4c  call    cs:__imp_KeEnterCriticalRegion
0x14002cd53  nop     dword ptr [rax+rax+00h]
0x14002cd58  mov     rax, [rsp+58h+arg_20]
0x14002cd60  mov     [rdi+58h], rbx
0x14002cd64  mov     qword ptr [rdi+68h], 0
0x14002cd6c  test    rax, rax
0x14002cd6f  jz      short loc_14002CD79
0x14002cd71  movups  xmm0, xmmword ptr [rax]
0x14002cd74  movdqu  xmmword ptr [rdi+48h], xmm0
0x14002cd79  mov     eax, [rsp+58h+arg_28]
0x14002cd80  mov     rcx, [rdi+60h]; RunRef
0x14002cd84  mov     [rdi+34h], eax
0x14002cd87  mov     eax, [rsp+58h+arg_30]
0x14002cd8e  mov     [rdi+30h], eax
0x14002cd91  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002cd98  nop     dword ptr [rax+rax+00h]
0x14002cd9d  mov     rcx, [rdi+60h]; RunRef
0x14002cda1  call    cs:__imp_ExRundownCompleted
0x14002cda8  nop     dword ptr [rax+rax+00h]
0x14002cdad  mov     eax, cs:dword_14001A2FC
0x14002cdb3  mov     rcx, rsi
0x14002cdb6  sub     rcx, rax; FastMutex
0x14002cdb9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002cdc0  nop     dword ptr [rax+rax+00h]
0x14002cdc5  lea     r8, [rsp+58h+arg_38]
0x14002cdcd  mov     rdx, rbx
0x14002cdd0  mov     rcx, rsi
0x14002cdd3  call    WimFSFFindOverlayByDataSourceUnsafe
0x14002cdd8  test    eax, eax
0x14002cdda  js      short loc_14002CE36
0x14002cddc  mov     eax, cs:dword_14001A2FC
0x14002cde2  sub     rsi, rax
0x14002cde5  mov     rcx, rsi; FastMutex
0x14002cde8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002cdef  nop     dword ptr [rax+rax+00h]
0x14002cdf4  mov     rcx, [rdi+40h]; P
0x14002cdf8  test    rcx, rcx
0x14002cdfb  jz      short loc_14002CE0B
0x14002cdfd  xor     edx, edx; Tag
0x14002cdff  call    cs:__imp_ExFreePoolWithTag
0x14002ce06  nop     dword ptr [rax+rax+00h]
0x14002ce0b  xor     edx, edx; Tag
0x14002ce0d  mov     rcx, rdi; P
0x14002ce10  call    cs:__imp_ExFreePoolWithTag
0x14002ce17  nop     dword ptr [rax+rax+00h]
0x14002ce1c  mov     rax, [rsp+58h+arg_38]
0x14002ce24  mov     [rbp+0], rax
0x14002ce28  call    cs:__imp_KeLeaveCriticalRegion
0x14002ce2f  nop     dword ptr [rax+rax+00h]
0x14002ce34  jmp     short loc_14002CE85
0x14002ce36  lea     rax, [rsi+8]
0x14002ce3a  mov     rcx, [rax]
0x14002ce3d  cmp     [rcx+8], rax
0x14002ce41  jz      short loc_14002CE4A
0x14002ce43  mov     ecx, 3
0x14002ce48  int     29h; Win8: RtlFailFast(ecx)
0x14002ce4a  mov     [rdi], rcx
0x14002ce4d  mov     [rdi+8], rax
0x14002ce51  mov     [rcx+8], rdi
0x14002ce55  mov     [rax], rdi
0x14002ce58  lock or dword ptr [rdi+28h], 1
0x14002ce5d  mov     eax, cs:dword_14001A2FC
0x14002ce63  sub     rsi, rax
0x14002ce66  mov     rcx, rsi; FastMutex
0x14002ce69  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002ce70  nop     dword ptr [rax+rax+00h]
0x14002ce75  call    cs:__imp_KeLeaveCriticalRegion
0x14002ce7c  nop     dword ptr [rax+rax+00h]
0x14002ce81  mov     [rbp+0], rdi
0x14002ce85  xor     eax, eax
0x14002ce87  add     rsp, 28h
0x14002ce8b  pop     r15
0x14002ce8d  pop     r14
0x14002ce8f  pop     rdi
0x14002ce90  pop     rsi
0x14002ce91  pop     rbp
0x14002ce92  pop     rbx
0x14002ce93  retn
```
