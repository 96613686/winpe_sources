# VsmmVsmIoctlGetMemoryBlockProtections

- ea: `0x1400aabe0`
- end: `0x1400ab761`
- name: `VsmmVsmIoctlGetMemoryBlockProtections`
- size: `2945`
- prototype: `__int64 __fastcall(SIZE_T, SIZE_T, SIZE_T, SIZE_T, volatile void *Address)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400303c0`
- `0x140034554`
- `0x140034584`
- `0x1400aabe0`
- `0x1400ae630`
- `0x1400f42c8`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400aad10`
- `ntoskrnl!ProbeForWrite` at `0x1400aad10`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400aaee0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400aaee0`
- `ntoskrnl!IoFreeMdl` at `0x1400ab428`
- `ntoskrnl!IoFreeMdl` at `0x1400ab428`
- `ntoskrnl!IoAllocateMdl` at `0x1400aad2e`
- `ntoskrnl!IoAllocateMdl` at `0x1400aad2e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400aaeab`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400aaeab`
- `ntoskrnl!MmUnlockPages` at `0x1400ab414`
- `ntoskrnl!MmUnlockPages` at `0x1400ab414`

## pseudocode

```c
__int64 __fastcall VsmmVsmIoctlGetMemoryBlockProtections(
        SIZE_T a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        SIZE_T a4,
        volatile void *Address)
{
  __int64 v7; // rsi
  struct _MDL *v8; // r14
  int VsmMbpArray; // edi
  int v10; // eax
  SIZE_T v11; // rax
  struct _MDL *Mdl; // rax
  int v13; // r8d
  __int64 v14; // rax
  unsigned __int64 *v15; // rcx
  char *v16; // rdx
  SIZE_T v17; // rcx
  PVOID MappedSystemVa; // rax
  int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // rax
  char v22; // al
  int v24; // [rsp+34h] [rbp-164h] BYREF
  int v25; // [rsp+38h] [rbp-160h] BYREF
  char v26; // [rsp+3Ch] [rbp-15Ch]
  char v27; // [rsp+3Dh] [rbp-15Bh]
  SIZE_T v28; // [rsp+40h] [rbp-158h] BYREF
  __int64 v29; // [rsp+48h] [rbp-150h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-148h]
  SIZE_T v31; // [rsp+58h] [rbp-140h] BYREF
  unsigned __int64 v32; // [rsp+60h] [rbp-138h] BYREF
  unsigned __int64 v33; // [rsp+68h] [rbp-130h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-128h]
  PMDL MemoryDescriptorList; // [rsp+78h] [rbp-120h]
  _BYTE v36[24]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-F8h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-E8h] BYREF
  int *v39; // [rsp+C0h] [rbp-D8h]
  __int64 v40; // [rsp+C8h] [rbp-D0h]
  int *v41; // [rsp+D0h] [rbp-C8h]
  __int64 v42; // [rsp+D8h] [rbp-C0h]
  SIZE_T *v43; // [rsp+E0h] [rbp-B8h]
  __int64 v44; // [rsp+E8h] [rbp-B0h]
  __int64 *v45; // [rsp+F0h] [rbp-A8h]
  __int64 v46; // [rsp+F8h] [rbp-A0h]
  unsigned __int64 *v47; // [rsp+100h] [rbp-98h]
  __int64 v48; // [rsp+108h] [rbp-90h] BYREF
  SIZE_T *v49; // [rsp+110h] [rbp-88h]
  __int64 v50; // [rsp+118h] [rbp-80h]
  unsigned __int64 *v51; // [rsp+120h] [rbp-78h]
  __int64 v52; // [rsp+128h] [rbp-70h]
  unsigned __int64 *v53; // [rsp+130h] [rbp-68h]
  __int64 v54; // [rsp+138h] [rbp-60h]
  SIZE_T *v55; // [rsp+140h] [rbp-58h]
  __int64 v56; // [rsp+148h] [rbp-50h]

  v34 = a3;
  v30 = a2;
  v31 = a1;
  v32 = a2;
  v33 = a3;
  v28 = a4;
  v7 = 0;
  v29 = 0;
  v8 = 0;
  v27 = 0;
  if ( (*(_BYTE *)(a1 + 16) & 8) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x31E0LL) != 0 )
    {
      VsmMbpArray = -1073741790;
      goto LABEL_33;
    }
    if ( !a4 || !Address || ((a4 + ((unsigned __int16)Address & 0xFFF) + 4095LL) & 0xFFFFFFFFFFFFF000uLL) > 0xFFFFF000 )
    {
      VsmMbpArray = -1073741811;
      goto LABEL_33;
    }
    v10 = VsmmMemoryBlockLookupByHandle(a1, a2, 0, 0, (__int64)&v29);
    v7 = v29;
    if ( v10 < 0 || (*(_DWORD *)(v29 + 20) & 1) == 0 )
    {
      VsmMbpArray = -1070137326;
      goto LABEL_33;
    }
    VidObjectLockAcquireShared(a1 + 3736);
    v26 = 1;
    v11 = *(_QWORD *)(v7 + 48);
    if ( a4 > v11 || v34 > v11 - a4 )
    {
      VsmMbpArray = -1073741811;
      goto LABEL_30;
    }
    ProbeForWrite(Address, a4, 1u);
    Mdl = IoAllocateMdl((PVOID)Address, a4, 0, 0, 0);
    v8 = Mdl;
    MemoryDescriptorList = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
      v27 = 1;
      if ( (v8->MdlFlags & 5) != 0 )
        MappedSystemVa = v8->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u);
      if ( MappedSystemVa )
      {
        VsmMbpArray = VsmmVsmpQueryVsmMbpArray(v7, v34, a4, MappedSystemVa);
        if ( VsmMbpArray >= 0 )
        {
          VsmMbpArray = 0;
          goto LABEL_30;
        }
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_30;
        tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        v25 = 952;
        v39 = &v25;
        v40 = 4;
        v24 = VsmMbpArray;
        v41 = &v24;
        v42 = 4;
        v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
        v44 = 16;
        v21 = *(_QWORD *)(v7 + 8);
        v15 = *(unsigned __int64 **)(v21 + 128);
        LODWORD(v48) = *(unsigned __int16 *)(v21 + 120);
        v16 = (char *)&word_14004DBCE;
      }
      else
      {
        VsmMbpArray = -1073741670;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_30;
        tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        v25 = 937;
        v39 = &v25;
        v40 = 4;
        v24 = v19;
        v41 = &v24;
        v42 = 4;
        v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
        v44 = 16;
        v20 = *(_QWORD *)(v7 + 8);
        v15 = *(unsigned __int64 **)(v20 + 128);
        LODWORD(v48) = *(unsigned __int16 *)(v20 + 120);
        v16 = byte_14004DF05;
      }
    }
    else
    {
      VsmMbpArray = -1073741670;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_30;
      tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      v24 = 914;
      v39 = &v24;
      v40 = 4;
      v25 = v13;
      v41 = &v25;
      v42 = 4;
      v43 = (SIZE_T *)(*(_QWORD *)(v7 + 8) + 656LL);
      v44 = 16;
      v14 = *(_QWORD *)(v7 + 8);
      v15 = *(unsigned __int64 **)(v14 + 128);
      LODWORD(v48) = *(unsigned __int16 *)(v14 + 120);
      v16 = byte_14004DE29;
    }
    v45 = &v48;
    v46 = 2;
    v47 = v15;
    HIDWORD(v48) = 0;
    v17 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 648LL);
    v49 = &v28;
    v28 = v17;
    v50 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v16, 0, 0, 10, v36);
LABEL_30:
    v22 = 1;
    goto LABEL_34;
  }
  VsmMbpArray = -1073741637;
LABEL_33:
  v22 = 0;
LABEL_34:
  if ( v22 )
    VidObjectLockRelease(a1 + 3736);
  if ( v27 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  if ( v7 )
  {
    if ( VsmMbpArray < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
      v25 = 976;
      v39 = &v25;
      v40 = 4;
      v24 = VsmMbpArray;
      v41 = &v24;
      v42 = 4;
      v28 = *(_QWORD *)(v7 + 24);
      v43 = &v28;
      v44 = 8;
      v33 = *(_QWORD *)(v7 + 40);
      v45 = (__int64 *)&v33;
      v46 = 8;
      v32 = *(_QWORD *)(v7 + 48);
      v47 = &v32;
      v48 = 8;
      v31 = *(int *)(v7 + 20);
      v49 = &v31;
      v50 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_14004DC3C, 0, 0, 10, v36);
    }
    VidOpCtrlFinish(v7 + 128);
  }
  if ( VsmMbpArray < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v37, "VsmmVsmIoctlGetMemoryBlockProtections");
    tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
    v25 = 986;
    v39 = &v25;
    v40 = 4;
    v24 = VsmMbpArray;
    v41 = &v24;
    v42 = 4;
    v43 = (SIZE_T *)(a1 + 656);
    v44 = 16;
    v45 = &v48;
    v46 = 2;
    v47 = *(unsigned __int64 **)(a1 + 128);
    v48 = *(unsigned __int16 *)(a1 + 120);
    v28 = *(_QWORD *)(a1 + 648);
    v49 = &v28;
    v50 = 8;
    v33 = v30;
    v51 = &v33;
    v52 = 8;
    v32 = v34;
    v53 = &v32;
    v54 = 8;
    v31 = a4;
    v55 = &v31;
    v56 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14004DCAE, 0, 0, 13, v36);
  }
  return (unsigned int)VsmMbpArray;
}

```

## disassembly

```asm
0x1400aabe0  push    rbx
0x1400aabe2  push    rsi
0x1400aabe3  push    rdi
0x1400aabe4  push    r12
0x1400aabe6  push    r13
0x1400aabe8  push    r14
0x1400aabea  push    r15
0x1400aabec  sub     rsp, 160h
0x1400aabf3  mov     rax, cs:__security_cookie
0x1400aabfa  xor     rax, rsp
0x1400aabfd  mov     [rsp+198h+var_48], rax
0x1400aac05  mov     r15, r9
0x1400aac08  mov     [rsp+198h+var_128], r8
0x1400aac0d  mov     [rsp+198h+var_148], rdx
0x1400aac12  mov     r13, rcx
0x1400aac15  mov     [rsp+198h+var_140], rcx
0x1400aac1a  mov     [rsp+198h+var_138], rdx
0x1400aac1f  mov     [rsp+198h+var_130], r8
0x1400aac24  mov     [rsp+198h+var_158], r9
0x1400aac29  mov     rdi, [rsp+198h+Address]
0x1400aac31  xor     ebx, ebx
0x1400aac33  mov     esi, ebx
0x1400aac35  mov     [rsp+198h+var_150], rbx
0x1400aac3a  mov     r14d, ebx
0x1400aac3d  mov     [rsp+198h+var_15B], bl
0x1400aac41  lea     r12d, [rbx+8]
0x1400aac45  test    [rcx+10h], r12b
0x1400aac49  jnz     short loc_1400AAC55
0x1400aac4b  mov     edi, 0C00000BBh
0x1400aac50  jmp     loc_1400AB3F9
0x1400aac55  mov     eax, [rcx+20h]
0x1400aac58  test    rax, 31E0h
0x1400aac5e  jz      short loc_1400AAC6A
0x1400aac60  mov     edi, 0C0000022h
0x1400aac65  jmp     loc_1400AB3F9
0x1400aac6a  test    r15, r15
0x1400aac6d  jz      loc_1400AB3F4
0x1400aac73  test    rdi, rdi
0x1400aac76  jz      loc_1400AB3F4
0x1400aac7c  mov     ecx, edi
0x1400aac7e  and     ecx, 0FFFh
0x1400aac84  add     rcx, 0FFFh
0x1400aac8b  add     rcx, r15
0x1400aac8e  and     rcx, 0FFFFFFFFFFFFF000h
0x1400aac95  mov     eax, 0FFFFF000h
0x1400aac9a  cmp     rcx, rax
0x1400aac9d  ja      loc_1400AB3F4
0x1400aaca3  lea     rax, [rsp+198h+var_150]
0x1400aaca8  mov     [rsp+198h+Irp], rax
0x1400aacad  xor     r9d, r9d
0x1400aacb0  xor     r8d, r8d
0x1400aacb3  mov     rcx, r13
0x1400aacb6  call    VsmmMemoryBlockLookupByHandle
0x1400aacbb  mov     rsi, [rsp+198h+var_150]
0x1400aacc0  test    eax, eax
0x1400aacc2  js      loc_1400AB3ED
0x1400aacc8  mov     eax, [rsi+14h]
0x1400aaccb  test    al, 1
0x1400aaccd  jz      loc_1400AB3ED
0x1400aacd3  lea     rcx, [r13+0E98h]
0x1400aacda  call    VidObjectLockAcquireShared
0x1400aacdf  mov     al, 1
0x1400aace1  mov     [rsp+198h+var_168], al
0x1400aace5  mov     [rsp+198h+var_15C], al
0x1400aace9  mov     rax, [rsi+30h]
0x1400aaced  cmp     r15, rax
0x1400aacf0  ja      loc_1400AB3E2
0x1400aacf6  sub     rax, r15
0x1400aacf9  cmp     [rsp+198h+var_128], rax
0x1400aacfe  ja      loc_1400AB3E2
0x1400aad04  mov     r8d, 1; Alignment
0x1400aad0a  mov     rdx, r15; Length
0x1400aad0d  mov     rcx, rdi; Address
0x1400aad10  call    cs:__imp_ProbeForWrite
0x1400aad17  nop     dword ptr [rax+rax+00h]
0x1400aad1c  nop
0x1400aad1d  mov     edx, r15d; Length
0x1400aad20  mov     [rsp+198h+Irp], rbx; Irp
0x1400aad25  xor     r9d, r9d; ChargeQuota
0x1400aad28  xor     r8d, r8d; SecondaryBuffer
0x1400aad2b  mov     rcx, rdi; VirtualAddress
0x1400aad2e  call    cs:__imp_IoAllocateMdl
0x1400aad35  nop     dword ptr [rax+rax+00h]
0x1400aad3a  mov     r14, rax
0x1400aad3d  mov     [rsp+198h+MemoryDescriptorList], rax
0x1400aad42  test    rax, rax
0x1400aad45  jnz     loc_1400AAE9E
0x1400aad4b  mov     r8d, 0C000009Ah
0x1400aad51  mov     edi, r8d
0x1400aad54  mov     ecx, cs:dword_140064110
0x1400aad5a  cmp     ecx, 2
0x1400aad5d  jbe     loc_1400AB3E7
0x1400aad63  mov     edx, 100h
0x1400aad68  lea     rcx, dword_140064110
0x1400aad6f  call    _tlgKeywordOn
0x1400aad74  test    al, al
0x1400aad76  jz      loc_1400AB3E7
0x1400aad7c  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400aad83  lea     rcx, [rsp+198h+var_F8]
0x1400aad8b  call    _tlgCreate1Sz_char
0x1400aad90  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400aad97  lea     rcx, [rsp+198h+var_E8]
0x1400aad9f  call    _tlgCreate1Sz_char
0x1400aada4  mov     [rsp+198h+var_164], 392h
0x1400aadac  lea     rax, [rsp+198h+var_164]
0x1400aadb1  mov     [rsp+198h+var_D8], rax
0x1400aadb9  mov     [rsp+198h+var_D0], 4
0x1400aadc5  mov     [rsp+198h+var_160], r8d
0x1400aadca  lea     rax, [rsp+198h+var_160]
0x1400aadcf  mov     [rsp+198h+var_C8], rax
0x1400aadd7  mov     [rsp+198h+var_C0], 4
0x1400aade3  mov     rax, [rsi+8]
0x1400aade7  add     rax, 290h
0x1400aaded  mov     [rsp+198h+var_B8], rax
0x1400aadf5  mov     [rsp+198h+var_B0], 10h
0x1400aae01  mov     rax, [rsi+8]
0x1400aae05  movzx   edx, word ptr [rax+78h]
0x1400aae09  mov     rcx, [rax+80h]
0x1400aae10  mov     dword ptr [rsp+198h+var_90], edx
0x1400aae17  lea     rdx, byte_14004DE29
0x1400aae1e  lea     rax, [rsp+198h+var_90]
0x1400aae26  mov     [rsp+198h+var_A8], rax
0x1400aae2e  mov     [rsp+198h+var_A0], 2
0x1400aae3a  mov     [rsp+198h+var_98], rcx
0x1400aae42  mov     dword ptr [rsp+198h+var_90+4], ebx
0x1400aae49  mov     rax, [rsi+8]
0x1400aae4d  mov     rcx, [rax+288h]
0x1400aae54  lea     rax, [rsp+198h+var_158]
0x1400aae59  mov     [rsp+198h+var_88], rax
0x1400aae61  lea     rax, [rsp+198h+var_118]
0x1400aae69  mov     qword ptr [rsp+198h+Priority], rax
0x1400aae6e  xor     r9d, r9d
0x1400aae71  mov     [rsp+198h+var_158], rcx
0x1400aae76  mov     [rsp+198h+var_80], 8
0x1400aae82  mov     dword ptr [rsp+198h+Irp], 0Ah
0x1400aae8a  xor     r8d, r8d
0x1400aae8d  lea     rcx, dword_140064110
0x1400aae94  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400aae99  jmp     loc_1400AB3E7
0x1400aae9e  mov     edi, 1
0x1400aaea3  mov     r8d, edi; Operation
0x1400aaea6  xor     edx, edx; AccessMode
0x1400aaea8  mov     rcx, r14; MemoryDescriptorList
0x1400aaeab  call    cs:__imp_MmProbeAndLockPages
0x1400aaeb2  nop     dword ptr [rax+rax+00h]
0x1400aaeb7  mov     [rsp+198h+var_15B], dil
0x1400aaebc  test    byte ptr [r14+0Ah], 5
0x1400aaec1  jz      short loc_1400AAEC9
0x1400aaec3  mov     rax, [r14+18h]
0x1400aaec7  jmp     short loc_1400AAEEC
0x1400aaec9  mov     [rsp+198h+Priority], 40000010h; Priority
0x1400aaed1  mov     dword ptr [rsp+198h+Irp], ebx; BugCheckOnFailure
0x1400aaed5  xor     r9d, r9d; RequestedAddress
0x1400aaed8  mov     r8d, edi; CacheType
0x1400aaedb  xor     edx, edx; AccessMode
0x1400aaedd  mov     rcx, r14; MemoryDescriptorList
0x1400aaee0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400aaee7  nop     dword ptr [rax+rax+00h]
0x1400aaeec  test    rax, rax
0x1400aaeef  jnz     loc_1400AAFCD
0x1400aaef5  mov     r8d, 0C000009Ah
0x1400aaefb  mov     edi, r8d
0x1400aaefe  mov     eax, cs:dword_140064110
0x1400aaf04  cmp     eax, 2
0x1400aaf07  jbe     loc_1400AB3E7
0x1400aaf0d  mov     edx, 100h
0x1400aaf12  lea     rcx, dword_140064110
0x1400aaf19  call    _tlgKeywordOn
0x1400aaf1e  test    al, al
0x1400aaf20  jz      loc_1400AB3E7
0x1400aaf26  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400aaf2d  lea     rcx, [rsp+198h+var_F8]
0x1400aaf35  call    _tlgCreate1Sz_char
0x1400aaf3a  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400aaf41  lea     rcx, [rsp+198h+var_E8]
0x1400aaf49  call    _tlgCreate1Sz_char
0x1400aaf4e  mov     [rsp+198h+var_160], 3A9h
0x1400aaf56  lea     rax, [rsp+198h+var_160]
0x1400aaf5b  mov     [rsp+198h+var_D8], rax
0x1400aaf63  mov     [rsp+198h+var_D0], 4
0x1400aaf6f  mov     [rsp+198h+var_164], r8d
0x1400aaf74  lea     rax, [rsp+198h+var_164]
0x1400aaf79  mov     [rsp+198h+var_C8], rax
0x1400aaf81  mov     [rsp+198h+var_C0], 4
0x1400aaf8d  mov     rax, [rsi+8]
0x1400aaf91  add     rax, 290h
0x1400aaf97  mov     [rsp+198h+var_B8], rax
0x1400aaf9f  mov     [rsp+198h+var_B0], 10h
0x1400aafab  mov     rax, [rsi+8]
0x1400aafaf  movzx   edx, word ptr [rax+78h]
0x1400aafb3  mov     rcx, [rax+80h]
0x1400aafba  mov     dword ptr [rsp+198h+var_90], edx
0x1400aafc1  lea     rdx, byte_14004DF05
0x1400aafc8  jmp     loc_1400AAE1E
0x1400aafcd  mov     r9, rax
0x1400aafd0  mov     r8, r15
0x1400aafd3  mov     rdx, [rsp+198h+var_128]
0x1400aafd8  mov     rcx, rsi
0x1400aafdb  call    VsmmVsmpQueryVsmMbpArray
0x1400aafe0  mov     edi, eax
0x1400aafe2  test    eax, eax
0x1400aafe4  jns     loc_1400AB0B8
0x1400aafea  mov     ecx, cs:dword_140064110
0x1400aaff0  cmp     ecx, 2
0x1400aaff3  jbe     loc_1400AB3E7
0x1400aaff9  mov     edx, 100h
0x1400aaffe  lea     rcx, dword_140064110
0x1400ab005  call    _tlgKeywordOn
0x1400ab00a  test    al, al
0x1400ab00c  jz      loc_1400AB3E7
0x1400ab012  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400ab019  lea     rcx, [rsp+198h+var_F8]
0x1400ab021  call    _tlgCreate1Sz_char
0x1400ab026  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ab02d  lea     rcx, [rsp+198h+var_E8]
0x1400ab035  call    _tlgCreate1Sz_char
0x1400ab03a  mov     [rsp+198h+var_160], 3B8h
0x1400ab042  lea     rax, [rsp+198h+var_160]
0x1400ab047  mov     [rsp+198h+var_D8], rax
0x1400ab04f  mov     [rsp+198h+var_D0], 4
0x1400ab05b  mov     [rsp+198h+var_164], edi
0x1400ab05f  lea     rax, [rsp+198h+var_164]
0x1400ab064  mov     [rsp+198h+var_C8], rax
0x1400ab06c  mov     [rsp+198h+var_C0], 4
0x1400ab078  mov     rax, [rsi+8]
0x1400ab07c  add     rax, 290h
0x1400ab082  mov     [rsp+198h+var_B8], rax
0x1400ab08a  mov     [rsp+198h+var_B0], 10h
0x1400ab096  mov     rax, [rsi+8]
0x1400ab09a  movzx   edx, word ptr [rax+78h]
0x1400ab09e  mov     rcx, [rax+80h]
0x1400ab0a5  mov     dword ptr [rsp+198h+var_90], edx
0x1400ab0ac  lea     rdx, word_14004DBCE
0x1400ab0b3  jmp     loc_1400AAE1E
0x1400ab0b8  mov     edi, ebx
0x1400ab0ba  jmp     loc_1400AB3E7
0x1400ab0bf  mov     edi, eax
0x1400ab0c1  mov     eax, cs:dword_140064110
0x1400ab0c7  cmp     eax, 2
0x1400ab0ca  jbe     loc_1400AB220
0x1400ab0d0  mov     edx, 100h
0x1400ab0d5  lea     rcx, dword_140064110
0x1400ab0dc  call    _tlgKeywordOn
0x1400ab0e1  test    al, al
0x1400ab0e3  jz      loc_1400AB220
0x1400ab0e9  lea     rdx, aVsmmvsmioctlge_0; "VsmmVsmIoctlGetMemoryBlockProtections"
0x1400ab0f0  lea     rcx, [rsp+198h+var_F8]
0x1400ab0f8  call    _tlgCreate1Sz_char
0x1400ab0fd  lea     rdx, aOnecoreVmVidSy_63; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c"
0x1400ab104  lea     rcx, [rsp+198h+var_E8]
0x1400ab10c  call    _tlgCreate1Sz_char
0x1400ab111  mov     [rsp+198h+var_160], 39Eh
0x1400ab119  lea     rax, [rsp+198h+var_160]
0x1400ab11e  mov     [rsp+198h+var_D8], rax
0x1400ab126  mov     [rsp+198h+var_D0], 4
0x1400ab132  mov     [rsp+198h+var_164], edi
0x1400ab136  lea     rax, [rsp+198h+var_164]
0x1400ab13b  mov     [rsp+198h+var_C8], rax
0x1400ab143  mov     [rsp+198h+var_C0], 4
0x1400ab14f  mov     rsi, [rsp+198h+var_150]
0x1400ab154  mov     rax, [rsi+8]
0x1400ab158  add     rax, 290h
0x1400ab15e  mov     [rsp+198h+var_B8], rax
0x1400ab166  mov     [rsp+198h+var_B0], 10h
0x1400ab172  mov     r8d, 7
0x1400ab178  mov     rax, [rsi+8]
0x1400ab17c  movzx   edx, word ptr [rax+78h]
0x1400ab180  mov     rcx, [rax+80h]
0x1400ab187  mov     eax, r8d
0x1400ab18a  shl     rax, 4
0x1400ab18e  lea     r9, [rsp+198h+var_100]
0x1400ab196  add     rax, r9
0x1400ab199  mov     [rsp+198h+var_A8], rax
0x1400ab1a1  mov     [rsp+198h+var_A0], 2
0x1400ab1ad  mov     [rsp+198h+var_98], rcx
0x1400ab1b5  mov     dword ptr [rsp+198h+var_90], edx
0x1400ab1bc  mov     dword ptr [rsp+198h+var_90+4], 0
0x1400ab1c7  mov     rax, [rsi+8]
0x1400ab1cb  mov     rcx, [rax+288h]
0x1400ab1d2  mov     [rsp+198h+var_148], rcx
0x1400ab1d7  lea     rax, [rsp+198h+var_148]
0x1400ab1dc  mov     [rsp+198h+var_88], rax
0x1400ab1e4  mov     [rsp+198h+var_80], 8
0x1400ab1f0  lea     eax, [r8+3]
0x1400ab1f4  lea     rcx, [rsp+198h+var_118]
0x1400ab1fc  mov     qword ptr [rsp+198h+Priority], rcx
0x1400ab201  mov     dword ptr [rsp+198h+Irp], eax
0x1400ab205  xor     r9d, r9d
0x1400ab208  xor     r8d, r8d
0x1400ab20b  lea     rdx, byte_14004DE97
0x1400ab212  lea     rcx, dword_140064110
0x1400ab219  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400ab21e  jmp     short loc_1400AB225
0x1400ab220  mov     rsi, [rsp+198h+var_150]
0x1400ab225  xor     ebx, ebx
0x1400ab227  mov     r14, [rsp+198h+MemoryDescriptorList]
0x1400ab22c  mov     al, [rsp+198h+var_15C]
0x1400ab230  mov     r13, [rsp+198h+var_140]
0x1400ab235  mov     rdx, [rsp+198h+var_138]
0x1400ab23a  mov     [rsp+198h+var_148], rdx
  ... truncated ...
```
