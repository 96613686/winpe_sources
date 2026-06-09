# VsmmMemReservepMemPartSetupViaCreate

- ea: `0x14001843c`
- end: `0x140018a09`
- name: `VsmmMemReservepMemPartSetupViaCreate`
- size: `1485`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400c0ccc`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x14001843c`
- `0x140021c60`
- `0x140021db0`
- `0x140021e00`
- `0x1400a8228`
- `0x1400c06e0`
- `0x1400c1da8`
- `0x1400c3784`
- `0x1400c4d94`
- `0x1400c4e38`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001860b`
- `ntoskrnl!ExAllocatePool2` at `0x1400186e1`
- `ntoskrnl!ExAllocatePool2` at `0x14001860b`
- `ntoskrnl!ExAllocatePool2` at `0x1400186e1`

## string_xrefs

- `0x1400184c7`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x1400185a9`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x140018655`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x14001872c`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x1400187ea`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x140018907`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x14001897f`: `VsmmMemReservepMemPartSetupViaCreate`

## pseudocode

```c
__int64 __fastcall VsmmMemReservepMemPartSetupViaCreate(__int64 a1)
{
  __int64 v1; // r15
  _BYTE *v3; // r14
  __int64 v4; // rcx
  int v5; // ebx
  int *v6; // rax
  int *v7; // rcx
  char *v8; // rdx
  __int64 Pool2; // rax
  int v10; // r8d
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // r8d
  char *v14; // rdx
  unsigned __int8 v15; // dl
  _QWORD *i; // r12
  __int64 v17; // r8
  unsigned __int64 v18; // rcx
  __int64 v19; // r9
  int v21; // [rsp+20h] [rbp-89h]
  _BYTE v22[4]; // [rsp+30h] [rbp-79h] BYREF
  int v23; // [rsp+34h] [rbp-75h] BYREF
  int v24; // [rsp+38h] [rbp-71h] BYREF
  __int64 v25; // [rsp+40h] [rbp-69h] BYREF
  __int64 v26; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v27[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v28[16]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v29[16]; // [rsp+80h] [rbp-29h] BYREF
  int *v30; // [rsp+90h] [rbp-19h]
  __int64 v31; // [rsp+98h] [rbp-11h]
  int *v32; // [rsp+A0h] [rbp-9h]
  __int64 v33; // [rsp+A8h] [rbp-1h]
  int *v34; // [rsp+B0h] [rbp+7h]
  __int64 v35; // [rsp+B8h] [rbp+Fh]
  _BYTE *v36; // [rsp+C0h] [rbp+17h]
  __int64 v37; // [rsp+C8h] [rbp+1Fh]

  v1 = *(int *)(a1 + 28);
  v3 = VidDeviceExtension;
  v4 = *(unsigned int *)(a1 + 28);
  v25 = 0;
  v26 = 0;
  VsmmMemReservepTargetRegistryRemove(v4);
  v5 = VsmmMemReservepRegQueryPageCount(a1, &v25);
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
      v23 = 7064;
      v32 = &v24;
      v6 = &v23;
      v7 = (int *)&v25;
      LODWORD(v25) = v1;
      v8 = byte_140050ECD;
LABEL_5:
      v30 = v6;
      v21 = 7;
      v24 = v5;
LABEL_6:
      v34 = v7;
      v35 = 4;
      v33 = 4;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v8, 0, 0, v21, v27);
      return (unsigned int)v5;
    }
    return (unsigned int)v5;
  }
  if ( !v25 )
    return (unsigned int)-1073741637;
  _InterlockedOr((volatile signed __int32 *)VidDeviceExtension + 162, 8u);
  v5 = VsmmMemPartSetupViaCreate(a1);
  if ( v5 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 8LL * (unsigned __int8)v3[256], 1833788502);
    *(_QWORD *)(a1 + 176) = Pool2;
    if ( !Pool2 )
    {
      v5 = -1073741670;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7109;
        v30 = (int *)&v25;
        v8 = byte_140050F75;
        v22[0] = v3[256];
        v36 = v22;
        v32 = &v24;
        v7 = &v23;
        v21 = 8;
        v24 = v10;
        v23 = v1;
        v37 = 1;
        goto LABEL_6;
      }
      return (unsigned int)v5;
    }
    v11 = ExAllocatePool2(256, 8LL * (unsigned __int8)v3[256], 1833788502);
    *(_QWORD *)(a1 + 192) = v11;
    if ( !v11 )
    {
      v5 = -1073741670;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7127;
        v30 = (int *)&v25;
        v8 = byte_140050FE9;
        v22[0] = v3[256];
        v36 = v22;
        v32 = &v24;
        v7 = &v23;
        v21 = 8;
        v24 = v13;
        v23 = v1;
        v37 = 1;
        goto LABEL_6;
      }
      return (unsigned int)v5;
    }
    v5 = VsmmMemReservepCreatePartitionKey(off_14003B3C0[v1], v12, &v26);
    if ( v5 >= 0 )
    {
      v15 = 0;
      for ( i = *(_QWORD **)(a1 + 176); v15 < v3[256]; i[v17] = v18 >> 8 )
      {
        v17 = v15;
        v18 = *(_QWORD *)(*(_QWORD *)(a1 + 168) + 8LL * v15);
        i[v15] = v18;
        v19 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 8LL * v15);
        if ( v19 != -1 )
          v18 += v19;
        ++v15;
      }
      v5 = VsmmMemReservepTargetSet(a1, v26, i);
      if ( v5 >= 0 )
      {
        memset(i, 0, 8LL * (unsigned __int8)v3[256]);
        v5 = VsmmMemReservepPopulate(a1);
        if ( v5 >= 0 )
        {
          v5 = 0;
        }
        else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
          tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
          LODWORD(v25) = 7214;
          v14 = byte_140050E23;
          goto LABEL_25;
        }
      }
      else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7187;
        v14 = &byte_140050DCF;
        goto LABEL_25;
      }
    }
    else if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
      LODWORD(v25) = 7150;
      v14 = byte_140050D7B;
LABEL_25:
      v31 = 4;
      v32 = &v24;
      v30 = (int *)&v25;
      v34 = &v23;
      v24 = v5;
      v33 = 4;
      v23 = v1;
      v35 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v14, 0, 0, 7, v27);
    }
    if ( v26 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v26);
    return (unsigned int)v5;
  }
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
    LODWORD(v25) = 7088;
    v32 = &v24;
    v6 = (int *)&v25;
    v7 = &v23;
    v23 = v1;
    v8 = byte_140050F21;
    goto LABEL_5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001843c  mov     [rsp-8+arg_8], rbx
0x140018441  mov     [rsp-8+arg_10], rsi
0x140018446  push    rbp
0x140018447  push    rdi
0x140018448  push    r12
0x14001844a  push    r14
0x14001844c  push    r15
0x14001844e  lea     rbp, [rsp-37h]
0x140018453  sub     rsp, 0E0h
0x14001845a  mov     rax, cs:__security_cookie
0x140018461  xor     rax, rsp
0x140018464  mov     [rbp+57h+var_30], rax
0x140018468  movsxd  r15, dword ptr [rcx+1Ch]
0x14001846c  mov     rsi, rcx
0x14001846f  mov     r14, cs:VidDeviceExtension
0x140018476  xor     r12d, r12d
0x140018479  mov     ecx, r15d
0x14001847c  mov     [rbp+57h+var_C0], r12
0x140018480  mov     [rbp+57h+var_B8], r12
0x140018484  call    VsmmMemReservepTargetRegistryRemove
0x140018489  lea     rdx, [rbp+57h+var_C0]
0x14001848d  mov     rcx, rsi
0x140018490  call    VsmmMemReservepRegQueryPageCount
0x140018495  mov     ebx, eax
0x140018497  test    eax, eax
0x140018499  jns     loc_140018554
0x14001849f  mov     ecx, cs:dword_140065110
0x1400184a5  cmp     ecx, 2
0x1400184a8  jbe     loc_1400189DE
0x1400184ae  mov     edx, 100h
0x1400184b3  lea     rcx, dword_140065110
0x1400184ba  call    _tlgKeywordOn
0x1400184bf  test    al, al
0x1400184c1  jz      loc_1400189DE
0x1400184c7  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x1400184ce  lea     rcx, [rbp+57h+var_90]
0x1400184d2  call    _tlgCreate1Sz_char
0x1400184d7  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x1400184de  lea     rcx, [rbp+57h+var_80]
0x1400184e2  call    _tlgCreate1Sz_char
0x1400184e7  lea     rcx, [rbp+57h+var_C8]
0x1400184eb  mov     [rbp+57h+var_CC], 1B98h
0x1400184f2  mov     [rbp+57h+var_60], rcx
0x1400184f6  lea     rax, [rbp+57h+var_CC]
0x1400184fa  lea     rcx, [rbp+57h+var_C0]
0x1400184fe  mov     dword ptr [rbp+57h+var_C0], r15d
0x140018502  lea     rdx, byte_140050ECD
0x140018509  mov     [rbp+57h+var_70], rax
0x14001850d  lea     rax, [rbp+57h+var_B0]
0x140018511  mov     [rsp+100h+var_D8], rax
0x140018516  mov     [rsp+100h+var_E0], 7
0x14001851e  mov     [rbp+57h+var_C8], ebx
0x140018521  mov     [rbp+57h+var_50], rcx
0x140018525  xor     r9d, r9d
0x140018528  lea     rcx, dword_140065110
0x14001852f  mov     [rbp+57h+var_48], 4
0x140018537  xor     r8d, r8d
0x14001853a  mov     [rbp+57h+var_58], 4
0x140018542  mov     [rbp+57h+var_68], 4
0x14001854a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001854f  jmp     loc_1400189DE
0x140018554  cmp     [rbp+57h+var_C0], r12
0x140018558  jnz     short loc_140018564
0x14001855a  mov     ebx, 0C00000BBh
0x14001855f  jmp     loc_1400189DE
0x140018564  mov     rax, cs:VidDeviceExtension
0x14001856b  lock or dword ptr [rax+288h], 8
0x140018573  mov     rcx, rsi
0x140018576  call    VsmmMemPartSetupViaCreate
0x14001857b  mov     ebx, eax
0x14001857d  test    eax, eax
0x14001857f  jns     short loc_1400185F0
0x140018581  mov     eax, cs:dword_140065110
0x140018587  cmp     eax, 2
0x14001858a  jbe     loc_1400189DE
0x140018590  mov     edx, 100h
0x140018595  lea     rcx, dword_140065110
0x14001859c  call    _tlgKeywordOn
0x1400185a1  test    al, al
0x1400185a3  jz      loc_1400189DE
0x1400185a9  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x1400185b0  lea     rcx, [rbp+57h+var_90]
0x1400185b4  call    _tlgCreate1Sz_char
0x1400185b9  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x1400185c0  lea     rcx, [rbp+57h+var_80]
0x1400185c4  call    _tlgCreate1Sz_char
0x1400185c9  lea     rcx, [rbp+57h+var_C8]
0x1400185cd  mov     dword ptr [rbp+57h+var_C0], 1BB0h
0x1400185d4  mov     [rbp+57h+var_60], rcx
0x1400185d8  lea     rax, [rbp+57h+var_C0]
0x1400185dc  lea     rcx, [rbp+57h+var_CC]
0x1400185e0  mov     [rbp+57h+var_CC], r15d
0x1400185e4  lea     rdx, byte_140050F21
0x1400185eb  jmp     loc_140018509
0x1400185f0  movzx   edx, byte ptr [r14+100h]
0x1400185f8  mov     ebx, 6D4D6456h
0x1400185fd  mov     edi, 100h
0x140018602  shl     rdx, 3
0x140018606  mov     r8d, ebx
0x140018609  mov     ecx, edi
0x14001860b  call    cs:__imp_ExAllocatePool2
0x140018612  nop     dword ptr [rax+rax+00h]
0x140018617  mov     [rsi+0B0h], rax
0x14001861e  test    rax, rax
0x140018621  jnz     loc_1400186CF
0x140018627  mov     eax, cs:dword_140065110
0x14001862d  mov     r8d, 0C000009Ah
0x140018633  mov     ebx, r8d
0x140018636  cmp     eax, 2
0x140018639  jbe     loc_1400189DE
0x14001863f  mov     edx, edi
0x140018641  lea     rcx, dword_140065110
0x140018648  call    _tlgKeywordOn
0x14001864d  test    al, al
0x14001864f  jz      loc_1400189DE
0x140018655  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x14001865c  lea     rcx, [rbp+57h+var_90]
0x140018660  call    _tlgCreate1Sz_char
0x140018665  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x14001866c  lea     rcx, [rbp+57h+var_80]
0x140018670  call    _tlgCreate1Sz_char
0x140018675  lea     rax, [rbp+57h+var_C0]
0x140018679  mov     dword ptr [rbp+57h+var_C0], 1BC5h
0x140018680  mov     [rbp+57h+var_70], rax
0x140018684  lea     rcx, [rbp+57h+var_C8]
0x140018688  mov     al, [r14+100h]
0x14001868f  lea     rdx, byte_140050F75
0x140018696  mov     [rbp+57h+var_D0], al
0x140018699  lea     rax, [rbp+57h+var_D0]
0x14001869d  mov     [rbp+57h+var_40], rax
0x1400186a1  lea     rax, [rbp+57h+var_B0]
0x1400186a5  mov     [rsp+100h+var_D8], rax
0x1400186aa  mov     [rbp+57h+var_60], rcx
0x1400186ae  lea     rcx, [rbp+57h+var_CC]
0x1400186b2  mov     [rsp+100h+var_E0], 8
0x1400186ba  mov     [rbp+57h+var_C8], r8d
0x1400186be  mov     [rbp+57h+var_CC], r15d
0x1400186c2  mov     [rbp+57h+var_38], 1
0x1400186ca  jmp     loc_140018521
0x1400186cf  movzx   edx, byte ptr [r14+100h]
0x1400186d7  mov     r8d, ebx
0x1400186da  shl     rdx, 3
0x1400186de  mov     rcx, rdi
0x1400186e1  call    cs:__imp_ExAllocatePool2
0x1400186e8  nop     dword ptr [rax+rax+00h]
0x1400186ed  mov     [rsi+0C0h], rax
0x1400186f4  test    rax, rax
0x1400186f7  jnz     loc_1400187A6
0x1400186fd  mov     eax, cs:dword_140065110
0x140018703  mov     r8d, 0C000009Ah
0x140018709  mov     ebx, r8d
0x14001870c  cmp     eax, 2
0x14001870f  jbe     loc_1400189DE
0x140018715  mov     rdx, rdi
0x140018718  lea     rcx, dword_140065110
0x14001871f  call    _tlgKeywordOn
0x140018724  test    al, al
0x140018726  jz      loc_1400189DE
0x14001872c  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018733  lea     rcx, [rbp+57h+var_90]
0x140018737  call    _tlgCreate1Sz_char
0x14001873c  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018743  lea     rcx, [rbp+57h+var_80]
0x140018747  call    _tlgCreate1Sz_char
0x14001874c  lea     rax, [rbp+57h+var_C0]
0x140018750  mov     dword ptr [rbp+57h+var_C0], 1BD7h
0x140018757  mov     [rbp+57h+var_70], rax
0x14001875b  lea     rcx, [rbp+57h+var_C8]
0x14001875f  mov     al, [r14+100h]
0x140018766  lea     rdx, byte_140050FE9
0x14001876d  mov     [rbp+57h+var_D0], al
0x140018770  lea     rax, [rbp+57h+var_D0]
0x140018774  mov     [rbp+57h+var_40], rax
0x140018778  lea     rax, [rbp+57h+var_B0]
0x14001877c  mov     [rsp+100h+var_D8], rax
0x140018781  mov     [rbp+57h+var_60], rcx
0x140018785  lea     rcx, [rbp+57h+var_CC]
0x140018789  mov     [rsp+100h+var_E0], 8
0x140018791  mov     [rbp+57h+var_C8], r8d
0x140018795  mov     [rbp+57h+var_CC], r15d
0x140018799  mov     [rbp+57h+var_38], 1
0x1400187a1  jmp     loc_140018521
0x1400187a6  lea     rax, off_14003B3C0; "Primary"
0x1400187ad  mov     rcx, [rax+r15*8]
0x1400187b1  lea     r8, [rbp+57h+var_B8]
0x1400187b5  call    VsmmMemReservepCreatePartitionKey
0x1400187ba  mov     ebx, eax
0x1400187bc  test    eax, eax
0x1400187be  jns     loc_140018877
0x1400187c4  mov     eax, cs:dword_140065110
0x1400187ca  cmp     eax, 2
0x1400187cd  jbe     loc_1400189BA
0x1400187d3  mov     rdx, rdi
0x1400187d6  lea     rcx, dword_140065110
0x1400187dd  call    _tlgKeywordOn
0x1400187e2  test    al, al
0x1400187e4  jz      loc_1400189BA
0x1400187ea  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x1400187f1  lea     rcx, [rbp+57h+var_90]
0x1400187f5  call    _tlgCreate1Sz_char
0x1400187fa  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018801  lea     rcx, [rbp+57h+var_80]
0x140018805  call    _tlgCreate1Sz_char
0x14001880a  mov     dword ptr [rbp+57h+var_C0], 1BEEh
0x140018811  lea     rdx, byte_140050D7B
0x140018818  lea     rcx, [rbp+57h+var_C8]
0x14001881c  mov     [rbp+57h+var_68], 4
0x140018824  mov     [rbp+57h+var_60], rcx
0x140018828  lea     rax, [rbp+57h+var_C0]
0x14001882c  lea     rcx, [rbp+57h+var_CC]
0x140018830  mov     [rbp+57h+var_70], rax
0x140018834  lea     rax, [rbp+57h+var_B0]
0x140018838  mov     [rbp+57h+var_50], rcx
0x14001883c  mov     [rsp+100h+var_D8], rax
0x140018841  lea     rcx, dword_140065110
0x140018848  xor     r9d, r9d
0x14001884b  mov     [rbp+57h+var_C8], ebx
0x14001884e  xor     r8d, r8d
0x140018851  mov     [rbp+57h+var_58], 4
0x140018859  mov     [rbp+57h+var_CC], r15d
0x14001885d  mov     [rbp+57h+var_48], 4
0x140018865  mov     [rsp+100h+var_E0], 7
0x14001886d  call    _tlgWriteTransfer_EtwWriteTransfer
0x140018872  jmp     loc_1400189BA
0x140018877  mov     r9b, [r14+100h]
0x14001887e  xor     dl, dl
0x140018880  mov     r12, [rsi+0B0h]
0x140018887  test    r9b, r9b
0x14001888a  jz      short loc_1400188C9
0x14001888c  mov     rax, [rsi+0A8h]
0x140018893  movzx   r8d, dl
0x140018897  mov     rcx, [rax+r8*8]
0x14001889b  mov     [r12+r8*8], rcx
0x14001889f  mov     rax, [rsi+0B8h]
0x1400188a6  mov     r9, [rax+r8*8]
0x1400188aa  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1400188ae  jz      short loc_1400188B3
0x1400188b0  add     rcx, r9
0x1400188b3  shr     rcx, 8
0x1400188b7  inc     dl
0x1400188b9  mov     [r12+r8*8], rcx
0x1400188bd  mov     r9b, [r14+100h]
0x1400188c4  cmp     dl, r9b
0x1400188c7  jb      short loc_14001888C
0x1400188c9  mov     rdx, [rbp+57h+var_B8]
0x1400188cd  mov     r8, r12
0x1400188d0  mov     rcx, rsi
0x1400188d3  call    VsmmMemReservepTargetSet
0x1400188d8  mov     ebx, eax
0x1400188da  test    eax, eax
0x1400188dc  jns     short loc_14001893A
0x1400188de  mov     eax, cs:dword_140065110
0x1400188e4  cmp     eax, 2
0x1400188e7  jbe     loc_1400189B7
0x1400188ed  mov     rdx, rdi
0x1400188f0  lea     rcx, dword_140065110
0x1400188f7  call    _tlgKeywordOn
0x1400188fc  xor     r12d, r12d
0x1400188ff  test    al, al
0x140018901  jz      loc_1400189BA
0x140018907  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x14001890e  lea     rcx, [rbp+57h+var_90]
0x140018912  call    _tlgCreate1Sz_char
0x140018917  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x14001891e  lea     rcx, [rbp+57h+var_80]
0x140018922  call    _tlgCreate1Sz_char
0x140018927  mov     dword ptr [rbp+57h+var_C0], 1C13h
0x14001892e  lea     rdx, byte_140050DCF
0x140018935  jmp     loc_140018818
0x14001893a  movzx   r8d, byte ptr [r14+100h]
0x140018942  xor     edx, edx; Val
0x140018944  shl     r8, 3; Size
0x140018948  mov     rcx, r12; void *
0x14001894b  call    memset
0x140018950  mov     rcx, rsi
0x140018953  call    VsmmMemReservepPopulate
0x140018958  xor     r12d, r12d
0x14001895b  mov     ebx, eax
0x14001895d  test    eax, eax
0x14001895f  jns     short loc_1400189B2
0x140018961  mov     eax, cs:dword_140065110
0x140018967  cmp     eax, 2
0x14001896a  jbe     short loc_1400189BA
0x14001896c  mov     rdx, rdi
0x14001896f  lea     rcx, dword_140065110
0x140018976  call    _tlgKeywordOn
0x14001897b  test    al, al
0x14001897d  jz      short loc_1400189BA
0x14001897f  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018986  lea     rcx, [rbp+57h+var_90]
0x14001898a  call    _tlgCreate1Sz_char
0x14001898f  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018996  lea     rcx, [rbp+57h+var_80]
0x14001899a  call    _tlgCreate1Sz_char
0x14001899f  mov     dword ptr [rbp+57h+var_C0], 1C2Eh
0x1400189a6  lea     rdx, byte_140050E23
0x1400189ad  jmp     loc_140018818
0x1400189b2  mov     ebx, r12d
0x1400189b5  jmp     short loc_1400189BA
0x1400189b7  xor     r12d, r12d
  ... truncated ...
```
