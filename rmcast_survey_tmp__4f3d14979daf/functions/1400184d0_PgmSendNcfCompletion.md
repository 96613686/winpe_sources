# PgmSendNcfCompletion

- ea: `0x1400184d0`
- end: `0x14001859c`
- name: `PgmSendNcfCompletion`
- size: `204`
- prototype: `void __fastcall(__int64, void *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400067f4`
- `0x1400184d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001856b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001856b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400184ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400184ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018584`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018584`

## pseudocode

```c
void __fastcall PgmSendNcfCompletion(__int64 a1, void *a2, int a3)
{
  KSPIN_LOCK *v3; // rsi
  KIRQL v7; // r14

  v3 = (KSPIN_LOCK *)(a1 + 360);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  if ( a3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        44,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)a3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
  }
  KeReleaseSpinLock(v3, v7);
  PgmDereferenceSessionCommon(a1);
  ExFreePoolWithTag(a2, 0);
}

```

## disassembly

```asm
0x1400184d0  push    rbx
0x1400184d2  push    rbp
0x1400184d3  push    rsi
0x1400184d4  push    rdi
0x1400184d5  push    r14
0x1400184d7  sub     rsp, 20h
0x1400184db  lea     rsi, [rcx+168h]
0x1400184e2  mov     rdi, rcx
0x1400184e5  mov     rcx, rsi; SpinLock
0x1400184e8  mov     ebx, r8d
0x1400184eb  mov     rbp, rdx
0x1400184ee  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400184f5  nop     dword ptr [rax+rax+00h]
0x1400184fa  mov     r14b, al
0x1400184fd  test    ebx, ebx
0x1400184ff  js      short loc_140018533
0x140018501  mov     rcx, cs:WPP_GLOBAL_Control
0x140018508  lea     r8, WPP_GLOBAL_Control
0x14001850f  cmp     rcx, r8
0x140018512  jz      short loc_140018565
0x140018514  mov     edx, [rcx+2Ch]
0x140018517  test    dl, 10h
0x14001851a  jz      short loc_140018565
0x14001851c  mov     rcx, [rcx+18h]
0x140018520  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018527  mov     edx, 2Bh ; '+'
0x14001852c  call    WPP_SF_
0x140018531  jmp     short loc_140018565
0x140018533  mov     rcx, cs:WPP_GLOBAL_Control
0x14001853a  lea     r8, WPP_GLOBAL_Control
0x140018541  cmp     rcx, r8
0x140018544  jz      short loc_140018565
0x140018546  mov     eax, [rcx+2Ch]
0x140018549  test    al, 2
0x14001854b  jz      short loc_140018565
0x14001854d  mov     rcx, [rcx+18h]
0x140018551  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140018558  mov     edx, 2Ch ; ','
0x14001855d  mov     r9d, ebx
0x140018560  call    WPP_SF_d
0x140018565  mov     dl, r14b; NewIrql
0x140018568  mov     rcx, rsi; SpinLock
0x14001856b  call    cs:__imp_KeReleaseSpinLock
0x140018572  nop     dword ptr [rax+rax+00h]
0x140018577  mov     rcx, rdi
0x14001857a  call    PgmDereferenceSessionCommon
0x14001857f  xor     edx, edx; Tag
0x140018581  mov     rcx, rbp; P
0x140018584  call    cs:__imp_ExFreePoolWithTag
0x14001858b  nop     dword ptr [rax+rax+00h]
0x140018590  add     rsp, 20h
0x140018594  pop     r14
0x140018596  pop     rdi
0x140018597  pop     rsi
0x140018598  pop     rbp
0x140018599  pop     rbx
0x14001859a  retn
```
