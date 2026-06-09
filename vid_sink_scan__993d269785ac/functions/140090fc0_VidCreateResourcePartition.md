# VidCreateResourcePartition

- ea: `0x140090fc0`
- end: `0x1400918dc`
- name: `VidCreateResourcePartition`
- size: `2332`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140007234`
- `0x1400087b8`
- `0x14000a4e0`
- `0x140021650`
- `0x1400307d0`
- `0x140033900`
- `0x1400769f8`
- `0x140076a7c`
- `0x140090fc0`
- `0x140093f54`
- `0x1400942f8`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400917b8`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400917b8`
- `ntoskrnl!KeReadStateEvent` at `0x14009153f`
- `ntoskrnl!KeReadStateEvent` at `0x14009153f`
- `ntoskrnl!KeSetEvent` at `0x1400915fc`
- `ntoskrnl!KeSetEvent` at `0x1400915fc`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400910ab`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400910ab`

## string_xrefs

- `0x140091141`: `VidCreateResourcePartition`
- `0x1400911ca`: `VidCreateResourcePartition`
- `0x140091256`: `VidCreateResourcePartition`
- `0x14009132e`: `VidCreateResourcePartition`
- `0x140091393`: `VidCreateResourcePartition`
- `0x1400913f8`: `VidCreateResourcePartition`
- `0x1400914ae`: `VidCreateResourcePartition`
- `0x140091583`: `VidCreateResourcePartition`
- `0x140091643`: `VidCreateResourcePartition`
- `0x1400916ba`: `VidCreateResourcePartition`
- `0x1400917fe`: `VidCreateResourcePartition`

## pseudocode

```c
__int64 __fastcall VidCreateResourcePartition(__int64 *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // edi
  _DWORD *v8; // r15
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned int v12; // r14d
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  void *v16; // rcx
  int v17; // r8d
  char *v18; // rdx
  int v19; // eax
  __int64 v20; // r10
  __int128 *v21; // rax
  __int64 v22; // r10
  char *v23; // r14
  __int64 *v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 v27; // r8
  __int64 v28; // r9
  char *v29; // rdx
  int v30; // r8d
  int v31; // r8d
  int v32; // r8d
  unsigned __int64 v33; // rdi
  int v34; // r14d
  unsigned __int64 v35; // rax
  __int64 v36; // r9
  int v38; // [rsp+20h] [rbp-A9h]
  __int64 v39; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v40; // [rsp+38h] [rbp-91h] BYREF
  __int128 v41; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v42[32]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v43[16]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-49h] BYREF
  __int128 *v45; // [rsp+90h] [rbp-39h]
  __int64 v46; // [rsp+98h] [rbp-31h]
  __int64 *v47; // [rsp+A0h] [rbp-29h]
  __int64 v48; // [rsp+A8h] [rbp-21h]
  __int64 *v49; // [rsp+B0h] [rbp-19h]
  __int64 v50; // [rsp+B8h] [rbp-11h]
  __int128 *v51; // [rsp+C0h] [rbp-9h]
  __int64 v52; // [rsp+C8h] [rbp-1h]

  v40 = a1;
  if ( (a4 & 0xFFFFFFFFFFFFFFFCuLL) != 0 )
    return (unsigned int)-1073741811;
  v8 = VidDeviceExtension;
  v9 = VidResourcePartitionpAllocate(a1, 1u);
  if ( !v9 )
    return (unsigned int)-1073741670;
  v11 = 0;
  v12 = 0;
  v39 = 0;
  if ( !a2 )
  {
LABEL_20:
    if ( (a4 & 2) != 0 )
    {
      if ( !*(_QWORD *)(v9 + 96) )
      {
        v7 = -1073741811;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1708;
          v45 = (__int128 *)&v40;
          v18 = byte_1400482B9;
          v47 = &v39;
          v49 = (__int64 *)(v9 + 8);
          v19 = *(_DWORD *)(a3 + 24LL * v12);
LABEL_32:
          LODWORD(v41) = v19;
          v21 = &v41;
LABEL_33:
          v51 = v21;
          LODWORD(v39) = v17;
          v52 = 4;
          v50 = 16;
          v48 = 4;
          v46 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v18, 0, 0, 8, v42);
        }
        goto LABEL_87;
      }
      *(_DWORD *)(v9 + 56) |= 1u;
    }
    v23 = (char *)(v8 + 410);
    *(_QWORD *)&v41 = v8 + 410;
    VidLockAcquireShared(v8 + 410, v11, v10);
    VidPushLockAcquireExclusive(v8 + 550);
    v24 = v40;
    v26 = VidResourcePartitionFindById(v8 + 550, v40);
    if ( v26 )
    {
      if ( (a4 & 1) == 0 )
      {
        v7 = -1073741771;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1736;
          v29 = &byte_1400481FF;
          LODWORD(v39) = -1073741771;
LABEL_49:
          v45 = (__int128 *)&v40;
          v47 = &v39;
          v49 = (__int64 *)(v9 + 8);
          v38 = 7;
LABEL_50:
          v50 = 16;
          v48 = 4;
          v46 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v29, 0, 0, v38, v42);
          goto LABEL_86;
        }
        goto LABEL_86;
      }
      if ( KeReadStateEvent(*(PRKEVENT *)(v26 + 24)) )
      {
        v27 = 3221225860LL;
        v7 = -1073741436;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1747;
          v29 = byte_140048155;
          LODWORD(v39) = v30;
          goto LABEL_49;
        }
LABEL_86:
        VidPushLockRelease(v8 + 550, v25, v27, v28);
        VidLockRelease(v23);
        if ( v9 )
          goto LABEL_87;
        return v7;
      }
      *(_OWORD *)(v26 + 60) = *(_OWORD *)(v9 + 60);
      *(_QWORD *)(v26 + 80) = *(_QWORD *)(v9 + 80);
      *(_QWORD *)(v26 + 88) = *(_QWORD *)(v9 + 88);
      *(_QWORD *)(v26 + 96) = *(_QWORD *)(v9 + 96);
      *(_DWORD *)(v26 + 56) = *(_DWORD *)(v9 + 56);
      *(_QWORD *)(v9 + 80) = 0;
      *(_QWORD *)(v9 + 88) = 0;
      *(_QWORD *)(v9 + 96) = 0;
      *(_DWORD *)(v9 + 56) = 0;
      KeSetEvent(*(PRKEVENT *)(v26 + 24), 0, 0);
    }
    else
    {
      if ( (a4 & 1) != 0 )
      {
        v27 = 3221225860LL;
        v7 = -1073741436;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1766;
          v29 = (char *)word_1400481AA;
          LODWORD(v39) = v31;
          goto LABEL_49;
        }
        goto LABEL_86;
      }
      if ( v8[409] )
      {
        v27 = 3221225860LL;
        v7 = -1073741436;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1781;
          v45 = (__int128 *)&v40;
          v29 = byte_1400480DD;
          LODWORD(v39) = v32;
          v47 = &v39;
          v49 = (__int64 *)(v9 + 8);
          *(_QWORD *)&v41 = (int)v8[409];
          v51 = &v41;
          v38 = 8;
          v52 = 8;
          goto LABEL_50;
        }
        goto LABEL_86;
      }
      v33 = *((_QWORD *)v8 + 276);
      if ( (v8[554] & 1) != 0 )
      {
        if ( v33 )
          v33 ^= (unsigned __int64)(v8 + 552);
        else
          v33 = 0;
      }
      LOBYTE(v27) = 0;
      v34 = v8[554] & 1;
      if ( v33 )
      {
        while ( 1 )
        {
          if ( (int)VidResourcePartitionCompareById(v9 + 8, v33, v27) < 0 )
          {
            v35 = *(_QWORD *)v33;
            if ( v34 )
            {
              if ( !v35 )
                goto LABEL_80;
              v35 ^= v33;
            }
            if ( !v35 )
            {
LABEL_80:
              LOBYTE(v27) = 0;
              break;
            }
          }
          else
          {
            v35 = *(_QWORD *)(v33 + 8);
            if ( v34 )
            {
              if ( !v35 )
                goto LABEL_74;
              v35 ^= v33;
            }
            if ( !v35 )
            {
LABEL_74:
              LOBYTE(v27) = 1;
              break;
            }
          }
          v33 = v35;
        }
      }
      RtlRbInsertNodeEx(v8 + 552, v33, v27, v9 + 32);
      v24 = v40;
      v9 = 0;
      v23 = (char *)v41;
    }
    v28 = 4;
    if ( (unsigned int)dword_140064110 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
      tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      v46 = v36;
      v45 = (__int128 *)&v40;
      LODWORD(v40) = 1797;
      v49 = &v39;
      v47 = v24;
      v51 = &v41;
      v48 = 16;
      v50 = 8;
      *(_QWORD *)&v41 = a4;
      v52 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004807B, 0, 0, 8, v42);
    }
    v7 = 0;
    goto LABEL_86;
  }
  while ( 1 )
  {
    v13 = *(_DWORD *)(a3 + 24LL * v12);
    v11 |= 1LL << v13;
    v39 = v11;
    if ( !v13 )
      break;
    v14 = v13 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        if ( v15 != 1 )
        {
          v7 = -1073741811;
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            goto LABEL_87;
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1695;
          v18 = (char *)&dword_140048254;
          goto LABEL_31;
        }
        v16 = *(void **)(a3 + 24LL * v12 + 8);
        if ( !v16 )
        {
          v7 = -1073741811;
          if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          {
            tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
            tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            LODWORD(v41) = 1678;
            v45 = &v41;
            v18 = byte_140048383;
            v47 = &v39;
            v49 = (__int64 *)(v9 + 8);
            LODWORD(v40) = *(_DWORD *)(a3 + 8 * v20);
            v21 = (__int128 *)&v40;
            goto LABEL_33;
          }
          goto LABEL_87;
        }
        *(_QWORD *)(v9 + 96) = v16;
      }
      else
      {
        v16 = *(void **)(a3 + 24LL * v12 + 8);
        if ( !v16 )
        {
          v7 = -1073741811;
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            goto LABEL_87;
          tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          LODWORD(v40) = 1659;
          v18 = (char *)&word_14004831E;
          goto LABEL_31;
        }
        *(_QWORD *)(v9 + 88) = v16;
      }
    }
    else
    {
      v16 = *(void **)(a3 + 24LL * v12 + 8);
      if ( !v16 )
      {
        v7 = -1073741811;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_87;
        tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
        tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
        LODWORD(v40) = 1641;
        v18 = byte_14004844D;
LABEL_31:
        v45 = (__int128 *)&v40;
        v47 = &v39;
        v49 = (__int64 *)(v9 + 8);
        v19 = *(_DWORD *)(a3 + 8 * v22);
        goto LABEL_32;
      }
      *(_QWORD *)(v9 + 80) = v16;
    }
    ObfReferenceObjectWithTag(v16, 0x72446456u);
    v11 = v39;
LABEL_19:
    if ( ++v12 >= a2 )
      goto LABEL_20;
  }
  v41 = 0;
  if ( *(_OWORD *)(a3 + 24LL * v12 + 8) )
  {
    *(_OWORD *)(v9 + 60) = *(_OWORD *)(a3 + 24LL * v12 + 8);
    goto LABEL_19;
  }
  v7 = -1073741811;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v43, "VidCreateResourcePartition");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    LODWORD(v40) = 1627;
    v18 = (char *)&unk_1400483E8;
    goto LABEL_31;
  }
LABEL_87:
  VidResourcePartitionpFree((PVOID)v9);
  return v7;
}

```

## disassembly

```asm
0x140090fc0  push    rbp
0x140090fc2  push    rbx
0x140090fc3  push    rsi
0x140090fc4  push    rdi
0x140090fc5  push    r12
0x140090fc7  push    r13
0x140090fc9  push    r14
0x140090fcb  push    r15
0x140090fcd  lea     rbp, [rsp-1Fh]
0x140090fd2  sub     rsp, 0E8h
0x140090fd9  mov     rax, cs:__security_cookie
0x140090fe0  xor     rax, rsp
0x140090fe3  mov     [rbp+57h+var_50], rax
0x140090fe7  mov     [rsp+120h+var_E8], rcx
0x140090fec  mov     r12, r9
0x140090fef  mov     rsi, r8
0x140090ff2  mov     edi, edx
0x140090ff4  test    r9, 0FFFFFFFFFFFFFFFCh
0x140090ffb  jz      short loc_140091007
0x140090ffd  mov     edi, 0C000000Dh
0x140091002  jmp     loc_1400918B9
0x140091007  mov     r15, cs:VidDeviceExtension
0x14009100e  mov     dl, 1
0x140091010  call    VidResourcePartitionpAllocate
0x140091015  xor     r11d, r11d
0x140091018  mov     rbx, rax
0x14009101b  test    rax, rax
0x14009101e  jnz     short loc_14009102A
0x140091020  mov     edi, 0C000009Ah
0x140091025  jmp     loc_1400918B9
0x14009102a  mov     rdx, r11
0x14009102d  mov     r14d, r11d
0x140091030  mov     [rsp+120h+var_F0], rdx
0x140091035  test    edi, edi
0x140091037  jz      loc_1400910FC
0x14009103d  mov     r13d, 72446456h
0x140091043  mov     eax, r14d
0x140091046  lea     r10, [rax+rax*2]
0x14009104a  movsxd  rcx, dword ptr [rsi+r10*8]
0x14009104e  bts     rdx, rcx
0x140091052  mov     [rsp+120h+var_F0], rdx
0x140091057  test    ecx, ecx
0x140091059  jz      short loc_1400910C1
0x14009105b  sub     ecx, 1
0x14009105e  jz      short loc_140091096
0x140091060  sub     ecx, 1
0x140091063  jz      short loc_140091082
0x140091065  cmp     ecx, 1
0x140091068  jnz     loc_140091225
0x14009106e  mov     rcx, [rsi+r10*8+8]
0x140091073  test    rcx, rcx
0x140091076  jz      loc_140091199
0x14009107c  mov     [rbx+60h], rcx
0x140091080  jmp     short loc_1400910A8
0x140091082  mov     rcx, [rsi+r10*8+8]
0x140091087  test    rcx, rcx
0x14009108a  jz      loc_1400912FD
0x140091090  mov     [rbx+58h], rcx
0x140091094  jmp     short loc_1400910A8
0x140091096  mov     rcx, [rsi+r10*8+8]; Object
0x14009109b  test    rcx, rcx
0x14009109e  jz      loc_140091362
0x1400910a4  mov     [rbx+50h], rcx
0x1400910a8  mov     edx, r13d; Tag
0x1400910ab  call    cs:__imp_ObfReferenceObjectWithTag
0x1400910b2  nop     dword ptr [rax+rax+00h]
0x1400910b7  mov     rdx, [rsp+120h+var_F0]
0x1400910bc  xor     r11d, r11d
0x1400910bf  jmp     short loc_1400910F0
0x1400910c1  xorps   xmm0, xmm0
0x1400910c4  movq    rax, xmm0
0x1400910c9  movups  [rsp+120h+var_E0], xmm0
0x1400910ce  cmp     [rsi+r10*8+8], rax
0x1400910d3  jnz     short loc_1400910E5
0x1400910d5  mov     rax, [rsi+r10*8+10h]
0x1400910da  cmp     rax, qword ptr [rsp+120h+var_E0+8]
0x1400910df  jz      loc_1400913C7
0x1400910e5  movups  xmm0, xmmword ptr [rsi+r10*8+8]
0x1400910eb  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x1400910f0  inc     r14d
0x1400910f3  cmp     r14d, edi
0x1400910f6  jb      loc_140091043
0x1400910fc  test    r12b, 2
0x140091100  jz      loc_140091430
0x140091106  cmp     [rbx+60h], r11
0x14009110a  jnz     loc_14009142C
0x140091110  mov     eax, cs:dword_140064110
0x140091116  mov     r8d, 0C000000Dh
0x14009111c  mov     edi, r8d
0x14009111f  cmp     eax, 2
0x140091122  jbe     loc_1400918B1
0x140091128  mov     edx, 100h
0x14009112d  lea     rcx, dword_140064110
0x140091134  call    _tlgKeywordOn
0x140091139  test    al, al
0x14009113b  jz      loc_1400918B1
0x140091141  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x140091148  lea     rcx, [rbp+57h+var_B0]
0x14009114c  call    _tlgCreate1Sz_char
0x140091151  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091158  lea     rcx, [rbp+57h+var_A0]
0x14009115c  call    _tlgCreate1Sz_char
0x140091161  lea     rax, [rsp+120h+var_E8]
0x140091166  mov     dword ptr [rsp+120h+var_E8], 6ACh
0x14009116e  mov     [rbp+57h+var_90], rax
0x140091172  lea     rdx, byte_1400482B9
0x140091179  lea     rax, [rsp+120h+var_F0]
0x14009117e  mov     [rbp+57h+var_80], rax
0x140091182  lea     rax, [rbx+8]
0x140091186  mov     [rbp+57h+var_70], rax
0x14009118a  mov     eax, r14d
0x14009118d  lea     rcx, [rax+rax*2]
0x140091191  mov     eax, [rsi+rcx*8]
0x140091194  jmp     loc_1400912A3
0x140091199  mov     eax, cs:dword_140064110
0x14009119f  mov     r8d, 0C000000Dh
0x1400911a5  mov     edi, r8d
0x1400911a8  cmp     eax, 2
0x1400911ab  jbe     loc_1400918B1
0x1400911b1  mov     edx, 100h
0x1400911b6  lea     rcx, dword_140064110
0x1400911bd  call    _tlgKeywordOn
0x1400911c2  test    al, al
0x1400911c4  jz      loc_1400918B1
0x1400911ca  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x1400911d1  lea     rcx, [rbp+57h+var_B0]
0x1400911d5  call    _tlgCreate1Sz_char
0x1400911da  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400911e1  lea     rcx, [rbp+57h+var_A0]
0x1400911e5  call    _tlgCreate1Sz_char
0x1400911ea  lea     rax, [rsp+120h+var_E0]
0x1400911ef  mov     dword ptr [rsp+120h+var_E0], 68Eh
0x1400911f7  mov     [rbp+57h+var_90], rax
0x1400911fb  lea     rdx, byte_140048383
0x140091202  lea     rax, [rsp+120h+var_F0]
0x140091207  mov     [rbp+57h+var_80], rax
0x14009120b  lea     rax, [rbx+8]
0x14009120f  mov     [rbp+57h+var_70], rax
0x140091213  mov     eax, [rsi+r10*8]
0x140091217  mov     dword ptr [rsp+120h+var_E8], eax
0x14009121b  lea     rax, [rsp+120h+var_E8]
0x140091220  jmp     loc_1400912AC
0x140091225  mov     eax, cs:dword_140064110
0x14009122b  mov     r8d, 0C000000Dh
0x140091231  mov     edi, r8d
0x140091234  cmp     eax, 2
0x140091237  jbe     loc_1400918B1
0x14009123d  mov     edx, 100h
0x140091242  lea     rcx, dword_140064110
0x140091249  call    _tlgKeywordOn
0x14009124e  test    al, al
0x140091250  jz      loc_1400918B1
0x140091256  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x14009125d  lea     rcx, [rbp+57h+var_B0]
0x140091261  call    _tlgCreate1Sz_char
0x140091266  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009126d  lea     rcx, [rbp+57h+var_A0]
0x140091271  call    _tlgCreate1Sz_char
0x140091276  mov     dword ptr [rsp+120h+var_E8], 69Fh
0x14009127e  lea     rdx, dword_140048254
0x140091285  lea     rax, [rsp+120h+var_E8]
0x14009128a  mov     [rbp+57h+var_90], rax
0x14009128e  lea     rax, [rsp+120h+var_F0]
0x140091293  mov     [rbp+57h+var_80], rax
0x140091297  lea     rax, [rbx+8]
0x14009129b  mov     [rbp+57h+var_70], rax
0x14009129f  mov     eax, [rsi+r10*8]
0x1400912a3  mov     dword ptr [rsp+120h+var_E0], eax
0x1400912a7  lea     rax, [rsp+120h+var_E0]
0x1400912ac  mov     [rbp+57h+var_60], rax
0x1400912b0  lea     rcx, dword_140064110
0x1400912b7  lea     rax, [rbp+57h+var_D0]
0x1400912bb  mov     dword ptr [rsp+120h+var_F0], r8d
0x1400912c0  mov     [rsp+120h+var_F8], rax
0x1400912c5  xor     r9d, r9d
0x1400912c8  xor     r8d, r8d
0x1400912cb  mov     [rsp+120h+var_100], 8
0x1400912d3  mov     [rbp+57h+var_58], 4
0x1400912db  mov     [rbp+57h+var_68], 10h
0x1400912e3  mov     [rbp+57h+var_78], 4
0x1400912eb  mov     [rbp+57h+var_88], 4
0x1400912f3  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400912f8  jmp     loc_1400918B1
0x1400912fd  mov     eax, cs:dword_140064110
0x140091303  mov     r8d, 0C000000Dh
0x140091309  mov     edi, r8d
0x14009130c  cmp     eax, 2
0x14009130f  jbe     loc_1400918B1
0x140091315  mov     edx, 100h
0x14009131a  lea     rcx, dword_140064110
0x140091321  call    _tlgKeywordOn
0x140091326  test    al, al
0x140091328  jz      loc_1400918B1
0x14009132e  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x140091335  lea     rcx, [rbp+57h+var_B0]
0x140091339  call    _tlgCreate1Sz_char
0x14009133e  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140091345  lea     rcx, [rbp+57h+var_A0]
0x140091349  call    _tlgCreate1Sz_char
0x14009134e  mov     dword ptr [rsp+120h+var_E8], 67Bh
0x140091356  lea     rdx, word_14004831E
0x14009135d  jmp     loc_140091285
0x140091362  mov     eax, cs:dword_140064110
0x140091368  mov     r8d, 0C000000Dh
0x14009136e  mov     edi, r8d
0x140091371  cmp     eax, 2
0x140091374  jbe     loc_1400918B1
0x14009137a  mov     edx, 100h
0x14009137f  lea     rcx, dword_140064110
0x140091386  call    _tlgKeywordOn
0x14009138b  test    al, al
0x14009138d  jz      loc_1400918B1
0x140091393  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x14009139a  lea     rcx, [rbp+57h+var_B0]
0x14009139e  call    _tlgCreate1Sz_char
0x1400913a3  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400913aa  lea     rcx, [rbp+57h+var_A0]
0x1400913ae  call    _tlgCreate1Sz_char
0x1400913b3  mov     dword ptr [rsp+120h+var_E8], 669h
0x1400913bb  lea     rdx, byte_14004844D
0x1400913c2  jmp     loc_140091285
0x1400913c7  mov     eax, cs:dword_140064110
0x1400913cd  mov     r8d, 0C000000Dh
0x1400913d3  mov     edi, r8d
0x1400913d6  cmp     eax, 2
0x1400913d9  jbe     loc_1400918B1
0x1400913df  mov     edx, 100h
0x1400913e4  lea     rcx, dword_140064110
0x1400913eb  call    _tlgKeywordOn
0x1400913f0  test    al, al
0x1400913f2  jz      loc_1400918B1
0x1400913f8  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x1400913ff  lea     rcx, [rbp+57h+var_B0]
0x140091403  call    _tlgCreate1Sz_char
0x140091408  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x14009140f  lea     rcx, [rbp+57h+var_A0]
0x140091413  call    _tlgCreate1Sz_char
0x140091418  mov     dword ptr [rsp+120h+var_E8], 65Bh
0x140091420  lea     rdx, unk_1400483E8
0x140091427  jmp     loc_140091285
0x14009142c  or      dword ptr [rbx+38h], 1
0x140091430  lea     r14, [r15+668h]
0x140091437  mov     rcx, r14
0x14009143a  mov     qword ptr [rsp+120h+var_E0], r14
0x14009143f  lea     r13, [r15+898h]
0x140091446  call    VidLockAcquireShared
0x14009144b  mov     rcx, r13
0x14009144e  call    VidPushLockAcquireExclusive
0x140091453  mov     rsi, [rsp+120h+var_E8]
0x140091458  mov     rcx, r13
0x14009145b  mov     rdx, rsi
0x14009145e  call    VidResourcePartitionFindById
0x140091463  mov     rdi, rax
0x140091466  xor     r10d, r10d
0x140091469  mov     rax, r12
0x14009146c  and     eax, 1
0x14009146f  test    rdi, rdi
0x140091472  jz      loc_14009160D
0x140091478  test    rax, rax
0x14009147b  jnz     loc_14009153B
0x140091481  mov     eax, cs:dword_140064110
0x140091487  mov     edi, 0C0000035h
0x14009148c  cmp     eax, 2
0x14009148f  jbe     loc_14009189C
0x140091495  mov     edx, 100h
0x14009149a  lea     rcx, dword_140064110
0x1400914a1  call    _tlgKeywordOn
0x1400914a6  test    al, al
0x1400914a8  jz      loc_14009189C
0x1400914ae  lea     rdx, aVidcreateresou; "VidCreateResourcePartition"
0x1400914b5  lea     rcx, [rbp+57h+var_B0]
0x1400914b9  call    _tlgCreate1Sz_char
0x1400914be  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400914c5  lea     rcx, [rbp+57h+var_A0]
0x1400914c9  call    _tlgCreate1Sz_char
0x1400914ce  mov     dword ptr [rsp+120h+var_E8], 6C8h
0x1400914d6  lea     rdx, byte_1400481FF
0x1400914dd  mov     dword ptr [rsp+120h+var_F0], edi
0x1400914e1  lea     rax, [rsp+120h+var_E8]
0x1400914e6  mov     [rbp+57h+var_90], rax
0x1400914ea  lea     rax, [rsp+120h+var_F0]
0x1400914ef  mov     [rbp+57h+var_80], rax
0x1400914f3  lea     rax, [rbx+8]
0x1400914f7  mov     [rbp+57h+var_70], rax
0x1400914fb  lea     rax, [rbp+57h+var_D0]
0x1400914ff  mov     [rsp+120h+var_F8], rax
0x140091504  mov     [rsp+120h+var_100], 7
0x14009150c  xor     r9d, r9d
0x14009150f  mov     [rbp+57h+var_68], 10h
0x140091517  xor     r8d, r8d
0x14009151a  mov     [rbp+57h+var_78], 4
0x140091522  lea     rcx, dword_140064110
0x140091529  mov     [rbp+57h+var_88], 4
0x140091531  call    _tlgWriteTransfer_EtwWriteTransfer
0x140091536  jmp     loc_14009189C
0x14009153b  mov     rcx, [rdi+18h]; Event
0x14009153f  call    cs:__imp_KeReadStateEvent
0x140091546  nop     dword ptr [rax+rax+00h]
0x14009154b  xor     r10d, r10d
0x14009154e  test    eax, eax
  ... truncated ...
```
