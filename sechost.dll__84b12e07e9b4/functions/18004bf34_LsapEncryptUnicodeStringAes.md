# LsapEncryptUnicodeStringAes

- ea: `0x18004bf34`
- end: `0x18004c2fe`
- name: `LsapEncryptUnicodeStringAes`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003e360`

## callees

- `0x18004b694`
- `0x18004b8d8`
- `0x18004bacc`
- `0x18004bf34`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c074`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004c074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c26b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c242`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c26b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c2bd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c035`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004c035`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c2cf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004c2cf`

## pseudocode

```c
__int64 __fastcall LsapEncryptUnicodeStringAes(
        void *a1,
        __int64 a2,
        UCHAR *a3,
        __int64 a4,
        unsigned __int16 *a5,
        void **a6)
{
  ULONG v6; // esi
  _BYTE *v7; // r12
  _BYTE *v8; // r14
  HLOCAL v9; // r15
  UCHAR *v11; // rdi
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  UCHAR *v14; // rax
  const void *v15; // rdx
  int HMACWithSHA512; // eax
  PUCHAR v17; // r13
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  HLOCAL v21; // r13
  void **v22; // rcx
  __int64 v23; // rax
  _BYTE *v24; // rcx
  __int64 v25; // rcx
  UCHAR *v26; // rax
  __int64 v27; // rcx
  _BYTE *v28; // rax
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  ULONG cbSecret; // [rsp+50h] [rbp-B0h] BYREF
  ULONG cbInput; // [rsp+54h] [rbp-ACh] BYREF
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v35; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v36; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v37; // [rsp+78h] [rbp-88h] BYREF
  void *Src[2]; // [rsp+80h] [rbp-80h] BYREF
  void **v39; // [rsp+90h] [rbp-70h]
  PUCHAR pbIV; // [rsp+98h] [rbp-68h]
  char v41[56]; // [rsp+A0h] [rbp-60h] BYREF
  char v42[64]; // [rsp+D8h] [rbp-28h] BYREF

  v6 = 0;
  v7 = 0;
  strcpy(v42, "Microsoft LSAD encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v8 = 0;
  pbIV = a3;
  v9 = 0;
  Src[1] = a1;
  v39 = a6;
  phAlgorithm = 0;
  v37 = 0;
  v35 = 0;
  cbSecret = 0;
  v36 = 0;
  strcpy(v41, "Microsoft LSAD MAC key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v30 = 0;
  Src[0] = 0;
  LODWORD(Size) = 0;
  hMem = 0;
  cbInput = 0;
  if ( !*a6 )
    return 3221225485LL;
  v11 = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
  if ( v12 >= 0 )
  {
    if ( *a5 )
    {
      v13 = *a5;
      v6 = v13 + 4;
    }
    else
    {
      v6 = 4;
      v13 = 0;
    }
    v14 = (UCHAR *)LocalAlloc(0x40u, v6);
    v11 = v14;
    if ( v14 )
    {
      *(_WORD *)v14 = *a5;
      *((_WORD *)v14 + 1) = a5[1];
      if ( v13 )
      {
        v15 = (const void *)*((_QWORD *)a5 + 1);
        if ( v15 )
          memcpy_0(v14 + 4, v15, v13);
      }
      HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x3Eu, (__int64)&v37, (__int64)&cbSecret);
      v7 = v37;
      v12 = HMACWithSHA512;
      if ( HMACWithSHA512 >= 0 )
      {
        v17 = pbIV;
        v12 = LsapCrEncryptDataWithAES(v11, v6, pbIV, (__int64)v37, cbSecret, (__int64)&v36, (__int64)&v30);
        if ( v12 < 0 )
        {
          v9 = v36;
        }
        else
        {
          v18 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x37u, (__int64)&v35, (__int64)&v30 + 4);
          v9 = v36;
          v12 = v18;
          if ( v18 >= 0 )
          {
            v20 = LsapCrPrepareDataForHMACSignature(v17, v19, v36, (unsigned int)v30, &hMem, &cbInput);
            v21 = hMem;
            v12 = v20;
            v8 = v35;
            if ( v20 >= 0 )
            {
              v12 = LsapCrGenerateHMACWithSHA512(phAlgorithm, cbInput, (__int64)Src, (__int64)&Size);
              if ( v12 >= 0 )
              {
                memcpy_0(*v39, Src[0], (unsigned int)Size);
                v22 = v39;
                *((_OWORD *)*v39 + 4) = *(_OWORD *)pbIV;
                *((_QWORD *)*v22 + 11) = v9;
                v9 = 0;
                *((_DWORD *)*v22 + 20) = v30;
              }
            }
            goto LABEL_21;
          }
          v8 = v35;
        }
      }
    }
    else
    {
      v12 = -1073741801;
    }
  }
  v21 = hMem;
LABEL_21:
  LocalFree(Src[0]);
  LocalFree(v21);
  if ( v8 )
  {
    v23 = HIDWORD(v30);
    v24 = v8;
    if ( HIDWORD(v30) )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    LocalFree(v8);
  }
  LocalFree(v9);
  if ( v11 )
  {
    v25 = v6;
    v26 = v11;
    if ( v6 )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    LocalFree(v11);
  }
  if ( v7 )
  {
    v27 = cbSecret;
    v28 = v7;
    if ( cbSecret )
    {
      do
      {
        *v28++ = 0;
        --v27;
      }
      while ( v27 );
    }
    LocalFree(v7);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004bf34  mov     [rsp-8+arg_8], rbx
0x18004bf39  push    rbp
0x18004bf3a  push    rsi
0x18004bf3b  push    rdi
0x18004bf3c  push    r12
0x18004bf3e  push    r13
0x18004bf40  push    r14
0x18004bf42  push    r15
0x18004bf44  lea     rbp, [rsp-20h]
0x18004bf49  sub     rsp, 120h
0x18004bf50  mov     rax, cs:__security_cookie
0x18004bf57  xor     rax, rsp
0x18004bf5a  mov     [rbp+50h+var_38], rax
0x18004bf5e  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE; "Microsoft LSAD encryption key AEAD-AES-"...
0x18004bf65  mov     rax, [rbp+50h+arg_28]
0x18004bf6c  xor     esi, esi
0x18004bf6e  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x18004bf75  mov     r13, [rbp+50h+arg_20]
0x18004bf7c  mov     r12d, esi
0x18004bf7f  movups  xmmword ptr [rbp+50h+var_78], xmm0
0x18004bf83  mov     r14d, esi
0x18004bf86  mov     [rbp+50h+pbIV], r8
0x18004bf8a  mov     r15d, esi
0x18004bf8d  mov     [rbp+50h+var_C8], rcx
0x18004bf91  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x18004bf98  mov     [rbp+50h+var_C0], rax
0x18004bf9c  movups  xmmword ptr [rbp+50h+var_78+10h], xmm1
0x18004bfa0  mov     [rsp+150h+phAlgorithm], rsi
0x18004bfa5  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+2Eh; "-HMAC-SHA512 16"
0x18004bfac  mov     [rsp+150h+var_D8], rsi
0x18004bfb1  movups  xmmword ptr [rbp+50h+var_78+20h], xmm0
0x18004bfb5  mov     [rsp+150h+var_E8], rsi
0x18004bfba  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM; "Microsoft LSAD MAC key AEAD-AES-256-CBC"...
0x18004bfc1  mov     [rsp+150h+var_100], esi
0x18004bfc5  movups  xmmword ptr [rbp+50h+var_78+2Eh], xmm1
0x18004bfc9  mov     dword ptr [rsp+150h+var_108+4], esi
0x18004bfcd  movups  xmm1, xmmword ptr cs:aMicrosoftLsadM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x18004bfd4  mov     [rsp+150h+var_E0], rsi
0x18004bfd9  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18004bfdd  mov     dword ptr [rsp+150h+var_108], esi
0x18004bfe1  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM+20h; "256-CBC-HMAC-SHA512 16"
0x18004bfe8  mov     [rbp+50h+Src], rsi
0x18004bfec  movups  xmmword ptr [rbp+50h+var_B0+10h], xmm1
0x18004bff0  mov     dword ptr [rsp+150h+Size], esi
0x18004bff4  movsd   xmm1, qword ptr cs:aMicrosoftLsadM+2Fh; "A512 16"
0x18004bffc  movups  xmmword ptr [rbp+50h+var_B0+20h], xmm0
0x18004c000  mov     [rsp+150h+hMem], rsi
0x18004c005  movsd   qword ptr [rbp+50h+var_B0+2Fh], xmm1
0x18004c00a  mov     [rsp+150h+var_FC], esi
0x18004c00e  cmp     [rax], rsi
0x18004c011  jnz     short loc_18004C01D
0x18004c013  mov     eax, 0C000000Dh
0x18004c018  jmp     loc_18004C2D7
0x18004c01d  mov     r9d, 8; dwFlags
0x18004c023  lea     rdx, aSha512; "SHA512"
0x18004c02a  xor     r8d, r8d; pszImplementation
0x18004c02d  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x18004c032  mov     rdi, rsi
0x18004c035  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004c03b  mov     ebx, eax
0x18004c03d  test    eax, eax
0x18004c03f  js      loc_18004C230
0x18004c045  cmp     [r13+0], si
0x18004c04a  jbe     short loc_18004C066
0x18004c04c  movzx   ebx, word ptr [r13+0]
0x18004c051  lea     esi, [rbx+4]
0x18004c054  cmp     esi, 4
0x18004c057  jnb     short loc_18004C06D
0x18004c059  or      esi, 0FFFFFFFFh
0x18004c05c  mov     ebx, 0C0000095h
0x18004c061  jmp     loc_18004C230
0x18004c066  mov     esi, 4
0x18004c06b  xor     ebx, ebx
0x18004c06d  mov     edx, esi; uBytes
0x18004c06f  mov     ecx, 40h ; '@'; uFlags
0x18004c074  call    cs:__imp_LocalAlloc
0x18004c07a  mov     rdi, rax
0x18004c07d  test    rax, rax
0x18004c080  jnz     short loc_18004C08C
0x18004c082  mov     ebx, 0C0000017h
0x18004c087  jmp     loc_18004C230
0x18004c08c  movzx   eax, word ptr [r13+0]
0x18004c091  mov     [rdi], ax
0x18004c094  movzx   eax, word ptr [r13+2]
0x18004c099  mov     [rdi+2], ax
0x18004c09d  test    ebx, ebx
0x18004c09f  jz      short loc_18004C0B6
0x18004c0a1  mov     rdx, [r13+8]; Src
0x18004c0a5  test    rdx, rdx
0x18004c0a8  jz      short loc_18004C0B6
0x18004c0aa  mov     r8d, ebx; Size
0x18004c0ad  lea     rcx, [rdi+4]; void *
0x18004c0b1  call    memcpy_0
0x18004c0b6  mov     rdx, [rbp+50h+var_C8]
0x18004c0ba  lea     rax, [rsp+150h+var_100]
0x18004c0bf  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004c0c4  lea     r9, [rbp+50h+var_78]
0x18004c0c8  mov     [rsp+150h+var_120], rax; __int64
0x18004c0cd  mov     r8d, 10h
0x18004c0d3  lea     rax, [rsp+150h+var_D8]
0x18004c0d8  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004c0dd  mov     [rsp+150h+cbInput], 3Eh ; '>'; cbInput
0x18004c0e5  call    LsapCrGenerateHMACWithSHA512
0x18004c0ea  mov     r12, [rsp+150h+var_D8]
0x18004c0ef  mov     ebx, eax
0x18004c0f1  test    eax, eax
0x18004c0f3  js      loc_18004C230
0x18004c0f9  mov     r13, [rbp+50h+pbIV]
0x18004c0fd  lea     rax, [rsp+150h+var_108]
0x18004c102  mov     [rsp+150h+var_118], rax; __int64
0x18004c107  mov     r8, r13; pbIV
0x18004c10a  lea     rax, [rsp+150h+var_E0]
0x18004c10f  mov     edx, esi; cbInput
0x18004c111  mov     [rsp+150h+var_120], rax; __int64
0x18004c116  mov     rcx, rdi; pbInput
0x18004c119  mov     eax, [rsp+150h+var_100]
0x18004c11d  mov     [rsp+150h+cbSecret], eax; cbSecret
0x18004c121  mov     qword ptr [rsp+150h+cbInput], r12; __int64
0x18004c126  call    LsapCrEncryptDataWithAES
0x18004c12b  mov     ebx, eax
0x18004c12d  test    eax, eax
0x18004c12f  js      loc_18004C22B
0x18004c135  mov     rdx, [rbp+50h+var_C8]
0x18004c139  lea     rax, [rsp+150h+var_108+4]
0x18004c13e  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004c143  lea     r9, [rbp+50h+var_B0]
0x18004c147  mov     [rsp+150h+var_120], rax; __int64
0x18004c14c  mov     r8d, 10h
0x18004c152  lea     rax, [rsp+150h+var_E8]
0x18004c157  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004c15c  mov     [rsp+150h+cbInput], 37h ; '7'; cbInput
0x18004c164  call    LsapCrGenerateHMACWithSHA512
0x18004c169  mov     r15, [rsp+150h+var_E0]
0x18004c16e  mov     ebx, eax
0x18004c170  test    eax, eax
0x18004c172  js      loc_18004C224
0x18004c178  mov     r9d, dword ptr [rsp+150h+var_108]
0x18004c17d  lea     rax, [rsp+150h+var_FC]
0x18004c182  mov     qword ptr [rsp+150h+cbSecret], rax
0x18004c187  mov     r8, r15
0x18004c18a  lea     rax, [rsp+150h+hMem]
0x18004c18f  mov     rcx, r13
0x18004c192  mov     qword ptr [rsp+150h+cbInput], rax
0x18004c197  call    LsapCrPrepareDataForHMACSignature
0x18004c19c  mov     r13, [rsp+150h+hMem]
0x18004c1a1  mov     ebx, eax
0x18004c1a3  mov     r14, [rsp+150h+var_E8]
0x18004c1a8  test    eax, eax
0x18004c1aa  js      loc_18004C235
0x18004c1b0  mov     r8d, dword ptr [rsp+150h+var_108+4]
0x18004c1b5  lea     rax, [rsp+150h+Size]
0x18004c1ba  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004c1bf  mov     r9, r13
0x18004c1c2  mov     [rsp+150h+var_120], rax; __int64
0x18004c1c7  mov     rdx, r14
0x18004c1ca  lea     rax, [rbp+50h+Src]
0x18004c1ce  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004c1d3  mov     eax, [rsp+150h+var_FC]
0x18004c1d7  mov     [rsp+150h+cbInput], eax; cbInput
0x18004c1db  call    LsapCrGenerateHMACWithSHA512
0x18004c1e0  mov     ebx, eax
0x18004c1e2  test    eax, eax
0x18004c1e4  js      short loc_18004C235
0x18004c1e6  mov     rcx, [rbp+50h+var_C0]
0x18004c1ea  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18004c1ef  mov     rdx, [rbp+50h+Src]; Src
0x18004c1f3  mov     rcx, [rcx]; void *
0x18004c1f6  call    memcpy_0
0x18004c1fb  mov     rcx, [rbp+50h+var_C0]
0x18004c1ff  mov     rdx, [rbp+50h+pbIV]
0x18004c203  mov     rax, [rcx]
0x18004c206  movups  xmm0, xmmword ptr [rdx]
0x18004c209  movdqu  xmmword ptr [rax+40h], xmm0
0x18004c20e  mov     rax, [rcx]
0x18004c211  mov     [rax+58h], r15
0x18004c215  xor     r15d, r15d
0x18004c218  mov     rax, [rcx]
0x18004c21b  mov     ecx, dword ptr [rsp+150h+var_108]
0x18004c21f  mov     [rax+50h], ecx
0x18004c222  jmp     short loc_18004C235
0x18004c224  mov     r14, [rsp+150h+var_E8]
0x18004c229  jmp     short loc_18004C230
0x18004c22b  mov     r15, [rsp+150h+var_E0]
0x18004c230  mov     r13, [rsp+150h+hMem]
0x18004c235  mov     rcx, [rbp+50h+Src]; hMem
0x18004c239  call    cs:__imp_LocalFree
0x18004c23f  mov     rcx, r13; hMem
0x18004c242  call    cs:__imp_LocalFree
0x18004c248  xor     r13d, r13d
0x18004c24b  test    r14, r14
0x18004c24e  jz      short loc_18004C271
0x18004c250  mov     eax, dword ptr [rsp+150h+var_108+4]
0x18004c254  mov     rcx, r14
0x18004c257  test    rax, rax
0x18004c25a  jz      short loc_18004C268
0x18004c25c  mov     [rcx], r13b
0x18004c25f  inc     rcx
0x18004c262  sub     rax, 1
0x18004c266  jnz     short loc_18004C25C
0x18004c268  mov     rcx, r14; hMem
0x18004c26b  call    cs:__imp_LocalFree
0x18004c271  mov     rcx, r15; hMem
0x18004c274  call    cs:__imp_LocalFree
0x18004c27a  test    rdi, rdi
0x18004c27d  jz      short loc_18004C29D
0x18004c27f  mov     ecx, esi
0x18004c281  mov     rax, rdi
0x18004c284  test    esi, esi
0x18004c286  jz      short loc_18004C294
0x18004c288  mov     [rax], r13b
0x18004c28b  inc     rax
0x18004c28e  sub     rcx, 1
0x18004c292  jnz     short loc_18004C288
0x18004c294  mov     rcx, rdi; hMem
0x18004c297  call    cs:__imp_LocalFree
0x18004c29d  test    r12, r12
0x18004c2a0  jz      short loc_18004C2C3
0x18004c2a2  mov     ecx, [rsp+150h+var_100]
0x18004c2a6  mov     rax, r12
0x18004c2a9  test    rcx, rcx
0x18004c2ac  jz      short loc_18004C2BA
0x18004c2ae  mov     [rax], r13b
0x18004c2b1  inc     rax
0x18004c2b4  sub     rcx, 1
0x18004c2b8  jnz     short loc_18004C2AE
0x18004c2ba  mov     rcx, r12; hMem
0x18004c2bd  call    cs:__imp_LocalFree
0x18004c2c3  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004c2c8  test    rcx, rcx
0x18004c2cb  jz      short loc_18004C2D5
0x18004c2cd  xor     edx, edx; dwFlags
0x18004c2cf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004c2d5  mov     eax, ebx
0x18004c2d7  mov     rcx, [rbp+50h+var_38]
0x18004c2db  xor     rcx, rsp; StackCookie
0x18004c2de  call    __security_check_cookie
0x18004c2e3  mov     rbx, [rsp+150h+arg_8]
0x18004c2eb  add     rsp, 120h
0x18004c2f2  pop     r15
0x18004c2f4  pop     r14
0x18004c2f6  pop     r13
0x18004c2f8  pop     r12
0x18004c2fa  pop     rdi
0x18004c2fb  pop     rsi
0x18004c2fc  pop     rbp
0x18004c2fd  retn
```
