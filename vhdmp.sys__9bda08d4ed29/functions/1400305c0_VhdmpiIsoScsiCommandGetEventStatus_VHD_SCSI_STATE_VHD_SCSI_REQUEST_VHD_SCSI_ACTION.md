# VhdmpiIsoScsiCommandGetEventStatus(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x1400305c0`
- end: `0x1400309a3`
- name: `?VhdmpiIsoScsiCommandGetEventStatus@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `995`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140023980`
- `0x1400304e8`
- `0x1400305c0`
- `0x140036284`
- `0x14005de00`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003067a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003067a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400308ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400306f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030907`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400306f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030907`

## string_xrefs

- `0x14003077b`: `VhdmpiIsoScsiCommandGetEventStatus: media arrival`
- `0x14003078d`: `VhdmpiIsoScsiCommandGetEventStatus`
- `0x1400307d7`: `VhdmpiIsoScsiCommandGetEventStatus: media removal`

## pseudocode

```c
unsigned __int8 __fastcall VhdmpiIsoScsiCommandGetEventStatus(
        KSPIN_LOCK *a1,
        struct VHD_SCSI_REQUEST *a2,
        struct VHD_SCSI_ACTION *a3)
{
  unsigned int v3; // edi
  __int64 v5; // rcx
  unsigned __int16 v8; // ax
  unsigned int v9; // esi
  unsigned __int8 v10; // r14
  char *v11; // r12
  char v12; // bl
  char v13; // al
  char v14; // bl
  char v15; // di
  KIRQL v16; // al
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  bool v20; // zf
  char v21; // cl
  unsigned int inited; // eax
  unsigned int v23; // esi
  unsigned int v24; // edi
  __int64 v25; // rbx
  char v26; // al
  unsigned int v27; // esi
  unsigned int v28; // eax
  const struct _NOTIFICATION_BUSY_STATUS *v29; // rdx
  unsigned int v30; // esi
  __int64 v31; // rdi
  char *v32; // rcx
  unsigned int v33; // eax
  KIRQL v34; // al
  char v35; // dl
  unsigned __int8 result; // al
  _DWORD Src[4]; // [rsp+30h] [rbp-10h] BYREF
  int v38; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v5 = *(_QWORD *)a2;
  Src[0] = 0;
  v8 = __ROR2__(*(_WORD *)(v5 + 7), 8);
  v9 = v8;
  if ( (unsigned int)v8 <= *((_DWORD *)a2 + 4) )
  {
    v11 = (char *)*((_QWORD *)a2 + 1);
    v12 = *(_BYTE *)(v5 + 1);
    LOBYTE(v38) = *(_BYTE *)(v5 + 4);
    memset(v11, 0, v8);
    if ( (v12 & 1) == 0 )
    {
      *((_BYTE *)a2 + 37) = 2;
      v10 = 4;
      *(_OWORD *)((char *)a2 + 42) = 0;
      *((_WORD *)a2 + 29) = 0;
      *(_WORD *)((char *)a2 + 41) = 28673;
      v13 = *((_BYTE *)a2 + 44) & 0xF5;
      *((_BYTE *)a2 + 49) = 10;
      *((_BYTE *)a2 + 54) = 36;
      *((_BYTE *)a2 + 44) = v13 | 5;
      goto LABEL_50;
    }
    v14 = v38;
    v15 = v38 & 0x10;
    if ( (v38 & 0x10) == 0 )
      goto LABEL_27;
    v38 = 0;
    v16 = KeAcquireSpinLockRaiseToDpc(a1 + 10);
    v17 = *((_DWORD *)a1 + 28);
    if ( !v17 )
    {
LABEL_15:
      KeReleaseSpinLock(a1 + 10, v16);
      if ( v38 )
      {
        inited = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 4u);
        v23 = v9 - inited;
        v24 = inited;
        if ( v23 > 4 )
          v23 = 4;
        memmove(&v11[inited], Src, v23);
        v3 = v23 + v24;
        if ( (Src[0] & 0xF) == 2 )
        {
          if ( (unsigned int)dword_1400876D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
            TraceEvents(
              "VhdmpiIsoScsiCommandGetEventStatus",
              0x1D5u,
              5u,
              0x20u,
              "VhdmpiIsoScsiCommandGetEventStatus: media arrival");
        }
        else if ( (Src[0] & 0xF) == 3
               && (unsigned int)dword_1400876D0 > 5
               && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 32) )
        {
          TraceEvents(
            "VhdmpiIsoScsiCommandGetEventStatus",
            0x1DAu,
            5u,
            0x20u,
            "VhdmpiIsoScsiCommandGetEventStatus: media removal");
        }
        goto LABEL_49;
      }
LABEL_27:
      if ( (v14 & 2) != 0 )
      {
        v25 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 1u);
LABEL_29:
        HIWORD(v38) = 0;
        v26 = *((_BYTE *)a1 + 108) << 7;
        v27 = v9 - v25;
        LOBYTE(v38) = 0;
        BYTE1(v38) = v26;
        if ( v27 > 4 )
          v27 = 4;
        memmove(&v11[v25], &v38, v27);
        v3 = v27 + v25;
        goto LABEL_49;
      }
      if ( (v14 & 4) != 0 )
      {
        v28 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 2u);
        v29 = (const struct _NOTIFICATION_BUSY_STATUS *)&ISOGetEventStatusPowerStatus;
      }
      else
      {
        if ( (v14 & 8) != 0 )
        {
          v25 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 3u);
          goto LABEL_29;
        }
        if ( v15 )
        {
          v33 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 4u);
          v30 = v9 - v33;
          v31 = v33;
          if ( v30 > 4 )
            v30 = 4;
          v34 = KeAcquireSpinLockRaiseToDpc(a1 + 10);
          v35 = *((_BYTE *)a1 + 116);
          LOBYTE(Src[0]) = 0;
          HIWORD(Src[0]) = 0;
          BYTE1(Src[0]) = *((_BYTE *)a1 + 117) & 1 | (2 * (v35 & 1));
          KeReleaseSpinLock(a1 + 10, v34);
          v32 = &v11[v31];
          v29 = (const struct _NOTIFICATION_BUSY_STATUS *)Src;
          goto LABEL_37;
        }
        if ( (v14 & 0x20) != 0 )
        {
          v25 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 5u);
          goto LABEL_29;
        }
        if ( (v14 & 0x40) == 0 )
        {
          v3 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 2u, 1u, 0);
          goto LABEL_49;
        }
        v28 = VhdmpiIsoInitEventHeader((unsigned __int8 *)v11, v9, 6u, 0, 6u);
        v29 = &ISOGetEventStatusBusyStatus;
      }
      v30 = v9 - v28;
      LODWORD(v31) = v28;
      if ( v30 > 4 )
        v30 = 4;
      v32 = &v11[v28];
LABEL_37:
      memmove(v32, v29, v30);
      v3 = v30 + v31;
LABEL_49:
      v10 = 1;
      goto LABEL_50;
    }
    v38 = *((_DWORD *)a1 + 28);
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 == 1;
        v21 = BYTE1(Src[0]);
        if ( v20 )
        {
          v21 = BYTE1(Src[0]) & 0xFD;
          *((_BYTE *)a1 + 117) = 1;
          *((_DWORD *)a1 + 28) = 1;
          *((_DWORD *)a3 + 6) |= 1u;
          LOBYTE(Src[0]) = 3;
LABEL_14:
          BYTE1(Src[0]) = v21 & 0xFE | *((_BYTE *)a1 + 117) & 1;
          goto LABEL_15;
        }
      }
      else
      {
        v21 = BYTE1(Src[0]) & 0xFD;
        LOBYTE(Src[0]) = 3;
      }
    }
    else
    {
      v21 = BYTE1(Src[0]) | 2;
      LOBYTE(Src[0]) = 2;
      *((_WORD *)a1 + 58) = 1;
    }
    *((_DWORD *)a1 + 28) = 0;
    goto LABEL_14;
  }
  v10 = 18;
LABEL_50:
  result = v10;
  *((_DWORD *)a2 + 4) = v3;
  return result;
}

```

## disassembly

```asm
0x1400305c0  mov     [rsp-38h+arg_0], rbx
0x1400305c5  push    rbp
0x1400305c6  push    rsi
0x1400305c7  push    rdi
0x1400305c8  push    r12
0x1400305ca  push    r13
0x1400305cc  push    r14
0x1400305ce  push    r15
0x1400305d0  mov     rbp, rsp
0x1400305d3  sub     rsp, 40h
0x1400305d7  xor     edi, edi
0x1400305d9  mov     r13, rcx
0x1400305dc  mov     rcx, [rdx]
0x1400305df  mov     r14, r8
0x1400305e2  mov     r15, rdx
0x1400305e5  mov     [rbp+Src], edi
0x1400305e8  movzx   eax, word ptr [rcx+7]
0x1400305ec  ror     ax, 8
0x1400305f0  movzx   esi, ax
0x1400305f3  cmp     esi, [rdx+10h]
0x1400305f6  jbe     short loc_140030600
0x1400305f8  mov     r14b, 12h
0x1400305fb  jmp     loc_140030983
0x140030600  mov     r12, [rdx+8]
0x140030604  mov     r8, rsi; Size
0x140030607  mov     al, [rcx+4]
0x14003060a  xor     edx, edx; Val
0x14003060c  mov     bl, [rcx+1]
0x14003060f  mov     rcx, r12; void *
0x140030612  mov     byte ptr [rbp+arg_18], al
0x140030615  call    memset
0x14003061a  test    bl, 1
0x14003061d  jnz     short loc_14003065B
0x14003061f  mov     byte ptr [r15+25h], 2
0x140030624  xor     eax, eax
0x140030626  xorps   xmm0, xmm0
0x140030629  mov     r14d, 4
0x14003062f  movups  xmmword ptr [r15+2Ah], xmm0
0x140030634  mov     [r15+3Ah], ax
0x140030639  mov     word ptr [r15+29h], 7001h
0x140030640  mov     al, [r15+2Ch]
0x140030644  and     al, 0F5h
0x140030646  mov     byte ptr [r15+31h], 0Ah
0x14003064b  or      al, 5
0x14003064d  mov     byte ptr [r15+36h], 24h ; '$'
0x140030652  mov     [r15+2Ch], al
0x140030656  jmp     loc_140030983
0x14003065b  mov     bl, byte ptr [rbp+arg_18]
0x14003065e  mov     dil, bl
0x140030661  mov     [rbp+arg_8], 1
0x140030665  and     dil, 10h
0x140030669  jz      loc_1400307E0
0x14003066f  lea     rcx, [r13+50h]; SpinLock
0x140030673  mov     [rbp+arg_18], 0
0x14003067a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030681  nop     dword ptr [rax+rax+00h]
0x140030686  mov     ecx, [r13+70h]
0x14003068a  xor     r8d, r8d
0x14003068d  mov     dl, al; NewIrql
0x14003068f  test    ecx, ecx
0x140030691  jz      short loc_1400306F2
0x140030693  mov     [rbp+arg_18], ecx
0x140030696  sub     ecx, 1
0x140030699  jz      short loc_1400306CF
0x14003069b  sub     ecx, 1
0x14003069e  jz      short loc_1400306C3
0x1400306a0  cmp     ecx, 1
0x1400306a3  mov     cl, byte ptr [rbp+Src+1]
0x1400306a6  jnz     short loc_1400306E0
0x1400306a8  and     cl, 0FDh
0x1400306ab  mov     byte ptr [r13+75h], 1
0x1400306b0  mov     dword ptr [r13+70h], 1
0x1400306b8  or      dword ptr [r14+18h], 1
0x1400306bd  mov     byte ptr [rbp+Src], 3
0x1400306c1  jmp     short loc_1400306E4
0x1400306c3  mov     cl, byte ptr [rbp+Src+1]
0x1400306c6  and     cl, 0FDh
0x1400306c9  mov     byte ptr [rbp+Src], 3
0x1400306cd  jmp     short loc_1400306E0
0x1400306cf  mov     cl, byte ptr [rbp+Src+1]
0x1400306d2  or      cl, 2
0x1400306d5  mov     byte ptr [rbp+Src], 2
0x1400306d9  mov     word ptr [r13+74h], 1
0x1400306e0  mov     [r13+70h], r8d
0x1400306e4  mov     al, [r13+75h]
0x1400306e8  and     cl, 0FEh
0x1400306eb  and     al, 1
0x1400306ed  or      al, cl
0x1400306ef  mov     byte ptr [rbp+Src+1], al
0x1400306f2  lea     rcx, [r13+50h]; SpinLock
0x1400306f6  call    cs:__imp_KeReleaseSpinLock
0x1400306fd  nop     dword ptr [rax+rax+00h]
0x140030702  cmp     [rbp+arg_18], 0
0x140030706  jz      loc_1400307E0
0x14003070c  mov     r8d, 6; unsigned __int16
0x140030712  xor     r9d, r9d; unsigned __int8
0x140030715  mov     edx, esi; unsigned int
0x140030717  mov     rcx, r12; unsigned __int8 *
0x14003071a  lea     r14d, [r8-2]
0x14003071e  mov     byte ptr [rsp+40h+var_20], r14b; unsigned __int8
0x140030723  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x140030728  sub     esi, eax
0x14003072a  mov     ecx, eax
0x14003072c  cmp     esi, r14d
0x14003072f  mov     edi, eax
0x140030731  lea     rdx, [rbp+Src]; Src
0x140030735  cmova   esi, r14d
0x140030739  add     rcx, r12; void *
0x14003073c  mov     r8d, esi; Size
0x14003073f  call    memmove
0x140030744  mov     al, byte ptr [rbp+Src]
0x140030747  add     edi, esi
0x140030749  and     al, 0Fh
0x14003074b  cmp     al, 2
0x14003074d  jnz     short loc_1400307A2
0x14003074f  mov     eax, cs:dword_1400876D0
0x140030755  cmp     eax, 5
0x140030758  jbe     loc_14003097F
0x14003075e  lea     edx, [r14+1Ch]
0x140030762  lea     rcx, dword_1400876D0
0x140030769  call    _tlgKeywordOn
0x14003076e  test    al, al
0x140030770  jz      loc_14003097F
0x140030776  mov     edx, 1D5h; int
0x14003077b  lea     rax, aVhdmpiisoscsic_3; "VhdmpiIsoScsiCommandGetEventStatus: med"...
0x140030782  mov     r9d, 20h ; ' '; int
0x140030788  mov     [rsp+40h+var_20], rax; char *
0x14003078d  lea     rcx, aVhdmpiisoscsic; "VhdmpiIsoScsiCommandGetEventStatus"
0x140030794  lea     r8d, [r9-1Bh]; int
0x140030798  call    TraceEvents
0x14003079d  jmp     loc_14003097F
0x1400307a2  cmp     al, 3
0x1400307a4  jnz     loc_14003097F
0x1400307aa  mov     eax, cs:dword_1400876D0
0x1400307b0  cmp     eax, 5
0x1400307b3  jbe     loc_14003097F
0x1400307b9  mov     edx, 20h ; ' '
0x1400307be  lea     rcx, dword_1400876D0
0x1400307c5  call    _tlgKeywordOn
0x1400307ca  test    al, al
0x1400307cc  jz      loc_14003097F
0x1400307d2  mov     edx, 1DAh
0x1400307d7  lea     rax, aVhdmpiisoscsic_1; "VhdmpiIsoScsiCommandGetEventStatus: med"...
0x1400307de  jmp     short loc_140030782
0x1400307e0  mov     edx, esi; unsigned int
0x1400307e2  mov     rcx, r12; unsigned __int8 *
0x1400307e5  test    bl, 2
0x1400307e8  jz      short loc_14003083F
0x1400307ea  mov     r8d, 6; unsigned __int16
0x1400307f0  mov     byte ptr [rsp+40h+var_20], 1; unsigned __int8
0x1400307f5  xor     r9d, r9d; unsigned __int8
0x1400307f8  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x1400307fd  mov     ebx, eax
0x1400307ff  mov     r14d, 4
0x140030805  movzx   eax, cs:word_1400680BE
0x14003080c  mov     word ptr [rbp+arg_18+2], ax
0x140030810  lea     rcx, [r12+rbx]; void *
0x140030814  mov     al, [r13+6Ch]
0x140030818  lea     rdx, [rbp+arg_18]; Src
0x14003081c  shl     al, 7
0x14003081f  sub     esi, ebx
0x140030821  cmp     esi, r14d
0x140030824  mov     byte ptr [rbp+arg_18], 0
0x140030828  mov     byte ptr [rbp+arg_18+1], al
0x14003082b  cmova   esi, r14d
0x14003082f  mov     r8d, esi; Size
0x140030832  call    memmove
0x140030837  lea     edi, [rsi+rbx]
0x14003083a  jmp     loc_14003097F
0x14003083f  mov     r14d, 4
0x140030845  test    r14b, bl
0x140030848  jz      short loc_140030881
0x14003084a  lea     r8d, [r14+2]; unsigned __int16
0x14003084e  mov     byte ptr [rsp+40h+var_20], 2; unsigned __int8
0x140030853  xor     r9d, r9d; unsigned __int8
0x140030856  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003085b  lea     rdx, ?ISOGetEventStatusPowerStatus@@3U_NOTIFICATION_POWER_STATUS@@B; Src
0x140030862  sub     esi, eax
0x140030864  mov     ecx, eax
0x140030866  cmp     esi, r14d
0x140030869  mov     edi, eax
0x14003086b  cmova   esi, r14d
0x14003086f  add     rcx, r12; void *
0x140030872  mov     r8d, esi; Size
0x140030875  call    memmove
0x14003087a  add     edi, esi
0x14003087c  jmp     loc_14003097F
0x140030881  test    bl, 8
0x140030884  jz      short loc_1400308A7
0x140030886  mov     r8d, 6; unsigned __int16
0x14003088c  mov     byte ptr [rsp+40h+var_20], 3; unsigned __int8
0x140030891  xor     r9d, r9d; unsigned __int8
0x140030894  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x140030899  mov     ebx, eax
0x14003089b  movzx   eax, cs:word_1400680BE
0x1400308a2  jmp     loc_14003080C
0x1400308a7  test    dil, dil
0x1400308aa  jz      short loc_140030920
0x1400308ac  mov     r8d, 6; unsigned __int16
0x1400308b2  mov     byte ptr [rsp+40h+var_20], r14b; unsigned __int8
0x1400308b7  xor     r9d, r9d; unsigned __int8
0x1400308ba  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x1400308bf  sub     esi, eax
0x1400308c1  mov     edi, eax
0x1400308c3  cmp     esi, r14d
0x1400308c6  lea     rcx, [r13+50h]; SpinLock
0x1400308ca  cmova   esi, r14d
0x1400308ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400308d5  nop     dword ptr [rax+rax+00h]
0x1400308da  mov     dl, [r13+74h]
0x1400308de  lea     rcx, [r13+50h]; SpinLock
0x1400308e2  mov     r8b, al
0x1400308e5  mov     byte ptr [rbp+Src], 0
0x1400308e9  movzx   eax, cs:word_1400680C2
0x1400308f0  and     dl, 1
0x1400308f3  mov     word ptr [rbp+Src+2], ax
0x1400308f7  add     dl, dl
0x1400308f9  mov     al, [r13+75h]
0x1400308fd  and     al, 1
0x1400308ff  or      dl, al
0x140030901  mov     byte ptr [rbp+Src+1], dl
0x140030904  mov     dl, r8b; NewIrql
0x140030907  call    cs:__imp_KeReleaseSpinLock
0x14003090e  nop     dword ptr [rax+rax+00h]
0x140030913  lea     rcx, [r12+rdi]
0x140030917  lea     rdx, [rbp+Src]
0x14003091b  jmp     loc_140030872
0x140030920  test    bl, 20h
0x140030923  jz      short loc_140030946
0x140030925  mov     r8d, 6; unsigned __int16
0x14003092b  mov     byte ptr [rsp+40h+var_20], 5; unsigned __int8
0x140030930  xor     r9d, r9d; unsigned __int8
0x140030933  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x140030938  mov     ebx, eax
0x14003093a  movzx   eax, cs:word_1400680BE
0x140030941  jmp     loc_14003080C
0x140030946  test    bl, 40h
0x140030949  jz      short loc_14003096A
0x14003094b  mov     r8d, 6; unsigned __int16
0x140030951  xor     r9d, r9d; unsigned __int8
0x140030954  mov     byte ptr [rsp+40h+var_20], r8b; unsigned __int8
0x140030959  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003095e  lea     rdx, ?ISOGetEventStatusBusyStatus@@3U_NOTIFICATION_BUSY_STATUS@@B; _NOTIFICATION_BUSY_STATUS const ISOGetEventStatusBusyStatus
0x140030965  jmp     loc_140030862
0x14003096a  mov     r8d, 2; unsigned __int16
0x140030970  mov     byte ptr [rsp+40h+var_20], 0; unsigned __int8
0x140030975  mov     r9b, 1; unsigned __int8
0x140030978  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003097d  mov     edi, eax
0x14003097f  mov     r14b, [rbp+arg_8]
0x140030983  mov     rbx, [rsp+40h+arg_0]
0x14003098b  mov     al, r14b
0x14003098e  mov     [r15+10h], edi
0x140030992  add     rsp, 40h
0x140030996  pop     r15
0x140030998  pop     r14
0x14003099a  pop     r13
0x14003099c  pop     r12
0x14003099e  pop     rdi
0x14003099f  pop     rsi
0x1400309a0  pop     rbp
0x1400309a1  retn
```
