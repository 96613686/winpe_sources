# VsmmVaGpaRangepCreate

- ea: `0x1400f5dc8`
- end: `0x1400f675b`
- name: `VsmmVaGpaRangepCreate`
- size: `2451`
- prototype: `__int64 __usercall@<rax>(PVOID P@<rcx>, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1400d5d40`
- `0x1400f5d94`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140028954`
- `0x14002e080`
- `0x14002f524`
- `0x1400303c0`
- `0x140033860`
- `0x140034554`
- `0x140034914`
- `0x140038630`
- `0x14009abb8`
- `0x1400aa41c`
- `0x1400cb1bc`
- `0x1400d1728`
- `0x1400d723c`
- `0x1400ee9e0`
- `0x1400ef710`
- `0x1400efcc0`
- `0x1400f2e2c`
- `0x1400f2e74`
- `0x1400f380c`
- `0x1400f42c8`
- `0x1400f5dc8`
- `0x1400f8bd8`
- `0x1400fb920`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400f61dd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400f61dd`

## string_xrefs

- `0x1400f5e8f`: `VsmmVaGpaRangepCreate`
- `0x1400f5ecf`: `VsmmVaGpaRangepCreate`
- `0x1400f5f1a`: `VsmmVaGpaRangepCreate`
- `0x1400f5f4e`: `VsmmVaGpaRangepCreate`
- `0x1400f5f78`: `VsmmVaGpaRangepCreate`
- `0x1400f5fa5`: `VsmmVaGpaRangepCreate`
- `0x1400f5ff1`: `VsmmVaGpaRangepCreate`
- `0x1400f6089`: `VsmmVaGpaRangepCreate`
- `0x1400f60c0`: `VsmmVaGpaRangepCreate`
- `0x1400f6108`: `VsmmVaGpaRangepCreate`
- `0x1400f6179`: `VsmmVaGpaRangepCreate`
- `0x1400f6200`: `VsmmVaGpaRangepCreate`
- `0x1400f6260`: `VsmmVaGpaRangepCreate`
- `0x1400f62e0`: `VsmmVaGpaRangepCreate`
- `0x1400f6375`: `VsmmVaGpaRangepCreate`
- `0x1400f6421`: `VsmmVaGpaRangepCreate`
- `0x1400f648b`: `VsmmVaGpaRangepCreate`
- `0x1400f64ba`: `VsmmVaGpaRangepCreate`
- `0x1400f64fa`: `VsmmVaGpaRangepCreate`
- `0x1400f6564`: `VsmmVaGpaRangepCreate`
- `0x1400f65ed`: `VsmmVaGpaRangepCreate`

## pseudocode

```c
__int64 __fastcall VsmmVaGpaRangepCreate(_BYTE *P, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, _QWORD *a7)
{
  char v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r12
  __int64 v12; // r14
  int Entry; // ebx
  int v14; // eax
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r14d
  int v18; // ecx
  bool v19; // zf
  __int64 v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // r14d
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // r9d
  int v29; // r8d
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v42[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v43[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v45; // [rsp+D0h] [rbp-30h]
  __int64 v46; // [rsp+D8h] [rbp-28h]
  __int64 *v47; // [rsp+E0h] [rbp-20h]
  __int64 v48; // [rsp+E8h] [rbp-18h]
  char v49[32]; // [rsp+F0h] [rbp-10h] BYREF
  char v50[16]; // [rsp+110h] [rbp+10h] BYREF
  char v51[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v52; // [rsp+130h] [rbp+30h]
  __int64 v53; // [rsp+138h] [rbp+38h]
  __int64 *v54; // [rsp+140h] [rbp+40h]
  __int64 v55; // [rsp+148h] [rbp+48h]
  char *v56; // [rsp+150h] [rbp+50h]
  __int64 v57; // [rsp+158h] [rbp+58h]
  _DWORD *v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+168h] [rbp+68h]
  __int64 v60; // [rsp+170h] [rbp+70h]
  _DWORD v61[2]; // [rsp+178h] [rbp+78h] BYREF
  _QWORD **v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  __int64 *v68; // [rsp+1B0h] [rbp+B0h]
  __int64 v69; // [rsp+1B8h] [rbp+B8h]
  __int64 *v70; // [rsp+1C0h] [rbp+C0h]
  __int64 v71; // [rsp+1C8h] [rbp+C8h]

  v8 = 0;
  v38 = a4;
  v9 = 0;
  v34 = a3;
  v10 = 0;
  v33 = a2;
  *a7 = -1;
  v11 = a3;
  v39 = a7;
  v12 = a2;
  v40 = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  VidObjectLockAcquireExclusive(P + 3736);
  if ( (P[40] & 4) != 0 || (*((_DWORD *)P + 8) & 0xB1E0LL) != 0 )
  {
    Entry = -1073741637;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5225);
    goto LABEL_50;
  }
  Entry = VsmmGpaRangeValidatePageRange(P, v12, v11);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5235);
    goto LABEL_50;
  }
  if ( (unsigned int)VsmmGpaRangeListOverlapCheck((_DWORD)P, v12, v11, 1, 0) )
  {
    Entry = -1070137272;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5250);
    goto LABEL_50;
  }
  Entry = VsmmMemoryBlockLookupByHandle((_DWORD)P, v38, a6, 1, (__int64)&v36);
  if ( Entry < 0 )
  {
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5263);
    v10 = v36;
    goto LABEL_50;
  }
  v10 = v36;
  v14 = *(_DWORD *)(v36 + 20);
  if ( (v14 & 8) == 0 )
  {
    Entry = -1070137326;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5273);
    goto LABEL_50;
  }
  if ( (v14 & 0x2F6) != 0 )
  {
    Entry = -1070137326;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5285);
    goto LABEL_50;
  }
  if ( *(_QWORD *)(v36 + 232) == -1 )
  {
    Entry = -1070137322;
    VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5296);
    goto LABEL_50;
  }
  if ( !*(_DWORD *)(v36 + 224) )
  {
    if ( v11 != *(_QWORD *)(v36 + 40) )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5316);
      goto LABEL_50;
    }
    if ( (a5 & 8) != 0 && (*(_DWORD *)(v36 + 20) & 1) == 0 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5325);
      v8 = 0;
      goto LABEL_50;
    }
    v16 = *(_DWORD *)(v36 + 20);
    v17 = 8196;
    if ( (v16 & 1) != 0 )
    {
      v17 = 8213;
      if ( *(_QWORD *)&P[8 * *(unsigned __int8 *)(v36 + 16) + 8984] )
      {
        Entry = -1073741811;
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5343);
        v8 = 0;
LABEL_49:
        v12 = v33;
        goto LABEL_50;
      }
    }
    if ( (v16 & 0x10000) != 0 )
    {
      v18 = *(_DWORD *)(v36 + 904);
      if ( ((v18 - 32) & 0xFFFFFFDF) == 0 )
        v17 |= 0x10u;
      if ( v18 == 2 || v18 == 32 )
        v17 |= 0x4000u;
    }
    Entry = VsmmGpaRangeAlloc((volatile signed __int64 *)P, 0, v17, v33, v11, (PVOID *)&v35);
    if ( Entry < 0 )
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5374);
      v9 = v35;
      v8 = 0;
      goto LABEL_49;
    }
    v9 = v35;
    VsmmGpaRangeInitializeMbBacked(v35, v10, 0);
    v19 = (v17 & 1) == 0;
    *(_QWORD *)(v9 + 264) = *(_QWORD *)(v10 + 48) + *(_QWORD *)(v9 + 256) - 1LL;
    v12 = v33;
    if ( !v19 )
      *(_QWORD *)(v10 + 872) = v33 & 0x3FFFF;
    v20 = *((_QWORD *)P + 1280);
    if ( PsGetCurrentProcess() != v20 )
    {
      Entry = -1073741811;
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5394);
LABEL_39:
      v8 = 0;
      goto LABEL_50;
    }
    VsmmHvMemPreDepositForGpaRange(v9);
    *(_DWORD *)(v9 + 292) |= 0x400u;
    Entry = VsmmHvPrecommitGpas(
              (_DWORD)P,
              0,
              *(_QWORD *)(v9 + 256),
              (unsigned int)*(_QWORD *)(v9 + 272) - (unsigned int)*(_QWORD *)(v9 + 256) + 1,
              (__int64)&v40);
    if ( Entry < 0 )
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5422);
      goto LABEL_39;
    }
    v23 = 6;
    if ( (a5 & 8) != 0 && (unsigned int)VsmmVsmAnyDefaultVtlProtectionsRequired(P, v21, v22) )
      v23 = 7;
    Entry = VsmmHvMapGpasFromPfnArray(
              (_DWORD)P,
              *(_QWORD *)(v9 + 256),
              (unsigned int)*(_QWORD *)(v9 + 272) - (unsigned int)*(_QWORD *)(v9 + 256) + 1,
              v23,
              v31,
              (__int64)&v37,
              *(_DWORD *)(v9 + 292),
              4);
    if ( Entry >= 0 )
    {
      v27 = *(_QWORD *)(v9 + 256);
      if ( v37 != *(_QWORD *)(v9 + 272) - v27 + 1 )
      {
        Entry = -1073741670;
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v43, "VsmmVaGpaRangepCreate");
          tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
          LODWORD(v36) = 5468;
          v45 = &v36;
          v35 = v37;
          v46 = 4;
          v47 = &v35;
          v48 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &byte_140057307, 0, 0, 6, v42);
        }
        goto LABEL_47;
      }
      if ( v23 != 6 )
      {
        Entry = VsmmVsmApplyDefaultVtlProtectionToGpaRange((__int64)P, 1, v9, v27, *(_QWORD *)(v9 + 272) - v27 + 1);
        if ( Entry < 0 )
        {
          VidTraceErrorStatusInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5495);
          goto LABEL_47;
        }
        VsmmHvMapGpasFromPfnArray(
          (_DWORD)P,
          *(_QWORD *)(v9 + 256),
          *(_QWORD *)(v9 + 272) - *(_QWORD *)(v9 + 256) + 1,
          6,
          v32,
          (__int64)&v37,
          *(_DWORD *)(v9 + 292),
          0);
      }
      Entry = VsmmNtSlatMemoryRangeRegister((int)P);
      if ( Entry >= 0 )
      {
        Entry = VsmmGpaRangeListInsert((__int64)P, v9);
        if ( Entry >= 0 )
        {
          v8 = 1;
          Entry = VidHandleTableAllocateEntry(P + 3264, v9, v9 + 248);
          if ( Entry >= 0 )
          {
            if ( (*(_DWORD *)(v10 + 896) & 1) != 0 )
              VsmmGpaRangeReference(v9);
            *v39 = *(_QWORD *)(v9 + 248);
            if ( *(_QWORD *)(v10 + 40) != *(_QWORD *)(v10 + 48) )
              *(_QWORD *)&P[8 * *(unsigned __int8 *)(v10 + 16) + 8984] = *(_QWORD *)(v9 + 264) + 1LL;
          }
          else
          {
            VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5552);
          }
          goto LABEL_48;
        }
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5536);
      }
      else
      {
        VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5525);
      }
    }
    else
    {
      VidTraceErrorInternal0("VsmmVaGpaRangepCreate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c", 5461);
    }
LABEL_47:
    v8 = 0;
LABEL_48:
    v11 = v34;
    goto LABEL_49;
  }
  Entry = -1070137326;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v43, "VsmmVaGpaRangepCreate");
    tlgCreate1Sz_char(v44, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
    LODWORD(v35) = 5306;
    v45 = &v35;
    v46 = 4;
    LODWORD(v36) = *(_DWORD *)(v10 + 224);
    v47 = &v36;
    v48 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_1400572B2, v15, 0, 6, v42);
  }
LABEL_50:
  VidObjectLockRelease(P + 3736);
  if ( Entry < 0 )
  {
    if ( v9 )
    {
      if ( v8 )
      {
        LOBYTE(v24) = 1;
        VidOpCtrlBlock(v9 + 8, v24);
      }
      VsmmGpaRangeRelease(v25, v9, 0);
    }
    else if ( v10 )
    {
      VidOpCtrlFinish(v10 + 128);
    }
    if ( Entry == -1070137299 && a6 == 1 )
      Entry = -1073741670;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v50, "VsmmVaGpaRangepCreate");
      tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagparange.c");
      v61[1] = v28;
      v52 = &v36;
      LODWORD(v33) = v29;
      v54 = &v35;
      LODWORD(v36) = 5653;
      v56 = P + 656;
      v53 = 4;
      v58 = v61;
      v60 = *((_QWORD *)P + 16);
      v61[0] = *((unsigned __int16 *)P + 60);
      v39 = (_QWORD *)*((_QWORD *)P + 81);
      v62 = &v39;
      v64 = &v34;
      v66 = &v41;
      v68 = &v38;
      v70 = &v33;
      LODWORD(v35) = Entry;
      v55 = 4;
      v57 = 16;
      v59 = 2;
      v63 = 8;
      v34 = v12;
      v65 = 8;
      v41 = v11;
      v67 = 8;
      v69 = 8;
      v71 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_140057209, 0, 0, 14, v49);
    }
  }
  else if ( (*(_DWORD *)(v10 + 896) & 1) != 0 )
  {
    VsmmVaGpaRangepSpeculativeFaultForRangeCreate(v9, v24, v26, 0);
  }
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1400f5dc8  push    rbp
0x1400f5dca  push    rbx
0x1400f5dcb  push    rsi
0x1400f5dcc  push    rdi
0x1400f5dcd  push    r12
0x1400f5dcf  push    r13
0x1400f5dd1  push    r14
0x1400f5dd3  push    r15
0x1400f5dd5  lea     rbp, [rsp-0E8h]
0x1400f5ddd  sub     rsp, 1E8h
0x1400f5de4  mov     rax, cs:__security_cookie
0x1400f5deb  xor     rax, rsp
0x1400f5dee  mov     [rbp+120h+var_50], rax
0x1400f5df5  mov     rax, [rbp+120h+arg_30]
0x1400f5dfc  mov     r15, rcx
0x1400f5dff  xor     r13b, r13b
0x1400f5e02  mov     [rsp+220h+var_1B0], r9
0x1400f5e07  xor     esi, esi
0x1400f5e09  mov     [rsp+220h+var_1D0], r8
0x1400f5e0e  xor     edi, edi
0x1400f5e10  mov     [rsp+220h+var_1D8], rdx
0x1400f5e15  add     rcx, 0E98h
0x1400f5e1c  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400f5e23  mov     r12, r8
0x1400f5e26  mov     [rsp+220h+var_1A8], rax
0x1400f5e2b  mov     r14, rdx
0x1400f5e2e  mov     [rbp+120h+var_1A0], 0
0x1400f5e36  mov     [rsp+220h+var_1B8], 0
0x1400f5e3f  mov     [rsp+220h+var_1E0], r13b
0x1400f5e44  mov     [rsp+220h+var_1C8], rsi
0x1400f5e49  mov     [rsp+220h+var_1C0], rdi
0x1400f5e4e  call    VidObjectLockAcquireExclusive
0x1400f5e53  test    byte ptr [r15+28h], 4
0x1400f5e58  jnz     loc_1400F6552
0x1400f5e5e  mov     eax, [r15+20h]
0x1400f5e62  test    rax, 0B1E0h
0x1400f5e68  jnz     loc_1400F6552
0x1400f5e6e  mov     r8, r12
0x1400f5e71  mov     rdx, r14
0x1400f5e74  mov     rcx, r15
0x1400f5e77  call    VsmmGpaRangeValidatePageRange
0x1400f5e7c  mov     ebx, eax
0x1400f5e7e  test    eax, eax
0x1400f5e80  jns     short loc_1400F5EA0
0x1400f5e82  mov     r8d, 1473h
0x1400f5e88  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5e8f  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5e96  call    VidTraceErrorInternal0
0x1400f5e9b  jmp     loc_1400F62FB
0x1400f5ea0  mov     r9d, 1
0x1400f5ea6  mov     [rsp+220h+var_200], rsi
0x1400f5eab  mov     r8, r12
0x1400f5eae  mov     rdx, r14
0x1400f5eb1  mov     rcx, r15
0x1400f5eb4  call    VsmmGpaRangeListOverlapCheck
0x1400f5eb9  test    eax, eax
0x1400f5ebb  jz      short loc_1400F5EE0
0x1400f5ebd  mov     ebx, 0C0370048h
0x1400f5ec2  mov     r8d, 1482h
0x1400f5ec8  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5ecf  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5ed6  call    VidTraceErrorInternal0
0x1400f5edb  jmp     loc_1400F62FB
0x1400f5ee0  mov     r8d, [rbp+120h+arg_28]
0x1400f5ee7  lea     rax, [rsp+220h+var_1C0]
0x1400f5eec  mov     rdx, [rsp+220h+var_1B0]
0x1400f5ef1  mov     r9d, 1
0x1400f5ef7  mov     rcx, r15
0x1400f5efa  mov     [rsp+220h+var_200], rax
0x1400f5eff  call    VsmmMemoryBlockLookupByHandle
0x1400f5f04  xor     r8d, r8d
0x1400f5f07  mov     ebx, eax
0x1400f5f09  test    eax, eax
0x1400f5f0b  jns     short loc_1400F5F30
0x1400f5f0d  mov     r8d, 148Fh
0x1400f5f13  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5f1a  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5f21  call    VidTraceErrorInternal0
0x1400f5f26  mov     rdi, [rsp+220h+var_1C0]
0x1400f5f2b  jmp     loc_1400F62FB
0x1400f5f30  mov     rdi, [rsp+220h+var_1C0]
0x1400f5f35  mov     eax, [rdi+14h]
0x1400f5f38  test    al, 8
0x1400f5f3a  jnz     short loc_1400F5F5F
0x1400f5f3c  mov     ebx, 0C0370012h
0x1400f5f41  mov     r8d, 1499h
0x1400f5f47  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5f4e  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5f55  call    VidTraceErrorInternal0
0x1400f5f5a  jmp     loc_1400F62FB
0x1400f5f5f  test    eax, 2F6h
0x1400f5f64  jz      short loc_1400F5F89
0x1400f5f66  mov     ebx, 0C0370012h
0x1400f5f6b  mov     r8d, 14A5h
0x1400f5f71  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5f78  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5f7f  call    VidTraceErrorInternal0
0x1400f5f84  jmp     loc_1400F62FB
0x1400f5f89  cmp     qword ptr [rdi+0E8h], 0FFFFFFFFFFFFFFFFh
0x1400f5f91  jnz     short loc_1400F5FB6
0x1400f5f93  mov     ebx, 0C0370016h
0x1400f5f98  mov     r8d, 14B0h
0x1400f5f9e  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f5fa5  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5fac  call    VidTraceErrorInternal0
0x1400f5fb1  jmp     loc_1400F62FB
0x1400f5fb6  mov     eax, [rdi+0E0h]
0x1400f5fbc  test    eax, eax
0x1400f5fbe  jz      loc_1400F6071
0x1400f5fc4  mov     eax, cs:dword_140064110
0x1400f5fca  mov     ebx, 0C0370012h
0x1400f5fcf  cmp     eax, 2
0x1400f5fd2  jbe     loc_1400F62FB
0x1400f5fd8  mov     edx, 100h
0x1400f5fdd  lea     rcx, dword_140064110
0x1400f5fe4  call    _tlgKeywordOn
0x1400f5fe9  test    al, al
0x1400f5feb  jz      loc_1400F62FB
0x1400f5ff1  lea     rdx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f5ff8  lea     rcx, [rbp+120h+var_170]
0x1400f5ffc  call    _tlgCreate1Sz_char
0x1400f6001  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6008  lea     rcx, [rbp+120h+var_160]
0x1400f600c  call    _tlgCreate1Sz_char
0x1400f6011  lea     rax, [rsp+220h+var_1C8]
0x1400f6016  mov     dword ptr [rsp+220h+var_1C8], 14BAh
0x1400f601e  mov     [rbp+120h+var_150], rax
0x1400f6022  lea     rdx, word_1400572B2
0x1400f6029  mov     [rbp+120h+var_148], 4
0x1400f6031  lea     rcx, dword_140064110
0x1400f6038  mov     eax, [rdi+0E0h]
0x1400f603e  xor     r9d, r9d
0x1400f6041  mov     dword ptr [rsp+220h+var_1C0], eax
0x1400f6045  lea     rax, [rsp+220h+var_1C0]
0x1400f604a  mov     [rbp+120h+var_140], rax
0x1400f604e  lea     rax, [rbp+120h+var_190]
0x1400f6052  mov     [rsp+220h+var_1F8], rax
0x1400f6057  mov     dword ptr [rsp+220h+var_200], 6
0x1400f605f  mov     [rbp+120h+var_138], 4
0x1400f6067  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400f606c  jmp     loc_1400F62FB
0x1400f6071  cmp     r12, [rdi+28h]
0x1400f6075  jz      short loc_1400F609A
0x1400f6077  mov     ebx, 0C000000Dh
0x1400f607c  mov     r8d, 14C4h
0x1400f6082  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6089  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f6090  call    VidTraceErrorInternal0
0x1400f6095  jmp     loc_1400F62FB
0x1400f609a  mov     r13, [rbp+120h+arg_20]
0x1400f60a1  and     r13d, 8
0x1400f60a5  jz      short loc_1400F60D4
0x1400f60a7  mov     eax, [rdi+14h]
0x1400f60aa  test    al, 1
0x1400f60ac  jnz     short loc_1400F60D4
0x1400f60ae  mov     ebx, 0C000000Dh
0x1400f60b3  mov     r8d, 14CDh
0x1400f60b9  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f60c0  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f60c7  call    VidTraceErrorInternal0
0x1400f60cc  mov     r13b, sil
0x1400f60cf  jmp     loc_1400F62FB
0x1400f60d4  mov     ecx, [rdi+14h]
0x1400f60d7  mov     r14d, 2004h
0x1400f60dd  test    cl, 1
0x1400f60e0  jz      short loc_1400F611C
0x1400f60e2  movzx   eax, byte ptr [rdi+10h]
0x1400f60e6  mov     r14d, 2015h
0x1400f60ec  cmp     [r15+rax*8+2318h], r8
0x1400f60f4  jz      short loc_1400F611C
0x1400f60f6  mov     ebx, 0C000000Dh
0x1400f60fb  mov     r8d, 14DFh
0x1400f6101  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6108  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f610f  call    VidTraceErrorInternal0
0x1400f6114  mov     r13b, sil
0x1400f6117  jmp     loc_1400F62F6
0x1400f611c  bt      ecx, 10h
0x1400f6120  jnb     short loc_1400F6145
0x1400f6122  mov     ecx, [rdi+388h]
0x1400f6128  lea     eax, [rcx-20h]
0x1400f612b  test    eax, 0FFFFFFDFh
0x1400f6130  jnz     short loc_1400F6136
0x1400f6132  or      r14d, 10h
0x1400f6136  cmp     ecx, 2
0x1400f6139  jz      short loc_1400F6140
0x1400f613b  cmp     ecx, 20h ; ' '
0x1400f613e  jnz     short loc_1400F6145
0x1400f6140  bts     r14d, 0Eh
0x1400f6145  mov     r9, [rsp+220h+var_1D8]
0x1400f614a  lea     rax, [rsp+220h+var_1C8]
0x1400f614f  mov     [rsp+220h+var_1F8], rax; __int64
0x1400f6154  mov     r8d, r14d
0x1400f6157  xor     edx, edx
0x1400f6159  mov     [rsp+220h+var_200], r12; __int64
0x1400f615e  mov     rcx, r15; P
0x1400f6161  call    VsmmGpaRangeAlloc
0x1400f6166  mov     ebx, eax
0x1400f6168  test    eax, eax
0x1400f616a  jns     short loc_1400F6194
0x1400f616c  mov     r8d, 14FEh
0x1400f6172  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6179  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f6180  call    VidTraceErrorInternal0
0x1400f6185  mov     rsi, [rsp+220h+var_1C8]
0x1400f618a  mov     r13b, [rsp+220h+var_1E0]
0x1400f618f  jmp     loc_1400F62F6
0x1400f6194  mov     rsi, [rsp+220h+var_1C8]
0x1400f6199  xor     r8d, r8d
0x1400f619c  mov     rcx, rsi
0x1400f619f  mov     rdx, rdi
0x1400f61a2  call    VsmmGpaRangeInitializeMbBacked
0x1400f61a7  mov     rcx, [rsi+100h]
0x1400f61ae  dec     rcx
0x1400f61b1  add     rcx, [rdi+30h]
0x1400f61b5  test    r14b, 1
0x1400f61b9  mov     [rsi+108h], rcx
0x1400f61c0  mov     r14, [rsp+220h+var_1D8]
0x1400f61c5  jz      short loc_1400F61D6
0x1400f61c7  mov     rax, r14
0x1400f61ca  and     eax, 3FFFFh
0x1400f61cf  mov     [rdi+368h], rax
0x1400f61d6  mov     rbx, [r15+2800h]
0x1400f61dd  call    cs:__imp_PsGetCurrentProcess
0x1400f61e4  nop     dword ptr [rax+rax+00h]
0x1400f61e9  cmp     rax, rbx
0x1400f61ec  jz      short loc_1400F6216
0x1400f61ee  mov     ebx, 0C000000Dh
0x1400f61f3  mov     r8d, 1512h
0x1400f61f9  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6200  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f6207  call    VidTraceErrorInternal0
0x1400f620c  mov     r13b, [rsp+220h+var_1E0]
0x1400f6211  jmp     loc_1400F62FB
0x1400f6216  mov     rcx, rsi
0x1400f6219  call    VsmmHvMemPreDepositForGpaRange
0x1400f621e  bts     dword ptr [rsi+124h], 0Ah
0x1400f6226  lea     rax, [rbp+120h+var_1A0]
0x1400f622a  mov     r8, [rsi+100h]
0x1400f6231  xor     edx, edx
0x1400f6233  mov     r9, [rsi+110h]
0x1400f623a  mov     rcx, r15
0x1400f623d  sub     r9, r8
0x1400f6240  mov     [rsp+220h+var_200], rax
0x1400f6245  inc     r9
0x1400f6248  call    VsmmHvPrecommitGpas
0x1400f624d  mov     ebx, eax
0x1400f624f  test    eax, eax
0x1400f6251  jns     short loc_1400F626E
0x1400f6253  mov     r8d, 152Eh
0x1400f6259  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f6260  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f6267  call    VidTraceErrorInternal0
0x1400f626c  jmp     short loc_1400F620C
0x1400f626e  mov     r12d, 6
0x1400f6274  mov     r14d, r12d
0x1400f6277  test    r13, r13
0x1400f627a  jz      short loc_1400F628F
0x1400f627c  mov     rcx, r15
0x1400f627f  call    VsmmVsmAnyDefaultVtlProtectionsRequired
0x1400f6284  test    eax, eax
0x1400f6286  lea     ecx, [r12+1]
0x1400f628b  cmovnz  r14d, ecx
0x1400f628f  mov     eax, [rsi+124h]
0x1400f6295  mov     r13d, 4
0x1400f629b  mov     rdx, [rsi+100h]
0x1400f62a2  mov     r9d, r14d
0x1400f62a5  mov     r8, [rsi+110h]
0x1400f62ac  mov     rcx, r15
0x1400f62af  mov     [rsp+220h+var_1E8], r13d
0x1400f62b4  sub     r8, rdx
0x1400f62b7  mov     [rsp+220h+var_1F0], eax
0x1400f62bb  inc     r8
0x1400f62be  lea     rax, [rsp+220h+var_1B8]
0x1400f62c3  mov     [rsp+220h+var_1F8], rax
0x1400f62c8  call    VsmmHvMapGpasFromPfnArray
0x1400f62cd  mov     ebx, eax
0x1400f62cf  test    eax, eax
0x1400f62d1  jns     short loc_1400F632D
0x1400f62d3  mov     r8d, 1555h
0x1400f62d9  lea     rdx, aOnecoreVmVidSy_57; "onecore\\vm\\vid\\sys\\vsmm\\vsmmvagpar"...
0x1400f62e0  lea     rcx, aVsmmvagparange_9; "VsmmVaGpaRangepCreate"
0x1400f62e7  call    VidTraceErrorInternal0
0x1400f62ec  mov     r13b, [rsp+220h+var_1E0]
0x1400f62f1  mov     r12, [rsp+220h+var_1D0]
0x1400f62f6  mov     r14, [rsp+220h+var_1D8]
0x1400f62fb  lea     rcx, [r15+0E98h]
0x1400f6302  call    VidObjectLockRelease
0x1400f6307  xor     r9d, r9d
0x1400f630a  test    ebx, ebx
0x1400f630c  js      loc_1400F6575
0x1400f6312  mov     eax, [rdi+380h]
0x1400f6318  test    al, 1
0x1400f631a  jz      loc_1400F6735
0x1400f6320  mov     rcx, rsi
0x1400f6323  call    VsmmVaGpaRangepSpeculativeFaultForRangeCreate
0x1400f6328  jmp     loc_1400F6735
0x1400f632d  mov     r9, [rsi+100h]
0x1400f6334  mov     rax, [rsi+110h]
0x1400f633b  sub     rax, r9
  ... truncated ...
```
