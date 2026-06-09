# VsmmVsmIoctlSetMemoryBlockProtections

- ea: `0x1400adc68`
- end: `0x1400ae3b8`
- name: `VsmmVsmIoctlSetMemoryBlockProtections`
- size: `1872`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400305c0`
- `0x1400347a4`
- `0x1400347d4`
- `0x1400386a0`
- `0x1400adc68`
- `0x1400af52c`
- `0x1400f6da8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400ade28`
- `ntoskrnl!ProbeForRead` at `0x1400ade28`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400adec3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400adec3`
- `ntoskrnl!IoFreeMdl` at `0x1400ae1c1`
- `ntoskrnl!IoFreeMdl` at `0x1400ae1c1`
- `ntoskrnl!IoAllocateMdl` at `0x1400ade46`
- `ntoskrnl!IoAllocateMdl` at `0x1400ade46`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ade8e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400ade8e`
- `ntoskrnl!MmUnlockPages` at `0x1400ae1ad`
- `ntoskrnl!MmUnlockPages` at `0x1400ae1ad`

## pseudocode

```c
__int64 __fastcall VsmmVsmIoctlSetMemoryBlockProtections(
        __int64 a1,
        __int64 a2,
        SIZE_T a3,
        SIZE_T a4,
        volatile void *a5,
        int a6)
{
  __int64 v9; // r14
  struct _MDL *v10; // rsi
  int v11; // edi
  SIZE_T v12; // rax
  SIZE_T v13; // rax
  void *v14; // rdi
  struct _MDL *Mdl; // rax
  PVOID MappedSystemVa; // r9
  char v17; // al
  char v19; // [rsp+32h] [rbp-176h]
  struct _MDL *v20; // [rsp+38h] [rbp-170h] BYREF
  __int64 v21; // [rsp+40h] [rbp-168h] BYREF
  __int64 v22; // [rsp+48h] [rbp-160h] BYREF
  SIZE_T v23; // [rsp+50h] [rbp-158h] BYREF
  SIZE_T v24; // [rsp+58h] [rbp-150h] BYREF
  SIZE_T v25; // [rsp+60h] [rbp-148h] BYREF
  volatile void *Address; // [rsp+68h] [rbp-140h] BYREF
  __int64 v27; // [rsp+70h] [rbp-138h]
  _BYTE v28[32]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v30[16]; // [rsp+B0h] [rbp-F8h] BYREF
  _QWORD *v31; // [rsp+C0h] [rbp-E8h]
  __int64 v32; // [rsp+C8h] [rbp-E0h]
  _QWORD *v33; // [rsp+D0h] [rbp-D8h]
  __int64 v34; // [rsp+D8h] [rbp-D0h]
  volatile void **p_Address; // [rsp+E0h] [rbp-C8h]
  __int64 v36; // [rsp+E8h] [rbp-C0h]
  __int64 *v37; // [rsp+F0h] [rbp-B8h]
  __int64 v38; // [rsp+F8h] [rbp-B0h]
  SIZE_T *v39; // [rsp+100h] [rbp-A8h]
  __int64 v40; // [rsp+108h] [rbp-A0h] BYREF
  volatile void **v41; // [rsp+110h] [rbp-98h]
  __int64 v42; // [rsp+118h] [rbp-90h]
  SIZE_T *v43; // [rsp+120h] [rbp-88h]
  __int64 v44; // [rsp+128h] [rbp-80h]
  SIZE_T *v45; // [rsp+130h] [rbp-78h]
  __int64 v46; // [rsp+138h] [rbp-70h]
  SIZE_T *v47; // [rsp+140h] [rbp-68h]
  __int64 v48; // [rsp+148h] [rbp-60h]
  __int64 *v49; // [rsp+150h] [rbp-58h]
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
      1179,
      3221225485LL);
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
      1202,
      3221225506LL);
    goto LABEL_31;
  }
  v11 = VsmmMemoryBlockLookupByHandle(a1, a2, 0, 0, &v21);
  v9 = v21;
  if ( v11 < 0 )
    goto LABEL_31;
  if ( (*(_DWORD *)(v21 + 264) & 1) == 0 )
  {
    v11 = -1070137326;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1223,
      3224829970LL);
    goto LABEL_31;
  }
  v12 = *(_QWORD *)(v21 + 40);
  if ( a3 >= v12 || a4 > v12 || a3 > v12 - a4 )
  {
    v11 = -1073741811;
    VidTraceErrorStatusInternal0(
      "VsmmVsmIoctlSetMemoryBlockProtections",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c",
      1236,
      3221225485LL);
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
      1248,
      3221225485LL);
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
      1273,
      3221225626LL);
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
      1296,
      3221225626LL);
    goto LABEL_28;
  }
  v11 = VsmmVsmpApplyVsmMbpArray(v9, a3, a4, (_DWORD)MappedSystemVa, a6 & 1);
  v17 = 1;
  if ( v11 >= 0 )
    v11 = 0;
LABEL_32:
  if ( v17 )
    VidObjectLockRelease(a1 + 3736);
  if ( v9 )
  {
    if ( v11 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v29, "VsmmVsmIoctlSetMemoryBlockProtections");
      tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      LODWORD(v22) = 1323;
      v31 = &v22;
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
      v23 = *(int *)(v9 + 264);
      v41 = (volatile void **)&v23;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &dword_14004E244, 0, 0, 10, v28);
    }
    VidOpCtrlFinish(v9 + 128, a2, a3);
  }
  if ( v19 )
    MmUnlockPages(v10);
  if ( v10 )
    IoFreeMdl(v10);
  if ( v11 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v29, "VsmmVsmIoctlSetMemoryBlockProtections");
    tlgCreate1Sz_char(v30, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
    LODWORD(v20) = 1345;
    v31 = &v20;
    v32 = 4;
    LODWORD(v22) = v11;
    v33 = &v22;
    v34 = 4;
    p_Address = (volatile void **)(a1 + 656);
    v36 = 16;
    v37 = &v40;
    v38 = 2;
    v39 = *(SIZE_T **)(a1 + 128);
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
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_14004DF3D, 0, 0, 14, v28);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400adc68  push    rbx
0x1400adc6a  push    rsi
0x1400adc6b  push    rdi
0x1400adc6c  push    r12
0x1400adc6e  push    r13
0x1400adc70  push    r14
0x1400adc72  push    r15
0x1400adc74  sub     rsp, 170h
0x1400adc7b  mov     rax, cs:__security_cookie
0x1400adc82  xor     rax, rsp
0x1400adc85  mov     [rsp+1A8h+var_48], rax
0x1400adc8d  mov     r15, r9
0x1400adc90  mov     r12, r8
0x1400adc93  mov     [rsp+1A8h+var_138], rdx
0x1400adc98  mov     r13, rcx
0x1400adc9b  mov     [rsp+1A8h+var_160], rcx
0x1400adca0  mov     [rsp+1A8h+var_158], rdx
0x1400adca5  mov     [rsp+1A8h+var_150], r8
0x1400adcaa  mov     [rsp+1A8h+var_148], r9
0x1400adcaf  mov     rcx, [rsp+1A8h+arg_20]
0x1400adcb7  mov     [rsp+1A8h+Address], rcx
0x1400adcbc  xor     ebx, ebx
0x1400adcbe  mov     r14d, ebx
0x1400adcc1  mov     [rsp+1A8h+var_168], rbx
0x1400adcc6  mov     esi, ebx
0x1400adcc8  mov     [rsp+1A8h+var_176], bl
0x1400adccc  test    byte ptr [r13+10h], 8
0x1400adcd1  jnz     short loc_1400ADCF6
0x1400adcd3  mov     edi, 0C00000BBh
0x1400adcd8  mov     r8d, 494h
0x1400adcde  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adce5  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400adcec  call    VidTraceErrorInternal0
0x1400adcf1  jmp     loc_1400AE02E
0x1400adcf6  test    r15, r15
0x1400adcf9  jz      loc_1400AE00C
0x1400adcff  test    rcx, rcx
0x1400add02  jz      loc_1400AE00C
0x1400add08  and     ecx, 0FFFh
0x1400add0e  add     rcx, 0FFFh
0x1400add15  add     rcx, r15
0x1400add18  and     rcx, 0FFFFFFFFFFFFF000h
0x1400add1f  mov     eax, 0FFFFF000h
0x1400add24  cmp     rcx, rax
0x1400add27  jbe     short loc_1400ADD33
0x1400add29  mov     edi, 0C000000Dh
0x1400add2e  jmp     loc_1400AE02E
0x1400add33  mov     eax, [r13+20h]
0x1400add37  test    rax, 31E0h
0x1400add3d  jz      short loc_1400ADD65
0x1400add3f  mov     edi, 0C0000022h
0x1400add44  mov     r9d, edi
0x1400add47  mov     r8d, 4B2h
0x1400add4d  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400add54  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400add5b  call    VidTraceErrorStatusInternal0
0x1400add60  jmp     loc_1400AE02E
0x1400add65  lea     rax, [rsp+1A8h+var_168]
0x1400add6a  mov     [rsp+1A8h+Irp], rax
0x1400add6f  xor     r9d, r9d
0x1400add72  xor     r8d, r8d
0x1400add75  mov     rcx, r13
0x1400add78  call    VsmmMemoryBlockLookupByHandle
0x1400add7d  mov     edi, eax
0x1400add7f  mov     r14, [rsp+1A8h+var_168]
0x1400add84  test    eax, eax
0x1400add86  js      loc_1400AE02E
0x1400add8c  mov     eax, [r14+108h]
0x1400add93  test    al, 1
0x1400add95  jnz     short loc_1400ADDBD
0x1400add97  mov     edi, 0C0370012h
0x1400add9c  mov     r9d, edi
0x1400add9f  mov     r8d, 4C7h
0x1400adda5  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400addac  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400addb3  call    VidTraceErrorStatusInternal0
0x1400addb8  jmp     loc_1400AE02E
0x1400addbd  mov     rax, [r14+28h]
0x1400addc1  cmp     r12, rax
0x1400addc4  jnb     loc_1400ADFE8
0x1400addca  cmp     r15, rax
0x1400addcd  ja      loc_1400ADFE8
0x1400addd3  sub     rax, r15
0x1400addd6  cmp     r12, rax
0x1400addd9  ja      loc_1400ADFE8
0x1400adddf  lea     rcx, [r13+0E98h]
0x1400adde6  call    VidObjectLockAcquireShared
0x1400addeb  mov     al, 1
0x1400added  mov     [rsp+1A8h+var_178], al
0x1400addf1  mov     [rsp+1A8h+var_177], al
0x1400addf5  mov     rax, [r14+30h]
0x1400addf9  cmp     r12, rax
0x1400addfc  jnb     loc_1400ADFC0
0x1400ade02  cmp     r15, rax
0x1400ade05  ja      loc_1400ADFC0
0x1400ade0b  sub     rax, r15
0x1400ade0e  cmp     r12, rax
0x1400ade11  ja      loc_1400ADFC0
0x1400ade17  mov     r8d, 1; Alignment
0x1400ade1d  mov     rdx, r15; Length
0x1400ade20  mov     rdi, [rsp+1A8h+Address]
0x1400ade25  mov     rcx, rdi; Address
0x1400ade28  call    cs:__imp_ProbeForRead
0x1400ade2f  nop     dword ptr [rax+rax+00h]
0x1400ade34  nop
0x1400ade35  mov     edx, r15d; Length
0x1400ade38  mov     [rsp+1A8h+Irp], rbx; Irp
0x1400ade3d  xor     r9d, r9d; ChargeQuota
0x1400ade40  xor     r8d, r8d; SecondaryBuffer
0x1400ade43  mov     rcx, rdi; VirtualAddress
0x1400ade46  call    cs:__imp_IoAllocateMdl
0x1400ade4d  nop     dword ptr [rax+rax+00h]
0x1400ade52  mov     rsi, rax
0x1400ade55  mov     [rsp+1A8h+var_170], rax
0x1400ade5a  test    rax, rax
0x1400ade5d  jnz     short loc_1400ADE86
0x1400ade5f  mov     r9d, 0C000009Ah
0x1400ade65  mov     edi, r9d
0x1400ade68  mov     r8d, 4F9h
0x1400ade6e  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ade75  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ade7c  call    VidTraceErrorStatusInternal0
0x1400ade81  jmp     loc_1400ADFE2
0x1400ade86  xor     r8d, r8d; Operation
0x1400ade89  xor     edx, edx; AccessMode
0x1400ade8b  mov     rcx, rsi; MemoryDescriptorList
0x1400ade8e  call    cs:__imp_MmProbeAndLockPages
0x1400ade95  nop     dword ptr [rax+rax+00h]
0x1400ade9a  mov     [rsp+1A8h+var_176], 1
0x1400ade9f  test    byte ptr [rsi+0Ah], 5
0x1400adea3  jz      short loc_1400ADEAB
0x1400adea5  mov     r9, [rsi+18h]
0x1400adea9  jmp     short loc_1400ADED2
0x1400adeab  mov     [rsp+1A8h+Priority], 0C0000010h; Priority
0x1400adeb3  mov     dword ptr [rsp+1A8h+Irp], ebx; BugCheckOnFailure
0x1400adeb7  xor     r9d, r9d; RequestedAddress
0x1400adeba  xor     edx, edx; AccessMode
0x1400adebc  lea     r8d, [r9+1]; CacheType
0x1400adec0  mov     rcx, rsi; MemoryDescriptorList
0x1400adec3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400adeca  nop     dword ptr [rax+rax+00h]
0x1400adecf  mov     r9, rax
0x1400aded2  test    r9, r9
0x1400aded5  jnz     short loc_1400ADEFE
0x1400aded7  mov     r9d, 0C000009Ah
0x1400adedd  mov     edi, r9d
0x1400adee0  mov     r8d, 510h
0x1400adee6  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adeed  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400adef4  call    VidTraceErrorStatusInternal0
0x1400adef9  jmp     loc_1400ADFE2
0x1400adefe  mov     eax, [rsp+1A8h+arg_28]
0x1400adf05  and     al, 1
0x1400adf07  mov     byte ptr [rsp+1A8h+Irp], al
0x1400adf0b  mov     r8, r15
0x1400adf0e  mov     rdx, r12
0x1400adf11  mov     rcx, r14
0x1400adf14  call    VsmmVsmpApplyVsmMbpArray
0x1400adf19  mov     edi, eax
0x1400adf1b  test    eax, eax
0x1400adf1d  mov     al, [rsp+1A8h+var_178]
0x1400adf21  js      loc_1400AE030
0x1400adf27  mov     edi, ebx
0x1400adf29  jmp     loc_1400AE030
0x1400adf2e  mov     edi, eax
0x1400adf30  mov     r9d, eax
0x1400adf33  mov     r8d, 505h
0x1400adf39  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adf40  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400adf47  call    VidTraceErrorStatusInternal0
0x1400adf4c  xor     ebx, ebx
0x1400adf4e  mov     r14, [rsp+1A8h+var_168]
0x1400adf53  mov     al, [rsp+1A8h+var_177]
0x1400adf57  mov     rsi, [rsp+1A8h+var_170]
0x1400adf5c  mov     r13, [rsp+1A8h+var_160]
0x1400adf61  mov     rcx, [rsp+1A8h+var_158]
0x1400adf66  mov     [rsp+1A8h+var_138], rcx
0x1400adf6b  mov     r12, [rsp+1A8h+var_150]
0x1400adf70  mov     r15, [rsp+1A8h+var_148]
0x1400adf75  jmp     loc_1400AE030
0x1400adf7a  mov     edi, eax
0x1400adf7c  mov     r9d, eax
0x1400adf7f  mov     r8d, 4EBh
0x1400adf85  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adf8c  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400adf93  call    VidTraceErrorStatusInternal0
0x1400adf98  xor     ebx, ebx
0x1400adf9a  mov     r14, [rsp+1A8h+var_168]
0x1400adf9f  mov     al, [rsp+1A8h+var_177]
0x1400adfa3  mov     esi, ebx
0x1400adfa5  mov     r13, [rsp+1A8h+var_160]
0x1400adfaa  mov     rcx, [rsp+1A8h+var_158]
0x1400adfaf  mov     [rsp+1A8h+var_138], rcx
0x1400adfb4  mov     r12, [rsp+1A8h+var_150]
0x1400adfb9  mov     r15, [rsp+1A8h+var_148]
0x1400adfbe  jmp     short loc_1400AE030
0x1400adfc0  mov     r9d, 0C000000Dh
0x1400adfc6  mov     edi, r9d
0x1400adfc9  mov     r8d, 4E0h
0x1400adfcf  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adfd6  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400adfdd  call    VidTraceErrorStatusInternal0
0x1400adfe2  mov     al, [rsp+1A8h+var_178]
0x1400adfe6  jmp     short loc_1400AE030
0x1400adfe8  mov     r9d, 0C000000Dh
0x1400adfee  mov     edi, r9d
0x1400adff1  mov     r8d, 4D4h
0x1400adff7  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400adffe  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ae005  call    VidTraceErrorStatusInternal0
0x1400ae00a  jmp     short loc_1400AE02E
0x1400ae00c  mov     r9d, 0C000000Dh
0x1400ae012  mov     edi, r9d
0x1400ae015  mov     r8d, 49Bh
0x1400ae01b  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae022  lea     rcx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ae029  call    VidTraceErrorStatusInternal0
0x1400ae02e  mov     al, bl
0x1400ae030  test    al, al
0x1400ae032  jz      short loc_1400AE040
0x1400ae034  lea     rcx, [r13+0E98h]
0x1400ae03b  call    VidObjectLockRelease
0x1400ae040  test    r14, r14
0x1400ae043  jz      loc_1400AE1A4
0x1400ae049  test    edi, edi
0x1400ae04b  jns     loc_1400AE198
0x1400ae051  mov     eax, cs:dword_140065110
0x1400ae057  cmp     eax, 2
0x1400ae05a  jbe     loc_1400AE198
0x1400ae060  mov     edx, 100h
0x1400ae065  lea     rcx, dword_140065110
0x1400ae06c  call    _tlgKeywordOn
0x1400ae071  test    al, al
0x1400ae073  jz      loc_1400AE198
0x1400ae079  lea     rdx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ae080  lea     rcx, [rsp+1A8h+var_108]
0x1400ae088  call    _tlgCreate1Sz_char
0x1400ae08d  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ae094  lea     rcx, [rsp+1A8h+var_F8]
0x1400ae09c  call    _tlgCreate1Sz_char
0x1400ae0a1  mov     dword ptr [rsp+1A8h+var_160], 52Bh
0x1400ae0a9  lea     rax, [rsp+1A8h+var_160]
0x1400ae0ae  mov     [rsp+1A8h+var_E8], rax
0x1400ae0b6  mov     [rsp+1A8h+var_E0], 4
0x1400ae0c2  mov     dword ptr [rsp+1A8h+var_170], edi
0x1400ae0c6  lea     rax, [rsp+1A8h+var_170]
0x1400ae0cb  mov     [rsp+1A8h+var_D8], rax
0x1400ae0d3  mov     [rsp+1A8h+var_D0], 4
0x1400ae0df  mov     rax, [r14+18h]
0x1400ae0e3  mov     [rsp+1A8h+Address], rax
0x1400ae0e8  lea     rax, [rsp+1A8h+Address]
0x1400ae0ed  mov     [rsp+1A8h+var_C8], rax
0x1400ae0f5  mov     [rsp+1A8h+var_C0], 8
0x1400ae101  mov     rax, [r14+28h]
0x1400ae105  mov     [rsp+1A8h+var_148], rax
0x1400ae10a  lea     rax, [rsp+1A8h+var_148]
0x1400ae10f  mov     [rsp+1A8h+var_B8], rax
0x1400ae117  mov     [rsp+1A8h+var_B0], 8
0x1400ae123  mov     rax, [r14+30h]
0x1400ae127  mov     [rsp+1A8h+var_150], rax
0x1400ae12c  lea     rax, [rsp+1A8h+var_150]
0x1400ae131  mov     [rsp+1A8h+var_A8], rax
0x1400ae139  mov     [rsp+1A8h+var_A0], 8
0x1400ae145  movsxd  rax, dword ptr [r14+108h]
0x1400ae14c  mov     [rsp+1A8h+var_158], rax
0x1400ae151  lea     rax, [rsp+1A8h+var_158]
0x1400ae156  mov     [rsp+1A8h+var_98], rax
0x1400ae15e  mov     [rsp+1A8h+var_90], 8
0x1400ae16a  lea     rax, [rsp+1A8h+var_128]
0x1400ae172  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400ae177  mov     dword ptr [rsp+1A8h+Irp], 0Ah
0x1400ae17f  xor     r9d, r9d
0x1400ae182  xor     r8d, r8d
0x1400ae185  lea     rdx, dword_14004E244
0x1400ae18c  lea     rcx, dword_140065110
0x1400ae193  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ae198  lea     rcx, [r14+80h]
0x1400ae19f  call    VidOpCtrlFinish
0x1400ae1a4  cmp     [rsp+1A8h+var_176], bl
0x1400ae1a8  jz      short loc_1400AE1B9
0x1400ae1aa  mov     rcx, rsi; MemoryDescriptorList
0x1400ae1ad  call    cs:__imp_MmUnlockPages
0x1400ae1b4  nop     dword ptr [rax+rax+00h]
0x1400ae1b9  test    rsi, rsi
0x1400ae1bc  jz      short loc_1400AE1CD
0x1400ae1be  mov     rcx, rsi; Mdl
0x1400ae1c1  call    cs:__imp_IoFreeMdl
0x1400ae1c8  nop     dword ptr [rax+rax+00h]
0x1400ae1cd  test    edi, edi
0x1400ae1cf  jns     loc_1400AE392
0x1400ae1d5  mov     eax, cs:dword_140065110
0x1400ae1db  cmp     eax, 2
0x1400ae1de  jbe     loc_1400AE392
0x1400ae1e4  mov     edx, 100h
0x1400ae1e9  lea     rcx, dword_140065110
0x1400ae1f0  call    _tlgKeywordOn
0x1400ae1f5  test    al, al
0x1400ae1f7  jz      loc_1400AE392
0x1400ae1fd  lea     rdx, aVsmmvsmioctlse_0; "VsmmVsmIoctlSetMemoryBlockProtections"
0x1400ae204  lea     rcx, [rsp+1A8h+var_108]
  ... truncated ...
```
