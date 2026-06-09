# PgmSendSpmCompletion

- ea: `0x14001a260`
- end: `0x14001a32c`
- name: `PgmSendSpmCompletion`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400067f4`
- `0x14001a260`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001a2fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001a2fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a27e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001a27e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a314`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a314`

## pseudocode

```c
void __fastcall PgmSendSpmCompletion(__int64 a1, void *a2, int a3)
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
        29,
        WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
        (unsigned int)a3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids);
  }
  KeReleaseSpinLock(v3, v7);
  PgmDereferenceSessionCommon(a1);
  ExFreePoolWithTag(a2, 0);
}

```

## disassembly

```asm
0x14001a260  push    rbx
0x14001a262  push    rbp
0x14001a263  push    rsi
0x14001a264  push    rdi
0x14001a265  push    r14
0x14001a267  sub     rsp, 20h
0x14001a26b  lea     rsi, [rcx+168h]
0x14001a272  mov     rdi, rcx
0x14001a275  mov     rcx, rsi; SpinLock
0x14001a278  mov     ebx, r8d
0x14001a27b  mov     rbp, rdx
0x14001a27e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001a285  nop     dword ptr [rax+rax+00h]
0x14001a28a  mov     r14b, al
0x14001a28d  test    ebx, ebx
0x14001a28f  js      short loc_14001A2C3
0x14001a291  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a298  lea     r8, WPP_GLOBAL_Control
0x14001a29f  cmp     rcx, r8
0x14001a2a2  jz      short loc_14001A2F5
0x14001a2a4  mov     edx, [rcx+2Ch]
0x14001a2a7  test    dl, 10h
0x14001a2aa  jz      short loc_14001A2F5
0x14001a2ac  mov     rcx, [rcx+18h]
0x14001a2b0  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x14001a2b7  mov     edx, 1Ch
0x14001a2bc  call    WPP_SF_
0x14001a2c1  jmp     short loc_14001A2F5
0x14001a2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a2ca  lea     r8, WPP_GLOBAL_Control
0x14001a2d1  cmp     rcx, r8
0x14001a2d4  jz      short loc_14001A2F5
0x14001a2d6  mov     eax, [rcx+2Ch]
0x14001a2d9  test    al, 2
0x14001a2db  jz      short loc_14001A2F5
0x14001a2dd  mov     rcx, [rcx+18h]
0x14001a2e1  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x14001a2e8  mov     edx, 1Dh
0x14001a2ed  mov     r9d, ebx
0x14001a2f0  call    WPP_SF_d
0x14001a2f5  mov     dl, r14b; NewIrql
0x14001a2f8  mov     rcx, rsi; SpinLock
0x14001a2fb  call    cs:__imp_KeReleaseSpinLock
0x14001a302  nop     dword ptr [rax+rax+00h]
0x14001a307  mov     rcx, rdi
0x14001a30a  call    PgmDereferenceSessionCommon
0x14001a30f  xor     edx, edx; Tag
0x14001a311  mov     rcx, rbp; P
0x14001a314  call    cs:__imp_ExFreePoolWithTag
0x14001a31b  nop     dword ptr [rax+rax+00h]
0x14001a320  add     rsp, 20h
0x14001a324  pop     r14
0x14001a326  pop     rdi
0x14001a327  pop     rsi
0x14001a328  pop     rbp
0x14001a329  pop     rbx
0x14001a32a  retn
```
