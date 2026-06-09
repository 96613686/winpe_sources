# sub_18003EADC

- ea: `0x18003eadc`
- end: `0x18003ee4c`
- name: `sub_18003EADC`
- size: `880`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180040740`

## callees

- `0x180004564`
- `0x180004ca0`
- `0x180006c10`
- `0x180007638`
- `0x1800088b4`
- `0x180016cd4`
- `0x18002305c`
- `0x18003eadc`
- `0x18003f950`
- `0x18003ff50`
- `0x18004a43c`
- `0x180053e84`
- `0x180053f0c`
- `0x1800543b8`
- `0x18005457c`
- `0x180054e84`

## string_xrefs

- `0x18003ebfd`: `GenuineAdvantageClientToken`
- `0x18003ec20`: `ActivationToken`

## pseudocode

```c
__int64 __fastcall sub_18003EADC(
        _DWORD *a1,
        _QWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        _DWORD *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        const WCHAR *a12,
        const WCHAR *a13,
        __int64 *a14)
{
  __int64 v16; // r15
  int v17; // r14d
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rcx
  const WCHAR *v21; // rax
  const WCHAR *v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // edi
  __int64 v25; // rsi
  int v26; // eax
  __int64 v27; // rax
  unsigned int v29; // ecx
  signed int v30; // [rsp+38h] [rbp-D0h] BYREF
  int v31; // [rsp+3Ch] [rbp-CCh] BYREF
  int v32; // [rsp+40h] [rbp-C8h] BYREF
  int v33; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v34; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v39[3]; // [rsp+78h] [rbp-90h] BYREF
  int v40; // [rsp+90h] [rbp-78h]
  const wchar_t *v41; // [rsp+98h] [rbp-70h]
  __int64 v42; // [rsp+A0h] [rbp-68h]
  int v43; // [rsp+A8h] [rbp-60h]
  const wchar_t *v44; // [rsp+B0h] [rbp-58h]
  __int64 v45; // [rsp+B8h] [rbp-50h]
  int v46; // [rsp+C0h] [rbp-48h]
  const wchar_t *v47; // [rsp+C8h] [rbp-40h]
  __int64 v48; // [rsp+D0h] [rbp-38h]
  int v49; // [rsp+D8h] [rbp-30h]
  const wchar_t *v50; // [rsp+E0h] [rbp-28h]
  const WCHAR *v51; // [rsp+E8h] [rbp-20h]
  int v52; // [rsp+F0h] [rbp-18h]
  const wchar_t *v53; // [rsp+F8h] [rbp-10h]
  const WCHAR *v54; // [rsp+100h] [rbp-8h]
  _BYTE v55[40]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v56; // [rsp+130h] [rbp+28h]
  unsigned int v57; // [rsp+13Ch] [rbp+34h]
  __int64 v58; // [rsp+158h] [rbp+50h]
  __int64 v59; // [rsp+188h] [rbp+80h]
  __int64 v60; // [rsp+190h] [rbp+88h]

  sub_1800088B4(v55);
  v37 = 0;
  v16 = 0;
  v36 = 0;
  v17 = 0;
  v35 = 0;
  v38 = 0;
  LODWORD(v34) = 0;
  v32 = 0;
  v33 = 0;
  v31 = 0;
  v18 = sub_180053F0C(v55);
  v19 = v18;
  if ( v18 < 0 )
    goto LABEL_2;
  v18 = sub_180053E84(v55, L"SLWGA");
  v19 = v18;
  if ( v18 < 0 )
    goto LABEL_2;
  v18 = sub_18005457C(v55, a8);
  v19 = v18;
  if ( v18 < 0 )
    goto LABEL_2;
  LODWORD(v39[0]) = 0;
  v40 = 0;
  v39[1] = L"GenuineAdvantagePhase";
  v43 = 0;
  v39[2] = L"GenuineAdvantagePhase2";
  v46 = 0;
  v41 = L"GenuineAdvantageBlob";
  v42 = a9;
  v44 = L"GenuineAdvantageSessionData";
  v45 = a10;
  v47 = L"GenuineAdvantageClientTransactionId";
  v48 = a11;
  v50 = L"GenuineAdvantageClientToken";
  v21 = a12;
  v49 = 0;
  v52 = 0;
  if ( !a12 )
    v21 = &LocaleName;
  v51 = v21;
  v53 = L"ActivationToken";
  v22 = a13;
  if ( !a13 )
    v22 = &LocaleName;
  v54 = v22;
  v18 = sub_1800543B8(v55, 6, v39);
  v19 = v18;
  if ( v18 < 0 )
    goto LABEL_2;
  if ( a14 )
  {
    v23 = *a14;
    if ( *a14 )
    {
      v60 = a14[1];
      v59 = v23;
    }
  }
  v18 = sub_180054E84(v55);
  v30 = v18;
  v19 = v18;
  if ( v18 == -2147156991 )
  {
    v18 = sub_180016CD4(v58, &v30, (unsigned int *)&v34);
    v19 = v18;
    if ( v18 >= 0 )
    {
      v19 = v30;
      if ( v30 >= 0 )
        v19 = -1073415165;
      goto LABEL_18;
    }
  }
  else if ( v18 >= 0 )
  {
    v24 = v57;
    v25 = v56;
    if ( !v57 )
    {
      v19 = -2147024883;
LABEL_18:
      v20 = v19;
      goto LABEL_3;
    }
    v18 = sub_18003F950(v56, v57, (unsigned int)L"GenuineAdvantageTicket", (unsigned int)&v37, (__int64)&v32);
    v19 = v18;
    if ( v18 >= 0 )
    {
      if ( v24 > 1 )
      {
        v18 = sub_18003F950(v25, v24, (unsigned int)L"EncryptedClientKey", (unsigned int)&v36, (__int64)&v33);
        v19 = v18;
        if ( v18 < 0 )
          goto LABEL_2;
        v26 = sub_18003FF50(v25, v24, L"EndUserLicense", &v38);
        if ( v26 < 0 )
        {
          if ( v26 != -1073418222 )
          {
            sub_180004CA0((unsigned int)v26);
            v19 = v29;
            goto LABEL_29;
          }
        }
        else
        {
          v18 = sub_18002305C((unsigned int)v26, v38, &v35, &v31);
          v19 = v18;
          if ( v18 < 0 )
            goto LABEL_2;
          v16 = v35;
          v17 = v31;
        }
      }
      v27 = v37;
      v37 = 0;
      v35 = 0;
      *a2 = v27;
      *a3 = v32;
      *a4 = v36;
      *a5 = v33;
      v36 = 0;
      *a6 = v16;
      *a7 = v17;
      goto LABEL_29;
    }
  }
LABEL_2:
  v20 = (unsigned int)v18;
LABEL_3:
  sub_180004CA0(v20);
LABEL_29:
  *a1 = v34;
  sub_180006C10(v19);
  sub_180004564(&v38);
  sub_180007638(&v35);
  sub_180007638(&v36);
  sub_180007638(&v37);
  sub_18004A43C(v55);
  return v19;
}

```

## disassembly

```asm
0x18003eadc  mov     rax, rsp
0x18003eadf  mov     [rax+18h], rbx
0x18003eae3  mov     [rax+10h], rdx
0x18003eae7  mov     [rax+8], rcx
0x18003eaeb  push    rbp
0x18003eaec  push    rsi
0x18003eaed  push    rdi
0x18003eaee  push    r12
0x18003eaf0  push    r13
0x18003eaf2  push    r14
0x18003eaf4  push    r15
0x18003eaf6  lea     rbp, [rax-0C8h]
0x18003eafd  sub     rsp, 190h
0x18003eb04  lea     rcx, [rbp+0C0h+var_C0]
0x18003eb08  mov     r12, r9
0x18003eb0b  mov     r13, r8
0x18003eb0e  call    sub_1800088B4
0x18003eb13  xor     edi, edi
0x18003eb15  lea     rcx, [rbp+0C0h+var_C0]
0x18003eb19  mov     [rsp+1C0h+var_168], rdi
0x18003eb1e  mov     r15d, edi
0x18003eb21  mov     [rsp+1C0h+var_170], rdi
0x18003eb26  mov     r14d, edi
0x18003eb29  mov     [rsp+1C0h+var_178], rdi
0x18003eb2e  mov     [rsp+1C0h+var_160], rdi
0x18003eb33  mov     dword ptr [rsp+1C0h+var_180], edi
0x18003eb37  mov     [rsp+1C0h+var_188], edi
0x18003eb3b  mov     [rsp+1C0h+var_184], edi
0x18003eb3f  mov     [rsp+1C0h+var_18C], edi
0x18003eb43  call    sub_180053F0C
0x18003eb48  mov     ebx, eax
0x18003eb4a  test    eax, eax
0x18003eb4c  jns     short loc_18003EB5A
0x18003eb4e  mov     ecx, eax
0x18003eb50  call    sub_180004CA0
0x18003eb55  jmp     loc_18003EDD5
0x18003eb5a  lea     rdx, aSlwga; "SLWGA"
0x18003eb61  lea     rcx, [rbp+0C0h+var_C0]
0x18003eb65  call    sub_180053E84
0x18003eb6a  mov     ebx, eax
0x18003eb6c  test    eax, eax
0x18003eb6e  js      short loc_18003EB4E
0x18003eb70  mov     rdx, [rbp+0C0h+arg_38]
0x18003eb77  lea     rcx, [rbp+0C0h+var_C0]
0x18003eb7b  call    sub_18005457C
0x18003eb80  mov     ebx, eax
0x18003eb82  test    eax, eax
0x18003eb84  js      short loc_18003EB4E
0x18003eb86  lea     rcx, LocaleName
0x18003eb8d  mov     dword ptr [rsp+1C0h+var_150], edi
0x18003eb91  lea     rax, aGenuineadvanta; "GenuineAdvantagePhase"
0x18003eb98  mov     [rbp+0C0h+var_138], edi
0x18003eb9b  mov     [rsp+78h], rax
0x18003eba0  lea     r8, [rsp+1C0h+var_150]
0x18003eba5  lea     rax, aGenuineadvanta_7; "GenuineAdvantagePhase2"
0x18003ebac  mov     [rbp+0C0h+var_120], edi
0x18003ebaf  mov     [rbp+0C0h+var_140], rax
0x18003ebb3  mov     edx, 6
0x18003ebb8  lea     rax, aGenuineadvanta_8; "GenuineAdvantageBlob"
0x18003ebbf  mov     [rbp+0C0h+var_108], edi
0x18003ebc2  mov     [rbp+0C0h+var_130], rax
0x18003ebc6  mov     rax, [rbp+0C0h+arg_40]
0x18003ebcd  mov     [rbp+0C0h+var_128], rax
0x18003ebd1  lea     rax, aGenuineadvanta_9; "GenuineAdvantageSessionData"
0x18003ebd8  mov     [rbp+0C0h+var_118], rax
0x18003ebdc  mov     rax, [rbp+0C0h+arg_48]
0x18003ebe3  mov     [rbp+0C0h+var_110], rax
0x18003ebe7  lea     rax, aGenuineadvanta_3; "GenuineAdvantageClientTransactionId"
0x18003ebee  mov     [rbp+0C0h+var_100], rax
0x18003ebf2  mov     rax, [rbp+0C0h+arg_50]
0x18003ebf9  mov     [rbp+0C0h+var_F8], rax
0x18003ebfd  lea     rax, aGenuineadvanta_4; "GenuineAdvantageClientToken"
0x18003ec04  mov     [rbp+0C0h+var_E8], rax
0x18003ec08  mov     rax, [rbp+0C0h+arg_58]
0x18003ec0f  test    rax, rax
0x18003ec12  mov     [rbp+0C0h+var_F0], edi
0x18003ec15  mov     [rbp+0C0h+var_D8], edi
0x18003ec18  cmovz   rax, rcx
0x18003ec1c  mov     [rbp+0C0h+var_E0], rax
0x18003ec20  lea     rax, aActivationtoke; "ActivationToken"
0x18003ec27  mov     [rbp+0C0h+var_D0], rax
0x18003ec2b  mov     rax, [rbp+0C0h+arg_60]
0x18003ec32  test    rax, rax
0x18003ec35  cmovz   rax, rcx
0x18003ec39  lea     rcx, [rbp+0C0h+var_C0]
0x18003ec3d  mov     [rbp+0C0h+var_C8], rax
0x18003ec41  call    sub_1800543B8
0x18003ec46  mov     ebx, eax
0x18003ec48  test    eax, eax
0x18003ec4a  js      loc_18003EB4E
0x18003ec50  mov     rax, [rbp+0C0h+arg_68]
0x18003ec57  test    rax, rax
0x18003ec5a  jz      short loc_18003EC76
0x18003ec5c  mov     rcx, [rax]
0x18003ec5f  test    rcx, rcx
0x18003ec62  jz      short loc_18003EC76
0x18003ec64  mov     rax, [rax+8]
0x18003ec68  mov     [rbp+0C0h+var_38], rax
0x18003ec6f  mov     [rbp+0C0h+var_40], rcx
0x18003ec76  lea     rcx, [rbp+0C0h+var_C0]
0x18003ec7a  call    sub_180054E84
0x18003ec7f  mov     [rsp+1C0h+var_190], eax
0x18003ec83  mov     ebx, eax
0x18003ec85  cmp     eax, 8004FC01h
0x18003ec8a  jnz     short loc_18003ECBD
0x18003ec8c  mov     rcx, [rbp+0C0h+var_70]
0x18003ec90  lea     r8, [rsp+1C0h+var_180]
0x18003ec95  lea     rdx, [rsp+1C0h+var_190]
0x18003ec9a  call    sub_180016CD4
0x18003ec9f  mov     ebx, eax
0x18003eca1  test    eax, eax
0x18003eca3  js      loc_18003EB4E
0x18003eca9  mov     ebx, [rsp+1C0h+var_190]
0x18003ecad  test    ebx, ebx
0x18003ecaf  js      short loc_18003ECB6
0x18003ecb1  mov     ebx, 0C004FC03h
0x18003ecb6  mov     ecx, ebx
0x18003ecb8  jmp     loc_18003EB50
0x18003ecbd  test    eax, eax
0x18003ecbf  js      loc_18003EB4E
0x18003ecc5  mov     edi, [rbp+0C0h+var_8C]
0x18003ecc8  mov     rsi, [rbp+0C0h+var_98]
0x18003eccc  cmp     edi, 1
0x18003eccf  jnb     short loc_18003ECD8
0x18003ecd1  mov     ebx, 8007000Dh
0x18003ecd6  jmp     short loc_18003ECB6
0x18003ecd8  lea     rax, [rsp+1C0h+var_188]
0x18003ecdd  mov     edx, edi
0x18003ecdf  lea     r9, [rsp+1C0h+var_168]
0x18003ece4  mov     [rsp+20h], rax
0x18003ece9  lea     r8, aGenuineadvanta_10; "GenuineAdvantageTicket"
0x18003ecf0  mov     rcx, rsi
0x18003ecf3  call    sub_18003F950
0x18003ecf8  mov     ebx, eax
0x18003ecfa  test    eax, eax
0x18003ecfc  js      loc_18003EB4E
0x18003ed02  cmp     edi, 1
0x18003ed05  jbe     short loc_18003ED79
0x18003ed07  lea     rax, [rsp+1C0h+var_184]
0x18003ed0c  mov     edx, edi
0x18003ed0e  lea     r9, [rsp+1C0h+var_170]
0x18003ed13  mov     [rsp+20h], rax
0x18003ed18  lea     r8, aEncryptedclien; "EncryptedClientKey"
0x18003ed1f  mov     rcx, rsi
0x18003ed22  call    sub_18003F950
0x18003ed27  mov     ebx, eax
0x18003ed29  test    eax, eax
0x18003ed2b  js      loc_18003EB4E
0x18003ed31  lea     r9, [rsp+1C0h+var_160]
0x18003ed36  mov     edx, edi
0x18003ed38  lea     r8, aEnduserlicense; "EndUserLicense"
0x18003ed3f  mov     rcx, rsi
0x18003ed42  call    sub_18003FF50
0x18003ed47  mov     ecx, eax
0x18003ed49  test    eax, eax
0x18003ed4b  js      loc_18003EE37
0x18003ed51  mov     rdx, [rsp+1C0h+var_160]
0x18003ed56  lea     r9, [rsp+1C0h+var_18C]
0x18003ed5b  lea     r8, [rsp+1C0h+var_178]
0x18003ed60  call    sub_18002305C
0x18003ed65  mov     ebx, eax
0x18003ed67  test    eax, eax
0x18003ed69  js      loc_18003EB4E
0x18003ed6f  mov     r15, [rsp+1C0h+var_178]
0x18003ed74  mov     r14d, [rsp+1C0h+var_18C]
0x18003ed79  mov     rax, [rsp+1C0h+var_168]
0x18003ed7e  mov     rcx, [rbp+0C0h+arg_8]
0x18003ed85  mov     [rsp+1C0h+var_168], 0
0x18003ed8e  mov     [rsp+1C0h+var_178], 0
0x18003ed97  mov     [rcx], rax
0x18003ed9a  mov     eax, [rsp+1C0h+var_188]
0x18003ed9e  mov     rcx, [rbp+0C0h+arg_20]
0x18003eda5  mov     [r13+0], eax
0x18003eda9  mov     rax, [rsp+1C0h+var_170]
0x18003edae  mov     [r12], rax
0x18003edb2  mov     eax, [rsp+1C0h+var_184]
0x18003edb6  mov     [rcx], eax
0x18003edb8  mov     rax, [rbp+0C0h+arg_28]
0x18003edbf  mov     [rsp+1C0h+var_170], 0
0x18003edc8  mov     [rax], r15
0x18003edcb  mov     rax, [rbp+0C0h+arg_30]
0x18003edd2  mov     [rax], r14d
0x18003edd5  mov     rcx, [rbp+0C0h+arg_0]
0x18003eddc  mov     eax, dword ptr [rsp+1C0h+var_180]
0x18003ede0  mov     [rcx], eax
0x18003ede2  mov     ecx, ebx
0x18003ede4  call    sub_180006C10
0x18003ede9  lea     rcx, [rsp+1C0h+var_160]
0x18003edee  call    sub_180004564
0x18003edf3  lea     rcx, [rsp+1C0h+var_178]
0x18003edf8  call    sub_180007638
0x18003edfd  lea     rcx, [rsp+1C0h+var_170]
0x18003ee02  call    sub_180007638
0x18003ee07  lea     rcx, [rsp+1C0h+var_168]
0x18003ee0c  call    sub_180007638
0x18003ee11  lea     rcx, [rbp+0C0h+var_C0]
0x18003ee15  call    sub_18004A43C
0x18003ee1a  mov     eax, ebx
0x18003ee1c  mov     rbx, [rsp+1C0h+arg_10]
0x18003ee24  add     rsp, 190h
0x18003ee2b  pop     r15
0x18003ee2d  pop     r14
0x18003ee2f  pop     r13
0x18003ee31  pop     r12
0x18003ee33  pop     rdi
0x18003ee34  pop     rsi
0x18003ee35  pop     rbp
0x18003ee36  retn
0x18003ee37  cmp     ecx, 0C004F012h
0x18003ee3d  jz      loc_18003ED79
0x18003ee43  call    sub_180004CA0
0x18003ee48  mov     ebx, ecx
0x18003ee4a  jmp     short loc_18003EDD5
```
