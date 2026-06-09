# VsmmCloneTemplateApply

- ea: `0x1400aeedc`
- end: `0x1400af7bf`
- name: `VsmmCloneTemplateApply`
- size: `2275`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008d084`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140034554`
- `0x140034584`
- `0x140073864`
- `0x140074acc`
- `0x140077b5c`
- `0x1400a4db0`
- `0x1400a4e30`
- `0x1400aeedc`
- `0x1400f3d30`
- `0x1400fad1c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400af755`
- `ntoskrnl!ObfDereferenceObject` at `0x1400af755`
- `ntoskrnl!ZwClose` at `0x1400af769`
- `ntoskrnl!ZwClose` at `0x1400af769`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400aef41`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400af28e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400af2cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400aef41`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400af28e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400af2cd`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400af29d`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400af29d`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400af790`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1400af790`
- `ntoskrnl!PsGetProcessJob` at `0x1400af2dc`
- `ntoskrnl!PsGetProcessJob` at `0x1400af2dc`

## string_xrefs

- `0x1400aef8a`: `VsmmCloneTemplateApply`
- `0x1400af09b`: `VsmmCloneTemplateApply`
- `0x1400af131`: `VsmmCloneTemplateApply`
- `0x1400af1be`: `VsmmCloneTemplateApply`
- `0x1400af34c`: `VsmmCloneTemplateApply`
- `0x1400af467`: `VsmmCloneTemplateApply`
- `0x1400af4ee`: `VsmmCloneTemplateApply`
- `0x1400af5ff`: `VsmmCloneTemplateApply`
- `0x1400af670`: `VsmmCloneTemplateApply`

## pseudocode

```c
__int64 __fastcall VsmmCloneTemplateApply(__int64 a1, __int64 a2)
{
  PVOID v2; // rsi
  __int64 v3; // rbx
  char *v4; // r13
  PVOID v5; // r12
  HANDLE v6; // r15
  int v8; // ebx
  __int64 v9; // r9
  char *v10; // rdx
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
  char *v27; // rdx
  char v29; // [rsp+40h] [rbp-C0h]
  _QWORD *v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
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
  v30 = (_QWORD *)a2;
  P = 0;
  v31 = 0;
  Object = 0;
  Handle = 0;
  if ( PsGetCurrentProcess() != v3 )
  {
    v8 = -1073741811;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(P) = 773;
      p_P = &P;
      v10 = byte_14004E729;
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
      v31 = *(_QWORD *)(a1 + 648);
      p_Handle = (HANDLE *)&v31;
      v46 = 2;
      v44 = 16;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v10, v13, v9, 10, v36);
      return (unsigned int)v8;
    }
    return (unsigned int)v8;
  }
  if ( (*(_BYTE *)(a1 + 40) & 4) != 0 )
  {
    v8 = -1073741790;
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 783;
      p_P = (PVOID *)&v30;
      v10 = &byte_14004E797;
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v30) = 804;
        p_P = (PVOID *)&v30;
        v10 = byte_14004E873;
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
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
          v31 = *(_QWORD *)(a1 + 648);
          p_Handle = (HANDLE *)&v31;
          v44 = 16;
          v46 = 2;
          v49 = 0;
          v51 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004E64D, 0, 0, 10, v36);
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
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          goto LABEL_59;
        tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
        tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
        LODWORD(v30) = 869;
        v27 = byte_14004E6BB;
        v49 = 0;
        goto LABEL_58;
      }
      v5 = 0;
      v29 = 1;
      v6 = 0;
      v8 = VsmmClonepTemplateAlloc(3, &v31);
      if ( v8 < 0 )
      {
        if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
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
          tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_14004E503, 0, 0, 10, v36);
        }
        v2 = (PVOID)v31;
        goto LABEL_59;
      }
      v2 = (PVOID)v31;
      v8 = VsmmClonepTemplateDuplicateMemoryBlockTree((__int64)v30, (_OWORD *)(v31 + 104));
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
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_59;
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 905;
      v27 = byte_14004E571;
    }
    else
    {
LABEL_54:
      v22 = 0;
      v8 = -1073741275;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        goto LABEL_59;
      tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
      tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
      LODWORD(v30) = 819;
      v27 = &byte_14004E5DF;
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
    v31 = *(_QWORD *)(a1 + 648);
    p_Handle = (HANDLE *)&v31;
    v46 = 2;
    v51 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v27, 0, 0, 10, v36);
    goto LABEL_59;
  }
  v8 = -1073741811;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v37, "VsmmCloneTemplateApply");
    tlgCreate1Sz_char(v38, "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone.c");
    LODWORD(v30) = 794;
    p_P = (PVOID *)&v30;
    v10 = byte_14004E805;
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
0x1400aeedc  push    rbp
0x1400aeede  push    rbx
0x1400aeedf  push    rsi
0x1400aeee0  push    rdi
0x1400aeee1  push    r12
0x1400aeee3  push    r13
0x1400aeee5  push    r14
0x1400aeee7  push    r15
0x1400aeee9  lea     rbp, [rsp-38h]
0x1400aeeee  sub     rsp, 138h
0x1400aeef5  mov     rax, cs:__security_cookie
0x1400aeefc  xor     rax, rsp
0x1400aeeff  mov     [rbp+70h+var_50], rax
0x1400aef03  mov     r13, cs:VidDeviceExtension
0x1400aef0a  xor     esi, esi
0x1400aef0c  mov     rbx, [rcx+2800h]
0x1400aef13  add     r13, 2A8h
0x1400aef1a  xor     r12d, r12d
0x1400aef1d  mov     [rsp+170h+var_100], r13
0x1400aef22  xor     r15d, r15d
0x1400aef25  mov     [rsp+170h+var_128], rdx
0x1400aef2a  mov     rdi, rcx
0x1400aef2d  mov     [rsp+170h+P], rsi
0x1400aef32  mov     [rsp+170h+var_120], rsi
0x1400aef37  mov     [rsp+170h+Object], r12
0x1400aef3c  mov     [rsp+170h+Handle], r15
0x1400aef41  call    cs:__imp_PsGetCurrentProcess
0x1400aef48  nop     dword ptr [rax+rax+00h]
0x1400aef4d  cmp     rax, rbx
0x1400aef50  jz      loc_1400AF05B
0x1400aef56  mov     eax, cs:dword_140064110
0x1400aef5c  mov     r8d, 0C000000Dh
0x1400aef62  mov     ebx, r8d
0x1400aef65  cmp     eax, 2
0x1400aef68  jbe     loc_1400AF79C
0x1400aef6e  mov     edx, 100h
0x1400aef73  lea     rcx, dword_140064110
0x1400aef7a  call    _tlgKeywordOn
0x1400aef7f  xor     r9d, r9d
0x1400aef82  test    al, al
0x1400aef84  jz      loc_1400AF79C
0x1400aef8a  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400aef91  lea     rcx, [rbp+70h+var_D0]
0x1400aef95  call    _tlgCreate1Sz_char
0x1400aef9a  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400aefa1  lea     rcx, [rbp+70h+var_C0]
0x1400aefa5  call    _tlgCreate1Sz_char
0x1400aefaa  lea     rax, [rsp+170h+P]
0x1400aefaf  mov     dword ptr [rsp+170h+P], 305h
0x1400aefb7  mov     [rbp+70h+var_B0], rax
0x1400aefbb  lea     rdx, byte_14004E729
0x1400aefc2  lea     rax, [rsp+170h+var_128]
0x1400aefc7  mov     [rbp+70h+var_A8], 4
0x1400aefcf  mov     dword ptr [rsp+170h+var_128], r8d
0x1400aefd4  mov     [rbp+70h+var_98], 4
0x1400aefdc  mov     [rbp+70h+var_64], r9d
0x1400aefe0  xor     r8d, r8d
0x1400aefe3  mov     [rbp+70h+var_A0], rax
0x1400aefe7  lea     rcx, dword_140064110
0x1400aefee  lea     rax, [rdi+290h]
0x1400aeff5  mov     [rbp+70h+var_58], 8
0x1400aeffd  mov     [rbp+70h+var_90], rax
0x1400af001  lea     rax, [rbp+70h+var_68]
0x1400af005  mov     [rbp+70h+var_80], rax
0x1400af009  mov     rax, [rdi+80h]
0x1400af010  mov     [rbp+70h+var_70], rax
0x1400af014  movzx   eax, word ptr [rdi+78h]
0x1400af018  mov     [rbp+70h+var_68], eax
0x1400af01b  mov     rax, [rdi+288h]
0x1400af022  mov     [rsp+170h+var_120], rax
0x1400af027  lea     rax, [rsp+170h+var_120]
0x1400af02c  mov     [rbp+70h+var_60], rax
0x1400af030  lea     rax, [rbp+70h+var_F0]
0x1400af034  mov     [rsp+170h+var_148], rax
0x1400af039  mov     dword ptr [rsp+170h+var_150], 0Ah
0x1400af041  mov     [rbp+70h+var_78], 2
0x1400af049  mov     [rbp+70h+var_88], 10h
0x1400af051  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400af056  jmp     loc_1400AF79C
0x1400af05b  mov     r14d, 4
0x1400af061  test    [rdi+28h], r14b
0x1400af065  jz      loc_1400AF0F0
0x1400af06b  mov     eax, cs:dword_140064110
0x1400af071  mov     ebx, 0C0000022h
0x1400af076  cmp     eax, 2
0x1400af079  jbe     loc_1400AF79C
0x1400af07f  mov     edx, 100h
0x1400af084  lea     rcx, dword_140064110
0x1400af08b  call    _tlgKeywordOn
0x1400af090  xor     r8d, r8d
0x1400af093  test    al, al
0x1400af095  jz      loc_1400AF79C
0x1400af09b  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400af0a2  lea     rcx, [rbp+70h+var_D0]
0x1400af0a6  call    _tlgCreate1Sz_char
0x1400af0ab  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400af0b2  lea     rcx, [rbp+70h+var_C0]
0x1400af0b6  call    _tlgCreate1Sz_char
0x1400af0bb  lea     rax, [rsp+170h+var_128]
0x1400af0c0  mov     dword ptr [rsp+170h+var_128], 30Fh
0x1400af0c8  mov     [rbp+70h+var_B0], rax
0x1400af0cc  lea     rdx, byte_14004E797
0x1400af0d3  lea     rax, [rsp+170h+P]
0x1400af0d8  mov     [rbp+70h+var_A8], r14
0x1400af0dc  mov     dword ptr [rsp+170h+P], ebx
0x1400af0e0  xor     r9d, r9d
0x1400af0e3  mov     [rbp+70h+var_98], r14
0x1400af0e7  mov     [rbp+70h+var_64], r8d
0x1400af0eb  jmp     loc_1400AEFE3
0x1400af0f0  xor     r9d, r9d
0x1400af0f3  cmp     [rdi+2858h], r9
0x1400af0fa  jz      loc_1400AF180
0x1400af100  mov     eax, cs:dword_140064110
0x1400af106  mov     r8d, 0C000000Dh
0x1400af10c  mov     ebx, r8d
0x1400af10f  cmp     eax, 2
0x1400af112  jbe     loc_1400AF79C
0x1400af118  mov     edx, 100h
0x1400af11d  lea     rcx, dword_140064110
0x1400af124  call    _tlgKeywordOn
0x1400af129  test    al, al
0x1400af12b  jz      loc_1400AF79C
0x1400af131  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400af138  lea     rcx, [rbp+70h+var_D0]
0x1400af13c  call    _tlgCreate1Sz_char
0x1400af141  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400af148  lea     rcx, [rbp+70h+var_C0]
0x1400af14c  call    _tlgCreate1Sz_char
0x1400af151  lea     rax, [rsp+170h+var_128]
0x1400af156  mov     dword ptr [rsp+170h+var_128], 31Ah
0x1400af15e  mov     [rbp+70h+var_B0], rax
0x1400af162  lea     rdx, byte_14004E805
0x1400af169  lea     rax, [rsp+170h+P]
0x1400af16e  mov     [rbp+70h+var_A8], r14
0x1400af172  mov     dword ptr [rsp+170h+P], r8d
0x1400af177  mov     [rbp+70h+var_98], r14
0x1400af17b  jmp     loc_1400AEFDC
0x1400af180  cmp     [rdi+28A0h], r9
0x1400af187  jz      loc_1400AF20D
0x1400af18d  mov     eax, cs:dword_140064110
0x1400af193  mov     r8d, 0C000000Dh
0x1400af199  mov     ebx, r8d
0x1400af19c  cmp     eax, 2
0x1400af19f  jbe     loc_1400AF79C
0x1400af1a5  mov     edx, 100h
0x1400af1aa  lea     rcx, dword_140064110
0x1400af1b1  call    _tlgKeywordOn
0x1400af1b6  test    al, al
0x1400af1b8  jz      loc_1400AF79C
0x1400af1be  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400af1c5  lea     rcx, [rbp+70h+var_D0]
0x1400af1c9  call    _tlgCreate1Sz_char
0x1400af1ce  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400af1d5  lea     rcx, [rbp+70h+var_C0]
0x1400af1d9  call    _tlgCreate1Sz_char
0x1400af1de  lea     rax, [rsp+170h+var_128]
0x1400af1e3  mov     dword ptr [rsp+170h+var_128], 324h
0x1400af1eb  mov     [rbp+70h+var_B0], rax
0x1400af1ef  lea     rdx, byte_14004E873
0x1400af1f6  lea     rax, [rsp+170h+P]
0x1400af1fb  mov     [rbp+70h+var_A8], r14
0x1400af1ff  mov     dword ptr [rsp+170h+P], r8d
0x1400af204  mov     [rbp+70h+var_98], r14
0x1400af208  jmp     loc_1400AEFDC
0x1400af20d  mov     rcx, r13
0x1400af210  mov     [rsp+170h+var_130], r9b
0x1400af215  call    VidObjectLockAcquireShared
0x1400af21a  lea     rcx, [r13+10h]
0x1400af21e  test    byte ptr [rcx+8], 1
0x1400af222  mov     rbx, [rcx]
0x1400af225  jz      short loc_1400AF22F
0x1400af227  test    rbx, rbx
0x1400af22a  jz      short loc_1400AF22F
0x1400af22c  xor     rbx, rcx
0x1400af22f  movzx   r13d, byte ptr [rcx+8]
0x1400af234  and     r13d, 1
0x1400af238  test    rbx, rbx
0x1400af23b  jz      loc_1400AF640
0x1400af241  mov     rsi, [rsp+170h+var_128]
0x1400af246  mov     rdx, rbx
0x1400af249  mov     rcx, rsi
0x1400af24c  call    VsmmClonepTableNodeCompareById
0x1400af251  test    eax, eax
0x1400af253  jns     short loc_1400AF25A
0x1400af255  mov     rax, [rbx]
0x1400af258  jmp     short loc_1400AF260
0x1400af25a  jle     short loc_1400AF277
0x1400af25c  mov     rax, [rbx+8]
0x1400af260  test    r13d, r13d
0x1400af263  jz      short loc_1400AF26F
0x1400af265  test    rax, rax
0x1400af268  jz      short loc_1400AF26F
0x1400af26a  xor     rbx, rax
0x1400af26d  jmp     short loc_1400AF272
0x1400af26f  mov     rbx, rax
0x1400af272  test    rbx, rbx
0x1400af275  jnz     short loc_1400AF246
0x1400af277  mov     rsi, [rsp+170h+P]
0x1400af27c  test    rbx, rbx
0x1400af27f  jz      loc_1400AF640
0x1400af285  lea     r15, [rbx-20h]
0x1400af289  mov     [rsp+170h+var_128], r15
0x1400af28e  call    cs:__imp_PsGetCurrentProcess
0x1400af295  nop     dword ptr [rax+rax+00h]
0x1400af29a  mov     rcx, rax; Process
0x1400af29d  call    cs:__imp_PsReferencePrimaryToken
0x1400af2a4  nop     dword ptr [rax+rax+00h]
0x1400af2a9  mov     ecx, [rdi+10h]
0x1400af2ac  mov     r13, rax
0x1400af2af  mov     edx, [rdi+18h]
0x1400af2b2  and     ecx, 4000h
0x1400af2b8  shr     rdx, 4
0x1400af2bc  and     edx, r14d
0x1400af2bf  mov     ebx, edx
0x1400af2c1  or      ebx, 8
0x1400af2c4  test    rcx, rcx
0x1400af2c7  cmovz   ebx, edx
0x1400af2ca  or      ebx, 1
0x1400af2cd  call    cs:__imp_PsGetCurrentProcess
0x1400af2d4  nop     dword ptr [rax+rax+00h]
0x1400af2d9  mov     rcx, rax
0x1400af2dc  call    cs:__imp_PsGetProcessJob
0x1400af2e3  nop     dword ptr [rax+rax+00h]
0x1400af2e8  lea     rdx, [rsp+170h+Handle]
0x1400af2ed  mov     r9d, ebx; int
0x1400af2f0  mov     [rsp+170h+var_140], rdx; __int64
0x1400af2f5  lea     rcx, [rdi+2860h]
0x1400af2fc  lea     rdx, [rsp+170h+Object]
0x1400af301  mov     r8, rax; int
0x1400af304  mov     [rsp+170h+var_148], rdx; __int64
0x1400af309  mov     rdx, r13; int
0x1400af30c  mov     [rsp+170h+var_150], rcx; PVOID
0x1400af311  mov     rcx, [r15+58h]; int
0x1400af315  call    VsmmNtSlatMemoryProcessCreate
0x1400af31a  mov     ebx, eax
0x1400af31c  test    eax, eax
0x1400af31e  jns     loc_1400AF421
0x1400af324  mov     ecx, cs:dword_140064110
0x1400af32a  cmp     ecx, 2
0x1400af32d  jbe     loc_1400AF412
0x1400af333  mov     edx, 100h
0x1400af338  lea     rcx, dword_140064110
0x1400af33f  call    _tlgKeywordOn
0x1400af344  test    al, al
0x1400af346  jz      loc_1400AF412
0x1400af34c  lea     rdx, aVsmmclonetempl; "VsmmCloneTemplateApply"
0x1400af353  lea     rcx, [rbp+70h+var_D0]
0x1400af357  call    _tlgCreate1Sz_char
0x1400af35c  lea     rdx, aOnecoreVmVidSy_25; "onecore\\vm\\vid\\sys\\vsmm\\vsmmclone."...
0x1400af363  lea     rcx, [rbp+70h+var_C0]
0x1400af367  call    _tlgCreate1Sz_char
0x1400af36c  lea     rax, [rsp+170h+var_128]
0x1400af371  mov     dword ptr [rsp+170h+var_128], 356h
0x1400af379  mov     [rbp+70h+var_B0], rax
0x1400af37d  lea     rdx, byte_14004E64D
0x1400af384  lea     rax, [rsp+170h+P]
0x1400af389  mov     [rbp+70h+var_A8], r14
0x1400af38d  mov     [rbp+70h+var_A0], rax
0x1400af391  lea     rcx, dword_140064110
0x1400af398  lea     rax, [rdi+290h]
0x1400af39f  mov     dword ptr [rsp+170h+P], ebx
0x1400af3a3  mov     [rbp+70h+var_90], rax
0x1400af3a7  xor     r9d, r9d
0x1400af3aa  lea     rax, [rbp+70h+var_68]
0x1400af3ae  mov     [rbp+70h+var_98], r14
0x1400af3b2  mov     [rbp+70h+var_80], rax
0x1400af3b6  xor     r8d, r8d
0x1400af3b9  mov     rax, [rdi+80h]
0x1400af3c0  mov     [rbp+70h+var_70], rax
0x1400af3c4  movzx   eax, word ptr [rdi+78h]
0x1400af3c8  mov     [rbp+70h+var_68], eax
0x1400af3cb  mov     rax, [rdi+288h]
0x1400af3d2  mov     [rsp+170h+var_120], rax
0x1400af3d7  lea     rax, [rsp+170h+var_120]
0x1400af3dc  mov     [rbp+70h+var_60], rax
0x1400af3e0  lea     rax, [rbp+70h+var_F0]
0x1400af3e4  mov     [rsp+170h+var_148], rax
0x1400af3e9  mov     dword ptr [rsp+170h+var_150], 0Ah
0x1400af3f1  mov     [rbp+70h+var_88], 10h
0x1400af3f9  mov     [rbp+70h+var_78], 2
0x1400af401  mov     [rbp+70h+var_64], r12d
0x1400af405  mov     [rbp+70h+var_58], 8
0x1400af40d  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400af412  mov     r12, [rsp+170h+Object]
0x1400af417  mov     r15, [rsp+170h+Handle]
0x1400af41c  jmp     loc_1400AF736
0x1400af421  mov     r12, [rsp+170h+Object]
0x1400af426  mov     rcx, rdi
0x1400af429  mov     r15, [rsp+170h+Handle]
0x1400af42e  mov     r9, r12
0x1400af431  mov     r8, r15
0x1400af434  call    VsmmProcessMemoryHostingSetupViaProcessPointer
0x1400af439  mov     ebx, eax
0x1400af43b  test    eax, eax
0x1400af43d  jns     short loc_1400AF4A2
0x1400af43f  mov     eax, cs:dword_140064110
0x1400af445  cmp     eax, 2
0x1400af448  jbe     loc_1400AF736
0x1400af44e  mov     edx, 100h
0x1400af453  lea     rcx, dword_140064110
  ... truncated ...
```
