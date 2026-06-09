# VsmmPpmpCreate

- ea: `0x1400fdab0`
- end: `0x1400fe383`
- name: `VsmmPpmpCreate`
- size: `2259`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int16, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `17`
- tags: ``

## callers

- `0x1400dc2bc`
- `0x1400fd5bc`

## callees

- `0x1400029c0`
- `0x140005b14`
- `0x140005c60`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021800`
- `0x14002e080`
- `0x1400303c0`
- `0x140030760`
- `0x140030790`
- `0x1400307d0`
- `0x140033860`
- `0x1400ecb68`
- `0x1400ed530`
- `0x1400ef710`
- `0x1400fdab0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400fe0aa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400fe0aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fe345`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400fe345`
- `ntoskrnl!ExAllocatePool2` at `0x1400fdd68`
- `ntoskrnl!ExAllocatePool2` at `0x1400fdf19`
- `ntoskrnl!ExAllocatePool2` at `0x1400fdd68`
- `ntoskrnl!ExAllocatePool2` at `0x1400fdf19`

## string_xrefs

- `0x1400fdb61`: `VsmmPpmpCreate`
- `0x1400fdc7c`: `VsmmPpmpCreate`
- `0x1400fddb6`: `VsmmPpmpCreate`
- `0x1400fdf68`: `VsmmPpmpCreate`
- `0x1400fe101`: `VsmmPpmpCreate`
- `0x1400fe227`: `VsmmPpmpCreate`

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
  __int64 v15; // r9
  __int64 Pool2; // rax
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // r8d
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // rax
  void *v23; // r15
  __int64 v24; // r9
  char *v25; // rdx
  int v26; // r8d
  unsigned __int64 v27; // rcx
  __int64 v28; // r8
  int v29; // r9d
  int v30; // eax
  char v31; // bl
  void *CurrentProcess; // rax
  int Object; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v39; // [rsp+50h] [rbp-B0h]
  _QWORD *v40; // [rsp+58h] [rbp-A8h]
  _BYTE v41[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v42[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v43[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  __int64 *v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h]
  int *v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  int v53; // [rsp+E8h] [rbp-18h] BYREF
  int v54; // [rsp+ECh] [rbp-14h]
  __int64 *v55; // [rsp+F0h] [rbp-10h]
  __int64 v56; // [rsp+F8h] [rbp-8h]
  __int64 *v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+108h] [rbp+8h]

  v8 = *(_QWORD *)(a1 + 8);
  v39 = a6;
  v40 = a7;
  v37 = a3;
  v36 = a2;
  v35 = 0;
  v38 = a1 + 128;
  if ( !VidOpCtrlStart((volatile signed __int32 *)(a1 + 128)) )
  {
    v11 = (unsigned int)(v10 + 2);
    v12 = -1073741811;
    if ( dword_140064110 > (unsigned int)v11 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
      LODWORD(v36) = 544;
      v44 = &v36;
      v46 = &v35;
      v48 = v8 + 656;
      v45 = 4;
      v50 = &v53;
      v52 = *(_QWORD *)(v8 + 128);
      v53 = *(unsigned __int16 *)(v8 + 120);
      v37 = *(_QWORD *)(v8 + 648);
      v55 = &v37;
      LODWORD(v35) = -1073741811;
      v47 = 4;
      v49 = 16;
      v51 = v11;
      v54 = v13;
      v56 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140058A79, 0, v13, 10, v41);
    }
    return (unsigned int)v12;
  }
  v14 = v10;
  if ( a5 )
  {
    if ( !(unsigned __int8)VsmmGpaRangeReference(a5) )
    {
      v12 = -1070137310;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
        tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
        LODWORD(v35) = 558;
        v44 = &v35;
        v46 = &v36;
        v48 = v8 + 656;
        v45 = 4;
        v50 = &v53;
        v52 = *(_QWORD *)(v8 + 128);
        v53 = *(unsigned __int16 *)(v8 + 120);
        v37 = *(_QWORD *)(v8 + 648);
        v55 = &v37;
        LODWORD(v36) = -1070137310;
        v47 = 4;
        v49 = 16;
        v51 = 2;
        v54 = v15;
        v56 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_140058AE7, 0, v15, 10, v41);
      }
LABEL_17:
      VidOpCtrlFinish(v38);
      return (unsigned int)v12;
    }
    v14 = 1;
  }
  Pool2 = ExAllocatePool2(64, 144, 1833788502);
  v18 = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
      tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
      LODWORD(v36) = v19;
      v44 = &v35;
      v46 = &v36;
      v48 = v8 + 656;
      LODWORD(v35) = 591;
      v50 = &v53;
      v52 = *(_QWORD *)(v8 + 128);
      v53 = *(unsigned __int16 *)(v8 + 120);
      v37 = *(_QWORD *)(v8 + 648);
      v55 = &v37;
      v45 = 4;
      v47 = 4;
      v49 = 16;
      v51 = 2;
      v54 = v20;
      v56 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140058B55, 0, v20, 10, v41);
    }
    if ( v14 )
      VsmmGpaRangeRelease(v17, a5, 0);
    goto LABEL_17;
  }
  *(_QWORD *)(Pool2 + 24) = v36;
  *(_QWORD *)(Pool2 + 32) = v37;
  *(_DWORD *)(Pool2 + 40) = ((a4 & 1) != 0 ? 3 : 0) | (2 * (a4 & 0xFFF0 | (2 * (a4 & 6))));
  memset((void *)(Pool2 + 64), 0, 0x48u);
  *(_QWORD *)(v18 + 112) = v18 + 104;
  *(_QWORD *)(v18 + 104) = v18 + 104;
  *(_QWORD *)(v18 + 16) = a1;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 228));
  _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v8 + 1528) + 824LL));
  v21 = *(_DWORD *)(v18 + 32);
  *(_QWORD *)(v18 + 48) = a5;
  v22 = ExAllocatePool2(64, (unsigned int)(8 * v21 + 48), 1833788502);
  v23 = (void *)v22;
  if ( !v22 )
  {
    v12 = -1073741670;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_41;
    tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v35) = 641;
    v44 = &v35;
    v25 = byte_140058925;
    LODWORD(v36) = v26;
    v48 = v8 + 656;
    v50 = &v53;
    v52 = *(_QWORD *)(v8 + 128);
    v53 = *(unsigned __int16 *)(v8 + 120);
    v38 = *(_QWORD *)(v8 + 648);
    v55 = &v38;
    v57 = &v37;
    Object = 11;
    v54 = v24;
    v58 = 8;
    goto LABEL_30;
  }
  v27 = *(_QWORD *)(v18 + 32);
  *(_QWORD *)(v22 + 12) = 0;
  *(_QWORD *)(v22 + 20) = 0;
  *(_DWORD *)(v22 + 28) = 0;
  *(_QWORD *)v22 = 0;
  v27 <<= 12;
  *(_QWORD *)(v22 + 32) = 0;
  *(_DWORD *)(v22 + 44) = 0;
  *(_WORD *)(v22 + 8) = 8 * ((v27 >> 12) + 6);
  *(_DWORD *)(v22 + 40) = v27;
  *(_WORD *)(v22 + 10) = 2;
  v28 = *(_QWORD *)(v18 + 32);
  v29 = *(_DWORD *)(v18 + 40);
  if ( a5 )
    v30 = VsmmLockGpaRange(a5, *(_DWORD *)(v18 + 24) + *(_DWORD *)(a5 + 256) - *(_DWORD *)(a5 + 392), v28, v29, v22);
  else
    v30 = VsmmLockMbpRange(*(_QWORD *)(v18 + 16), *(_QWORD *)(v18 + 24), v28, v29, v22);
  v12 = v30;
  if ( v30 < 0 )
  {
    ExFreePoolWithTag(v23, 0x6D4D6456u);
    goto LABEL_41;
  }
  v31 = ~(unsigned __int8)*(_DWORD *)(v18 + 40);
  *(_QWORD *)(v18 + 56) = v23;
  *(_QWORD *)(v18 + 120) = v23;
  CurrentProcess = (void *)PsGetCurrentProcess();
  v12 = VidClientBufferShare(v18 + 64, 0, (_QWORD *)(v18 + 64), v31 & 1, CurrentProcess, 0);
  if ( v12 < 0 )
  {
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_41;
    tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v35) = 693;
    v44 = &v35;
    v25 = byte_14005899D;
    LODWORD(v36) = v12;
    v48 = v8 + 656;
    v24 = 0;
    v54 = 0;
    v50 = &v53;
    v52 = *(_QWORD *)(v8 + 128);
    v53 = *(unsigned __int16 *)(v8 + 120);
    v38 = *(_QWORD *)(v8 + 648);
    v55 = &v38;
    Object = 10;
LABEL_30:
    v45 = 4;
    v46 = &v36;
    v56 = 8;
    v51 = 2;
    v49 = 16;
    v47 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v25, 0, v24, Object, v41);
LABEL_41:
    VsmmPpmpDestroy((PVOID)v18);
    return (unsigned int)v12;
  }
  VidLockAcquireExclusive(*(_QWORD *)(v8 + 4256));
  v12 = VidHandleTableAllocateEntry(*(_QWORD *)(v8 + 4256) + 8LL, v18, &v35);
  if ( v12 >= 0 )
  {
    v12 = 0;
    *v39 = *(_QWORD *)(v18 + 96);
    *v40 = v35;
    if ( (*(_DWORD *)(v18 + 40) & 0x18) == 0 )
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v8 + 1528) + 832LL));
    v18 = 0;
  }
  else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v42, "VsmmPpmpCreate");
    tlgCreate1Sz_char(v43, "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c");
    LODWORD(v35) = 714;
    v44 = &v35;
    v46 = &v36;
    v48 = v8 + 656;
    v45 = 4;
    v50 = &v53;
    v52 = *(_QWORD *)(v8 + 128);
    v53 = *(unsigned __int16 *)(v8 + 120);
    v38 = *(_QWORD *)(v8 + 648);
    v55 = &v38;
    LODWORD(v36) = v12;
    v47 = 4;
    v49 = 16;
    v51 = 2;
    v54 = 0;
    v56 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140058A0B, 0, 0, 10, v41);
  }
  VidLockRelease(*(_QWORD *)(v8 + 4256));
  if ( v18 )
    goto LABEL_41;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400fdab0  mov     [rsp-8+arg_8], rbx
0x1400fdab5  push    rbp
0x1400fdab6  push    rsi
0x1400fdab7  push    rdi
0x1400fdab8  push    r12
0x1400fdaba  push    r13
0x1400fdabc  push    r14
0x1400fdabe  push    r15
0x1400fdac0  lea     rbp, [rsp-20h]
0x1400fdac5  sub     rsp, 120h
0x1400fdacc  mov     rax, cs:__security_cookie
0x1400fdad3  xor     rax, rsp
0x1400fdad6  mov     [rbp+50h+var_40], rax
0x1400fdada  mov     rax, [rbp+50h+arg_28]
0x1400fdae1  mov     ebx, r9d
0x1400fdae4  mov     r14, [rcx+8]
0x1400fdae8  mov     rsi, rcx
0x1400fdaeb  mov     r13, [rbp+50h+arg_20]
0x1400fdaf2  xor     r9d, r9d
0x1400fdaf5  mov     [rsp+150h+var_100], rax
0x1400fdafa  mov     rax, [rbp+50h+arg_30]
0x1400fdb01  mov     [rsp+150h+var_F8], rax
0x1400fdb06  lea     rax, [rcx+80h]
0x1400fdb0d  mov     rcx, rax
0x1400fdb10  mov     [rsp+150h+var_110], r8
0x1400fdb15  mov     [rsp+150h+var_118], rdx
0x1400fdb1a  mov     [rsp+150h+var_120], r9
0x1400fdb1f  mov     [rsp+150h+var_108], rax
0x1400fdb24  call    VidOpCtrlStart
0x1400fdb29  test    al, al
0x1400fdb2b  jnz     loc_1400FDC2F
0x1400fdb31  mov     eax, cs:dword_140064110
0x1400fdb37  lea     esi, [r9+2]
0x1400fdb3b  mov     ebx, 0C000000Dh
0x1400fdb40  cmp     eax, esi
0x1400fdb42  jbe     loc_1400FE359
0x1400fdb48  mov     edx, 100h
0x1400fdb4d  lea     rcx, dword_140064110
0x1400fdb54  call    _tlgKeywordOn
0x1400fdb59  test    al, al
0x1400fdb5b  jz      loc_1400FE359
0x1400fdb61  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x1400fdb68  lea     rcx, [rbp+50h+var_D0]
0x1400fdb6c  call    _tlgCreate1Sz_char
0x1400fdb71  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x1400fdb78  lea     rcx, [rbp+50h+var_C0]
0x1400fdb7c  call    _tlgCreate1Sz_char
0x1400fdb81  lea     rax, [rsp+150h+var_118]
0x1400fdb86  mov     dword ptr [rsp+150h+var_118], 220h
0x1400fdb8e  mov     [rbp+50h+var_B0], rax
0x1400fdb92  lea     rcx, [rsp+150h+var_120]
0x1400fdb97  lea     rax, [r14+290h]
0x1400fdb9e  mov     [rbp+50h+var_A0], rcx
0x1400fdba2  mov     [rbp+50h+var_90], rax
0x1400fdba6  lea     rdx, byte_140058A79
0x1400fdbad  lea     rax, [rbp+50h+var_68]
0x1400fdbb1  mov     [rbp+50h+var_A8], 4
0x1400fdbb9  mov     [rbp+50h+var_80], rax
0x1400fdbbd  lea     rcx, dword_140064110
0x1400fdbc4  mov     rax, [r14+80h]
0x1400fdbcb  xor     r8d, r8d
0x1400fdbce  mov     [rbp+50h+var_70], rax
0x1400fdbd2  movzx   eax, word ptr [r14+78h]
0x1400fdbd7  mov     [rbp+50h+var_68], eax
0x1400fdbda  mov     rax, [r14+288h]
0x1400fdbe1  mov     [rsp+150h+var_110], rax
0x1400fdbe6  lea     rax, [rsp+150h+var_110]
0x1400fdbeb  mov     [rbp+50h+var_60], rax
0x1400fdbef  lea     rax, [rsp+150h+var_F0]
0x1400fdbf4  mov     [rsp+150h+var_128], rax
0x1400fdbf9  mov     dword ptr [rsp+150h+Object], 0Ah
0x1400fdc01  mov     dword ptr [rsp+150h+var_120], ebx
0x1400fdc05  mov     [rbp+50h+var_98], 4
0x1400fdc0d  mov     [rbp+50h+var_88], 10h
0x1400fdc15  mov     [rbp+50h+var_78], rsi
0x1400fdc19  mov     [rbp+50h+var_64], r9d
0x1400fdc1d  mov     [rbp+50h+var_58], 8
0x1400fdc25  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400fdc2a  jmp     loc_1400FE359
0x1400fdc2f  mov     r15b, r9b
0x1400fdc32  test    r13, r13
0x1400fdc35  jz      loc_1400FDD4D
0x1400fdc3b  mov     rcx, r13
0x1400fdc3e  call    VsmmGpaRangeReference
0x1400fdc43  test    al, al
0x1400fdc45  jnz     loc_1400FDD4A
0x1400fdc4b  mov     eax, cs:dword_140064110
0x1400fdc51  mov     esi, 2
0x1400fdc56  mov     ebx, 0C0370022h
0x1400fdc5b  cmp     eax, esi
0x1400fdc5d  jbe     loc_1400FDE90
0x1400fdc63  mov     edx, 100h
0x1400fdc68  lea     rcx, dword_140064110
0x1400fdc6f  call    _tlgKeywordOn
0x1400fdc74  test    al, al
0x1400fdc76  jz      loc_1400FDE90
0x1400fdc7c  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x1400fdc83  lea     rcx, [rbp+50h+var_D0]
0x1400fdc87  call    _tlgCreate1Sz_char
0x1400fdc8c  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x1400fdc93  lea     rcx, [rbp+50h+var_C0]
0x1400fdc97  call    _tlgCreate1Sz_char
0x1400fdc9c  lea     rax, [rsp+150h+var_120]
0x1400fdca1  mov     dword ptr [rsp+150h+var_120], 22Eh
0x1400fdca9  mov     [rbp+50h+var_B0], rax
0x1400fdcad  lea     rcx, [rsp+150h+var_118]
0x1400fdcb2  lea     rax, [r14+290h]
0x1400fdcb9  mov     [rbp+50h+var_A0], rcx
0x1400fdcbd  mov     [rbp+50h+var_90], rax
0x1400fdcc1  lea     rdx, byte_140058AE7
0x1400fdcc8  lea     rax, [rbp+50h+var_68]
0x1400fdccc  mov     [rbp+50h+var_A8], 4
0x1400fdcd4  mov     [rbp+50h+var_80], rax
0x1400fdcd8  lea     rcx, dword_140064110
0x1400fdcdf  mov     rax, [r14+80h]
0x1400fdce6  xor     r8d, r8d
0x1400fdce9  mov     [rbp+50h+var_70], rax
0x1400fdced  movzx   eax, word ptr [r14+78h]
0x1400fdcf2  mov     [rbp+50h+var_68], eax
0x1400fdcf5  mov     rax, [r14+288h]
0x1400fdcfc  mov     [rsp+150h+var_110], rax
0x1400fdd01  lea     rax, [rsp+150h+var_110]
0x1400fdd06  mov     [rbp+50h+var_60], rax
0x1400fdd0a  lea     rax, [rsp+150h+var_F0]
0x1400fdd0f  mov     [rsp+150h+var_128], rax
0x1400fdd14  mov     dword ptr [rsp+150h+Object], 0Ah
0x1400fdd1c  mov     dword ptr [rsp+150h+var_118], ebx
0x1400fdd20  mov     [rbp+50h+var_98], 4
0x1400fdd28  mov     [rbp+50h+var_88], 10h
0x1400fdd30  mov     [rbp+50h+var_78], rsi
0x1400fdd34  mov     [rbp+50h+var_64], r9d
0x1400fdd38  mov     [rbp+50h+var_58], 8
0x1400fdd40  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400fdd45  jmp     loc_1400FDE90
0x1400fdd4a  mov     r15b, 1
0x1400fdd4d  mov     eax, ebx
0x1400fdd4f  mov     edx, 90h
0x1400fdd54  and     al, 1
0x1400fdd56  mov     r8d, 6D4D6456h
0x1400fdd5c  neg     al
0x1400fdd5e  sbb     r12d, r12d
0x1400fdd61  lea     ecx, [rdx-50h]
0x1400fdd64  and     r12d, 3
0x1400fdd68  call    cs:__imp_ExAllocatePool2
0x1400fdd6f  nop     dword ptr [rax+rax+00h]
0x1400fdd74  xor     r9d, r9d
0x1400fdd77  mov     rdi, rax
0x1400fdd7a  test    rax, rax
0x1400fdd7d  jnz     loc_1400FDE9F
0x1400fdd83  mov     eax, cs:dword_140064110
0x1400fdd89  lea     esi, [rdi+2]
0x1400fdd8c  mov     r8d, 0C000009Ah
0x1400fdd92  mov     ebx, r8d
0x1400fdd95  cmp     eax, esi
0x1400fdd97  jbe     loc_1400FDE80
0x1400fdd9d  mov     edx, 100h
0x1400fdda2  lea     rcx, dword_140064110
0x1400fdda9  call    _tlgKeywordOn
0x1400fddae  test    al, al
0x1400fddb0  jz      loc_1400FDE80
0x1400fddb6  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x1400fddbd  lea     rcx, [rbp+50h+var_D0]
0x1400fddc1  call    _tlgCreate1Sz_char
0x1400fddc6  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x1400fddcd  lea     rcx, [rbp+50h+var_C0]
0x1400fddd1  call    _tlgCreate1Sz_char
0x1400fddd6  lea     rax, [rsp+150h+var_120]
0x1400fdddb  mov     dword ptr [rsp+150h+var_118], r8d
0x1400fdde0  mov     [rbp+50h+var_B0], rax
0x1400fdde4  lea     rcx, [rsp+150h+var_118]
0x1400fdde9  lea     rax, [r14+290h]
0x1400fddf0  mov     [rbp+50h+var_A0], rcx
0x1400fddf4  mov     [rbp+50h+var_90], rax
0x1400fddf8  lea     rdx, byte_140058B55
0x1400fddff  lea     rax, [rbp+50h+var_68]
0x1400fde03  mov     dword ptr [rsp+150h+var_120], 24Fh
0x1400fde0b  mov     [rbp+50h+var_80], rax
0x1400fde0f  lea     rcx, dword_140064110
0x1400fde16  mov     rax, [r14+80h]
0x1400fde1d  xor     r8d, r8d
0x1400fde20  mov     [rbp+50h+var_70], rax
0x1400fde24  movzx   eax, word ptr [r14+78h]
0x1400fde29  mov     [rbp+50h+var_68], eax
0x1400fde2c  mov     rax, [r14+288h]
0x1400fde33  mov     [rsp+150h+var_110], rax
0x1400fde38  lea     rax, [rsp+150h+var_110]
0x1400fde3d  mov     [rbp+50h+var_60], rax
0x1400fde41  lea     rax, [rsp+150h+var_F0]
0x1400fde46  mov     [rsp+150h+var_128], rax
0x1400fde4b  mov     dword ptr [rsp+150h+Object], 0Ah
0x1400fde53  mov     [rbp+50h+var_A8], 4
0x1400fde5b  mov     [rbp+50h+var_98], 4
0x1400fde63  mov     [rbp+50h+var_88], 10h
0x1400fde6b  mov     [rbp+50h+var_78], rsi
0x1400fde6f  mov     [rbp+50h+var_64], r9d
0x1400fde73  mov     [rbp+50h+var_58], 8
0x1400fde7b  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400fde80  test    r15b, r15b
0x1400fde83  jz      short loc_1400FDE90
0x1400fde85  xor     r8d, r8d
0x1400fde88  mov     rdx, r13
0x1400fde8b  call    VsmmGpaRangeRelease
0x1400fde90  mov     rcx, [rsp+150h+var_108]
0x1400fde95  call    VidOpCtrlFinish
0x1400fde9a  jmp     loc_1400FE359
0x1400fde9f  mov     rax, [rsp+150h+var_118]
0x1400fdea4  xor     edx, edx; Val
0x1400fdea6  mov     [rdi+18h], rax
0x1400fdeaa  mov     rax, [rsp+150h+var_110]
0x1400fdeaf  mov     [rdi+20h], rax
0x1400fdeb3  mov     eax, ebx
0x1400fdeb5  and     eax, 6
0x1400fdeb8  lea     r8d, [rdx+48h]; Size
0x1400fdebc  add     eax, eax
0x1400fdebe  and     ebx, 0FFF0h
0x1400fdec4  or      eax, ebx
0x1400fdec6  add     eax, eax
0x1400fdec8  or      eax, r12d
0x1400fdecb  lea     r12, [rdi+40h]
0x1400fdecf  mov     rcx, r12; void *
0x1400fded2  mov     [rdi+28h], eax
0x1400fded5  call    memset
0x1400fdeda  lea     rax, [r12+28h]
0x1400fdedf  mov     [rax+8], rax
0x1400fdee3  mov     [rax], rax
0x1400fdee6  mov     [rdi+10h], rsi
0x1400fdeea  lock inc dword ptr [rsi+0E4h]
0x1400fdef1  mov     rax, [r14+5F8h]
0x1400fdef8  lock inc qword ptr [rax+338h]
0x1400fdf00  mov     eax, [rdi+20h]
0x1400fdf03  mov     ecx, 40h ; '@'
0x1400fdf08  mov     r8d, 6D4D6456h
0x1400fdf0e  mov     [rdi+30h], r13
0x1400fdf12  lea     edx, ds:30h[rax*8]
0x1400fdf19  call    cs:__imp_ExAllocatePool2
0x1400fdf20  nop     dword ptr [rax+rax+00h]
0x1400fdf25  xor     r9d, r9d
0x1400fdf28  mov     r15, rax
0x1400fdf2b  lea     esi, [r9+2]
0x1400fdf2f  test    rax, rax
0x1400fdf32  jnz     loc_1400FE016
0x1400fdf38  mov     eax, cs:dword_140064110
0x1400fdf3e  mov     r8d, 0C000009Ah
0x1400fdf44  mov     ebx, r8d
0x1400fdf47  cmp     eax, esi
0x1400fdf49  jbe     loc_1400FE351
0x1400fdf4f  mov     edx, 100h
0x1400fdf54  lea     rcx, dword_140064110
0x1400fdf5b  call    _tlgKeywordOn
0x1400fdf60  test    al, al
0x1400fdf62  jz      loc_1400FE351
0x1400fdf68  lea     rdx, aVsmmppmpcreate; "VsmmPpmpCreate"
0x1400fdf6f  lea     rcx, [rbp+50h+var_D0]
0x1400fdf73  call    _tlgCreate1Sz_char
0x1400fdf78  lea     rdx, aOnecoreVmVidSy_48; "onecore\\vm\\vid\\sys\\vsmm\\vsmmppm.c"
0x1400fdf7f  lea     rcx, [rbp+50h+var_C0]
0x1400fdf83  call    _tlgCreate1Sz_char
0x1400fdf88  lea     rax, [rsp+150h+var_120]
0x1400fdf8d  mov     dword ptr [rsp+150h+var_120], 281h
0x1400fdf95  mov     [rbp+50h+var_B0], rax
0x1400fdf99  lea     rdx, byte_140058925
0x1400fdfa0  lea     rax, [r14+290h]
0x1400fdfa7  mov     dword ptr [rsp+150h+var_118], r8d
0x1400fdfac  mov     [rbp+50h+var_90], rax
0x1400fdfb0  lea     rax, [rbp+50h+var_68]
0x1400fdfb4  mov     [rbp+50h+var_80], rax
0x1400fdfb8  mov     rax, [r14+80h]
0x1400fdfbf  mov     [rbp+50h+var_70], rax
0x1400fdfc3  movzx   eax, word ptr [r14+78h]
0x1400fdfc8  mov     [rbp+50h+var_68], eax
0x1400fdfcb  mov     rax, [r14+288h]
0x1400fdfd2  mov     [rsp+150h+var_108], rax
0x1400fdfd7  lea     rax, [rsp+150h+var_108]
0x1400fdfdc  mov     [rbp+50h+var_60], rax
0x1400fdfe0  mov     rax, [rsp+150h+var_110]
0x1400fdfe5  mov     [rsp+150h+var_110], rax
0x1400fdfea  lea     rax, [rsp+150h+var_110]
0x1400fdfef  mov     [rbp+50h+var_50], rax
0x1400fdff3  lea     rax, [rsp+150h+var_F0]
0x1400fdff8  mov     [rsp+150h+var_128], rax
0x1400fdffd  mov     dword ptr [rsp+150h+Object], 0Bh
0x1400fe005  mov     [rbp+50h+var_64], r9d
0x1400fe009  mov     [rbp+50h+var_48], 8
0x1400fe011  jmp     loc_1400FE191
0x1400fe016  mov     rcx, [rdi+20h]
0x1400fe01a  mov     [rax+0Ch], r9
0x1400fe01e  mov     [rax+14h], r9
0x1400fe022  mov     [rax+1Ch], r9d
0x1400fe026  mov     [rax], r9
0x1400fe029  shl     rcx, 0Ch
0x1400fe02d  mov     [r15+20h], r9
0x1400fe031  mov     rax, rcx
0x1400fe034  shr     rax, 0Ch
0x1400fe038  add     ax, 6
0x1400fe03c  mov     [r15+2Ch], r9d
0x1400fe040  shl     ax, 3
0x1400fe044  mov     [r15+8], ax
0x1400fe049  mov     [r15+28h], ecx
0x1400fe04d  mov     [r15+0Ah], si
0x1400fe052  mov     r8, [rdi+20h]
  ... truncated ...
```
