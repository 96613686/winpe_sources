# VidResourcePartitionGetComponent

- ea: `0x140092814`
- end: `0x140092f49`
- name: `VidResourcePartitionGetComponent`
- size: `1845`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, int *, unsigned __int64, void *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140092f50`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140021d40`
- `0x140092814`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140092a1e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140092b35`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140092c4c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140092a1e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140092b35`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140092c4c`
- `ntoskrnl!PsJobType` at `0x140092b1f`
- `ntoskrnl!PsJobType` at `0x140092c36`
- `ntoskrnl!PsPartitionType` at `0x140092a08`

## string_xrefs

- `0x14009289b`: `VidResourcePartitionGetComponent`
- `0x14009298b`: `VidResourcePartitionGetComponent`
- `0x140092a5c`: `VidResourcePartitionGetComponent`
- `0x140092b73`: `VidResourcePartitionGetComponent`
- `0x140092c8a`: `VidResourcePartitionGetComponent`
- `0x140092db3`: `VidResourcePartitionGetComponent`
- `0x140092e89`: `VidResourcePartitionGetComponent`

## pseudocode

```c
__int64 __fastcall VidResourcePartitionGetComponent(
        __int64 a1,
        unsigned __int64 a2,
        int *a3,
        unsigned __int64 a4,
        void *a5,
        _DWORD *a6)
{
  unsigned int v8; // ebx
  __int64 v9; // r11
  char *v10; // rdx
  int v11; // r8d
  int *v12; // rax
  __int64 v13; // r10
  __int64 v14; // rcx
  __int64 v15; // rsi
  int v16; // ecx
  int v17; // ecx
  int v18; // r8d
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void **p_Src; // rdx
  int v23; // r8d
  __int64 v24; // r10
  __int64 v25; // r9
  int v26; // r8d
  int ObjectType; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  void *Src; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  char v35[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[16]; // [rsp+A0h] [rbp-60h] BYREF
  int *v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int *v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C8h] [rbp-38h]
  __int64 v42; // [rsp+D0h] [rbp-30h]
  __int64 v43; // [rsp+D8h] [rbp-28h]
  int *v44; // [rsp+E0h] [rbp-20h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  __int64 *v46; // [rsp+F0h] [rbp-10h]
  __int64 v47; // [rsp+F8h] [rbp-8h]
  __int128 *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]

  Src = 0;
  if ( a2 >= 4 )
  {
    v14 = *a3;
    if ( (unsigned int)v14 > 3 )
    {
      v8 = -1073741808;
      if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
        return v8;
      tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
      tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
      LODWORD(v32) = 787;
      v38 = (int *)&v32;
      v10 = byte_140048895;
      v30 = v26;
      v40 = &v30;
      v42 = a1 + 8;
      v29 = *a3;
      v12 = &v29;
LABEL_40:
      v45 = v9;
      goto LABEL_41;
    }
    v15 = 2 * v14;
    if ( a2 < qword_140064200[2 * v14] + 4 || a4 < qword_140064200[2 * v14 + 1] )
    {
      v8 = -1073741820;
      if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
        tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
        LODWORD(v32) = 804;
        v38 = (int *)&v32;
        v10 = byte_140048809;
        v30 = v23;
        v40 = &v30;
        v42 = a1 + 8;
        v29 = *a3;
        v44 = &v29;
        v46 = &v31;
        v48 = &v34;
        ObjectType = 10;
        v45 = v9;
        v31 = v24;
        v47 = 8;
        *(_QWORD *)&v34 = v25;
        v49 = 8;
LABEL_42:
        v41 = v9;
        v39 = v9;
        goto LABEL_43;
      }
      return v8;
    }
    if ( !(_DWORD)v14 )
    {
      p_Src = (void **)(a1 + 60);
      v34 = 0;
      if ( *(_OWORD *)(a1 + 60) )
        goto LABEL_31;
      return (unsigned int)-1073741275;
    }
    v16 = v14 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 != 1 )
        {
          *a6 = 0;
          v8 = -1073741808;
          if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
            return v8;
          tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
          tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
          v29 = 934;
          v38 = &v29;
          v10 = byte_14004869B;
          LODWORD(v31) = v18;
          v40 = (int *)&v31;
          v42 = a1 + 8;
          v30 = *a3;
          v12 = &v30;
          goto LABEL_40;
        }
        v19 = *(void **)(a1 + 96);
        if ( v19 )
        {
          v8 = ObOpenObjectByPointer(v19, 0, 0, a3[1], PsPartitionType, 1, &Src);
          if ( (v8 & 0x80000000) != 0 )
          {
            if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
              return v8;
            tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
            tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
            v30 = 919;
            v38 = &v30;
            v10 = byte_140048615;
            v39 = 4;
            v40 = &v29;
            v42 = a1 + 8;
            LODWORD(v31) = *a3;
            v44 = (int *)&v31;
            LODWORD(v32) = a3[1];
            v46 = &v32;
            ObjectType = 9;
            v29 = v8;
            v41 = 4;
            v45 = 4;
            v47 = 4;
            goto LABEL_43;
          }
          goto LABEL_30;
        }
        return (unsigned int)-1073741275;
      }
      v20 = *(void **)(a1 + 88);
      if ( !v20 )
        return (unsigned int)-1073741275;
      v8 = ObOpenObjectByPointer(v20, 0, 0, a3[1], (POBJECT_TYPE)PsJobType, 1, &Src);
      if ( (v8 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          return v8;
        tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
        tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
        LODWORD(v32) = 884;
        v38 = (int *)&v32;
        v10 = byte_1400486FD;
        v39 = 4;
        v40 = &v30;
        v42 = a1 + 8;
        v29 = *a3;
        v44 = &v29;
        LODWORD(v31) = a3[1];
        v46 = &v31;
        ObjectType = 9;
        v30 = v8;
        v41 = 4;
        v45 = 4;
        v47 = 4;
        goto LABEL_43;
      }
    }
    else
    {
      v21 = *(void **)(a1 + 80);
      if ( !v21 )
        return (unsigned int)-1073741275;
      v8 = ObOpenObjectByPointer(v21, 0, 0, a3[1], (POBJECT_TYPE)PsJobType, 1, &Src);
      if ( (v8 & 0x80000000) != 0 )
      {
        if ( (unsigned int)dword_140064110 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
          return v8;
        tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
        tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
        LODWORD(v32) = 849;
        v38 = (int *)&v32;
        v10 = byte_140048783;
        v39 = 4;
        v40 = &v30;
        v42 = a1 + 8;
        v29 = *a3;
        v44 = &v29;
        LODWORD(v31) = a3[1];
        v46 = &v31;
        ObjectType = 9;
        v30 = v8;
        v41 = 4;
        v45 = 4;
        v47 = 4;
LABEL_43:
        v43 = 16;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, v10, 0, 0, ObjectType, v35);
        return v8;
      }
    }
LABEL_30:
    p_Src = &Src;
LABEL_31:
    memmove(a5, p_Src, qword_140064200[v15 + 1]);
    v8 = 0;
    *a6 = qword_140064200[v15 + 1];
    return v8;
  }
  v8 = -1073741820;
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v36, "VidResourcePartitionGetComponent");
    tlgCreate1Sz_char(v37, "onecore\\vm\\vid\\sys\\driver\\vidresourcepartition.c");
    LODWORD(v31) = 773;
    v38 = (int *)&v31;
    v10 = &byte_1400488F7;
    v29 = v11;
    v40 = &v29;
    v42 = a1 + 8;
    v12 = (int *)&v32;
    v32 = v13;
    v45 = 8;
LABEL_41:
    v44 = v12;
    ObjectType = 8;
    goto LABEL_42;
  }
  return v8;
}

```

## disassembly

```asm
0x140092814  mov     [rsp-8+arg_8], rbx
0x140092819  push    rbp
0x14009281a  push    rsi
0x14009281b  push    rdi
0x14009281c  push    r12
0x14009281e  push    r13
0x140092820  push    r14
0x140092822  push    r15
0x140092824  lea     rbp, [rsp-20h]
0x140092829  sub     rsp, 120h
0x140092830  mov     rax, cs:__security_cookie
0x140092837  xor     rax, rsp
0x14009283a  mov     [rbp+50h+var_40], rax
0x14009283e  mov     r12, [rbp+50h+arg_20]
0x140092845  xor     r13d, r13d
0x140092848  mov     r15, [rbp+50h+arg_28]
0x14009284f  mov     r14, r8
0x140092852  mov     r10, rdx
0x140092855  mov     [rsp+150h+Src], r13
0x14009285a  mov     rdi, rcx
0x14009285d  lea     r11d, [r13+4]
0x140092861  cmp     rdx, r11
0x140092864  jnb     loc_140092900
0x14009286a  mov     eax, cs:dword_140064110
0x140092870  mov     r8d, 0C0000004h
0x140092876  mov     ebx, r8d
0x140092879  cmp     eax, 2
0x14009287c  jbe     loc_140092F1F
0x140092882  mov     edx, 100h
0x140092887  lea     rcx, dword_140064110
0x14009288e  call    _tlgKeywordOn
0x140092893  test    al, al
0x140092895  jz      loc_140092F1F
0x14009289b  lea     rdx, aVidresourcepar_5; "VidResourcePartitionGetComponent"
0x1400928a2  lea     rcx, [rbp+50h+var_C0]
0x1400928a6  call    _tlgCreate1Sz_char
0x1400928ab  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400928b2  lea     rcx, [rbp+50h+var_B0]
0x1400928b6  call    _tlgCreate1Sz_char
0x1400928bb  lea     rax, [rsp+150h+var_108]
0x1400928c0  mov     dword ptr [rsp+150h+var_108], 305h
0x1400928c8  mov     [rbp+50h+var_A0], rax
0x1400928cc  lea     rdx, byte_1400488F7
0x1400928d3  lea     rax, [rsp+150h+var_110]
0x1400928d8  mov     [rsp+150h+var_110], r8d
0x1400928dd  mov     [rbp+50h+var_90], rax
0x1400928e1  lea     rax, [rdi+8]
0x1400928e5  mov     [rbp+50h+var_80], rax
0x1400928e9  lea     rax, [rsp+150h+var_100]
0x1400928ee  mov     [rsp+150h+var_100], r10
0x1400928f3  mov     [rbp+50h+var_68], 8
0x1400928fb  jmp     loc_140092EE7
0x140092900  movsxd  rcx, dword ptr [r8]
0x140092903  cmp     ecx, 3
0x140092906  ja      loc_140092E58
0x14009290c  mov     rsi, rcx
0x14009290f  lea     rdx, qword_140064200
0x140092916  add     rsi, rsi
0x140092919  mov     rax, [rdx+rsi*8]
0x14009291d  add     rax, r11
0x140092920  cmp     r10, rax
0x140092923  jb      loc_140092D82
0x140092929  cmp     r9, [rdx+rsi*8+8]
0x14009292e  jb      loc_140092D82
0x140092934  test    ecx, ecx
0x140092936  jz      loc_140092D57
0x14009293c  sub     ecx, 1
0x14009293f  jz      loc_140092C18
0x140092945  sub     ecx, 1
0x140092948  jz      loc_140092B01
0x14009294e  cmp     ecx, 1
0x140092951  jz      loc_1400929EA
0x140092957  mov     [r15], r13d
0x14009295a  mov     r8d, 0C0000010h
0x140092960  mov     eax, cs:dword_140064110
0x140092966  mov     ebx, r8d
0x140092969  cmp     eax, 2
0x14009296c  jbe     loc_140092F1F
0x140092972  mov     edx, 100h
0x140092977  lea     rcx, dword_140064110
0x14009297e  call    _tlgKeywordOn
0x140092983  test    al, al
0x140092985  jz      loc_140092F1F
0x14009298b  lea     rdx, aVidresourcepar_5; "VidResourcePartitionGetComponent"
0x140092992  lea     rcx, [rbp+50h+var_C0]
0x140092996  call    _tlgCreate1Sz_char
0x14009299b  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x1400929a2  lea     rcx, [rbp+50h+var_B0]
0x1400929a6  call    _tlgCreate1Sz_char
0x1400929ab  lea     rax, [rsp+150h+var_110]
0x1400929b0  mov     [rsp+150h+var_110], 3A6h
0x1400929b8  mov     [rbp+50h+var_A0], rax
0x1400929bc  lea     rdx, byte_14004869B
0x1400929c3  lea     rax, [rsp+150h+var_108]
0x1400929c8  mov     dword ptr [rsp+150h+var_108], r8d
0x1400929cd  mov     [rbp+50h+var_90], rax
0x1400929d1  lea     rax, [rdi+8]
0x1400929d5  mov     [rbp+50h+var_80], rax
0x1400929d9  mov     eax, [r14]
0x1400929dc  mov     [rsp+150h+var_10C], eax
0x1400929e0  lea     rax, [rsp+150h+var_10C]
0x1400929e5  jmp     loc_140092EE3
0x1400929ea  mov     rcx, [rdi+60h]; Object
0x1400929ee  test    rcx, rcx
0x1400929f1  jz      loc_140092D78
0x1400929f7  mov     r9d, [r8+4]; DesiredAccess
0x1400929fb  lea     rax, [rsp+150h+Src]
0x140092a00  mov     [rsp+150h+Handle], rax; Handle
0x140092a05  xor     r8d, r8d; PassedAccessState
0x140092a08  mov     rax, cs:__imp_PsPartitionType
0x140092a0f  mov     [rsp+150h+AccessMode], 1; AccessMode
0x140092a14  mov     rdx, [rax]
0x140092a17  mov     [rsp+150h+ObjectType], rdx; ObjectType
0x140092a1c  xor     edx, edx; HandleAttributes
0x140092a1e  call    cs:__imp_ObOpenObjectByPointer
0x140092a25  nop     dword ptr [rax+rax+00h]
0x140092a2a  mov     ebx, eax
0x140092a2c  test    eax, eax
0x140092a2e  jns     loc_140092D2F
0x140092a34  mov     ecx, cs:dword_140064110
0x140092a3a  cmp     ecx, 2
0x140092a3d  jbe     loc_140092F1F
0x140092a43  mov     edx, 100h
0x140092a48  lea     rcx, dword_140064110
0x140092a4f  call    _tlgKeywordOn
0x140092a54  test    al, al
0x140092a56  jz      loc_140092F1F
0x140092a5c  lea     rdx, aVidresourcepar_5; "VidResourcePartitionGetComponent"
0x140092a63  lea     rcx, [rbp+50h+var_C0]
0x140092a67  call    _tlgCreate1Sz_char
0x140092a6c  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092a73  lea     rcx, [rbp+50h+var_B0]
0x140092a77  call    _tlgCreate1Sz_char
0x140092a7c  lea     rax, [rsp+150h+var_10C]
0x140092a81  mov     [rsp+150h+var_10C], 397h
0x140092a89  mov     [rbp+50h+var_A0], rax
0x140092a8d  lea     rdx, byte_140048615
0x140092a94  lea     rax, [rsp+150h+var_110]
0x140092a99  mov     [rbp+50h+var_98], 4
0x140092aa1  mov     [rbp+50h+var_90], rax
0x140092aa5  lea     rax, [rdi+8]
0x140092aa9  mov     [rbp+50h+var_80], rax
0x140092aad  mov     eax, [r14]
0x140092ab0  mov     dword ptr [rsp+150h+var_108], eax
0x140092ab4  lea     rax, [rsp+150h+var_108]
0x140092ab9  mov     [rbp+50h+var_70], rax
0x140092abd  mov     eax, [r14+4]
0x140092ac1  mov     dword ptr [rsp+150h+var_100], eax
0x140092ac5  lea     rax, [rsp+150h+var_100]
0x140092aca  mov     [rbp+50h+var_60], rax
0x140092ace  lea     rax, [rsp+150h+var_E0]
0x140092ad3  mov     qword ptr [rsp+150h+AccessMode], rax
0x140092ad8  mov     dword ptr [rsp+150h+ObjectType], 9
0x140092ae0  mov     [rsp+150h+var_110], ebx
0x140092ae4  mov     [rbp+50h+var_88], 4
0x140092aec  mov     [rbp+50h+var_68], 4
0x140092af4  mov     [rbp+50h+var_58], 4
0x140092afc  jmp     loc_140092F05
0x140092b01  mov     rcx, [rdi+58h]; Object
0x140092b05  test    rcx, rcx
0x140092b08  jz      loc_140092D78
0x140092b0e  mov     r9d, [r8+4]; DesiredAccess
0x140092b12  lea     rax, [rsp+150h+Src]
0x140092b17  mov     [rsp+150h+Handle], rax; Handle
0x140092b1c  xor     r8d, r8d; PassedAccessState
0x140092b1f  mov     rax, cs:PsJobType
0x140092b26  mov     [rsp+150h+AccessMode], 1; AccessMode
0x140092b2b  mov     rdx, [rax]
0x140092b2e  mov     [rsp+150h+ObjectType], rdx; ObjectType
0x140092b33  xor     edx, edx; HandleAttributes
0x140092b35  call    cs:__imp_ObOpenObjectByPointer
0x140092b3c  nop     dword ptr [rax+rax+00h]
0x140092b41  mov     ebx, eax
0x140092b43  test    eax, eax
0x140092b45  jns     loc_140092D2F
0x140092b4b  mov     eax, cs:dword_140064110
0x140092b51  cmp     eax, 2
0x140092b54  jbe     loc_140092F1F
0x140092b5a  mov     edx, 100h
0x140092b5f  lea     rcx, dword_140064110
0x140092b66  call    _tlgKeywordOn
0x140092b6b  test    al, al
0x140092b6d  jz      loc_140092F1F
0x140092b73  lea     rdx, aVidresourcepar_5; "VidResourcePartitionGetComponent"
0x140092b7a  lea     rcx, [rbp+50h+var_C0]
0x140092b7e  call    _tlgCreate1Sz_char
0x140092b83  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092b8a  lea     rcx, [rbp+50h+var_B0]
0x140092b8e  call    _tlgCreate1Sz_char
0x140092b93  lea     rax, [rsp+150h+var_100]
0x140092b98  mov     dword ptr [rsp+150h+var_100], 374h
0x140092ba0  mov     [rbp+50h+var_A0], rax
0x140092ba4  lea     rdx, byte_1400486FD
0x140092bab  lea     rax, [rsp+150h+var_10C]
0x140092bb0  mov     [rbp+50h+var_98], 4
0x140092bb8  mov     [rbp+50h+var_90], rax
0x140092bbc  lea     rax, [rdi+8]
0x140092bc0  mov     [rbp+50h+var_80], rax
0x140092bc4  mov     eax, [r14]
0x140092bc7  mov     [rsp+150h+var_110], eax
0x140092bcb  lea     rax, [rsp+150h+var_110]
0x140092bd0  mov     [rbp+50h+var_70], rax
0x140092bd4  mov     eax, [r14+4]
0x140092bd8  mov     dword ptr [rsp+150h+var_108], eax
0x140092bdc  lea     rax, [rsp+150h+var_108]
0x140092be1  mov     [rbp+50h+var_60], rax
0x140092be5  lea     rax, [rsp+150h+var_E0]
0x140092bea  mov     qword ptr [rsp+150h+AccessMode], rax
0x140092bef  mov     dword ptr [rsp+150h+ObjectType], 9
0x140092bf7  mov     [rsp+150h+var_10C], ebx
0x140092bfb  mov     [rbp+50h+var_88], 4
0x140092c03  mov     [rbp+50h+var_68], 4
0x140092c0b  mov     [rbp+50h+var_58], 4
0x140092c13  jmp     loc_140092F05
0x140092c18  mov     rcx, [rdi+50h]; Object
0x140092c1c  test    rcx, rcx
0x140092c1f  jz      loc_140092D78
0x140092c25  mov     r9d, [r8+4]; DesiredAccess
0x140092c29  lea     rax, [rsp+150h+Src]
0x140092c2e  mov     [rsp+150h+Handle], rax; Handle
0x140092c33  xor     r8d, r8d; PassedAccessState
0x140092c36  mov     rax, cs:PsJobType
0x140092c3d  mov     [rsp+150h+AccessMode], 1; AccessMode
0x140092c42  mov     rdx, [rax]
0x140092c45  mov     [rsp+150h+ObjectType], rdx; ObjectType
0x140092c4a  xor     edx, edx; HandleAttributes
0x140092c4c  call    cs:__imp_ObOpenObjectByPointer
0x140092c53  nop     dword ptr [rax+rax+00h]
0x140092c58  mov     ebx, eax
0x140092c5a  test    eax, eax
0x140092c5c  jns     loc_140092D2F
0x140092c62  mov     eax, cs:dword_140064110
0x140092c68  cmp     eax, 2
0x140092c6b  jbe     loc_140092F1F
0x140092c71  mov     edx, 100h
0x140092c76  lea     rcx, dword_140064110
0x140092c7d  call    _tlgKeywordOn
0x140092c82  test    al, al
0x140092c84  jz      loc_140092F1F
0x140092c8a  lea     rdx, aVidresourcepar_5; "VidResourcePartitionGetComponent"
0x140092c91  lea     rcx, [rbp+50h+var_C0]
0x140092c95  call    _tlgCreate1Sz_char
0x140092c9a  lea     rdx, aOnecoreVmVidSy_54; "onecore\\vm\\vid\\sys\\driver\\vidresou"...
0x140092ca1  lea     rcx, [rbp+50h+var_B0]
0x140092ca5  call    _tlgCreate1Sz_char
0x140092caa  lea     rax, [rsp+150h+var_100]
0x140092caf  mov     dword ptr [rsp+150h+var_100], 351h
0x140092cb7  mov     [rbp+50h+var_A0], rax
0x140092cbb  lea     rdx, byte_140048783
0x140092cc2  lea     rax, [rsp+150h+var_10C]
0x140092cc7  mov     [rbp+50h+var_98], 4
0x140092ccf  mov     [rbp+50h+var_90], rax
0x140092cd3  lea     rax, [rdi+8]
0x140092cd7  mov     [rbp+50h+var_80], rax
0x140092cdb  mov     eax, [r14]
0x140092cde  mov     [rsp+150h+var_110], eax
0x140092ce2  lea     rax, [rsp+150h+var_110]
0x140092ce7  mov     [rbp+50h+var_70], rax
0x140092ceb  mov     eax, [r14+4]
0x140092cef  mov     dword ptr [rsp+150h+var_108], eax
0x140092cf3  lea     rax, [rsp+150h+var_108]
0x140092cf8  mov     [rbp+50h+var_60], rax
0x140092cfc  lea     rax, [rsp+150h+var_E0]
0x140092d01  mov     qword ptr [rsp+150h+AccessMode], rax
0x140092d06  mov     dword ptr [rsp+150h+ObjectType], 9
0x140092d0e  mov     [rsp+150h+var_10C], ebx
0x140092d12  mov     [rbp+50h+var_88], 4
0x140092d1a  mov     [rbp+50h+var_68], 4
0x140092d22  mov     [rbp+50h+var_58], 4
0x140092d2a  jmp     loc_140092F05
0x140092d2f  lea     rdx, [rsp+150h+Src]; Src
0x140092d34  lea     rbx, qword_140064200
0x140092d3b  mov     rcx, r12; void *
0x140092d3e  mov     r8, [rbx+rsi*8+8]; Size
0x140092d43  call    memmove
0x140092d48  mov     eax, [rbx+rsi*8+8]
0x140092d4c  mov     ebx, r13d
0x140092d4f  mov     [r15], eax
0x140092d52  jmp     loc_140092F1F
0x140092d57  xorps   xmm0, xmm0
0x140092d5a  lea     rdx, [rdi+3Ch]
0x140092d5e  movq    rax, xmm0
0x140092d63  movups  [rsp+150h+var_F0], xmm0
0x140092d68  cmp     [rdx], rax
0x140092d6b  jnz     short loc_140092D34
0x140092d6d  mov     rax, [rdx+8]
0x140092d71  cmp     rax, qword ptr [rsp+150h+var_F0+8]
0x140092d76  jnz     short loc_140092D34
0x140092d78  mov     ebx, 0C0000225h
0x140092d7d  jmp     loc_140092F1F
0x140092d82  mov     eax, cs:dword_140064110
0x140092d88  mov     r8d, 0C0000004h
0x140092d8e  mov     ebx, r8d
0x140092d91  cmp     eax, 2
0x140092d94  jbe     loc_140092F1F
0x140092d9a  mov     edx, 100h
0x140092d9f  lea     rcx, dword_140064110
0x140092da6  call    _tlgKeywordOn
0x140092dab  test    al, al
0x140092dad  jz      loc_140092F1F
  ... truncated ...
```
