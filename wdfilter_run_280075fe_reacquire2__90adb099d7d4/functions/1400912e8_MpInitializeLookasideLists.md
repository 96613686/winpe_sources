# MpInitializeLookasideLists

- ea: `0x1400912e8`
- end: `0x14009159f`
- name: `MpInitializeLookasideLists`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1400907b8`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140091320`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14009135c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140091320`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14009135c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091394`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400913cc`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091404`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009143c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091474`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400914ac`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400914e4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009151c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091554`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009158c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091394`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400913cc`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091404`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009143c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091474`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400914ac`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400914e4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009151c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140091554`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14009158c`

## pseudocode

```c
void MpInitializeLookasideLists()
{
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(MpData + 1408),
    0,
    0,
    ExDefaultNonPagedPoolType,
    0x90u,
    0x7772504Du,
    0);
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(MpData + 1152),
    0,
    0,
    ExDefaultNonPagedPoolType,
    0x30u,
    0x7877504Du,
    0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1024), 0, 0, 0, 0x18u, 0x7869504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 896), 0, 0, 0, 0xF8u, 0x7443504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1536), 0, 0, 0, 0x800u, 0x6669504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1664), 0, 0, 0, 0x80u, 0x3161504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1792), 0, 0, 0, 0x210u, 0x3261504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2112), 0, 0, 0, 0x28u, 0x6363504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 1280), 0, 0, 0, 0x28u, 0x7869504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 2240), 0, 0, 0, 0x78u, 0x7273504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 4224), 0, 0, 0, 0x60u, 0x6F63504Du, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 4352), 0, 0, 0, 0xDCu, 0x6972504Du, 0);
}

```

## disassembly

```asm
0x1400912e8  push    rsi
0x1400912ea  sub     rsp, 40h
0x1400912ee  mov     rcx, cs:MpData
0x1400912f5  xor     esi, esi
0x1400912f7  mov     r9d, cs:ExDefaultNonPagedPoolType; Flags
0x1400912fe  add     rcx, 580h; Lookaside
0x140091305  mov     [rsp+48h+Depth], si; Depth
0x14009130a  xor     r8d, r8d; Free
0x14009130d  mov     [rsp+48h+Tag], 7772504Dh; Tag
0x140091315  xor     edx, edx; Allocate
0x140091317  mov     [rsp+48h+Size], 90h; Size
0x140091320  call    cs:__imp_ExInitializeNPagedLookasideList
0x140091327  nop     dword ptr [rax+rax+00h]
0x14009132c  mov     rcx, cs:MpData
0x140091333  xor     r8d, r8d; Free
0x140091336  mov     r9d, cs:ExDefaultNonPagedPoolType; Flags
0x14009133d  add     rcx, 480h; Lookaside
0x140091344  mov     [rsp+48h+Depth], si; Depth
0x140091349  xor     edx, edx; Allocate
0x14009134b  mov     [rsp+48h+Tag], 7877504Dh; Tag
0x140091353  mov     [rsp+48h+Size], 30h ; '0'; Size
0x14009135c  call    cs:__imp_ExInitializeNPagedLookasideList
0x140091363  nop     dword ptr [rax+rax+00h]
0x140091368  mov     rcx, cs:MpData
0x14009136f  xor     r9d, r9d; Flags
0x140091372  mov     [rsp+48h+Depth], si; Depth
0x140091377  add     rcx, 400h; Lookaside
0x14009137e  mov     [rsp+48h+Tag], 7869504Dh; Tag
0x140091386  xor     r8d, r8d; Free
0x140091389  xor     edx, edx; Allocate
0x14009138b  mov     [rsp+48h+Size], 18h; Size
0x140091394  call    cs:__imp_ExInitializePagedLookasideList
0x14009139b  nop     dword ptr [rax+rax+00h]
0x1400913a0  mov     rcx, cs:MpData
0x1400913a7  xor     r9d, r9d; Flags
0x1400913aa  mov     [rsp+48h+Depth], si; Depth
0x1400913af  add     rcx, 380h; Lookaside
0x1400913b6  mov     [rsp+48h+Tag], 7443504Dh; Tag
0x1400913be  xor     r8d, r8d; Free
0x1400913c1  xor     edx, edx; Allocate
0x1400913c3  mov     [rsp+48h+Size], 0F8h; Size
0x1400913cc  call    cs:__imp_ExInitializePagedLookasideList
0x1400913d3  nop     dword ptr [rax+rax+00h]
0x1400913d8  mov     rcx, cs:MpData
0x1400913df  xor     r9d, r9d; Flags
0x1400913e2  mov     [rsp+48h+Depth], si; Depth
0x1400913e7  add     rcx, 600h; Lookaside
0x1400913ee  mov     [rsp+48h+Tag], 6669504Dh; Tag
0x1400913f6  xor     r8d, r8d; Free
0x1400913f9  xor     edx, edx; Allocate
0x1400913fb  mov     [rsp+48h+Size], 800h; Size
0x140091404  call    cs:__imp_ExInitializePagedLookasideList
0x14009140b  nop     dword ptr [rax+rax+00h]
0x140091410  mov     rcx, cs:MpData
0x140091417  xor     r9d, r9d; Flags
0x14009141a  mov     [rsp+48h+Depth], si; Depth
0x14009141f  add     rcx, 680h; Lookaside
0x140091426  mov     [rsp+48h+Tag], 3161504Dh; Tag
0x14009142e  xor     r8d, r8d; Free
0x140091431  xor     edx, edx; Allocate
0x140091433  mov     [rsp+48h+Size], 80h; Size
0x14009143c  call    cs:__imp_ExInitializePagedLookasideList
0x140091443  nop     dword ptr [rax+rax+00h]
0x140091448  mov     rcx, cs:MpData
0x14009144f  xor     r9d, r9d; Flags
0x140091452  mov     [rsp+48h+Depth], si; Depth
0x140091457  add     rcx, 700h; Lookaside
0x14009145e  mov     [rsp+48h+Tag], 3261504Dh; Tag
0x140091466  xor     r8d, r8d; Free
0x140091469  xor     edx, edx; Allocate
0x14009146b  mov     [rsp+48h+Size], 210h; Size
0x140091474  call    cs:__imp_ExInitializePagedLookasideList
0x14009147b  nop     dword ptr [rax+rax+00h]
0x140091480  mov     rcx, cs:MpData
0x140091487  xor     r9d, r9d; Flags
0x14009148a  mov     [rsp+48h+Depth], si; Depth
0x14009148f  add     rcx, 840h; Lookaside
0x140091496  mov     [rsp+48h+Tag], 6363504Dh; Tag
0x14009149e  xor     r8d, r8d; Free
0x1400914a1  xor     edx, edx; Allocate
0x1400914a3  mov     [rsp+48h+Size], 28h ; '('; Size
0x1400914ac  call    cs:__imp_ExInitializePagedLookasideList
0x1400914b3  nop     dword ptr [rax+rax+00h]
0x1400914b8  mov     rcx, cs:MpData
0x1400914bf  xor     r9d, r9d; Flags
0x1400914c2  mov     [rsp+48h+Depth], si; Depth
0x1400914c7  add     rcx, 500h; Lookaside
0x1400914ce  xor     r8d, r8d; Free
0x1400914d1  mov     [rsp+48h+Tag], 7869504Dh; Tag
0x1400914d9  xor     edx, edx; Allocate
0x1400914db  mov     [rsp+48h+Size], 28h ; '('; Size
0x1400914e4  call    cs:__imp_ExInitializePagedLookasideList
0x1400914eb  nop     dword ptr [rax+rax+00h]
0x1400914f0  mov     rcx, cs:MpData
0x1400914f7  xor     r9d, r9d; Flags
0x1400914fa  mov     [rsp+48h+Depth], si; Depth
0x1400914ff  add     rcx, 8C0h; Lookaside
0x140091506  mov     [rsp+48h+Tag], 7273504Dh; Tag
0x14009150e  xor     r8d, r8d; Free
0x140091511  xor     edx, edx; Allocate
0x140091513  mov     [rsp+48h+Size], 78h ; 'x'; Size
0x14009151c  call    cs:__imp_ExInitializePagedLookasideList
0x140091523  nop     dword ptr [rax+rax+00h]
0x140091528  mov     rcx, cs:MpData
0x14009152f  xor     r9d, r9d; Flags
0x140091532  mov     [rsp+48h+Depth], si; Depth
0x140091537  add     rcx, 1080h; Lookaside
0x14009153e  mov     [rsp+48h+Tag], 6F63504Dh; Tag
0x140091546  xor     r8d, r8d; Free
0x140091549  xor     edx, edx; Allocate
0x14009154b  mov     [rsp+48h+Size], 60h ; '`'; Size
0x140091554  call    cs:__imp_ExInitializePagedLookasideList
0x14009155b  nop     dword ptr [rax+rax+00h]
0x140091560  mov     rcx, cs:MpData
0x140091567  xor     r9d, r9d; Flags
0x14009156a  mov     [rsp+48h+Depth], si; Depth
0x14009156f  add     rcx, 1100h; Lookaside
0x140091576  mov     [rsp+48h+Tag], 6972504Dh; Tag
0x14009157e  xor     r8d, r8d; Free
0x140091581  xor     edx, edx; Allocate
0x140091583  mov     [rsp+48h+Size], 0DCh; Size
0x14009158c  call    cs:__imp_ExInitializePagedLookasideList
0x140091593  nop     dword ptr [rax+rax+00h]
0x140091598  add     rsp, 40h
0x14009159c  pop     rsi
0x14009159d  retn
```
