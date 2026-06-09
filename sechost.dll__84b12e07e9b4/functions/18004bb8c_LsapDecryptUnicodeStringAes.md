# LsapDecryptUnicodeStringAes

- ea: `0x18004bb8c`
- end: `0x18004bf2d`
- name: `LsapDecryptUnicodeStringAes`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003e2b4`

## callees

- `0x18004b424`
- `0x18004b8d8`
- `0x18004bacc`
- `0x18004bb8c`
- `0x18004c364`
- `0x18004f8f6`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004be20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004be20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004be8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bebc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004be8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bebc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beec`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004bc78`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004bc78`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004befe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004befe`

## pseudocode

```c
__int64 __fastcall LsapDecryptUnicodeStringAes(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  PUCHAR v6; // r15
  _BYTE *v7; // rsi
  ULONG v8; // r13d
  unsigned int v9; // r12d
  __int64 v10; // rdi
  NTSTATUS HMACWithSHA512; // ebx
  __int64 v12; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  size_t v16; // r13
  _WORD *v17; // rax
  _WORD *v18; // r14
  __int64 v19; // rcx
  _BYTE *v20; // rax
  __int64 v21; // rdx
  PUCHAR v22; // rax
  __int64 v23; // rax
  _BYTE *v24; // rcx
  ULONG cbSecret; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+44h] [rbp-BCh] BYREF
  ULONG cbInput; // [rsp+4Ch] [rbp-B4h] BYREF
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h]
  PUCHAR pbSecret; // [rsp+78h] [rbp-88h] BYREF
  void *Buf1; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v37; // [rsp+90h] [rbp-70h]
  _OWORD v38[2]; // [rsp+98h] [rbp-68h] BYREF
  char v39[24]; // [rsp+B8h] [rbp-48h] BYREF
  char v40[64]; // [rsp+D0h] [rbp-30h] BYREF

  v33 = a1;
  strcpy(v40, "Microsoft LSAD encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v6 = 0;
  pbSecret = 0;
  v7 = 0;
  v32 = 0;
  v8 = 0;
  cbSecret = 0;
  v9 = 0;
  Buf1 = 0;
  v10 = 0;
  LODWORD(Size) = 0;
  hMem = 0;
  cbInput = 0;
  qmemcpy(v38, "Microsoft LSAD MAC key AEAD-AES-", sizeof(v38));
  v27 = 0;
  v31 = 0;
  phAlgorithm = 0;
  *a5 = 0;
  strcpy(v39, "256-CBC-HMAC-SHA512 16");
  v37 = a5;
  HMACWithSHA512 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
  if ( HMACWithSHA512 >= 0 )
  {
    HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x37u, (__int64)&v32, (__int64)&v27 + 4);
    if ( HMACWithSHA512 < 0 )
    {
      v7 = (_BYTE *)v32;
    }
    else
    {
      v13 = LsapCrPrepareDataForHMACSignature(
              a3 + 64,
              v12,
              *(_QWORD *)(a3 + 88),
              *(unsigned int *)(a3 + 80),
              &hMem,
              &cbInput);
      v7 = (_BYTE *)v32;
      HMACWithSHA512 = v13;
      if ( v13 >= 0 )
      {
        HMACWithSHA512 = LsapCrGenerateHMACWithSHA512(phAlgorithm, cbInput, (__int64)&Buf1, (__int64)&Size);
        if ( HMACWithSHA512 >= 0 )
        {
          if ( memcmp_0(Buf1, (const void *)a3, (unsigned int)Size) )
          {
LABEL_6:
            HMACWithSHA512 = -1073741811;
            goto LABEL_17;
          }
          v14 = LsapCrGenerateHMACWithSHA512(phAlgorithm, 0x3Eu, (__int64)&pbSecret, (__int64)&cbSecret);
          v8 = cbSecret;
          HMACWithSHA512 = v14;
          v6 = pbSecret;
          if ( v14 >= 0 )
          {
            v15 = LsapCrDecryptDataWithAES(
                    *(PUCHAR *)(a3 + 88),
                    *(_DWORD *)(a3 + 80),
                    (PUCHAR)(a3 + 64),
                    pbSecret,
                    cbSecret,
                    (__int64)&v31,
                    (__int64)&v27);
            v9 = v27;
            HMACWithSHA512 = v15;
            v10 = v31;
            if ( v15 >= 0 )
            {
              if ( (unsigned int)v27 < 4 )
                goto LABEL_6;
              v16 = *(unsigned __int16 *)v31;
              if ( (_DWORD)v27 == (_DWORD)v16 + 4 )
              {
                v33 = *(unsigned __int16 *)(v31 + 2);
                v17 = LocalAlloc(0x40u, v33 + 16);
                v18 = v17;
                if ( v17 )
                {
                  *v17 = v16;
                  HMACWithSHA512 = 0;
                  v17[1] = v33;
                  *((_QWORD *)v17 + 1) = v17 + 8;
                  memcpy_0(v17 + 8, (const void *)(v10 + 4), v16);
                  *v37 = v18;
                }
                else
                {
                  HMACWithSHA512 = -1073741801;
                }
              }
              else
              {
                HMACWithSHA512 = -1073741811;
              }
              v8 = cbSecret;
            }
          }
        }
      }
    }
  }
LABEL_17:
  LsapFreeAesClearValue(0);
  if ( v10 )
  {
    v19 = v9;
    v20 = (_BYTE *)v10;
    if ( v9 )
    {
      do
      {
        *v20++ = 0;
        --v19;
      }
      while ( v19 );
    }
    LocalFree((HLOCAL)v10);
  }
  if ( v6 )
  {
    v21 = v8;
    v22 = v6;
    if ( v8 )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    LocalFree(v6);
  }
  LocalFree(Buf1);
  LocalFree(hMem);
  if ( v7 )
  {
    v23 = HIDWORD(v27);
    v24 = v7;
    if ( HIDWORD(v27) )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    LocalFree(v7);
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)HMACWithSHA512;
}

```

## disassembly

```asm
0x18004bb8c  mov     [rsp-8+arg_8], rbx
0x18004bb91  push    rbp
0x18004bb92  push    rsi
0x18004bb93  push    rdi
0x18004bb94  push    r12
0x18004bb96  push    r13
0x18004bb98  push    r14
0x18004bb9a  push    r15
0x18004bb9c  lea     rbp, [rsp-20h]
0x18004bba1  sub     rsp, 120h
0x18004bba8  mov     rax, cs:__security_cookie
0x18004bbaf  xor     rax, rsp
0x18004bbb2  mov     [rbp+50h+var_40], rax
0x18004bbb6  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE; "Microsoft LSAD encryption key AEAD-AES-"...
0x18004bbbd  mov     rax, [rbp+50h+arg_20]
0x18004bbc4  mov     r14, r8
0x18004bbc7  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x18004bbce  mov     [rsp+150h+var_E0], rcx
0x18004bbd3  xor     ecx, ecx
0x18004bbd5  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x18004bbd9  mov     r15d, ecx
0x18004bbdc  mov     [rsp+150h+var_D8], rcx
0x18004bbe1  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x18004bbe8  mov     esi, ecx
0x18004bbea  mov     [rsp+150h+var_E8], rcx
0x18004bbef  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x18004bbf3  mov     r13d, ecx
0x18004bbf6  mov     [rsp+150h+var_110], ecx
0x18004bbfa  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+2Eh; "-HMAC-SHA512 16"
0x18004bc01  mov     dword ptr [rsp+150h+var_10C+4], ecx
0x18004bc05  mov     r12d, ecx
0x18004bc08  movups  xmmword ptr [rbp+50h+var_80+20h], xmm0
0x18004bc0c  mov     [rbp+50h+Buf1], rcx
0x18004bc10  mov     edi, ecx
0x18004bc12  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM; "Microsoft LSAD MAC key AEAD-AES-256-CBC"...
0x18004bc19  mov     dword ptr [rsp+150h+Size], ecx
0x18004bc1d  lea     r9d, [rcx+8]; dwFlags
0x18004bc21  movups  xmmword ptr [rbp+50h+var_80+2Eh], xmm1
0x18004bc25  mov     [rbp+50h+hMem], rcx
0x18004bc29  xor     r8d, r8d; pszImplementation
0x18004bc2c  movups  xmm1, xmmword ptr cs:aMicrosoftLsadM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x18004bc33  mov     [rsp+150h+cbInput], ecx
0x18004bc37  lea     rdx, aSha512; "SHA512"
0x18004bc3e  movups  [rbp+50h+var_B8], xmm0
0x18004bc42  mov     dword ptr [rsp+150h+var_10C], ecx
0x18004bc46  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM+20h; "256-CBC-HMAC-SHA512 16"
0x18004bc4d  mov     [rsp+150h+var_F0], rcx
0x18004bc52  movups  [rbp+50h+var_A8], xmm1
0x18004bc56  mov     [rsp+150h+phAlgorithm], rcx
0x18004bc5b  movsd   xmm1, qword ptr cs:aMicrosoftLsadM+2Fh; "A512 16"
0x18004bc63  mov     [rax], rcx
0x18004bc66  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x18004bc6b  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18004bc6f  mov     [rbp+50h+var_C0], rax
0x18004bc73  movsd   qword ptr [rbp+50h+var_98+0Fh], xmm1
0x18004bc78  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004bc7e  mov     ebx, eax
0x18004bc80  test    eax, eax
0x18004bc82  js      loc_18004BE67
0x18004bc88  mov     rdx, [rsp+150h+var_E0]
0x18004bc8d  lea     rax, [rsp+150h+var_10C+4]
0x18004bc92  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004bc97  lea     r9, [rbp+50h+var_B8]
0x18004bc9b  mov     [rsp+150h+var_120], rax; __int64
0x18004bca0  lea     r8d, [rdi+10h]
0x18004bca4  lea     rax, [rsp+150h+var_E8]
0x18004bca9  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004bcae  mov     dword ptr [rsp+150h+pbSecret], 37h ; '7'; cbInput
0x18004bcb6  call    LsapCrGenerateHMACWithSHA512
0x18004bcbb  mov     ebx, eax
0x18004bcbd  test    eax, eax
0x18004bcbf  js      loc_18004BE62
0x18004bcc5  mov     r9d, [r14+50h]
0x18004bcc9  lea     rcx, [rsp+150h+cbInput]
0x18004bcce  mov     r8, [r14+58h]
0x18004bcd2  mov     qword ptr [rsp+150h+cbSecret], rcx
0x18004bcd7  lea     rcx, [rbp+50h+hMem]
0x18004bcdb  mov     [rsp+150h+pbSecret], rcx
0x18004bce0  lea     rcx, [r14+40h]
0x18004bce4  call    LsapCrPrepareDataForHMACSignature
0x18004bce9  mov     rsi, [rsp+150h+var_E8]
0x18004bcee  mov     ebx, eax
0x18004bcf0  test    eax, eax
0x18004bcf2  js      loc_18004BE67
0x18004bcf8  mov     r9, [rbp+50h+hMem]
0x18004bcfc  lea     rax, [rsp+150h+Size]
0x18004bd01  mov     r8d, dword ptr [rsp+150h+var_10C+4]
0x18004bd06  mov     rdx, rsi
0x18004bd09  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004bd0e  mov     [rsp+150h+var_120], rax; __int64
0x18004bd13  lea     rax, [rbp+50h+Buf1]
0x18004bd17  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004bd1c  mov     eax, [rsp+150h+cbInput]
0x18004bd20  mov     dword ptr [rsp+150h+pbSecret], eax; cbInput
0x18004bd24  call    LsapCrGenerateHMACWithSHA512
0x18004bd29  mov     ebx, eax
0x18004bd2b  test    eax, eax
0x18004bd2d  js      loc_18004BE67
0x18004bd33  mov     r8d, dword ptr [rsp+150h+Size]; Size
0x18004bd38  mov     rdx, r14; Buf2
0x18004bd3b  mov     rcx, [rbp+50h+Buf1]; Buf1
0x18004bd3f  call    memcmp_0
0x18004bd44  test    eax, eax
0x18004bd46  jz      short loc_18004BD52
0x18004bd48  mov     ebx, 0C000000Dh
0x18004bd4d  jmp     loc_18004BE67
0x18004bd52  mov     rdx, [rsp+150h+var_E0]
0x18004bd57  lea     rax, [rsp+150h+var_110]
0x18004bd5c  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004bd61  lea     r9, [rbp+50h+var_80]
0x18004bd65  mov     [rsp+150h+var_120], rax; __int64
0x18004bd6a  mov     r8d, 10h
0x18004bd70  lea     rax, [rsp+150h+var_D8]
0x18004bd75  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18004bd7a  mov     dword ptr [rsp+150h+pbSecret], 3Eh ; '>'; cbInput
0x18004bd82  call    LsapCrGenerateHMACWithSHA512
0x18004bd87  mov     r13d, [rsp+150h+var_110]
0x18004bd8c  mov     ebx, eax
0x18004bd8e  mov     r15, [rsp+150h+var_D8]
0x18004bd93  test    eax, eax
0x18004bd95  js      loc_18004BE67
0x18004bd9b  mov     edx, [r14+50h]; cbInput
0x18004bd9f  lea     rax, [rsp+150h+var_10C]
0x18004bda4  mov     rcx, [r14+58h]; pbInput
0x18004bda8  lea     r8, [r14+40h]; pbIV
0x18004bdac  mov     [rsp+150h+var_118], rax; __int64
0x18004bdb1  lea     rax, [rsp+150h+var_F0]
0x18004bdb6  mov     [rsp+150h+var_120], rax; __int64
0x18004bdbb  mov     [rsp+150h+cbSecret], r13d; cbSecret
0x18004bdc0  mov     [rsp+150h+pbSecret], r15; pbSecret
0x18004bdc5  call    LsapCrDecryptDataWithAES
0x18004bdca  mov     r12d, dword ptr [rsp+150h+var_10C]
0x18004bdcf  mov     ebx, eax
0x18004bdd1  mov     rdi, [rsp+150h+var_F0]
0x18004bdd6  test    eax, eax
0x18004bdd8  js      loc_18004BE67
0x18004bdde  cmp     r12d, 4
0x18004bde2  jb      loc_18004BD48
0x18004bde8  movzx   r13d, word ptr [rdi]
0x18004bdec  lea     eax, [r13+4]
0x18004bdf0  cmp     r12d, eax
0x18004bdf3  jz      short loc_18004BE01
0x18004bdf5  mov     ebx, 0C000000Dh
0x18004bdfa  mov     r13d, [rsp+150h+var_110]
0x18004bdff  jmp     short loc_18004BE67
0x18004be01  movzx   eax, word ptr [rdi+2]
0x18004be05  mov     [rsp+150h+var_E0], rax
0x18004be0a  lea     rdx, [rax+10h]; uBytes
0x18004be0e  cmp     rdx, 10h
0x18004be12  jnb     short loc_18004BE1B
0x18004be14  mov     ebx, 0C0000095h
0x18004be19  jmp     short loc_18004BDFA
0x18004be1b  mov     ecx, 40h ; '@'; uFlags
0x18004be20  call    cs:__imp_LocalAlloc
0x18004be26  mov     r14, rax
0x18004be29  test    rax, rax
0x18004be2c  jnz     short loc_18004BE35
0x18004be2e  mov     ebx, 0C0000017h
0x18004be33  jmp     short loc_18004BDFA
0x18004be35  mov     [rax], r13w
0x18004be39  lea     rcx, [r14+10h]; void *
0x18004be3d  mov     rax, [rsp+150h+var_E0]
0x18004be42  lea     rdx, [rdi+4]; Src
0x18004be46  xor     ebx, ebx
0x18004be48  mov     [r14+2], ax
0x18004be4d  mov     r8, r13; Size
0x18004be50  mov     [r14+8], rcx
0x18004be54  call    memcpy_0
0x18004be59  mov     rax, [rbp+50h+var_C0]
0x18004be5d  mov     [rax], r14
0x18004be60  jmp     short loc_18004BDFA
0x18004be62  mov     rsi, [rsp+150h+var_E8]
0x18004be67  xor     ecx, ecx
0x18004be69  call    LsapFreeAesClearValue
0x18004be6e  test    rdi, rdi
0x18004be71  jz      short loc_18004BE93
0x18004be73  mov     ecx, r12d
0x18004be76  mov     rax, rdi
0x18004be79  test    r12d, r12d
0x18004be7c  jz      short loc_18004BE8A
0x18004be7e  mov     byte ptr [rax], 0
0x18004be81  inc     rax
0x18004be84  sub     rcx, 1
0x18004be88  jnz     short loc_18004BE7E
0x18004be8a  mov     rcx, rdi; hMem
0x18004be8d  call    cs:__imp_LocalFree
0x18004be93  test    r15, r15
0x18004be96  jz      short loc_18004BEB8
0x18004be98  mov     edx, r13d
0x18004be9b  mov     rax, r15
0x18004be9e  test    r13d, r13d
0x18004bea1  jz      short loc_18004BEAF
0x18004bea3  mov     byte ptr [rax], 0
0x18004bea6  inc     rax
0x18004bea9  sub     rdx, 1
0x18004bead  jnz     short loc_18004BEA3
0x18004beaf  mov     rcx, r15; hMem
0x18004beb2  call    cs:__imp_LocalFree
0x18004beb8  mov     rcx, [rbp+50h+Buf1]; hMem
0x18004bebc  call    cs:__imp_LocalFree
0x18004bec2  mov     rcx, [rbp+50h+hMem]; hMem
0x18004bec6  call    cs:__imp_LocalFree
0x18004becc  test    rsi, rsi
0x18004becf  jz      short loc_18004BEF2
0x18004bed1  mov     eax, dword ptr [rsp+150h+var_10C+4]
0x18004bed5  mov     rcx, rsi
0x18004bed8  test    rax, rax
0x18004bedb  jz      short loc_18004BEE9
0x18004bedd  mov     byte ptr [rcx], 0
0x18004bee0  inc     rcx
0x18004bee3  sub     rax, 1
0x18004bee7  jnz     short loc_18004BEDD
0x18004bee9  mov     rcx, rsi; hMem
0x18004beec  call    cs:__imp_LocalFree
0x18004bef2  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18004bef7  test    rcx, rcx
0x18004befa  jz      short loc_18004BF04
0x18004befc  xor     edx, edx; dwFlags
0x18004befe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004bf04  mov     eax, ebx
0x18004bf06  mov     rcx, [rbp+50h+var_40]
0x18004bf0a  xor     rcx, rsp; StackCookie
0x18004bf0d  call    __security_check_cookie
0x18004bf12  mov     rbx, [rsp+150h+arg_8]
0x18004bf1a  add     rsp, 120h
0x18004bf21  pop     r15
0x18004bf23  pop     r14
0x18004bf25  pop     r13
0x18004bf27  pop     r12
0x18004bf29  pop     rdi
0x18004bf2a  pop     rsi
0x18004bf2b  pop     rbp
0x18004bf2c  retn
```
