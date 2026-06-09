# VhdmpiInitializeSectorBitmapTracking(_VHD1_BACKING_STORE *)

- ea: `0x14003cba8`
- end: `0x14003ccfd`
- name: `?VhdmpiInitializeSectorBitmapTracking@@YAJPEAU_VHD1_BACKING_STORE@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct _VHD1_BACKING_STORE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400bd7cc`

## callees

- `0x14001bc1c`
- `0x14001c088`
- `0x14002553c`
- `0x140025db0`
- `0x14003cba8`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003cc1b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003cc1b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003cbc1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003cbc1`
- `ntoskrnl!ExAllocatePool2` at `0x14003ccc1`
- `ntoskrnl!ExAllocatePool2` at `0x14003ccc1`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeSectorBitmapTracking(struct _VHD1_BACKING_STORE *a1)
{
  int AppropriateSectorBitmaps; // esi
  __int64 i; // rdx
  char *v4; // rcx
  __int64 v5; // rax
  __int64 Pool2; // rax

  KeInitializeSpinLock((PKSPIN_LOCK)a1 + 548);
  *((_QWORD *)a1 + 571) = (char *)a1 + 4560;
  *((_QWORD *)a1 + 570) = (char *)a1 + 4560;
  dword_14008A038 = 1;
  dword_14008A138 = 1;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)((char *)a1 + 4416),
    0,
    0,
    0x200u,
    *((unsigned int *)a1 + 481),
    0x6D444856u,
    0);
  *((_BYTE *)a1 + 4544) = 1;
  VhdmpiAcquirePassiveLock((char *)a1 + 3592);
  AppropriateSectorBitmaps = VhdmpiAllocateAppropriateSectorBitmaps(a1);
  VhdmpiReleasePassiveLock((char *)a1 + 3592);
  if ( AppropriateSectorBitmaps >= 0 )
  {
    for ( i = 0; i != 256; ++i )
    {
      v4 = (char *)a1 + 16 * i + 4576;
      *((_QWORD *)a1 + 2 * i + 573) = v4;
      v5 = 2 * (i + 286);
      *((_QWORD *)a1 + v5) = v4;
    }
    Pool2 = ExAllocatePool2(
              256,
              (unsigned __int64)((unsigned int)((~(*((unsigned int *)a1 + 618) - 1LL)
                                               & ((unsigned __int64)*((unsigned int *)a1 + 618)
                                                + *((_QWORD *)a1 + 247)
                                                - 1LL))
                                              / *((unsigned int *)a1 + 618))
                               + 7) >> 3,
              1833191510);
    *((_QWORD *)a1 + 569) = Pool2;
    if ( Pool2 )
      return 0;
    AppropriateSectorBitmaps = -1073741801;
  }
  VhdmpiCleanupSectorBitmapTracking(a1);
  return (unsigned int)AppropriateSectorBitmaps;
}

```

## disassembly

```asm
0x14003cba8  mov     [rsp+arg_0], rbx
0x14003cbad  mov     [rsp+arg_8], rsi
0x14003cbb2  push    rdi
0x14003cbb3  sub     rsp, 40h
0x14003cbb7  mov     rdi, rcx
0x14003cbba  add     rcx, 1120h; SpinLock
0x14003cbc1  call    cs:__imp_KeInitializeSpinLock
0x14003cbc8  nop     dword ptr [rax+rax+00h]
0x14003cbcd  lea     rax, [rdi+11D0h]
0x14003cbd4  mov     r9d, 200h; Flags
0x14003cbda  mov     [rax+8], rax
0x14003cbde  lea     rcx, [rdi+1140h]; Lookaside
0x14003cbe5  mov     [rax], rax
0x14003cbe8  xor     r8d, r8d; Free
0x14003cbeb  mov     cs:dword_14008A038, 1
0x14003cbf5  xor     eax, eax
0x14003cbf7  mov     [rsp+48h+Depth], ax; Depth
0x14003cbfc  mov     cs:dword_14008A138, 1
0x14003cc06  mov     edx, [rdi+784h]
0x14003cc0c  mov     [rsp+48h+Tag], 6D444856h; Tag
0x14003cc14  mov     [rsp+48h+Size], rdx; Size
0x14003cc19  xor     edx, edx; Allocate
0x14003cc1b  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003cc22  nop     dword ptr [rax+rax+00h]
0x14003cc27  lea     rbx, [rdi+0E08h]
0x14003cc2e  mov     byte ptr [rdi+11C0h], 1
0x14003cc35  mov     rcx, rbx
0x14003cc38  call    VhdmpiAcquirePassiveLock
0x14003cc3d  mov     rcx, rdi; struct _VHD1_BACKING_STORE *
0x14003cc40  call    ?VhdmpiAllocateAppropriateSectorBitmaps@@YAJPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiAllocateAppropriateSectorBitmaps(_VHD1_BACKING_STORE *)
0x14003cc45  mov     rcx, rbx
0x14003cc48  mov     esi, eax
0x14003cc4a  call    VhdmpiReleasePassiveLock
0x14003cc4f  test    esi, esi
0x14003cc51  js      loc_14003CCDE
0x14003cc57  xor     edx, edx
0x14003cc59  mov     r10d, 100h
0x14003cc5f  mov     rax, rdx
0x14003cc62  lea     rcx, [rdi+11E0h]
0x14003cc69  shl     rax, 4
0x14003cc6d  add     rcx, rax
0x14003cc70  mov     [rax+rdi+11E8h], rcx
0x14003cc78  lea     rax, [rdx+11Eh]
0x14003cc7f  add     rax, rax
0x14003cc82  inc     rdx
0x14003cc85  mov     [rdi+rax*8], rcx
0x14003cc89  cmp     rdx, r10
0x14003cc8c  jnz     short loc_14003CC5F
0x14003cc8e  mov     r9d, [rdi+9A8h]
0x14003cc95  mov     r8d, 6D444856h
0x14003cc9b  mov     rax, [rdi+7B8h]
0x14003cca2  mov     rcx, r10
0x14003cca5  dec     rax
0x14003cca8  add     rax, r9
0x14003ccab  lea     rdx, [r9-1]
0x14003ccaf  not     rdx
0x14003ccb2  and     rax, rdx
0x14003ccb5  xor     edx, edx
0x14003ccb7  div     r9
0x14003ccba  lea     edx, [rax+7]
0x14003ccbd  shr     rdx, 3
0x14003ccc1  call    cs:__imp_ExAllocatePool2
0x14003ccc8  nop     dword ptr [rax+rax+00h]
0x14003cccd  mov     [rdi+11C8h], rax
0x14003ccd4  test    rax, rax
0x14003ccd7  jnz     short loc_14003CCF9
0x14003ccd9  mov     esi, 0C0000017h
0x14003ccde  mov     rcx, rdi; struct _VHD1_BACKING_STORE *
0x14003cce1  call    ?VhdmpiCleanupSectorBitmapTracking@@YAXPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiCleanupSectorBitmapTracking(_VHD1_BACKING_STORE *)
0x14003cce6  mov     rbx, [rsp+48h+arg_0]
0x14003cceb  mov     eax, esi
0x14003cced  mov     rsi, [rsp+48h+arg_8]
0x14003ccf2  add     rsp, 40h
0x14003ccf6  pop     rdi
0x14003ccf7  retn
0x14003ccf9  xor     esi, esi
0x14003ccfb  jmp     short loc_14003CCE6
```
