# VsmmHwIsoDebugReadMbpRange

- ea: `0x1400e2408`
- end: `0x1400e2f1f`
- name: `VsmmHwIsoDebugReadMbpRange`
- size: `2839`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int64, void *, ULONG Length)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400295e0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002e080`
- `0x1400e2408`
- `0x1400edc70`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400e28f7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400e28f7`
- `ntoskrnl!IoFreeMdl` at `0x1400e2ed7`
- `ntoskrnl!IoFreeMdl` at `0x1400e2ed7`
- `ntoskrnl!IoAllocateMdl` at `0x1400e2789`
- `ntoskrnl!IoAllocateMdl` at `0x1400e2789`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400e28c6`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400e28c6`
- `ntoskrnl!MmUnlockPages` at `0x1400e2ec3`
- `ntoskrnl!MmUnlockPages` at `0x1400e2ec3`
- `winhvr!WinHvReadGpa` at `0x1400e2a81`
- `winhvr!WinHvReadGpa` at `0x1400e2a81`

## string_xrefs

- `0x1400e24c8`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e263b`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e27da`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e2940`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e2aeb`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e2c5b`: `VsmmHwIsoDebugReadMbpRange`
- `0x1400e2d6b`: `VsmmHwIsoDebugReadMbpRange`

## pseudocode

```c
__int64 __fastcall VsmmHwIsoDebugReadMbpRange(__int64 a1, int a2, unsigned __int64 a3, void *a4, ULONG Length)
{
  struct _MDL *v8; // rsi
  unsigned __int64 v9; // rcx
  int v10; // r14d
  __int64 v11; // rdx
  int v12; // ecx
  __int64 v13; // rax
  unsigned __int64 *v14; // rax
  char *v15; // rdx
  __int64 v16; // rdx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // r8
  struct _MDL *Mdl; // rax
  int v21; // r8d
  __int64 v22; // rdx
  int v23; // ecx
  __int64 v24; // rax
  char *MappedSystemVa; // r15
  int v26; // r8d
  __int64 v27; // rdx
  int v28; // ecx
  __int64 v29; // rax
  __int64 v30; // r12
  __int64 v31; // rbx
  unsigned __int64 v32; // r13
  __int64 v33; // rax
  __int64 v34; // rdx
  int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rdx
  int v38; // ecx
  __int64 v39; // rax
  int Irp; // [rsp+20h] [rbp-188h]
  char v42; // [rsp+40h] [rbp-168h]
  _QWORD v43[2]; // [rsp+48h] [rbp-160h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-150h] BYREF
  __int64 v45; // [rsp+60h] [rbp-148h] BYREF
  unsigned __int64 v46; // [rsp+68h] [rbp-140h] BYREF
  __int64 v47; // [rsp+70h] [rbp-138h] BYREF
  __int64 v48; // [rsp+78h] [rbp-130h] BYREF
  _QWORD v49[4]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v50[24]; // [rsp+A0h] [rbp-108h] BYREF
  _BYTE v51[16]; // [rsp+C0h] [rbp-E8h] BYREF
  _BYTE v52[16]; // [rsp+D0h] [rbp-D8h] BYREF
  unsigned __int64 *v53; // [rsp+E0h] [rbp-C8h]
  __int64 v54; // [rsp+E8h] [rbp-C0h]
  unsigned __int64 *v55; // [rsp+F0h] [rbp-B8h]
  __int64 v56; // [rsp+F8h] [rbp-B0h]
  __int64 v57; // [rsp+100h] [rbp-A8h]
  __int64 v58; // [rsp+108h] [rbp-A0h]
  int *v59; // [rsp+110h] [rbp-98h]
  __int64 v60; // [rsp+118h] [rbp-90h]
  __int64 v61; // [rsp+120h] [rbp-88h]
  int v62; // [rsp+128h] [rbp-80h] BYREF
  int v63; // [rsp+12Ch] [rbp-7Ch]
  unsigned __int64 *v64; // [rsp+130h] [rbp-78h]
  __int64 v65; // [rsp+138h] [rbp-70h]
  __int64 *v66; // [rsp+140h] [rbp-68h]
  __int64 v67; // [rsp+148h] [rbp-60h]
  unsigned __int64 *v68; // [rsp+150h] [rbp-58h]
  __int64 v69; // [rsp+158h] [rbp-50h]

  v44 = a3;
  v47 = a1;
  v49[1] = a1;
  v48 = 0;
  v46 = *(_QWORD *)(a1 + 8);
  v45 = 0;
  v42 = 0;
  v8 = 0;
  v49[0] = 0;
  v10 = VsmmGpaRangeLookupGpaByMbp(v46, a1, a2, 0, 0, (__int64)&v45, (__int64)v49);
  if ( v10 >= 0 )
  {
    v9 = *(_QWORD *)(v49[0] + 272LL) - v45 + 1;
    if ( a3 < v9 )
      v9 = a3;
    if ( v9 >= a3 )
    {
      Mdl = IoAllocateMdl(a4, Length, 0, 0, 0);
      v8 = Mdl;
      v49[2] = Mdl;
      if ( Mdl )
      {
        MmProbeAndLockPages(Mdl, 1, IoWriteAccess);
        if ( (v8->MdlFlags & 5) != 0 )
          MappedSystemVa = (char *)v8->MappedSystemVa;
        else
          MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v8, 0, MmCached, 0, 0, 0x40000010u);
        if ( MappedSystemVa )
        {
          v42 = 1;
          v43[0] = 6;
          v30 = 0;
          if ( a3 )
          {
            v31 = v43[0];
LABEL_26:
            v32 = 0;
            v33 = (v30 + v45) << 12;
            v43[0] = v33;
            while ( 1 )
            {
              v10 = WinHvReadGpa(*(_QWORD *)(v46 + 648), 0xFFFFFFFFLL, v33 + v32, 16, v31, &v48, MappedSystemVa);
              if ( v10 < 0 )
                break;
              if ( (_DWORD)v48 )
              {
                if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
                {
                  tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
                  tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
                  LODWORD(v43[0]) = 833;
                  v53 = v43;
                  v54 = 4;
                  LODWORD(v44) = v10;
                  v55 = &v44;
                  v56 = 4;
                  v34 = *(_QWORD *)(v47 + 8);
                  v57 = v34 + 656;
                  v58 = 16;
                  v35 = *(unsigned __int16 *)(v34 + 120);
                  v36 = *(_QWORD *)(v34 + 128);
                  v59 = &v62;
                  v60 = 2;
                  v61 = v36;
                  v62 = v35;
                  v63 = 0;
                  v46 = *(_QWORD *)(v34 + 648);
                  v64 = &v46;
                  v65 = 8;
                  LODWORD(v45) = v48;
                  v66 = &v45;
                  v67 = 4;
                  tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14005AC52, 0, 0, 11, v50);
                }
                v10 = -1073741790;
                goto LABEL_39;
              }
              MappedSystemVa += 16;
              v32 += 16LL;
              v33 = v43[0];
              if ( v32 >= 0x1000 )
              {
                if ( ++v30 < v44 )
                  goto LABEL_26;
                goto LABEL_39;
              }
            }
            if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            {
              tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
              tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
              LODWORD(v45) = 824;
              v53 = (unsigned __int64 *)&v45;
              v54 = 4;
              LODWORD(v43[0]) = v10;
              v55 = v43;
              v56 = 4;
              v37 = *(_QWORD *)(v47 + 8);
              v57 = v37 + 656;
              v58 = 16;
              v38 = *(unsigned __int16 *)(v37 + 120);
              v39 = *(_QWORD *)(v37 + 128);
              v59 = &v62;
              v60 = 2;
              v61 = v39;
              v62 = v38;
              v63 = 0;
              v46 = *(_QWORD *)(v37 + 648);
              v14 = &v46;
              v15 = (char *)&dword_14005ABE4;
              goto LABEL_5;
            }
          }
        }
        else
        {
          v10 = -1073741670;
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          {
            tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
            tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
            LODWORD(v43[0]) = 796;
            v53 = v43;
            v54 = 4;
            LODWORD(v44) = v26;
            v55 = &v44;
            v56 = 4;
            v27 = *(_QWORD *)(a1 + 8);
            v57 = v27 + 656;
            v58 = 16;
            v28 = *(unsigned __int16 *)(v27 + 120);
            v29 = *(_QWORD *)(v27 + 128);
            v59 = &v62;
            v60 = 2;
            v61 = v29;
            v62 = v28;
            v63 = 0;
            v46 = *(_QWORD *)(v27 + 648);
            v14 = &v46;
            v15 = byte_14005ADB5;
            goto LABEL_5;
          }
        }
      }
      else
      {
        v10 = -1073741670;
        v9 = (unsigned int)dword_140064110;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
          tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
          LODWORD(v43[0]) = 774;
          v53 = v43;
          v54 = 4;
          LODWORD(v44) = v21;
          v55 = &v44;
          v56 = 4;
          v22 = *(_QWORD *)(a1 + 8);
          v57 = v22 + 656;
          v58 = 16;
          v23 = *(unsigned __int16 *)(v22 + 120);
          v24 = *(_QWORD *)(v22 + 128);
          v59 = &v62;
          v60 = 2;
          v61 = v24;
          v62 = v23;
          v63 = 0;
          v46 = *(_QWORD *)(v22 + 648);
          v14 = &v46;
          v15 = byte_14005ACD9;
          goto LABEL_5;
        }
      }
    }
    else
    {
      v10 = -1073741811;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
        tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
        LODWORD(v43[0]) = 759;
        v53 = v43;
        v54 = 4;
        LODWORD(v44) = -1073741811;
        v55 = &v44;
        v56 = 4;
        v16 = *(_QWORD *)(a1 + 8);
        v57 = v16 + 656;
        v58 = 16;
        v17 = *(unsigned __int16 *)(v16 + 120);
        v18 = *(_QWORD *)(v16 + 128);
        v59 = &v62;
        v60 = 2;
        v61 = v18;
        v62 = v17;
        v63 = 0;
        v47 = *(_QWORD *)(v16 + 648);
        v64 = (unsigned __int64 *)&v47;
        v45 = v19;
        v66 = &v45;
        v67 = 8;
        v46 = a3;
        v68 = &v46;
        v69 = 8;
        Irp = 12;
        v15 = byte_14005AE91;
        goto LABEL_6;
      }
    }
  }
  else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v51, "VsmmHwIsoDebugReadMbpRange");
    tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisolation.c");
    LODWORD(v44) = 743;
    v53 = &v44;
    v54 = 4;
    LODWORD(v43[0]) = v10;
    v55 = v43;
    v56 = 4;
    v11 = *(_QWORD *)(a1 + 8);
    v57 = v11 + 656;
    v58 = 16;
    v12 = *(unsigned __int16 *)(v11 + 120);
    v13 = *(_QWORD *)(v11 + 128);
    v59 = &v62;
    v60 = 2;
    v61 = v13;
    v62 = v12;
    v63 = 0;
    v47 = *(_QWORD *)(v11 + 648);
    v14 = (unsigned __int64 *)&v47;
    v15 = byte_14005AE23;
LABEL_5:
    v64 = v14;
    Irp = 10;
LABEL_6:
    v65 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v15, 0, 0, Irp, v50);
  }
LABEL_39:
  if ( v42 )
    MmUnlockPages(v8);
  if ( v8 )
    IoFreeMdl(v8);
  if ( v49[0] )
    VsmmGpaRangeRelease(v9, v49[0], 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400e2408  push    rbx
0x1400e240a  push    rsi
0x1400e240b  push    rdi
0x1400e240c  push    r12
0x1400e240e  push    r13
0x1400e2410  push    r14
0x1400e2412  push    r15
0x1400e2414  sub     rsp, 170h
0x1400e241b  mov     rax, cs:__security_cookie
0x1400e2422  xor     rax, rsp
0x1400e2425  mov     [rsp+1A8h+var_48], rax
0x1400e242d  mov     r15, r9
0x1400e2430  mov     rbx, r8
0x1400e2433  mov     [rsp+1A8h+var_150], rbx
0x1400e2438  mov     r13, rcx
0x1400e243b  mov     [rsp+1A8h+var_138], rcx
0x1400e2440  mov     [rsp+1A8h+var_120], rcx
0x1400e2448  xor     edi, edi
0x1400e244a  mov     [rsp+1A8h+var_130], rdi
0x1400e244f  mov     rcx, [rcx+8]
0x1400e2453  mov     [rsp+1A8h+var_140], rcx
0x1400e2458  mov     [rsp+1A8h+var_148], rdi
0x1400e245d  mov     [rsp+1A8h+var_168], dil
0x1400e2462  mov     esi, edi
0x1400e2464  mov     [rsp+1A8h+var_128], rdi
0x1400e246c  lea     rax, [rsp+1A8h+var_128]
0x1400e2474  mov     [rsp+1A8h+var_178], rax
0x1400e2479  lea     rax, [rsp+1A8h+var_148]
0x1400e247e  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e2483  mov     dword ptr [rsp+1A8h+Irp], edi
0x1400e2487  xor     r9d, r9d
0x1400e248a  mov     r8, rdx
0x1400e248d  mov     rdx, r13
0x1400e2490  call    VsmmGpaRangeLookupGpaByMbp
0x1400e2495  mov     r14d, eax
0x1400e2498  test    eax, eax
0x1400e249a  jns     loc_1400E25E3
0x1400e24a0  mov     eax, cs:dword_140064110
0x1400e24a6  cmp     eax, 2
0x1400e24a9  jbe     loc_1400E2EB9
0x1400e24af  mov     edx, 100h
0x1400e24b4  lea     rcx, dword_140064110
0x1400e24bb  call    _tlgKeywordOn
0x1400e24c0  test    al, al
0x1400e24c2  jz      loc_1400E2EB9
0x1400e24c8  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e24cf  lea     rcx, [rsp+1A8h+var_E8]
0x1400e24d7  call    _tlgCreate1Sz_char
0x1400e24dc  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e24e3  lea     rcx, [rsp+1A8h+var_D8]
0x1400e24eb  call    _tlgCreate1Sz_char
0x1400e24f0  mov     dword ptr [rsp+1A8h+var_150], 2E7h
0x1400e24f8  lea     rax, [rsp+1A8h+var_150]
0x1400e24fd  mov     [rsp+1A8h+var_C8], rax
0x1400e2505  mov     [rsp+1A8h+var_C0], 4
0x1400e2511  mov     dword ptr [rsp+1A8h+var_160], r14d
0x1400e2516  lea     rax, [rsp+1A8h+var_160]
0x1400e251b  mov     [rsp+1A8h+var_B8], rax
0x1400e2523  mov     [rsp+1A8h+var_B0], 4
0x1400e252f  mov     rdx, [r13+8]
0x1400e2533  lea     rax, [rdx+290h]
0x1400e253a  mov     [rsp+1A8h+var_A8], rax
0x1400e2542  mov     [rsp+1A8h+var_A0], 10h
0x1400e254e  movzx   ecx, word ptr [rdx+78h]
0x1400e2552  mov     rax, [rdx+80h]
0x1400e2559  lea     r8, [rsp+1A8h+var_80]
0x1400e2561  mov     [rsp+1A8h+var_98], r8
0x1400e2569  mov     [rsp+1A8h+var_90], 2
0x1400e2575  mov     [rsp+1A8h+var_88], rax
0x1400e257d  mov     [rsp+1A8h+var_80], ecx
0x1400e2584  mov     [rsp+1A8h+var_7C], edi
0x1400e258b  mov     rax, [rdx+288h]
0x1400e2592  mov     [rsp+1A8h+var_138], rax
0x1400e2597  lea     rax, [rsp+1A8h+var_138]
0x1400e259c  lea     rdx, byte_14005AE23
0x1400e25a3  mov     [rsp+1A8h+var_78], rax
0x1400e25ab  lea     rax, [rsp+1A8h+var_108]
0x1400e25b3  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e25b8  mov     dword ptr [rsp+1A8h+Irp], 0Ah
0x1400e25c0  xor     r9d, r9d
0x1400e25c3  mov     [rsp+1A8h+var_70], 8
0x1400e25cf  xor     r8d, r8d
0x1400e25d2  lea     rcx, dword_140064110
0x1400e25d9  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400e25de  jmp     loc_1400E2EB9
0x1400e25e3  mov     rax, [rsp+1A8h+var_128]
0x1400e25eb  mov     rcx, [rax+110h]
0x1400e25f2  mov     r8, [rsp+1A8h+var_148]
0x1400e25f7  sub     rcx, r8
0x1400e25fa  inc     rcx
0x1400e25fd  cmp     rbx, rcx
0x1400e2600  cmovb   rcx, rbx
0x1400e2604  cmp     rcx, rbx
0x1400e2607  jnb     loc_1400E2774
0x1400e260d  mov     r14d, 0C000000Dh
0x1400e2613  mov     eax, cs:dword_140064110
0x1400e2619  cmp     eax, 2
0x1400e261c  jbe     loc_1400E2EB9
0x1400e2622  mov     edx, 100h
0x1400e2627  lea     rcx, dword_140064110
0x1400e262e  call    _tlgKeywordOn
0x1400e2633  test    al, al
0x1400e2635  jz      loc_1400E2EB9
0x1400e263b  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e2642  lea     rcx, [rsp+1A8h+var_E8]
0x1400e264a  call    _tlgCreate1Sz_char
0x1400e264f  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e2656  lea     rcx, [rsp+1A8h+var_D8]
0x1400e265e  call    _tlgCreate1Sz_char
0x1400e2663  mov     dword ptr [rsp+1A8h+var_160], 2F7h
0x1400e266b  lea     rax, [rsp+1A8h+var_160]
0x1400e2670  mov     [rsp+1A8h+var_C8], rax
0x1400e2678  mov     [rsp+1A8h+var_C0], 4
0x1400e2684  mov     dword ptr [rsp+1A8h+var_150], r14d
0x1400e2689  lea     rax, [rsp+1A8h+var_150]
0x1400e268e  mov     [rsp+1A8h+var_B8], rax
0x1400e2696  mov     [rsp+1A8h+var_B0], 4
0x1400e26a2  mov     rdx, [r13+8]
0x1400e26a6  lea     rax, [rdx+290h]
0x1400e26ad  mov     [rsp+1A8h+var_A8], rax
0x1400e26b5  mov     [rsp+1A8h+var_A0], 10h
0x1400e26c1  movzx   ecx, word ptr [rdx+78h]
0x1400e26c5  mov     rax, [rdx+80h]
0x1400e26cc  lea     r9, [rsp+1A8h+var_80]
0x1400e26d4  mov     [rsp+1A8h+var_98], r9
0x1400e26dc  mov     [rsp+1A8h+var_90], 2
0x1400e26e8  mov     [rsp+1A8h+var_88], rax
0x1400e26f0  mov     [rsp+1A8h+var_80], ecx
0x1400e26f7  mov     [rsp+1A8h+var_7C], edi
0x1400e26fe  mov     rax, [rdx+288h]
0x1400e2705  mov     [rsp+1A8h+var_138], rax
0x1400e270a  lea     rax, [rsp+1A8h+var_138]
0x1400e270f  mov     [rsp+1A8h+var_78], rax
0x1400e2717  mov     [rsp+1A8h+var_148], r8
0x1400e271c  lea     rax, [rsp+1A8h+var_148]
0x1400e2721  mov     [rsp+1A8h+var_68], rax
0x1400e2729  mov     [rsp+1A8h+var_60], 8
0x1400e2735  mov     [rsp+1A8h+var_140], rbx
0x1400e273a  lea     rax, [rsp+1A8h+var_140]
0x1400e273f  mov     [rsp+1A8h+var_58], rax
0x1400e2747  mov     [rsp+1A8h+var_50], 8
0x1400e2753  lea     rax, [rsp+1A8h+var_108]
0x1400e275b  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e2760  mov     dword ptr [rsp+1A8h+Irp], 0Ch
0x1400e2768  lea     rdx, byte_14005AE91
0x1400e276f  jmp     loc_1400E25C0
0x1400e2774  mov     edx, [rsp+1A8h+Length]; Length
0x1400e277b  mov     [rsp+1A8h+Irp], rdi; Irp
0x1400e2780  xor     r9d, r9d; ChargeQuota
0x1400e2783  xor     r8d, r8d; SecondaryBuffer
0x1400e2786  mov     rcx, r15; VirtualAddress
0x1400e2789  call    cs:__imp_IoAllocateMdl
0x1400e2790  nop     dword ptr [rax+rax+00h]
0x1400e2795  mov     rsi, rax
0x1400e2798  mov     [rsp+1A8h+var_118], rax
0x1400e27a0  test    rax, rax
0x1400e27a3  jnz     loc_1400E28BA
0x1400e27a9  mov     r8d, 0C000009Ah
0x1400e27af  mov     r14d, r8d
0x1400e27b2  mov     ecx, cs:dword_140064110
0x1400e27b8  cmp     ecx, 2
0x1400e27bb  jbe     loc_1400E2EB9
0x1400e27c1  mov     edx, 100h
0x1400e27c6  lea     rcx, dword_140064110
0x1400e27cd  call    _tlgKeywordOn
0x1400e27d2  test    al, al
0x1400e27d4  jz      loc_1400E2EB9
0x1400e27da  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e27e1  lea     rcx, [rsp+1A8h+var_E8]
0x1400e27e9  call    _tlgCreate1Sz_char
0x1400e27ee  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e27f5  lea     rcx, [rsp+1A8h+var_D8]
0x1400e27fd  call    _tlgCreate1Sz_char
0x1400e2802  mov     dword ptr [rsp+1A8h+var_160], 306h
0x1400e280a  lea     rax, [rsp+1A8h+var_160]
0x1400e280f  mov     [rsp+1A8h+var_C8], rax
0x1400e2817  mov     [rsp+1A8h+var_C0], 4
0x1400e2823  mov     dword ptr [rsp+1A8h+var_150], r8d
0x1400e2828  lea     rax, [rsp+1A8h+var_150]
0x1400e282d  mov     [rsp+1A8h+var_B8], rax
0x1400e2835  mov     [rsp+1A8h+var_B0], 4
0x1400e2841  mov     rdx, [r13+8]
0x1400e2845  lea     rax, [rdx+290h]
0x1400e284c  mov     [rsp+1A8h+var_A8], rax
0x1400e2854  mov     [rsp+1A8h+var_A0], 10h
0x1400e2860  movzx   ecx, word ptr [rdx+78h]
0x1400e2864  mov     rax, [rdx+80h]
0x1400e286b  lea     r8, [rsp+1A8h+var_80]
0x1400e2873  mov     [rsp+1A8h+var_98], r8
0x1400e287b  mov     [rsp+1A8h+var_90], 2
0x1400e2887  mov     [rsp+1A8h+var_88], rax
0x1400e288f  mov     [rsp+1A8h+var_80], ecx
0x1400e2896  mov     [rsp+1A8h+var_7C], edi
0x1400e289d  mov     rax, [rdx+288h]
0x1400e28a4  mov     [rsp+1A8h+var_140], rax
0x1400e28a9  lea     rax, [rsp+1A8h+var_140]
0x1400e28ae  lea     rdx, byte_14005ACD9
0x1400e28b5  jmp     loc_1400E25A3
0x1400e28ba  mov     r8d, 1; Operation
0x1400e28c0  mov     dl, r8b; AccessMode
0x1400e28c3  mov     rcx, rsi; MemoryDescriptorList
0x1400e28c6  call    cs:__imp_MmProbeAndLockPages
0x1400e28cd  nop     dword ptr [rax+rax+00h]
0x1400e28d2  nop
0x1400e28d3  test    byte ptr [rsi+0Ah], 5
0x1400e28d7  jz      short loc_1400E28DF
0x1400e28d9  mov     r15, [rsi+18h]
0x1400e28dd  jmp     short loc_1400E2906
0x1400e28df  mov     [rsp+1A8h+Priority], 40000010h; Priority
0x1400e28e7  mov     dword ptr [rsp+1A8h+Irp], edi; BugCheckOnFailure
0x1400e28eb  xor     r9d, r9d; RequestedAddress
0x1400e28ee  xor     edx, edx; AccessMode
0x1400e28f0  lea     r8d, [r9+1]; CacheType
0x1400e28f4  mov     rcx, rsi; MemoryDescriptorList
0x1400e28f7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400e28fe  nop     dword ptr [rax+rax+00h]
0x1400e2903  mov     r15, rax
0x1400e2906  test    r15, r15
0x1400e2909  jnz     loc_1400E2A20
0x1400e290f  mov     r8d, 0C000009Ah
0x1400e2915  mov     r14d, r8d
0x1400e2918  mov     eax, cs:dword_140064110
0x1400e291e  cmp     eax, 2
0x1400e2921  jbe     loc_1400E2EB9
0x1400e2927  mov     edx, 100h
0x1400e292c  lea     rcx, dword_140064110
0x1400e2933  call    _tlgKeywordOn
0x1400e2938  test    al, al
0x1400e293a  jz      loc_1400E2EB9
0x1400e2940  lea     rdx, aVsmmhwisodebug; "VsmmHwIsoDebugReadMbpRange"
0x1400e2947  lea     rcx, [rsp+1A8h+var_E8]
0x1400e294f  call    _tlgCreate1Sz_char
0x1400e2954  lea     rdx, aOnecoreVmVidSy_24; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhwisol"...
0x1400e295b  lea     rcx, [rsp+1A8h+var_D8]
0x1400e2963  call    _tlgCreate1Sz_char
0x1400e2968  mov     dword ptr [rsp+1A8h+var_160], 31Ch
0x1400e2970  lea     rax, [rsp+1A8h+var_160]
0x1400e2975  mov     [rsp+1A8h+var_C8], rax
0x1400e297d  mov     [rsp+1A8h+var_C0], 4
0x1400e2989  mov     dword ptr [rsp+1A8h+var_150], r8d
0x1400e298e  lea     rax, [rsp+1A8h+var_150]
0x1400e2993  mov     [rsp+1A8h+var_B8], rax
0x1400e299b  mov     [rsp+1A8h+var_B0], 4
0x1400e29a7  mov     rdx, [r13+8]
0x1400e29ab  lea     rax, [rdx+290h]
0x1400e29b2  mov     [rsp+1A8h+var_A8], rax
0x1400e29ba  mov     [rsp+1A8h+var_A0], 10h
0x1400e29c6  movzx   ecx, word ptr [rdx+78h]
0x1400e29ca  mov     rax, [rdx+80h]
0x1400e29d1  lea     r8, [rsp+1A8h+var_80]
0x1400e29d9  mov     [rsp+1A8h+var_98], r8
0x1400e29e1  mov     [rsp+1A8h+var_90], 2
0x1400e29ed  mov     [rsp+1A8h+var_88], rax
0x1400e29f5  mov     [rsp+1A8h+var_80], ecx
0x1400e29fc  mov     [rsp+1A8h+var_7C], edi
0x1400e2a03  mov     rax, [rdx+288h]
0x1400e2a0a  mov     [rsp+1A8h+var_140], rax
0x1400e2a0f  lea     rax, [rsp+1A8h+var_140]
0x1400e2a14  lea     rdx, byte_14005ADB5
0x1400e2a1b  jmp     loc_1400E25A3
0x1400e2a20  mov     [rsp+1A8h+var_168], 1
0x1400e2a25  mov     [rsp+1A8h+var_160], rdi
0x1400e2a2a  mov     byte ptr [rsp+1A8h+var_160], 6
0x1400e2a2f  mov     r12, rdi
0x1400e2a32  test    rbx, rbx
0x1400e2a35  jz      loc_1400E2EB9
0x1400e2a3b  mov     rbx, [rsp+1A8h+var_160]
0x1400e2a40  mov     r13, rdi
0x1400e2a43  mov     rax, [rsp+1A8h+var_148]
0x1400e2a48  add     rax, r12
0x1400e2a4b  shl     rax, 0Ch
0x1400e2a4f  mov     [rsp+1A8h+var_160], rax
0x1400e2a54  lea     r8, [rax+r13]
0x1400e2a58  mov     [rsp+1A8h+var_178], r15
0x1400e2a5d  lea     rax, [rsp+1A8h+var_130]
0x1400e2a62  mov     qword ptr [rsp+1A8h+Priority], rax
0x1400e2a67  mov     [rsp+1A8h+Irp], rbx
0x1400e2a6c  mov     r9d, 10h
0x1400e2a72  or      edx, 0FFFFFFFFh
0x1400e2a75  mov     rax, [rsp+1A8h+var_140]
0x1400e2a7a  mov     rcx, [rax+288h]
0x1400e2a81  call    cs:__imp_WinHvReadGpa
0x1400e2a88  nop     dword ptr [rax+rax+00h]
0x1400e2a8d  mov     r14d, eax
0x1400e2a90  test    eax, eax
0x1400e2a92  js      loc_1400E2C33
0x1400e2a98  cmp     dword ptr [rsp+1A8h+var_130], edi
0x1400e2a9c  jnz     short loc_1400E2AC3
0x1400e2a9e  add     r15, 10h
0x1400e2aa2  add     r13, 10h
0x1400e2aa6  cmp     r13, 1000h
0x1400e2aad  mov     rax, [rsp+1A8h+var_160]
0x1400e2ab2  jb      short loc_1400E2A54
0x1400e2ab4  inc     r12
0x1400e2ab7  cmp     r12, [rsp+1A8h+var_150]
0x1400e2abc  jb      short loc_1400E2A40
0x1400e2abe  jmp     loc_1400E2EB9
0x1400e2ac3  mov     eax, cs:dword_140064110
0x1400e2ac9  cmp     eax, 2
0x1400e2acc  jbe     loc_1400E2C28
  ... truncated ...
```
