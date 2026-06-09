# TranslateToExtendedSrb

- ea: `0x14002da00`
- end: `0x14002e03a`
- name: `TranslateToExtendedSrb`
- size: `1594`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000b0c0`

## callees

- `0x14002da00`
- `0x14002e040`
- `0x140066e18`
- `0x14014b500`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002df35`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002df46`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002df35`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002df46`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14002dcb9`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14002dd2f`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14002dcb9`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14002dd2f`
- `HAL!KeQueryPerformanceCounter` at `0x14002da51`
- `HAL!KeQueryPerformanceCounter` at `0x14002dd95`
- `HAL!KeQueryPerformanceCounter` at `0x14002da51`
- `HAL!KeQueryPerformanceCounter` at `0x14002dd95`

## pseudocode

```c
__int64 __fastcall TranslateToExtendedSrb(__int64 a1, __int64 a2, unsigned int a3, char a4, __int64 a5, char a6)
{
  unsigned __int64 v6; // r12
  int v9; // r15d
  LARGE_INTEGER v10; // rax
  LARGE_INTEGER v11; // rbx
  char v12; // bp
  unsigned int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  char v16; // cl
  int v17; // eax
  _DWORD *v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rbp
  __int64 v23; // rdx
  int v24; // ecx
  __int64 v25; // r14
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  __int64 v29; // rdx
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v31; // rdx
  unsigned int LowPart; // ecx
  unsigned __int64 v33; // r8
  char v34; // r10
  unsigned __int64 v35; // r9
  char v37; // al
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp+8h] BYREF
  int v39; // [rsp+88h] [rbp+20h] BYREF

  LOBYTE(v39) = a4;
  v6 = a3;
  PerformanceFrequency.QuadPart = 1;
  if ( !a1 || !a2 )
    return 3221225485LL;
  v9 = 0;
  if ( UseQPCTime )
    v10 = KeQueryPerformanceCounter(&PerformanceFrequency);
  else
    v10.QuadPart = KeQueryUnbiasedInterruptTime();
  v11 = v10;
  if ( *(_BYTE *)(a2 + 2) )
  {
    switch ( *(_BYTE *)(a2 + 2) )
    {
      case 1:
      case 2:
      case 4:
      case 6:
      case 7:
      case 8:
      case 9:
      case 0x10:
      case 0x12:
      case 0x13:
      case 0x15:
      case 0x18:
      case 0x19:
      case 0x1A:
      case 0x20:
      case 0x26:
        if ( (unsigned int)v6 < 0x90 )
          goto LABEL_68;
        TranslateScsiRequestBlockToStorageRequestBlock(a1, a2, 0, 0, 144);
        goto LABEL_50;
      case 0x17:
        if ( (unsigned int)v6 < 0xA8 )
          goto LABEL_68;
        TranslateScsiRequestBlockToStorageRequestBlock(a1, a2, 1, 0, 168);
        *(_DWORD *)(a1 + 120) = 144;
        *(_DWORD *)(a1 + 144) = 96;
        *(_DWORD *)(a1 + 148) = 16;
        *(_BYTE *)(a1 + 152) = *(_BYTE *)(a2 + 4);
        *(_BYTE *)(a1 + 153) = *(_BYTE *)(a2 + 9);
        *(_QWORD *)(a1 + 160) = *(_QWORD *)(a2 + 32);
        goto LABEL_50;
      case 0x24:
        if ( (unsigned int)v6 < 0xA8 )
          goto LABEL_68;
        TranslateScsiRequestBlockToStorageRequestBlock(a1, a2, 1, 0, 168);
        *(_DWORD *)(a1 + 120) = 144;
        *(_DWORD *)(a1 + 144) = 97;
        *(_DWORD *)(a1 + 148) = 12;
        goto LABEL_95;
      case 0x25:
        if ( (unsigned int)v6 < 0xA8 )
          goto LABEL_68;
        TranslateScsiRequestBlockToStorageRequestBlock(a1, a2, 1, 0, 168);
        *(_DWORD *)(a1 + 120) = 144;
        *(_DWORD *)(a1 + 144) = 98;
        *(_DWORD *)(a1 + 148) = 16;
LABEL_95:
        *(_BYTE *)(a1 + 152) = *(_BYTE *)(a2 + 4);
        *(_DWORD *)(a1 + 156) = *(_DWORD *)(a2 + 8);
        *(_DWORD *)(a1 + 160) = *(_DWORD *)(a2 + 64);
        goto LABEL_50;
      default:
        v9 = -1073741811;
        goto LABEL_52;
    }
  }
  v12 = a6;
  v13 = 224;
  if ( a6 != 1 )
    v13 = 184;
  if ( (unsigned int)v6 < v13 )
    goto LABEL_68;
  *(_DWORD *)(a1 + 16) = v13;
  v14 = 2;
  *(_WORD *)(a1 + 36) = 2;
  *(_WORD *)a1 = 8;
  *(_BYTE *)(a1 + 2) = 40;
  *(_DWORD *)(a1 + 8) = 1397899864;
  *(_DWORD *)(a1 + 12) = 1;
  *(_DWORD *)(a1 + 52) = 128;
  if ( v12 )
    *(_DWORD *)(a1 + 52) = 136;
  else
    v14 = 1;
  *(_DWORD *)(a1 + 56) = v14;
  *(_DWORD *)(a1 + 20) = *(unsigned __int8 *)(a2 + 2);
  *(_BYTE *)(a1 + 3) = *(_BYTE *)(a2 + 3);
  *(_DWORD *)(a1 + 24) = *(_DWORD *)(a2 + 12);
  *(_DWORD *)(a1 + 60) = *(_DWORD *)(a2 + 16);
  *(_QWORD *)(a1 + 64) = *(_QWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 20);
  *(_QWORD *)(a1 + 104) = *(_QWORD *)(a2 + 56);
  if ( *(_BYTE *)(a2 + 2) == 23 )
    v15 = 0;
  else
    v15 = *(_QWORD *)(a2 + 40);
  *(_QWORD *)(a1 + 112) = v15;
  v16 = *(_BYTE *)(a2 + 2);
  if ( (unsigned __int8)(v16 - 36) <= 1u || v16 == 23 )
  {
    v17 = 0;
    *(_DWORD *)(a1 + 32) = 0;
    *(_WORD *)(a1 + 38) = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 32) = *(unsigned __int8 *)(a2 + 8);
    *(_WORD *)(a1 + 38) = *(unsigned __int8 *)(a2 + 9);
    v17 = *(_DWORD *)(a2 + 64);
  }
  *(_DWORD *)(a1 + 44) = v17;
  v18 = *(_DWORD **)(a2 + 48);
  if ( v18 )
  {
    if ( *v18 == 523124044 )
    {
      *(_QWORD *)(a1 + 96) = v18;
      *(_QWORD *)(a1 + 80) = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 176LL);
    }
    else
    {
      *(_QWORD *)(a1 + 80) = v18;
      *(_QWORD *)(a1 + 96) = *(_QWORD *)(a2 + 56);
    }
  }
  v19 = 152;
  v20 = 152;
  if ( v12 != 1 )
  {
    v20 = 144;
    v19 = 144;
  }
  *(_DWORD *)(a1 + 120) = v20;
  if ( v19 + 40 > v6 )
  {
    v9 = -1073741670;
  }
  else
  {
    *(_DWORD *)(v19 + a1) = 64;
    v21 = v19 + a1;
    *(_DWORD *)(v19 + a1 + 4) = 32;
    *(_BYTE *)(v19 + a1 + 10) = *(_BYTE *)(a2 + 10);
    *(_BYTE *)(v19 + a1 + 8) = *(_BYTE *)(a2 + 4);
    *(_BYTE *)(v19 + a1 + 9) = *(_BYTE *)(a2 + 11);
    *(_QWORD *)(v19 + a1 + 16) = *(_QWORD *)(a2 + 32);
    if ( *(_BYTE *)(a2 + 10) )
      memmove((void *)(v21 + 24), (const void *)(a2 + 72), *(unsigned __int8 *)(a2 + 10));
    else
      *(_OWORD *)(v21 + 24) = 0;
  }
  if ( v12 != 1 || *(_DWORD *)(a1 + 56) <= 1u )
    goto LABEL_49;
  *(_DWORD *)(a1 + 124) = 192;
  if ( v6 < 0xE0 )
    goto LABEL_68;
  v22 = a5;
  if ( !a5 )
  {
    v22 = *(_QWORD *)(a2 + 48);
    if ( !v22 )
      goto LABEL_49;
  }
  v23 = *(_QWORD *)(v22 + 192);
  v24 = 0;
  v25 = *(_QWORD *)(v22 + 184);
  *(_DWORD *)(a1 + 192) = 128;
  *(_QWORD *)(a1 + 196) = 24;
  if ( (*(_DWORD *)(v22 + 16) & 1) != 0 )
  {
    *(_DWORD *)(a1 + 200) = 1;
    v24 = 1;
  }
  if ( (*(_DWORD *)(v22 + 16) & 0x42) != 0 )
  {
    v24 |= 2u;
    *(_DWORD *)(a1 + 200) = v24;
  }
  if ( !v23 )
  {
    v26 = v24 | 0x40;
    goto LABEL_40;
  }
  if ( (*(_DWORD *)(v23 + 80) & 0x20) != 0 )
  {
    v24 |= 4u;
    *(_DWORD *)(a1 + 200) = v24;
  }
  if ( (*(_DWORD *)(v23 + 80) & 0x18000) != 0 )
  {
    v24 |= 8u;
    *(_DWORD *)(a1 + 200) = v24;
  }
  if ( (*(_DWORD *)(v23 + 80) & 0x10) != 0 )
  {
    v26 = v24 | 0x10;
LABEL_40:
    *(_DWORD *)(a1 + 200) = v26;
  }
  v39 = 0;
  if ( (int)IoGetGenericIrpExtension(v22, &v39, 4) >= 0 && (v39 & 0x20) != 0 )
    *(_DWORD *)(a1 + 200) |= 0x20u;
  if ( v25 )
  {
    if ( *(_BYTE *)v25 == 3 )
    {
      v27 = *(_DWORD *)(v25 + 16);
      *(_DWORD *)(a1 + 204) = v27;
      v28 = *(_DWORD *)(v25 + 8);
    }
    else
    {
      if ( *(_BYTE *)v25 == 4 )
      {
        v27 = *(_DWORD *)(v25 + 16);
        *(_DWORD *)(a1 + 204) = v27;
        v28 = *(_DWORD *)(v25 + 8);
        *(_BYTE *)(a1 + 212) = 1;
LABEL_46:
        *(_DWORD *)(a1 + 208) = v28;
        if ( (v27 & 0xFFFF0000) == 0x56530000 )
          *(_DWORD *)(a1 + 200) |= 0x80u;
        goto LABEL_48;
      }
      v28 = 0;
      *(_DWORD *)(a1 + 204) = 0;
      v27 = 0;
    }
    *(_BYTE *)(a1 + 212) = 0;
    goto LABEL_46;
  }
  *(_QWORD *)(a1 + 204) = 0;
  *(_BYTE *)(a1 + 212) = 0;
LABEL_48:
  v39 = 0;
  if ( (int)IoGetGenericIrpExtension(v22, &v39, 4) >= 0 )
  {
    v37 = v39;
    if ( (v39 & 0x10) != 0 )
    {
      *(_DWORD *)(a1 + 200) |= 0x80000000;
      *(_BYTE *)(a1 + 213) = v37 & 0xF;
    }
  }
LABEL_49:
  if ( v9 >= 0 )
  {
LABEL_50:
    v29 = *(unsigned int *)(a1 + 52);
    if ( v29 + 16 <= v6 )
    {
      *(_DWORD *)(v29 + a1) = 1;
      *(_DWORD *)(v29 + a1 + 4) = 4;
      *(_BYTE *)(v29 + a1 + 8) = *(_BYTE *)(a2 + 5);
      *(_BYTE *)(v29 + a1 + 9) = *(_BYTE *)(a2 + 6);
      *(_BYTE *)(v29 + a1 + 10) = *(_BYTE *)(a2 + 7);
      goto LABEL_52;
    }
LABEL_68:
    v9 = -1073741670;
  }
LABEL_52:
  if ( UseQPCTime )
    PerformanceCounter = KeQueryPerformanceCounter(0);
  else
    PerformanceCounter.QuadPart = KeQueryUnbiasedInterruptTime();
  if ( PerformanceCounter.QuadPart > 0 && PerformanceCounter.QuadPart < v11.QuadPart )
    v33 = PerformanceCounter.QuadPart - v11.QuadPart - 1;
  else
    v33 = PerformanceCounter.QuadPart - v11.QuadPart;
  if ( UseQPCTime )
  {
    LowPart = PerformanceFrequency.LowPart;
    v34 = 0;
    if ( PerformanceFrequency.QuadPart && v33 )
    {
      v35 = 1000 * (v33 % PerformanceFrequency.QuadPart);
      v33 = v35 / PerformanceFrequency.QuadPart + 1000 * (v33 / PerformanceFrequency.QuadPart);
      v31.QuadPart = 10000 * (v35 % PerformanceFrequency.QuadPart) % PerformanceFrequency.QuadPart;
      v34 = 10000 * (v35 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart + 16 * v33;
    }
  }
  else
  {
    v34 = v33;
  }
  if ( (Microsoft_Windows_StorPortEnableBits & 0x40) != 0 )
    McTemplateK0zx_EtwWriteTransfer(LowPart, v31.LowPart, v33, (unsigned int)L"Translate SCSI_REQUEST_BLOCK", v34);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002da00  mov     byte ptr [rsp+arg_18], r9b
0x14002da05  push    rsi
0x14002da06  push    rdi
0x14002da07  push    r12
0x14002da09  push    r13
0x14002da0b  push    r15
0x14002da0d  sub     rsp, 40h
0x14002da11  mov     r12d, r8d
0x14002da14  mov     r13d, 1
0x14002da1a  mov     qword ptr [rsp+68h+PerformanceFrequency], r13
0x14002da1f  mov     rsi, rdx
0x14002da22  mov     rdi, rcx
0x14002da25  test    rcx, rcx
0x14002da28  jz      loc_14002DEB6
0x14002da2e  test    rdx, rdx
0x14002da31  jz      loc_14002DEB6
0x14002da37  xor     r15d, r15d
0x14002da3a  mov     [rsp+68h+arg_8], rbx
0x14002da3f  cmp     cs:UseQPCTime, r15b
0x14002da46  jz      loc_14002DF35
0x14002da4c  lea     rcx, [rsp+68h+PerformanceFrequency]; PerformanceFrequency
0x14002da51  call    cs:__imp_KeQueryPerformanceCounter
0x14002da58  nop     dword ptr [rax+rax+00h]
0x14002da5d  mov     rbx, rax
0x14002da60  mov     [rsp+68h+var_30], rbp
0x14002da65  movzx   eax, byte ptr [rsi+2]
0x14002da69  mov     [rsp+68h+var_38], r14
0x14002da6e  test    eax, eax
0x14002da70  jnz     loc_14002DE60
0x14002da76  movzx   ebp, [rsp+68h+arg_28]
0x14002da7e  mov     eax, 0E0h
0x14002da83  cmp     bpl, r13b
0x14002da86  mov     ecx, 0B8h
0x14002da8b  cmovnz  eax, ecx
0x14002da8e  cmp     r12d, eax
0x14002da91  jb      loc_14002DE9B
0x14002da97  mov     [rdi+10h], eax
0x14002da9a  mov     eax, 2
0x14002da9f  mov     [rdi+24h], ax
0x14002daa3  mov     word ptr [rdi], 8
0x14002daa8  mov     byte ptr [rdi+2], 28h ; '('
0x14002daac  mov     dword ptr [rdi+8], 53524258h
0x14002dab3  mov     [rdi+0Ch], r13d
0x14002dab7  mov     dword ptr [rdi+34h], 80h
0x14002dabe  test    bpl, bpl
0x14002dac1  jz      loc_14002E032
0x14002dac7  mov     dword ptr [rdi+34h], 88h
0x14002dace  mov     [rdi+38h], eax
0x14002dad1  movzx   eax, byte ptr [rsi+2]
0x14002dad5  mov     [rdi+14h], eax
0x14002dad8  movzx   eax, byte ptr [rsi+3]
0x14002dadc  mov     [rdi+3], al
0x14002dadf  mov     eax, [rsi+0Ch]
0x14002dae2  mov     [rdi+18h], eax
0x14002dae5  mov     eax, [rsi+10h]
0x14002dae8  mov     [rdi+3Ch], eax
0x14002daeb  mov     rax, [rsi+18h]
0x14002daef  mov     [rdi+40h], rax
0x14002daf3  mov     eax, [rsi+14h]
0x14002daf6  mov     [rdi+28h], eax
0x14002daf9  mov     rax, [rsi+38h]
0x14002dafd  mov     [rdi+68h], rax
0x14002db01  cmp     byte ptr [rsi+2], 17h
0x14002db05  jz      loc_14002DF99
0x14002db0b  mov     rax, [rsi+28h]
0x14002db0f  mov     [rdi+70h], rax
0x14002db13  movzx   ecx, byte ptr [rsi+2]
0x14002db17  lea     eax, [rcx-24h]
0x14002db1a  cmp     al, r13b
0x14002db1d  jbe     loc_14002DF57
0x14002db23  cmp     cl, 17h
0x14002db26  jz      loc_14002DF57
0x14002db2c  movzx   eax, byte ptr [rsi+8]
0x14002db30  mov     [rdi+20h], eax
0x14002db33  movzx   eax, byte ptr [rsi+9]
0x14002db37  mov     [rdi+26h], ax
0x14002db3b  mov     eax, [rsi+40h]
0x14002db3e  mov     [rdi+2Ch], eax
0x14002db41  mov     rax, [rsi+30h]
0x14002db45  test    rax, rax
0x14002db48  jz      short loc_14002DB62
0x14002db4a  cmp     dword ptr [rax], 1F2E3D4Ch
0x14002db50  jz      loc_14002DF81
0x14002db56  mov     [rdi+50h], rax
0x14002db5a  mov     rax, [rsi+38h]
0x14002db5e  mov     [rdi+60h], rax
0x14002db62  cmp     bpl, r13b
0x14002db65  mov     ecx, 98h
0x14002db6a  mov     eax, ecx
0x14002db6c  mov     r9d, 90h
0x14002db72  cmovnz  eax, r9d
0x14002db76  cmovnz  ecx, r9d
0x14002db7a  mov     [rdi+78h], eax
0x14002db7d  lea     rax, [rcx+28h]
0x14002db81  cmp     rax, r12
0x14002db84  ja      loc_14002DFA0
0x14002db8a  mov     dword ptr [rcx+rdi], 40h ; '@'
0x14002db91  lea     r9, [rcx+rdi]
0x14002db95  mov     dword ptr [rcx+rdi+4], 20h ; ' '
0x14002db9d  movzx   eax, byte ptr [rsi+0Ah]
0x14002dba1  mov     [rcx+rdi+0Ah], al
0x14002dba5  movzx   eax, byte ptr [rsi+4]
0x14002dba9  mov     [rcx+rdi+8], al
0x14002dbad  movzx   eax, byte ptr [rsi+0Bh]
0x14002dbb1  mov     [rcx+rdi+9], al
0x14002dbb5  mov     rax, [rsi+20h]
0x14002dbb9  mov     [rcx+rdi+10h], rax
0x14002dbbe  movzx   eax, byte ptr [rsi+0Ah]
0x14002dbc2  test    al, al
0x14002dbc4  jz      loc_14002DFAB
0x14002dbca  mov     r8d, eax; Size
0x14002dbcd  lea     rdx, [rsi+48h]; Src
0x14002dbd1  lea     rcx, [r9+18h]; void *
0x14002dbd5  call    memmove
0x14002dbda  cmp     bpl, r13b
0x14002dbdd  jnz     loc_14002DD43
0x14002dbe3  cmp     [rdi+38h], r13d
0x14002dbe7  jbe     loc_14002DD43
0x14002dbed  mov     dword ptr [rdi+7Ch], 0C0h
0x14002dbf4  cmp     r12, 0E0h
0x14002dbfb  jb      loc_14002DE9B
0x14002dc01  mov     rbp, [rsp+68h+arg_20]
0x14002dc09  test    rbp, rbp
0x14002dc0c  jnz     short loc_14002DC1B
0x14002dc0e  mov     rbp, [rsi+30h]
0x14002dc12  test    rbp, rbp
0x14002dc15  jz      loc_14002DD43
0x14002dc1b  mov     rdx, [rbp+0C0h]
0x14002dc22  xor     ecx, ecx
0x14002dc24  mov     r14, [rbp+0B8h]
0x14002dc2b  mov     dword ptr [rdi+0C0h], 80h
0x14002dc35  mov     qword ptr [rdi+0C4h], 18h
0x14002dc40  mov     eax, [rbp+10h]
0x14002dc43  test    r13b, al
0x14002dc46  jz      short loc_14002DC52
0x14002dc48  mov     [rdi+0C8h], r13d
0x14002dc4f  mov     ecx, r13d
0x14002dc52  mov     eax, [rbp+10h]
0x14002dc55  test    al, 42h
0x14002dc57  jz      short loc_14002DC62
0x14002dc59  or      ecx, 2
0x14002dc5c  mov     [rdi+0C8h], ecx
0x14002dc62  test    rdx, rdx
0x14002dc65  jz      loc_14002DEAE
0x14002dc6b  mov     eax, [rdx+50h]
0x14002dc6e  test    al, 20h
0x14002dc70  jz      short loc_14002DC7B
0x14002dc72  or      ecx, 4
0x14002dc75  mov     [rdi+0C8h], ecx
0x14002dc7b  test    dword ptr [rdx+50h], 18000h
0x14002dc82  jz      short loc_14002DC8D
0x14002dc84  or      ecx, 8
0x14002dc87  mov     [rdi+0C8h], ecx
0x14002dc8d  mov     eax, [rdx+50h]
0x14002dc90  test    al, 10h
0x14002dc92  jz      short loc_14002DC9D
0x14002dc94  or      ecx, 10h
0x14002dc97  mov     [rdi+0C8h], ecx
0x14002dc9d  mov     r8d, 4
0x14002dca3  mov     [rsp+68h+arg_18], 0
0x14002dcae  lea     rdx, [rsp+68h+arg_18]
0x14002dcb6  mov     rcx, rbp
0x14002dcb9  call    cs:__imp_IoGetGenericIrpExtension
0x14002dcc0  nop     dword ptr [rax+rax+00h]
0x14002dcc5  test    eax, eax
0x14002dcc7  jns     loc_14002DEE2
0x14002dccd  test    r14, r14
0x14002dcd0  jz      loc_14002DECB
0x14002dcd6  movzx   eax, byte ptr [r14]
0x14002dcda  cmp     al, 3
0x14002dcdc  jnz     loc_14002DE3E
0x14002dce2  mov     eax, [r14+10h]
0x14002dce6  mov     [rdi+0CCh], eax
0x14002dcec  mov     ecx, [r14+8]
0x14002dcf0  mov     byte ptr [rdi+0D4h], 0
0x14002dcf7  and     eax, 0FFFF0000h
0x14002dcfc  mov     [rdi+0D0h], ecx
0x14002dd02  cmp     eax, 56530000h
0x14002dd07  jnz     short loc_14002DD13
0x14002dd09  or      dword ptr [rdi+0C8h], 80h
0x14002dd13  mov     r8d, 4
0x14002dd19  mov     [rsp+68h+arg_18], 0
0x14002dd24  lea     rdx, [rsp+68h+arg_18]
0x14002dd2c  mov     rcx, rbp
0x14002dd2f  call    cs:__imp_IoGetGenericIrpExtension
0x14002dd36  nop     dword ptr [rax+rax+00h]
0x14002dd3b  test    eax, eax
0x14002dd3d  jns     loc_14002DEFC
0x14002dd43  test    r15d, r15d
0x14002dd46  js      short loc_14002DD7C
0x14002dd48  mov     edx, [rdi+34h]
0x14002dd4b  lea     rcx, [rdx+10h]
0x14002dd4f  cmp     rcx, r12
0x14002dd52  ja      loc_14002DE9B
0x14002dd58  mov     [rdx+rdi], r13d
0x14002dd5c  mov     dword ptr [rdx+rdi+4], 4
0x14002dd64  movzx   eax, byte ptr [rsi+5]
0x14002dd68  mov     [rdx+rdi+8], al
0x14002dd6c  movzx   eax, byte ptr [rsi+6]
0x14002dd70  mov     [rdx+rdi+9], al
0x14002dd74  movzx   eax, byte ptr [rsi+7]
0x14002dd78  mov     [rdx+rdi+0Ah], al
0x14002dd7c  cmp     cs:UseQPCTime, 0
0x14002dd83  mov     r14, [rsp+68h+var_38]
0x14002dd88  mov     rbp, [rsp+68h+var_30]
0x14002dd8d  jz      loc_14002DF46
0x14002dd93  xor     ecx, ecx; PerformanceFrequency
0x14002dd95  call    cs:__imp_KeQueryPerformanceCounter
0x14002dd9c  nop     dword ptr [rax+rax+00h]
0x14002dda1  mov     r8, rax
0x14002dda4  test    rax, rax
0x14002dda7  jle     short loc_14002DDB2
0x14002dda9  cmp     rax, rbx
0x14002ddac  jl      loc_14002DEC0
0x14002ddb2  sub     r8, rbx
0x14002ddb5  cmp     cs:UseQPCTime, 0
0x14002ddbc  mov     rbx, [rsp+68h+arg_8]
0x14002ddc1  jz      loc_14002DEA6
0x14002ddc7  mov     rcx, qword ptr [rsp+68h+PerformanceFrequency]
0x14002ddcc  xor     r10d, r10d
0x14002ddcf  test    rcx, rcx
0x14002ddd2  jz      short loc_14002DE20
0x14002ddd4  test    r8, r8
0x14002ddd7  jz      short loc_14002DE20
0x14002ddd9  xor     edx, edx
0x14002dddb  mov     rax, r8
0x14002ddde  div     rcx
0x14002dde1  mov     rax, r8
0x14002dde4  imul    r9, rdx, 3E8h
0x14002ddeb  xor     edx, edx
0x14002dded  div     rcx
0x14002ddf0  xor     edx, edx
0x14002ddf2  imul    r8, rax, 3E8h
0x14002ddf9  mov     rax, r9
0x14002ddfc  div     rcx
0x14002ddff  xor     edx, edx
0x14002de01  add     r8, rax
0x14002de04  mov     rax, r9
0x14002de07  div     rcx
0x14002de0a  imul    r10, r8, 2710h
0x14002de11  imul    rax, rdx, 2710h
0x14002de18  xor     edx, edx
0x14002de1a  div     rcx
0x14002de1d  add     r10, rax
0x14002de20  test    cs:Microsoft_Windows_StorPortEnableBits, 40h
0x14002de27  jnz     loc_14002DFB8
0x14002de2d  mov     eax, r15d
0x14002de30  add     rsp, 40h
0x14002de34  pop     r15
0x14002de36  pop     r13
0x14002de38  pop     r12
0x14002de3a  pop     rdi
0x14002de3b  pop     rsi
0x14002de3c  retn
0x14002de3e  cmp     al, 4
0x14002de40  jnz     loc_14002DF22
0x14002de46  mov     eax, [r14+10h]
0x14002de4a  mov     [rdi+0CCh], eax
0x14002de50  mov     ecx, [r14+8]
0x14002de54  mov     [rdi+0D4h], r13b
0x14002de5b  jmp     loc_14002DCF7
0x14002de60  dec     eax; switch 40 cases
0x14002de62  cmp     eax, 27h
0x14002de65  ja      def_14002DE86; jumptable 000000014002DE86 default case, cases 3,5,10-15,17,20,22,27-31,33-35,39,40
0x14002de6b  lea     rdx, cs:140000000h
0x14002de72  cdqe
0x14002de74  movzx   eax, ds:(byte_140163A0F - 140000000h)[rdx+rax]
0x14002de7c  mov     ecx, ds:(jpt_14002DE86 - 140000000h)[rdx+rax*4]
0x14002de83  add     rcx, rdx
0x14002de86  jmp     rcx; switch jump
0x14002de8c  mov     r9d, 90h; jumptable 000000014002DE86 cases 1,2,4,6-9,16,18,19,21,24-26,32,38
0x14002de92  cmp     r12d, r9d
0x14002de95  jnb     loc_14002DF66
0x14002de9b  mov     r15d, 0C000009Ah
0x14002dea1  jmp     loc_14002DD7C
0x14002dea6  mov     r10, r8
0x14002dea9  jmp     loc_14002DE20
0x14002deae  or      ecx, 40h
0x14002deb1  jmp     loc_14002DC97
0x14002deb6  mov     eax, 0C000000Dh
0x14002debb  jmp     loc_14002DE30
0x14002dec0  sub     r8, rbx
0x14002dec3  dec     r8
0x14002dec6  jmp     loc_14002DDB5
0x14002decb  mov     qword ptr [rdi+0CCh], 0
0x14002ded6  mov     byte ptr [rdi+0D4h], 0
0x14002dedd  jmp     loc_14002DD13
0x14002dee2  test    byte ptr [rsp+68h+arg_18], 20h
0x14002deea  jz      loc_14002DCCD
0x14002def0  or      dword ptr [rdi+0C8h], 20h
0x14002def7  jmp     loc_14002DCCD
0x14002defc  mov     eax, [rsp+68h+arg_18]
0x14002df03  test    al, 10h
0x14002df05  jz      loc_14002DD43
0x14002df0b  or      dword ptr [rdi+0C8h], 80000000h
0x14002df15  and     al, 0Fh
0x14002df17  mov     [rdi+0D5h], al
0x14002df1d  jmp     loc_14002DD43
0x14002df22  xor     ecx, ecx
0x14002df24  mov     dword ptr [rdi+0CCh], 0
  ... truncated ...
```
