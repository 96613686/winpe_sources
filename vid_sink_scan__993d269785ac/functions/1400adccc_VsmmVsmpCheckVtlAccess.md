# VsmmVsmpCheckVtlAccess

- ea: `0x1400adccc`
- end: `0x1400ae158`
- name: `VsmmVsmpCheckVtlAccess`
- size: `1164`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64, char, unsigned int, _QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400aa6c0`
- `0x1400fbae8`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140034554`
- `0x140034584`
- `0x1400adccc`
- `0x1400f297c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae126`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae10d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae126`
- `ntoskrnl!ExAllocatePool2` at `0x1400adf22`
- `ntoskrnl!ExAllocatePool2` at `0x1400adf48`
- `ntoskrnl!ExAllocatePool2` at `0x1400adf22`
- `ntoskrnl!ExAllocatePool2` at `0x1400adf48`
- `winhvr!WinHvCheckSparseGpaPageVtlAccess` at `0x1400adfe5`
- `winhvr!WinHvCheckSparseGpaPageVtlAccess` at `0x1400adfe5`

## string_xrefs

- `0x1400addaf`: `VsmmVsmpCheckVtlAccess`

## pseudocode

```c
__int64 __fastcall VsmmVsmpCheckVtlAccess(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char a4,
        unsigned int a5,
        _QWORD *a6,
        __int64 *a7)
{
  __int64 v7; // r12
  void *v9; // rdi
  __int64 v10; // rbx
  void *v13; // r13
  char v14; // r11
  int v15; // eax
  int v16; // esi
  __int64 v17; // r8
  char v18; // r11
  __int64 v19; // rdx
  unsigned __int64 v20; // r12
  _BYTE *v21; // rdx
  _BYTE *v22; // r8
  __int64 v23; // rsi
  __int64 v24; // rax
  unsigned __int64 v25; // r15
  unsigned __int64 v26; // rdi
  unsigned __int64 i; // rcx
  __int64 v28; // rcx
  int DefaultVtlPermissionSet; // r11d
  int v30; // r10d
  bool v31; // zf
  int v32; // edx
  char v33; // cl
  unsigned int v34; // edx
  int v35; // eax
  _BYTE *v37; // [rsp+20h] [rbp-E0h]
  _BYTE v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 Pool2; // [rsp+58h] [rbp-A8h]
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h]
  unsigned __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v46; // [rsp+80h] [rbp-80h]
  __int64 *v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  char v49[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v50[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v51[16]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  __int64 *v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int64 v57; // [rsp+108h] [rbp+8h]
  _DWORD *v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  __int64 v60; // [rsp+120h] [rbp+20h]
  _DWORD v61[2]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD *v62; // [rsp+130h] [rbp+30h]
  __int64 v63; // [rsp+138h] [rbp+38h]
  __int64 *v64; // [rsp+140h] [rbp+40h]
  __int64 v65; // [rsp+148h] [rbp+48h]
  _BYTE *v66; // [rsp+150h] [rbp+50h]
  __int64 v67; // [rsp+158h] [rbp+58h]
  _BYTE v68[64]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v69[64]; // [rsp+1A0h] [rbp+A0h] BYREF

  v7 = *(_QWORD *)(a1 + 240);
  v9 = 0;
  v46 = a6;
  v10 = 0;
  v47 = a7;
  v38[0] = a4;
  v45 = 0;
  LODWORD(v39) = 0;
  v13 = 0;
  Pool2 = 0;
  v44 = v7;
  v42 = 0;
  v48 = v7 + 3736;
  VidObjectLockAcquireShared(v7 + 3736);
  v14 = v38[0];
  v15 = *(_DWORD *)(v7 + 8776);
  if ( ((1 << v38[0]) & v15) == 0 )
  {
    v16 = -1073741811;
    if ( (unsigned int)dword_140064110 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v50, "VsmmVsmpCheckVtlAccess");
        tlgCreate1Sz_char(v51, "onecore\\vm\\vid\\sys\\vsmm\\vsmmvsm.c");
        LODWORD(v39) = 3443;
        v52 = &v39;
        v53 = 4;
        v54 = &v42;
        LODWORD(v42) = -1073741811;
        v56 = v7 + 656;
        v55 = 4;
        v58 = v61;
        v60 = *(_QWORD *)(v7 + 128);
        v61[0] = *(unsigned __int16 *)(v7 + 120);
        v43 = *(_BYTE **)(v7 + 648);
        v62 = &v43;
        LODWORD(v40) = *(_DWORD *)(v7 + 8776);
        v64 = &v40;
        v66 = v38;
        v57 = 16;
        v59 = 2;
        v61[1] = v17;
        v63 = 8;
        v65 = 4;
        v38[0] = v18;
        v67 = 1;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &unk_14004D770, v17, 0, 12, v49);
      }
      v9 = 0;
    }
    goto LABEL_39;
  }
  v19 = -1;
  v40 = -1;
  if ( (v15 & 0xFFFFFFFE) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 292) & 1) != 0 )
    {
      v20 = 8;
      v21 = v69;
      v43 = v69;
      v22 = v68;
      v39 = v68;
      if ( a3 <= 8 )
        goto LABEL_16;
      v23 = a3;
      if ( a3 >= 0x1FE )
        v23 = 510;
      Pool2 = ExAllocatePool2(256, 8 * v23, 1833788502);
      if ( Pool2 )
      {
        v24 = ExAllocatePool2(256, 8 * v23, 1833788502);
        v14 = v38[0];
        v13 = (void *)v24;
        if ( v24 )
        {
          v21 = (_BYTE *)Pool2;
          v20 = v23;
          v43 = (_BYTE *)Pool2;
          v22 = (_BYTE *)v24;
          v39 = (_BYTE *)v24;
          goto LABEL_16;
        }
      }
      else
      {
        v14 = v38[0];
      }
      v21 = v69;
      v22 = v68;
LABEL_16:
      v25 = a2 + a3;
      if ( a2 < v25 )
      {
        while ( 1 )
        {
          v26 = v25 - a2;
          if ( v25 - a2 >= v20 )
            v26 = v20;
          for ( i = 0; i < v26; ++i )
            *(_QWORD *)&v21[8 * i] = i + a2;
          v37 = v21;
          LOBYTE(v21) = v14;
          v16 = WinHvCheckSparseGpaPageVtlAccess(*(_QWORD *)(v44 + 648), v21, a5, v26, v37, v22, &v45);
          if ( v16 < 0 )
            goto LABEL_38;
          v28 = 0;
          v22 = v39;
          if ( v45 )
          {
            while ( !v39[8 * v28] )
            {
              if ( ++v28 >= v45 )
                goto LABEL_25;
            }
            v10 = *(_QWORD *)&v39[8 * v28];
            v19 = v28 + a2;
            v42 = v10;
            v40 = v28 + a2;
          }
          else
          {
LABEL_25:
            v19 = v40;
          }
          if ( (_BYTE)v42 )
            goto LABEL_34;
          v21 = v43;
          a2 += v26;
          v14 = v38[0];
          if ( a2 >= v25 )
          {
            v19 = v40;
            goto LABEL_34;
          }
        }
      }
      goto LABEL_33;
    }
    DefaultVtlPermissionSet = VsmmVsmGetDefaultVtlPermissionSet(v7, &v39);
    v31 = !_BitScanForward((unsigned int *)&v32, DefaultVtlPermissionSet & ~(v30 | (v30 - 1)));
    if ( v31 )
    {
LABEL_33:
      v19 = -1;
      goto LABEL_34;
    }
    while ( 1 )
    {
      v33 = v32;
      v34 = a5 & ~*(unsigned __int16 *)&v38[2 * (unsigned __int8)v32 + 6];
      if ( v34 )
        break;
      v31 = !_BitScanForward((unsigned int *)&v32, DefaultVtlPermissionSet & ~((1 << v33) | ((1 << v33) - 1)));
      if ( v31 )
        goto LABEL_33;
    }
    v35 = (unsigned __int8)v34;
    v19 = a2;
    LODWORD(v42) = ((v35 | ((v33 & 0xF) << 8)) << 8) | 1;
    v10 = v42;
  }
LABEL_34:
  v16 = 0;
  *v46 = v10;
  if ( !(_BYTE)v42 )
  {
LABEL_38:
    v9 = (void *)Pool2;
    goto LABEL_39;
  }
  v9 = (void *)Pool2;
  if ( v47 )
    *v47 = v19;
LABEL_39:
  VidObjectLockRelease(v48);
  if ( v13 )
    ExFreePoolWithTag(v13, 0x6D4D6456u);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x6D4D6456u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400adccc  push    rbp
0x1400adcce  push    rbx
0x1400adccf  push    rsi
0x1400adcd0  push    rdi
0x1400adcd1  push    r12
0x1400adcd3  push    r13
0x1400adcd5  push    r14
0x1400adcd7  push    r15
0x1400adcd9  lea     rbp, [rsp-0F8h]
0x1400adce1  sub     rsp, 1F8h
0x1400adce8  mov     rax, cs:__security_cookie
0x1400adcef  xor     rax, rsp
0x1400adcf2  mov     [rbp+130h+var_50], rax
0x1400adcf9  mov     r12, [rcx+0F0h]
0x1400add00  mov     rsi, rcx
0x1400add03  mov     rax, [rbp+130h+arg_28]
0x1400add0a  xor     edi, edi
0x1400add0c  mov     [rbp+130h+var_1B0], rax
0x1400add10  xor     ebx, ebx
0x1400add12  mov     rax, [rbp+130h+arg_30]
0x1400add19  mov     r15, r8
0x1400add1c  mov     [rbp+130h+var_1A8], rax
0x1400add20  mov     r14, rdx
0x1400add23  lea     rax, [r12+0E98h]
0x1400add2b  mov     [rsp+230h+var_1F0], r9b
0x1400add30  mov     rcx, rax
0x1400add33  mov     [rsp+230h+var_1B8], 0
0x1400add3c  mov     dword ptr [rsp+230h+var_1E8], 0
0x1400add44  xor     r13d, r13d
0x1400add47  mov     [rsp+230h+var_1D8], rdi
0x1400add4c  mov     [rsp+230h+var_1C0], r12
0x1400add51  mov     [rsp+230h+var_1D0], rbx
0x1400add56  mov     [rbp+130h+var_1A0], rax
0x1400add5a  call    VidObjectLockAcquireShared
0x1400add5f  mov     r11b, [rsp+230h+var_1F0]
0x1400add64  lea     r10d, [rdi+1]
0x1400add68  mov     eax, [r12+2248h]
0x1400add70  mov     cl, r11b
0x1400add73  shl     r10d, cl
0x1400add76  test    eax, r10d
0x1400add79  jnz     loc_1400ADEBA
0x1400add7f  mov     eax, cs:dword_140064110
0x1400add85  mov     esi, 0C000000Dh
0x1400add8a  cmp     eax, 2
0x1400add8d  jbe     loc_1400AE0F7
0x1400add93  mov     edx, 100h
0x1400add98  lea     rcx, dword_140064110
0x1400add9f  call    _tlgKeywordOn
0x1400adda4  xor     r8d, r8d
0x1400adda7  test    al, al
0x1400adda9  jz      loc_1400ADEB2
0x1400addaf  lea     rdx, aVsmmvsmpcheckv
0x1400addb6  lea     rcx, [rbp+130h+var_170]
0x1400addba  call    _tlgCreate1Sz_char
0x1400addbf  lea     rdx, aOnecoreVmVidSy_63
0x1400addc6  lea     rcx, [rbp+130h+var_160]
0x1400addca  call    _tlgCreate1Sz_char
0x1400addcf  lea     rax, [rsp+230h+var_1E8]
0x1400addd4  mov     dword ptr [rsp+230h+var_1E8], 0D73h
0x1400adddc  mov     [rbp+130h+var_150], rax
0x1400adde0  lea     rdx, unk_14004D770
0x1400adde7  lea     rax, [rsp+230h+var_1D0]
0x1400addec  mov     [rbp+130h+var_148], 4
0x1400addf4  mov     [rbp+130h+var_140], rax
0x1400addf8  lea     rcx, dword_140064110
0x1400addff  lea     rax, [r12+290h]
0x1400ade07  mov     dword ptr [rsp+230h+var_1D0], esi
0x1400ade0b  mov     [rbp+130h+var_130], rax
0x1400ade0f  xor     r9d, r9d
0x1400ade12  lea     rax, [rbp+130h+var_108]
0x1400ade16  mov     [rbp+130h+var_138], 4
0x1400ade1e  mov     [rbp+130h+var_120], rax
0x1400ade22  mov     rax, [r12+80h]
0x1400ade2a  mov     [rbp+130h+var_110], rax
0x1400ade2e  movzx   eax, word ptr [r12+78h]
0x1400ade34  mov     [rbp+130h+var_108], eax
0x1400ade37  mov     rax, [r12+288h]
0x1400ade3f  mov     [rsp+230h+var_1C8], rax
0x1400ade44  lea     rax, [rsp+230h+var_1C8]
0x1400ade49  mov     [rbp+130h+var_100], rax
0x1400ade4d  mov     eax, [r12+2248h]
0x1400ade55  mov     dword ptr [rsp+230h+var_1E0], eax
0x1400ade59  lea     rax, [rsp+230h+var_1E0]
0x1400ade5e  mov     [rbp+130h+var_F0], rax
0x1400ade62  lea     rax, [rsp+230h+var_1F0]
0x1400ade67  mov     [rbp+130h+var_E0], rax
0x1400ade6b  lea     rax, [rbp+130h+var_190]
0x1400ade6f  mov     [rsp+230h+var_208], rax
0x1400ade74  mov     dword ptr [rsp+230h+var_210], 0Ch
0x1400ade7c  mov     [rbp+130h+var_128], 10h
0x1400ade84  mov     [rbp+130h+var_118], 2
0x1400ade8c  mov     [rbp+130h+var_104], r8d
0x1400ade90  mov     [rbp+130h+var_F8], 8
0x1400ade98  mov     [rbp+130h+var_E8], 4
0x1400adea0  mov     [rsp+230h+var_1F0], r11b
0x1400adea5  mov     [rbp+130h+var_D8], 1
0x1400adead  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400adeb2  mov     rdi, rbx
0x1400adeb5  jmp     loc_1400AE0F7
0x1400adeba  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400adebe  mov     [rsp+230h+var_1E0], rdx
0x1400adec3  test    eax, 0FFFFFFFEh
0x1400adec8  jz      loc_1400AE0B0
0x1400adece  mov     eax, [rsi+124h]
0x1400aded4  test    al, 1
0x1400aded6  jz      loc_1400AE05C
0x1400adedc  lea     r12d, [rdx+9]
0x1400adee0  lea     rdx, [rbp+130h+var_90]
0x1400adee7  mov     [rsp+230h+var_1C8], rdx
0x1400adeec  lea     r8, [rbp+130h+var_D0]
0x1400adef0  mov     [rsp+230h+var_1E8], r8
0x1400adef5  cmp     r15, r12
0x1400adef8  jbe     loc_1400ADF88
0x1400adefe  mov     eax, 1FEh
0x1400adf03  mov     rsi, r15
0x1400adf06  cmp     r15, rax
0x1400adf09  mov     edi, 100h
0x1400adf0e  mov     r8d, 6D4D6456h
0x1400adf14  mov     ecx, edi
0x1400adf16  cmovnb  rsi, rax
0x1400adf1a  lea     rdx, ds:0[rsi*8]
0x1400adf22  call    cs:__imp_ExAllocatePool2
0x1400adf29  nop     dword ptr [rax+rax+00h]
0x1400adf2e  mov     [rsp+230h+var_1D8], rax
0x1400adf33  test    rax, rax
0x1400adf36  jz      short loc_1400ADF78
0x1400adf38  mov     r8d, 6D4D6456h
0x1400adf3e  lea     rdx, ds:0[rsi*8]
0x1400adf46  mov     ecx, edi
0x1400adf48  call    cs:__imp_ExAllocatePool2
0x1400adf4f  nop     dword ptr [rax+rax+00h]
0x1400adf54  mov     r11b, [rsp+230h+var_1F0]
0x1400adf59  mov     r13, rax
0x1400adf5c  test    rax, rax
0x1400adf5f  jz      short loc_1400ADF7D
0x1400adf61  mov     rdx, [rsp+230h+var_1D8]
0x1400adf66  mov     r12, rsi
0x1400adf69  mov     [rsp+230h+var_1C8], rdx
0x1400adf6e  mov     r8, rax
0x1400adf71  mov     [rsp+230h+var_1E8], rax
0x1400adf76  jmp     short loc_1400ADF88
0x1400adf78  mov     r11b, [rsp+230h+var_1F0]
0x1400adf7d  lea     rdx, [rbp+130h+var_90]
0x1400adf84  lea     r8, [rbp+130h+var_D0]
0x1400adf88  add     r15, r14
0x1400adf8b  cmp     r14, r15
0x1400adf8e  jnb     loc_1400AE0AC
0x1400adf94  mov     rdi, r15
0x1400adf97  sub     rdi, r14
0x1400adf9a  cmp     rdi, r12
0x1400adf9d  cmovnb  rdi, r12
0x1400adfa1  xor     ecx, ecx
0x1400adfa3  test    rdi, rdi
0x1400adfa6  jz      short loc_1400ADFB8
0x1400adfa8  lea     rax, [rcx+r14]
0x1400adfac  mov     [rdx+rcx*8], rax
0x1400adfb0  inc     rcx
0x1400adfb3  cmp     rcx, rdi
0x1400adfb6  jb      short loc_1400ADFA8
0x1400adfb8  lea     rax, [rsp+230h+var_1B8]
0x1400adfbd  mov     r9, rdi
0x1400adfc0  mov     [rsp+230h+var_200], rax
0x1400adfc5  mov     rax, [rsp+230h+var_1C0]
0x1400adfca  mov     [rsp+230h+var_208], r8
0x1400adfcf  mov     r8d, [rbp+130h+arg_20]
0x1400adfd6  mov     [rsp+230h+var_210], rdx
0x1400adfdb  mov     dl, r11b
0x1400adfde  mov     rcx, [rax+288h]
0x1400adfe5  call    cs:__imp_WinHvCheckSparseGpaPageVtlAccess
0x1400adfec  nop     dword ptr [rax+rax+00h]
0x1400adff1  mov     esi, eax
0x1400adff3  test    eax, eax
0x1400adff5  js      loc_1400AE0F2
0x1400adffb  mov     rdx, [rsp+230h+var_1B8]
0x1400ae000  xor     ecx, ecx
0x1400ae002  mov     r8, [rsp+230h+var_1E8]
0x1400ae007  test    rdx, rdx
0x1400ae00a  jz      short loc_1400AE01B
0x1400ae00c  cmp     byte ptr [r8+rcx*8], 0
0x1400ae011  jnz     short loc_1400AE048
0x1400ae013  inc     rcx
0x1400ae016  cmp     rcx, rdx
0x1400ae019  jb      short loc_1400AE00C
0x1400ae01b  mov     rdx, [rsp+230h+var_1E0]
0x1400ae020  cmp     byte ptr [rsp+230h+var_1D0], 0
0x1400ae025  jnz     loc_1400AE0B0
0x1400ae02b  mov     rdx, [rsp+230h+var_1C8]
0x1400ae030  add     r14, rdi
0x1400ae033  mov     r11b, [rsp+230h+var_1F0]
0x1400ae038  cmp     r14, r15
0x1400ae03b  jb      loc_1400ADF94
0x1400ae041  mov     rdx, [rsp+230h+var_1E0]
0x1400ae046  jmp     short loc_1400AE0B0
0x1400ae048  mov     rbx, [r8+rcx*8]
0x1400ae04c  lea     rdx, [rcx+r14]
0x1400ae050  mov     [rsp+230h+var_1D0], rbx
0x1400ae055  mov     [rsp+230h+var_1E0], rdx
0x1400ae05a  jmp     short loc_1400AE020
0x1400ae05c  lea     rdx, [rsp+230h+var_1E8]
0x1400ae061  mov     rcx, r12
0x1400ae064  call    VsmmVsmGetDefaultVtlPermissionSet
0x1400ae069  lea     ecx, [r10-1]
0x1400ae06d  mov     r11d, eax
0x1400ae070  or      ecx, r10d
0x1400ae073  not     ecx
0x1400ae075  and     ecx, eax
0x1400ae077  bsf     edx, ecx
0x1400ae07a  setnz   cl
0x1400ae07d  test    cl, cl
0x1400ae07f  jz      short loc_1400AE0AC
0x1400ae081  movzx   ecx, dl
0x1400ae084  movzx   edx, [rsp+rcx*2+230h+var_1EA]
0x1400ae089  not     edx
0x1400ae08b  and     edx, [rbp+130h+arg_20]
0x1400ae091  jnz     short loc_1400AE0D3
0x1400ae093  lea     eax, [rdx+1]
0x1400ae096  shl     eax, cl
0x1400ae098  lea     ecx, [rax-1]
0x1400ae09b  or      ecx, eax
0x1400ae09d  not     ecx
0x1400ae09f  and     ecx, r11d
0x1400ae0a2  bsf     edx, ecx
0x1400ae0a5  setnz   al
0x1400ae0a8  test    al, al
0x1400ae0aa  jnz     short loc_1400AE081
0x1400ae0ac  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400ae0b0  mov     rax, [rbp+130h+var_1B0]
0x1400ae0b4  xor     esi, esi
0x1400ae0b6  mov     [rax], rbx
0x1400ae0b9  cmp     byte ptr [rsp+230h+var_1D0], sil
0x1400ae0be  jz      short loc_1400AE0F2
0x1400ae0c0  mov     rax, [rbp+130h+var_1A8]
0x1400ae0c4  mov     rdi, [rsp+230h+var_1D8]
0x1400ae0c9  test    rax, rax
0x1400ae0cc  jz      short loc_1400AE0F7
0x1400ae0ce  mov     [rax], rdx
0x1400ae0d1  jmp     short loc_1400AE0F7
0x1400ae0d3  and     ecx, 0Fh
0x1400ae0d6  movzx   eax, dl
0x1400ae0d9  shl     ecx, 8
0x1400ae0dc  mov     rdx, r14
0x1400ae0df  or      ecx, eax
0x1400ae0e1  shl     ecx, 8
0x1400ae0e4  or      ecx, 1
0x1400ae0e7  mov     dword ptr [rsp+230h+var_1D0], ecx
0x1400ae0eb  mov     rbx, [rsp+230h+var_1D0]
0x1400ae0f0  jmp     short loc_1400AE0B0
0x1400ae0f2  mov     rdi, [rsp+230h+var_1D8]
0x1400ae0f7  mov     rcx, [rbp+130h+var_1A0]
0x1400ae0fb  call    VidObjectLockRelease
0x1400ae100  test    r13, r13
0x1400ae103  jz      short loc_1400AE119
0x1400ae105  mov     edx, 6D4D6456h; Tag
0x1400ae10a  mov     rcx, r13; P
0x1400ae10d  call    cs:__imp_ExFreePoolWithTag
0x1400ae114  nop     dword ptr [rax+rax+00h]
0x1400ae119  test    rdi, rdi
0x1400ae11c  jz      short loc_1400AE132
0x1400ae11e  mov     edx, 6D4D6456h; Tag
0x1400ae123  mov     rcx, rdi; P
0x1400ae126  call    cs:__imp_ExFreePoolWithTag
0x1400ae12d  nop     dword ptr [rax+rax+00h]
0x1400ae132  mov     eax, esi
0x1400ae134  mov     rcx, [rbp+130h+var_50]
0x1400ae13b  xor     rcx, rsp; StackCookie
0x1400ae13e  call    __security_check_cookie
0x1400ae143  add     rsp, 1F8h
0x1400ae14a  pop     r15
0x1400ae14c  pop     r14
0x1400ae14e  pop     r13
0x1400ae150  pop     r12
0x1400ae152  pop     rdi
0x1400ae153  pop     rsi
0x1400ae154  pop     rbx
0x1400ae155  pop     rbp
0x1400ae156  retn
```
