# PgmSendNakCompletion

- ea: `0x140011fc0`
- end: `0x1400120ae`
- name: `PgmSendNakCompletion`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005038`
- `0x140005068`
- `0x1400067f4`
- `0x140011fc0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140012067`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001208e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012067`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001208e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011fe5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011fe5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012078`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012078`

## pseudocode

```c
void __fastcall PgmSendNakCompletion(__int64 a1, _DWORD *a2, int a3)
{
  KSPIN_LOCK *v3; // rdi
  KIRQL v7; // si

  v3 = (KSPIN_LOCK *)(a1 + 360);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 360));
  if ( a3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
        (unsigned int)a3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids);
  }
  if ( (*a2)-- == 1 )
  {
    KeReleaseSpinLock(v3, v7);
    ExFreePoolWithTag(a2, 0);
    PgmDereferenceSessionCommon(a1);
  }
  else
  {
    KeReleaseSpinLock(v3, v7);
  }
}

```

## disassembly

```asm
0x140011fc0  mov     [rsp+arg_0], rbx
0x140011fc5  mov     [rsp+arg_8], rbp
0x140011fca  push    rsi
0x140011fcb  push    rdi
0x140011fcc  push    r14
0x140011fce  sub     rsp, 20h
0x140011fd2  lea     rdi, [rcx+168h]
0x140011fd9  mov     r14, rcx
0x140011fdc  mov     rcx, rdi; SpinLock
0x140011fdf  mov     ebp, r8d
0x140011fe2  mov     rbx, rdx
0x140011fe5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011fec  nop     dword ptr [rax+rax+00h]
0x140011ff1  mov     sil, al
0x140011ff4  test    ebp, ebp
0x140011ff6  js      short loc_14001202A
0x140011ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x140011fff  lea     rdx, WPP_GLOBAL_Control
0x140012006  cmp     rcx, rdx
0x140012009  jz      short loc_14001205C
0x14001200b  mov     edx, [rcx+2Ch]
0x14001200e  test    dl, 10h
0x140012011  jz      short loc_14001205C
0x140012013  mov     rcx, [rcx+18h]
0x140012017  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001201e  mov     edx, 29h ; ')'
0x140012023  call    WPP_SF_
0x140012028  jmp     short loc_14001205C
0x14001202a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012031  lea     rdx, WPP_GLOBAL_Control
0x140012038  cmp     rcx, rdx
0x14001203b  jz      short loc_14001205C
0x14001203d  mov     eax, [rcx+2Ch]
0x140012040  test    al, 2
0x140012042  jz      short loc_14001205C
0x140012044  mov     rcx, [rcx+18h]
0x140012048  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x14001204f  mov     edx, 2Ah ; '*'
0x140012054  mov     r9d, ebp
0x140012057  call    WPP_SF_d
0x14001205c  add     dword ptr [rbx], 0FFFFFFFFh
0x14001205f  mov     dl, sil; NewIrql
0x140012062  mov     rcx, rdi; SpinLock
0x140012065  jnz     short loc_14001208E
0x140012067  call    cs:__imp_KeReleaseSpinLock
0x14001206e  nop     dword ptr [rax+rax+00h]
0x140012073  xor     edx, edx; Tag
0x140012075  mov     rcx, rbx; P
0x140012078  call    cs:__imp_ExFreePoolWithTag
0x14001207f  nop     dword ptr [rax+rax+00h]
0x140012084  mov     rcx, r14
0x140012087  call    PgmDereferenceSessionCommon
0x14001208c  jmp     short loc_14001209A
0x14001208e  call    cs:__imp_KeReleaseSpinLock
0x140012095  nop     dword ptr [rax+rax+00h]
0x14001209a  mov     rbx, [rsp+38h+arg_0]
0x14001209f  mov     rbp, [rsp+38h+arg_8]
0x1400120a4  add     rsp, 20h
0x1400120a8  pop     r14
0x1400120aa  pop     rdi
0x1400120ab  pop     rsi
0x1400120ac  retn
```
