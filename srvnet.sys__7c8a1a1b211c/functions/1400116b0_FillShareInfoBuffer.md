# FillShareInfoBuffer

- ea: `0x1400116b0`
- end: `0x140011b97`
- name: `FillShareInfoBuffer`
- size: `1255`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c4d4`

## callees

- `0x1400116b0`
- `0x14002561c`
- `0x14002a3e0`
- `0x14002a410`
- `0x14004196c`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14001187e`
- `ntoskrnl!ExGetPreviousMode` at `0x14001196f`
- `ntoskrnl!ExGetPreviousMode` at `0x140011abb`
- `ntoskrnl!ExGetPreviousMode` at `0x140011b19`
- `ntoskrnl!ExGetPreviousMode` at `0x140011b3f`
- `ntoskrnl!ExGetPreviousMode` at `0x14001187e`
- `ntoskrnl!ExGetPreviousMode` at `0x14001196f`
- `ntoskrnl!ExGetPreviousMode` at `0x140011abb`
- `ntoskrnl!ExGetPreviousMode` at `0x140011b19`
- `ntoskrnl!ExGetPreviousMode` at `0x140011b3f`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001183c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001192f`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001183c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14001192f`

## pseudocode

```c
__int64 __fastcall FillShareInfoBuffer(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  __int64 result; // rax
  __int64 v8; // r13
  unsigned int v9; // ecx
  bool v10; // r8
  bool v11; // si
  char *v12; // rdi
  unsigned int v13; // eax
  void **v14; // r12
  unsigned int v15; // eax
  unsigned int v16; // eax
  void *v17; // rcx
  ULONG v18; // eax
  unsigned int v19; // r8d
  ULONG v20; // r12d
  int v21; // edx
  ULONG v22; // r8d
  KPROCESSOR_MODE PreviousMode; // al
  void *v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  int v27; // ecx
  void *v28; // rcx
  ULONG v29; // eax
  ULONG v30; // r13d
  int v31; // edx
  ULONG v32; // r8d
  void *v33; // r12
  KPROCESSOR_MODE v34; // al
  void *v35; // rdx
  bool v36; // zf
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v39; // ecx
  int v40; // edx
  int v41; // eax
  KPROCESSOR_MODE v42; // al
  void *v43; // rcx
  KPROCESSOR_MODE v44; // al
  void *v46[2]; // [rsp+28h] [rbp-81h] BYREF
  size_t Size; // [rsp+38h] [rbp-71h]
  __int128 Src; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v49[4]; // [rsp+50h] [rbp-59h] BYREF
  __int128 v50; // [rsp+90h] [rbp-19h]
  _OWORD v51[2]; // [rsp+A0h] [rbp-9h] BYREF

  result = *(unsigned int *)(a1 + 64);
  v8 = a1;
  if ( (_DWORD)result )
  {
    switch ( (_DWORD)result )
    {
      case 1:
        v9 = 24;
        break;
      case 2:
        v9 = 56;
        break;
      case 0x1F5:
        v9 = 32;
        break;
      case 0x1F6:
        v9 = 72;
        break;
      case 0x1F7:
        v9 = 80;
        break;
      default:
        v9 = 4;
        if ( (_DWORD)result == 505 )
          v9 = 120;
        break;
    }
  }
  else
  {
    v9 = 8;
  }
  v10 = 0;
  Src = 0;
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  memset(v51, 0, 24);
  *(_OWORD *)v46 = 0;
  if ( (_DWORD)result == 505 )
  {
    v11 = (*(_DWORD *)(v8 + 72) & 0x80u) == 0;
    result = 1;
    v10 = (*(_DWORD *)(v8 + 72) & 0x100) != 0;
  }
  else
  {
    v11 = 1;
  }
  if ( v9 > *a4 )
    return result;
  v12 = (char *)*a3;
  Size = v9;
  *a3 = &v12[v9];
  *a4 -= v9;
  v13 = *(_DWORD *)(v8 + 64);
  v14 = 0;
  if ( v13 <= 0x1F6 )
  {
    if ( v13 != 502 )
    {
      if ( !v13 )
      {
LABEL_65:
        SvcCopyUnicodeStringToBuffer1(a2 + 8, *a3, a4, &Src);
        goto LABEL_66;
      }
      v15 = v13 - 1;
      if ( !v15 )
      {
LABEL_59:
        v39 = *(_DWORD *)(a2 + 124);
        v40 = (unsigned __int8)v39;
        if ( (unsigned __int8)v39 == 104 || (unsigned __int8)v39 == 105 )
          v40 = 0;
        v41 = *(_DWORD *)(v8 + 72);
        DWORD2(Src) = v40 | v39 & 0xC0000000;
        if ( (v41 & 0x40) != 0 )
          DWORD2(Src) = v40 | v39 & 0xC0000000 | v39 & 0x3FFFFF00;
        SvcCopyUnicodeStringToBuffer1(a2 + 88, *a3, a4, v49);
        goto LABEL_65;
      }
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 != 499 )
          goto LABEL_66;
        goto LABEL_57;
      }
LABEL_51:
      if ( v11 )
      {
        if ( *(_DWORD *)(v8 + 64) != 505 )
          DWORD2(v49[0]) = 0;
        v36 = (*(_DWORD *)(a2 + 124) & 0x100000) == 0;
        v37 = a2 + 200;
        v38 = *a3;
        HIDWORD(v49[0]) = *(_DWORD *)(a2 + 104);
        LODWORD(v49[1]) = *(_DWORD *)(a2 + 108);
        if ( v36 )
          v37 = a2 + 72;
        SvcCopyUnicodeStringToBuffer1(v37, v38, a4, (char *)&v49[1] + 8);
        *(_QWORD *)&v49[2] = 0;
      }
LABEL_57:
      if ( *(_DWORD *)(v8 + 64) == 501 )
        DWORD2(v49[0]) = *(_DWORD *)(a2 + 128) | *(_DWORD *)(a2 + 132);
      goto LABEL_59;
    }
    if ( v11 )
    {
LABEL_28:
      v17 = *(void **)(a2 + 192);
      v14 = v46;
      if ( v17 )
      {
        v18 = RtlLengthSecurityDescriptor(v17);
        v19 = *a4;
        v20 = v18;
        v21 = (*(_DWORD *)a3 + *a4 - v18) & 3;
        if ( *a4 > v21 + v18 )
        {
          LODWORD(v46[0]) = v18;
          v22 = v19 - v21 - v18;
          *a4 = v22;
          v46[1] = (void *)(*a3 + v22);
          PreviousMode = ExGetPreviousMode();
          v24 = *(void **)(a2 + 192);
          if ( PreviousMode )
            RtlCopyToUser(v46[1], v24, v20);
          else
            RtlCopyVolatileMemory(v46[1], v24, v20);
          v14 = v46;
          goto LABEL_51;
        }
        v14 = v46;
      }
      LODWORD(v46[0]) = 0;
      v46[1] = 0;
      goto LABEL_51;
    }
LABEL_27:
    if ( !v10 )
      goto LABEL_51;
    goto LABEL_28;
  }
  v25 = v13 - 503;
  if ( !v25 )
  {
    if ( !v11 )
      goto LABEL_27;
LABEL_47:
    SvcCopyUnicodeStringToBuffer1(a2 + 24, *a3, a4, (char *)&v49[2] + 8);
    goto LABEL_28;
  }
  v26 = v25 - 2;
  if ( !v26 )
  {
    v27 = *(_DWORD *)(a2 + 128) | *(_DWORD *)(a2 + 132);
    LODWORD(v51[0]) = *(_DWORD *)(a2 + 216);
    DWORD1(v50) = v27;
    *(_OWORD *)((char *)v51 + 4) = *(_OWORD *)(a2 + 220);
    if ( !v11 )
      goto LABEL_27;
    v28 = *(void **)(a2 + 184);
    *((_QWORD *)&v50 + 1) = *(_QWORD *)(a2 + 140);
    if ( v28 )
    {
      v29 = RtlLengthSecurityDescriptor(v28);
      v30 = v29;
      v31 = (*(_DWORD *)a3 + *a4 - v29) & 3;
      if ( *a4 <= v31 + v29 )
      {
        v8 = a1;
        DWORD2(v49[0]) = 0;
      }
      else
      {
        v32 = *a4 - v31 - v29;
        *a4 = v32;
        v33 = (void *)(v32 + *a3);
        DWORD2(v49[0]) = v32 + *(_DWORD *)a3 - (_DWORD)v12;
        v34 = ExGetPreviousMode();
        v35 = *(void **)(a2 + 184);
        if ( v34 )
          RtlCopyToUser(v33, v35, v30);
        else
          RtlCopyVolatileMemory(v33, v35, v30);
        v8 = a1;
      }
    }
    else
    {
      DWORD2(v49[0]) = 0;
    }
    goto LABEL_47;
  }
  if ( v26 == 500 )
    LODWORD(Src) = *(_DWORD *)(a2 + 128) | *(_DWORD *)(a2 + 132);
LABEL_66:
  if ( ExGetPreviousMode() )
    result = RtlCopyToUser(v12, &Src, Size);
  else
    result = (__int64)RtlCopyVolatileMemory(v12, &Src, Size);
  if ( v14 )
  {
    result = *(unsigned int *)(v8 + 64);
    if ( (_DWORD)result == 502 )
    {
      v44 = ExGetPreviousMode();
      v43 = v12 + 56;
      if ( v44 )
        return RtlCopyToUser(v43, v46, 0x10u);
      return (__int64)RtlCopyVolatileMemory(v43, v46, 0x10u);
    }
    if ( (_DWORD)result == 503 || (_DWORD)result == 505 )
    {
      v42 = ExGetPreviousMode();
      v43 = v12 + 64;
      if ( v42 )
        return RtlCopyToUser(v43, v46, 0x10u);
      return (__int64)RtlCopyVolatileMemory(v43, v46, 0x10u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400116b0  push    rbp
0x1400116b2  push    rbx
0x1400116b3  push    r13
0x1400116b5  push    r14
0x1400116b7  push    r15
0x1400116b9  lea     rbp, [rsp-37h]
0x1400116be  sub     rsp, 0E0h
0x1400116c5  mov     rax, cs:__security_cookie
0x1400116cc  xor     rax, rsp
0x1400116cf  mov     [rbp+57h+var_40], rax
0x1400116d3  mov     eax, [rcx+40h]
0x1400116d6  mov     r14, r9
0x1400116d9  mov     [rsp+100h+var_E0], rcx
0x1400116de  mov     r15, r8
0x1400116e1  mov     rbx, rdx
0x1400116e4  mov     r13, rcx
0x1400116e7  test    eax, eax
0x1400116e9  jnz     short loc_1400116F2
0x1400116eb  mov     ecx, 8
0x1400116f0  jmp     short loc_140011746
0x1400116f2  cmp     eax, 1
0x1400116f5  jnz     short loc_1400116FE
0x1400116f7  mov     ecx, 18h
0x1400116fc  jmp     short loc_140011746
0x1400116fe  cmp     eax, 2
0x140011701  jnz     short loc_14001170A
0x140011703  mov     ecx, 38h ; '8'
0x140011708  jmp     short loc_140011746
0x14001170a  cmp     eax, 1F5h
0x14001170f  jnz     short loc_140011718
0x140011711  mov     ecx, 20h ; ' '
0x140011716  jmp     short loc_140011746
0x140011718  cmp     eax, 1F6h
0x14001171d  jnz     short loc_140011726
0x14001171f  mov     ecx, 48h ; 'H'
0x140011724  jmp     short loc_140011746
0x140011726  cmp     eax, 1F7h
0x14001172b  jnz     short loc_140011734
0x14001172d  mov     ecx, 50h ; 'P'
0x140011732  jmp     short loc_140011746
0x140011734  cmp     eax, 1F9h
0x140011739  mov     ecx, 4
0x14001173e  mov     edx, 78h ; 'x'
0x140011743  cmovz   ecx, edx
0x140011746  xorps   xmm0, xmm0
0x140011749  mov     [rsp+100h+arg_0], rsi
0x140011751  xor     edx, edx
0x140011753  xor     r8b, r8b
0x140011756  mov     [rbp+57h+var_50], rdx
0x14001175a  movups  [rbp+57h+Src], xmm0
0x14001175e  movups  [rbp+57h+var_B0], xmm0
0x140011762  movups  [rbp+57h+var_A0], xmm0
0x140011766  movups  [rbp+57h+var_90], xmm0
0x14001176a  movups  [rbp+57h+var_80], xmm0
0x14001176e  movups  [rbp+57h+var_70], xmm0
0x140011772  movups  [rbp+57h+var_60], xmm0
0x140011776  movups  xmmword ptr [rsp+100h+var_D8], xmm0
0x14001177b  cmp     eax, 1F9h
0x140011780  jnz     short loc_1400117A5
0x140011782  mov     eax, [r13+48h]
0x140011786  test    al, 80h
0x140011788  jz      short loc_14001178F
0x14001178a  xor     sil, sil
0x14001178d  jmp     short loc_140011792
0x14001178f  mov     sil, 1
0x140011792  bt      eax, 8
0x140011796  movzx   r8d, r8b
0x14001179a  mov     eax, 1
0x14001179f  cmovb   r8d, eax
0x1400117a3  jmp     short loc_1400117A8
0x1400117a5  mov     sil, 1
0x1400117a8  cmp     ecx, [r9]
0x1400117ab  ja      loc_140011B72
0x1400117b1  mov     [rsp+100h+var_28], rdi
0x1400117b9  xor     r9d, r9d
0x1400117bc  mov     rdi, [r15]
0x1400117bf  mov     eax, ecx
0x1400117c1  mov     [rbp+57h+Size], rax
0x1400117c5  add     rax, rdi
0x1400117c8  mov     [r15], rax
0x1400117cb  sub     [r14], ecx
0x1400117ce  mov     eax, [r13+40h]
0x1400117d2  mov     [rsp+100h+var_30], r12
0x1400117da  mov     r12d, r9d
0x1400117dd  cmp     eax, 1F6h
0x1400117e2  ja      loc_1400118B2
0x1400117e8  jz      short loc_140011814
0x1400117ea  test    eax, eax
0x1400117ec  jz      loc_140011AA8
0x1400117f2  sub     eax, 1
0x1400117f5  jz      loc_140011A5B
0x1400117fb  sub     eax, 1
0x1400117fe  jz      loc_1400119F9
0x140011804  cmp     eax, 1F3h
0x140011809  jz      loc_140011A42
0x14001180f  jmp     loc_140011ABB
0x140011814  test    sil, sil
0x140011817  jnz     short loc_140011822
0x140011819  test    r8b, r8b
0x14001181c  jz      loc_1400119F9
0x140011822  mov     rcx, [rbx+0C0h]; SecurityDescriptor
0x140011829  lea     r12, [rsp+100h+var_D8]
0x14001182e  mov     [rsp+100h+var_E0], r12
0x140011833  test    rcx, rcx
0x140011836  jz      loc_1400119F0
0x14001183c  call    cs:__imp_RtlLengthSecurityDescriptor
0x140011843  nop     dword ptr [rax+rax+00h]
0x140011848  mov     r8d, [r14]
0x14001184b  mov     edx, r8d
0x14001184e  sub     edx, eax
0x140011850  mov     r12d, eax
0x140011853  add     edx, [r15]
0x140011856  and     edx, 3
0x140011859  lea     ecx, [rdx+r12]
0x14001185d  cmp     r8d, ecx
0x140011860  jbe     loc_1400119E8
0x140011866  sub     r8d, edx
0x140011869  mov     dword ptr [rsp+100h+var_D8], r12d
0x14001186e  sub     r8d, r12d
0x140011871  mov     eax, r8d
0x140011874  mov     [r14], eax
0x140011877  add     rax, [r15]
0x14001187a  mov     [rbp+57h+var_D8+8], rax
0x14001187e  call    cs:__imp_ExGetPreviousMode
0x140011885  nop     dword ptr [rax+rax+00h]
0x14001188a  mov     rdx, [rbx+0C0h]; Src
0x140011891  mov     r8d, r12d; Size
0x140011894  mov     rcx, [rbp+57h+var_D8+8]; void *
0x140011898  test    al, al
0x14001189a  jz      loc_1400119D9
0x1400118a0  call    RtlCopyToUser
0x1400118a5  mov     r12, [rsp+100h+var_E0]
0x1400118aa  xor     r9d, r9d
0x1400118ad  jmp     loc_1400119F9
0x1400118b2  sub     eax, 1F7h
0x1400118b7  jz      loc_1400119B5
0x1400118bd  sub     eax, 2
0x1400118c0  jz      short loc_1400118E1
0x1400118c2  cmp     eax, 1F4h
0x1400118c7  jnz     loc_140011ABB
0x1400118cd  mov     ecx, [rbx+84h]
0x1400118d3  or      ecx, [rbx+80h]
0x1400118d9  mov     dword ptr [rbp+57h+Src], ecx
0x1400118dc  jmp     loc_140011ABB
0x1400118e1  mov     ecx, [rbx+84h]
0x1400118e7  or      ecx, [rbx+80h]
0x1400118ed  mov     eax, [rbx+0D8h]
0x1400118f3  mov     dword ptr [rbp+57h+var_60], eax
0x1400118f6  mov     dword ptr [rbp+57h+var_70+4], ecx
0x1400118f9  movups  xmm0, xmmword ptr [rbx+0DCh]
0x140011900  movups  [rbp+57h+var_60+4], xmm0
0x140011904  test    sil, sil
0x140011907  jz      loc_140011819
0x14001190d  mov     eax, [rbx+90h]
0x140011913  mov     rcx, [rbx+0B8h]; SecurityDescriptor
0x14001191a  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x14001191d  mov     eax, [rbx+8Ch]
0x140011923  mov     dword ptr [rbp+57h+var_70+8], eax
0x140011926  test    rcx, rcx
0x140011929  jz      loc_1400119AF
0x14001192f  call    cs:__imp_RtlLengthSecurityDescriptor
0x140011936  nop     dword ptr [rax+rax+00h]
0x14001193b  mov     r8d, [r14]
0x14001193e  mov     edx, r8d
0x140011941  sub     edx, eax
0x140011943  mov     r13d, eax
0x140011946  add     edx, [r15]
0x140011949  and     edx, 3
0x14001194c  lea     ecx, [rdx+r13]
0x140011950  cmp     r8d, ecx
0x140011953  jbe     short loc_1400119A4
0x140011955  sub     r8d, edx
0x140011958  sub     r8d, r13d
0x14001195b  mov     ecx, r8d
0x14001195e  mov     [r14], ecx
0x140011961  mov     r12, [r15]
0x140011964  add     r12, rcx
0x140011967  mov     eax, r12d
0x14001196a  sub     eax, edi
0x14001196c  mov     dword ptr [rbp+57h+var_B0+8], eax
0x14001196f  call    cs:__imp_ExGetPreviousMode
0x140011976  nop     dword ptr [rax+rax+00h]
0x14001197b  mov     rdx, [rbx+0B8h]; Src
0x140011982  mov     r8d, r13d; Size
0x140011985  mov     rcx, r12; void *
0x140011988  test    al, al
0x14001198a  jz      short loc_140011998
0x14001198c  call    RtlCopyToUser
0x140011991  mov     r13, [rsp+100h+var_E0]
0x140011996  jmp     short loc_1400119BE
0x140011998  call    RtlCopyVolatileMemory
0x14001199d  mov     r13, [rsp+100h+var_E0]
0x1400119a2  jmp     short loc_1400119BE
0x1400119a4  mov     r13, [rsp+100h+var_E0]
0x1400119a9  mov     dword ptr [rbp+57h+var_B0+8], r12d
0x1400119ad  jmp     short loc_1400119BE
0x1400119af  mov     dword ptr [rbp+57h+var_B0+8], r9d
0x1400119b3  jmp     short loc_1400119BE
0x1400119b5  test    sil, sil
0x1400119b8  jz      loc_140011819
0x1400119be  mov     rdx, [r15]
0x1400119c1  lea     rcx, [rbx+18h]
0x1400119c5  lea     r9, [rbp+57h+var_90+8]
0x1400119c9  mov     r8, r14
0x1400119cc  call    SvcCopyUnicodeStringToBuffer1
0x1400119d1  xor     r9d, r9d
0x1400119d4  jmp     loc_140011822
0x1400119d9  call    RtlCopyVolatileMemory
0x1400119de  mov     r12, [rsp+100h+var_E0]
0x1400119e3  xor     r9d, r9d
0x1400119e6  jmp     short loc_1400119F9
0x1400119e8  mov     r12, [rsp+100h+var_E0]
0x1400119ed  xor     r9d, r9d
0x1400119f0  mov     dword ptr [rsp+100h+var_D8], r9d
0x1400119f5  mov     [rbp+57h+var_D8+8], r9
0x1400119f9  test    sil, sil
0x1400119fc  jz      short loc_140011A42
0x1400119fe  cmp     dword ptr [r13+40h], 1F9h
0x140011a06  jz      short loc_140011A0C
0x140011a08  mov     dword ptr [rbp+57h+var_B0+8], r9d
0x140011a0c  test    dword ptr [rbx+7Ch], 100000h
0x140011a13  lea     rcx, [rbx+0C8h]
0x140011a1a  mov     eax, [rbx+68h]
0x140011a1d  mov     rdx, [r15]
0x140011a20  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x140011a23  mov     eax, [rbx+6Ch]
0x140011a26  mov     dword ptr [rbp+57h+var_A0], eax
0x140011a29  jnz     short loc_140011A2F
0x140011a2b  lea     rcx, [rbx+48h]
0x140011a2f  lea     r9, [rbp+57h+var_A0+8]
0x140011a33  mov     r8, r14
0x140011a36  call    SvcCopyUnicodeStringToBuffer1
0x140011a3b  xor     r9d, r9d
0x140011a3e  mov     qword ptr [rbp+57h+var_90], r9
0x140011a42  cmp     dword ptr [r13+40h], 1F5h
0x140011a4a  jnz     short loc_140011A5B
0x140011a4c  mov     ecx, [rbx+84h]
0x140011a52  or      ecx, [rbx+80h]
0x140011a58  mov     dword ptr [rbp+57h+var_B0+8], ecx
0x140011a5b  mov     ecx, [rbx+7Ch]
0x140011a5e  movzx   edx, cl
0x140011a61  mov     eax, edx
0x140011a63  sub     eax, 68h ; 'h'
0x140011a66  jz      short loc_140011A6D
0x140011a68  cmp     eax, 1
0x140011a6b  jnz     short loc_140011A70
0x140011a6d  mov     edx, r9d
0x140011a70  mov     eax, [r13+48h]
0x140011a74  mov     r9d, ecx
0x140011a77  and     r9d, 0C0000000h
0x140011a7e  or      r9d, edx
0x140011a81  mov     dword ptr [rbp+57h+Src+8], r9d
0x140011a85  test    al, 40h
0x140011a87  jz      short loc_140011A95
0x140011a89  and     ecx, 3FFFFF00h
0x140011a8f  or      ecx, r9d
0x140011a92  mov     dword ptr [rbp+57h+Src+8], ecx
0x140011a95  mov     rdx, [r15]
0x140011a98  lea     rcx, [rbx+58h]
0x140011a9c  lea     r9, [rbp+57h+var_B0]
0x140011aa0  mov     r8, r14
0x140011aa3  call    SvcCopyUnicodeStringToBuffer1
0x140011aa8  mov     rdx, [r15]
0x140011aab  lea     rcx, [rbx+8]
0x140011aaf  lea     r9, [rbp+57h+Src]
0x140011ab3  mov     r8, r14
0x140011ab6  call    SvcCopyUnicodeStringToBuffer1
0x140011abb  call    cs:__imp_ExGetPreviousMode
0x140011ac2  nop     dword ptr [rax+rax+00h]
0x140011ac7  mov     r8, [rbp+57h+Size]; Size
0x140011acb  lea     rdx, [rbp+57h+Src]; Src
0x140011acf  mov     rcx, rdi; void *
0x140011ad2  test    al, al
0x140011ad4  jz      short loc_140011ADD
0x140011ad6  call    RtlCopyToUser
0x140011adb  jmp     short loc_140011AE2
0x140011add  call    RtlCopyVolatileMemory
0x140011ae2  test    r12, r12
0x140011ae5  mov     r12, [rsp+100h+var_30]
0x140011aed  jz      short loc_140011B6A
0x140011aef  mov     eax, [r13+40h]
0x140011af3  cmp     eax, 1F6h
0x140011af8  jz      short loc_140011B3F
0x140011afa  cmp     eax, 1F7h
0x140011aff  jz      short loc_140011B19
0x140011b01  cmp     eax, 1F9h
0x140011b06  jnz     short loc_140011B6A
0x140011b08  sub     eax, 1F6h
0x140011b0d  jz      short loc_140011B3F
0x140011b0f  sub     eax, 1
0x140011b12  jz      short loc_140011B19
0x140011b14  cmp     eax, 2
0x140011b17  jnz     short loc_140011B6A
0x140011b19  call    cs:__imp_ExGetPreviousMode
0x140011b20  nop     dword ptr [rax+rax+00h]
0x140011b25  mov     r8d, 10h; Size
0x140011b2b  lea     rdx, [rsp+100h+var_D8]; Src
0x140011b30  lea     rcx, [rdi+40h]; void *
0x140011b34  test    al, al
0x140011b36  jz      short loc_140011B65
  ... truncated ...
```
