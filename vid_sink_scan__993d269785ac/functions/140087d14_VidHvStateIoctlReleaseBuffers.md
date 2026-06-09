# VidHvStateIoctlReleaseBuffers

- ea: `0x140087d14`
- end: `0x140088806`
- name: `VidHvStateIoctlReleaseBuffers`
- size: `2802`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140031fa4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021606`
- `0x140021650`
- `0x140024c78`
- `0x1400303c0`
- `0x140030760`
- `0x140030790`
- `0x1400307d0`
- `0x140087d14`
- `0x140089978`
- `0x140089990`
- `0x1400899ac`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x14008827b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140088610`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14008827b`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140088610`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400881ed`
- `ntoskrnl!RtlRbRemoveNode` at `0x140088582`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400881ed`
- `ntoskrnl!RtlRbRemoveNode` at `0x140088582`
- `ntoskrnl!ProbeForRead` at `0x140087da2`
- `ntoskrnl!ProbeForRead` at `0x140087da2`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x14008806e`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x140088383`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x14008806e`
- `winhvr!WinHvReleaseStateTransferBuffers` at `0x140088383`

## pseudocode

```c
__int64 __fastcall VidHvStateIoctlReleaseBuffers(__int64 a1, _QWORD *a2, unsigned int a3)
{
  unsigned int v3; // r13d
  _QWORD *v4; // r14
  __int64 v6; // r12
  int v7; // r14d
  __int128 *v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // r15d
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // r13
  __int64 v14; // rdi
  int v15; // r14d
  int v16; // eax
  __int64 v17; // rax
  int v18; // r8d
  _QWORD *v19; // r9
  __int16 *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r15
  unsigned __int64 v25; // r14
  int v26; // r12d
  unsigned __int64 v27; // rax
  _QWORD *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r13
  __int64 v32; // r8
  __int64 v33; // r15
  unsigned __int64 v34; // rdi
  int v35; // r12d
  unsigned __int64 v36; // rax
  int v38; // [rsp+20h] [rbp-1188h]
  char v39; // [rsp+40h] [rbp-1168h]
  int v40; // [rsp+44h] [rbp-1164h] BYREF
  int v41; // [rsp+48h] [rbp-1160h] BYREF
  unsigned int v42; // [rsp+50h] [rbp-1158h]
  __int64 v43; // [rsp+58h] [rbp-1150h] BYREF
  __int128 v44; // [rsp+60h] [rbp-1148h] BYREF
  __int64 v45; // [rsp+70h] [rbp-1138h] BYREF
  __int64 v46; // [rsp+78h] [rbp-1130h]
  _QWORD *v47; // [rsp+80h] [rbp-1128h]
  _QWORD *v48; // [rsp+88h] [rbp-1120h] BYREF
  _QWORD v49[4]; // [rsp+90h] [rbp-1118h] BYREF
  _BYTE v50[32]; // [rsp+B0h] [rbp-10F8h] BYREF
  _BYTE v51[16]; // [rsp+D0h] [rbp-10D8h] BYREF
  _BYTE v52[16]; // [rsp+E0h] [rbp-10C8h] BYREF
  int *v53; // [rsp+F0h] [rbp-10B8h]
  __int64 v54; // [rsp+F8h] [rbp-10B0h]
  int *v55; // [rsp+100h] [rbp-10A8h]
  __int64 v56; // [rsp+108h] [rbp-10A0h]
  __int64 v57; // [rsp+110h] [rbp-1098h]
  __int64 v58; // [rsp+118h] [rbp-1090h]
  int *v59; // [rsp+120h] [rbp-1088h]
  __int64 v60; // [rsp+128h] [rbp-1080h]
  __int64 v61; // [rsp+130h] [rbp-1078h]
  int v62; // [rsp+138h] [rbp-1070h] BYREF
  int v63; // [rsp+13Ch] [rbp-106Ch]
  __int64 *v64; // [rsp+140h] [rbp-1068h]
  __int64 v65; // [rsp+148h] [rbp-1060h]
  int *v66; // [rsp+150h] [rbp-1058h]
  __int64 v67; // [rsp+158h] [rbp-1050h]
  _DWORD *v68; // [rsp+160h] [rbp-1048h]
  __int64 v69; // [rsp+168h] [rbp-1040h]
  _DWORD v70[1020]; // [rsp+170h] [rbp-1038h] BYREF

  v3 = a3;
  v42 = a3;
  v4 = a2;
  v47 = a2;
  v49[1] = a1;
  v48 = a2;
  v41 = a3;
  v44 = 0;
  v49[0] = 0;
  v6 = *(_QWORD *)(a1 + 12720);
  v46 = v6;
  v49[2] = v6;
  v39 = 0;
  ProbeForRead(a2, 8LL * a3, 8u);
  *((_QWORD *)&v44 + 1) = &v44;
  *(_QWORD *)&v44 = &v44;
  if ( !VidOpCtrlStart((volatile signed __int32 *)(a1 + 12624)) )
  {
    v7 = -1073741436;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlReleaseBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      514,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      -1073741436);
    goto LABEL_62;
  }
  VidLockAcquireExclusive(v6);
  v39 = 1;
  if ( v3 > *(_DWORD *)(v6 + 32) )
  {
    v7 = -1073741811;
    VidTracePartitionErrorInternal0(
      (unsigned int)"VidHvStateIoctlReleaseBuffers",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidhvstate.c",
      525,
      a1 + 656,
      a1 + 120,
      *(_QWORD *)(a1 + 648),
      -1073741811);
    goto LABEL_62;
  }
  v10 = 0;
  v11 = 0;
  while ( 1 )
  {
    v40 = v11;
    if ( (unsigned int)v11 >= v3 )
      break;
    v12 = v4[v11];
    v45 = v12;
    v43 = v12;
    v13 = v6 + 64;
    v14 = *(_QWORD *)(v6 + 64);
    if ( (*(_BYTE *)(v6 + 72) & 1) != 0 )
    {
      if ( v14 )
        v14 ^= v13;
      else
        v14 = 0;
    }
    v15 = *(_BYTE *)(v6 + 72) & 1;
    if ( !v14 )
      goto LABEL_22;
    do
    {
      v16 = VidHvStatepCompareBuffersByMappedAddress(&v43, v14, v9);
      if ( v16 >= 0 )
      {
        if ( v16 <= 0 )
          break;
        v17 = *(_QWORD *)(v14 + 8);
      }
      else
      {
        v17 = *(_QWORD *)v14;
      }
      if ( v15 && v17 )
        v14 ^= v17;
      else
        v14 = v17;
    }
    while ( v14 );
    v12 = v45;
    if ( !v14 )
    {
LABEL_22:
      v9 = 3221225485LL;
      v7 = -1073741811;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v51, "VidHvStateIoctlReleaseBuffers");
        tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
        v41 = 552;
        v53 = &v41;
        v40 = v18;
        v55 = &v40;
        v57 = a1 + 656;
        v59 = &v62;
        v61 = *(_QWORD *)(a1 + 128);
        v62 = *(unsigned __int16 *)(a1 + 120);
        v43 = *(_QWORD *)(a1 + 648);
        v64 = &v43;
        v48 = v19;
        v66 = (int *)&v48;
        v67 = 8;
        v38 = 11;
        v20 = (__int16 *)&byte_140046F87;
        goto LABEL_25;
      }
LABEL_26:
      VidHvStatepDebugState(a1, v8, v9, v12);
      goto LABEL_62;
    }
    if ( v10 == 1020 )
    {
      v7 = WinHvReleaseStateTransferBuffers(*(_QWORD *)(a1 + 648), 1020, v70, v49);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_26;
        tlgCreate1Sz_char(v51, "VidHvStateIoctlReleaseBuffers");
        tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
        v41 = 582;
        v53 = &v41;
        LODWORD(v45) = v7;
        v55 = (int *)&v45;
        v57 = a1 + 656;
        v59 = &v62;
        v61 = *(_QWORD *)(a1 + 128);
        v62 = *(unsigned __int16 *)(a1 + 120);
        v43 = *(_QWORD *)(a1 + 648);
        v64 = &v43;
        LOWORD(v40) = 1020;
        v66 = &v40;
        v67 = 2;
        v68 = v70;
        v69 = 4080;
        v38 = 12;
        v20 = (__int16 *)&dword_140047004;
        goto LABEL_25;
      }
      while ( 1 )
      {
        v21 = v44;
        if ( (__int128 *)v44 == &v44 )
          break;
        if ( *(__int128 **)(v44 + 8) != &v44 )
          goto LABEL_83;
        v22 = *(_QWORD *)v44;
        if ( *(_QWORD *)(*(_QWORD *)v44 + 8LL) != (_QWORD)v44 )
          goto LABEL_83;
        *(_QWORD *)&v44 = *(_QWORD *)v44;
        *(_QWORD *)(v22 + 8) = &v44;
        v14 = v21 - 24;
        RtlRbRemoveNode(v13, v21 - 24);
        v24 = v6 + 16;
        v25 = *(_QWORD *)(v6 + 16);
        if ( (*(_BYTE *)(v6 + 24) & 1) != 0 )
        {
          if ( v25 )
            v25 ^= v24;
          else
            v25 = 0;
        }
        v26 = *(_BYTE *)(v6 + 24) & 1;
        LOBYTE(v23) = 0;
        if ( v25 )
        {
          while ( 1 )
          {
            if ( (int)VidHvStatepCompareBuffersById(v14 + 40, v25, v23) < 0 )
            {
              v27 = *(_QWORD *)v25;
              if ( v26 )
              {
                if ( !v27 )
                  goto LABEL_51;
                v27 ^= v25;
              }
              if ( !v27 )
              {
LABEL_51:
                LOBYTE(v23) = 0;
                break;
              }
            }
            else
            {
              v27 = *(_QWORD *)(v25 + 8);
              if ( v26 )
              {
                if ( !v27 )
                  goto LABEL_45;
                v27 ^= v25;
              }
              if ( !v27 )
              {
LABEL_45:
                LOBYTE(v23) = 1;
                break;
              }
            }
            v25 = v27;
          }
        }
        RtlRbInsertNodeEx(v24, v25, v23, v14);
        *(_DWORD *)(v14 + 128) &= 0xFFFFFFFC;
        v6 = v46;
      }
      v10 = 0;
    }
    v70[v10] = *(_DWORD *)(v14 + 40);
    v28 = (_QWORD *)*((_QWORD *)&v44 + 1);
    if ( **((__int128 ***)&v44 + 1) != &v44 )
LABEL_83:
      __fastfail(3u);
    ++v10;
    v8 = &v44;
    *(_QWORD *)(v14 + 24) = &v44;
    *(_QWORD *)(v14 + 32) = v28;
    *v28 = v14 + 24;
    *((_QWORD *)&v44 + 1) = v14 + 24;
    v11 = (unsigned int)(v40 + 1);
    v3 = v42;
    v4 = v47;
  }
  if ( v10 )
  {
    v7 = WinHvReleaseStateTransferBuffers(*(_QWORD *)(a1 + 648), v10, v70, v49);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_26;
      tlgCreate1Sz_char(v51, "VidHvStateIoctlReleaseBuffers");
      tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
      LODWORD(v45) = 632;
      v53 = (int *)&v45;
      v41 = v7;
      v55 = &v41;
      v57 = a1 + 656;
      v59 = &v62;
      v61 = *(_QWORD *)(a1 + 128);
      v62 = *(unsigned __int16 *)(a1 + 120);
      v43 = *(_QWORD *)(a1 + 648);
      v64 = &v43;
      LOWORD(v40) = v10;
      v66 = &v40;
      v67 = 2;
      v68 = v70;
      v69 = 4 * (unsigned int)(unsigned __int16)v10;
      v38 = 12;
      v20 = &word_140046F0E;
LABEL_25:
      v54 = 4;
      v56 = 4;
      v58 = 16;
      v60 = 2;
      v63 = 0;
      v65 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v20, 0, 0, v38, v50);
      goto LABEL_26;
    }
  }
  v7 = 0;
LABEL_62:
  while ( 1 )
  {
    v29 = v44;
    if ( (__int128 *)v44 == &v44 )
      break;
    if ( *(__int128 **)(v44 + 8) != &v44 )
      goto LABEL_83;
    v30 = *(_QWORD *)v44;
    if ( *(_QWORD *)(*(_QWORD *)v44 + 8LL) != (_QWORD)v44 )
      goto LABEL_83;
    *(_QWORD *)&v44 = *(_QWORD *)v44;
    *(_QWORD *)(v30 + 8) = &v44;
    v31 = v29 - 24;
    RtlRbRemoveNode(v6 + 64, v29 - 24);
    v33 = v6 + 16;
    v34 = *(_QWORD *)(v6 + 16);
    if ( (*(_BYTE *)(v6 + 24) & 1) != 0 )
    {
      if ( v34 )
        v34 ^= v33;
      else
        v34 = 0;
    }
    v35 = *(_BYTE *)(v6 + 24) & 1;
    LOBYTE(v32) = 0;
    if ( v34 )
    {
      while ( 1 )
      {
        if ( (int)VidHvStatepCompareBuffersById(v31 + 40, v34, v32) < 0 )
        {
          v36 = *(_QWORD *)v34;
          if ( v35 )
          {
            if ( !v36 )
              goto LABEL_81;
            v36 ^= v34;
          }
          if ( !v36 )
          {
LABEL_81:
            LOBYTE(v32) = 0;
            break;
          }
        }
        else
        {
          v36 = *(_QWORD *)(v34 + 8);
          if ( v35 )
          {
            if ( !v36 )
              goto LABEL_75;
            v36 ^= v34;
          }
          if ( !v36 )
          {
LABEL_75:
            LOBYTE(v32) = 1;
            break;
          }
        }
        v34 = v36;
      }
    }
    RtlRbInsertNodeEx(v33, v34, v32, v31);
    *(_DWORD *)(v31 + 128) &= 0xFFFFFFFC;
    v6 = v46;
  }
  if ( v39 )
  {
    VidLockRelease(v6);
    VidOpCtrlFinish(a1 + 12624);
  }
  if ( v7 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v51, "VidHvStateIoctlReleaseBuffers");
    tlgCreate1Sz_char(v52, "onecore\\vm\\vid\\sys\\driver\\vidhvstate.c");
    LODWORD(v45) = 679;
    v53 = (int *)&v45;
    v54 = 4;
    v41 = v7;
    v55 = &v41;
    v56 = 4;
    v57 = a1 + 656;
    v58 = 16;
    v59 = &v62;
    v60 = 2;
    v61 = *(_QWORD *)(a1 + 128);
    v62 = *(unsigned __int16 *)(a1 + 120);
    v63 = 0;
    v43 = *(_QWORD *)(a1 + 648);
    v64 = &v43;
    v65 = 8;
    LOWORD(v40) = v42;
    v66 = &v40;
    v67 = 2;
    v68 = v47;
    v69 = 8 * (unsigned int)(unsigned __int16)v42;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &dword_140046E94, 0, 0, 12, v50);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140087d14  push    rbx
0x140087d16  push    rsi
0x140087d17  push    rdi
0x140087d18  push    r12
0x140087d1a  push    r13
0x140087d1c  push    r14
0x140087d1e  push    r15
0x140087d20  mov     eax, 1170h
0x140087d25  call    __chkstk_0
0x140087d2a  sub     rsp, rax
0x140087d2d  mov     rax, cs:__security_cookie
0x140087d34  xor     rax, rsp
0x140087d37  mov     [rsp+11A8h+var_48], rax
0x140087d3f  mov     r13d, r8d
0x140087d42  mov     [rsp+11A8h+var_1158], r13d
0x140087d47  mov     r14, rdx
0x140087d4a  mov     [rsp+11A8h+var_1128], rdx
0x140087d52  mov     rsi, rcx
0x140087d55  mov     [rsp+11A8h+var_1110], rcx
0x140087d5d  mov     [rsp+11A8h+var_1120], rdx
0x140087d65  mov     [rsp+11A8h+var_1160], r13d
0x140087d6a  xorps   xmm0, xmm0
0x140087d6d  movups  [rsp+11A8h+var_1148], xmm0
0x140087d72  xor     ebx, ebx
0x140087d74  mov     [rsp+11A8h+var_1118], rbx
0x140087d7c  mov     r12, [rcx+31B0h]
0x140087d83  mov     [rsp+11A8h+var_1130], r12
0x140087d88  mov     [rsp+11A8h+var_1108], r12
0x140087d90  mov     [rsp+11A8h+var_1168], bl
0x140087d94  mov     edx, r13d
0x140087d97  shl     rdx, 3; Length
0x140087d9b  lea     r8d, [rbx+8]; Alignment
0x140087d9f  mov     rcx, r14; Address
0x140087da2  call    cs:__imp_ProbeForRead
0x140087da9  nop     dword ptr [rax+rax+00h]
0x140087dae  nop
0x140087daf  lea     rax, [rsp+11A8h+var_1148]
0x140087db4  mov     qword ptr [rsp+11A8h+var_1148+8], rax
0x140087db9  lea     rax, [rsp+11A8h+var_1148]
0x140087dbe  mov     qword ptr [rsp+11A8h+var_1148], rax
0x140087dc3  lea     rcx, [rsi+3150h]
0x140087dca  call    VidOpCtrlStart
0x140087dcf  test    al, al
0x140087dd1  jnz     short loc_140087E18
0x140087dd3  mov     r14d, 0C0000184h
0x140087dd9  mov     [rsp+11A8h+var_1178], r14d
0x140087dde  mov     r8d, 202h
0x140087de4  mov     rax, [rsi+288h]
0x140087deb  mov     [rsp+11A8h+var_1180], rax
0x140087df0  lea     rcx, [rsi+78h]
0x140087df4  mov     [rsp+11A8h+var_1188], rcx
0x140087df9  lea     r9, [rsi+290h]
0x140087e00  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140087e07  lea     rcx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x140087e0e  call    VidTracePartitionErrorInternal0
0x140087e13  jmp     loc_140088539
0x140087e18  mov     rcx, r12
0x140087e1b  call    VidLockAcquireExclusive
0x140087e20  mov     [rsp+11A8h+var_1168], 1
0x140087e25  cmp     r13d, [r12+20h]
0x140087e2a  jbe     short loc_140087E42
0x140087e2c  mov     r8d, 0C000000Dh
0x140087e32  mov     r14d, r8d
0x140087e35  mov     [rsp+11A8h+var_1178], r8d
0x140087e3a  mov     r8d, 20Dh
0x140087e40  jmp     short loc_140087DE4
0x140087e42  mov     r15d, ebx
0x140087e45  mov     eax, ebx
0x140087e47  mov     ecx, 3FCh
0x140087e4c  mov     [rsp+11A8h+var_1164], eax
0x140087e50  cmp     eax, r13d
0x140087e53  jnb     loc_140088360
0x140087e59  mov     r9, [r14+rax*8]
0x140087e5d  mov     [rsp+11A8h+var_1138], r9
0x140087e62  mov     [rsp+11A8h+var_1150], r9
0x140087e67  lea     r13, [r12+40h]
0x140087e6c  mov     rdi, [r13+0]
0x140087e70  test    byte ptr [r13+8], 1
0x140087e75  jz      short loc_140087E84
0x140087e77  test    rdi, rdi
0x140087e7a  jz      short loc_140087E81
0x140087e7c  xor     rdi, r13
0x140087e7f  jmp     short loc_140087E84
0x140087e81  mov     rdi, rbx
0x140087e84  movzx   r14d, byte ptr [r13+8]
0x140087e89  and     r14d, 1
0x140087e8d  test    rdi, rdi
0x140087e90  jz      short loc_140087ED8
0x140087e92  mov     rdx, rdi
0x140087e95  lea     rcx, [rsp+11A8h+var_1150]
0x140087e9a  call    VidHvStatepCompareBuffersByMappedAddress
0x140087e9f  test    eax, eax
0x140087ea1  jns     short loc_140087EA8
0x140087ea3  mov     rax, [rdi]
0x140087ea6  jmp     short loc_140087EAE
0x140087ea8  jle     short loc_140087EC5
0x140087eaa  mov     rax, [rdi+8]
0x140087eae  test    r14d, r14d
0x140087eb1  jz      short loc_140087EBD
0x140087eb3  test    rax, rax
0x140087eb6  jz      short loc_140087EBD
0x140087eb8  xor     rdi, rax
0x140087ebb  jmp     short loc_140087EC0
0x140087ebd  mov     rdi, rax
0x140087ec0  test    rdi, rdi
0x140087ec3  jnz     short loc_140087E92
0x140087ec5  mov     ecx, 3FCh
0x140087eca  mov     r9, [rsp+11A8h+var_1138]
0x140087ecf  test    rdi, rdi
0x140087ed2  jnz     loc_14008804C
0x140087ed8  mov     r8d, 0C000000Dh
0x140087ede  mov     r14d, r8d
0x140087ee1  mov     eax, cs:dword_140064110
0x140087ee7  cmp     eax, 2
0x140087eea  jbe     loc_14008803F
0x140087ef0  mov     edx, 100h
0x140087ef5  lea     rcx, dword_140064110
0x140087efc  call    _tlgKeywordOn
0x140087f01  test    al, al
0x140087f03  jz      loc_14008803F
0x140087f09  lea     rdx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x140087f10  lea     rcx, [rsp+11A8h+var_10D8]
0x140087f18  call    _tlgCreate1Sz_char
0x140087f1d  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x140087f24  lea     rcx, [rsp+11A8h+var_10C8]
0x140087f2c  call    _tlgCreate1Sz_char
0x140087f31  mov     [rsp+11A8h+var_1160], 228h
0x140087f39  lea     rax, [rsp+11A8h+var_1160]
0x140087f3e  mov     [rsp+11A8h+var_10B8], rax
0x140087f46  mov     [rsp+11A8h+var_1164], r8d
0x140087f4b  lea     rax, [rsp+11A8h+var_1164]
0x140087f50  mov     [rsp+11A8h+var_10A8], rax
0x140087f58  lea     rax, [rsi+290h]
0x140087f5f  mov     [rsp+11A8h+var_1098], rax
0x140087f67  lea     rax, [rsp+11A8h+var_1070]
0x140087f6f  mov     [rsp+11A8h+var_1088], rax
0x140087f77  mov     rax, [rsi+80h]
0x140087f7e  mov     [rsp+11A8h+var_1078], rax
0x140087f86  movzx   eax, word ptr [rsi+78h]
0x140087f8a  mov     [rsp+11A8h+var_1070], eax
0x140087f91  mov     rax, [rsi+288h]
0x140087f98  mov     [rsp+11A8h+var_1150], rax
0x140087f9d  lea     rax, [rsp+11A8h+var_1150]
0x140087fa2  mov     [rsp+11A8h+var_1068], rax
0x140087faa  mov     [rsp+11A8h+var_1120], r9
0x140087fb2  lea     rcx, [rsp+11A8h+var_1120]
0x140087fba  mov     [rsp+11A8h+var_1058], rcx
0x140087fc2  mov     [rsp+11A8h+var_1050], 8
0x140087fce  lea     rax, [rsp+11A8h+var_10F8]
0x140087fd6  mov     [rsp+11A8h+var_1180], rax
0x140087fdb  mov     dword ptr [rsp+11A8h+var_1188], 0Bh
0x140087fe3  lea     rdx, byte_140046F87
0x140087fea  mov     [rsp+11A8h+var_10B0], 4
0x140087ff6  mov     [rsp+11A8h+var_10A0], 4
0x140088002  xor     r9d, r9d
0x140088005  mov     [rsp+11A8h+var_1090], 10h
0x140088011  mov     [rsp+11A8h+var_1080], 2
0x14008801d  mov     [rsp+11A8h+var_106C], ebx
0x140088024  mov     [rsp+11A8h+var_1060], 8
0x140088030  xor     r8d, r8d
0x140088033  lea     rcx, dword_140064110
0x14008803a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14008803f  mov     rcx, rsi
0x140088042  call    VidHvStatepDebugState
0x140088047  jmp     loc_140088539
0x14008804c  cmp     r15d, ecx
0x14008804f  jnz     loc_14008829B
0x140088055  lea     r9, [rsp+11A8h+var_1118]
0x14008805d  lea     r8, [rsp+11A8h+var_1038]
0x140088065  mov     edx, ecx
0x140088067  mov     rcx, [rsi+288h]
0x14008806e  call    cs:__imp_WinHvReleaseStateTransferBuffers
0x140088075  nop     dword ptr [rax+rax+00h]
0x14008807a  mov     r14d, eax
0x14008807d  test    eax, eax
0x14008807f  jns     loc_1400881A6
0x140088085  mov     ecx, cs:dword_140064110
0x14008808b  cmp     ecx, 2
0x14008808e  jbe     short loc_14008803F
0x140088090  mov     edx, 100h
0x140088095  lea     rcx, dword_140064110
0x14008809c  call    _tlgKeywordOn
0x1400880a1  test    al, al
0x1400880a3  jz      short loc_14008803F
0x1400880a5  lea     rdx, aVidhvstateioct; "VidHvStateIoctlReleaseBuffers"
0x1400880ac  lea     rcx, [rsp+11A8h+var_10D8]
0x1400880b4  call    _tlgCreate1Sz_char
0x1400880b9  lea     rdx, aOnecoreVmVidSy_17; "onecore\\vm\\vid\\sys\\driver\\vidhvsta"...
0x1400880c0  lea     rcx, [rsp+11A8h+var_10C8]
0x1400880c8  call    _tlgCreate1Sz_char
0x1400880cd  mov     [rsp+11A8h+var_1160], 246h
0x1400880d5  lea     rax, [rsp+11A8h+var_1160]
0x1400880da  mov     [rsp+11A8h+var_10B8], rax
0x1400880e2  mov     dword ptr [rsp+11A8h+var_1138], r14d
0x1400880e7  lea     rax, [rsp+11A8h+var_1138]
0x1400880ec  mov     [rsp+11A8h+var_10A8], rax
0x1400880f4  lea     rax, [rsi+290h]
0x1400880fb  mov     [rsp+11A8h+var_1098], rax
0x140088103  lea     rax, [rsp+11A8h+var_1070]
0x14008810b  mov     [rsp+11A8h+var_1088], rax
0x140088113  mov     rax, [rsi+80h]
0x14008811a  mov     [rsp+11A8h+var_1078], rax
0x140088122  movzx   eax, word ptr [rsi+78h]
0x140088126  mov     [rsp+11A8h+var_1070], eax
0x14008812d  mov     rax, [rsi+288h]
0x140088134  mov     [rsp+11A8h+var_1150], rax
0x140088139  lea     rax, [rsp+11A8h+var_1150]
0x14008813e  mov     [rsp+11A8h+var_1068], rax
0x140088146  mov     eax, 3FCh
0x14008814b  mov     word ptr [rsp+11A8h+var_1164], ax
0x140088150  lea     rax, [rsp+11A8h+var_1164]
0x140088155  mov     [rsp+11A8h+var_1058], rax
0x14008815d  mov     [rsp+11A8h+var_1050], 2
0x140088169  lea     rax, [rsp+11A8h+var_1038]
0x140088171  mov     [rsp+11A8h+var_1048], rax
0x140088179  mov     [rsp+11A8h+var_1040], 0FF0h
0x140088185  lea     rax, [rsp+11A8h+var_10F8]
0x14008818d  mov     [rsp+11A8h+var_1180], rax
0x140088192  mov     dword ptr [rsp+11A8h+var_1188], 0Ch
0x14008819a  lea     rdx, dword_140047004
0x1400881a1  jmp     loc_140087FEA
0x1400881a6  mov     rax, qword ptr [rsp+11A8h+var_1148]
0x1400881ab  lea     rcx, [rsp+11A8h+var_1148]
0x1400881b0  cmp     rax, rcx
0x1400881b3  jz      loc_140088298
0x1400881b9  lea     rcx, [rsp+11A8h+var_1148]
0x1400881be  cmp     [rax+8], rcx
0x1400881c2  jnz     loc_14008862E
0x1400881c8  mov     rcx, [rax]
0x1400881cb  cmp     [rcx+8], rax
0x1400881cf  jnz     loc_14008862E
0x1400881d5  mov     qword ptr [rsp+11A8h+var_1148], rcx
0x1400881da  lea     rdx, [rsp+11A8h+var_1148]
0x1400881df  mov     [rcx+8], rdx
0x1400881e3  lea     rdi, [rax-18h]
0x1400881e7  mov     rdx, rdi
0x1400881ea  mov     rcx, r13
0x1400881ed  call    cs:__imp_RtlRbRemoveNode
0x1400881f4  nop     dword ptr [rax+rax+00h]
0x1400881f9  lea     r15, [r12+10h]
0x1400881fe  mov     r14, [r15]
0x140088201  test    byte ptr [r12+18h], 1
0x140088207  jz      short loc_140088216
0x140088209  test    r14, r14
0x14008820c  jz      short loc_140088213
0x14008820e  xor     r14, r15
0x140088211  jmp     short loc_140088216
0x140088213  mov     r14, rbx
0x140088216  movzx   r12d, byte ptr [r15+8]
0x14008821b  and     r12d, 1
0x14008821f  mov     r8b, bl
0x140088222  test    r14, r14
0x140088225  jz      short loc_140088272
0x140088227  lea     rax, [rdi+28h]
0x14008822b  mov     rdx, r14
0x14008822e  mov     rcx, rax
0x140088231  call    VidHvStatepCompareBuffersById
0x140088236  test    eax, eax
0x140088238  js      short loc_140088255
0x14008823a  mov     rax, [r14+8]
0x14008823e  test    r12d, r12d
0x140088241  jz      short loc_14008824B
0x140088243  test    rax, rax
0x140088246  jz      short loc_140088250
0x140088248  xor     rax, r14
0x14008824b  test    rax, rax
0x14008824e  jnz     short loc_14008826A
0x140088250  mov     r8b, 1
0x140088253  jmp     short loc_140088272
0x140088255  mov     rax, [r14]
0x140088258  test    r12d, r12d
0x14008825b  jz      short loc_140088265
0x14008825d  test    rax, rax
0x140088260  jz      short loc_14008826F
0x140088262  xor     rax, r14
0x140088265  test    rax, rax
0x140088268  jz      short loc_14008826F
0x14008826a  mov     r14, rax
0x14008826d  jmp     short loc_140088227
0x14008826f  mov     r8b, bl
0x140088272  mov     r9, rdi
0x140088275  mov     rdx, r14
0x140088278  mov     rcx, r15
0x14008827b  call    cs:__imp_RtlRbInsertNodeEx
0x140088282  nop     dword ptr [rax+rax+00h]
0x140088287  and     dword ptr [rdi+80h], 0FFFFFFFCh
0x14008828e  mov     r12, [rsp+11A8h+var_1130]
0x140088293  jmp     loc_1400881A6
0x140088298  mov     r15d, ebx
0x14008829b  mov     ecx, r15d
0x14008829e  mov     eax, [rdi+28h]
0x1400882a1  mov     [rsp+rcx*4+11A8h+var_1038], eax
0x1400882a8  mov     rcx, qword ptr [rsp+11A8h+var_1148+8]
0x1400882ad  lea     rax, [rsp+11A8h+var_1148]
0x1400882b2  cmp     [rcx], rax
0x1400882b5  jnz     loc_14008862E
0x1400882bb  inc     r15d
0x1400882be  lea     rax, [rdi+18h]
0x1400882c2  lea     rdx, [rsp+11A8h+var_1148]
0x1400882c7  mov     [rax], rdx
  ... truncated ...
```
