# XPartCreateInterrupt

- ea: `0x140012854`
- end: `0x140012a1d`
- name: `XPartCreateInterrupt`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400104c8`

## callees

- `0x140012854`
- `0x1400131f0`
- `0x1400132a8`
- `0x140013408`
- `0x140017190`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400129ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400129ff`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400129d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400129d7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400128d3`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400128d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001287a`
- `ntoskrnl!ExAllocatePool2` at `0x14001287a`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001289f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14001289f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400128ae`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400128ae`
- `ntoskrnl!ExRundownCompleted` at `0x1400128bd`
- `ntoskrnl!ExRundownCompleted` at `0x1400128bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400129bd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400129bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001297f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001297f`

## pseudocode

```c
__int64 __fastcall XPartCreateInterrupt(ULONG_PTR a1, __int64 a2, struct _EX_RUNDOWN_REF **a3)
{
  struct _EX_RUNDOWN_REF *Pool2; // rax
  struct _EX_RUNDOWN_REF *v7; // rdi
  struct _EX_RUNDOWN_REF *v9; // rbx
  unsigned int v10; // ebp
  int v11; // ebx
  __int16 v12; // cx
  unsigned int v13; // eax
  __int64 (__fastcall *v14)(struct _EX_RUNDOWN_REF *, __int64); // rax
  KIRQL v15; // al
  _QWORD *v16; // rdx

  Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(64, 176, 1937072726);
  v7 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = Pool2 + 6;
  ExInitializeRundownProtection(Pool2 + 6);
  ExWaitForRundownProtectionRelease(v9);
  ExRundownCompleted(v9);
  ExAcquireFastMutex((PFAST_MUTEX)(a1 + 240));
  if ( *(_BYTE *)(a2 + 22) )
  {
    v10 = -1;
    v11 = XPartRelIdSet(a1, *(unsigned int *)(a2 + 8), v7);
    if ( v11 >= 0 )
    {
      v10 = *(_DWORD *)(a2 + 8);
      v12 = *(_WORD *)(a2 + 26);
LABEL_9:
      v7->Count = a1;
      v7[3].Count = *(ULONG_PTR *)a2;
      LODWORD(v7[4].Count) = v10;
      WORD2(v7[4].Ptr) = v12;
      v14 = *(__int64 (__fastcall **)(struct _EX_RUNDOWN_REF *, __int64))(a1 + 1080);
      if ( !v14 || (v11 = v14(v7, a2), v11 >= 0) )
      {
        if ( _InterlockedIncrement64((volatile signed __int64 *)(a1 + 160)) <= 1 )
          __fastfail(0xEu);
        v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 296));
        v16 = *(_QWORD **)(a1 + 312);
        if ( *v16 != a1 + 304 )
          __fastfail(3u);
        v7[1].Count = a1 + 304;
        v7[2].Count = (ULONG_PTR)v16;
        *v16 = v7 + 1;
        *(_QWORD *)(a1 + 312) = v7 + 1;
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 296), v15);
        *a3 = v7;
        v10 = -1;
        v7 = 0;
        v11 = 0;
      }
    }
  }
  else
  {
    v13 = XPartRelIdAllocate(a1, v7);
    v10 = v13;
    if ( v13 != -1 )
    {
      v12 = v13;
      goto LABEL_9;
    }
    v11 = -1073741670;
  }
  ExReleaseFastMutex((PFAST_MUTEX)(a1 + 240));
  if ( v10 != -1 )
    XPartRelIdFree(a1, v10);
  if ( v7 )
    ExFreePoolWithTag(v7, 0x73756256u);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140012854  push    rbx
0x140012856  push    rbp
0x140012857  push    rsi
0x140012858  push    rdi
0x140012859  push    r12
0x14001285b  push    r13
0x14001285d  push    r14
0x14001285f  sub     rsp, 20h
0x140012863  mov     r14, rdx
0x140012866  mov     r13, r8
0x140012869  mov     edx, 0B0h
0x14001286e  mov     rsi, rcx
0x140012871  mov     r8d, 73756256h
0x140012877  lea     ecx, [rdx-70h]
0x14001287a  call    cs:__imp_ExAllocatePool2
0x140012881  nop     dword ptr [rax+rax+00h]
0x140012886  mov     rdi, rax
0x140012889  test    rax, rax
0x14001288c  jnz     short loc_140012898
0x14001288e  mov     eax, 0C000009Ah
0x140012893  jmp     loc_140012A0D
0x140012898  lea     rbx, [rax+30h]
0x14001289c  mov     rcx, rbx; RunRef
0x14001289f  call    cs:__imp_ExInitializeRundownProtection
0x1400128a6  nop     dword ptr [rax+rax+00h]
0x1400128ab  mov     rcx, rbx; RunRef
0x1400128ae  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400128b5  nop     dword ptr [rax+rax+00h]
0x1400128ba  mov     rcx, rbx; RunRef
0x1400128bd  call    cs:__imp_ExRundownCompleted
0x1400128c4  nop     dword ptr [rax+rax+00h]
0x1400128c9  lea     r12, [rsi+0F0h]
0x1400128d0  mov     rcx, r12; FastMutex
0x1400128d3  call    cs:__imp_ExAcquireFastMutex
0x1400128da  nop     dword ptr [rax+rax+00h]
0x1400128df  cmp     byte ptr [r14+16h], 0
0x1400128e4  mov     rcx, rsi
0x1400128e7  jz      short loc_14001290D
0x1400128e9  mov     edx, [r14+8]
0x1400128ed  mov     r8, rdi
0x1400128f0  or      ebp, 0FFFFFFFFh
0x1400128f3  call    XPartRelIdSet
0x1400128f8  mov     ebx, eax
0x1400128fa  test    eax, eax
0x1400128fc  js      loc_1400129D4
0x140012902  mov     ebp, [r14+8]
0x140012906  movzx   ecx, word ptr [r14+1Ah]
0x14001290b  jmp     short loc_140012929
0x14001290d  mov     rdx, rdi
0x140012910  call    XPartRelIdAllocate
0x140012915  mov     ebp, eax
0x140012917  cmp     eax, 0FFFFFFFFh
0x14001291a  jnz     short loc_140012926
0x14001291c  mov     ebx, 0C000009Ah
0x140012921  jmp     loc_1400129D4
0x140012926  movzx   ecx, ax
0x140012929  mov     [rdi], rsi
0x14001292c  mov     rax, [r14]
0x14001292f  mov     [rdi+18h], rax
0x140012933  mov     [rdi+20h], ebp
0x140012936  mov     [rdi+24h], cx
0x14001293a  mov     rax, [rsi+438h]
0x140012941  test    rax, rax
0x140012944  jz      short loc_140012957
0x140012946  mov     rdx, r14
0x140012949  mov     rcx, rdi
0x14001294c  call    _guard_dispatch_icall
0x140012951  mov     ebx, eax
0x140012953  test    eax, eax
0x140012955  js      short loc_1400129D4
0x140012957  mov     eax, 1
0x14001295c  lock xadd [rsi+0A0h], rax
0x140012965  inc     rax
0x140012968  cmp     rax, 1
0x14001296c  jg      short loc_140012975
0x14001296e  mov     ecx, 0Eh
0x140012973  int     29h; Win8: RtlFailFast(ecx)
0x140012975  lea     rbx, [rsi+128h]
0x14001297c  mov     rcx, rbx; SpinLock
0x14001297f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012986  nop     dword ptr [rax+rax+00h]
0x14001298b  lea     rcx, [rsi+130h]
0x140012992  mov     r8b, al
0x140012995  mov     rdx, [rcx+8]
0x140012999  cmp     [rdx], rcx
0x14001299c  jz      short loc_1400129A5
0x14001299e  mov     ecx, 3
0x1400129a3  int     29h; Win8: RtlFailFast(ecx)
0x1400129a5  lea     rax, [rdi+8]
0x1400129a9  mov     [rax], rcx
0x1400129ac  mov     [rax+8], rdx
0x1400129b0  mov     [rdx], rax
0x1400129b3  mov     dl, r8b; NewIrql
0x1400129b6  mov     [rcx+8], rax
0x1400129ba  mov     rcx, rbx; SpinLock
0x1400129bd  call    cs:__imp_KeReleaseSpinLock
0x1400129c4  nop     dword ptr [rax+rax+00h]
0x1400129c9  mov     [r13+0], rdi
0x1400129cd  or      ebp, 0FFFFFFFFh
0x1400129d0  xor     edi, edi
0x1400129d2  xor     ebx, ebx
0x1400129d4  mov     rcx, r12; FastMutex
0x1400129d7  call    cs:__imp_ExReleaseFastMutex
0x1400129de  nop     dword ptr [rax+rax+00h]
0x1400129e3  cmp     ebp, 0FFFFFFFFh
0x1400129e6  jz      short loc_1400129F2
0x1400129e8  mov     edx, ebp
0x1400129ea  mov     rcx, rsi
0x1400129ed  call    XPartRelIdFree
0x1400129f2  test    rdi, rdi
0x1400129f5  jz      short loc_140012A0B
0x1400129f7  mov     edx, 73756256h; Tag
0x1400129fc  mov     rcx, rdi; P
0x1400129ff  call    cs:__imp_ExFreePoolWithTag
0x140012a06  nop     dword ptr [rax+rax+00h]
0x140012a0b  mov     eax, ebx
0x140012a0d  add     rsp, 20h
0x140012a11  pop     r14
0x140012a13  pop     r13
0x140012a15  pop     r12
0x140012a17  pop     rdi
0x140012a18  pop     rsi
0x140012a19  pop     rbp
0x140012a1a  pop     rbx
0x140012a1b  retn
```
