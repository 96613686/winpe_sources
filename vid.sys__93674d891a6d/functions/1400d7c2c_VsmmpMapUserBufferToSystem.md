# VsmmpMapUserBufferToSystem

- ea: `0x1400d7c2c`
- end: `0x1400d7d88`
- name: `VsmmpMapUserBufferToSystem`
- size: `348`
- prototype: `__int64 __fastcall(void *, ULONG, struct _MDL **, LOCK_OPERATION, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ba38`
- `0x14000d4d8`

## callees

- `0x14002f724`
- `0x1400d7c2c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d7cdf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400d7cdf`
- `ntoskrnl!IoFreeMdl` at `0x1400d7d6f`
- `ntoskrnl!IoFreeMdl` at `0x1400d7d6f`
- `ntoskrnl!IoAllocateMdl` at `0x1400d7c53`
- `ntoskrnl!IoAllocateMdl` at `0x1400d7c53`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400d7c9b`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400d7c9b`
- `ntoskrnl!MmUnlockPages` at `0x1400d7d60`
- `ntoskrnl!MmUnlockPages` at `0x1400d7d60`

## pseudocode

```c
__int64 __fastcall VsmmpMapUserBufferToSystem(void *a1, ULONG a2, struct _MDL **a3, LOCK_OPERATION a4, _QWORD *a5)
{
  char v7; // si
  struct _MDL *Mdl; // rax
  struct _MDL *v9; // rbx
  unsigned int v10; // edi
  ULONG Priority; // ecx
  PVOID MappedSystemVa; // rcx

  v7 = 0;
  Mdl = IoAllocateMdl(a1, a2, 0, 0, 0);
  v9 = Mdl;
  if ( Mdl )
  {
    MmProbeAndLockPages(Mdl, 0, a4);
    v7 = 1;
    Priority = 1073741840;
    if ( a4 != IoWriteAccess )
      Priority = -1073741808;
    if ( (v9->MdlFlags & 5) != 0 )
      MappedSystemVa = v9->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, Priority);
    if ( MappedSystemVa )
    {
      *a5 = MappedSystemVa;
      *a3 = v9;
      v9 = 0;
      v10 = 0;
    }
    else
    {
      v10 = -1073741670;
      VidTraceErrorStatusInternal0(
        "VsmmpMapUserBufferToSystem",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
        377,
        3221225626LL);
    }
  }
  else
  {
    v10 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmpMapUserBufferToSystem",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilities.c",
      345,
      3221225626LL);
  }
  if ( v9 )
  {
    if ( v7 )
      MmUnlockPages(v9);
    IoFreeMdl(v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1400d7c2c  push    rbx
0x1400d7c2e  push    rsi
0x1400d7c2f  push    rdi
0x1400d7c30  push    r14
0x1400d7c32  sub     rsp, 48h
0x1400d7c36  mov     edi, r9d
0x1400d7c39  mov     r14, r8
0x1400d7c3c  xor     sil, sil
0x1400d7c3f  mov     [rsp+68h+var_38], sil
0x1400d7c44  mov     [rsp+68h+Irp], 0; Irp
0x1400d7c4d  xor     r9d, r9d; ChargeQuota
0x1400d7c50  xor     r8d, r8d; SecondaryBuffer
0x1400d7c53  call    cs:__imp_IoAllocateMdl
0x1400d7c5a  nop     dword ptr [rax+rax+00h]
0x1400d7c5f  mov     rbx, rax
0x1400d7c62  mov     [rsp+68h+var_30], rax
0x1400d7c67  test    rax, rax
0x1400d7c6a  jnz     short loc_1400D7C93
0x1400d7c6c  mov     r9d, 0C000009Ah
0x1400d7c72  mov     edi, r9d
0x1400d7c75  mov     r8d, 159h
0x1400d7c7b  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d7c82  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d7c89  call    VidTraceErrorStatusInternal0
0x1400d7c8e  jmp     loc_1400D7D53
0x1400d7c93  mov     r8d, edi; Operation
0x1400d7c96  xor     edx, edx; AccessMode
0x1400d7c98  mov     rcx, rbx; MemoryDescriptorList
0x1400d7c9b  call    cs:__imp_MmProbeAndLockPages
0x1400d7ca2  nop     dword ptr [rax+rax+00h]
0x1400d7ca7  nop
0x1400d7ca8  mov     esi, 1
0x1400d7cad  mov     ecx, 40000010h
0x1400d7cb2  mov     eax, 0C0000010h
0x1400d7cb7  cmp     edi, esi
0x1400d7cb9  cmovnz  ecx, eax
0x1400d7cbc  test    byte ptr [rbx+0Ah], 5
0x1400d7cc0  jz      short loc_1400D7CC8
0x1400d7cc2  mov     rcx, [rbx+18h]
0x1400d7cc6  jmp     short loc_1400D7CEE
0x1400d7cc8  mov     [rsp+68h+Priority], ecx; Priority
0x1400d7ccc  mov     dword ptr [rsp+68h+Irp], 0; BugCheckOnFailure
0x1400d7cd4  xor     r9d, r9d; RequestedAddress
0x1400d7cd7  mov     r8d, esi; CacheType
0x1400d7cda  xor     edx, edx; AccessMode
0x1400d7cdc  mov     rcx, rbx; MemoryDescriptorList
0x1400d7cdf  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400d7ce6  nop     dword ptr [rax+rax+00h]
0x1400d7ceb  mov     rcx, rax
0x1400d7cee  test    rcx, rcx
0x1400d7cf1  jnz     short loc_1400D7D17
0x1400d7cf3  mov     r9d, 0C000009Ah
0x1400d7cf9  mov     edi, r9d
0x1400d7cfc  mov     r8d, 179h
0x1400d7d02  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d7d09  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d7d10  call    VidTraceErrorStatusInternal0
0x1400d7d15  jmp     short loc_1400D7D53
0x1400d7d17  mov     rax, [rsp+68h+arg_20]
0x1400d7d1f  mov     [rax], rcx
0x1400d7d22  mov     [r14], rbx
0x1400d7d25  xor     ebx, ebx
0x1400d7d27  xor     edi, edi
0x1400d7d29  jmp     short loc_1400D7D53
0x1400d7d2b  mov     edi, eax
0x1400d7d2d  mov     r9d, eax
0x1400d7d30  mov     r8d, 164h
0x1400d7d36  lea     rdx, aOnecoreVmVidSy_34; "onecore\\vm\\vid\\sys\\vsmm\\vsmmutilit"...
0x1400d7d3d  lea     rcx, aVsmmpmapuserbu; "VsmmpMapUserBufferToSystem"
0x1400d7d44  call    VidTraceErrorStatusInternal0
0x1400d7d49  mov     rbx, [rsp+68h+var_30]
0x1400d7d4e  mov     sil, [rsp+68h+var_38]
0x1400d7d53  test    rbx, rbx
0x1400d7d56  jz      short loc_1400D7D7B
0x1400d7d58  test    sil, sil
0x1400d7d5b  jz      short loc_1400D7D6C
0x1400d7d5d  mov     rcx, rbx; MemoryDescriptorList
0x1400d7d60  call    cs:__imp_MmUnlockPages
0x1400d7d67  nop     dword ptr [rax+rax+00h]
0x1400d7d6c  mov     rcx, rbx; Mdl
0x1400d7d6f  call    cs:__imp_IoFreeMdl
0x1400d7d76  nop     dword ptr [rax+rax+00h]
0x1400d7d7b  mov     eax, edi
0x1400d7d7d  add     rsp, 48h
0x1400d7d81  pop     r14
0x1400d7d83  pop     rdi
0x1400d7d84  pop     rsi
0x1400d7d85  pop     rbx
0x1400d7d86  retn
```
