# VsmmPpmpCreate

- ea: `0x14010092c`
- end: `0x1401011ff`
- name: `VsmmPpmpCreate`
- size: `2259`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1400ded18`
- `0x140100438`

## callees

- `0x1400029c0`
- `0x140005a84`
- `0x140005bd0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x140021e00`
- `0x14002e270`
- `0x1400305c0`
- `0x140030960`
- `0x140030990`
- `0x1400309d0`
- `0x140033a60`
- `0x1400ef848`
- `0x1400f0210`
- `0x1400f1ea0`
- `0x14010092c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140100f26`
- `ntoskrnl!PsGetCurrentProcess` at `0x140100f26`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401011c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401011c1`
- `ntoskrnl!ExAllocatePool2` at `0x140100be4`
- `ntoskrnl!ExAllocatePool2` at `0x140100d95`
- `ntoskrnl!ExAllocatePool2` at `0x140100be4`
- `ntoskrnl!ExAllocatePool2` at `0x140100d95`

## string_xrefs

- `0x1401009dd`: `VsmmPpmpCreate`
- `0x140100af8`: `VsmmPpmpCreate`
- `0x140100c32`: `VsmmPpmpCreate`
- `0x140100de4`: `VsmmPpmpCreate`
- `0x140100f7d`: `VsmmPpmpCreate`
- `0x1401010a3`: `VsmmPpmpCreate`

## pseudocode

```c
__int64 __fastcall VsmmPpmpCreate(__int64 a1, __int64 a2, __int64 a3, __int16 a4, __int64 a5, _QWORD *a6, _QWORD *a7)
{
  __int64 v8; // r14
  int v10; // r9d
  __int64 v11; // rsi
  int v12; // ebx
  __int64 v13; // r9
  char v14; // r15
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 Pool2; // rax
  __int64 v19; // rcx
  __int64 v20; // rdi
  int v21; // r8d
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // rax
  void *v25; // r15
  __int64 v26; // r9
  char *v27; // rdx
  int v28; // r8d
  unsigned __int64 v29; // rcx
  __int64 v30; // r8
  int v31; // r9d
  int v32; // eax
  char v33; // bl
  void *CurrentProcess; // rax
  int Object; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v41; // [rsp+50h] [rbp-B0h]
  _QWORD *v42; // [rsp+58h] [rbp-A8h]
  _BYTE v43[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v45[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  __int64 *v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  int *v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+D8h] [rbp-28h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E8h] [rbp-18h] BYREF
  int v56; // [rsp+ECh] [rbp-14h]
  __int64 *v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  __int64 *v59; // [rsp+100h] [rbp+0h]
  __int64 v60; // [rsp+108h] [rbp+8h]

  v8 = *(_QWORD *)(a1 + 8);
  v41 = a6;
  v42 = a7;
  v39 = a3;
  v38 = a2;
  v37 = 0;
  v40 = a1 + 128;
  if ( !(unsigned __int8)VidOpCtrlStart(a1 + 128) )
  {
    v11 = (unsigned int)(v10 + 2);
    v12 = -1073741811;
    if ( dword_140065110 > (unsigned int)v11 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
      tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
      LODWORD(v38) = 544;
      v46 = &v38;
      v48 = &v37;
      v50 = v8 + 656;
      v47 = 4;
      v52 = &v55;
      v54 = *(_QWORD *)(v8 + 128);
      v55 = *(unsigned __int16 *)(v8 + 120);
      v39 = *(_QWORD *)(v8 + 648);
      v57 = &v39;
      LODWORD(v37) = -1073741811;
      v49 = 4;
      v51 = 16;
      v53 = v11;
      v56 = v13;
      v58 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_1400591D3, 0, v13, 10, v43);
    }
    return (unsigned int)v12;
  }
  v14 = v10;
  if ( a5 )
  {
    if ( !(unsigned __int8)VsmmGpaRangeReference(a5) )
    {
      v12 = -1070137310;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
        tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
        LODWORD(v37) = 558;
        v46 = &v37;
        v48 = &v38;
        v50 = v8 + 656;
        v47 = 4;
        v52 = &v55;
        v54 = *(_QWORD *)(v8 + 128);
        v55 = *(unsigned __int16 *)(v8 + 120);
        v39 = *(_QWORD *)(v8 + 648);
        v57 = &v39;
        LODWORD(v38) = -1070137310;
        v49 = 4;
        v51 = 16;
        v53 = 2;
        v56 = v17;
        v58 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_140059241, 0, v17, 10, v43);
      }
LABEL_17:
      VidOpCtrlFinish(v40, v15, v16);
      return (unsigned int)v12;
    }
    v14 = 1;
  }
  Pool2 = ExAllocatePool2(64, 144, 1833788502);
  v20 = Pool2;
  if ( !Pool2 )
  {
    v16 = 3221225626LL;
    v12 = -1073741670;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
      tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
      LODWORD(v38) = v21;
      v46 = &v37;
      v48 = &v38;
      v50 = v8 + 656;
      LODWORD(v37) = 591;
      v52 = &v55;
      v54 = *(_QWORD *)(v8 + 128);
      v55 = *(unsigned __int16 *)(v8 + 120);
      v39 = *(_QWORD *)(v8 + 648);
      v57 = &v39;
      v47 = 4;
      v49 = 4;
      v51 = 16;
      v53 = 2;
      v56 = v22;
      v58 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &byte_1400592AF, 0, v22, 10, v43);
    }
    if ( v14 )
      VsmmGpaRangeRelease(v19, a5, 0);
    goto LABEL_17;
  }
  *(_QWORD *)(Pool2 + 24) = v38;
  *(_QWORD *)(Pool2 + 32) = v39;
  *(_DWORD *)(Pool2 + 40) = ((a4 & 1) != 0 ? 3 : 0) | (2 * (a4 & 0xFFF0 | (2 * (a4 & 6))));
  memset((void *)(Pool2 + 64), 0, 0x48u);
  *(_QWORD *)(v20 + 112) = v20 + 104;
  *(_QWORD *)(v20 + 104) = v20 + 104;
  *(_QWORD *)(v20 + 16) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 228));
  _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v8 + 1528) + 824LL));
  v23 = *(_DWORD *)(v20 + 32);
  *(_QWORD *)(v20 + 48) = a5;
  v24 = ExAllocatePool2(64, (unsigned int)(8 * v23 + 48), 1833788502);
  v25 = (void *)v24;
  if ( !v24 )
  {
    v12 = -1073741670;
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_41;
    tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v37) = 641;
    v46 = &v37;
    v27 = &byte_140058FC7;
    LODWORD(v38) = v28;
    v50 = v8 + 656;
    v52 = &v55;
    v54 = *(_QWORD *)(v8 + 128);
    v55 = *(unsigned __int16 *)(v8 + 120);
    v40 = *(_QWORD *)(v8 + 648);
    v57 = &v40;
    v59 = &v39;
    Object = 11;
    v56 = v26;
    v60 = 8;
    goto LABEL_30;
  }
  v29 = *(_QWORD *)(v20 + 32);
  *(_QWORD *)(v24 + 12) = 0;
  *(_QWORD *)(v24 + 20) = 0;
  *(_DWORD *)(v24 + 28) = 0;
  *(_QWORD *)v24 = 0;
  v29 <<= 12;
  *(_QWORD *)(v24 + 32) = 0;
  *(_DWORD *)(v24 + 44) = 0;
  *(_WORD *)(v24 + 8) = 8 * ((v29 >> 12) + 6);
  *(_DWORD *)(v24 + 40) = v29;
  *(_WORD *)(v24 + 10) = 2;
  v30 = *(_QWORD *)(v20 + 32);
  v31 = *(_DWORD *)(v20 + 40);
  if ( a5 )
    v32 = VsmmLockGpaRange(a5, *(_DWORD *)(v20 + 24) + *(_DWORD *)(a5 + 256) - *(_DWORD *)(a5 + 392), v30, v31, v24);
  else
    v32 = VsmmLockMbpRange(*(_QWORD *)(v20 + 16), *(_QWORD *)(v20 + 24), v30, v31, v24);
  v12 = v32;
  if ( v32 < 0 )
  {
    ExFreePoolWithTag(v25, 0x6D4D6456u);
    goto LABEL_41;
  }
  v33 = ~(unsigned __int8)*(_DWORD *)(v20 + 40);
  *(_QWORD *)(v20 + 56) = v25;
  *(_QWORD *)(v20 + 120) = v25;
  CurrentProcess = (void *)PsGetCurrentProcess();
  v12 = VidClientBufferShare((int)v20 + 64, 0, (int)v20 + 64, v33 & 1, CurrentProcess, 0);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      goto LABEL_41;
    tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v37) = 693;
    v46 = &v37;
    v27 = &byte_14005903F;
    LODWORD(v38) = v12;
    v50 = v8 + 656;
    v26 = 0;
    v56 = 0;
    v52 = &v55;
    v54 = *(_QWORD *)(v8 + 128);
    v55 = *(unsigned __int16 *)(v8 + 120);
    v40 = *(_QWORD *)(v8 + 648);
    v57 = &v40;
    Object = 10;
LABEL_30:
    v47 = 4;
    v48 = &v38;
    v58 = 8;
    v53 = 2;
    v51 = 16;
    v49 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v27, 0, v26, Object, v43);
LABEL_41:
    VsmmPpmpDestroy((PVOID)v20);
    return (unsigned int)v12;
  }
  VidLockAcquireExclusive(*(_QWORD *)(v8 + 4256));
  v12 = VidHandleTableAllocateEntry(*(_QWORD *)(v8 + 4256) + 8LL, v20, &v37);
  if ( v12 >= 0 )
  {
    v12 = 0;
    *v41 = *(_QWORD *)(v20 + 96);
    *v42 = v37;
    if ( (*(_DWORD *)(v20 + 40) & 0x18) == 0 )
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v8 + 1528) + 832LL));
    v20 = 0;
  }
  else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v44, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v45, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v37) = 714;
    v46 = &v37;
    v48 = &v38;
    v50 = v8 + 656;
    v47 = 4;
    v52 = &v55;
    v54 = *(_QWORD *)(v8 + 128);
    v55 = *(unsigned __int16 *)(v8 + 120);
    v40 = *(_QWORD *)(v8 + 648);
    v57 = &v40;
    LODWORD(v38) = v12;
    v49 = 4;
    v51 = 16;
    v53 = 2;
    v56 = 0;
    v58 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_1400590AD, 0, 0, 10, v43);
  }
  VidLockRelease(*(_QWORD *)(v8 + 4256));
  if ( v20 )
    goto LABEL_41;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14010092c  mov     [rsp-8+arg_8], rbx
0x140100931  push    rbp
0x140100932  push    rsi
0x140100933  push    rdi
0x140100934  push    r12
0x140100936  push    r13
0x140100938  push    r14
0x14010093a  push    r15
0x14010093c  lea     rbp, [rsp-20h]
0x140100941  sub     rsp, 120h
0x140100948  mov     rax, cs:__security_cookie
0x14010094f  xor     rax, rsp
0x140100952  mov     [rbp+50h+var_40], rax
0x140100956  mov     rax, [rbp+50h+arg_28]
0x14010095d  mov     ebx, r9d
0x140100960  mov     r14, [rcx+8]
0x140100964  mov     rsi, rcx
0x140100967  mov     r13, [rbp+50h+arg_20]
0x14010096e  xor     r9d, r9d
0x140100971  mov     [rsp+150h+var_100], rax
0x140100976  mov     rax, [rbp+50h+arg_30]
0x14010097d  mov     [rsp+150h+var_F8], rax
0x140100982  lea     rax, [rcx+80h]
0x140100989  mov     rcx, rax
0x14010098c  mov     [rsp+150h+var_110], r8
0x140100991  mov     [rsp+150h+var_118], rdx
0x140100996  mov     [rsp+150h+var_120], r9
0x14010099b  mov     [rsp+150h+var_108], rax
0x1401009a0  call    VidOpCtrlStart
0x1401009a5  test    al, al
0x1401009a7  jnz     loc_140100AAB
0x1401009ad  mov     eax, cs:dword_140065110
0x1401009b3  lea     esi, [r9+2]
0x1401009b7  mov     ebx, 0C000000Dh
0x1401009bc  cmp     eax, esi
0x1401009be  jbe     loc_1401011D5
0x1401009c4  mov     edx, 100h
0x1401009c9  lea     rcx, dword_140065110
0x1401009d0  call    _tlgKeywordOn
0x1401009d5  test    al, al
0x1401009d7  jz      loc_1401011D5
0x1401009dd  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x1401009e4  lea     rcx, [rbp+50h+var_D0]
0x1401009e8  call    _tlgCreate1Sz_char
0x1401009ed  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x1401009f4  lea     rcx, [rbp+50h+var_C0]
0x1401009f8  call    _tlgCreate1Sz_char
0x1401009fd  lea     rax, [rsp+150h+var_118]
0x140100a02  mov     dword ptr [rsp+150h+var_118], 220h
0x140100a0a  mov     [rbp+50h+var_B0], rax
0x140100a0e  lea     rcx, [rsp+150h+var_120]
0x140100a13  lea     rax, [r14+290h]
0x140100a1a  mov     [rbp+50h+var_A0], rcx
0x140100a1e  mov     [rbp+50h+var_90], rax
0x140100a22  lea     rdx, byte_1400591D3
0x140100a29  lea     rax, [rbp+50h+var_68]
0x140100a2d  mov     [rbp+50h+var_A8], 4
0x140100a35  mov     [rbp+50h+var_80], rax
0x140100a39  lea     rcx, dword_140065110
0x140100a40  mov     rax, [r14+80h]
0x140100a47  xor     r8d, r8d
0x140100a4a  mov     [rbp+50h+var_70], rax
0x140100a4e  movzx   eax, word ptr [r14+78h]
0x140100a53  mov     [rbp+50h+var_68], eax
0x140100a56  mov     rax, [r14+288h]
0x140100a5d  mov     [rsp+150h+var_110], rax
0x140100a62  lea     rax, [rsp+150h+var_110]
0x140100a67  mov     [rbp+50h+var_60], rax
0x140100a6b  lea     rax, [rsp+150h+var_F0]
0x140100a70  mov     [rsp+150h+var_128], rax
0x140100a75  mov     dword ptr [rsp+150h+Object], 0Ah
0x140100a7d  mov     dword ptr [rsp+150h+var_120], ebx
0x140100a81  mov     [rbp+50h+var_98], 4
0x140100a89  mov     [rbp+50h+var_88], 10h
0x140100a91  mov     [rbp+50h+var_78], rsi
0x140100a95  mov     [rbp+50h+var_64], r9d
0x140100a99  mov     [rbp+50h+var_58], 8
0x140100aa1  call    _tlgWriteTransfer_EtwWriteTransfer
0x140100aa6  jmp     loc_1401011D5
0x140100aab  mov     r15b, r9b
0x140100aae  test    r13, r13
0x140100ab1  jz      loc_140100BC9
0x140100ab7  mov     rcx, r13
0x140100aba  call    VsmmGpaRangeReference
0x140100abf  test    al, al
0x140100ac1  jnz     loc_140100BC6
0x140100ac7  mov     eax, cs:dword_140065110
0x140100acd  mov     esi, 2
0x140100ad2  mov     ebx, 0C0370022h
0x140100ad7  cmp     eax, esi
0x140100ad9  jbe     loc_140100D0C
0x140100adf  mov     edx, 100h
0x140100ae4  lea     rcx, dword_140065110
0x140100aeb  call    _tlgKeywordOn
0x140100af0  test    al, al
0x140100af2  jz      loc_140100D0C
0x140100af8  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x140100aff  lea     rcx, [rbp+50h+var_D0]
0x140100b03  call    _tlgCreate1Sz_char
0x140100b08  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x140100b0f  lea     rcx, [rbp+50h+var_C0]
0x140100b13  call    _tlgCreate1Sz_char
0x140100b18  lea     rax, [rsp+150h+var_120]
0x140100b1d  mov     dword ptr [rsp+150h+var_120], 22Eh
0x140100b25  mov     [rbp+50h+var_B0], rax
0x140100b29  lea     rcx, [rsp+150h+var_118]
0x140100b2e  lea     rax, [r14+290h]
0x140100b35  mov     [rbp+50h+var_A0], rcx
0x140100b39  mov     [rbp+50h+var_90], rax
0x140100b3d  lea     rdx, byte_140059241
0x140100b44  lea     rax, [rbp+50h+var_68]
0x140100b48  mov     [rbp+50h+var_A8], 4
0x140100b50  mov     [rbp+50h+var_80], rax
0x140100b54  lea     rcx, dword_140065110
0x140100b5b  mov     rax, [r14+80h]
0x140100b62  xor     r8d, r8d
0x140100b65  mov     [rbp+50h+var_70], rax
0x140100b69  movzx   eax, word ptr [r14+78h]
0x140100b6e  mov     [rbp+50h+var_68], eax
0x140100b71  mov     rax, [r14+288h]
0x140100b78  mov     [rsp+150h+var_110], rax
0x140100b7d  lea     rax, [rsp+150h+var_110]
0x140100b82  mov     [rbp+50h+var_60], rax
0x140100b86  lea     rax, [rsp+150h+var_F0]
0x140100b8b  mov     [rsp+150h+var_128], rax
0x140100b90  mov     dword ptr [rsp+150h+Object], 0Ah
0x140100b98  mov     dword ptr [rsp+150h+var_118], ebx
0x140100b9c  mov     [rbp+50h+var_98], 4
0x140100ba4  mov     [rbp+50h+var_88], 10h
0x140100bac  mov     [rbp+50h+var_78], rsi
0x140100bb0  mov     [rbp+50h+var_64], r9d
0x140100bb4  mov     [rbp+50h+var_58], 8
0x140100bbc  call    _tlgWriteTransfer_EtwWriteTransfer
0x140100bc1  jmp     loc_140100D0C
0x140100bc6  mov     r15b, 1
0x140100bc9  mov     eax, ebx
0x140100bcb  mov     edx, 90h
0x140100bd0  and     al, 1
0x140100bd2  mov     r8d, 6D4D6456h
0x140100bd8  neg     al
0x140100bda  sbb     r12d, r12d
0x140100bdd  lea     ecx, [rdx-50h]
0x140100be0  and     r12d, 3
0x140100be4  call    cs:__imp_ExAllocatePool2
0x140100beb  nop     dword ptr [rax+rax+00h]
0x140100bf0  xor     r9d, r9d
0x140100bf3  mov     rdi, rax
0x140100bf6  test    rax, rax
0x140100bf9  jnz     loc_140100D1B
0x140100bff  mov     eax, cs:dword_140065110
0x140100c05  lea     esi, [rdi+2]
0x140100c08  mov     r8d, 0C000009Ah
0x140100c0e  mov     ebx, r8d
0x140100c11  cmp     eax, esi
0x140100c13  jbe     loc_140100CFC
0x140100c19  mov     edx, 100h
0x140100c1e  lea     rcx, dword_140065110
0x140100c25  call    _tlgKeywordOn
0x140100c2a  test    al, al
0x140100c2c  jz      loc_140100CFC
0x140100c32  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x140100c39  lea     rcx, [rbp+50h+var_D0]
0x140100c3d  call    _tlgCreate1Sz_char
0x140100c42  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x140100c49  lea     rcx, [rbp+50h+var_C0]
0x140100c4d  call    _tlgCreate1Sz_char
0x140100c52  lea     rax, [rsp+150h+var_120]
0x140100c57  mov     dword ptr [rsp+150h+var_118], r8d
0x140100c5c  mov     [rbp+50h+var_B0], rax
0x140100c60  lea     rcx, [rsp+150h+var_118]
0x140100c65  lea     rax, [r14+290h]
0x140100c6c  mov     [rbp+50h+var_A0], rcx
0x140100c70  mov     [rbp+50h+var_90], rax
0x140100c74  lea     rdx, byte_1400592AF
0x140100c7b  lea     rax, [rbp+50h+var_68]
0x140100c7f  mov     dword ptr [rsp+150h+var_120], 24Fh
0x140100c87  mov     [rbp+50h+var_80], rax
0x140100c8b  lea     rcx, dword_140065110
0x140100c92  mov     rax, [r14+80h]
0x140100c99  xor     r8d, r8d
0x140100c9c  mov     [rbp+50h+var_70], rax
0x140100ca0  movzx   eax, word ptr [r14+78h]
0x140100ca5  mov     [rbp+50h+var_68], eax
0x140100ca8  mov     rax, [r14+288h]
0x140100caf  mov     [rsp+150h+var_110], rax
0x140100cb4  lea     rax, [rsp+150h+var_110]
0x140100cb9  mov     [rbp+50h+var_60], rax
0x140100cbd  lea     rax, [rsp+150h+var_F0]
0x140100cc2  mov     [rsp+150h+var_128], rax
0x140100cc7  mov     dword ptr [rsp+150h+Object], 0Ah
0x140100ccf  mov     [rbp+50h+var_A8], 4
0x140100cd7  mov     [rbp+50h+var_98], 4
0x140100cdf  mov     [rbp+50h+var_88], 10h
0x140100ce7  mov     [rbp+50h+var_78], rsi
0x140100ceb  mov     [rbp+50h+var_64], r9d
0x140100cef  mov     [rbp+50h+var_58], 8
0x140100cf7  call    _tlgWriteTransfer_EtwWriteTransfer
0x140100cfc  test    r15b, r15b
0x140100cff  jz      short loc_140100D0C
0x140100d01  xor     r8d, r8d
0x140100d04  mov     rdx, r13
0x140100d07  call    VsmmGpaRangeRelease
0x140100d0c  mov     rcx, [rsp+150h+var_108]
0x140100d11  call    VidOpCtrlFinish
0x140100d16  jmp     loc_1401011D5
0x140100d1b  mov     rax, [rsp+150h+var_118]
0x140100d20  xor     edx, edx; Val
0x140100d22  mov     [rdi+18h], rax
0x140100d26  mov     rax, [rsp+150h+var_110]
0x140100d2b  mov     [rdi+20h], rax
0x140100d2f  mov     eax, ebx
0x140100d31  and     eax, 6
0x140100d34  lea     r8d, [rdx+48h]; Size
0x140100d38  add     eax, eax
0x140100d3a  and     ebx, 0FFF0h
0x140100d40  or      eax, ebx
0x140100d42  add     eax, eax
0x140100d44  or      eax, r12d
0x140100d47  lea     r12, [rdi+40h]
0x140100d4b  mov     rcx, r12; void *
0x140100d4e  mov     [rdi+28h], eax
0x140100d51  call    memset
0x140100d56  lea     rax, [r12+28h]
0x140100d5b  mov     [rax+8], rax
0x140100d5f  mov     [rax], rax
0x140100d62  mov     [rdi+10h], rsi
0x140100d66  lock inc dword ptr [rsi+0E4h]
0x140100d6d  mov     rax, [r14+5F8h]
0x140100d74  lock inc qword ptr [rax+338h]
0x140100d7c  mov     eax, [rdi+20h]
0x140100d7f  mov     ecx, 40h ; '@'
0x140100d84  mov     r8d, 6D4D6456h
0x140100d8a  mov     [rdi+30h], r13
0x140100d8e  lea     edx, ds:30h[rax*8]
0x140100d95  call    cs:__imp_ExAllocatePool2
0x140100d9c  nop     dword ptr [rax+rax+00h]
0x140100da1  xor     r9d, r9d
0x140100da4  mov     r15, rax
0x140100da7  lea     esi, [r9+2]
0x140100dab  test    rax, rax
0x140100dae  jnz     loc_140100E92
0x140100db4  mov     eax, cs:dword_140065110
0x140100dba  mov     r8d, 0C000009Ah
0x140100dc0  mov     ebx, r8d
0x140100dc3  cmp     eax, esi
0x140100dc5  jbe     loc_1401011CD
0x140100dcb  mov     edx, 100h
0x140100dd0  lea     rcx, dword_140065110
0x140100dd7  call    _tlgKeywordOn
0x140100ddc  test    al, al
0x140100dde  jz      loc_1401011CD
0x140100de4  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x140100deb  lea     rcx, [rbp+50h+var_D0]
0x140100def  call    _tlgCreate1Sz_char
0x140100df4  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x140100dfb  lea     rcx, [rbp+50h+var_C0]
0x140100dff  call    _tlgCreate1Sz_char
0x140100e04  lea     rax, [rsp+150h+var_120]
0x140100e09  mov     dword ptr [rsp+150h+var_120], 281h
0x140100e11  mov     [rbp+50h+var_B0], rax
0x140100e15  lea     rdx, byte_140058FC7
0x140100e1c  lea     rax, [r14+290h]
0x140100e23  mov     dword ptr [rsp+150h+var_118], r8d
0x140100e28  mov     [rbp+50h+var_90], rax
0x140100e2c  lea     rax, [rbp+50h+var_68]
0x140100e30  mov     [rbp+50h+var_80], rax
0x140100e34  mov     rax, [r14+80h]
0x140100e3b  mov     [rbp+50h+var_70], rax
0x140100e3f  movzx   eax, word ptr [r14+78h]
0x140100e44  mov     [rbp+50h+var_68], eax
0x140100e47  mov     rax, [r14+288h]
0x140100e4e  mov     [rsp+150h+var_108], rax
0x140100e53  lea     rax, [rsp+150h+var_108]
0x140100e58  mov     [rbp+50h+var_60], rax
0x140100e5c  mov     rax, [rsp+150h+var_110]
0x140100e61  mov     [rsp+150h+var_110], rax
0x140100e66  lea     rax, [rsp+150h+var_110]
0x140100e6b  mov     [rbp+50h+var_50], rax
0x140100e6f  lea     rax, [rsp+150h+var_F0]
0x140100e74  mov     [rsp+150h+var_128], rax
0x140100e79  mov     dword ptr [rsp+150h+Object], 0Bh
0x140100e81  mov     [rbp+50h+var_64], r9d
0x140100e85  mov     [rbp+50h+var_48], 8
0x140100e8d  jmp     loc_14010100D
0x140100e92  mov     rcx, [rdi+20h]
0x140100e96  mov     [rax+0Ch], r9
0x140100e9a  mov     [rax+14h], r9
0x140100e9e  mov     [rax+1Ch], r9d
0x140100ea2  mov     [rax], r9
0x140100ea5  shl     rcx, 0Ch
0x140100ea9  mov     [r15+20h], r9
0x140100ead  mov     rax, rcx
0x140100eb0  shr     rax, 0Ch
0x140100eb4  add     ax, 6
0x140100eb8  mov     [r15+2Ch], r9d
0x140100ebc  shl     ax, 3
0x140100ec0  mov     [r15+8], ax
0x140100ec5  mov     [r15+28h], ecx
0x140100ec9  mov     [r15+0Ah], si
0x140100ece  mov     r8, [rdi+20h]
  ... truncated ...
```
