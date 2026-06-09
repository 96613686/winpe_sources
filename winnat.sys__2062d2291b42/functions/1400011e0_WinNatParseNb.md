# WinNatParseNb

- ea: `0x1400011e0`
- end: `0x1400019e4`
- name: `WinNatParseNb`
- size: `2052`
- prototype: `char __fastcall(PNET_BUFFER NetBuffer, __int64 *, char, unsigned __int16)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001120`
- `0x140001190`
- `0x1400020e0`
- `0x14001df6c`
- `0x14001e7d8`

## callees

- `0x1400011e0`
- `0x14000caa0`
- `0x140018c8c`
- `0x14001f320`

## import_xrefs

- `NDIS!NdisGetDataBuffer` at `0x14000123a`
- `NDIS!NdisGetDataBuffer` at `0x140001299`
- `NDIS!NdisGetDataBuffer` at `0x140001307`
- `NDIS!NdisGetDataBuffer` at `0x14000148d`
- `NDIS!NdisGetDataBuffer` at `0x140001564`
- `NDIS!NdisGetDataBuffer` at `0x1400015c5`
- `NDIS!NdisGetDataBuffer` at `0x14000169f`
- `NDIS!NdisGetDataBuffer` at `0x14000176b`
- `NDIS!NdisGetDataBuffer` at `0x1400018af`
- `NDIS!NdisGetDataBuffer` at `0x14000123a`
- `NDIS!NdisGetDataBuffer` at `0x140001299`
- `NDIS!NdisGetDataBuffer` at `0x140001307`
- `NDIS!NdisGetDataBuffer` at `0x14000148d`
- `NDIS!NdisGetDataBuffer` at `0x140001564`
- `NDIS!NdisGetDataBuffer` at `0x1400015c5`
- `NDIS!NdisGetDataBuffer` at `0x14000169f`
- `NDIS!NdisGetDataBuffer` at `0x14000176b`
- `NDIS!NdisGetDataBuffer` at `0x1400018af`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001324`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001507`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001324`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140001507`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400012e6`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14000136a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400016c5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400017f8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400012e6`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14000136a`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400016c5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400017f8`

## pseudocode

```c
char __fastcall WinNatParseNb(PNET_BUFFER NetBuffer, __int64 *a2, char a3, unsigned __int16 a4)
{
  unsigned int v4; // esi
  _BYTE *DataBuffer; // rax
  __int64 v9; // rcx
  char v10; // al
  _BYTE *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned __int8 v15; // al
  ULONG v16; // esi
  ULONG v17; // esi
  char *v18; // r14
  unsigned __int8 v19; // cl
  int v20; // ebp
  __int64 v21; // r8
  _BYTE *v22; // rsi
  char v23; // cl
  __int64 v24; // rdx
  unsigned __int64 v25; // rcx
  char v26; // al
  char v27; // bp
  __int64 v28; // rcx
  _BYTE *v29; // rcx
  int v30; // ecx
  _BYTE *v31; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // rdx
  _WORD *v34; // rdx
  __int16 v35; // ax
  ULONG v36; // edx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  int v41; // ecx
  int v42; // ecx
  PVOID v43; // rax
  char *v44; // rax
  int v45; // ecx
  char v46; // dl
  PVOID v47; // rax
  __int64 v48; // rcx
  char v49; // al
  __int16 *v50; // r14
  ULONG v51; // ebp
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // r8
  _DWORD *v55; // r15
  int v56; // ecx
  int v57; // ebp
  _BYTE *v58; // rax
  char v59; // al
  unsigned int v60; // edx
  __int64 v61; // r8
  _OWORD *v62; // rcx
  __int16 v63; // [rsp+30h] [rbp-88h] BYREF
  __int64 v64; // [rsp+38h] [rbp-80h] BYREF
  __int64 v65; // [rsp+40h] [rbp-78h] BYREF
  _BYTE Storage[40]; // [rsp+48h] [rbp-70h] BYREF

  v4 = a4;
  *((_DWORD *)a2 + 35) = 0;
  v63 = 0;
  v64 = 0;
  DataBuffer = NdisGetDataBuffer(NetBuffer, 1u, 0, 1u, 0);
  if ( !DataBuffer )
    goto LABEL_62;
  *((_DWORD *)a2 + 55) = 0;
  *((_WORD *)a2 + 112) = 0;
  *((_DWORD *)a2 + 53) = 0;
  v10 = *DataBuffer >> 4;
  *((_BYTE *)a2 + 17) = v10;
  if ( v10 == 4 )
  {
    v11 = NdisGetDataBuffer(NetBuffer, 0x14u, (char *)a2 + 18, 4u, 0);
    *a2 = (__int64)v11;
    if ( !v11 )
    {
      v27 = 0;
      goto LABEL_29;
    }
    v15 = 4 * (*v11 & 0xF);
    v16 = v15;
    if ( v15 < 0x14u )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12, v14);
    if ( v16 > NetBuffer->DataLength )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12, v14);
    if ( (_BYTE)v16 != 20 )
    {
      v17 = v16 - 20;
      NdisAdvanceNetBufferDataStart(NetBuffer, 0x14u, 0, 0);
      v18 = (char *)NdisGetDataBuffer(NetBuffer, v17, Storage, 1u, 0);
      NdisRetreatNetBufferDataStart(NetBuffer, 0x14u, 0, 0);
      if ( !v18 )
        goto LABEL_62;
      while ( v17 )
      {
        v59 = *v18;
        if ( (unsigned __int8)*v18 < 2u )
        {
          v60 = 1;
        }
        else
        {
          if ( v17 < 2 )
            goto LABEL_62;
          v60 = (unsigned __int8)v18[1];
        }
        if ( v59 == -119 || v59 == -125 )
        {
          if ( v17 < 3 )
            goto LABEL_62;
          if ( v60 >= 7 )
            goto LABEL_62;
          v61 = v60;
          if ( (unsigned int)(unsigned __int8)v18[2] - 1 <= (unsigned __int64)v60 - 4 )
            goto LABEL_62;
        }
        else
        {
          v61 = v60;
        }
        if ( v17 < v60 )
          goto LABEL_62;
        v18 += v61;
        v17 -= v60;
      }
    }
    v19 = 4 * (*(_BYTE *)*a2 & 0xF);
    v20 = v19;
    if ( NetBuffer->DataLength < v19 )
    {
      v27 = 0;
      goto LABEL_29;
    }
    NdisAdvanceNetBufferDataStart(NetBuffer, v19, 0, 0);
    v21 = *a2;
    v22 = a2 + 2;
    *((_BYTE *)a2 + 16) = *(_BYTE *)(*a2 + 9);
    *((_BYTE *)a2 + 150) = *(_BYTE *)(v21 + 8);
    *((_BYTE *)a2 + 149) = 20;
    *((_DWORD *)a2 + 35) = v20;
    *((_DWORD *)a2 + 55) = *(unsigned __int16 *)(v21 + 4);
    v23 = *((_BYTE *)a2 + 212) ^ (*((_BYTE *)a2 + 212) ^ (2 * (*(_WORD *)(v21 + 6) >> 5))) & 2;
    *((_BYTE *)a2 + 212) = v23;
    v24 = *(unsigned __int16 *)(v21 + 6);
    LOWORD(v24) = (unsigned __int16)v24 >> 6;
    LOBYTE(v24) = v23 ^ (v23 ^ (4 * v24)) & 4;
    *((_BYTE *)a2 + 212) = v24;
    v25 = *(unsigned __int16 *)(v21 + 6);
    if ( (__ROR2__(v25 & 0xFF1F, 8) & 0x1FFF) != 0 || (v25 & 0x20) != 0 )
    {
      LOBYTE(v24) = v24 | 1;
      *((_BYTE *)a2 + 212) = v24;
      *((_WORD *)a2 + 112) = 8 * __ROR2__(*(_WORD *)(v21 + 6) & 0xFF1F, 8);
    }
  }
  else
  {
    if ( v10 != 6 )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM(v9, NetBuffer->DataOffset, v4);
      return 0;
    }
    v47 = NdisGetDataBuffer(NetBuffer, 0x28u, (char *)a2 + 18, 4u, 0);
    *a2 = (__int64)v47;
    if ( !v47 )
    {
      v27 = 0;
      goto LABEL_29;
    }
    NdisAdvanceNetBufferDataStart(NetBuffer, 0x28u, 0, 0);
    v48 = *a2;
    v22 = a2 + 2;
    *((_DWORD *)a2 + 35) = 40;
    *((_BYTE *)a2 + 16) = *(_BYTE *)(v48 + 6);
    *((_BYTE *)a2 + 150) = *(_BYTE *)(v48 + 7);
    v49 = *((_BYTE *)a2 + 212);
    *((_BYTE *)a2 + 149) = 40;
    *((_DWORD *)a2 + 36) = 0;
    *((_BYTE *)a2 + 212) = v49 & 0xF9 | 4;
    while ( 1 )
    {
      v25 = (unsigned __int8)*v22;
      v24 = 0x1000180000000001LL;
      if ( (unsigned __int8)v25 > 0x3Cu || !_bittest64(&v24, v25) )
        break;
      v50 = &v63;
      v51 = 8;
      if ( (_BYTE)v25 == 44 )
        v50 = (__int16 *)&v64;
      else
        v51 = 2;
      if ( NetBuffer->DataLength < v51 )
        goto LABEL_62;
      v55 = NdisGetDataBuffer(NetBuffer, v51, v50, 1u, 0);
      if ( *v22 == 44 )
      {
        *((_BYTE *)a2 + 212) |= 1u;
        if ( v50 != (__int16 *)&v64 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v53, v52, v54);
        *((_DWORD *)a2 + 55) = v55[1];
        *((_WORD *)a2 + 112) = __ROR2__(*((_WORD *)v55 + 1) & 0xF8FF, 8);
        *((_BYTE *)a2 + 212) = *((_BYTE *)a2 + 212) & 0xF9 ^ (2 * (*((_BYTE *)v55 + 3) & 1));
      }
      else
      {
        v57 = *((unsigned __int8 *)v55 + 1);
        if ( *v22 == 43 )
        {
          v65 = 0;
          v58 = NdisGetDataBuffer(NetBuffer, 8u, &v65, 1u, 0);
          if ( !v58 || v58[3] )
            goto LABEL_62;
        }
        v51 = 8 * v57 + 8;
      }
      if ( NetBuffer->DataLength < v51 )
        goto LABEL_62;
      *v22 = *(_BYTE *)v55;
      NdisAdvanceNetBufferDataStart(NetBuffer, v51, 0, 0);
      *((_DWORD *)a2 + 35) += v51;
      *((_DWORD *)a2 + 36) += v51;
    }
  }
  v26 = *((_BYTE *)a2 + 17);
  v27 = 1;
  if ( v26 == 4 )
  {
    *((_WORD *)a2 + 76) = 2;
    *((_WORD *)a2 + 90) = 2;
    *((_DWORD *)a2 + 39) = *(_DWORD *)(*a2 + 12);
    v28 = 4;
    if ( *((_WORD *)a2 + 90) != 2 )
      v28 = 8;
    *(_DWORD *)((char *)a2 + v28 + 180) = *(_DWORD *)(*a2 + 16);
    goto LABEL_18;
  }
  if ( v26 != 6 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v25, v24, v21);
LABEL_18:
    v29 = v22;
    goto LABEL_19;
  }
  v62 = a2 + 23;
  *((_WORD *)a2 + 76) = 23;
  *((_WORD *)a2 + 90) = 23;
  *((_OWORD *)a2 + 10) = *(_OWORD *)(*a2 + 8);
  if ( *((_WORD *)a2 + 90) != 2 )
    v62 = (_OWORD *)((char *)a2 + 188);
  *v62 = *(_OWORD *)(*a2 + 24);
  v29 = a2 + 2;
LABEL_19:
  if ( (*((_BYTE *)a2 + 212) & 1) != 0 )
  {
    if ( *((_WORD *)a2 + 112) )
    {
      *((_BYTE *)a2 + 148) = 0;
      goto LABEL_29;
    }
  }
  else
  {
    v22 = v29;
  }
  v30 = (unsigned __int8)*v22;
  if ( v30 != 6 )
  {
    v41 = v30 - 1;
    if ( v41 )
    {
      v42 = v41 - 16;
      if ( !v42 )
      {
        v43 = NdisGetDataBuffer(NetBuffer, 8u, (char *)a2 + 58, 2u, 0);
        a2[1] = (__int64)v43;
        if ( !v43 )
        {
          v27 = 0;
          goto LABEL_29;
        }
        *((_BYTE *)a2 + 148) = 8;
        goto LABEL_24;
      }
      if ( v42 != 41 )
        goto LABEL_24;
    }
    v44 = (char *)NdisGetDataBuffer(NetBuffer, 8u, (char *)a2 + 58, 4u, 0);
    a2[1] = (__int64)v44;
    if ( !v44 )
    {
      v27 = 0;
      goto LABEL_29;
    }
    v45 = (unsigned __int8)*v22;
    *((_BYTE *)a2 + 148) = 8;
    v46 = *v44;
    if ( v45 == 1 )
    {
      if ( ((v46 - 3) & 0xF6) == 0 && v46 != 4 )
        goto LABEL_45;
LABEL_71:
      if ( (v46 & 0xF7) == 0 )
      {
LABEL_72:
        *((_BYTE *)a2 + 214) = 1;
        goto LABEL_24;
      }
      goto LABEL_76;
    }
    if ( v45 == 58 )
    {
      if ( (unsigned __int8)(v46 - 1) <= 3u )
      {
LABEL_45:
        *((_BYTE *)a2 + 213) = 1;
        goto LABEL_24;
      }
    }
    else
    {
      v56 = v45 - 1;
      if ( !v56 )
        goto LABEL_71;
      if ( v56 != 57 )
      {
LABEL_76:
        if ( a3 )
        {
          *((_BYTE *)a2 + 215) = 1;
          goto LABEL_24;
        }
LABEL_62:
        v27 = 0;
        goto LABEL_29;
      }
    }
    if ( (unsigned __int8)(v46 + 0x80) <= 1u )
      goto LABEL_72;
    goto LABEL_76;
  }
  v31 = NdisGetDataBuffer(NetBuffer, 0x14u, (char *)a2 + 58, 1u, 0);
  a2[1] = (__int64)v31;
  if ( !v31 )
  {
    v27 = 0;
    goto LABEL_29;
  }
  *((_BYTE *)a2 + 148) = 20;
  *((_BYTE *)a2 + 216) = v31[13];
LABEL_24:
  v32 = (unsigned __int8)*v22;
  if ( (unsigned __int8)v32 > 0x3Au )
    goto LABEL_29;
  v33 = 0x400000000020042LL;
  if ( !_bittest64(&v33, v32) )
    goto LABEL_29;
  v34 = (_WORD *)a2[1];
  if ( (_DWORD)v32 == 17 )
    goto LABEL_27;
  if ( (_DWORD)v32 == 1 )
  {
LABEL_104:
    *((_WORD *)a2 + 77) = v34[2];
    v35 = v34[2];
    goto LABEL_28;
  }
  if ( (_DWORD)v32 != 6 )
  {
    if ( (_DWORD)v32 != 58 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v32, v34, (unsigned int)(v32 - 6));
      goto LABEL_29;
    }
    goto LABEL_104;
  }
LABEL_27:
  *((_WORD *)a2 + 77) = *v34;
  v35 = v34[1];
LABEL_28:
  *((_WORD *)a2 + 91) = v35;
LABEL_29:
  v36 = *((_DWORD *)a2 + 35);
  if ( v36 )
  {
    if ( NdisRetreatNetBufferDataStart(NetBuffer, v36, 0, 0) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v38, v37, v39);
  }
  return v27;
}

```

## disassembly

```asm
0x1400011e0  mov     [rsp+arg_10], rbx
0x1400011e5  push    rbp
0x1400011e6  push    rsi
0x1400011e7  push    rdi
0x1400011e8  push    r12
0x1400011ea  push    r13
0x1400011ec  push    r14
0x1400011ee  push    r15
0x1400011f0  sub     rsp, 80h
0x1400011f7  mov     rax, cs:__security_cookie
0x1400011fe  xor     rax, rsp
0x140001201  mov     [rsp+0B8h+var_48], rax
0x140001206  xor     r13d, r13d
0x140001209  movzx   esi, r9w
0x14000120d  mov     r9d, 1; AlignMultiple
0x140001213  mov     [rdx+8Ch], r13d
0x14000121a  movzx   r12d, r8b
0x14000121e  mov     [rsp+0B8h+var_88], r13w
0x140001224  mov     rbx, rdx
0x140001227  mov     [rsp+0B8h+var_80], r13
0x14000122c  mov     edx, r9d; BytesNeeded
0x14000122f  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x140001234  xor     r8d, r8d; Storage
0x140001237  mov     rdi, rcx
0x14000123a  call    cs:__imp_NdisGetDataBuffer
0x140001241  nop     dword ptr [rax+rax+00h]
0x140001246  test    rax, rax
0x140001249  jz      loc_140001750
0x14000124f  mov     [rbx+0DCh], r13d
0x140001256  mov     r14d, 8
0x14000125c  mov     [rbx+0E0h], r13w
0x140001264  mov     r15d, 2
0x14000126a  mov     [rbx+0D4h], r13d
0x140001271  movzx   eax, byte ptr [rax]
0x140001274  shr     al, 4
0x140001277  mov     [rbx+11h], al
0x14000127a  cmp     al, 4
0x14000127c  jnz     loc_140001680
0x140001282  lea     r8, [rbx+12h]; Storage
0x140001286  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x14000128b  mov     edx, 14h; BytesNeeded
0x140001290  mov     r9d, 4; AlignMultiple
0x140001296  mov     rcx, rdi; NetBuffer
0x140001299  call    cs:__imp_NdisGetDataBuffer
0x1400012a0  nop     dword ptr [rax+rax+00h]
0x1400012a5  mov     [rbx], rax
0x1400012a8  test    rax, rax
0x1400012ab  jz      loc_14000158D
0x1400012b1  movzx   eax, byte ptr [rax]
0x1400012b4  and     al, 0Fh
0x1400012b6  shl     al, 2
0x1400012b9  movzx   esi, al
0x1400012bc  cmp     sil, 14h
0x1400012c0  jb      loc_1400018DA
0x1400012c6  cmp     esi, [rdi+18h]
0x1400012c9  ja      loc_1400018E4
0x1400012cf  cmp     sil, 14h
0x1400012d3  jz      short loc_140001347
0x1400012d5  xor     r9d, r9d; FreeMdlHandler
0x1400012d8  xor     r8d, r8d; FreeMdl
0x1400012db  mov     edx, 14h; DataOffsetDelta
0x1400012e0  mov     rcx, rdi; NetBuffer
0x1400012e3  add     esi, 0FFFFFFECh
0x1400012e6  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400012ed  nop     dword ptr [rax+rax+00h]
0x1400012f2  mov     r9d, 1; AlignMultiple
0x1400012f8  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x1400012fd  lea     r8, [rsp+0B8h+Storage]; Storage
0x140001302  mov     edx, esi; BytesNeeded
0x140001304  mov     rcx, rdi; NetBuffer
0x140001307  call    cs:__imp_NdisGetDataBuffer
0x14000130e  nop     dword ptr [rax+rax+00h]
0x140001313  xor     r9d, r9d; AllocateMdlHandler
0x140001316  xor     r8d, r8d; DataBackFill
0x140001319  mov     edx, 14h; DataOffsetDelta
0x14000131e  mov     rcx, rdi; NetBuffer
0x140001321  mov     r14, rax
0x140001324  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14000132b  nop     dword ptr [rax+rax+00h]
0x140001330  test    r14, r14
0x140001333  jz      loc_140001750
0x140001339  test    esi, esi
0x14000133b  jnz     loc_1400018EE
0x140001341  mov     r14d, 8
0x140001347  mov     rax, [rbx]
0x14000134a  movzx   ecx, byte ptr [rax]
0x14000134d  and     cl, 0Fh
0x140001350  shl     cl, 2
0x140001353  movzx   ebp, cl
0x140001356  cmp     [rdi+18h], ebp
0x140001359  jb      loc_140001958
0x14000135f  xor     r9d, r9d; FreeMdlHandler
0x140001362  xor     r8d, r8d; FreeMdl
0x140001365  mov     edx, ebp; DataOffsetDelta
0x140001367  mov     rcx, rdi; NetBuffer
0x14000136a  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140001371  nop     dword ptr [rax+rax+00h]
0x140001376  mov     r8, [rbx]
0x140001379  lea     rsi, [rbx+10h]
0x14000137d  mov     r10d, 0FF1Fh
0x140001383  mov     r9d, 1FFFh
0x140001389  movzx   eax, byte ptr [r8+9]
0x14000138e  mov     [rsi], al
0x140001390  movzx   eax, byte ptr [r8+8]
0x140001395  mov     [rbx+96h], al
0x14000139b  mov     byte ptr [rbx+95h], 14h
0x1400013a2  mov     [rbx+8Ch], ebp
0x1400013a8  movzx   eax, word ptr [r8+4]
0x1400013ad  mov     [rbx+0DCh], eax
0x1400013b3  movzx   eax, byte ptr [rbx+0D4h]
0x1400013ba  movzx   ecx, word ptr [r8+6]
0x1400013bf  shr     cx, 5
0x1400013c3  add     cl, cl
0x1400013c5  xor     cl, al
0x1400013c7  and     cl, r15b
0x1400013ca  xor     cl, al
0x1400013cc  mov     [rbx+0D4h], cl
0x1400013d2  movzx   edx, word ptr [r8+6]
0x1400013d7  shr     dx, 6
0x1400013db  shl     dl, 2
0x1400013de  xor     dl, cl
0x1400013e0  and     dl, 4
0x1400013e3  xor     dl, cl
0x1400013e5  mov     [rbx+0D4h], dl
0x1400013eb  movzx   ecx, word ptr [r8+6]
0x1400013f0  movzx   eax, cx
0x1400013f3  and     ax, r10w
0x1400013f7  ror     ax, 8
0x1400013fb  test    r9w, ax
0x1400013ff  jnz     loc_140001632
0x140001405  test    cl, 20h
0x140001408  jnz     loc_140001632
0x14000140e  movzx   eax, byte ptr [rbx+11h]
0x140001412  mov     bpl, 1
0x140001415  cmp     al, 4
0x140001417  jnz     loc_14000183B
0x14000141d  mov     [rbx+98h], r15w
0x140001425  mov     [rbx+0B4h], r15w
0x14000142d  mov     rax, [rbx]
0x140001430  mov     ecx, [rax+0Ch]
0x140001433  mov     [rbx+9Ch], ecx
0x140001439  mov     ecx, 4
0x14000143e  cmp     word ptr [rbx+0B4h], 2
0x140001446  mov     rax, [rbx]
0x140001449  cmovnz  rcx, r14
0x14000144d  mov     eax, [rax+10h]
0x140001450  mov     [rcx+rbx+0B4h], eax
0x140001457  mov     rcx, rsi
0x14000145a  test    [rbx+0D4h], bpl
0x140001461  jnz     loc_140001618
0x140001467  mov     rsi, rcx
0x14000146a  movzx   ecx, byte ptr [rsi]
0x14000146d  cmp     ecx, 6
0x140001470  jnz     loc_140001548
0x140001476  lea     r8, [rbx+3Ah]; Storage
0x14000147a  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x14000147f  mov     edx, 14h; BytesNeeded
0x140001484  mov     r9d, 1; AlignMultiple
0x14000148a  mov     rcx, rdi; NetBuffer
0x14000148d  call    cs:__imp_NdisGetDataBuffer
0x140001494  nop     dword ptr [rax+rax+00h]
0x140001499  mov     [rbx+8], rax
0x14000149d  test    rax, rax
0x1400014a0  jz      loc_140001585
0x1400014a6  mov     byte ptr [rbx+94h], 14h
0x1400014ad  movzx   eax, byte ptr [rax+0Dh]
0x1400014b1  mov     [rbx+0D8h], al
0x1400014b7  movzx   ecx, byte ptr [rsi]
0x1400014ba  cmp     cl, 3Ah ; ':'
0x1400014bd  ja      short loc_1400014F4
0x1400014bf  mov     rdx, 400000000020042h
0x1400014c9  bt      rdx, rcx
0x1400014cd  jnb     short loc_1400014F4
0x1400014cf  mov     rdx, [rbx+8]
0x1400014d3  mov     r8d, ecx
0x1400014d6  cmp     ecx, 11h
0x1400014d9  jnz     loc_140001658
0x1400014df  movzx   eax, word ptr [rdx]
0x1400014e2  mov     [rbx+9Ah], ax
0x1400014e9  movzx   eax, word ptr [rdx+2]
0x1400014ed  mov     [rbx+0B6h], ax
0x1400014f4  mov     edx, [rbx+8Ch]; DataOffsetDelta
0x1400014fa  test    edx, edx
0x1400014fc  jz      short loc_14000151B
0x1400014fe  xor     r9d, r9d; AllocateMdlHandler
0x140001501  xor     r8d, r8d; DataBackFill
0x140001504  mov     rcx, rdi; NetBuffer
0x140001507  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14000150e  nop     dword ptr [rax+rax+00h]
0x140001513  test    eax, eax
0x140001515  js      loc_14000159D
0x14000151b  movzx   eax, bpl
0x14000151f  mov     rcx, [rsp+0B8h+var_48]
0x140001524  xor     rcx, rsp; StackCookie
0x140001527  call    __security_check_cookie
0x14000152c  mov     rbx, [rsp+0B8h+arg_10]
0x140001534  add     rsp, 80h
0x14000153b  pop     r15
0x14000153d  pop     r14
0x14000153f  pop     r13
0x140001541  pop     r12
0x140001543  pop     rdi
0x140001544  pop     rsi
0x140001545  pop     rbp
0x140001546  retn
0x140001548  sub     ecx, 1
0x14000154b  jz      short loc_1400015B0
0x14000154d  sub     ecx, 10h
0x140001550  jnz     short loc_1400015A7
0x140001552  lea     r8, [rbx+3Ah]; Storage
0x140001556  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x14000155b  mov     r9d, r15d; AlignMultiple
0x14000155e  mov     edx, r14d; BytesNeeded
0x140001561  mov     rcx, rdi; NetBuffer
0x140001564  call    cs:__imp_NdisGetDataBuffer
0x14000156b  nop     dword ptr [rax+rax+00h]
0x140001570  mov     [rbx+8], rax
0x140001574  test    rax, rax
0x140001577  jz      short loc_140001595
0x140001579  mov     byte ptr [rbx+94h], 8
0x140001580  jmp     loc_1400014B7
0x140001585  xor     bpl, bpl
0x140001588  jmp     loc_1400014F4
0x14000158d  xor     bpl, bpl
0x140001590  jmp     loc_1400014F4
0x140001595  xor     bpl, bpl
0x140001598  jmp     loc_1400014F4
0x14000159d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400015a2  jmp     loc_14000151B
0x1400015a7  cmp     ecx, 29h ; ')'
0x1400015aa  jnz     loc_1400014B7
0x1400015b0  lea     r8, [rbx+3Ah]; Storage
0x1400015b4  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x1400015b9  mov     r9d, 4; AlignMultiple
0x1400015bf  mov     edx, r14d; BytesNeeded
0x1400015c2  mov     rcx, rdi; NetBuffer
0x1400015c5  call    cs:__imp_NdisGetDataBuffer
0x1400015cc  nop     dword ptr [rax+rax+00h]
0x1400015d1  mov     [rbx+8], rax
0x1400015d5  test    rax, rax
0x1400015d8  jz      loc_1400019AC
0x1400015de  movzx   ecx, byte ptr [rsi]
0x1400015e1  mov     r8d, ecx
0x1400015e4  mov     byte ptr [rbx+94h], 8
0x1400015eb  movzx   edx, byte ptr [rax]
0x1400015ee  sub     r8d, 1
0x1400015f2  jnz     loc_14000181B
0x1400015f8  lea     eax, [rdx-3]
0x1400015fb  test    al, 0F6h
0x1400015fd  jnz     loc_14000182A
0x140001603  cmp     dl, 4
0x140001606  jz      loc_14000182A
0x14000160c  mov     [rbx+0D5h], bpl
0x140001613  jmp     loc_1400014B7
0x140001618  cmp     [rbx+0E0h], r13w
0x140001620  jz      loc_14000146A
0x140001626  mov     [rbx+94h], r13b
0x14000162d  jmp     loc_1400014F4
0x140001632  or      dl, 1
0x140001635  mov     [rbx+0D4h], dl
0x14000163b  movzx   eax, word ptr [r8+6]
0x140001640  and     ax, r10w
0x140001644  ror     ax, 8
0x140001648  shl     ax, 3
0x14000164c  mov     [rbx+0E0h], ax
0x140001653  jmp     loc_14000140E
0x140001658  sub     r8d, 1
0x14000165c  jz      loc_1400019D0
0x140001662  sub     r8d, 5
0x140001666  jz      loc_1400014DF
0x14000166c  cmp     r8d, 34h ; '4'
0x140001670  jz      loc_1400019D0
0x140001676  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000167b  jmp     loc_1400014F4
0x140001680  cmp     al, 6
0x140001682  jnz     loc_14000186B
0x140001688  lea     r8, [rbx+12h]; Storage
0x14000168c  mov     [rsp+0B8h+AlignOffset], r13d; AlignOffset
0x140001691  mov     edx, 28h ; '('; BytesNeeded
0x140001696  mov     r9d, 4; AlignMultiple
0x14000169c  mov     rcx, rdi; NetBuffer
0x14000169f  call    cs:__imp_NdisGetDataBuffer
0x1400016a6  nop     dword ptr [rax+rax+00h]
0x1400016ab  mov     [rbx], rax
0x1400016ae  test    rax, rax
0x1400016b1  jz      loc_14000187D
0x1400016b7  xor     r9d, r9d; FreeMdlHandler
0x1400016ba  xor     r8d, r8d; FreeMdl
0x1400016bd  mov     edx, 28h ; '('; DataOffsetDelta
0x1400016c2  mov     rcx, rdi; NetBuffer
0x1400016c5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400016cc  nop     dword ptr [rax+rax+00h]
0x1400016d1  mov     rcx, [rbx]
0x1400016d4  lea     rsi, [rbx+10h]
0x1400016d8  mov     dword ptr [rbx+8Ch], 28h ; '('
0x1400016e2  movzx   eax, byte ptr [rcx+6]
0x1400016e6  mov     [rsi], al
0x1400016e8  movzx   eax, byte ptr [rcx+7]
0x1400016ec  mov     [rbx+96h], al
0x1400016f2  movzx   eax, byte ptr [rbx+0D4h]
  ... truncated ...
```
