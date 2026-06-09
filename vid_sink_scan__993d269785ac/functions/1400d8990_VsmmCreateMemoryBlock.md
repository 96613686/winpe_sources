# VsmmCreateMemoryBlock

- ea: `0x1400d8990`
- end: `0x1400d974e`
- name: `VsmmCreateMemoryBlock`
- size: `3518`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update`

## callers

- `0x140035698`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x1400116c8`
- `0x140021650`
- `0x14002b228`
- `0x14002b430`
- `0x1400303c0`
- `0x140030960`
- `0x140034554`
- `0x1400345f0`
- `0x140034914`
- `0x140034a14`
- `0x140034d68`
- `0x140038630`
- `0x140074d50`
- `0x14009ea60`
- `0x1400d8990`
- `0x1400dcbe4`
- `0x1400ddc18`
- `0x1400de9ac`
- `0x1400e832c`
- `0x1400ef614`
- `0x1400f2bac`
- `0x1400f2cbc`
- `0x1400f34cc`
- `0x1400fe38c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1400d8a11`
- `ntoskrnl!EtwEventEnabled` at `0x1400d947b`
- `ntoskrnl!EtwEventEnabled` at `0x1400d94b8`
- `ntoskrnl!EtwEventEnabled` at `0x1400d8a11`
- `ntoskrnl!EtwEventEnabled` at `0x1400d947b`
- `ntoskrnl!EtwEventEnabled` at `0x1400d94b8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d8e6d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400d8e6d`

## string_xrefs

- `0x1400d8a72`: `VsmmCreateMemoryBlock`
- `0x1400d8aad`: `VsmmCreateMemoryBlock`
- `0x1400d8ae9`: `VsmmCreateMemoryBlock`
- `0x1400d8b26`: `VsmmCreateMemoryBlock`
- `0x1400d8b7d`: `VsmmCreateMemoryBlock`
- `0x1400d8d4f`: `VsmmCreateMemoryBlock`
- `0x1400d8d77`: `VsmmCreateMemoryBlock`
- `0x1400d8dbe`: `VsmmCreateMemoryBlock`
- `0x1400d8e0f`: `VsmmCreateMemoryBlock`
- `0x1400d8e4a`: `VsmmCreateMemoryBlock`
- `0x1400d8ea0`: `VsmmCreateMemoryBlock`
- `0x1400d8f37`: `VsmmCreateMemoryBlock`
- `0x1400d8fa1`: `VsmmCreateMemoryBlock`
- `0x1400d9081`: `VsmmCreateMemoryBlock`
- `0x1400d90c6`: `VsmmCreateMemoryBlock`
- `0x1400d9126`: `VsmmCreateMemoryBlock`
- `0x1400d91af`: `VsmmCreateMemoryBlock`
- `0x1400d928d`: `VsmmCreateMemoryBlock`
- `0x1400d9384`: `VsmmCreateMemoryBlock`
- `0x1400d93df`: `VsmmCreateMemoryBlock`
- `0x1400d9402`: `VsmmCreateMemoryBlock`
- `0x1400d9512`: `VsmmCreateMemoryBlock`

## pseudocode

```c
__int64 __fastcall VsmmCreateMemoryBlock(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r12
  _QWORD *v4; // r13
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r12
  __int64 v10; // r8
  __int64 *v11; // r9
  __int64 *v12; // rdx
  void **v13; // r13
  __int64 v14; // r9
  __int64 v15; // r8
  unsigned __int64 v16; // rax
  size_t v17; // r8
  void *v18; // rdx
  __int64 v19; // rdx
  char *v20; // rcx
  int v21; // eax
  _QWORD *v22; // rcx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  int v27; // [rsp+20h] [rbp-1D8h]
  char v28; // [rsp+30h] [rbp-1C8h]
  char v29; // [rsp+31h] [rbp-1C7h] BYREF
  _QWORD *v30; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 *v31; // [rsp+40h] [rbp-1B8h] BYREF
  PVOID P; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v33; // [rsp+50h] [rbp-1A8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-1A0h] BYREF
  int v35; // [rsp+60h] [rbp-198h] BYREF
  _QWORD *v36; // [rsp+68h] [rbp-190h] BYREF
  __int64 v37; // [rsp+70h] [rbp-188h] BYREF
  __int64 v38; // [rsp+78h] [rbp-180h] BYREF
  _BYTE *v39; // [rsp+80h] [rbp-178h] BYREF
  void *v40[2]; // [rsp+88h] [rbp-170h] BYREF
  GUID ActivityId; // [rsp+98h] [rbp-160h] BYREF
  _BYTE v42[32]; // [rsp+B0h] [rbp-148h] BYREF
  _BYTE v43[16]; // [rsp+D0h] [rbp-128h] BYREF
  _BYTE v44[16]; // [rsp+E0h] [rbp-118h] BYREF
  __int64 *v45; // [rsp+F0h] [rbp-108h]
  __int64 v46; // [rsp+F8h] [rbp-100h]
  __int64 *v47; // [rsp+100h] [rbp-F8h]
  __int64 v48; // [rsp+108h] [rbp-F0h]
  __int64 v49; // [rsp+110h] [rbp-E8h]
  __int64 v50; // [rsp+118h] [rbp-E0h]
  int *v51; // [rsp+120h] [rbp-D8h]
  __int64 v52; // [rsp+128h] [rbp-D0h]
  __int64 v53; // [rsp+130h] [rbp-C8h]
  int v54; // [rsp+138h] [rbp-C0h] BYREF
  int v55; // [rsp+13Ch] [rbp-BCh]
  __int64 *v56; // [rsp+140h] [rbp-B8h]
  __int64 v57; // [rsp+148h] [rbp-B0h]
  __int64 *v58; // [rsp+150h] [rbp-A8h]
  __int64 v59; // [rsp+158h] [rbp-A0h]
  __int64 *v60; // [rsp+160h] [rbp-98h]
  __int64 v61; // [rsp+168h] [rbp-90h]
  __int64 *v62; // [rsp+170h] [rbp-88h]
  __int64 v63; // [rsp+178h] [rbp-80h]
  _BYTE **v64; // [rsp+180h] [rbp-78h]
  __int64 v65; // [rsp+188h] [rbp-70h]
  _QWORD **v66; // [rsp+190h] [rbp-68h]
  __int64 v67; // [rsp+198h] [rbp-60h]
  char *v68; // [rsp+1A0h] [rbp-58h]
  __int64 v69; // [rsp+1A8h] [rbp-50h]
  GUID *p_ActivityId; // [rsp+1B0h] [rbp-48h]
  __int64 v71; // [rsp+1B8h] [rbp-40h]

  v3 = a3;
  v30 = a3;
  v4 = (_QWORD *)a2;
  v31 = (__int64 *)a2;
  v34 = a2;
  v38 = a1;
  v36 = a3;
  *(_OWORD *)v40 = 0;
  v35 = 0;
  P = 0;
  VidTraceCreateAndSetActivityId(&ActivityId);
  if ( VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_CREATE_MEMBLOCK_START) )
    VidTraceInt2Routine(&VID_CREATE_MEMBLOCK_START);
  v28 = 0;
  P = 0;
  *(_OWORD *)v40 = 0;
  v39 = v4 + 2;
  v7 = v4[2];
  if ( (v7 & 0x40) != 0 )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 417);
    goto LABEL_89;
  }
  v9 = v4[2] & 4LL;
  if ( (v9 != 0) != (v4[9] != 0) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 429);
LABEL_88:
    v3 = v30;
    goto LABEL_89;
  }
  v10 = v4[5];
  if ( (v4[4] == 0) != (v10 == 0) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 437);
    goto LABEL_88;
  }
  if ( v10 && v10 != 8 * ((unsigned __int64)(*v4 + 63LL) >> 6) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 457);
    goto LABEL_88;
  }
  if ( (v4[10] || v4[11]) && (v7 & 8) == 0 )
  {
    v8 = -1073741811;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_88;
    tlgCreate1Sz_char(v43, "VsmmCreateMemoryBlock");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v31) = 477;
    v45 = (__int64 *)&v31;
    v46 = 4;
    LODWORD(v33) = -1073741811;
    v47 = &v33;
    v48 = 4;
    v49 = a1 + 656;
    v51 = &v54;
    v53 = *(_QWORD *)(a1 + 128);
    v54 = *(unsigned __int16 *)(a1 + 120);
    v36 = *(_QWORD **)(a1 + 648);
    v56 = (__int64 *)&v36;
    v37 = *v11;
    v58 = &v37;
    v59 = 8;
    v38 = v4[10];
    v60 = &v38;
    v61 = 8;
    v34 = v4[11];
    v62 = &v34;
    v63 = 8;
    v27 = 13;
    v12 = (__int64 *)byte_140058845;
    goto LABEL_19;
  }
  v13 = 0;
  if ( *(_QWORD *)(a2 + 48) )
  {
    v14 = *(_QWORD *)(a2 + 56);
    if ( !v14 )
      goto LABEL_86;
    v15 = *(unsigned __int8 *)(a2 + 64);
    if ( !(_BYTE)v15 )
      goto LABEL_86;
    if ( (v7 & 1) != 0 )
    {
      if ( (v7 & 8) != 0 )
      {
        if ( ((*(_DWORD *)(a1 + 24) >> 9) & 0xF) != 0 && (*(_BYTE *)(a1 + 32) & 3) != 1 )
        {
          if ( v15 != ((*(_DWORD *)(a1 + 24) >> 9) & 0xF) )
          {
            v8 = -1073741811;
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 548);
            goto LABEL_87;
          }
          v4 = (_QWORD *)a2;
          v16 = ((1LL << v15) + *(_QWORD *)a2 - 1LL) / (unsigned __int64)(1LL << v15);
          if ( v14 != 8 * ((v16 + 63) >> 6) )
          {
            v8 = -1073741811;
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 562);
            goto LABEL_88;
          }
          v8 = VsmmBitmapSetup(v40, v16, 64, 0);
          if ( v8 < 0 )
          {
            VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 576);
            goto LABEL_88;
          }
          v17 = *(_QWORD *)(a2 + 56);
          v18 = *(void **)(a2 + 48);
          if ( v17 && ((unsigned __int8)v18 & 7) != 0 )
            ExRaiseDatatypeMisalignment();
          RtlCopyFromUser(v40[1], v18, v17);
          v13 = v40;
        }
        *(_QWORD *)(a2 + 48) = 0;
        *(_QWORD *)(a2 + 56) = 0;
        goto LABEL_44;
      }
      v8 = -1073741811;
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 521);
    }
    else
    {
      v8 = -1073741637;
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 511);
    }
LABEL_87:
    v4 = (_QWORD *)a2;
    goto LABEL_88;
  }
  if ( *(_QWORD *)(a2 + 56) || *(_BYTE *)(a2 + 64) )
  {
LABEL_86:
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 495);
    goto LABEL_87;
  }
LABEL_44:
  if ( *(_QWORD *)(a2 + 24) >= *(_QWORD *)(a2 + 8)
    || (*(_QWORD *)(a2 + 24) & 0x1FFLL) != 0 && (*(_QWORD *)(a2 + 24) & 0x3FFFFLL) != 0 )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 615);
    goto LABEL_49;
  }
  VidObjectLockAcquireExclusive(a1 + 3736);
  v28 = 1;
  if ( (*v39 & 1) != 0 && *(_QWORD *)(a1 + 8LL * *(unsigned __int8 *)(a2 + 65) + 8984) )
  {
    v8 = -1073741811;
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 631);
LABEL_49:
    v4 = v31;
    goto LABEL_88;
  }
  if ( v9 )
  {
    v19 = *(_QWORD *)(a2 + 72);
    if ( *(_BYTE *)(a1 + 8657) )
    {
      v8 = VsmmMemoryBlockLookupByPersistId(a1, v19, 0, &P);
      if ( v8 >= 0 )
      {
        v20 = (char *)P;
        v3 = v30;
        *v30 = *((_QWORD *)P + 3);
        VidOpCtrlFinish(v20 + 128);
        P = 0;
        v4 = v31;
        goto LABEL_89;
      }
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v43, "VsmmCreateMemoryBlock");
        tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v33) = 651;
        v45 = &v33;
        v46 = 4;
        v34 = *(_QWORD *)(a2 + 72);
        v47 = &v34;
        v48 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_1400588DD, 0, 0, 6, v42);
      }
      goto LABEL_49;
    }
    v8 = VsmmPhuCheckObjectRestore(a1, v19);
    if ( v8 < 0 )
    {
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 673);
      goto LABEL_49;
    }
  }
  v8 = VsmmMemoryBlockAlloc((__int64 *)&P, a1, a2, (__int64)v13, 0, &v35);
  if ( v8 < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 688);
    goto LABEL_49;
  }
  v4 = v31;
  if ( !v9 )
  {
    v33 = 0;
    v8 = VsmmMemoryBlockDmBalloon(
           (__int64)P,
           *v31,
           *(_QWORD *)(a2 + 8),
           *(void **)(a2 + 32),
           *(_QWORD *)(a2 + 40),
           &v33);
    if ( v8 < 0 )
    {
      VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 707);
      goto LABEL_88;
    }
    v21 = *((_DWORD *)P + 5);
    if ( (v21 & 8) != 0 )
    {
      v8 = VsmmMemoryBlockBackVirtually((_DWORD)P, *(_QWORD *)(a2 + 80), 0, 0, a2 + 88);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_88;
        tlgCreate1Sz_char(v43, "VsmmCreateMemoryBlock");
        tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
        LODWORD(v33) = 760;
        v45 = &v33;
        v46 = 4;
        LODWORD(v31) = v8;
        v47 = (__int64 *)&v31;
        v48 = 4;
        v49 = a1 + 656;
        v51 = &v54;
        v53 = *(_QWORD *)(a1 + 128);
        v54 = *(unsigned __int16 *)(a1 + 120);
        v34 = *(_QWORD *)(a1 + 648);
        v56 = &v34;
        v27 = 10;
        v12 = qword_140058620;
LABEL_19:
        v50 = 16;
        v52 = 2;
        v57 = 8;
        v55 = 0;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v12, 0, 0, v27, v42);
        goto LABEL_88;
      }
    }
    else if ( v33 )
    {
      if ( (v21 & 0x10) != 0 )
      {
        v8 = VsmmMemoryBlockBackNoReserve();
        if ( v8 == -1073741670 )
          v8 = -1070137301;
      }
      else
      {
        v8 = VsmmMemoryBlockBackFromReserveBucket(P, *(_QWORD *)(a2 + 8), *(_QWORD *)(a2 + 24));
      }
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VsmmCreateMemoryBlock");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
          LODWORD(v33) = 742;
          v45 = &v33;
          v46 = 4;
          LODWORD(v31) = *((_DWORD *)P + 5);
          v47 = (__int64 *)&v31;
          v48 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_1400585D7, 0, 0, 6, v42);
        }
        goto LABEL_88;
      }
    }
  }
  v8 = VsmmMemoryBlockHandleTableInsert(P);
  if ( v8 < 0 )
  {
    VidTraceErrorInternal0("VsmmCreateMemoryBlock", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 775);
    goto LABEL_88;
  }
  v22 = P;
  if ( *((_QWORD *)P + 80) )
  {
    v23 = *((_DWORD *)P + 5);
    if ( (v23 & 0x20) != 0 )
    {
      *((_DWORD *)P + 5) = v23 | 0x800;
      v22 = P;
    }
  }
  v3 = v30;
  *v30 = v22[3];
  if ( v35 )
    VsmmHostAccessMakeMbpsSharedForVmPhuUpgrade((__int64)v22);
LABEL_89:
  VsmmBitmapTeardown(v40);
  if ( v8 < 0 )
  {
    if ( P )
    {
      VsmmDmMemoryBlockUninitialize(P, v24, v25);
      VsmmMemoryBlockMetadataTeardown(P);
      VsmmMemoryBlockFree(P);
    }
    *v3 = -1;
  }
  if ( v28 )
    VidObjectLockRelease(a1 + 3736);
  if ( v8 < 0
    && VID_TRACE_ETW_GUID_Context
    && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &MSVML_VID_CREATE_MEMBLOCK_ERROR) )
  {
    VidTraceInt3Routine(&MSVML_VID_CREATE_MEMBLOCK_ERROR);
  }
  if ( VID_TRACE_ETW_GUID_Context && EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_CREATE_MEMBLOCK_STOP) )
    VidTraceInt3Routine(&VID_CREATE_MEMBLOCK_STOP);
  if ( v8 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v43, "VsmmCreateMemoryBlock");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    LODWORD(v33) = 854;
    v45 = &v33;
    v46 = 4;
    LODWORD(v31) = v8;
    v47 = (__int64 *)&v31;
    v48 = 4;
    v49 = a1 + 656;
    v50 = 16;
    v51 = &v54;
    v52 = 2;
    v53 = *(_QWORD *)(a1 + 128);
    v54 = *(unsigned __int16 *)(a1 + 120);
    v55 = 0;
    v34 = *(_QWORD *)(a1 + 648);
    v56 = &v34;
    v57 = 8;
    v38 = *v4;
    v58 = &v38;
    v59 = 8;
    v37 = *(_QWORD *)(a2 + 8);
    v60 = &v37;
    v61 = 8;
    v36 = *(_QWORD **)v39;
    v62 = (__int64 *)&v36;
    v63 = 8;
    v39 = *(_BYTE **)(a2 + 24);
    v64 = &v39;
    v65 = 8;
    v30 = *(_QWORD **)(a2 + 40);
    v66 = &v30;
    v67 = 8;
    v29 = *(_BYTE *)(a2 + 65);
    v68 = &v29;
    v69 = 1;
    *(_QWORD *)&ActivityId.Data1 = *(_QWORD *)(a2 + 72);
    p_ActivityId = &ActivityId;
    v71 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_14005868E, 0, 0, 17, v42);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400d8990  mov     [rsp+arg_18], rbx
0x1400d8995  push    rsi
0x1400d8996  push    rdi
0x1400d8997  push    r12
0x1400d8999  push    r13
0x1400d899b  push    r14
0x1400d899d  sub     rsp, 1D0h
0x1400d89a4  mov     rax, cs:__security_cookie
0x1400d89ab  xor     rax, rsp
0x1400d89ae  mov     [rsp+1F8h+var_38], rax
0x1400d89b6  mov     r12, r8
0x1400d89b9  mov     [rsp+1F8h+var_1C0], r8
0x1400d89be  mov     r13, rdx
0x1400d89c1  mov     [rsp+1F8h+var_1B8], rdx
0x1400d89c6  mov     r14, rcx
0x1400d89c9  mov     [rsp+1F8h+var_1A0], rdx
0x1400d89ce  mov     [rsp+1F8h+var_180], rcx
0x1400d89d3  mov     rsi, rdx
0x1400d89d6  mov     [rsp+1F8h+var_190], r8
0x1400d89db  xorps   xmm0, xmm0
0x1400d89de  movups  xmmword ptr [rsp+1F8h+var_170], xmm0
0x1400d89e6  xor     ebx, ebx
0x1400d89e8  mov     [rsp+1F8h+var_198], ebx
0x1400d89ec  mov     [rsp+1F8h+P], rbx
0x1400d89f1  lea     rcx, [rsp+1F8h+ActivityId]; ActivityId
0x1400d89f9  call    VidTraceCreateAndSetActivityId
0x1400d89fe  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x1400d8a05  test    rcx, rcx
0x1400d8a08  jz      short loc_1400D8A38
0x1400d8a0a  lea     rdx, VID_CREATE_MEMBLOCK_START; EventDescriptor
0x1400d8a11  call    cs:__imp_EtwEventEnabled
0x1400d8a18  nop     dword ptr [rax+rax+00h]
0x1400d8a1d  test    al, al
0x1400d8a1f  jz      short loc_1400D8A38
0x1400d8a21  mov     r8, [rsi+8]
0x1400d8a25  mov     rdx, [r14+288h]
0x1400d8a2c  lea     rcx, VID_CREATE_MEMBLOCK_START; EventDescriptor
0x1400d8a33  call    VidTraceInt2Routine
0x1400d8a38  mov     [rsp+1F8h+var_1C8], bl
0x1400d8a3c  mov     [rsp+1F8h+P], rbx
0x1400d8a41  xorps   xmm0, xmm0
0x1400d8a44  movups  xmmword ptr [rsp+1F8h+var_170], xmm0
0x1400d8a4c  lea     r9, [r13+10h]
0x1400d8a50  mov     [rsp+1F8h+var_178], r9
0x1400d8a58  mov     rdx, [r9]
0x1400d8a5b  test    dl, 40h
0x1400d8a5e  jz      short loc_1400D8A83
0x1400d8a60  mov     edi, 0C000000Dh
0x1400d8a65  mov     r8d, 1A1h
0x1400d8a6b  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8a72  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8a79  call    VidTraceErrorInternal0
0x1400d8a7e  jmp     loc_1400D9416
0x1400d8a83  mov     r12, rdx
0x1400d8a86  and     r12d, 4
0x1400d8a8a  cmp     [r13+48h], rbx
0x1400d8a8e  setnz   cl
0x1400d8a91  test    r12, r12
0x1400d8a94  setnz   al
0x1400d8a97  cmp     al, cl
0x1400d8a99  jz      short loc_1400D8ABE
0x1400d8a9b  mov     edi, 0C000000Dh
0x1400d8aa0  mov     r8d, 1ADh
0x1400d8aa6  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8aad  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8ab4  call    VidTraceErrorInternal0
0x1400d8ab9  jmp     loc_1400D9411
0x1400d8abe  mov     r8, [r13+28h]
0x1400d8ac2  mov     ecx, ebx
0x1400d8ac4  test    r8, r8
0x1400d8ac7  setz    cl
0x1400d8aca  mov     eax, ebx
0x1400d8acc  cmp     [r13+20h], rbx
0x1400d8ad0  setz    al
0x1400d8ad3  cmp     eax, ecx
0x1400d8ad5  jz      short loc_1400D8AFA
0x1400d8ad7  mov     edi, 0C000000Dh
0x1400d8adc  mov     r8d, 1B5h
0x1400d8ae2  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8ae9  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8af0  call    VidTraceErrorInternal0
0x1400d8af5  jmp     loc_1400D9411
0x1400d8afa  test    r8, r8
0x1400d8afd  jz      short loc_1400D8B37
0x1400d8aff  mov     rax, [r13+0]
0x1400d8b03  add     rax, 3Fh ; '?'
0x1400d8b07  shr     rax, 6
0x1400d8b0b  shl     rax, 3
0x1400d8b0f  cmp     r8, rax
0x1400d8b12  jz      short loc_1400D8B37
0x1400d8b14  mov     edi, 0C000000Dh
0x1400d8b19  mov     r8d, 1C9h
0x1400d8b1f  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8b26  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8b2d  call    VidTraceErrorInternal0
0x1400d8b32  jmp     loc_1400D9411
0x1400d8b37  cmp     [r13+50h], rbx
0x1400d8b3b  jnz     short loc_1400D8B47
0x1400d8b3d  cmp     [r13+58h], rbx
0x1400d8b41  jz      loc_1400D8CF9
0x1400d8b47  test    dl, 8
0x1400d8b4a  jnz     loc_1400D8CF9
0x1400d8b50  mov     edi, 0C000000Dh
0x1400d8b55  mov     eax, cs:dword_140064110
0x1400d8b5b  cmp     eax, 2
0x1400d8b5e  jbe     loc_1400D9411
0x1400d8b64  mov     edx, 100h
0x1400d8b69  lea     rcx, dword_140064110
0x1400d8b70  call    _tlgKeywordOn
0x1400d8b75  test    al, al
0x1400d8b77  jz      loc_1400D9411
0x1400d8b7d  lea     rdx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8b84  lea     rcx, [rsp+1F8h+var_128]
0x1400d8b8c  call    _tlgCreate1Sz_char
0x1400d8b91  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8b98  lea     rcx, [rsp+1F8h+var_118]
0x1400d8ba0  call    _tlgCreate1Sz_char
0x1400d8ba5  mov     dword ptr [rsp+1F8h+var_1B8], 1DDh
0x1400d8bad  lea     rax, [rsp+1F8h+var_1B8]
0x1400d8bb2  mov     [rsp+1F8h+var_108], rax
0x1400d8bba  mov     [rsp+1F8h+var_100], 4
0x1400d8bc6  mov     dword ptr [rsp+1F8h+var_1A8], edi
0x1400d8bca  lea     rax, [rsp+1F8h+var_1A8]
0x1400d8bcf  mov     [rsp+1F8h+var_F8], rax
0x1400d8bd7  mov     [rsp+1F8h+var_F0], 4
0x1400d8be3  lea     rax, [r14+290h]
0x1400d8bea  mov     [rsp+1F8h+var_E8], rax
0x1400d8bf2  lea     rax, [rsp+1F8h+var_C0]
0x1400d8bfa  mov     [rsp+1F8h+var_D8], rax
0x1400d8c02  mov     rax, [r14+80h]
0x1400d8c09  mov     [rsp+1F8h+var_C8], rax
0x1400d8c11  movzx   eax, word ptr [r14+78h]
0x1400d8c16  mov     [rsp+1F8h+var_C0], eax
0x1400d8c1d  mov     rax, [r14+288h]
0x1400d8c24  mov     [rsp+1F8h+var_190], rax
0x1400d8c29  lea     rax, [rsp+1F8h+var_190]
0x1400d8c2e  mov     [rsp+1F8h+var_B8], rax
0x1400d8c36  mov     rax, [r9]
0x1400d8c39  mov     [rsp+1F8h+var_188], rax
0x1400d8c3e  lea     rax, [rsp+1F8h+var_188]
0x1400d8c43  mov     [rsp+1F8h+var_A8], rax
0x1400d8c4b  mov     [rsp+1F8h+var_A0], 8
0x1400d8c57  mov     rax, [r13+50h]
0x1400d8c5b  mov     [rsp+1F8h+var_180], rax
0x1400d8c60  lea     rax, [rsp+1F8h+var_180]
0x1400d8c65  mov     [rsp+1F8h+var_98], rax
0x1400d8c6d  mov     [rsp+1F8h+var_90], 8
0x1400d8c79  mov     rax, [r13+58h]
0x1400d8c7d  mov     [rsp+1F8h+var_1A0], rax
0x1400d8c82  lea     rax, [rsp+1F8h+var_1A0]
0x1400d8c87  mov     [rsp+1F8h+var_88], rax
0x1400d8c8f  mov     [rsp+1F8h+var_80], 8
0x1400d8c9b  lea     rax, [rsp+1F8h+var_148]
0x1400d8ca3  mov     [rsp+1F8h+var_1D0], rax
0x1400d8ca8  mov     dword ptr [rsp+1F8h+var_1D8], 0Dh
0x1400d8cb0  lea     rdx, byte_140058845
0x1400d8cb7  mov     [rsp+1F8h+var_E0], 10h
0x1400d8cc3  mov     [rsp+1F8h+var_D0], 2
0x1400d8ccf  mov     [rsp+1F8h+var_B0], 8
0x1400d8cdb  mov     [rsp+1F8h+var_BC], ebx
0x1400d8ce2  xor     r9d, r9d
0x1400d8ce5  xor     r8d, r8d
0x1400d8ce8  lea     rcx, dword_140064110
0x1400d8cef  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d8cf4  jmp     loc_1400D9411
0x1400d8cf9  mov     r13, rbx
0x1400d8cfc  mov     rax, [rsi+30h]
0x1400d8d00  test    rax, rax
0x1400d8d03  jnz     short loc_1400D8D1D
0x1400d8d05  cmp     [rsi+38h], rbx
0x1400d8d09  jnz     short loc_1400D8D14
0x1400d8d0b  cmp     [rsi+40h], bl
0x1400d8d0e  jz      loc_1400D8ED1
0x1400d8d14  test    rax, rax
0x1400d8d17  jz      loc_1400D93F0
0x1400d8d1d  mov     r9, [rsi+38h]
0x1400d8d21  test    r9, r9
0x1400d8d24  jz      loc_1400D93F0
0x1400d8d2a  movzx   r8d, byte ptr [rsi+40h]
0x1400d8d2f  test    r8b, r8b
0x1400d8d32  jz      loc_1400D93F0
0x1400d8d38  test    dl, 1
0x1400d8d3b  jnz     short loc_1400D8D60
0x1400d8d3d  mov     edi, 0C00000BBh
0x1400d8d42  mov     r8d, 1FFh
0x1400d8d48  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8d4f  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8d56  call    VidTraceErrorInternal0
0x1400d8d5b  jmp     loc_1400D940E
0x1400d8d60  test    dl, 8
0x1400d8d63  jnz     short loc_1400D8D88
0x1400d8d65  mov     edi, 0C000000Dh
0x1400d8d6a  mov     r8d, 209h
0x1400d8d70  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8d77  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8d7e  call    VidTraceErrorInternal0
0x1400d8d83  jmp     loc_1400D940E
0x1400d8d88  mov     ecx, [r14+18h]
0x1400d8d8c  shr     rcx, 9
0x1400d8d90  and     ecx, 0Fh
0x1400d8d93  jz      loc_1400D8EC9
0x1400d8d99  mov     al, [r14+20h]
0x1400d8d9d  and     al, 3
0x1400d8d9f  cmp     al, 1
0x1400d8da1  jz      loc_1400D8EC9
0x1400d8da7  cmp     r8, rcx
0x1400d8daa  jz      short loc_1400D8DCF
0x1400d8dac  mov     edi, 0C000000Dh
0x1400d8db1  mov     r8d, 224h
0x1400d8db7  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8dbe  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8dc5  call    VidTraceErrorInternal0
0x1400d8dca  jmp     loc_1400D940E
0x1400d8dcf  mov     cl, r8b
0x1400d8dd2  mov     r8d, 1
0x1400d8dd8  shl     r8, cl
0x1400d8ddb  mov     r13, rsi
0x1400d8dde  mov     rax, [rsi]
0x1400d8de1  dec     rax
0x1400d8de4  add     rax, r8
0x1400d8de7  xor     edx, edx
0x1400d8de9  div     r8
0x1400d8dec  lea     rcx, [rax+3Fh]
0x1400d8df0  shr     rcx, 6
0x1400d8df4  shl     rcx, 3
0x1400d8df8  cmp     r9, rcx
0x1400d8dfb  jz      short loc_1400D8E20
0x1400d8dfd  mov     edi, 0C000000Dh
0x1400d8e02  mov     r8d, 232h
0x1400d8e08  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8e0f  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8e16  call    VidTraceErrorInternal0
0x1400d8e1b  jmp     loc_1400D9411
0x1400d8e20  xor     r9d, r9d
0x1400d8e23  lea     r8d, [r9+40h]
0x1400d8e27  mov     rdx, rax
0x1400d8e2a  lea     rcx, [rsp+1F8h+var_170]
0x1400d8e32  call    VsmmBitmapSetup
0x1400d8e37  mov     edi, eax
0x1400d8e39  test    eax, eax
0x1400d8e3b  jns     short loc_1400D8E5B
0x1400d8e3d  mov     r8d, 240h
0x1400d8e43  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8e4a  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8e51  call    VidTraceErrorInternal0
0x1400d8e56  jmp     loc_1400D9411
0x1400d8e5b  mov     r8, [rsi+38h]
0x1400d8e5f  mov     rdx, [rsi+30h]
0x1400d8e63  test    r8, r8
0x1400d8e66  jz      short loc_1400D8E79
0x1400d8e68  test    dl, 7
0x1400d8e6b  jz      short loc_1400D8E79
0x1400d8e6d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400d8e74  nop     dword ptr [rax+rax+00h]
0x1400d8e79  mov     rcx, [rsp+1F8h+var_170+8]; void *
0x1400d8e81  call    RtlCopyFromUser
0x1400d8e86  nop
0x1400d8e87  lea     r13, [rsp+1F8h+var_170]
0x1400d8e8f  jmp     short loc_1400D8EC9
0x1400d8e91  mov     edi, eax
0x1400d8e93  mov     r8d, 24Fh
0x1400d8e99  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8ea0  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8ea7  call    VidTraceErrorInternal0
0x1400d8eac  xor     ebx, ebx
0x1400d8eae  mov     [rsp+1F8h+var_1C8], bl
0x1400d8eb2  mov     r13, [rsp+1F8h+var_1A0]
0x1400d8eb7  mov     r14, [rsp+1F8h+var_180]
0x1400d8ebc  mov     rsi, r13
0x1400d8ebf  mov     r12, [rsp+1F8h+var_190]
0x1400d8ec4  jmp     loc_1400D9416
0x1400d8ec9  mov     [rsi+30h], rbx
0x1400d8ecd  mov     [rsi+38h], rbx
0x1400d8ed1  mov     rax, [rsi+18h]
0x1400d8ed5  cmp     rax, [rsi+8]
0x1400d8ed9  jnb     loc_1400D93CD
0x1400d8edf  test    rax, 1FFh
0x1400d8ee5  setnz   cl
0x1400d8ee8  test    rax, 3FFFFh
0x1400d8eee  setnz   al
0x1400d8ef1  test    al, cl
0x1400d8ef3  jnz     loc_1400D93CD
0x1400d8ef9  lea     rcx, [r14+0E98h]
0x1400d8f00  call    VidObjectLockAcquireExclusive
0x1400d8f05  mov     [rsp+1F8h+var_1C8], 1
0x1400d8f0a  mov     rax, [rsp+1F8h+var_178]
0x1400d8f12  test    byte ptr [rax], 1
0x1400d8f15  jz      short loc_1400D8F4D
0x1400d8f17  movzx   eax, byte ptr [rsi+41h]
0x1400d8f1b  cmp     [r14+rax*8+2318h], rbx
0x1400d8f23  jz      short loc_1400D8F4D
0x1400d8f25  mov     edi, 0C000000Dh
0x1400d8f2a  mov     r8d, 277h
0x1400d8f30  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8f37  lea     rcx, aVsmmcreatememo_0; "VsmmCreateMemoryBlock"
0x1400d8f3e  call    VidTraceErrorInternal0
0x1400d8f43  mov     r13, [rsp+1F8h+var_1B8]
0x1400d8f48  jmp     loc_1400D9411
0x1400d8f4d  test    r12, r12
0x1400d8f50  jz      loc_1400D9092
  ... truncated ...
```
