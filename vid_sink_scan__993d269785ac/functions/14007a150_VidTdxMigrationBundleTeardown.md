# VidTdxMigrationBundleTeardown

- ea: `0x14007a150`
- end: `0x14007a262`
- name: `VidTdxMigrationBundleTeardown`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14007a578`
- `0x14007abc8`
- `0x14007b724`

## callees

- `0x140024c78`
- `0x140030790`
- `0x1400307d0`
- `0x14007a150`
- `0x1400ed1f0`
- `0x1400ed9b4`

## import_xrefs

- `ntoskrnl!MmFreePagesFromMdl` at `0x14007a1be`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14007a1be`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007a1aa`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007a1aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a245`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a1cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a245`
- `winhvr!WinHvDeleteTdMigrationBundle` at `0x14007a1ec`
- `winhvr!WinHvDeleteTdMigrationBundle` at `0x14007a1ec`

## pseudocode

```c
void __fastcall VidTdxMigrationBundleTeardown(__int64 a1, PMDL *a2)
{
  PMDL v4; // rcx
  PMDL *v5; // rbx
  int v6; // eax

  VidLockAcquireExclusive(a2);
  VidClientBufferUnShare(a2 + 35, 0, a2 + 35);
  a2[46] = 0;
  VidClientBufferUninitialize(a2 + 35);
  v4 = a2[44];
  v5 = a2 + 45;
  if ( v4 )
    MmUnmapLockedPages(v4, *v5);
  if ( *v5 )
  {
    MmFreePagesFromMdl(*v5);
    ExFreePoolWithTag(*v5, 0);
  }
  if ( a2[1] != (PMDL)-1LL )
  {
    v6 = WinHvDeleteTdMigrationBundle(*(_QWORD *)(a1 + 648));
    if ( v6 < 0 )
      VidTracePartitionErrorInternal0(
        (__int64)"VidTdxMigrationBundleTeardown",
        (__int64)"onecore\\vm\\vid\\sys\\driver\\amd64\\vidtdx.c",
        245,
        a1 + 656,
        (unsigned __int16 *)(a1 + 120),
        *(_QWORD *)(a1 + 648),
        v6);
  }
  VidLockRelease(a2);
  ExFreePoolWithTag(a2, 0x72446456u);
}

```

## disassembly

```asm
0x14007a150  mov     [rsp+arg_0], rbx
0x14007a155  mov     [rsp+arg_8], rsi
0x14007a15a  push    rdi
0x14007a15b  sub     rsp, 40h
0x14007a15f  mov     rsi, rcx
0x14007a162  mov     rdi, rdx
0x14007a165  mov     rcx, rdx
0x14007a168  call    VidLockAcquireExclusive
0x14007a16d  lea     rbx, [rdi+118h]
0x14007a174  xor     edx, edx
0x14007a176  mov     r8, rbx
0x14007a179  mov     rcx, rbx
0x14007a17c  call    VidClientBufferUnShare
0x14007a181  mov     rcx, rbx
0x14007a184  mov     qword ptr [rdi+170h], 0
0x14007a18f  call    VidClientBufferUninitialize
0x14007a194  mov     rcx, [rdi+160h]; BaseAddress
0x14007a19b  lea     rbx, [rdi+168h]
0x14007a1a2  test    rcx, rcx
0x14007a1a5  jz      short loc_14007A1B6
0x14007a1a7  mov     rdx, [rbx]; MemoryDescriptorList
0x14007a1aa  call    cs:__imp_MmUnmapLockedPages
0x14007a1b1  nop     dword ptr [rax+rax+00h]
0x14007a1b6  mov     rcx, [rbx]; MemoryDescriptorList
0x14007a1b9  test    rcx, rcx
0x14007a1bc  jz      short loc_14007A1DB
0x14007a1be  call    cs:__imp_MmFreePagesFromMdl
0x14007a1c5  nop     dword ptr [rax+rax+00h]
0x14007a1ca  mov     rcx, [rbx]; P
0x14007a1cd  xor     edx, edx; Tag
0x14007a1cf  call    cs:__imp_ExFreePoolWithTag
0x14007a1d6  nop     dword ptr [rax+rax+00h]
0x14007a1db  mov     rdx, [rdi+8]
0x14007a1df  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14007a1e3  jz      short loc_14007A235
0x14007a1e5  mov     rcx, [rsi+288h]
0x14007a1ec  call    cs:__imp_WinHvDeleteTdMigrationBundle
0x14007a1f3  nop     dword ptr [rax+rax+00h]
0x14007a1f8  test    eax, eax
0x14007a1fa  jns     short loc_14007A235
0x14007a1fc  mov     [rsp+48h+var_18], eax
0x14007a200  lea     rcx, [rsi+78h]
0x14007a204  mov     rax, [rsi+288h]
0x14007a20b  lea     r9, [rsi+290h]
0x14007a212  mov     [rsp+48h+var_20], rax
0x14007a217  lea     rdx, aOnecoreVmVidSy_49; "onecore\\vm\\vid\\sys\\driver\\amd64\\v"...
0x14007a21e  mov     [rsp+48h+var_28], rcx
0x14007a223  mov     r8d, 0F5h
0x14007a229  lea     rcx, aVidtdxmigratio; "VidTdxMigrationBundleTeardown"
0x14007a230  call    VidTracePartitionErrorInternal0
0x14007a235  mov     rcx, rdi
0x14007a238  call    VidLockRelease
0x14007a23d  mov     edx, 72446456h; Tag
0x14007a242  mov     rcx, rdi; P
0x14007a245  call    cs:__imp_ExFreePoolWithTag
0x14007a24c  nop     dword ptr [rax+rax+00h]
0x14007a251  mov     rbx, [rsp+48h+arg_0]
0x14007a256  mov     rsi, [rsp+48h+arg_8]
0x14007a25b  add     rsp, 40h
0x14007a25f  pop     rdi
0x14007a260  retn
```
