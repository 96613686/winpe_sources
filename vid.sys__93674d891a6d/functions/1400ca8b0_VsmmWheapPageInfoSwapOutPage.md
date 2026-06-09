# VsmmWheapPageInfoSwapOutPage

- ea: `0x1400ca8b0`
- end: `0x1400cb045`
- name: `VsmmWheapPageInfoSwapOutPage`
- size: `1941`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400cc118`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x1400071a4`
- `0x140007dbc`
- `0x14000a010`
- `0x14001b044`
- `0x14001b248`
- `0x140021c60`
- `0x140021e00`
- `0x14002f724`
- `0x1400347a4`
- `0x140034b64`
- `0x1400c8450`
- `0x1400c8a30`
- `0x1400ca8b0`
- `0x1400ea0d0`
- `0x1400ff40c`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400caddf`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400caddf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cacd6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400cacd6`
- `HAL!KeQueryPerformanceCounter` at `0x1400ca91a`
- `HAL!KeQueryPerformanceCounter` at `0x1400cae07`
- `HAL!KeQueryPerformanceCounter` at `0x1400ca91a`
- `HAL!KeQueryPerformanceCounter` at `0x1400cae07`
- `winhvr!WinHvGetPartitionProperty` at `0x1400ca983`
- `winhvr!WinHvGetPartitionProperty` at `0x1400ca983`

## pseudocode

```c
__int64 __fastcall VsmmWheapPageInfoSwapOutPage(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // r13
  unsigned int v4; // esi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r12
  int v10; // eax
  _QWORD *v11; // r15
  int v12; // edi
  int PartitionProperty; // eax
  __int64 v14; // r13
  __int64 v15; // rdx
  unsigned int v16; // ecx
  unsigned int v17; // r10d
  __int64 v18; // r8
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rax
  char *v24; // rax
  void *v25; // r13
  __int64 v26; // r8
  int v27; // r9d
  __int64 v28; // r8
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v44; // [rsp+A8h] [rbp-58h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE MemoryDescriptorList[64]; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v47[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v48[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v49[16]; // [rsp+130h] [rbp+30h] BYREF
  int *v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  int *v52; // [rsp+150h] [rbp+50h]
  __int64 v53; // [rsp+158h] [rbp+58h]
  __int64 v54; // [rsp+160h] [rbp+60h]
  __int64 v55; // [rsp+168h] [rbp+68h]
  unsigned __int64 *v56; // [rsp+170h] [rbp+70h]
  __int64 v57; // [rsp+178h] [rbp+78h]
  __int64 *v58; // [rsp+180h] [rbp+80h]
  unsigned __int64 v59; // [rsp+188h] [rbp+88h] BYREF
  __int64 *v60; // [rsp+190h] [rbp+90h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  __int64 *v62; // [rsp+1A0h] [rbp+A0h]
  __int64 v63; // [rsp+1A8h] [rbp+A8h]
  __int64 *v64; // [rsp+1B0h] [rbp+B0h]
  __int64 v65; // [rsp+1B8h] [rbp+B8h]
  __int64 *v66; // [rsp+1C0h] [rbp+C0h]
  __int64 v67; // [rsp+1C8h] [rbp+C8h]
  __int64 *v68; // [rsp+1D0h] [rbp+D0h]
  __int64 v69; // [rsp+1D8h] [rbp+D8h]
  int *v70; // [rsp+1E0h] [rbp+E0h]
  __int64 v71; // [rsp+1E8h] [rbp+E8h]
  int *v72; // [rsp+1F0h] [rbp+F0h]
  __int64 v73; // [rsp+1F8h] [rbp+F8h]
  __int64 *v74; // [rsp+200h] [rbp+100h]
  __int64 v75; // [rsp+208h] [rbp+108h]
  __int64 *v76; // [rsp+210h] [rbp+110h]
  __int64 v77; // [rsp+218h] [rbp+118h]

  v2 = a2;
  v32 = a2;
  memset(MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v34 = 0;
  PerformanceFrequency.QuadPart = 0;
  v4 = -1;
  v31 = 0;
  v30 = -1;
  v44 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v6 = *(_QWORD *)(a1 + 24);
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 32);
  *(LARGE_INTEGER *)&v44 = PerformanceCounter;
  v33 = *(_QWORD *)(v6 + 8);
  v9 = v33;
  v10 = VsmmWheapBadPageRegister(v6, v8, v7);
  v11 = (_QWORD *)(v33 + 648);
  v12 = v10;
  if ( v10 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmWheapPageInfoSwapOutPage",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
      2095,
      (unsigned int)v10);
    goto LABEL_31;
  }
  PartitionProperty = WinHvGetPartitionProperty(*v11, 327701, &v34);
  v12 = PartitionProperty;
  if ( PartitionProperty >= 0 )
  {
    if ( v34 && v34 != v2 )
    {
      v12 = v34 < v2 ? -1073741436 : -1073741637;
      _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 272LL), 1u);
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageInfoSwapOutPage",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        2156,
        (unsigned int)v12);
      v9 = v33;
      goto LABEL_29;
    }
  }
  else
  {
    if ( PartitionProperty != -1070268386 )
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageInfoSwapOutPage",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        2121,
        (unsigned int)PartitionProperty);
      goto LABEL_31;
    }
    v34 = 0;
  }
  v14 = v33 + 3736;
  VidObjectLockAcquireExclusive(v33 + 3736);
  VidPushLockAcquireExclusive(*(_QWORD *)(v6 + 400) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
  if ( (*(_DWORD *)(v6 + 264) & 0x1000) != 0 )
  {
    v12 = -1073741790;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v48, "VsmmWheapPageInfoSwapOutPage");
      tlgCreate1Sz_char(v49, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
      v15 = *(_QWORD *)(v6 + 8);
      v50 = &v31;
      v31 = 2178;
      v52 = &v30;
      v51 = 4;
      v54 = v15 + 656;
      v30 = -1073741790;
      v53 = 4;
      v55 = 16;
      v16 = *(unsigned __int16 *)(v15 + 120);
      v58 = *(__int64 **)(v15 + 128);
      v59 = __PAIR64__(v17, v16);
      v56 = &v59;
      v57 = v18;
      v33 = *(_QWORD *)(v15 + 648);
      v60 = &v33;
      v61 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)&byte_140053587, 0, 0, 0xAu, v47);
    }
  }
  else
  {
    v19 = VsmmHostAccessAcquireMbpRange(v6, *(_QWORD *)(a1 + 32), 1, 1, 0);
    v12 = v19;
    if ( v19 >= 0 )
    {
      v20 = VsmmMbpSwappingBegin(v6, *(_QWORD *)(a1 + 32), *(_QWORD *)(a1 + 16), (unsigned int)&v30, (__int64)&v31);
      v12 = v20;
      if ( v20 >= 0 )
      {
        VsmmUpdateGpaSpaceForMbpRangeModification(v33, v6, *(_QWORD *)(a1 + 32), 1, 0, -1, 0);
        VidPushLockRelease(*(_QWORD *)(v6 + 400) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
        VidObjectLockRelease(v14);
        v21 = *(_QWORD *)(a1 + 48);
        memset(&MemoryDescriptorList[12], 0, 28);
        *(_QWORD *)MemoryDescriptorList = 0;
        *(_DWORD *)&MemoryDescriptorList[8] = 131136;
        *(_QWORD *)&MemoryDescriptorList[40] = 0x2000;
        v22 = *(_QWORD *)(v21 + 48);
        v23 = *(_QWORD *)(a1 + 16);
        v35 = v22;
        *(_QWORD *)&MemoryDescriptorList[56] = v22;
        *(_QWORD *)&MemoryDescriptorList[48] = v23;
        v24 = (char *)MmMapLockedPagesSpecifyCache((PMDL)MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
        v25 = v24;
        if ( v24 )
        {
          qmemcpy(v24 + 4096, v24, 0x1000u);
          v12 = 0;
          *(_DWORD *)(a1 + 56) = 7;
        }
        else
        {
          v12 = -1073741801;
          VidTraceErrorStatusInternal0(
            "VsmmWheapPageInfoSwapOutPage",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
            2268,
            3221225495LL);
        }
        VidObjectLockAcquireExclusive(v33 + 3736);
        VidPushLockAcquireExclusive(*(_QWORD *)(v6 + 400) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
        v4 = v30;
        if ( v12 >= 0 )
        {
          LODWORD(v26) = v35;
          v27 = 0;
        }
        else
        {
          v26 = *(_QWORD *)(a1 + 16);
          v27 = v30;
        }
        VsmmMbpSwappingComplete(v6, *(_QWORD *)(a1 + 32), v26, v27, v31);
        v9 = v33;
        VsmmUpdateGpaSpaceForMbpRangeModification(v33, v6, *(_QWORD *)(a1 + 32), 1, 0, -1, 0);
        VidPushLockRelease(*(_QWORD *)(v6 + 400) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
        VidObjectLockRelease(v9 + 3736);
        if ( v25 )
          MmUnmapLockedPages(v25, (PMDL)MemoryDescriptorList);
        goto LABEL_28;
      }
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageInfoSwapOutPage",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        2213,
        (unsigned int)v20);
      v4 = v30;
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmWheapPageInfoSwapOutPage",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c",
        2196,
        (unsigned int)v19);
    }
    v9 = v33;
  }
  VidPushLockRelease(*(_QWORD *)(v6 + 400) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
  VidObjectLockRelease(v14);
LABEL_28:
  LODWORD(v2) = v32;
LABEL_29:
  if ( v12 >= 0 )
    VsmmWheapFreePage(v6, *(_QWORD *)(a1 + 16), v4);
LABEL_31:
  *((LARGE_INTEGER *)&v44 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
  if ( (unsigned int)dword_140065110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v48, "VsmmWheapPageInfoSwapOutPage");
    tlgCreate1Sz_char(v49, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
    v51 = v28;
    v50 = &v31;
    v35 = *v11;
    v52 = (int *)&v35;
    v54 = v9 + 656;
    v36 = *(_QWORD *)(v6 + 24);
    v56 = (unsigned __int64 *)&v36;
    v37 = *(_QWORD *)(v6 + 40);
    v58 = &v37;
    v38 = *(_QWORD *)(v6 + 48);
    v60 = &v38;
    v39 = *(int *)(v6 + 264);
    v62 = &v39;
    v40 = *(_QWORD *)(a1 + 32);
    v64 = &v40;
    v41 = *(_QWORD *)(a1 + 16);
    v66 = &v41;
    v42 = v34;
    v68 = (__int64 *)&v42;
    v70 = &v32;
    v72 = &v30;
    v71 = v28;
    v73 = v28;
    v77 = v28;
    v43 = 1000000LL * (*((_QWORD *)&v44 + 1) - (_QWORD)v44) / PerformanceFrequency.QuadPart;
    v31 = 2370;
    v74 = &v43;
    LODWORD(v33) = *(_DWORD *)(a1 + 56);
    v76 = &v33;
    v53 = 8;
    v55 = 16;
    v57 = 8;
    v59 = 8;
    v61 = 8;
    v63 = 8;
    v65 = 8;
    v67 = 8;
    v69 = 8;
    v32 = v2;
    v30 = v12;
    v75 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140065110, (unsigned __int8 *)byte_1400535F5, 0, 0, 0x12u, v47);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400ca8b0  push    rbp
0x1400ca8b2  push    rbx
0x1400ca8b3  push    rsi
0x1400ca8b4  push    rdi
0x1400ca8b5  push    r12
0x1400ca8b7  push    r13
0x1400ca8b9  push    r14
0x1400ca8bb  push    r15
0x1400ca8bd  lea     rbp, [rsp-138h]
0x1400ca8c5  sub     rsp, 238h
0x1400ca8cc  mov     rax, cs:__security_cookie
0x1400ca8d3  xor     rax, rsp
0x1400ca8d6  mov     [rbp+170h+var_50], rax
0x1400ca8dd  mov     r13d, edx
0x1400ca8e0  mov     rbx, rcx
0x1400ca8e3  xor     edx, edx; Val
0x1400ca8e5  mov     [rsp+270h+var_228], r13d
0x1400ca8ea  lea     rcx, [rbp+170h+MemoryDescriptorList]; void *
0x1400ca8ee  lea     r8d, [rdx+40h]; Size
0x1400ca8f2  call    memset
0x1400ca8f7  xor     eax, eax
0x1400ca8f9  mov     [rsp+270h+var_218], 0
0x1400ca902  xorps   xmm0, xmm0
0x1400ca905  mov     qword ptr [rbp+170h+PerformanceFrequency], rax
0x1400ca909  or      esi, 0FFFFFFFFh
0x1400ca90c  mov     [rsp+270h+var_22C], eax
0x1400ca910  xor     ecx, ecx; PerformanceFrequency
0x1400ca912  mov     [rsp+270h+var_230], esi
0x1400ca916  movups  [rbp+170h+var_1C8], xmm0
0x1400ca91a  call    cs:__imp_KeQueryPerformanceCounter
0x1400ca921  nop     dword ptr [rax+rax+00h]
0x1400ca926  mov     r14, [rbx+18h]
0x1400ca92a  mov     r8, [rbx+10h]
0x1400ca92e  mov     rcx, r14
0x1400ca931  mov     rdx, [rbx+20h]
0x1400ca935  mov     qword ptr [rbp+170h+var_1C8], rax
0x1400ca939  mov     r12, [r14+8]
0x1400ca93d  mov     [rsp+270h+var_220], r12
0x1400ca942  call    VsmmWheapBadPageRegister
0x1400ca947  lea     r15, [r12+288h]
0x1400ca94f  mov     edi, eax
0x1400ca951  test    eax, eax
0x1400ca953  jns     short loc_1400CA976
0x1400ca955  mov     r9d, eax
0x1400ca958  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400ca95f  mov     r8d, 82Fh
0x1400ca965  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400ca96c  call    VidTraceErrorStatusInternal0
0x1400ca971  jmp     loc_1400CAE03
0x1400ca976  mov     rcx, [r15]
0x1400ca979  lea     r8, [rsp+270h+var_218]
0x1400ca97e  mov     edx, 50015h
0x1400ca983  call    cs:__imp_WinHvGetPartitionProperty
0x1400ca98a  nop     dword ptr [rax+rax+00h]
0x1400ca98f  mov     edi, eax
0x1400ca991  test    eax, eax
0x1400ca993  jns     loc_1400CAB22
0x1400ca999  cmp     eax, 0C035001Eh
0x1400ca99e  jnz     loc_1400CAB01
0x1400ca9a4  mov     [rsp+270h+var_218], 0
0x1400ca9ad  lea     r13, [r12+0E98h]
0x1400ca9b5  mov     rcx, r13
0x1400ca9b8  call    VidObjectLockAcquireExclusive
0x1400ca9bd  mov     rcx, [rbx+20h]
0x1400ca9c1  mov     rax, [r14+190h]
0x1400ca9c8  shr     rcx, 9
0x1400ca9cc  lea     rcx, [rax+rcx*8]
0x1400ca9d0  call    VidPushLockAcquireExclusive
0x1400ca9d5  test    dword ptr [r14+108h], 1000h
0x1400ca9e0  jz      loc_1400CAB89
0x1400ca9e6  mov     eax, cs:dword_140065110
0x1400ca9ec  mov     r8d, 2
0x1400ca9f2  mov     edi, 0C0000022h
0x1400ca9f7  cmp     eax, r8d
0x1400ca9fa  jbe     loc_1400CAC19
0x1400caa00  mov     edx, 100h
0x1400caa05  lea     rcx, dword_140065110
0x1400caa0c  call    _tlgKeywordOn
0x1400caa11  xor     r10d, r10d
0x1400caa14  test    al, al
0x1400caa16  jz      loc_1400CAC19
0x1400caa1c  lea     rdx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400caa23  lea     rcx, [rbp+170h+var_150]
0x1400caa27  call    _tlgCreate1Sz_char
0x1400caa2c  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400caa33  lea     rcx, [rbp+170h+var_140]
0x1400caa37  call    _tlgCreate1Sz_char
0x1400caa3c  mov     rdx, [r14+8]
0x1400caa40  lea     rax, [rsp+270h+var_22C]
0x1400caa45  mov     [rbp+170h+var_130], rax
0x1400caa49  lea     r9, [rbp+170h+var_E8]
0x1400caa50  mov     [rsp+270h+var_22C], 882h
0x1400caa58  lea     rax, [rsp+270h+var_230]
0x1400caa5d  mov     [rbp+170h+var_120], rax
0x1400caa61  lea     rax, [rdx+290h]
0x1400caa68  mov     [rbp+170h+var_128], 4
0x1400caa70  mov     [rbp+170h+var_110], rax
0x1400caa74  mov     [rsp+270h+var_230], edi
0x1400caa78  mov     [rbp+170h+var_118], 4
0x1400caa80  mov     [rbp+170h+var_108], 10h
0x1400caa88  movzx   ecx, word ptr [rdx+78h]
0x1400caa8c  mov     rax, [rdx+80h]
0x1400caa93  mov     [rbp+170h+var_F0], rax
0x1400caa9a  mov     dword ptr [rbp+170h+var_E8], ecx
0x1400caaa0  lea     rcx, dword_140065110
0x1400caaa7  mov     [rbp+170h+var_100], r9
0x1400caaab  xor     r9d, r9d
0x1400caaae  mov     [rbp+170h+var_F8], r8
0x1400caab2  xor     r8d, r8d
0x1400caab5  mov     dword ptr [rbp+170h+var_E8+4], r10d
0x1400caabc  mov     rax, [rdx+288h]
0x1400caac3  lea     rdx, byte_140053587
0x1400caaca  mov     [rsp+270h+var_220], rax
0x1400caacf  lea     rax, [rsp+270h+var_220]
0x1400caad4  mov     [rbp+170h+var_E0], rax
0x1400caadb  lea     rax, [rbp+170h+var_170]
0x1400caadf  mov     qword ptr [rsp+270h+Priority], rax
0x1400caae4  mov     [rsp+270h+BugCheckOnFailure], 0Ah
0x1400caaec  mov     [rbp+170h+var_D8], 8
0x1400caaf7  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400caafc  jmp     loc_1400CAC19
0x1400cab01  mov     r9d, eax
0x1400cab04  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cab0b  mov     r8d, 849h
0x1400cab11  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400cab18  call    VidTraceErrorStatusInternal0
0x1400cab1d  jmp     loc_1400CAE03
0x1400cab22  mov     rax, [rsp+270h+var_218]
0x1400cab27  test    rax, rax
0x1400cab2a  jz      loc_1400CA9AD
0x1400cab30  cmp     rax, r13
0x1400cab33  jz      loc_1400CA9AD
0x1400cab39  mov     rax, cs:VidDeviceExtension
0x1400cab40  sbb     edi, edi
0x1400cab42  and     edi, 0C9h
0x1400cab48  mov     r12d, 1
0x1400cab4e  add     edi, 0C00000BBh
0x1400cab54  mov     rcx, [rax+168h]
0x1400cab5b  lock add [rcx+110h], r12
0x1400cab63  mov     r9d, edi
0x1400cab66  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cab6d  mov     r8d, 86Ch
0x1400cab73  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400cab7a  call    VidTraceErrorStatusInternal0
0x1400cab7f  mov     r12, [rsp+270h+var_220]
0x1400cab84  jmp     loc_1400CADF0
0x1400cab89  mov     rdx, [rbx+20h]
0x1400cab8d  mov     r12d, 1
0x1400cab93  mov     r9d, r12d
0x1400cab96  mov     [rsp+270h+BugCheckOnFailure], 0
0x1400cab9e  mov     r8d, r12d
0x1400caba1  mov     rcx, r14
0x1400caba4  call    VsmmHostAccessAcquireMbpRange
0x1400caba9  mov     edi, eax
0x1400cabab  test    eax, eax
0x1400cabad  jns     short loc_1400CABCD
0x1400cabaf  mov     r9d, eax
0x1400cabb2  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cabb9  mov     r8d, 894h
0x1400cabbf  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400cabc6  call    VidTraceErrorStatusInternal0
0x1400cabcb  jmp     short loc_1400CAC14
0x1400cabcd  mov     r8, [rbx+10h]
0x1400cabd1  lea     rax, [rsp+270h+var_22C]
0x1400cabd6  mov     rdx, [rbx+20h]
0x1400cabda  lea     r9, [rsp+270h+var_230]
0x1400cabdf  mov     rcx, r14
0x1400cabe2  mov     qword ptr [rsp+270h+BugCheckOnFailure], rax
0x1400cabe7  call    VsmmMbpSwappingBegin
0x1400cabec  xor     esi, esi
0x1400cabee  mov     edi, eax
0x1400cabf0  test    eax, eax
0x1400cabf2  jns     short loc_1400CAC3E
0x1400cabf4  mov     r9d, eax
0x1400cabf7  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cabfe  mov     r8d, 8A5h
0x1400cac04  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400cac0b  call    VidTraceErrorStatusInternal0
0x1400cac10  mov     esi, [rsp+270h+var_230]
0x1400cac14  mov     r12, [rsp+270h+var_220]
0x1400cac19  mov     rdx, [rbx+20h]
0x1400cac1d  mov     rax, [r14+190h]
0x1400cac24  shr     rdx, 9
0x1400cac28  lea     rcx, [rax+rdx*8]
0x1400cac2c  call    VidPushLockRelease
0x1400cac31  mov     rcx, r13
0x1400cac34  call    VidObjectLockRelease
0x1400cac39  jmp     loc_1400CADEB
0x1400cac3e  mov     r8, [rbx+20h]
0x1400cac42  mov     r9, r12
0x1400cac45  mov     rcx, [rsp+270h+var_220]
0x1400cac4a  mov     rdx, r14
0x1400cac4d  mov     [rsp+270h+var_240], rsi
0x1400cac52  mov     [rsp+270h+Priority], 0FFFFFFFFh
0x1400cac5a  mov     [rsp+270h+BugCheckOnFailure], esi
0x1400cac5e  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x1400cac63  mov     rcx, [rbx+20h]
0x1400cac67  mov     rax, [r14+190h]
0x1400cac6e  shr     rcx, 9
0x1400cac72  lea     rcx, [rax+rcx*8]
0x1400cac76  call    VidPushLockRelease
0x1400cac7b  mov     rcx, r13
0x1400cac7e  call    VidObjectLockRelease
0x1400cac83  mov     rax, [rbx+30h]
0x1400cac87  xor     r9d, r9d; RequestedAddress
0x1400cac8a  mov     qword ptr [rbp+170h+MemoryDescriptorList+0Ch], rsi
0x1400cac8e  mov     r8d, r12d; CacheType
0x1400cac91  mov     [rbp+170h+MemoryDescriptorList.Process+4], rsi
0x1400cac95  xor     edx, edx; AccessMode
0x1400cac97  mov     dword ptr [rbp+170h+MemoryDescriptorList.MappedSystemVa+4], esi
0x1400cac9a  mov     [rbp+170h+MemoryDescriptorList.Next], rsi
0x1400cac9e  mov     dword ptr [rbp+170h+MemoryDescriptorList.Size], 20040h
0x1400caca5  mov     [rbp+170h+MemoryDescriptorList.StartVa], rsi
0x1400caca9  mov     qword ptr [rbp+170h+MemoryDescriptorList.ByteCount], 2000h
0x1400cacb1  mov     rcx, [rax+30h]
0x1400cacb5  mov     rax, [rbx+10h]
0x1400cacb9  mov     [rsp+270h+var_210], rcx
0x1400cacbe  mov     [rbp+170h+var_178], rcx
0x1400cacc2  lea     rcx, [rbp+170h+MemoryDescriptorList]; MemoryDescriptorList
0x1400cacc6  mov     [rsp+270h+Priority], 40000010h; Priority
0x1400cacce  mov     [rbp+170h+var_180], rax
0x1400cacd2  mov     [rsp+270h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400cacd6  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400cacdd  nop     dword ptr [rax+rax+00h]
0x1400cace2  mov     r13, rax
0x1400cace5  test    rax, rax
0x1400cace8  jnz     short loc_1400CAD0D
0x1400cacea  mov     edi, 0C0000017h
0x1400cacef  mov     r9d, edi
0x1400cacf2  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400cacf9  mov     r8d, 8DCh
0x1400cacff  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400cad06  call    VidTraceErrorStatusInternal0
0x1400cad0b  jmp     short loc_1400CAD28
0x1400cad0d  lea     rdi, [rax+1000h]
0x1400cad14  mov     rsi, r13
0x1400cad17  mov     ecx, 200h
0x1400cad1c  rep movsq
0x1400cad1f  xor     edi, edi
0x1400cad21  mov     dword ptr [rbx+38h], 7
0x1400cad28  mov     rcx, [rsp+270h+var_220]
0x1400cad2d  add     rcx, 0E98h
0x1400cad34  call    VidObjectLockAcquireExclusive
0x1400cad39  mov     rcx, [rbx+20h]
0x1400cad3d  mov     rax, [r14+190h]
0x1400cad44  shr     rcx, 9
0x1400cad48  lea     rcx, [rax+rcx*8]
0x1400cad4c  call    VidPushLockAcquireExclusive
0x1400cad51  mov     esi, [rsp+270h+var_230]
0x1400cad55  test    edi, edi
0x1400cad57  jns     short loc_1400CAD62
0x1400cad59  mov     r8, [rbx+10h]
0x1400cad5d  mov     r9d, esi
0x1400cad60  jmp     short loc_1400CAD6A
0x1400cad62  mov     r8, [rsp+270h+var_210]
0x1400cad67  xor     r9d, r9d
0x1400cad6a  mov     eax, [rsp+270h+var_22C]
0x1400cad6e  mov     rcx, r14
0x1400cad71  mov     rdx, [rbx+20h]
0x1400cad75  mov     [rsp+270h+BugCheckOnFailure], eax
0x1400cad79  call    VsmmMbpSwappingComplete
0x1400cad7e  mov     r8, [rbx+20h]
0x1400cad82  mov     r9, r12
0x1400cad85  mov     r12, [rsp+270h+var_220]
0x1400cad8a  mov     rdx, r14
0x1400cad8d  mov     [rsp+270h+var_240], 0
0x1400cad96  mov     rcx, r12
0x1400cad99  mov     [rsp+270h+Priority], 0FFFFFFFFh
0x1400cada1  mov     [rsp+270h+BugCheckOnFailure], 0
0x1400cada9  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x1400cadae  mov     rcx, [rbx+20h]
0x1400cadb2  mov     rax, [r14+190h]
0x1400cadb9  shr     rcx, 9
0x1400cadbd  lea     rcx, [rax+rcx*8]
0x1400cadc1  call    VidPushLockRelease
0x1400cadc6  lea     rcx, [r12+0E98h]
0x1400cadce  call    VidObjectLockRelease
0x1400cadd3  test    r13, r13
0x1400cadd6  jz      short loc_1400CADEB
0x1400cadd8  lea     rdx, [rbp+170h+MemoryDescriptorList]; MemoryDescriptorList
0x1400caddc  mov     rcx, r13; BaseAddress
0x1400caddf  call    cs:__imp_MmUnmapLockedPages
0x1400cade6  nop     dword ptr [rax+rax+00h]
0x1400cadeb  mov     r13d, [rsp+270h+var_228]
0x1400cadf0  test    edi, edi
0x1400cadf2  js      short loc_1400CAE03
0x1400cadf4  mov     rdx, [rbx+10h]
0x1400cadf8  mov     r8d, esi
0x1400cadfb  mov     rcx, r14
0x1400cadfe  call    VsmmWheapFreePage
0x1400cae03  lea     rcx, [rbp+170h+PerformanceFrequency]; PerformanceFrequency
0x1400cae07  call    cs:__imp_KeQueryPerformanceCounter
0x1400cae0e  nop     dword ptr [rax+rax+00h]
0x1400cae13  mov     qword ptr [rbp+170h+var_1C8+8], rax
0x1400cae17  mov     r8d, 4
0x1400cae1d  mov     eax, cs:dword_140065110
0x1400cae23  cmp     eax, r8d
0x1400cae26  jbe     loc_1400CB01F
0x1400cae2c  mov     edx, 100h
0x1400cae31  lea     rcx, dword_140065110
  ... truncated ...
```
