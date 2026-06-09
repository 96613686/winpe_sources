# VsmmVsmIoctlSetMemoryBlockProtections

- ea: `0x1400abee0`
- end: `0x1400ac62a`
- name: `VsmmVsmIoctlSetMemoryBlockProtections`
- size: `1866`
- prototype: `__int64 __fastcall(__int64, SIZE_T, SIZE_T, SIZE_T, volatile void *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400303c0`
- `0x140034554`
- `0x140034584`
- `0x140038630`
- `0x1400abee0`
- `0x1400ad79c`
- `0x1400f42c8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400ac09d`
- `ntoskrnl!ProbeForRead` at `0x1400ac09d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ac138`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ac138`
- `ntoskrnl!IoFreeMdl` at `0x1400ac433`
- `ntoskrnl!IoFreeMdl` at `0x1400ac433`
- `ntoskrnl!IoAllocateMdl` at `0x1400ac0bb`
- `ntoskrnl!IoAllocateMdl` at `0x1400ac0bb`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ac103`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ac103`
- `ntoskrnl!MmUnlockPages` at `0x1400ac41f`
- `ntoskrnl!MmUnlockPages` at `0x1400ac41f`

## pseudocode

```c
__int64 __fastcall VsmmVsmIoctlSetMemoryBlockProtections(
        __int64 a1,
        SIZE_T a2,
        unsigned __int64 a3,
        SIZE_T a4,
        volatile void *a5,
        int a6)
{
  unsigned __int64 v9; // r14
  struct _MDL *v10; // rsi
  int v11; // edi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rax
  void *v14; // rdi
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // r9
  char v17; // al
  char v19; // [rsp+32h] [rbp-176h]
  struct _MDL *v20; // [rsp+38h] [rbp-170h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-168h] BYREF
  __int64 v22; // [rsp+48h] [rbp-160h] BYREF
  SIZE_T v23; // [rsp+50h] [rbp-158h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-150h] BYREF
  SIZE_T v25; // [rsp+60h] [rbp-148h] BYREF
  volatile void *Address; // [rsp+68h] [rbp-140h] BYREF
  SIZE_T v27; // [rsp+70h] [rbp-138h]
  _BYTE v28[32]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v30[16]; // [rsp+B0h] [rbp-F8h] BYREF
  struct _MDL **v31; // [rsp+C0h] [rbp-E8h]
  __int64 v32; // [rsp+C8h] [rbp-E0h]
  struct _MDL **v33; // [rsp+D0h] [rbp-D8h]
  __int64 v34; // [rsp+D8h] [rbp-D0h]
  volatile void **p_Address; // [rsp+E0h] [rbp-C8h]
  __int64 v36; // [rsp+E8h] [rbp-C0h]
  __int64 *v37; // [rsp+F0h] [rbp-B8h]
  __int64 v38; // [rsp+F8h] [rbp-B0h]
  unsigned __int64 *v39; // [rsp+100h] [rbp-A8h]
  __int64 v40; // [rsp+108h] [rbp-A0h] BYREF
  volatile void **v41; // [rsp+110h] [rbp-98h]
  __int64 v42; // [rsp+118h] [rbp-90h]
  SIZE_T *v43; // [rsp+120h] [rbp-88h]
  __int64 v44; // [rsp+128h] [rbp-80h]
  unsigned __int64 *v45; // [rsp+130h] [rbp-78h]
  __int64 v46; // [rsp+138h] [rbp-70h]
  SIZE_T *v47; // [rsp+140h] [rbp-68h]
  __int64 v48; // [rsp+148h] [rbp-60h]
  unsigned __int64 *v49; // [rsp+150h] [rbp-58h]
  __int64 v50; // [rsp+158h] [rbp-50h]

  v27 = a2;
  v22 = a1;
  v23 = a2;
  v24 = a3;
  v25 = a4;
  Address = a5;
  v9 = 0;
  v21 = 0;
  v10 = 0;
  v19 = 0;
  if ( (*(_BYTE *)(a1 + 16) & 8) == 0 )
  {
    v11 = -1073741637;
    VidTraceErrorInternal0("VsmmVsmIoctlSetMemoryBlockProtections", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c", 1172);
LABEL_31:
    v17 = 0;
    goto LABEL_32;
  }
  if ( !a4 || !a5 )
  {
    v11 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1179);
    goto LABEL_31;
  }
  if ( ((a4 + ((unsigned __int16)a5 & 0xFFF) + 4095LL) & 0xFFFFFFFFFFFFF000uLL) > 0xFFFFF000 )
  {
    v11 = -1073741811;
    goto LABEL_31;
  }
  if ( (*(_DWORD *)(a1 + 32) & 0x31E0LL) != 0 )
  {
    v11 = -1073741790;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1202);
    goto LABEL_31;
  }
  v11 = VsmmMemoryBlockLookupByHandle(a1, a2, 0, 0, (__int64)&v21);
  v9 = v21;
  if ( v11 < 0 )
    goto LABEL_31;
  if ( (*(_DWORD *)(v21 + 20) & 1) == 0 )
  {
    v11 = -1070137326;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1223);
    goto LABEL_31;
  }
  v12 = *(_QWORD *)(v21 + 40);
  if ( a3 >= v12 || a4 > v12 || a3 > v12 - a4 )
  {
    v11 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1236);
    goto LABEL_31;
  }
  VidObjectLockAcquireShared(a1 + 3736);
  v13 = *(_QWORD *)(v9 + 48);
  if ( a3 >= v13 || a4 > v13 || a3 > v13 - a4 )
  {
    v11 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1248);
    goto LABEL_28;
  }
  v14 = (void *)Address;
  ProbeForRead(Address, a4, 1u);
  Mdl = IoAllocateMdl(v14, a4, 0, 0, 0);
  v10 = Mdl;
  v20 = Mdl;
  if ( !Mdl )
  {
    v11 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1273);
LABEL_28:
    v17 = 1;
    goto LABEL_32;
  }
  MmProbeAndLockPages(Mdl, 0, IoReadAccess);
  v19 = 1;
  if ( (v10->MdlFlags & 5) != 0 )
    MappedSystemVa = v10->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0xC0000010);
  if ( !MappedSystemVa )
  {
    v11 = -1073741670;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1296);
    goto LABEL_28;
  }
  v11 = VsmmVsmpApplyVsmMbpArray(v9, a3, a4, (unsigned __int64)MappedSystemVa, a6 & 1);
  v17 = 1;
  if ( v11 >= 0 )
    v11 = 0;
LABEL_32:
  if ( v17 )
    VidObjectLockRelease(a1 + 3736);
  if ( v9 )
  {
    if ( v11 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v29, "VsmmVsmIoctlSetMemoryBlockProtections");
      tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      LODWORD(v22) = 1323;
      v31 = (struct _MDL **)&v22;
      v32 = 4;
      LODWORD(v20) = v11;
      v33 = &v20;
      v34 = 4;
      Address = *(volatile void **)(v9 + 24);
      p_Address = &Address;
      v36 = 8;
      v25 = *(_QWORD *)(v9 + 40);
      v37 = (__int64 *)&v25;
      v38 = 8;
      v24 = *(_QWORD *)(v9 + 48);
      v39 = &v24;
      v40 = 8;
      v23 = *(int *)(v9 + 20);
      v41 = (volatile void **)&v23;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004DD49, 0, 0, 10, v28);
    }
    VidOpCtrlFinish(v9 + 128);
  }
  if ( v19 )
    MmUnlockPages(v10);
  if ( v10 )
    IoFreeMdl(v10);
  if ( v11 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v29, "VsmmVsmIoctlSetMemoryBlockProtections");
    tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
    LODWORD(v20) = 1345;
    v31 = &v20;
    v32 = 4;
    LODWORD(v22) = v11;
    v33 = (struct _MDL **)&v22;
    v34 = 4;
    p_Address = (volatile void **)(a1 + 656);
    v36 = 16;
    v37 = &v40;
    v38 = 2;
    v39 = *(unsigned __int64 **)(a1 + 128);
    v40 = *(unsigned __int16 *)(a1 + 120);
    Address = *(volatile void **)(a1 + 648);
    v41 = &Address;
    v42 = 8;
    v25 = v27;
    v43 = &v25;
    v44 = 8;
    v24 = a3;
    v45 = &v24;
    v46 = 8;
    v23 = a4;
    v47 = &v23;
    v48 = 8;
    LODWORD(v21) = a6;
    v49 = &v21;
    v50 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14004DA42, 0, 0, 14, v28);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400abee0  push    rbx
0x1400abee2  push    rsi
0x1400abee3  push    rdi
0x1400abee4  push    r12
0x1400abee6  push    r13
0x1400abee8  push    r14
0x1400abeea  push    r15
0x1400abeec  sub     rsp, 170h
0x1400abef3  mov     rax, cs:__security_cookie
0x1400abefa  xor     rax, rsp
0x1400abefd  mov     [rsp+1A8h+var_48], rax
0x1400abf05  mov     r15, r9
0x1400abf08  mov     r12, r8
0x1400abf0b  mov     [rsp+1A8h+var_138], rdx
0x1400abf10  mov     r13, rcx
0x1400abf13  mov     [rsp+1A8h+var_160], rcx
0x1400abf18  mov     [rsp+1A8h+var_158], rdx
0x1400abf1d  mov     [rsp+1A8h+var_150], r8
0x1400abf22  mov     [rsp+1A8h+var_148], r9
0x1400abf27  mov     rcx, [rsp+1A8h+arg_20]
0x1400abf2f  mov     [rsp+1A8h+Address], rcx
0x1400abf34  xor     ebx, ebx
0x1400abf36  mov     r14d, ebx
0x1400abf39  mov     [rsp+1A8h+var_168], rbx
0x1400abf3e  mov     esi, ebx
0x1400abf40  mov     [rsp+1A8h+var_176], bl
0x1400abf44  test    byte ptr [r13+10h], 8
0x1400abf49  jnz     short loc_1400ABF6E
0x1400abf4b  mov     edi, 0C00000BBh
0x1400abf50  mov     r8d, 494h
0x1400abf56  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400abf5d  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400abf64  call    VidTraceErrorInternal0
0x1400abf69  jmp     loc_1400AC2A3
0x1400abf6e  test    r15, r15
0x1400abf71  jz      loc_1400AC281
0x1400abf77  test    rcx, rcx
0x1400abf7a  jz      loc_1400AC281
0x1400abf80  and     ecx, 0FFFh
0x1400abf86  add     rcx, 0FFFh
0x1400abf8d  add     rcx, r15
0x1400abf90  and     rcx, 0FFFFFFFFFFFFF000h
0x1400abf97  mov     eax, 0FFFFF000h
0x1400abf9c  cmp     rcx, rax
0x1400abf9f  jbe     short loc_1400ABFAB
0x1400abfa1  mov     edi, 0C000000Dh
0x1400abfa6  jmp     loc_1400AC2A3
0x1400abfab  mov     eax, [r13+20h]
0x1400abfaf  test    rax, 31E0h
0x1400abfb5  jz      short loc_1400ABFDD
0x1400abfb7  mov     edi, 0C0000022h
0x1400abfbc  mov     r9d, edi
0x1400abfbf  mov     r8d, 4B2h
0x1400abfc5  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400abfcc  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400abfd3  call    VidTraceErrorStatusInternal0
0x1400abfd8  jmp     loc_1400AC2A3
0x1400abfdd  lea     rax, [rsp+1A8h+var_168]
0x1400abfe2  mov     [rsp+1A8h+Irp], rax
0x1400abfe7  xor     r9d, r9d
0x1400abfea  xor     r8d, r8d
0x1400abfed  mov     rcx, r13
0x1400abff0  call    VsmmMemoryBlockLookupByHandle
0x1400abff5  mov     edi, eax
0x1400abff7  mov     r14, [rsp+1A8h+var_168]
0x1400abffc  test    eax, eax
0x1400abffe  js      loc_1400AC2A3
0x1400ac004  mov     eax, [r14+14h]
0x1400ac008  test    al, 1
0x1400ac00a  jnz     short loc_1400AC032
0x1400ac00c  mov     edi, 0C0370012h
0x1400ac011  mov     r9d, edi
0x1400ac014  mov     r8d, 4C7h
0x1400ac01a  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac021  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac028  call    VidTraceErrorStatusInternal0
0x1400ac02d  jmp     loc_1400AC2A3
0x1400ac032  mov     rax, [r14+28h]
0x1400ac036  cmp     r12, rax
0x1400ac039  jnb     loc_1400AC25D
0x1400ac03f  cmp     r15, rax
0x1400ac042  ja      loc_1400AC25D
0x1400ac048  sub     rax, r15
0x1400ac04b  cmp     r12, rax
0x1400ac04e  ja      loc_1400AC25D
0x1400ac054  lea     rcx, [r13+0E98h]
0x1400ac05b  call    VidObjectLockAcquireShared
0x1400ac060  mov     al, 1
0x1400ac062  mov     [rsp+1A8h+var_178], al
0x1400ac066  mov     [rsp+1A8h+var_177], al
0x1400ac06a  mov     rax, [r14+30h]
0x1400ac06e  cmp     r12, rax
0x1400ac071  jnb     loc_1400AC235
0x1400ac077  cmp     r15, rax
0x1400ac07a  ja      loc_1400AC235
0x1400ac080  sub     rax, r15
0x1400ac083  cmp     r12, rax
0x1400ac086  ja      loc_1400AC235
0x1400ac08c  mov     r8d, 1; Alignment
0x1400ac092  mov     rdx, r15; Length
0x1400ac095  mov     rdi, [rsp+1A8h+Address]
0x1400ac09a  mov     rcx, rdi; Address
0x1400ac09d  call    cs:__imp_ProbeForRead
0x1400ac0a4  nop     dword ptr [rax+rax+00h]
0x1400ac0a9  nop
0x1400ac0aa  mov     edx, r15d; Length
0x1400ac0ad  mov     [rsp+1A8h+Irp], rbx; Irp
0x1400ac0b2  xor     r9d, r9d; ChargeQuota
0x1400ac0b5  xor     r8d, r8d; SecondaryBuffer
0x1400ac0b8  mov     rcx, rdi; VirtualAddress
0x1400ac0bb  call    cs:__imp_IoAllocateMdl
0x1400ac0c2  nop     dword ptr [rax+rax+00h]
0x1400ac0c7  mov     rsi, rax
0x1400ac0ca  mov     [rsp+1A8h+var_170], rax
0x1400ac0cf  test    rax, rax
0x1400ac0d2  jnz     short loc_1400AC0FB
0x1400ac0d4  mov     r9d, 0C000009Ah
0x1400ac0da  mov     edi, r9d
0x1400ac0dd  mov     r8d, 4F9h
0x1400ac0e3  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac0ea  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac0f1  call    VidTraceErrorStatusInternal0
0x1400ac0f6  jmp     loc_1400AC257
0x1400ac0fb  xor     r8d, r8d; Operation
0x1400ac0fe  xor     edx, edx; AccessMode
0x1400ac100  mov     rcx, rsi; MemoryDescriptorList
0x1400ac103  call    cs:__imp_MmProbeAndLockPages
0x1400ac10a  nop     dword ptr [rax+rax+00h]
0x1400ac10f  mov     [rsp+1A8h+var_176], 1
0x1400ac114  test    byte ptr [rsi+0Ah], 5
0x1400ac118  jz      short loc_1400AC120
0x1400ac11a  mov     r9, [rsi+18h]
0x1400ac11e  jmp     short loc_1400AC147
0x1400ac120  mov     [rsp+1A8h+Priority], 0C0000010h; Priority
0x1400ac128  mov     dword ptr [rsp+1A8h+Irp], ebx; BugCheckOnFailure
0x1400ac12c  xor     r9d, r9d; RequestedAddress
0x1400ac12f  xor     edx, edx; AccessMode
0x1400ac131  lea     r8d, [r9+1]; CacheType
0x1400ac135  mov     rcx, rsi; MemoryDescriptorList
0x1400ac138  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ac13f  nop     dword ptr [rax+rax+00h]
0x1400ac144  mov     r9, rax
0x1400ac147  test    r9, r9
0x1400ac14a  jnz     short loc_1400AC173
0x1400ac14c  mov     r9d, 0C000009Ah
0x1400ac152  mov     edi, r9d
0x1400ac155  mov     r8d, 510h
0x1400ac15b  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac162  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac169  call    VidTraceErrorStatusInternal0
0x1400ac16e  jmp     loc_1400AC257
0x1400ac173  mov     eax, [rsp+1A8h+arg_28]
0x1400ac17a  and     al, 1
0x1400ac17c  mov     byte ptr [rsp+1A8h+Irp], al
0x1400ac180  mov     r8, r15
0x1400ac183  mov     rdx, r12
0x1400ac186  mov     rcx, r14
0x1400ac189  call    VsmmVsmpApplyVsmMbpArray
0x1400ac18e  mov     edi, eax
0x1400ac190  test    eax, eax
0x1400ac192  mov     al, [rsp+1A8h+var_178]
0x1400ac196  js      loc_1400AC2A5
0x1400ac19c  mov     edi, ebx
0x1400ac19e  jmp     loc_1400AC2A5
0x1400ac1a3  mov     edi, eax
0x1400ac1a5  mov     r9d, eax
0x1400ac1a8  mov     r8d, 505h
0x1400ac1ae  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac1b5  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac1bc  call    VidTraceErrorStatusInternal0
0x1400ac1c1  xor     ebx, ebx
0x1400ac1c3  mov     r14, [rsp+1A8h+var_168]
0x1400ac1c8  mov     al, [rsp+1A8h+var_177]
0x1400ac1cc  mov     rsi, [rsp+1A8h+var_170]
0x1400ac1d1  mov     r13, [rsp+1A8h+var_160]
0x1400ac1d6  mov     rcx, [rsp+1A8h+var_158]
0x1400ac1db  mov     [rsp+1A8h+var_138], rcx
0x1400ac1e0  mov     r12, [rsp+1A8h+var_150]
0x1400ac1e5  mov     r15, [rsp+1A8h+var_148]
0x1400ac1ea  jmp     loc_1400AC2A5
0x1400ac1ef  mov     edi, eax
0x1400ac1f1  mov     r9d, eax
0x1400ac1f4  mov     r8d, 4EBh
0x1400ac1fa  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac201  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac208  call    VidTraceErrorStatusInternal0
0x1400ac20d  xor     ebx, ebx
0x1400ac20f  mov     r14, [rsp+1A8h+var_168]
0x1400ac214  mov     al, [rsp+1A8h+var_177]
0x1400ac218  mov     esi, ebx
0x1400ac21a  mov     r13, [rsp+1A8h+var_160]
0x1400ac21f  mov     rcx, [rsp+1A8h+var_158]
0x1400ac224  mov     [rsp+1A8h+var_138], rcx
0x1400ac229  mov     r12, [rsp+1A8h+var_150]
0x1400ac22e  mov     r15, [rsp+1A8h+var_148]
0x1400ac233  jmp     short loc_1400AC2A5
0x1400ac235  mov     r9d, 0C000000Dh
0x1400ac23b  mov     edi, r9d
0x1400ac23e  mov     r8d, 4E0h
0x1400ac244  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac24b  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac252  call    VidTraceErrorStatusInternal0
0x1400ac257  mov     al, [rsp+1A8h+var_178]
0x1400ac25b  jmp     short loc_1400AC2A5
0x1400ac25d  mov     r9d, 0C000000Dh
0x1400ac263  mov     edi, r9d
0x1400ac266  mov     r8d, 4D4h
0x1400ac26c  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac273  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac27a  call    VidTraceErrorStatusInternal0
0x1400ac27f  jmp     short loc_1400AC2A3
0x1400ac281  mov     r9d, 0C000000Dh
0x1400ac287  mov     edi, r9d
0x1400ac28a  mov     r8d, 49Bh
0x1400ac290  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac297  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac29e  call    VidTraceErrorStatusInternal0
0x1400ac2a3  mov     al, bl
0x1400ac2a5  test    al, al
0x1400ac2a7  jz      short loc_1400AC2B5
0x1400ac2a9  lea     rcx, [r13+0E98h]
0x1400ac2b0  call    VidObjectLockRelease
0x1400ac2b5  test    r14, r14
0x1400ac2b8  jz      loc_1400AC416
0x1400ac2be  test    edi, edi
0x1400ac2c0  jns     loc_1400AC40A
0x1400ac2c6  mov     eax, cs:dword_140064110
0x1400ac2cc  cmp     eax, 2
0x1400ac2cf  jbe     loc_1400AC40A
0x1400ac2d5  mov     edx, 100h
0x1400ac2da  lea     rcx, dword_140064110
0x1400ac2e1  call    _tlgKeywordOn
0x1400ac2e6  test    al, al
0x1400ac2e8  jz      loc_1400AC40A
0x1400ac2ee  lea     rdx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac2f5  lea     rcx, [rsp+1A8h+var_108]
0x1400ac2fd  call    _tlgCreate1Sz_char
0x1400ac302  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ac309  lea     rcx, [rsp+1A8h+var_F8]
0x1400ac311  call    _tlgCreate1Sz_char
0x1400ac316  mov     dword ptr [rsp+1A8h+var_160], 52Bh
0x1400ac31e  lea     rax, [rsp+1A8h+var_160]
0x1400ac323  mov     [rsp+1A8h+var_E8], rax
0x1400ac32b  mov     [rsp+1A8h+var_E0], 4
0x1400ac337  mov     dword ptr [rsp+1A8h+var_170], edi
0x1400ac33b  lea     rax, [rsp+1A8h+var_170]
0x1400ac340  mov     [rsp+1A8h+var_D8], rax
0x1400ac348  mov     [rsp+1A8h+var_D0], 4
0x1400ac354  mov     rax, [r14+18h]
0x1400ac358  mov     [rsp+1A8h+Address], rax
0x1400ac35d  lea     rax, [rsp+1A8h+Address]
0x1400ac362  mov     [rsp+1A8h+var_C8], rax
0x1400ac36a  mov     [rsp+1A8h+var_C0], 8
0x1400ac376  mov     rax, [r14+28h]
0x1400ac37a  mov     [rsp+1A8h+var_148], rax
0x1400ac37f  lea     rax, [rsp+1A8h+var_148]
0x1400ac384  mov     [rsp+1A8h+var_B8], rax
0x1400ac38c  mov     [rsp+1A8h+var_B0], 8
0x1400ac398  mov     rax, [r14+30h]
0x1400ac39c  mov     [rsp+1A8h+var_150], rax
0x1400ac3a1  lea     rax, [rsp+1A8h+var_150]
0x1400ac3a6  mov     [rsp+1A8h+var_A8], rax
0x1400ac3ae  mov     [rsp+1A8h+var_A0], 8
0x1400ac3ba  movsxd  rax, dword ptr [r14+14h]
0x1400ac3be  mov     [rsp+1A8h+var_158], rax
0x1400ac3c3  lea     rax, [rsp+1A8h+var_158]
0x1400ac3c8  mov     [rsp+1A8h+var_98], rax
0x1400ac3d0  mov     [rsp+1A8h+var_90], 8
0x1400ac3dc  lea     rax, [rsp+1A8h+var_128]
0x1400ac3e4  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400ac3e9  mov     dword ptr [rsp+1A8h+Irp], 0Ah
0x1400ac3f1  xor     r9d, r9d
0x1400ac3f4  xor     r8d, r8d
0x1400ac3f7  lea     rdx, byte_14004DD49
0x1400ac3fe  lea     rcx, dword_140064110
0x1400ac405  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ac40a  lea     rcx, [r14+80h]
0x1400ac411  call    VidOpCtrlFinish
0x1400ac416  cmp     [rsp+1A8h+var_176], bl
0x1400ac41a  jz      short loc_1400AC42B
0x1400ac41c  mov     rcx, rsi; MemoryDescriptorList
0x1400ac41f  call    cs:__imp_MmUnlockPages
0x1400ac426  nop     dword ptr [rax+rax+00h]
0x1400ac42b  test    rsi, rsi
0x1400ac42e  jz      short loc_1400AC43F
0x1400ac430  mov     rcx, rsi; Mdl
0x1400ac433  call    cs:__imp_IoFreeMdl
0x1400ac43a  nop     dword ptr [rax+rax+00h]
0x1400ac43f  test    edi, edi
0x1400ac441  jns     loc_1400AC604
0x1400ac447  mov     eax, cs:dword_140064110
0x1400ac44d  cmp     eax, 2
0x1400ac450  jbe     loc_1400AC604
0x1400ac456  mov     edx, 100h
0x1400ac45b  lea     rcx, dword_140064110
0x1400ac462  call    _tlgKeywordOn
0x1400ac467  test    al, al
0x1400ac469  jz      loc_1400AC604
0x1400ac46f  lea     rdx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ac476  lea     rcx, [rsp+1A8h+var_108]
  ... truncated ...
```
