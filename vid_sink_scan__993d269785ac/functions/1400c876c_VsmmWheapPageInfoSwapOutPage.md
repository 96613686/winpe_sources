# VsmmWheapPageInfoSwapOutPage

- ea: `0x1400c876c`
- end: `0x1400c8ef9`
- name: `VsmmWheapPageInfoSwapOutPage`
- size: `1933`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400c9f78`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007234`
- `0x1400087b8`
- `0x14000a4e0`
- `0x14001f220`
- `0x14001f3e0`
- `0x140021650`
- `0x140021800`
- `0x14002f524`
- `0x140034554`
- `0x140034914`
- `0x1400c63ec`
- `0x1400c6938`
- `0x1400c876c`
- `0x1400e7534`
- `0x1400fc8b0`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x1400c8c96`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400c8c96`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c8b8d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c8b8d`
- `HAL!KeQueryPerformanceCounter` at `0x1400c87d6`
- `HAL!KeQueryPerformanceCounter` at `0x1400c8cbe`
- `HAL!KeQueryPerformanceCounter` at `0x1400c87d6`
- `HAL!KeQueryPerformanceCounter` at `0x1400c8cbe`
- `winhvr!WinHvGetPartitionProperty` at `0x1400c883f`
- `winhvr!WinHvGetPartitionProperty` at `0x1400c883f`

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
  _QWORD *v10; // r15
  int v11; // edi
  int PartitionProperty; // eax
  __int64 v13; // r13
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int v17; // ecx
  unsigned int v18; // r10d
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  char *v26; // rax
  void *v27; // r13
  __int64 v28; // r8
  int v29; // r9d
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r8
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh] BYREF
  int v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-58h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE MemoryDescriptorList[64]; // [rsp+C0h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v53[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v54[16]; // [rsp+130h] [rbp+30h] BYREF
  int *v55; // [rsp+140h] [rbp+40h]
  __int64 v56; // [rsp+148h] [rbp+48h]
  int *v57; // [rsp+150h] [rbp+50h]
  __int64 v58; // [rsp+158h] [rbp+58h]
  __int64 v59; // [rsp+160h] [rbp+60h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  unsigned __int64 *v61; // [rsp+170h] [rbp+70h]
  __int64 v62; // [rsp+178h] [rbp+78h]
  __int64 *v63; // [rsp+180h] [rbp+80h]
  unsigned __int64 v64; // [rsp+188h] [rbp+88h] BYREF
  __int64 *v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+198h] [rbp+98h]
  __int64 *v67; // [rsp+1A0h] [rbp+A0h]
  __int64 v68; // [rsp+1A8h] [rbp+A8h]
  __int64 *v69; // [rsp+1B0h] [rbp+B0h]
  __int64 v70; // [rsp+1B8h] [rbp+B8h]
  __int64 *v71; // [rsp+1C0h] [rbp+C0h]
  __int64 v72; // [rsp+1C8h] [rbp+C8h]
  __int64 *v73; // [rsp+1D0h] [rbp+D0h]
  __int64 v74; // [rsp+1D8h] [rbp+D8h]
  int *v75; // [rsp+1E0h] [rbp+E0h]
  __int64 v76; // [rsp+1E8h] [rbp+E8h]
  int *v77; // [rsp+1F0h] [rbp+F0h]
  __int64 v78; // [rsp+1F8h] [rbp+F8h]
  __int64 *v79; // [rsp+200h] [rbp+100h]
  __int64 v80; // [rsp+208h] [rbp+108h]
  __int64 *v81; // [rsp+210h] [rbp+110h]
  __int64 v82; // [rsp+218h] [rbp+118h]

  v2 = a2;
  v37 = a2;
  memset(MemoryDescriptorList, 0, sizeof(MemoryDescriptorList));
  v39 = 0;
  PerformanceFrequency.QuadPart = 0;
  v4 = -1;
  v36 = 0;
  v35 = -1;
  v49 = 0;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  v6 = *(_QWORD *)(a1 + 24);
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 32);
  *(LARGE_INTEGER *)&v49 = PerformanceCounter;
  v38 = *(_QWORD *)(v6 + 8);
  v9 = v38;
  v10 = (_QWORD *)(v38 + 648);
  v11 = VsmmWheapBadPageRegister(v6, v8, v7);
  if ( v11 < 0 )
  {
    VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2095);
    goto LABEL_31;
  }
  PartitionProperty = WinHvGetPartitionProperty(*v10, 327701, &v39);
  v11 = PartitionProperty;
  if ( PartitionProperty >= 0 )
  {
    if ( v39 && v39 != v2 )
    {
      v11 = v39 < v2 ? -1073741436 : -1073741637;
      _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 272LL), 1u);
      VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2156);
      v9 = v38;
      goto LABEL_29;
    }
  }
  else
  {
    if ( PartitionProperty != -1070268386 )
    {
      VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2121);
      goto LABEL_31;
    }
    v39 = 0;
  }
  v13 = v38 + 3736;
  VidObjectLockAcquireExclusive(v38 + 3736);
  VidPushLockAcquireExclusive(*(_QWORD *)(v6 + 328) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
  if ( (*(_DWORD *)(v6 + 20) & 0x1000) != 0 )
  {
    v15 = 2;
    v11 = -1073741790;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v53, "VsmmWheapPageInfoSwapOutPage");
      tlgCreate1Sz_char(v54, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
      v16 = *(_QWORD *)(v6 + 8);
      v55 = &v36;
      v36 = 2178;
      v57 = &v35;
      v56 = 4;
      v59 = v16 + 656;
      v35 = -1073741790;
      v58 = 4;
      v60 = 16;
      v17 = *(unsigned __int16 *)(v16 + 120);
      v63 = *(__int64 **)(v16 + 128);
      v64 = __PAIR64__(v18, v17);
      v61 = &v64;
      v62 = v19;
      v38 = *(_QWORD *)(v16 + 648);
      v65 = &v38;
      v66 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)qword_140053180, 0, 0, 0xAu, v52);
    }
  }
  else
  {
    v11 = VsmmHostAccessAcquireMbpRange(v6, *(_QWORD *)(a1 + 32), 1, 0, 0);
    if ( v11 >= 0 )
    {
      v11 = VsmmMbpSwappingBegin(v6, *(_QWORD *)(a1 + 32), *(_QWORD *)(a1 + 16), (unsigned int)&v35, (__int64)&v36);
      if ( v11 >= 0 )
      {
        VsmmUpdateGpaSpaceForMbpRangeModification(v38, v6, *(_QWORD *)(a1 + 32), 1, 0, -1, 0);
        VidPushLockRelease(*(_QWORD *)(v6 + 328) + 8LL * (*(_QWORD *)(a1 + 32) >> 9), v20, v21, v22);
        VidObjectLockRelease(v13);
        v23 = *(_QWORD *)(a1 + 48);
        memset(&MemoryDescriptorList[12], 0, 28);
        *(_QWORD *)MemoryDescriptorList = 0;
        *(_DWORD *)&MemoryDescriptorList[8] = 131136;
        *(_QWORD *)&MemoryDescriptorList[40] = 0x2000;
        v24 = *(_QWORD *)(v23 + 48);
        v25 = *(_QWORD *)(a1 + 16);
        v40 = v24;
        *(_QWORD *)&MemoryDescriptorList[56] = v24;
        *(_QWORD *)&MemoryDescriptorList[48] = v25;
        v26 = (char *)MmMapLockedPagesSpecifyCache((PMDL)MemoryDescriptorList, 0, MmCached, 0, 0, 0x40000010u);
        v27 = v26;
        if ( v26 )
        {
          qmemcpy(v26 + 4096, v26, 0x1000u);
          v11 = 0;
          *(_DWORD *)(a1 + 56) = 7;
        }
        else
        {
          v11 = -1073741801;
          VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2268);
        }
        VidObjectLockAcquireExclusive(v38 + 3736);
        VidPushLockAcquireExclusive(*(_QWORD *)(v6 + 328) + 8LL * (*(_QWORD *)(a1 + 32) >> 9));
        v4 = v35;
        if ( v11 >= 0 )
        {
          LODWORD(v28) = v40;
          v29 = 0;
        }
        else
        {
          v28 = *(_QWORD *)(a1 + 16);
          v29 = v35;
        }
        VsmmMbpSwappingComplete(v6, *(_QWORD *)(a1 + 32), v28, v29, v36);
        v9 = v38;
        VsmmUpdateGpaSpaceForMbpRangeModification(v38, v6, *(_QWORD *)(a1 + 32), 1, 0, -1, 0);
        VidPushLockRelease(*(_QWORD *)(v6 + 328) + 8LL * (*(_QWORD *)(a1 + 32) >> 9), v30, v31, v32);
        VidObjectLockRelease(v9 + 3736);
        if ( v27 )
          MmUnmapLockedPages(v27, (PMDL)MemoryDescriptorList);
        goto LABEL_28;
      }
      VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2213);
      v4 = v35;
    }
    else
    {
      VidTraceErrorStatusInternal0("VsmmWheapPageInfoSwapOutPage", "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c", 2196);
    }
    v9 = v38;
  }
  VidPushLockRelease(*(_QWORD *)(v6 + 328) + 8LL * (*(_QWORD *)(a1 + 32) >> 9), *(_QWORD *)(a1 + 32) >> 9, v15, v14);
  VidObjectLockRelease(v13);
LABEL_28:
  LODWORD(v2) = v37;
LABEL_29:
  if ( v11 >= 0 )
    VsmmWheapFreePage(v6, *(_QWORD *)(a1 + 16), v4);
LABEL_31:
  *((LARGE_INTEGER *)&v49 + 1) = KeQueryPerformanceCounter(&PerformanceFrequency);
  if ( (unsigned int)dword_140064110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v53, "VsmmWheapPageInfoSwapOutPage");
    tlgCreate1Sz_char(v54, "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c");
    v56 = v33;
    v55 = &v36;
    v40 = *v10;
    v57 = (int *)&v40;
    v59 = v9 + 656;
    v41 = *(_QWORD *)(v6 + 24);
    v61 = (unsigned __int64 *)&v41;
    v42 = *(_QWORD *)(v6 + 40);
    v63 = &v42;
    v43 = *(_QWORD *)(v6 + 48);
    v65 = &v43;
    v44 = *(int *)(v6 + 20);
    v67 = &v44;
    v45 = *(_QWORD *)(a1 + 32);
    v69 = &v45;
    v46 = *(_QWORD *)(a1 + 16);
    v71 = &v46;
    v47 = v39;
    v73 = (__int64 *)&v47;
    v75 = &v37;
    v77 = &v35;
    v76 = v33;
    v78 = v33;
    v82 = v33;
    v48 = 1000000LL * (*((_QWORD *)&v49 + 1) - (_QWORD)v49) / PerformanceFrequency.QuadPart;
    v36 = 2370;
    v79 = &v48;
    LODWORD(v38) = *(_DWORD *)(a1 + 56);
    v81 = &v38;
    v58 = 8;
    v60 = 16;
    v62 = 8;
    v64 = 8;
    v66 = 8;
    v68 = 8;
    v70 = 8;
    v72 = 8;
    v74 = 8;
    v37 = v2;
    v35 = v11;
    v80 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140064110, (unsigned __int8 *)byte_14005309F, 0, 0, 0x12u, v52);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400c876c  push    rbp
0x1400c876e  push    rbx
0x1400c876f  push    rsi
0x1400c8770  push    rdi
0x1400c8771  push    r12
0x1400c8773  push    r13
0x1400c8775  push    r14
0x1400c8777  push    r15
0x1400c8779  lea     rbp, [rsp-138h]
0x1400c8781  sub     rsp, 238h
0x1400c8788  mov     rax, cs:__security_cookie
0x1400c878f  xor     rax, rsp
0x1400c8792  mov     [rbp+170h+var_50], rax
0x1400c8799  mov     r13d, edx
0x1400c879c  mov     rbx, rcx
0x1400c879f  xor     edx, edx; Val
0x1400c87a1  mov     [rsp+270h+var_228], r13d
0x1400c87a6  lea     rcx, [rbp+170h+MemoryDescriptorList]; void *
0x1400c87aa  lea     r8d, [rdx+40h]; Size
0x1400c87ae  call    memset
0x1400c87b3  xor     eax, eax
0x1400c87b5  mov     [rsp+270h+var_218], 0
0x1400c87be  xorps   xmm0, xmm0
0x1400c87c1  mov     qword ptr [rbp+170h+PerformanceFrequency], rax
0x1400c87c5  or      esi, 0FFFFFFFFh
0x1400c87c8  mov     [rsp+270h+var_22C], eax
0x1400c87cc  xor     ecx, ecx; PerformanceFrequency
0x1400c87ce  mov     [rsp+270h+var_230], esi
0x1400c87d2  movups  [rbp+170h+var_1C8], xmm0
0x1400c87d6  call    cs:__imp_KeQueryPerformanceCounter
0x1400c87dd  nop     dword ptr [rax+rax+00h]
0x1400c87e2  mov     r14, [rbx+18h]
0x1400c87e6  mov     r8, [rbx+10h]
0x1400c87ea  mov     rcx, r14
0x1400c87ed  mov     rdx, [rbx+20h]
0x1400c87f1  mov     qword ptr [rbp+170h+var_1C8], rax
0x1400c87f5  mov     r12, [r14+8]
0x1400c87f9  mov     [rsp+270h+var_220], r12
0x1400c87fe  call    VsmmWheapBadPageRegister
0x1400c8803  lea     r15, [r12+288h]
0x1400c880b  mov     edi, eax
0x1400c880d  test    eax, eax
0x1400c880f  jns     short loc_1400C8832
0x1400c8811  mov     r9d, eax
0x1400c8814  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c881b  mov     r8d, 82Fh
0x1400c8821  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c8828  call    VidTraceErrorStatusInternal0
0x1400c882d  jmp     loc_1400C8CBA
0x1400c8832  mov     rcx, [r15]
0x1400c8835  lea     r8, [rsp+270h+var_218]
0x1400c883a  mov     edx, 50015h
0x1400c883f  call    cs:__imp_WinHvGetPartitionProperty
0x1400c8846  nop     dword ptr [rax+rax+00h]
0x1400c884b  mov     edi, eax
0x1400c884d  test    eax, eax
0x1400c884f  jns     loc_1400C89DB
0x1400c8855  cmp     eax, 0C035001Eh
0x1400c885a  jnz     loc_1400C89BA
0x1400c8860  mov     [rsp+270h+var_218], 0
0x1400c8869  lea     r13, [r12+0E98h]
0x1400c8871  mov     rcx, r13
0x1400c8874  call    VidObjectLockAcquireExclusive
0x1400c8879  mov     rcx, [rbx+20h]
0x1400c887d  mov     rax, [r14+148h]
0x1400c8884  shr     rcx, 9
0x1400c8888  lea     rcx, [rax+rcx*8]
0x1400c888c  call    VidPushLockAcquireExclusive
0x1400c8891  test    dword ptr [r14+14h], 1000h
0x1400c8899  jz      loc_1400C8A42
0x1400c889f  mov     eax, cs:dword_140064110
0x1400c88a5  mov     r8d, 2
0x1400c88ab  mov     edi, 0C0000022h
0x1400c88b0  cmp     eax, r8d
0x1400c88b3  jbe     loc_1400C8AD0
0x1400c88b9  mov     edx, 100h
0x1400c88be  lea     rcx, dword_140064110
0x1400c88c5  call    _tlgKeywordOn
0x1400c88ca  xor     r10d, r10d
0x1400c88cd  test    al, al
0x1400c88cf  jz      loc_1400C8AD0
0x1400c88d5  lea     rdx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c88dc  lea     rcx, [rbp+170h+var_150]
0x1400c88e0  call    _tlgCreate1Sz_char
0x1400c88e5  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c88ec  lea     rcx, [rbp+170h+var_140]
0x1400c88f0  call    _tlgCreate1Sz_char
0x1400c88f5  mov     rdx, [r14+8]
0x1400c88f9  lea     rax, [rsp+270h+var_22C]
0x1400c88fe  mov     [rbp+170h+var_130], rax
0x1400c8902  lea     r9, [rbp+170h+var_E8]
0x1400c8909  mov     [rsp+270h+var_22C], 882h
0x1400c8911  lea     rax, [rsp+270h+var_230]
0x1400c8916  mov     [rbp+170h+var_120], rax
0x1400c891a  lea     rax, [rdx+290h]
0x1400c8921  mov     [rbp+170h+var_128], 4
0x1400c8929  mov     [rbp+170h+var_110], rax
0x1400c892d  mov     [rsp+270h+var_230], edi
0x1400c8931  mov     [rbp+170h+var_118], 4
0x1400c8939  mov     [rbp+170h+var_108], 10h
0x1400c8941  movzx   ecx, word ptr [rdx+78h]
0x1400c8945  mov     rax, [rdx+80h]
0x1400c894c  mov     [rbp+170h+var_F0], rax
0x1400c8953  mov     dword ptr [rbp+170h+var_E8], ecx
0x1400c8959  lea     rcx, dword_140064110
0x1400c8960  mov     [rbp+170h+var_100], r9
0x1400c8964  xor     r9d, r9d
0x1400c8967  mov     [rbp+170h+var_F8], r8
0x1400c896b  xor     r8d, r8d
0x1400c896e  mov     dword ptr [rbp+170h+var_E8+4], r10d
0x1400c8975  mov     rax, [rdx+288h]
0x1400c897c  lea     rdx, qword_140053180
0x1400c8983  mov     [rsp+270h+var_220], rax
0x1400c8988  lea     rax, [rsp+270h+var_220]
0x1400c898d  mov     [rbp+170h+var_E0], rax
0x1400c8994  lea     rax, [rbp+170h+var_170]
0x1400c8998  mov     qword ptr [rsp+270h+Priority], rax
0x1400c899d  mov     [rsp+270h+BugCheckOnFailure], 0Ah
0x1400c89a5  mov     [rbp+170h+var_D8], 8
0x1400c89b0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400c89b5  jmp     loc_1400C8AD0
0x1400c89ba  mov     r9d, eax
0x1400c89bd  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c89c4  mov     r8d, 849h
0x1400c89ca  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c89d1  call    VidTraceErrorStatusInternal0
0x1400c89d6  jmp     loc_1400C8CBA
0x1400c89db  mov     rax, [rsp+270h+var_218]
0x1400c89e0  test    rax, rax
0x1400c89e3  jz      loc_1400C8869
0x1400c89e9  cmp     rax, r13
0x1400c89ec  jz      loc_1400C8869
0x1400c89f2  mov     rax, cs:VidDeviceExtension
0x1400c89f9  sbb     edi, edi
0x1400c89fb  and     edi, 0C9h
0x1400c8a01  mov     r12d, 1
0x1400c8a07  add     edi, 0C00000BBh
0x1400c8a0d  mov     rcx, [rax+168h]
0x1400c8a14  lock add [rcx+110h], r12
0x1400c8a1c  mov     r9d, edi
0x1400c8a1f  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c8a26  mov     r8d, 86Ch
0x1400c8a2c  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c8a33  call    VidTraceErrorStatusInternal0
0x1400c8a38  mov     r12, [rsp+270h+var_220]
0x1400c8a3d  jmp     loc_1400C8CA7
0x1400c8a42  mov     rdx, [rbx+20h]
0x1400c8a46  xor     r9d, r9d
0x1400c8a49  mov     rcx, r14
0x1400c8a4c  mov     [rsp+270h+BugCheckOnFailure], 0
0x1400c8a54  lea     r12d, [r9+1]
0x1400c8a58  mov     r8d, r12d
0x1400c8a5b  call    VsmmHostAccessAcquireMbpRange
0x1400c8a60  mov     edi, eax
0x1400c8a62  test    eax, eax
0x1400c8a64  jns     short loc_1400C8A84
0x1400c8a66  mov     r9d, eax
0x1400c8a69  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c8a70  mov     r8d, 894h
0x1400c8a76  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c8a7d  call    VidTraceErrorStatusInternal0
0x1400c8a82  jmp     short loc_1400C8ACB
0x1400c8a84  mov     r8, [rbx+10h]
0x1400c8a88  lea     rax, [rsp+270h+var_22C]
0x1400c8a8d  mov     rdx, [rbx+20h]
0x1400c8a91  lea     r9, [rsp+270h+var_230]
0x1400c8a96  mov     rcx, r14
0x1400c8a99  mov     qword ptr [rsp+270h+BugCheckOnFailure], rax
0x1400c8a9e  call    VsmmMbpSwappingBegin
0x1400c8aa3  xor     esi, esi
0x1400c8aa5  mov     edi, eax
0x1400c8aa7  test    eax, eax
0x1400c8aa9  jns     short loc_1400C8AF5
0x1400c8aab  mov     r9d, eax
0x1400c8aae  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c8ab5  mov     r8d, 8A5h
0x1400c8abb  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c8ac2  call    VidTraceErrorStatusInternal0
0x1400c8ac7  mov     esi, [rsp+270h+var_230]
0x1400c8acb  mov     r12, [rsp+270h+var_220]
0x1400c8ad0  mov     rdx, [rbx+20h]
0x1400c8ad4  mov     rax, [r14+148h]
0x1400c8adb  shr     rdx, 9
0x1400c8adf  lea     rcx, [rax+rdx*8]
0x1400c8ae3  call    VidPushLockRelease
0x1400c8ae8  mov     rcx, r13
0x1400c8aeb  call    VidObjectLockRelease
0x1400c8af0  jmp     loc_1400C8CA2
0x1400c8af5  mov     r8, [rbx+20h]
0x1400c8af9  mov     r9, r12
0x1400c8afc  mov     rcx, [rsp+270h+var_220]
0x1400c8b01  mov     rdx, r14
0x1400c8b04  mov     [rsp+270h+var_240], rsi
0x1400c8b09  mov     [rsp+270h+Priority], 0FFFFFFFFh
0x1400c8b11  mov     [rsp+270h+BugCheckOnFailure], esi
0x1400c8b15  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x1400c8b1a  mov     rcx, [rbx+20h]
0x1400c8b1e  mov     rax, [r14+148h]
0x1400c8b25  shr     rcx, 9
0x1400c8b29  lea     rcx, [rax+rcx*8]
0x1400c8b2d  call    VidPushLockRelease
0x1400c8b32  mov     rcx, r13
0x1400c8b35  call    VidObjectLockRelease
0x1400c8b3a  mov     rax, [rbx+30h]
0x1400c8b3e  xor     r9d, r9d; RequestedAddress
0x1400c8b41  mov     qword ptr [rbp+170h+MemoryDescriptorList+0Ch], rsi
0x1400c8b45  mov     r8d, r12d; CacheType
0x1400c8b48  mov     [rbp+170h+MemoryDescriptorList.Process+4], rsi
0x1400c8b4c  xor     edx, edx; AccessMode
0x1400c8b4e  mov     dword ptr [rbp+170h+MemoryDescriptorList.MappedSystemVa+4], esi
0x1400c8b51  mov     [rbp+170h+MemoryDescriptorList.Next], rsi
0x1400c8b55  mov     dword ptr [rbp+170h+MemoryDescriptorList.Size], 20040h
0x1400c8b5c  mov     [rbp+170h+MemoryDescriptorList.StartVa], rsi
0x1400c8b60  mov     qword ptr [rbp+170h+MemoryDescriptorList.ByteCount], 2000h
0x1400c8b68  mov     rcx, [rax+30h]
0x1400c8b6c  mov     rax, [rbx+10h]
0x1400c8b70  mov     [rsp+270h+var_210], rcx
0x1400c8b75  mov     [rbp+170h+var_178], rcx
0x1400c8b79  lea     rcx, [rbp+170h+MemoryDescriptorList]; MemoryDescriptorList
0x1400c8b7d  mov     [rsp+270h+Priority], 40000010h; Priority
0x1400c8b85  mov     [rbp+170h+var_180], rax
0x1400c8b89  mov     [rsp+270h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400c8b8d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c8b94  nop     dword ptr [rax+rax+00h]
0x1400c8b99  mov     r13, rax
0x1400c8b9c  test    rax, rax
0x1400c8b9f  jnz     short loc_1400C8BC4
0x1400c8ba1  mov     edi, 0C0000017h
0x1400c8ba6  mov     r9d, edi
0x1400c8ba9  lea     rdx, aOnecoreVmVidSy_51; "onecore\\vm\\vid\\sys\\vsmm\\vsmmwhea.c"
0x1400c8bb0  mov     r8d, 8DCh
0x1400c8bb6  lea     rcx, aVsmmwheappagei_0; "VsmmWheapPageInfoSwapOutPage"
0x1400c8bbd  call    VidTraceErrorStatusInternal0
0x1400c8bc2  jmp     short loc_1400C8BDF
0x1400c8bc4  lea     rdi, [rax+1000h]
0x1400c8bcb  mov     rsi, r13
0x1400c8bce  mov     ecx, 200h
0x1400c8bd3  rep movsq
0x1400c8bd6  xor     edi, edi
0x1400c8bd8  mov     dword ptr [rbx+38h], 7
0x1400c8bdf  mov     rcx, [rsp+270h+var_220]
0x1400c8be4  add     rcx, 0E98h
0x1400c8beb  call    VidObjectLockAcquireExclusive
0x1400c8bf0  mov     rcx, [rbx+20h]
0x1400c8bf4  mov     rax, [r14+148h]
0x1400c8bfb  shr     rcx, 9
0x1400c8bff  lea     rcx, [rax+rcx*8]
0x1400c8c03  call    VidPushLockAcquireExclusive
0x1400c8c08  mov     esi, [rsp+270h+var_230]
0x1400c8c0c  test    edi, edi
0x1400c8c0e  jns     short loc_1400C8C19
0x1400c8c10  mov     r8, [rbx+10h]
0x1400c8c14  mov     r9d, esi
0x1400c8c17  jmp     short loc_1400C8C21
0x1400c8c19  mov     r8, [rsp+270h+var_210]
0x1400c8c1e  xor     r9d, r9d
0x1400c8c21  mov     eax, [rsp+270h+var_22C]
0x1400c8c25  mov     rcx, r14
0x1400c8c28  mov     rdx, [rbx+20h]
0x1400c8c2c  mov     [rsp+270h+BugCheckOnFailure], eax
0x1400c8c30  call    VsmmMbpSwappingComplete
0x1400c8c35  mov     r8, [rbx+20h]
0x1400c8c39  mov     r9, r12
0x1400c8c3c  mov     r12, [rsp+270h+var_220]
0x1400c8c41  mov     rdx, r14
0x1400c8c44  mov     [rsp+270h+var_240], 0
0x1400c8c4d  mov     rcx, r12
0x1400c8c50  mov     [rsp+270h+Priority], 0FFFFFFFFh
0x1400c8c58  mov     [rsp+270h+BugCheckOnFailure], 0
0x1400c8c60  call    VsmmUpdateGpaSpaceForMbpRangeModification
0x1400c8c65  mov     rcx, [rbx+20h]
0x1400c8c69  mov     rax, [r14+148h]
0x1400c8c70  shr     rcx, 9
0x1400c8c74  lea     rcx, [rax+rcx*8]
0x1400c8c78  call    VidPushLockRelease
0x1400c8c7d  lea     rcx, [r12+0E98h]
0x1400c8c85  call    VidObjectLockRelease
0x1400c8c8a  test    r13, r13
0x1400c8c8d  jz      short loc_1400C8CA2
0x1400c8c8f  lea     rdx, [rbp+170h+MemoryDescriptorList]; MemoryDescriptorList
0x1400c8c93  mov     rcx, r13; BaseAddress
0x1400c8c96  call    cs:__imp_MmUnmapLockedPages
0x1400c8c9d  nop     dword ptr [rax+rax+00h]
0x1400c8ca2  mov     r13d, [rsp+270h+var_228]
0x1400c8ca7  test    edi, edi
0x1400c8ca9  js      short loc_1400C8CBA
0x1400c8cab  mov     rdx, [rbx+10h]
0x1400c8caf  mov     r8d, esi
0x1400c8cb2  mov     rcx, r14
0x1400c8cb5  call    VsmmWheapFreePage
0x1400c8cba  lea     rcx, [rbp+170h+PerformanceFrequency]; PerformanceFrequency
0x1400c8cbe  call    cs:__imp_KeQueryPerformanceCounter
0x1400c8cc5  nop     dword ptr [rax+rax+00h]
0x1400c8cca  mov     qword ptr [rbp+170h+var_1C8+8], rax
0x1400c8cce  mov     r8d, 4
0x1400c8cd4  mov     eax, cs:dword_140064110
0x1400c8cda  cmp     eax, r8d
0x1400c8cdd  jbe     loc_1400C8ED3
0x1400c8ce3  mov     edx, 100h
0x1400c8ce8  lea     rcx, dword_140064110
  ... truncated ...
```
