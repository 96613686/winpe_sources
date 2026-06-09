# VsmmCloneTemplateApply

- ea: `0x1400b0d1c`
- end: `0x1400b15ff`
- name: `VsmmCloneTemplateApply`
- size: `2275`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008e464`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400347a4`
- `0x1400347d4`
- `0x140074864`
- `0x1400758ec`
- `0x140078a38`
- `0x1400a690c`
- `0x1400a698c`
- `0x1400b0d1c`
- `0x1400f6810`
- `0x1400fd58c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400b1595`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b1595`
- `ntoskrnl!ZwClose` at `0x1400b15a9`
- `ntoskrnl!ZwClose` at `0x1400b15a9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b0d81`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b10ce`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b110d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b0d81`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b10ce`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b110d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400b10dd`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400b10dd`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b15d0`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400b15d0`
- `ntoskrnl!PsGetProcessJob` at `0x1400b111c`
- `ntoskrnl!PsGetProcessJob` at `0x1400b111c`

## string_xrefs

- `0x1400b0dca`: `VsmmCloneTemplateApply`
- `0x1400b0edb`: `VsmmCloneTemplateApply`
- `0x1400b0f71`: `VsmmCloneTemplateApply`
- `0x1400b0ffe`: `VsmmCloneTemplateApply`
- `0x1400b118c`: `VsmmCloneTemplateApply`
- `0x1400b12a7`: `VsmmCloneTemplateApply`
- `0x1400b132e`: `VsmmCloneTemplateApply`
- `0x1400b143f`: `VsmmCloneTemplateApply`
- `0x1400b14b0`: `VsmmCloneTemplateApply`

## pseudocode

```c
__int64 __fastcall VsmmCloneTemplateApply(__int64 a1, _QWORD *a2)
{
  PVOID v2; // rsi
  __int64 v3; // rbx
  char *v4; // r13
  PVOID v5; // r12
  HANDLE v6; // r15
  int v8; // ebx
  __int64 v9; // r9
  __int16 *v10; // rdx
  PVOID *v11; // rax
  int v12; // r8d
  __int64 v13; // r8
  int v14; // r8d
  int v15; // r8d
  unsigned __int64 v16; // rbx
  int v17; // r13d
  int v18; // eax
  unsigned __int64 v19; // rax
  _QWORD *v20; // r15
  struct _KPROCESS *CurrentProcess; // rax
  PACCESS_TOKEN v22; // r13
  int v23; // ebx
  __int64 v24; // rax
  int ProcessJob; // eax
  __int64 v26; // rdx
  __int16 *v27; // rdx
  char v29; // [rsp+40h] [rbp-C0h]
  _QWORD *v30; // [rsp+48h] [rbp-B8h] BYREF
  char *v31; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID Object; // [rsp+68h] [rbp-98h] BYREF
  char *v35; // [rsp+70h] [rbp-90h]
  _BYTE v36[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID *p_P; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  PVOID *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  int *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]
  __int64 v47; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+108h] [rbp+8h] BYREF
  int v49; // [rsp+10Ch] [rbp+Ch]
  HANDLE *p_Handle; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]

  v2 = 0;
  v3 = *(_QWORD *)(a1 + 10240);
  v4 = (char *)VidDeviceExtension + 680;
  v5 = 0;
  v35 = (char *)VidDeviceExtension + 680;
  v6 = 0;
  v30 = a2;
  P = 0;
  v31 = 0;
  Object = 0;
  Handle = 0;
  if ( PsGetCurrentProcess() != v3 )
  {
    v8 = -1073741811;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(P) = 773;
      p_P = &P;
      v10 = (__int16 *)&dword_14004EC24;
      v11 = (PVOID *)&v30;
      v40 = 4;
      LODWORD(v30) = v12;
      v42 = 4;
LABEL_5:
      v49 = v9;
      v13 = 0;
LABEL_6:
      v41 = v11;
      v51 = 8;
      v43 = a1 + 656;
      v45 = &v48;
      v47 = *(_QWORD *)(a1 + 128);
      v48 = *(unsigned __int16 *)(a1 + 120);
      v31 = *(char **)(a1 + 648);
      p_Handle = (HANDLE *)&v31;
      v46 = 2;
      v44 = 16;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v10, v13, v9, 10, v36);
      return (unsigned int)v8;
    }
    return (unsigned int)v8;
  }
  if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
  {
    v8 = -1073741790;
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 783;
      p_P = (PVOID *)&v30;
      v10 = word_14004EC92;
      v11 = &P;
      v40 = 4;
      LODWORD(P) = -1073741790;
      v9 = 0;
      v42 = 4;
      v49 = v13;
      goto LABEL_6;
    }
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)(a1 + 10328) )
  {
    if ( *(_QWORD *)(a1 + 10400) )
    {
      v8 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v30) = 804;
        p_P = (PVOID *)&v30;
        v10 = &word_14004ED6E;
        v11 = &P;
        v40 = 4;
        LODWORD(P) = v15;
        v42 = 4;
        goto LABEL_5;
      }
      return (unsigned int)v8;
    }
    v29 = 0;
    VidObjectLockAcquireShared(v4);
    v16 = *((_QWORD *)v4 + 2);
    if ( (v4[24] & 1) != 0 && v16 )
      v16 ^= (unsigned __int64)(v4 + 16);
    v17 = v4[24] & 1;
    if ( !v16 )
      goto LABEL_54;
    do
    {
      v18 = VsmmClonepTableNodeCompareById(v30, v16);
      if ( v18 >= 0 )
      {
        if ( v18 <= 0 )
          break;
        v19 = *(_QWORD *)(v16 + 8);
      }
      else
      {
        v19 = *(_QWORD *)v16;
      }
      if ( v17 && v19 )
        v16 ^= v19;
      else
        v16 = v19;
    }
    while ( v16 );
    v2 = P;
    if ( v16 )
    {
      v20 = (_QWORD *)(v16 - 32);
      v30 = (_QWORD *)(v16 - 32);
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
      v22 = PsReferencePrimaryToken(CurrentProcess);
      v23 = (*(_DWORD *)(a1 + 24) >> 4) & 4 | 8;
      if ( (*(_DWORD *)(a1 + 16) & 0x4000) == 0 )
        v23 = (*(_DWORD *)(a1 + 24) >> 4) & 4;
      v24 = PsGetCurrentProcess();
      ProcessJob = PsGetProcessJob(v24);
      v8 = VsmmNtSlatMemoryProcessCreate(
             v20[11],
             (int)v22,
             ProcessJob,
             v23 | 1u,
             (PVOID)(a1 + 10336),
             (__int64)&Object,
             (__int64)&Handle);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
          tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
          LODWORD(v30) = 854;
          p_P = (PVOID *)&v30;
          v40 = 4;
          v41 = &P;
          LODWORD(P) = v8;
          v43 = a1 + 656;
          v42 = 4;
          v45 = &v48;
          v47 = *(_QWORD *)(a1 + 128);
          v48 = *(unsigned __int16 *)(a1 + 120);
          v31 = *(char **)(a1 + 648);
          p_Handle = (HANDLE *)&v31;
          v44 = 16;
          v46 = 2;
          v49 = 0;
          v51 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, qword_14004EB48, 0, 0, 10, v36);
        }
        v5 = Object;
        v6 = Handle;
        goto LABEL_59;
      }
      v5 = Object;
      v6 = Handle;
      v8 = VsmmProcessMemoryHostingSetupViaProcessPointer(a1, v26, Handle, Object);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
          goto LABEL_59;
        tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v30) = 869;
        v27 = &word_14004EBB6;
        v49 = 0;
        goto LABEL_58;
      }
      v5 = 0;
      v29 = 1;
      v6 = 0;
      v8 = VsmmClonepTemplateAlloc(3, &v31);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
          tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
          LODWORD(v30) = 891;
          p_P = (PVOID *)&v30;
          v40 = 4;
          v41 = &P;
          LODWORD(P) = v8;
          v43 = a1 + 656;
          v42 = 4;
          v45 = &v48;
          v47 = *(_QWORD *)(a1 + 128);
          v48 = *(unsigned __int16 *)(a1 + 120);
          Handle = *(HANDLE *)(a1 + 648);
          p_Handle = &Handle;
          v44 = 16;
          v46 = 2;
          v49 = 0;
          v51 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &word_14004E9FE, 0, 0, 10, v36);
        }
        v2 = v31;
        goto LABEL_59;
      }
      v2 = v31;
      v8 = VsmmClonepTemplateDuplicateMemoryBlockTree(v30, v31 + 104);
      if ( v8 >= 0 )
      {
        *(_QWORD *)(a1 + 10400) = v2;
        v2 = 0;
        v8 = 0;
LABEL_59:
        VidObjectLockRelease(v35);
        if ( v2 )
          VsmmClonepTemplateFree(v2);
        if ( v5 )
          ObfDereferenceObject(v5);
        if ( v6 )
          ZwClose(v6);
        if ( v8 < 0 && v29 )
          VsmmProcessMemoryHostingTeardown(a1);
        if ( v22 )
          PsDereferencePrimaryToken(v22);
        return (unsigned int)v8;
      }
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_59;
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 905;
      v27 = (__int16 *)&dword_14004EA6C;
    }
    else
    {
LABEL_54:
      v22 = 0;
      v8 = -1073741275;
      if ( (unsigned int)dword_140065110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        goto LABEL_59;
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 819;
      v27 = word_14004EADA;
    }
    v49 = 0;
LABEL_58:
    v40 = 4;
    p_P = (PVOID *)&v30;
    LODWORD(P) = v8;
    v41 = &P;
    v42 = 4;
    v43 = a1 + 656;
    v44 = 16;
    v45 = &v48;
    v47 = *(_QWORD *)(a1 + 128);
    v48 = *(unsigned __int16 *)(a1 + 120);
    v31 = *(char **)(a1 + 648);
    p_Handle = (HANDLE *)&v31;
    v46 = 2;
    v51 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v27, 0, 0, 10, v36);
    goto LABEL_59;
  }
  v8 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
    tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v30) = 794;
    p_P = (PVOID *)&v30;
    v10 = (__int16 *)qword_14004ED00;
    v11 = &P;
    v40 = 4;
    LODWORD(P) = v14;
    v42 = 4;
    goto LABEL_5;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400b0d1c  push    rbp
0x1400b0d1e  push    rbx
0x1400b0d1f  push    rsi
0x1400b0d20  push    rdi
0x1400b0d21  push    r12
0x1400b0d23  push    r13
0x1400b0d25  push    r14
0x1400b0d27  push    r15
0x1400b0d29  lea     rbp, [rsp-38h]
0x1400b0d2e  sub     rsp, 138h
0x1400b0d35  mov     rax, cs:__security_cookie
0x1400b0d3c  xor     rax, rsp
0x1400b0d3f  mov     [rbp+70h+var_50], rax
0x1400b0d43  mov     r13, cs:VidDeviceExtension
0x1400b0d4a  xor     esi, esi
0x1400b0d4c  mov     rbx, [rcx+2800h]
0x1400b0d53  add     r13, 2A8h
0x1400b0d5a  xor     r12d, r12d
0x1400b0d5d  mov     [rsp+170h+var_100], r13
0x1400b0d62  xor     r15d, r15d
0x1400b0d65  mov     [rsp+170h+var_128], rdx
0x1400b0d6a  mov     rdi, rcx
0x1400b0d6d  mov     [rsp+170h+P], rsi
0x1400b0d72  mov     [rsp+170h+var_120], rsi
0x1400b0d77  mov     [rsp+170h+Object], r12
0x1400b0d7c  mov     [rsp+170h+Handle], r15
0x1400b0d81  call    cs:__imp_PsGetCurrentProcess
0x1400b0d88  nop     dword ptr [rax+rax+00h]
0x1400b0d8d  cmp     rax, rbx
0x1400b0d90  jz      loc_1400B0E9B
0x1400b0d96  mov     eax, cs:dword_140065110
0x1400b0d9c  mov     r8d, 0C000000Dh
0x1400b0da2  mov     ebx, r8d
0x1400b0da5  cmp     eax, 2
0x1400b0da8  jbe     loc_1400B15DC
0x1400b0dae  mov     edx, 100h
0x1400b0db3  lea     rcx, dword_140065110
0x1400b0dba  call    _tlgKeywordOn
0x1400b0dbf  xor     r9d, r9d
0x1400b0dc2  test    al, al
0x1400b0dc4  jz      loc_1400B15DC
0x1400b0dca  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400b0dd1  lea     rcx, [rbp+70h+var_D0]
0x1400b0dd5  call    _tlgCreate1Sz_char
0x1400b0dda  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0de1  lea     rcx, [rbp+70h+var_C0]
0x1400b0de5  call    _tlgCreate1Sz_char
0x1400b0dea  lea     rax, [rsp+170h+P]
0x1400b0def  mov     dword ptr [rsp+170h+P], 305h
0x1400b0df7  mov     [rbp+70h+var_B0], rax
0x1400b0dfb  lea     rdx, dword_14004EC24
0x1400b0e02  lea     rax, [rsp+170h+var_128]
0x1400b0e07  mov     [rbp+70h+var_A8], 4
0x1400b0e0f  mov     dword ptr [rsp+170h+var_128], r8d
0x1400b0e14  mov     [rbp+70h+var_98], 4
0x1400b0e1c  mov     [rbp+70h+var_64], r9d
0x1400b0e20  xor     r8d, r8d
0x1400b0e23  mov     [rbp+70h+var_A0], rax
0x1400b0e27  lea     rcx, dword_140065110
0x1400b0e2e  lea     rax, [rdi+290h]
0x1400b0e35  mov     [rbp+70h+var_58], 8
0x1400b0e3d  mov     [rbp+70h+var_90], rax
0x1400b0e41  lea     rax, [rbp+70h+var_68]
0x1400b0e45  mov     [rbp+70h+var_80], rax
0x1400b0e49  mov     rax, [rdi+80h]
0x1400b0e50  mov     [rbp+70h+var_70], rax
0x1400b0e54  movzx   eax, word ptr [rdi+78h]
0x1400b0e58  mov     [rbp+70h+var_68], eax
0x1400b0e5b  mov     rax, [rdi+288h]
0x1400b0e62  mov     [rsp+170h+var_120], rax
0x1400b0e67  lea     rax, [rsp+170h+var_120]
0x1400b0e6c  mov     [rbp+70h+var_60], rax
0x1400b0e70  lea     rax, [rbp+70h+var_F0]
0x1400b0e74  mov     [rsp+170h+var_148], rax
0x1400b0e79  mov     dword ptr [rsp+170h+var_150], 0Ah
0x1400b0e81  mov     [rbp+70h+var_78], 2
0x1400b0e89  mov     [rbp+70h+var_88], 10h
0x1400b0e91  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b0e96  jmp     loc_1400B15DC
0x1400b0e9b  mov     r14d, 4
0x1400b0ea1  test    [rdi+28h], r14b
0x1400b0ea5  jz      loc_1400B0F30
0x1400b0eab  mov     eax, cs:dword_140065110
0x1400b0eb1  mov     ebx, 0C0000022h
0x1400b0eb6  cmp     eax, 2
0x1400b0eb9  jbe     loc_1400B15DC
0x1400b0ebf  mov     edx, 100h
0x1400b0ec4  lea     rcx, dword_140065110
0x1400b0ecb  call    _tlgKeywordOn
0x1400b0ed0  xor     r8d, r8d
0x1400b0ed3  test    al, al
0x1400b0ed5  jz      loc_1400B15DC
0x1400b0edb  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400b0ee2  lea     rcx, [rbp+70h+var_D0]
0x1400b0ee6  call    _tlgCreate1Sz_char
0x1400b0eeb  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0ef2  lea     rcx, [rbp+70h+var_C0]
0x1400b0ef6  call    _tlgCreate1Sz_char
0x1400b0efb  lea     rax, [rsp+170h+var_128]
0x1400b0f00  mov     dword ptr [rsp+170h+var_128], 30Fh
0x1400b0f08  mov     [rbp+70h+var_B0], rax
0x1400b0f0c  lea     rdx, word_14004EC92
0x1400b0f13  lea     rax, [rsp+170h+P]
0x1400b0f18  mov     [rbp+70h+var_A8], r14
0x1400b0f1c  mov     dword ptr [rsp+170h+P], ebx
0x1400b0f20  xor     r9d, r9d
0x1400b0f23  mov     [rbp+70h+var_98], r14
0x1400b0f27  mov     [rbp+70h+var_64], r8d
0x1400b0f2b  jmp     loc_1400B0E23
0x1400b0f30  xor     r9d, r9d
0x1400b0f33  cmp     [rdi+2858h], r9
0x1400b0f3a  jz      loc_1400B0FC0
0x1400b0f40  mov     eax, cs:dword_140065110
0x1400b0f46  mov     r8d, 0C000000Dh
0x1400b0f4c  mov     ebx, r8d
0x1400b0f4f  cmp     eax, 2
0x1400b0f52  jbe     loc_1400B15DC
0x1400b0f58  mov     edx, 100h
0x1400b0f5d  lea     rcx, dword_140065110
0x1400b0f64  call    _tlgKeywordOn
0x1400b0f69  test    al, al
0x1400b0f6b  jz      loc_1400B15DC
0x1400b0f71  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400b0f78  lea     rcx, [rbp+70h+var_D0]
0x1400b0f7c  call    _tlgCreate1Sz_char
0x1400b0f81  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b0f88  lea     rcx, [rbp+70h+var_C0]
0x1400b0f8c  call    _tlgCreate1Sz_char
0x1400b0f91  lea     rax, [rsp+170h+var_128]
0x1400b0f96  mov     dword ptr [rsp+170h+var_128], 31Ah
0x1400b0f9e  mov     [rbp+70h+var_B0], rax
0x1400b0fa2  lea     rdx, qword_14004ED00
0x1400b0fa9  lea     rax, [rsp+170h+P]
0x1400b0fae  mov     [rbp+70h+var_A8], r14
0x1400b0fb2  mov     dword ptr [rsp+170h+P], r8d
0x1400b0fb7  mov     [rbp+70h+var_98], r14
0x1400b0fbb  jmp     loc_1400B0E1C
0x1400b0fc0  cmp     [rdi+28A0h], r9
0x1400b0fc7  jz      loc_1400B104D
0x1400b0fcd  mov     eax, cs:dword_140065110
0x1400b0fd3  mov     r8d, 0C000000Dh
0x1400b0fd9  mov     ebx, r8d
0x1400b0fdc  cmp     eax, 2
0x1400b0fdf  jbe     loc_1400B15DC
0x1400b0fe5  mov     edx, 100h
0x1400b0fea  lea     rcx, dword_140065110
0x1400b0ff1  call    _tlgKeywordOn
0x1400b0ff6  test    al, al
0x1400b0ff8  jz      loc_1400B15DC
0x1400b0ffe  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400b1005  lea     rcx, [rbp+70h+var_D0]
0x1400b1009  call    _tlgCreate1Sz_char
0x1400b100e  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b1015  lea     rcx, [rbp+70h+var_C0]
0x1400b1019  call    _tlgCreate1Sz_char
0x1400b101e  lea     rax, [rsp+170h+var_128]
0x1400b1023  mov     dword ptr [rsp+170h+var_128], 324h
0x1400b102b  mov     [rbp+70h+var_B0], rax
0x1400b102f  lea     rdx, word_14004ED6E
0x1400b1036  lea     rax, [rsp+170h+P]
0x1400b103b  mov     [rbp+70h+var_A8], r14
0x1400b103f  mov     dword ptr [rsp+170h+P], r8d
0x1400b1044  mov     [rbp+70h+var_98], r14
0x1400b1048  jmp     loc_1400B0E1C
0x1400b104d  mov     rcx, r13
0x1400b1050  mov     [rsp+170h+var_130], r9b
0x1400b1055  call    VidObjectLockAcquireShared
0x1400b105a  lea     rcx, [r13+10h]
0x1400b105e  test    byte ptr [rcx+8], 1
0x1400b1062  mov     rbx, [rcx]
0x1400b1065  jz      short loc_1400B106F
0x1400b1067  test    rbx, rbx
0x1400b106a  jz      short loc_1400B106F
0x1400b106c  xor     rbx, rcx
0x1400b106f  movzx   r13d, byte ptr [rcx+8]
0x1400b1074  and     r13d, 1
0x1400b1078  test    rbx, rbx
0x1400b107b  jz      loc_1400B1480
0x1400b1081  mov     rsi, [rsp+170h+var_128]
0x1400b1086  mov     rdx, rbx
0x1400b1089  mov     rcx, rsi
0x1400b108c  call    VsmmClonepTableNodeCompareById
0x1400b1091  test    eax, eax
0x1400b1093  jns     short loc_1400B109A
0x1400b1095  mov     rax, [rbx]
0x1400b1098  jmp     short loc_1400B10A0
0x1400b109a  jle     short loc_1400B10B7
0x1400b109c  mov     rax, [rbx+8]
0x1400b10a0  test    r13d, r13d
0x1400b10a3  jz      short loc_1400B10AF
0x1400b10a5  test    rax, rax
0x1400b10a8  jz      short loc_1400B10AF
0x1400b10aa  xor     rbx, rax
0x1400b10ad  jmp     short loc_1400B10B2
0x1400b10af  mov     rbx, rax
0x1400b10b2  test    rbx, rbx
0x1400b10b5  jnz     short loc_1400B1086
0x1400b10b7  mov     rsi, [rsp+170h+P]
0x1400b10bc  test    rbx, rbx
0x1400b10bf  jz      loc_1400B1480
0x1400b10c5  lea     r15, [rbx-20h]
0x1400b10c9  mov     [rsp+170h+var_128], r15
0x1400b10ce  call    cs:__imp_PsGetCurrentProcess
0x1400b10d5  nop     dword ptr [rax+rax+00h]
0x1400b10da  mov     rcx, rax; Process
0x1400b10dd  call    cs:__imp_PsReferencePrimaryToken
0x1400b10e4  nop     dword ptr [rax+rax+00h]
0x1400b10e9  mov     ecx, [rdi+10h]
0x1400b10ec  mov     r13, rax
0x1400b10ef  mov     edx, [rdi+18h]
0x1400b10f2  and     ecx, 4000h
0x1400b10f8  shr     rdx, 4
0x1400b10fc  and     edx, r14d
0x1400b10ff  mov     ebx, edx
0x1400b1101  or      ebx, 8
0x1400b1104  test    rcx, rcx
0x1400b1107  cmovz   ebx, edx
0x1400b110a  or      ebx, 1
0x1400b110d  call    cs:__imp_PsGetCurrentProcess
0x1400b1114  nop     dword ptr [rax+rax+00h]
0x1400b1119  mov     rcx, rax
0x1400b111c  call    cs:__imp_PsGetProcessJob
0x1400b1123  nop     dword ptr [rax+rax+00h]
0x1400b1128  lea     rdx, [rsp+170h+Handle]
0x1400b112d  mov     r9d, ebx; int
0x1400b1130  mov     [rsp+170h+var_140], rdx; __int64
0x1400b1135  lea     rcx, [rdi+2860h]
0x1400b113c  lea     rdx, [rsp+170h+Object]
0x1400b1141  mov     r8, rax; int
0x1400b1144  mov     [rsp+170h+var_148], rdx; __int64
0x1400b1149  mov     rdx, r13; int
0x1400b114c  mov     [rsp+170h+var_150], rcx; PVOID
0x1400b1151  mov     rcx, [r15+58h]; int
0x1400b1155  call    VsmmNtSlatMemoryProcessCreate
0x1400b115a  mov     ebx, eax
0x1400b115c  test    eax, eax
0x1400b115e  jns     loc_1400B1261
0x1400b1164  mov     ecx, cs:dword_140065110
0x1400b116a  cmp     ecx, 2
0x1400b116d  jbe     loc_1400B1252
0x1400b1173  mov     edx, 100h
0x1400b1178  lea     rcx, dword_140065110
0x1400b117f  call    _tlgKeywordOn
0x1400b1184  test    al, al
0x1400b1186  jz      loc_1400B1252
0x1400b118c  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400b1193  lea     rcx, [rbp+70h+var_D0]
0x1400b1197  call    _tlgCreate1Sz_char
0x1400b119c  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400b11a3  lea     rcx, [rbp+70h+var_C0]
0x1400b11a7  call    _tlgCreate1Sz_char
0x1400b11ac  lea     rax, [rsp+170h+var_128]
0x1400b11b1  mov     dword ptr [rsp+170h+var_128], 356h
0x1400b11b9  mov     [rbp+70h+var_B0], rax
0x1400b11bd  lea     rdx, qword_14004EB48
0x1400b11c4  lea     rax, [rsp+170h+P]
0x1400b11c9  mov     [rbp+70h+var_A8], r14
0x1400b11cd  mov     [rbp+70h+var_A0], rax
0x1400b11d1  lea     rcx, dword_140065110
0x1400b11d8  lea     rax, [rdi+290h]
0x1400b11df  mov     dword ptr [rsp+170h+P], ebx
0x1400b11e3  mov     [rbp+70h+var_90], rax
0x1400b11e7  xor     r9d, r9d
0x1400b11ea  lea     rax, [rbp+70h+var_68]
0x1400b11ee  mov     [rbp+70h+var_98], r14
0x1400b11f2  mov     [rbp+70h+var_80], rax
0x1400b11f6  xor     r8d, r8d
0x1400b11f9  mov     rax, [rdi+80h]
0x1400b1200  mov     [rbp+70h+var_70], rax
0x1400b1204  movzx   eax, word ptr [rdi+78h]
0x1400b1208  mov     [rbp+70h+var_68], eax
0x1400b120b  mov     rax, [rdi+288h]
0x1400b1212  mov     [rsp+170h+var_120], rax
0x1400b1217  lea     rax, [rsp+170h+var_120]
0x1400b121c  mov     [rbp+70h+var_60], rax
0x1400b1220  lea     rax, [rbp+70h+var_F0]
0x1400b1224  mov     [rsp+170h+var_148], rax
0x1400b1229  mov     dword ptr [rsp+170h+var_150], 0Ah
0x1400b1231  mov     [rbp+70h+var_88], 10h
0x1400b1239  mov     [rbp+70h+var_78], 2
0x1400b1241  mov     [rbp+70h+var_64], r12d
0x1400b1245  mov     [rbp+70h+var_58], 8
0x1400b124d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400b1252  mov     r12, [rsp+170h+Object]
0x1400b1257  mov     r15, [rsp+170h+Handle]
0x1400b125c  jmp     loc_1400B1576
0x1400b1261  mov     r12, [rsp+170h+Object]
0x1400b1266  mov     rcx, rdi
0x1400b1269  mov     r15, [rsp+170h+Handle]
0x1400b126e  mov     r9, r12
0x1400b1271  mov     r8, r15
0x1400b1274  call    VsmmProcessMemoryHostingSetupViaProcessPointer
0x1400b1279  mov     ebx, eax
0x1400b127b  test    eax, eax
0x1400b127d  jns     short loc_1400B12E2
0x1400b127f  mov     eax, cs:dword_140065110
0x1400b1285  cmp     eax, 2
0x1400b1288  jbe     loc_1400B1576
0x1400b128e  mov     edx, 100h
0x1400b1293  lea     rcx, dword_140065110
  ... truncated ...
```
