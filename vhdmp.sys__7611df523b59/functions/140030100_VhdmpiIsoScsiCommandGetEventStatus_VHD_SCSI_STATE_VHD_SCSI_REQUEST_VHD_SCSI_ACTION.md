# VhdmpiIsoScsiCommandGetEventStatus(VHD_SCSI_STATE *,VHD_SCSI_REQUEST *,VHD_SCSI_ACTION *)

- ea: `0x140030100`
- end: `0x1400304e3`
- name: `?VhdmpiIsoScsiCommandGetEventStatus@@YAEPEAUVHD_SCSI_STATE@@PEAUVHD_SCSI_REQUEST@@PEAUVHD_SCSI_ACTION@@@Z`
- size: `995`
- prototype: `unsigned __int8 __fastcall(struct VHD_SCSI_STATE *, struct VHD_SCSI_REQUEST *, struct VHD_SCSI_ACTION *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140023560`
- `0x140030028`
- `0x140030100`
- `0x140035e94`
- `0x14005da00`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400301ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003040e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400301ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003040e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030236`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030447`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030236`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030447`

## string_xrefs

- `0x1400302bb`: `VhdmpiIsoScsiCommandGetEventStatus: media arrival`
- `0x1400302cd`: `VhdmpiIsoScsiCommandGetEventStatus`
- `0x140030317`: `VhdmpiIsoScsiCommandGetEventStatus: media removal`

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
          if ( (unsigned int)dword_140087708 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
            TraceEvents(
              "VhdmpiIsoScsiCommandGetEventStatus",
              0x1D5u,
              5u,
              0x20u,
              "VhdmpiIsoScsiCommandGetEventStatus: media arrival");
        }
        else if ( (Src[0] & 0xF) == 3
               && (unsigned int)dword_140087708 > 5
               && (unsigned __int8)tlgKeywordOn(&dword_140087708, 32) )
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
0x140030100  mov     [rsp-38h+arg_0], rbx
0x140030105  push    rbp
0x140030106  push    rsi
0x140030107  push    rdi
0x140030108  push    r12
0x14003010a  push    r13
0x14003010c  push    r14
0x14003010e  push    r15
0x140030110  mov     rbp, rsp
0x140030113  sub     rsp, 40h
0x140030117  xor     edi, edi
0x140030119  mov     r13, rcx
0x14003011c  mov     rcx, [rdx]
0x14003011f  mov     r14, r8
0x140030122  mov     r15, rdx
0x140030125  mov     [rbp+Src], edi
0x140030128  movzx   eax, word ptr [rcx+7]
0x14003012c  ror     ax, 8
0x140030130  movzx   esi, ax
0x140030133  cmp     esi, [rdx+10h]
0x140030136  jbe     short loc_140030140
0x140030138  mov     r14b, 12h
0x14003013b  jmp     loc_1400304C3
0x140030140  mov     r12, [rdx+8]
0x140030144  mov     r8, rsi; Size
0x140030147  mov     al, [rcx+4]
0x14003014a  xor     edx, edx; Val
0x14003014c  mov     bl, [rcx+1]
0x14003014f  mov     rcx, r12; void *
0x140030152  mov     byte ptr [rbp+arg_18], al
0x140030155  call    memset
0x14003015a  test    bl, 1
0x14003015d  jnz     short loc_14003019B
0x14003015f  mov     byte ptr [r15+25h], 2
0x140030164  xor     eax, eax
0x140030166  xorps   xmm0, xmm0
0x140030169  mov     r14d, 4
0x14003016f  movups  xmmword ptr [r15+2Ah], xmm0
0x140030174  mov     [r15+3Ah], ax
0x140030179  mov     word ptr [r15+29h], 7001h
0x140030180  mov     al, [r15+2Ch]
0x140030184  and     al, 0F5h
0x140030186  mov     byte ptr [r15+31h], 0Ah
0x14003018b  or      al, 5
0x14003018d  mov     byte ptr [r15+36h], 24h ; '$'
0x140030192  mov     [r15+2Ch], al
0x140030196  jmp     loc_1400304C3
0x14003019b  mov     bl, byte ptr [rbp+arg_18]
0x14003019e  mov     dil, bl
0x1400301a1  mov     [rbp+arg_8], 1
0x1400301a5  and     dil, 10h
0x1400301a9  jz      loc_140030320
0x1400301af  lea     rcx, [r13+50h]; SpinLock
0x1400301b3  mov     [rbp+arg_18], 0
0x1400301ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400301c1  nop     dword ptr [rax+rax+00h]
0x1400301c6  mov     ecx, [r13+70h]
0x1400301ca  xor     r8d, r8d
0x1400301cd  mov     dl, al; NewIrql
0x1400301cf  test    ecx, ecx
0x1400301d1  jz      short loc_140030232
0x1400301d3  mov     [rbp+arg_18], ecx
0x1400301d6  sub     ecx, 1
0x1400301d9  jz      short loc_14003020F
0x1400301db  sub     ecx, 1
0x1400301de  jz      short loc_140030203
0x1400301e0  cmp     ecx, 1
0x1400301e3  mov     cl, byte ptr [rbp+Src+1]
0x1400301e6  jnz     short loc_140030220
0x1400301e8  and     cl, 0FDh
0x1400301eb  mov     byte ptr [r13+75h], 1
0x1400301f0  mov     dword ptr [r13+70h], 1
0x1400301f8  or      dword ptr [r14+18h], 1
0x1400301fd  mov     byte ptr [rbp+Src], 3
0x140030201  jmp     short loc_140030224
0x140030203  mov     cl, byte ptr [rbp+Src+1]
0x140030206  and     cl, 0FDh
0x140030209  mov     byte ptr [rbp+Src], 3
0x14003020d  jmp     short loc_140030220
0x14003020f  mov     cl, byte ptr [rbp+Src+1]
0x140030212  or      cl, 2
0x140030215  mov     byte ptr [rbp+Src], 2
0x140030219  mov     word ptr [r13+74h], 1
0x140030220  mov     [r13+70h], r8d
0x140030224  mov     al, [r13+75h]
0x140030228  and     cl, 0FEh
0x14003022b  and     al, 1
0x14003022d  or      al, cl
0x14003022f  mov     byte ptr [rbp+Src+1], al
0x140030232  lea     rcx, [r13+50h]; SpinLock
0x140030236  call    cs:__imp_KeReleaseSpinLock
0x14003023d  nop     dword ptr [rax+rax+00h]
0x140030242  cmp     [rbp+arg_18], 0
0x140030246  jz      loc_140030320
0x14003024c  mov     r8d, 6; unsigned __int16
0x140030252  xor     r9d, r9d; unsigned __int8
0x140030255  mov     edx, esi; unsigned int
0x140030257  mov     rcx, r12; unsigned __int8 *
0x14003025a  lea     r14d, [r8-2]
0x14003025e  mov     byte ptr [rsp+40h+var_20], r14b; unsigned __int8
0x140030263  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x140030268  sub     esi, eax
0x14003026a  mov     ecx, eax
0x14003026c  cmp     esi, r14d
0x14003026f  mov     edi, eax
0x140030271  lea     rdx, [rbp+Src]; Src
0x140030275  cmova   esi, r14d
0x140030279  add     rcx, r12; void *
0x14003027c  mov     r8d, esi; Size
0x14003027f  call    memmove
0x140030284  mov     al, byte ptr [rbp+Src]
0x140030287  add     edi, esi
0x140030289  and     al, 0Fh
0x14003028b  cmp     al, 2
0x14003028d  jnz     short loc_1400302E2
0x14003028f  mov     eax, cs:dword_140087708
0x140030295  cmp     eax, 5
0x140030298  jbe     loc_1400304BF
0x14003029e  lea     edx, [r14+1Ch]
0x1400302a2  lea     rcx, dword_140087708
0x1400302a9  call    _tlgKeywordOn
0x1400302ae  test    al, al
0x1400302b0  jz      loc_1400304BF
0x1400302b6  mov     edx, 1D5h; int
0x1400302bb  lea     rax, aVhdmpiisoscsic_3; "VhdmpiIsoScsiCommandGetEventStatus: med"...
0x1400302c2  mov     r9d, 20h ; ' '; int
0x1400302c8  mov     [rsp+40h+var_20], rax; char *
0x1400302cd  lea     rcx, aVhdmpiisoscsic; "VhdmpiIsoScsiCommandGetEventStatus"
0x1400302d4  lea     r8d, [r9-1Bh]; int
0x1400302d8  call    TraceEvents
0x1400302dd  jmp     loc_1400304BF
0x1400302e2  cmp     al, 3
0x1400302e4  jnz     loc_1400304BF
0x1400302ea  mov     eax, cs:dword_140087708
0x1400302f0  cmp     eax, 5
0x1400302f3  jbe     loc_1400304BF
0x1400302f9  mov     edx, 20h ; ' '
0x1400302fe  lea     rcx, dword_140087708
0x140030305  call    _tlgKeywordOn
0x14003030a  test    al, al
0x14003030c  jz      loc_1400304BF
0x140030312  mov     edx, 1DAh
0x140030317  lea     rax, aVhdmpiisoscsic_1; "VhdmpiIsoScsiCommandGetEventStatus: med"...
0x14003031e  jmp     short loc_1400302C2
0x140030320  mov     edx, esi; unsigned int
0x140030322  mov     rcx, r12; unsigned __int8 *
0x140030325  test    bl, 2
0x140030328  jz      short loc_14003037F
0x14003032a  mov     r8d, 6; unsigned __int16
0x140030330  mov     byte ptr [rsp+40h+var_20], 1; unsigned __int8
0x140030335  xor     r9d, r9d; unsigned __int8
0x140030338  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003033d  mov     ebx, eax
0x14003033f  mov     r14d, 4
0x140030345  movzx   eax, cs:word_14006806A
0x14003034c  mov     word ptr [rbp+arg_18+2], ax
0x140030350  lea     rcx, [r12+rbx]; void *
0x140030354  mov     al, [r13+6Ch]
0x140030358  lea     rdx, [rbp+arg_18]; Src
0x14003035c  shl     al, 7
0x14003035f  sub     esi, ebx
0x140030361  cmp     esi, r14d
0x140030364  mov     byte ptr [rbp+arg_18], 0
0x140030368  mov     byte ptr [rbp+arg_18+1], al
0x14003036b  cmova   esi, r14d
0x14003036f  mov     r8d, esi; Size
0x140030372  call    memmove
0x140030377  lea     edi, [rsi+rbx]
0x14003037a  jmp     loc_1400304BF
0x14003037f  mov     r14d, 4
0x140030385  test    r14b, bl
0x140030388  jz      short loc_1400303C1
0x14003038a  lea     r8d, [r14+2]; unsigned __int16
0x14003038e  mov     byte ptr [rsp+40h+var_20], 2; unsigned __int8
0x140030393  xor     r9d, r9d; unsigned __int8
0x140030396  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003039b  lea     rdx, ?ISOGetEventStatusPowerStatus@@3U_NOTIFICATION_POWER_STATUS@@B; Src
0x1400303a2  sub     esi, eax
0x1400303a4  mov     ecx, eax
0x1400303a6  cmp     esi, r14d
0x1400303a9  mov     edi, eax
0x1400303ab  cmova   esi, r14d
0x1400303af  add     rcx, r12; void *
0x1400303b2  mov     r8d, esi; Size
0x1400303b5  call    memmove
0x1400303ba  add     edi, esi
0x1400303bc  jmp     loc_1400304BF
0x1400303c1  test    bl, 8
0x1400303c4  jz      short loc_1400303E7
0x1400303c6  mov     r8d, 6; unsigned __int16
0x1400303cc  mov     byte ptr [rsp+40h+var_20], 3; unsigned __int8
0x1400303d1  xor     r9d, r9d; unsigned __int8
0x1400303d4  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x1400303d9  mov     ebx, eax
0x1400303db  movzx   eax, cs:word_14006806A
0x1400303e2  jmp     loc_14003034C
0x1400303e7  test    dil, dil
0x1400303ea  jz      short loc_140030460
0x1400303ec  mov     r8d, 6; unsigned __int16
0x1400303f2  mov     byte ptr [rsp+40h+var_20], r14b; unsigned __int8
0x1400303f7  xor     r9d, r9d; unsigned __int8
0x1400303fa  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x1400303ff  sub     esi, eax
0x140030401  mov     edi, eax
0x140030403  cmp     esi, r14d
0x140030406  lea     rcx, [r13+50h]; SpinLock
0x14003040a  cmova   esi, r14d
0x14003040e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030415  nop     dword ptr [rax+rax+00h]
0x14003041a  mov     dl, [r13+74h]
0x14003041e  lea     rcx, [r13+50h]; SpinLock
0x140030422  mov     r8b, al
0x140030425  mov     byte ptr [rbp+Src], 0
0x140030429  movzx   eax, cs:word_14006806E
0x140030430  and     dl, 1
0x140030433  mov     word ptr [rbp+Src+2], ax
0x140030437  add     dl, dl
0x140030439  mov     al, [r13+75h]
0x14003043d  and     al, 1
0x14003043f  or      dl, al
0x140030441  mov     byte ptr [rbp+Src+1], dl
0x140030444  mov     dl, r8b; NewIrql
0x140030447  call    cs:__imp_KeReleaseSpinLock
0x14003044e  nop     dword ptr [rax+rax+00h]
0x140030453  lea     rcx, [r12+rdi]
0x140030457  lea     rdx, [rbp+Src]
0x14003045b  jmp     loc_1400303B2
0x140030460  test    bl, 20h
0x140030463  jz      short loc_140030486
0x140030465  mov     r8d, 6; unsigned __int16
0x14003046b  mov     byte ptr [rsp+40h+var_20], 5; unsigned __int8
0x140030470  xor     r9d, r9d; unsigned __int8
0x140030473  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x140030478  mov     ebx, eax
0x14003047a  movzx   eax, cs:word_14006806A
0x140030481  jmp     loc_14003034C
0x140030486  test    bl, 40h
0x140030489  jz      short loc_1400304AA
0x14003048b  mov     r8d, 6; unsigned __int16
0x140030491  xor     r9d, r9d; unsigned __int8
0x140030494  mov     byte ptr [rsp+40h+var_20], r8b; unsigned __int8
0x140030499  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x14003049e  lea     rdx, ?ISOGetEventStatusBusyStatus@@3U_NOTIFICATION_BUSY_STATUS@@B; _NOTIFICATION_BUSY_STATUS const ISOGetEventStatusBusyStatus
0x1400304a5  jmp     loc_1400303A2
0x1400304aa  mov     r8d, 2; unsigned __int16
0x1400304b0  mov     byte ptr [rsp+40h+var_20], 0; unsigned __int8
0x1400304b5  mov     r9b, 1; unsigned __int8
0x1400304b8  call    ?VhdmpiIsoInitEventHeader@@YAKPEAEKGEE@Z; VhdmpiIsoInitEventHeader(uchar *,ulong,ushort,uchar,uchar)
0x1400304bd  mov     edi, eax
0x1400304bf  mov     r14b, [rbp+arg_8]
0x1400304c3  mov     rbx, [rsp+40h+arg_0]
0x1400304cb  mov     al, r14b
0x1400304ce  mov     [r15+10h], edi
0x1400304d2  add     rsp, 40h
0x1400304d6  pop     r15
0x1400304d8  pop     r14
0x1400304da  pop     r13
0x1400304dc  pop     r12
0x1400304de  pop     rdi
0x1400304df  pop     rsi
0x1400304e0  pop     rbp
0x1400304e1  retn
```
