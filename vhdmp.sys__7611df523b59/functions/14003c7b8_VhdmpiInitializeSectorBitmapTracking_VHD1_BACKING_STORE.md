# VhdmpiInitializeSectorBitmapTracking(_VHD1_BACKING_STORE *)

- ea: `0x14003c7b8`
- end: `0x14003c90d`
- name: `?VhdmpiInitializeSectorBitmapTracking@@YAJPEAU_VHD1_BACKING_STORE@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(struct _VHD1_BACKING_STORE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400bd7dc`

## callees

- `0x14001b7fc`
- `0x14001bc68`
- `0x14002511c`
- `0x140025990`
- `0x14003c7b8`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003c82b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14003c82b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c7d1`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003c7d1`
- `ntoskrnl!ExAllocatePool2` at `0x14003c8d1`
- `ntoskrnl!ExAllocatePool2` at `0x14003c8d1`

## pseudocode

```c
__int64 __fastcall VhdmpiInitializeSectorBitmapTracking(struct _VHD1_BACKING_STORE *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  int AppropriateSectorBitmaps; // esi
  __int64 i; // rdx
  char *v6; // rcx
  __int64 v7; // rax
  __int64 Pool2; // rax

  KeInitializeSpinLock((PKSPIN_LOCK)a1 + 548);
  *((_QWORD *)a1 + 571) = (char *)a1 + 4560;
  *((_QWORD *)a1 + 570) = (char *)a1 + 4560;
  dword_14008A138 = 1;
  dword_14008A038 = 1;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)((char *)a1 + 4416),
    0,
    0,
    0x200u,
    *((unsigned int *)a1 + 481),
    0x6D444856u,
    0);
  *((_BYTE *)a1 + 4544) = 1;
  VhdmpiAcquirePassiveLock((char *)a1 + 3592, v2, v3);
  AppropriateSectorBitmaps = VhdmpiAllocateAppropriateSectorBitmaps(a1);
  VhdmpiReleasePassiveLock((char *)a1 + 3592);
  if ( AppropriateSectorBitmaps >= 0 )
  {
    for ( i = 0; i != 256; ++i )
    {
      v6 = (char *)a1 + 16 * i + 4576;
      *((_QWORD *)a1 + 2 * i + 573) = v6;
      v7 = 2 * (i + 286);
      *((_QWORD *)a1 + v7) = v6;
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
0x14003c7b8  mov     [rsp+arg_0], rbx
0x14003c7bd  mov     [rsp+arg_8], rsi
0x14003c7c2  push    rdi
0x14003c7c3  sub     rsp, 40h
0x14003c7c7  mov     rdi, rcx
0x14003c7ca  add     rcx, 1120h; SpinLock
0x14003c7d1  call    cs:__imp_KeInitializeSpinLock
0x14003c7d8  nop     dword ptr [rax+rax+00h]
0x14003c7dd  lea     rax, [rdi+11D0h]
0x14003c7e4  mov     r9d, 200h; Flags
0x14003c7ea  mov     [rax+8], rax
0x14003c7ee  lea     rcx, [rdi+1140h]; Lookaside
0x14003c7f5  mov     [rax], rax
0x14003c7f8  xor     r8d, r8d; Free
0x14003c7fb  mov     cs:dword_14008A138, 1
0x14003c805  xor     eax, eax
0x14003c807  mov     [rsp+48h+Depth], ax; Depth
0x14003c80c  mov     cs:dword_14008A038, 1
0x14003c816  mov     edx, [rdi+784h]
0x14003c81c  mov     [rsp+48h+Tag], 6D444856h; Tag
0x14003c824  mov     [rsp+48h+Size], rdx; Size
0x14003c829  xor     edx, edx; Allocate
0x14003c82b  call    cs:__imp_ExInitializeNPagedLookasideList
0x14003c832  nop     dword ptr [rax+rax+00h]
0x14003c837  lea     rbx, [rdi+0E08h]
0x14003c83e  mov     byte ptr [rdi+11C0h], 1
0x14003c845  mov     rcx, rbx
0x14003c848  call    VhdmpiAcquirePassiveLock
0x14003c84d  mov     rcx, rdi; struct _VHD1_BACKING_STORE *
0x14003c850  call    ?VhdmpiAllocateAppropriateSectorBitmaps@@YAJPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiAllocateAppropriateSectorBitmaps(_VHD1_BACKING_STORE *)
0x14003c855  mov     rcx, rbx
0x14003c858  mov     esi, eax
0x14003c85a  call    VhdmpiReleasePassiveLock
0x14003c85f  test    esi, esi
0x14003c861  js      loc_14003C8EE
0x14003c867  xor     edx, edx
0x14003c869  mov     r10d, 100h
0x14003c86f  mov     rax, rdx
0x14003c872  lea     rcx, [rdi+11E0h]
0x14003c879  shl     rax, 4
0x14003c87d  add     rcx, rax
0x14003c880  mov     [rax+rdi+11E8h], rcx
0x14003c888  lea     rax, [rdx+11Eh]
0x14003c88f  add     rax, rax
0x14003c892  inc     rdx
0x14003c895  mov     [rdi+rax*8], rcx
0x14003c899  cmp     rdx, r10
0x14003c89c  jnz     short loc_14003C86F
0x14003c89e  mov     r9d, [rdi+9A8h]
0x14003c8a5  mov     r8d, 6D444856h
0x14003c8ab  mov     rax, [rdi+7B8h]
0x14003c8b2  mov     rcx, r10
0x14003c8b5  dec     rax
0x14003c8b8  add     rax, r9
0x14003c8bb  lea     rdx, [r9-1]
0x14003c8bf  not     rdx
0x14003c8c2  and     rax, rdx
0x14003c8c5  xor     edx, edx
0x14003c8c7  div     r9
0x14003c8ca  lea     edx, [rax+7]
0x14003c8cd  shr     rdx, 3
0x14003c8d1  call    cs:__imp_ExAllocatePool2
0x14003c8d8  nop     dword ptr [rax+rax+00h]
0x14003c8dd  mov     [rdi+11C8h], rax
0x14003c8e4  test    rax, rax
0x14003c8e7  jnz     short loc_14003C909
0x14003c8e9  mov     esi, 0C0000017h
0x14003c8ee  mov     rcx, rdi; struct _VHD1_BACKING_STORE *
0x14003c8f1  call    ?VhdmpiCleanupSectorBitmapTracking@@YAXPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiCleanupSectorBitmapTracking(_VHD1_BACKING_STORE *)
0x14003c8f6  mov     rbx, [rsp+48h+arg_0]
0x14003c8fb  mov     eax, esi
0x14003c8fd  mov     rsi, [rsp+48h+arg_8]
0x14003c902  add     rsp, 40h
0x14003c906  pop     rdi
0x14003c907  retn
0x14003c909  xor     esi, esi
0x14003c90b  jmp     short loc_14003C8F6
```
