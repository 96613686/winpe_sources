# VsmmClonepTemplateCreate

- ea: `0x1400af880`
- end: `0x1400affc6`
- name: `VsmmClonepTemplateCreate`
- size: `1862`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400ae870`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140034554`
- `0x140034914`
- `0x140073864`
- `0x140074acc`
- `0x140077a48`
- `0x1400af880`
- `0x1400d4420`
- `0x1400f2a5c`
- `0x1400f3f8c`
- `0x1400f69c0`
- `0x1400fad1c`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400afb49`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x1400afb49`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa42`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa42`
- `ntoskrnl!PsGetProcessJob` at `0x1400afe8a`
- `ntoskrnl!PsGetProcessJob` at `0x1400afe8a`

## string_xrefs

- `0x1400af904`: `VsmmClonepTemplateCreate`
- `0x1400afbec`: `VsmmClonepTemplateCreate`
- `0x1400afc46`: `VsmmClonepTemplateCreate`
- `0x1400afd4e`: `VsmmClonepTemplateCreate`
- `0x1400afdaa`: `VsmmClonepTemplateCreate`
- `0x1400afec9`: `VsmmClonepTemplateCreate`
- `0x1400aff4d`: `VsmmClonepTemplateCreate`

## pseudocode

```c
__int64 __fastcall VsmmClonepTemplateCreate(__int64 a1, char a2, _QWORD *a3)
{
  int v4; // ebx
  int v5; // edi
  int v6; // r11d
  _QWORD *v7; // rsi
  _DWORD *Next; // rax
  __int64 Pool2; // rax
  __int64 v10; // r8
  _QWORD *v11; // r15
  __int64 v12; // rcx
  bool v13; // zf
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rax
  _DWORD *v16; // rdi
  int v17; // r11d
  char *v18; // rdx
  int v19; // r11d
  char *v20; // rbx
  int v22; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v26; // [rsp+60h] [rbp-A0h]
  _BYTE v27[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  __int64 *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  __int64 v35; // [rsp+D8h] [rbp-28h]
  int *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  __int64 v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h] BYREF
  int v40; // [rsp+FCh] [rbp-4h]
  __int64 *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]

  v26 = a3;
  P = 0;
  v4 = a2 & 1;
  v5 = VsmmClonepTemplateAlloc(!(a2 & 1), &P);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      v22 = 1482;
      v30 = (__int64 *)&v22;
      v32 = &v23;
      v34 = a1 + 656;
      v31 = 4;
      v36 = &v39;
      v38 = *(_QWORD *)(a1 + 128);
      v39 = *(unsigned __int16 *)(a1 + 120);
      v24 = *(_QWORD *)(a1 + 648);
      v41 = &v24;
      LODWORD(v23) = v5;
      v33 = 4;
      v35 = 16;
      v37 = 2;
      v40 = v6;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004E495, 0, 0, 10, v27);
    }
    v7 = P;
    goto LABEL_58;
  }
  v23 = -1;
  Next = (_DWORD *)VidHandleTableGetNext(a1 + 3232, &v23);
  v7 = P;
  while ( 1 )
  {
    v16 = Next;
    if ( !Next )
    {
      v5 = VsmmNtSlatMemoryProcessCreate(
             *(_QWORD *)(a1 + 10328),
             0,
             0,
             v4 != 0 ? 3 : 17,
             (PVOID)(a1 + 10336),
             (__int64)(v7 + 11),
             (__int64)(v7 + 12));
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_58;
        tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v23) = 1609;
        v18 = &byte_14004E26F;
        goto LABEL_47;
      }
      if ( v4 )
        goto LABEL_57;
      if ( PsGetProcessJob(v7[11]) )
      {
        v5 = -1073741811;
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_58;
        tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v23) = 1622;
        v18 = byte_14004E2DD;
        goto LABEL_47;
      }
      v20 = (char *)VidDeviceExtension + 680;
      VidObjectLockAcquireExclusive((char *)VidDeviceExtension + 680);
      v5 = VsmmClonepTableInsertById(v20, v7);
      VidObjectLockRelease(v20);
      if ( v5 >= 0 )
      {
LABEL_57:
        v5 = 0;
        *v26 = v7;
        v7 = 0;
        goto LABEL_58;
      }
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_58;
      tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v23) = 1639;
      v18 = byte_14004E34B;
LABEL_47:
      v31 = 4;
      v30 = &v23;
      v32 = (__int64 *)&v22;
      v34 = a1 + 656;
      v22 = v5;
      v36 = &v39;
      v38 = *(_QWORD *)(a1 + 128);
      v39 = *(unsigned __int16 *)(a1 + 120);
      v24 = *(_QWORD *)(a1 + 648);
      v41 = &v24;
      v33 = 4;
      v35 = 16;
      v37 = 2;
      v40 = v17;
      v42 = 8;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v18, 0, 0, 10, v27);
      goto LABEL_58;
    }
    if ( (Next[5] & 8) != 0 && (Next[32] & 0x10000000) == 0 )
      break;
LABEL_31:
    Next = (_DWORD *)VidHandleTableGetNext(a1 + 3232, &v23);
  }
  if ( Next[8] == 1 )
  {
    v5 = -1073741436;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_58;
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1526;
    v18 = byte_14004E3B9;
    goto LABEL_47;
  }
  Pool2 = ExAllocatePool2(256, 80, 1833788502);
  v11 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
    if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      goto LABEL_58;
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1542;
    v18 = &byte_14004E427;
    goto LABEL_47;
  }
  *(_QWORD *)(Pool2 + 24) = *((_QWORD *)v16 + 110);
  *(_QWORD *)(Pool2 + 32) = *((_QWORD *)v16 + 5) << 12;
  *(_DWORD *)(Pool2 + 44) = *(_DWORD *)(Pool2 + 44) & 0xFFFFFFFE | *((_WORD *)v16 + 11) & 1;
  *(_OWORD *)(Pool2 + 48) = *(_OWORD *)(v16 + 226);
  if ( (v16[5] & 0x4000) == 0 || (v5 = VsmmBitmapClone((_OWORD *)(Pool2 + 64), (_QWORD *)v16 + 57), v5 >= 0) )
  {
    v12 = v11[3];
    v13 = (v7[14] & 1) == 0;
    v14 = v7[13];
    v24 = v12;
    if ( !v13 )
    {
      if ( v14 )
        v14 ^= (unsigned __int64)(v7 + 13);
      else
        v14 = 0;
    }
    LOBYTE(v10) = 0;
    v22 = v7[14] & 1;
    if ( v14 )
    {
      while ( 1 )
      {
        if ( (int)VsmmClonepTemplateCompareMemoryBlockEntry(v12, v14, v10) < 0 )
        {
          v15 = *(_QWORD *)v14;
          if ( v22 )
          {
            if ( !v15 )
              goto LABEL_29;
            v15 ^= v14;
          }
          if ( !v15 )
          {
LABEL_29:
            LOBYTE(v10) = 0;
            break;
          }
        }
        else
        {
          v15 = *(_QWORD *)(v14 + 8);
          if ( v22 )
          {
            if ( !v15 )
              goto LABEL_23;
            v15 ^= v14;
          }
          if ( !v15 )
          {
LABEL_23:
            LOBYTE(v10) = 1;
            break;
          }
        }
        v12 = v24;
        v14 = v15;
      }
    }
    RtlRbInsertNodeEx(v7 + 13, v14, v10, v11);
    goto LABEL_31;
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v28, "VsmmClonepTemplateCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v23) = 1560;
    v30 = &v23;
    v32 = (__int64 *)&v22;
    v34 = a1 + 656;
    v31 = 4;
    v36 = &v39;
    v38 = *(_QWORD *)(a1 + 128);
    v39 = *(unsigned __int16 *)(a1 + 120);
    v24 = *(_QWORD *)(a1 + 648);
    v41 = &v24;
    v22 = v5;
    v33 = 4;
    v35 = 16;
    v37 = 2;
    v40 = v19;
    v42 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004E201, 0, 0, 10, v27);
  }
  VsmmClonepTemplateFreeMemoryBlockEntry(v11);
LABEL_58:
  if ( v7 )
    VsmmClonepTemplateFree(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400af880  mov     [rsp-8+arg_18], rbx
0x1400af885  push    rbp
0x1400af886  push    rsi
0x1400af887  push    rdi
0x1400af888  push    r12
0x1400af88a  push    r13
0x1400af88c  push    r14
0x1400af88e  push    r15
0x1400af890  lea     rbp, [rsp-20h]
0x1400af895  sub     rsp, 120h
0x1400af89c  mov     rax, cs:__security_cookie
0x1400af8a3  xor     rax, rsp
0x1400af8a6  mov     [rbp+50h+var_40], rax
0x1400af8aa  mov     ebx, edx
0x1400af8ac  mov     [rsp+150h+var_F0], r8
0x1400af8b1  mov     r13, rcx
0x1400af8b4  mov     [rsp+150h+P], 0
0x1400af8bd  and     ebx, 1
0x1400af8c0  lea     rdx, [rsp+150h+P]
0x1400af8c5  mov     ecx, ebx
0x1400af8c7  xor     ecx, 1
0x1400af8ca  call    VsmmClonepTemplateAlloc
0x1400af8cf  xor     r11d, r11d
0x1400af8d2  mov     edi, eax
0x1400af8d4  test    eax, eax
0x1400af8d6  jns     loc_1400AF9DE
0x1400af8dc  mov     ecx, cs:dword_140064110
0x1400af8e2  cmp     ecx, 2
0x1400af8e5  jbe     loc_1400AF9D4
0x1400af8eb  mov     edx, 100h
0x1400af8f0  lea     rcx, dword_140064110
0x1400af8f7  call    _tlgKeywordOn
0x1400af8fc  test    al, al
0x1400af8fe  jz      loc_1400AF9D4
0x1400af904  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400af90b  lea     rcx, [rbp+50h+var_C0]
0x1400af90f  call    _tlgCreate1Sz_char
0x1400af914  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400af91b  lea     rcx, [rbp+50h+var_B0]
0x1400af91f  call    _tlgCreate1Sz_char
0x1400af924  lea     rax, [rsp+150h+var_110]
0x1400af929  mov     [rsp+150h+var_110], 5CAh
0x1400af931  mov     [rbp+50h+var_A0], rax
0x1400af935  lea     rcx, [rsp+150h+var_108]
0x1400af93a  lea     rax, [r13+290h]
0x1400af941  mov     [rbp+50h+var_90], rcx
0x1400af945  mov     [rbp+50h+var_80], rax
0x1400af949  lea     rdx, byte_14004E495
0x1400af950  lea     rax, [rbp+50h+var_58]
0x1400af954  mov     [rbp+50h+var_98], 4
0x1400af95c  mov     [rbp+50h+var_70], rax
0x1400af960  lea     rcx, dword_140064110
0x1400af967  mov     rax, [r13+80h]
0x1400af96e  xor     r9d, r9d
0x1400af971  mov     [rbp+50h+var_60], rax
0x1400af975  xor     r8d, r8d
0x1400af978  movzx   eax, word ptr [r13+78h]
0x1400af97d  mov     [rbp+50h+var_58], eax
0x1400af980  mov     rax, [r13+288h]
0x1400af987  mov     [rsp+150h+var_100], rax
0x1400af98c  lea     rax, [rsp+150h+var_100]
0x1400af991  mov     [rbp+50h+var_50], rax
0x1400af995  lea     rax, [rsp+150h+var_E0]
0x1400af99a  mov     [rsp+150h+var_128], rax
0x1400af99f  mov     dword ptr [rsp+150h+var_130], 0Ah
0x1400af9a7  mov     dword ptr [rsp+150h+var_108], edi
0x1400af9ab  mov     [rbp+50h+var_88], 4
0x1400af9b3  mov     [rbp+50h+var_78], 10h
0x1400af9bb  mov     [rbp+50h+var_68], 2
0x1400af9c3  mov     [rbp+50h+var_54], r11d
0x1400af9c7  mov     [rbp+50h+var_48], 8
0x1400af9cf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400af9d4  mov     rsi, [rsp+150h+P]
0x1400af9d9  jmp     loc_1400AFF8F
0x1400af9de  lea     rcx, [r13+0CA0h]
0x1400af9e5  mov     [rsp+150h+var_108], 0FFFFFFFFFFFFFFFFh
0x1400af9ee  lea     rdx, [rsp+150h+var_108]
0x1400af9f3  call    VidHandleTableGetNext
0x1400af9f8  mov     rsi, [rsp+150h+P]
0x1400af9fd  mov     r14d, 100h
0x1400afa03  mov     r12d, 8
0x1400afa09  jmp     loc_1400AFB6F
0x1400afa0e  mov     ecx, [rdi+14h]
0x1400afa11  test    r12b, cl
0x1400afa14  jz      loc_1400AFB5E
0x1400afa1a  mov     ecx, [rdi+80h]
0x1400afa20  bt      ecx, 1Ch
0x1400afa24  jb      loc_1400AFB5E
0x1400afa2a  cmp     dword ptr [rdi+20h], 1
0x1400afa2e  jz      loc_1400AFD7F
0x1400afa34  mov     edx, 50h ; 'P'
0x1400afa39  mov     r8d, 6D4D6456h
0x1400afa3f  mov     rcx, r14
0x1400afa42  call    cs:__imp_ExAllocatePool2
0x1400afa49  nop     dword ptr [rax+rax+00h]
0x1400afa4e  xor     r11d, r11d
0x1400afa51  mov     r15, rax
0x1400afa54  test    rax, rax
0x1400afa57  jz      loc_1400AFD23
0x1400afa5d  mov     rcx, [rdi+370h]
0x1400afa64  mov     [rax+18h], rcx
0x1400afa68  mov     rcx, [rdi+28h]
0x1400afa6c  shl     rcx, 0Ch
0x1400afa70  mov     [rax+20h], rcx
0x1400afa74  movzx   edx, word ptr [rdi+16h]
0x1400afa78  mov     ecx, [rax+2Ch]
0x1400afa7b  and     edx, 1
0x1400afa7e  and     ecx, 0FFFFFFFEh
0x1400afa81  or      edx, ecx
0x1400afa83  mov     [rax+2Ch], edx
0x1400afa86  movups  xmm0, xmmword ptr [rdi+388h]
0x1400afa8d  movdqu  xmmword ptr [rax+30h], xmm0
0x1400afa92  test    dword ptr [rdi+14h], 4000h
0x1400afa99  jz      short loc_1400AFAB8
0x1400afa9b  lea     rdx, [rdi+1C8h]
0x1400afaa2  lea     rcx, [rax+40h]
0x1400afaa6  call    VsmmBitmapClone
0x1400afaab  xor     r11d, r11d
0x1400afaae  mov     edi, eax
0x1400afab0  test    eax, eax
0x1400afab2  js      loc_1400AFC20
0x1400afab8  mov     rcx, [r15+18h]
0x1400afabc  lea     r12, [rsi+68h]
0x1400afac0  test    byte ptr [r12+8], 1
0x1400afac6  mov     rdi, [r12]
0x1400afaca  mov     [rsp+150h+var_100], rcx
0x1400afacf  jz      short loc_1400AFADE
0x1400afad1  test    rdi, rdi
0x1400afad4  jz      short loc_1400AFADB
0x1400afad6  xor     rdi, r12
0x1400afad9  jmp     short loc_1400AFADE
0x1400afadb  mov     rdi, r11
0x1400afade  movzx   eax, byte ptr [r12+8]
0x1400afae4  mov     r8b, r11b
0x1400afae7  and     eax, 1
0x1400afaea  mov     [rsp+150h+var_110], eax
0x1400afaee  test    rdi, rdi
0x1400afaf1  jz      short loc_1400AFB40
0x1400afaf3  mov     rdx, rdi
0x1400afaf6  call    VsmmClonepTemplateCompareMemoryBlockEntry
0x1400afafb  test    eax, eax
0x1400afafd  js      short loc_1400AFB1C
0x1400afaff  cmp     [rsp+150h+var_110], 0
0x1400afb04  mov     rax, [rdi+8]
0x1400afb08  jz      short loc_1400AFB12
0x1400afb0a  test    rax, rax
0x1400afb0d  jz      short loc_1400AFB17
0x1400afb0f  xor     rax, rdi
0x1400afb12  test    rax, rax
0x1400afb15  jnz     short loc_1400AFB33
0x1400afb17  mov     r8b, 1
0x1400afb1a  jmp     short loc_1400AFB40
0x1400afb1c  cmp     [rsp+150h+var_110], 0
0x1400afb21  mov     rax, [rdi]
0x1400afb24  jz      short loc_1400AFB2E
0x1400afb26  test    rax, rax
0x1400afb29  jz      short loc_1400AFB3D
0x1400afb2b  xor     rax, rdi
0x1400afb2e  test    rax, rax
0x1400afb31  jz      short loc_1400AFB3D
0x1400afb33  mov     rcx, [rsp+150h+var_100]
0x1400afb38  mov     rdi, rax
0x1400afb3b  jmp     short loc_1400AFAF3
0x1400afb3d  xor     r8b, r8b
0x1400afb40  mov     r9, r15
0x1400afb43  mov     rdx, rdi
0x1400afb46  mov     rcx, r12
0x1400afb49  call    cs:__imp_RtlRbInsertNodeEx
0x1400afb50  nop     dword ptr [rax+rax+00h]
0x1400afb55  xor     r11d, r11d
0x1400afb58  mov     r12d, 8
0x1400afb5e  lea     rdx, [rsp+150h+var_108]
0x1400afb63  lea     rcx, [r13+0CA0h]
0x1400afb6a  call    VidHandleTableGetNext
0x1400afb6f  mov     rdi, rax
0x1400afb72  test    rax, rax
0x1400afb75  jnz     loc_1400AFA0E
0x1400afb7b  mov     eax, ebx
0x1400afb7d  lea     rcx, [rsi+60h]
0x1400afb81  mov     [rsp+150h+var_120], rcx; __int64
0x1400afb86  lea     rdx, [r13+2860h]
0x1400afb8d  mov     rcx, [r13+2858h]; int
0x1400afb94  lea     r15, [rsi+58h]
0x1400afb98  neg     eax
0x1400afb9a  mov     [rsp+150h+var_128], r15; __int64
0x1400afb9f  mov     [rsp+150h+var_130], rdx; PVOID
0x1400afba4  sbb     r9d, r9d
0x1400afba7  xor     r8d, r8d; int
0x1400afbaa  and     r9d, 0FFFFFFF2h
0x1400afbae  xor     edx, edx; int
0x1400afbb0  add     r9d, 11h; int
0x1400afbb4  call    VsmmNtSlatMemoryProcessCreate
0x1400afbb9  xor     r11d, r11d
0x1400afbbc  mov     edi, eax
0x1400afbbe  test    eax, eax
0x1400afbc0  jns     loc_1400AFE7F
0x1400afbc6  mov     eax, cs:dword_140064110
0x1400afbcc  cmp     eax, 2
0x1400afbcf  jbe     loc_1400AFF8F
0x1400afbd5  mov     rdx, r14
0x1400afbd8  lea     rcx, dword_140064110
0x1400afbdf  call    _tlgKeywordOn
0x1400afbe4  test    al, al
0x1400afbe6  jz      loc_1400AFF8F
0x1400afbec  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400afbf3  lea     rcx, [rbp+50h+var_C0]
0x1400afbf7  call    _tlgCreate1Sz_char
0x1400afbfc  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400afc03  lea     rcx, [rbp+50h+var_B0]
0x1400afc07  call    _tlgCreate1Sz_char
0x1400afc0c  mov     dword ptr [rsp+150h+var_108], 649h
0x1400afc14  lea     rdx, byte_14004E26F
0x1400afc1b  jmp     loc_1400AFDD9
0x1400afc20  mov     eax, cs:dword_140064110
0x1400afc26  cmp     eax, 2
0x1400afc29  jbe     loc_1400AFD16
0x1400afc2f  mov     rdx, r14
0x1400afc32  lea     rcx, dword_140064110
0x1400afc39  call    _tlgKeywordOn
0x1400afc3e  test    al, al
0x1400afc40  jz      loc_1400AFD16
0x1400afc46  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400afc4d  lea     rcx, [rbp+50h+var_C0]
0x1400afc51  call    _tlgCreate1Sz_char
0x1400afc56  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400afc5d  lea     rcx, [rbp+50h+var_B0]
0x1400afc61  call    _tlgCreate1Sz_char
0x1400afc66  lea     rax, [rsp+150h+var_108]
0x1400afc6b  mov     dword ptr [rsp+150h+var_108], 618h
0x1400afc73  mov     [rbp+50h+var_A0], rax
0x1400afc77  lea     rcx, [rsp+150h+var_110]
0x1400afc7c  lea     rax, [r13+290h]
0x1400afc83  mov     [rbp+50h+var_90], rcx
0x1400afc87  mov     [rbp+50h+var_80], rax
0x1400afc8b  lea     rdx, byte_14004E201
0x1400afc92  lea     rax, [rbp+50h+var_58]
0x1400afc96  mov     [rbp+50h+var_98], 4
0x1400afc9e  mov     [rbp+50h+var_70], rax
0x1400afca2  lea     rcx, dword_140064110
0x1400afca9  mov     rax, [r13+80h]
0x1400afcb0  xor     r9d, r9d
0x1400afcb3  mov     [rbp+50h+var_60], rax
0x1400afcb7  xor     r8d, r8d
0x1400afcba  movzx   eax, word ptr [r13+78h]
0x1400afcbf  mov     [rbp+50h+var_58], eax
0x1400afcc2  mov     rax, [r13+288h]
0x1400afcc9  mov     [rsp+150h+var_100], rax
0x1400afcce  lea     rax, [rsp+150h+var_100]
0x1400afcd3  mov     [rbp+50h+var_50], rax
0x1400afcd7  lea     rax, [rsp+150h+var_E0]
0x1400afcdc  mov     [rsp+150h+var_128], rax
0x1400afce1  mov     dword ptr [rsp+150h+var_130], 0Ah
0x1400afce9  mov     [rsp+150h+var_110], edi
0x1400afced  mov     [rbp+50h+var_88], 4
0x1400afcf5  mov     [rbp+50h+var_78], 10h
0x1400afcfd  mov     [rbp+50h+var_68], 2
0x1400afd05  mov     [rbp+50h+var_54], r11d
0x1400afd09  mov     [rbp+50h+var_48], 8
0x1400afd11  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400afd16  mov     rcx, r15; P
0x1400afd19  call    VsmmClonepTemplateFreeMemoryBlockEntry
0x1400afd1e  jmp     loc_1400AFF8F
0x1400afd23  mov     eax, cs:dword_140064110
0x1400afd29  mov     edi, 0C000009Ah
0x1400afd2e  cmp     eax, 2
0x1400afd31  jbe     loc_1400AFF8F
0x1400afd37  mov     rdx, r14
0x1400afd3a  lea     rcx, dword_140064110
0x1400afd41  call    _tlgKeywordOn
0x1400afd46  test    al, al
0x1400afd48  jz      loc_1400AFF8F
0x1400afd4e  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400afd55  lea     rcx, [rbp+50h+var_C0]
0x1400afd59  call    _tlgCreate1Sz_char
0x1400afd5e  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400afd65  lea     rcx, [rbp+50h+var_B0]
0x1400afd69  call    _tlgCreate1Sz_char
0x1400afd6e  mov     dword ptr [rsp+150h+var_108], 606h
0x1400afd76  lea     rdx, byte_14004E427
0x1400afd7d  jmp     short loc_1400AFDD9
0x1400afd7f  mov     eax, cs:dword_140064110
0x1400afd85  mov     edi, 0C0000184h
0x1400afd8a  cmp     eax, 2
0x1400afd8d  jbe     loc_1400AFF8F
0x1400afd93  mov     rdx, r14
0x1400afd96  lea     rcx, dword_140064110
0x1400afd9d  call    _tlgKeywordOn
0x1400afda2  test    al, al
0x1400afda4  jz      loc_1400AFF8F
0x1400afdaa  lea     rdx, aVsmmcloneptemp; "VsmmClonepTemplateCreate"
0x1400afdb1  lea     rcx, [rbp+50h+var_C0]
0x1400afdb5  call    _tlgCreate1Sz_char
0x1400afdba  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400afdc1  lea     rcx, [rbp+50h+var_B0]
0x1400afdc5  call    _tlgCreate1Sz_char
0x1400afdca  mov     dword ptr [rsp+150h+var_108], 5F6h
0x1400afdd2  lea     rdx, byte_14004E3B9
0x1400afdd9  lea     rax, [rsp+150h+var_108]
0x1400afdde  mov     [rbp+50h+var_98], 4
0x1400afde6  mov     [rbp+50h+var_A0], rax
  ... truncated ...
```
