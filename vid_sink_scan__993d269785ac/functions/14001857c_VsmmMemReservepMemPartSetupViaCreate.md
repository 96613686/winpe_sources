# VsmmMemReservepMemPartSetupViaCreate

- ea: `0x14001857c`
- end: `0x140018b49`
- name: `VsmmMemReservepMemPartSetupViaCreate`
- size: `1485`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400beccc`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x14001857c`
- `0x140021650`
- `0x1400217a0`
- `0x140021800`
- `0x1400a64c0`
- `0x1400be6e0`
- `0x1400bfda8`
- `0x1400c1784`
- `0x1400c2d94`
- `0x1400c2e38`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001874b`
- `ntoskrnl!ExAllocatePool2` at `0x140018821`
- `ntoskrnl!ExAllocatePool2` at `0x14001874b`
- `ntoskrnl!ExAllocatePool2` at `0x140018821`

## string_xrefs

- `0x140018607`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x1400186e9`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x140018795`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x14001886c`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x14001892a`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x140018a47`: `VsmmMemReservepMemPartSetupViaCreate`
- `0x140018abf`: `VsmmMemReservepMemPartSetupViaCreate`

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
    if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
      v23 = 7064;
      v32 = &v24;
      v6 = &v23;
      v7 = (int *)&v25;
      LODWORD(v25) = v1;
      v8 = byte_140050BC9;
LABEL_5:
      v30 = v6;
      v21 = 7;
      v24 = v5;
LABEL_6:
      v34 = v7;
      v35 = 4;
      v33 = 4;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v8, 0, 0, v21, v27);
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7109;
        v30 = (int *)&v25;
        v8 = byte_1400509E5;
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
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7127;
        v30 = (int *)&v25;
        v8 = byte_140050A59;
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
    v5 = VsmmMemReservepCreatePartitionKey(off_14003B3A0[v1], v12, &v26);
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
        else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        {
          tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
          tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
          LODWORD(v25) = 7214;
          v14 = byte_140050891;
          goto LABEL_25;
        }
      }
      else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
        tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
        LODWORD(v25) = 7187;
        v14 = byte_14005083D;
        goto LABEL_25;
      }
    }
    else if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
    {
      tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
      tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
      LODWORD(v25) = 7150;
      v14 = byte_140050ACD;
LABEL_25:
      v31 = 4;
      v32 = &v24;
      v30 = (int *)&v25;
      v34 = &v23;
      v24 = v5;
      v33 = 4;
      v23 = v1;
      v35 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v14, 0, 0, 7, v27);
    }
    if ( v26 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1848))(WdfDriverGlobals, v26);
    return (unsigned int)v5;
  }
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v28, "VsmmMemReservepMemPartSetupViaCreate");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemreserve.c");
    LODWORD(v25) = 7088;
    v32 = &v24;
    v6 = (int *)&v25;
    v7 = &v23;
    v23 = v1;
    v8 = byte_140050991;
    goto LABEL_5;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001857c  mov     [rsp-8+arg_8], rbx
0x140018581  mov     [rsp-8+arg_10], rsi
0x140018586  push    rbp
0x140018587  push    rdi
0x140018588  push    r12
0x14001858a  push    r14
0x14001858c  push    r15
0x14001858e  lea     rbp, [rsp-37h]
0x140018593  sub     rsp, 0E0h
0x14001859a  mov     rax, cs:__security_cookie
0x1400185a1  xor     rax, rsp
0x1400185a4  mov     [rbp+57h+var_30], rax
0x1400185a8  movsxd  r15, dword ptr [rcx+1Ch]
0x1400185ac  mov     rsi, rcx
0x1400185af  mov     r14, cs:VidDeviceExtension
0x1400185b6  xor     r12d, r12d
0x1400185b9  mov     ecx, r15d
0x1400185bc  mov     [rbp+57h+var_C0], r12
0x1400185c0  mov     [rbp+57h+var_B8], r12
0x1400185c4  call    VsmmMemReservepTargetRegistryRemove
0x1400185c9  lea     rdx, [rbp+57h+var_C0]
0x1400185cd  mov     rcx, rsi
0x1400185d0  call    VsmmMemReservepRegQueryPageCount
0x1400185d5  mov     ebx, eax
0x1400185d7  test    eax, eax
0x1400185d9  jns     loc_140018694
0x1400185df  mov     ecx, cs:dword_140064110
0x1400185e5  cmp     ecx, 2
0x1400185e8  jbe     loc_140018B1E
0x1400185ee  mov     edx, 100h
0x1400185f3  lea     rcx, dword_140064110
0x1400185fa  call    _tlgKeywordOn
0x1400185ff  test    al, al
0x140018601  jz      loc_140018B1E
0x140018607  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x14001860e  lea     rcx, [rbp+57h+var_90]
0x140018612  call    _tlgCreate1Sz_char
0x140018617  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x14001861e  lea     rcx, [rbp+57h+var_80]
0x140018622  call    _tlgCreate1Sz_char
0x140018627  lea     rcx, [rbp+57h+var_C8]
0x14001862b  mov     [rbp+57h+var_CC], 1B98h
0x140018632  mov     [rbp+57h+var_60], rcx
0x140018636  lea     rax, [rbp+57h+var_CC]
0x14001863a  lea     rcx, [rbp+57h+var_C0]
0x14001863e  mov     dword ptr [rbp+57h+var_C0], r15d
0x140018642  lea     rdx, byte_140050BC9
0x140018649  mov     [rbp+57h+var_70], rax
0x14001864d  lea     rax, [rbp+57h+var_B0]
0x140018651  mov     [rsp+100h+var_D8], rax
0x140018656  mov     [rsp+100h+var_E0], 7
0x14001865e  mov     [rbp+57h+var_C8], ebx
0x140018661  mov     [rbp+57h+var_50], rcx
0x140018665  xor     r9d, r9d
0x140018668  lea     rcx, dword_140064110
0x14001866f  mov     [rbp+57h+var_48], 4
0x140018677  xor     r8d, r8d
0x14001867a  mov     [rbp+57h+var_58], 4
0x140018682  mov     [rbp+57h+var_68], 4
0x14001868a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001868f  jmp     loc_140018B1E
0x140018694  cmp     [rbp+57h+var_C0], r12
0x140018698  jnz     short loc_1400186A4
0x14001869a  mov     ebx, 0C00000BBh
0x14001869f  jmp     loc_140018B1E
0x1400186a4  mov     rax, cs:VidDeviceExtension
0x1400186ab  lock or dword ptr [rax+288h], 8
0x1400186b3  mov     rcx, rsi
0x1400186b6  call    VsmmMemPartSetupViaCreate
0x1400186bb  mov     ebx, eax
0x1400186bd  test    eax, eax
0x1400186bf  jns     short loc_140018730
0x1400186c1  mov     eax, cs:dword_140064110
0x1400186c7  cmp     eax, 2
0x1400186ca  jbe     loc_140018B1E
0x1400186d0  mov     edx, 100h
0x1400186d5  lea     rcx, dword_140064110
0x1400186dc  call    _tlgKeywordOn
0x1400186e1  test    al, al
0x1400186e3  jz      loc_140018B1E
0x1400186e9  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x1400186f0  lea     rcx, [rbp+57h+var_90]
0x1400186f4  call    _tlgCreate1Sz_char
0x1400186f9  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018700  lea     rcx, [rbp+57h+var_80]
0x140018704  call    _tlgCreate1Sz_char
0x140018709  lea     rcx, [rbp+57h+var_C8]
0x14001870d  mov     dword ptr [rbp+57h+var_C0], 1BB0h
0x140018714  mov     [rbp+57h+var_60], rcx
0x140018718  lea     rax, [rbp+57h+var_C0]
0x14001871c  lea     rcx, [rbp+57h+var_CC]
0x140018720  mov     [rbp+57h+var_CC], r15d
0x140018724  lea     rdx, byte_140050991
0x14001872b  jmp     loc_140018649
0x140018730  movzx   edx, byte ptr [r14+100h]
0x140018738  mov     ebx, 6D4D6456h
0x14001873d  mov     edi, 100h
0x140018742  shl     rdx, 3
0x140018746  mov     r8d, ebx
0x140018749  mov     ecx, edi
0x14001874b  call    cs:__imp_ExAllocatePool2
0x140018752  nop     dword ptr [rax+rax+00h]
0x140018757  mov     [rsi+0B0h], rax
0x14001875e  test    rax, rax
0x140018761  jnz     loc_14001880F
0x140018767  mov     eax, cs:dword_140064110
0x14001876d  mov     r8d, 0C000009Ah
0x140018773  mov     ebx, r8d
0x140018776  cmp     eax, 2
0x140018779  jbe     loc_140018B1E
0x14001877f  mov     edx, edi
0x140018781  lea     rcx, dword_140064110
0x140018788  call    _tlgKeywordOn
0x14001878d  test    al, al
0x14001878f  jz      loc_140018B1E
0x140018795  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x14001879c  lea     rcx, [rbp+57h+var_90]
0x1400187a0  call    _tlgCreate1Sz_char
0x1400187a5  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x1400187ac  lea     rcx, [rbp+57h+var_80]
0x1400187b0  call    _tlgCreate1Sz_char
0x1400187b5  lea     rax, [rbp+57h+var_C0]
0x1400187b9  mov     dword ptr [rbp+57h+var_C0], 1BC5h
0x1400187c0  mov     [rbp+57h+var_70], rax
0x1400187c4  lea     rcx, [rbp+57h+var_C8]
0x1400187c8  mov     al, [r14+100h]
0x1400187cf  lea     rdx, byte_1400509E5
0x1400187d6  mov     [rbp+57h+var_D0], al
0x1400187d9  lea     rax, [rbp+57h+var_D0]
0x1400187dd  mov     [rbp+57h+var_40], rax
0x1400187e1  lea     rax, [rbp+57h+var_B0]
0x1400187e5  mov     [rsp+100h+var_D8], rax
0x1400187ea  mov     [rbp+57h+var_60], rcx
0x1400187ee  lea     rcx, [rbp+57h+var_CC]
0x1400187f2  mov     [rsp+100h+var_E0], 8
0x1400187fa  mov     [rbp+57h+var_C8], r8d
0x1400187fe  mov     [rbp+57h+var_CC], r15d
0x140018802  mov     [rbp+57h+var_38], 1
0x14001880a  jmp     loc_140018661
0x14001880f  movzx   edx, byte ptr [r14+100h]
0x140018817  mov     r8d, ebx
0x14001881a  shl     rdx, 3
0x14001881e  mov     rcx, rdi
0x140018821  call    cs:__imp_ExAllocatePool2
0x140018828  nop     dword ptr [rax+rax+00h]
0x14001882d  mov     [rsi+0C0h], rax
0x140018834  test    rax, rax
0x140018837  jnz     loc_1400188E6
0x14001883d  mov     eax, cs:dword_140064110
0x140018843  mov     r8d, 0C000009Ah
0x140018849  mov     ebx, r8d
0x14001884c  cmp     eax, 2
0x14001884f  jbe     loc_140018B1E
0x140018855  mov     rdx, rdi
0x140018858  lea     rcx, dword_140064110
0x14001885f  call    _tlgKeywordOn
0x140018864  test    al, al
0x140018866  jz      loc_140018B1E
0x14001886c  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018873  lea     rcx, [rbp+57h+var_90]
0x140018877  call    _tlgCreate1Sz_char
0x14001887c  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018883  lea     rcx, [rbp+57h+var_80]
0x140018887  call    _tlgCreate1Sz_char
0x14001888c  lea     rax, [rbp+57h+var_C0]
0x140018890  mov     dword ptr [rbp+57h+var_C0], 1BD7h
0x140018897  mov     [rbp+57h+var_70], rax
0x14001889b  lea     rcx, [rbp+57h+var_C8]
0x14001889f  mov     al, [r14+100h]
0x1400188a6  lea     rdx, byte_140050A59
0x1400188ad  mov     [rbp+57h+var_D0], al
0x1400188b0  lea     rax, [rbp+57h+var_D0]
0x1400188b4  mov     [rbp+57h+var_40], rax
0x1400188b8  lea     rax, [rbp+57h+var_B0]
0x1400188bc  mov     [rsp+100h+var_D8], rax
0x1400188c1  mov     [rbp+57h+var_60], rcx
0x1400188c5  lea     rcx, [rbp+57h+var_CC]
0x1400188c9  mov     [rsp+100h+var_E0], 8
0x1400188d1  mov     [rbp+57h+var_C8], r8d
0x1400188d5  mov     [rbp+57h+var_CC], r15d
0x1400188d9  mov     [rbp+57h+var_38], 1
0x1400188e1  jmp     loc_140018661
0x1400188e6  lea     rax, off_14003B3A0; "Primary"
0x1400188ed  mov     rcx, [rax+r15*8]
0x1400188f1  lea     r8, [rbp+57h+var_B8]
0x1400188f5  call    VsmmMemReservepCreatePartitionKey
0x1400188fa  mov     ebx, eax
0x1400188fc  test    eax, eax
0x1400188fe  jns     loc_1400189B7
0x140018904  mov     eax, cs:dword_140064110
0x14001890a  cmp     eax, 2
0x14001890d  jbe     loc_140018AFA
0x140018913  mov     rdx, rdi
0x140018916  lea     rcx, dword_140064110
0x14001891d  call    _tlgKeywordOn
0x140018922  test    al, al
0x140018924  jz      loc_140018AFA
0x14001892a  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018931  lea     rcx, [rbp+57h+var_90]
0x140018935  call    _tlgCreate1Sz_char
0x14001893a  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018941  lea     rcx, [rbp+57h+var_80]
0x140018945  call    _tlgCreate1Sz_char
0x14001894a  mov     dword ptr [rbp+57h+var_C0], 1BEEh
0x140018951  lea     rdx, byte_140050ACD
0x140018958  lea     rcx, [rbp+57h+var_C8]
0x14001895c  mov     [rbp+57h+var_68], 4
0x140018964  mov     [rbp+57h+var_60], rcx
0x140018968  lea     rax, [rbp+57h+var_C0]
0x14001896c  lea     rcx, [rbp+57h+var_CC]
0x140018970  mov     [rbp+57h+var_70], rax
0x140018974  lea     rax, [rbp+57h+var_B0]
0x140018978  mov     [rbp+57h+var_50], rcx
0x14001897c  mov     [rsp+100h+var_D8], rax
0x140018981  lea     rcx, dword_140064110
0x140018988  xor     r9d, r9d
0x14001898b  mov     [rbp+57h+var_C8], ebx
0x14001898e  xor     r8d, r8d
0x140018991  mov     [rbp+57h+var_58], 4
0x140018999  mov     [rbp+57h+var_CC], r15d
0x14001899d  mov     [rbp+57h+var_48], 4
0x1400189a5  mov     [rsp+100h+var_E0], 7
0x1400189ad  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400189b2  jmp     loc_140018AFA
0x1400189b7  mov     r9b, [r14+100h]
0x1400189be  xor     dl, dl
0x1400189c0  mov     r12, [rsi+0B0h]
0x1400189c7  test    r9b, r9b
0x1400189ca  jz      short loc_140018A09
0x1400189cc  mov     rax, [rsi+0A8h]
0x1400189d3  movzx   r8d, dl
0x1400189d7  mov     rcx, [rax+r8*8]
0x1400189db  mov     [r12+r8*8], rcx
0x1400189df  mov     rax, [rsi+0B8h]
0x1400189e6  mov     r9, [rax+r8*8]
0x1400189ea  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1400189ee  jz      short loc_1400189F3
0x1400189f0  add     rcx, r9
0x1400189f3  shr     rcx, 8
0x1400189f7  inc     dl
0x1400189f9  mov     [r12+r8*8], rcx
0x1400189fd  mov     r9b, [r14+100h]
0x140018a04  cmp     dl, r9b
0x140018a07  jb      short loc_1400189CC
0x140018a09  mov     rdx, [rbp+57h+var_B8]
0x140018a0d  mov     r8, r12
0x140018a10  mov     rcx, rsi
0x140018a13  call    VsmmMemReservepTargetSet
0x140018a18  mov     ebx, eax
0x140018a1a  test    eax, eax
0x140018a1c  jns     short loc_140018A7A
0x140018a1e  mov     eax, cs:dword_140064110
0x140018a24  cmp     eax, 2
0x140018a27  jbe     loc_140018AF7
0x140018a2d  mov     rdx, rdi
0x140018a30  lea     rcx, dword_140064110
0x140018a37  call    _tlgKeywordOn
0x140018a3c  xor     r12d, r12d
0x140018a3f  test    al, al
0x140018a41  jz      loc_140018AFA
0x140018a47  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018a4e  lea     rcx, [rbp+57h+var_90]
0x140018a52  call    _tlgCreate1Sz_char
0x140018a57  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018a5e  lea     rcx, [rbp+57h+var_80]
0x140018a62  call    _tlgCreate1Sz_char
0x140018a67  mov     dword ptr [rbp+57h+var_C0], 1C13h
0x140018a6e  lea     rdx, byte_14005083D
0x140018a75  jmp     loc_140018958
0x140018a7a  movzx   r8d, byte ptr [r14+100h]
0x140018a82  xor     edx, edx; Val
0x140018a84  shl     r8, 3; Size
0x140018a88  mov     rcx, r12; void *
0x140018a8b  call    memset
0x140018a90  mov     rcx, rsi
0x140018a93  call    VsmmMemReservepPopulate
0x140018a98  xor     r12d, r12d
0x140018a9b  mov     ebx, eax
0x140018a9d  test    eax, eax
0x140018a9f  jns     short loc_140018AF2
0x140018aa1  mov     eax, cs:dword_140064110
0x140018aa7  cmp     eax, 2
0x140018aaa  jbe     short loc_140018AFA
0x140018aac  mov     rdx, rdi
0x140018aaf  lea     rcx, dword_140064110
0x140018ab6  call    _tlgKeywordOn
0x140018abb  test    al, al
0x140018abd  jz      short loc_140018AFA
0x140018abf  lea     rdx, aVsmmmemreserve_11; "VsmmMemReservepMemPartSetupViaCreate"
0x140018ac6  lea     rcx, [rbp+57h+var_90]
0x140018aca  call    _tlgCreate1Sz_char
0x140018acf  lea     rdx, aOnecoreVmVidSy_73; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmemres"...
0x140018ad6  lea     rcx, [rbp+57h+var_80]
0x140018ada  call    _tlgCreate1Sz_char
0x140018adf  mov     dword ptr [rbp+57h+var_C0], 1C2Eh
0x140018ae6  lea     rdx, byte_140050891
0x140018aed  jmp     loc_140018958
0x140018af2  mov     ebx, r12d
0x140018af5  jmp     short loc_140018AFA
0x140018af7  xor     r12d, r12d
  ... truncated ...
```
