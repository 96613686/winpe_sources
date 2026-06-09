# MinCrypK_VerifySignedDataKModeEx

- ea: `0x180015624`
- end: `0x180015e47`
- name: `MinCrypK_VerifySignedDataKModeEx`
- size: `2083`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, void *, __int64, __int64)`
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015360`
- `0x1800155d0`
- `0x1800162e4`
- `0x18002151c`
- `0x180045408`

## callees

- `0x180014614`
- `0x180014748`
- `0x180014bf4`
- `0x180014cc4`
- `0x180014ec4`
- `0x180014f60`
- `0x1800154e4`
- `0x180015550`
- `0x180015624`
- `0x180016a98`
- `0x180016f2c`
- `0x180017ebc`
- `0x180017f60`
- `0x1800183c8`
- `0x1800187d4`
- `0x180033908`
- `0x180033950`
- `0x18004cffc`
- `0x18004d040`
- `0x18004dd2c`
- `0x18004e328`
- `0x18004f3e8`

## import_xrefs

- `securekernel!SkAllocatePool` at `0x1800156d4`
- `securekernel!SkAllocatePool` at `0x180015ac1`
- `securekernel!SkAllocatePool` at `0x1800156d4`
- `securekernel!SkAllocatePool` at `0x180015ac1`
- `securekernel!RtlCompareMemory` at `0x18001573a`
- `securekernel!RtlCompareMemory` at `0x18001573a`
- `securekernel!SkFreePool` at `0x180015e1b`
- `securekernel!SkFreePool` at `0x180015e34`
- `securekernel!SkFreePool` at `0x180033b32`
- `securekernel!SkFreePool` at `0x180033b4d`
- `securekernel!SkFreePool` at `0x180015e1b`
- `securekernel!SkFreePool` at `0x180015e34`
- `securekernel!SkFreePool` at `0x180033b32`
- `securekernel!SkFreePool` at `0x180033b4d`

## pseudocode

```c
__int64 __fastcall MinCrypK_VerifySignedDataKModeEx(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        char *a7,
        __int64 *a8,
        _OWORD *a9)
{
  int v11; // esi
  unsigned int v12; // edi
  __int64 Pool; // rax
  __int64 v14; // r14
  int PlatformManifestBinaryIDAttribute; // ebx
  __int64 v16; // r14
  __int64 v17; // r13
  __int64 SignerCertificateByIssuerAndSerialNumber; // rax
  _DWORD *v19; // r12
  int v20; // eax
  unsigned int i; // ebx
  __int64 v22; // rdx
  __int64 v23; // r12
  char v24; // r8
  __int64 j; // rdx
  int v26; // eax
  int v27; // r13d
  __int64 v28; // r12
  int v29; // ecx
  int v30; // r8d
  int v31; // eax
  __int64 v32; // r12
  unsigned int v33; // r13d
  int v34; // r12d
  __int64 v35; // r9
  __int64 v37; // [rsp+0h] [rbp-108h] BYREF
  int SigningTime; // [rsp+30h] [rbp-D8h]
  unsigned int v39; // [rsp+34h] [rbp-D4h]
  __int64 v40; // [rsp+38h] [rbp-D0h]
  unsigned int v41; // [rsp+40h] [rbp-C8h] BYREF
  char v42; // [rsp+44h] [rbp-C4h]
  int v43; // [rsp+48h] [rbp-C0h] BYREF
  int v44; // [rsp+4Ch] [rbp-BCh]
  int v45; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v48; // [rsp+64h] [rbp-A4h]
  __int64 v49; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v50; // [rsp+70h] [rbp-98h] BYREF
  __int128 v51; // [rsp+80h] [rbp-88h]
  __int128 v52; // [rsp+90h] [rbp-78h]
  unsigned int v53; // [rsp+A0h] [rbp-68h]
  int v54; // [rsp+A4h] [rbp-64h]
  __int64 v55; // [rsp+A8h] [rbp-60h]
  __int128 v56; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-48h]
  int v58; // [rsp+C8h] [rbp-40h]
  __int64 v59; // [rsp+D0h] [rbp-38h]
  __int64 *v60; // [rsp+D8h] [rbp-30h]

  v60 = &v37;
  v11 = -1073740760;
  SigningTime = -1073740760;
  v40 = 0;
  v43 = 0;
  v55 = 0;
  v12 = 0;
  v39 = 0;
  v56 = 0;
  v45 = 0;
  v41 = 0;
  v46 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  LODWORD(v49) = 0;
  v44 = 0;
  v47 = 10;
  memset_0(a7, 0, 0x50u);
  Pool = SkAllocatePool(1, 2768, 1919109443);
  v14 = Pool;
  v40 = Pool;
  if ( Pool )
  {
    v16 = Pool + 2400;
    if ( (int)MinAsn1ParseSignedData(a1, a2, Pool + 2400) < 0 )
    {
LABEL_4:
      v12 = 327680;
LABEL_102:
      PlatformManifestBinaryIDAttribute = -1073740760;
      SigningTime = -1073740760;
      goto LABEL_103;
    }
    if ( *(_DWORD *)(v16 + 32) != 9 || RtlCompareMemory(&qword_180052018, *(const void **)(v16 + 40), 9u) != 9 )
    {
      v12 = 0x40000;
      goto LABEL_102;
    }
    if ( a4 && a3 )
    {
      if ( *(_DWORD *)(v16 + 80) )
        *(_OWORD *)a7 = *(_OWORD *)(v16 + 80);
      *((_QWORD *)a7 + 3) = a3;
      *((_DWORD *)a7 + 4) = a4;
    }
    else
    {
      if ( !*(_DWORD *)(v16 + 80) || !*(_DWORD *)(v16 + 96) )
        goto LABEL_4;
      *(_OWORD *)a7 = *(_OWORD *)(v16 + 80);
      if ( (int)MinAsn1SignedDataGetContent(v16, a7 + 16) <= 0 )
        goto LABEL_15;
      v45 = 1;
    }
    if ( !*(_DWORD *)(v16 + 160) )
      goto LABEL_4;
    v17 = v40;
    if ( (int)MinAsn1ParseSignedDataCertificatesEx(v16 + 112, &v47, v40) < 0
      || !v47
      || (SignerCertificateByIssuerAndSerialNumber = I_MinCryptFindSignerCertificateByIssuerAndSerialNumber(
                                                       (unsigned int *)(v16 + 192),
                                                       (unsigned int *)(v16 + 208),
                                                       v47,
                                                       v17),
          (v59 = SignerCertificateByIssuerAndSerialNumber) == 0) )
    {
      v12 = 393216;
      goto LABEL_102;
    }
    *((_OWORD *)a7 + 2) = *(_OWORD *)(SignerCertificateByIssuerAndSerialNumber + 16);
    v19 = (_DWORD *)(v16 + 240);
    *((_OWORD *)a7 + 3) = *(_OWORD *)(v16 + 240);
    *((_OWORD *)a7 + 4) = *(_OWORD *)(v16 + 288);
    v20 = MinCryptVerifyCertificateWithPolicy2(SignerCertificateByIssuerAndSerialNumber, v47, v40, a5, a6, v16 + 240);
    PlatformManifestBinaryIDAttribute = v20;
    SigningTime = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -1073740285 )
        goto LABEL_104;
      SigningTime = 0;
      v41 = 1;
    }
    if ( *v19 )
    {
      PlatformManifestBinaryIDAttribute = I_MinCryptGetPlatformManifestBinaryIDAttribute(v16 + 240, a6);
      SigningTime = PlatformManifestBinaryIDAttribute;
      if ( PlatformManifestBinaryIDAttribute < 0 )
        goto LABEL_104;
    }
    if ( !a5 || (*(_DWORD *)(a5 + 4) & 0x10) == 0 )
    {
      if ( *(_QWORD *)(a6 + 16) )
      {
        for ( i = 0; ; ++i )
        {
          v53 = i;
          v22 = *(_QWORD *)(a6 + 16);
          if ( i >= *(_DWORD *)(v22 + 48) )
            break;
          v23 = 120LL * i;
          if ( (unsigned __int8)I_MinCryptIsHashAlgPossiblyWeak(
                                  0x400000,
                                  *(unsigned int *)(*(_QWORD *)(v22 + 40) + v23),
                                  0)
            && !(unsigned __int8)MincryptIsWeakCertHashAllowed(v23 + *(_QWORD *)(*(_QWORD *)(a6 + 16) + 40LL)) )
          {
            LODWORD(v49) = 1;
            v58 = 1;
            break;
          }
        }
        v19 = (_DWORD *)(v16 + 240);
      }
      v24 = 0;
      v42 = 0;
      if ( g_WeakCryptoPolicies )
      {
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          v54 = j;
          if ( (unsigned int)j >= *(_DWORD *)g_WeakCryptoPolicies )
            break;
          if ( (*(_DWORD *)(*(_QWORD *)(g_WeakCryptoPolicies + 8) + 48 * j + 4) & 0x4014000) != 0 )
          {
            v24 = 1;
            v42 = 1;
            break;
          }
        }
      }
      v26 = v44;
      if ( v24 )
        v26 = 1;
      v44 = v26;
    }
    v48 = MinCryptDecodeHashAlgorithmIdentifier(v16 + 224);
    if ( !v48 )
      goto LABEL_15;
    v27 = MinCryptDecodeHashAlgorithmIdentifier(v16 + 256);
    if ( v45 )
    {
      if ( (int)MinAsn1ExtractContent(*(_QWORD *)(v16 + 104), *(unsigned int *)(v16 + 96), &v56, (char *)&v56 + 8) < 0 )
      {
LABEL_15:
        PlatformManifestBinaryIDAttribute = -1073740760;
        SigningTime = -1073740760;
LABEL_16:
        v12 = 0x40000;
LABEL_103:
        v39 = v12;
        goto LABEL_104;
      }
    }
    else
    {
      LODWORD(v56) = a4;
      *((_QWORD *)&v56 + 1) = a3;
    }
    v28 = (unsigned int)*v19;
    v45 = v28;
    if ( v27 == 0x8000 && !(_DWORD)v28 )
    {
      v29 = DWORD2(v56);
      v57 = *((_QWORD *)&v56 + 1);
      v30 = v56;
      goto LABEL_66;
    }
    PlatformManifestBinaryIDAttribute = HashpHashMemory(v48, 1, &v56, v16 + 304, &v43);
    SigningTime = PlatformManifestBinaryIDAttribute;
    if ( PlatformManifestBinaryIDAttribute < 0 )
      goto LABEL_16;
    v29 = v16 + 304;
    v57 = v16 + 304;
    if ( !(_DWORD)v28 )
    {
      v30 = v43;
      goto LABEL_66;
    }
    if ( v27 != 0x8000 )
    {
      v31 = I_MinCryptVerifySignerAuthenticatedAttributes(v48, v16 + 304, &v43, v16 + 240);
      SigningTime = v31;
      v30 = v43;
      v29 = v16 + 304;
      goto LABEL_63;
    }
    v32 = SkAllocatePool(1, v28, 1919109443);
    v55 = v32;
    if ( v32 )
    {
      v31 = I_MinCryptVerifyReturnSignerAuthenticatedAttributes((int)v16 + 304, v43, v32, (unsigned int)&v45, v16 + 240);
      SigningTime = v31;
      v29 = v32;
      v57 = v32;
      v30 = v45;
LABEL_63:
      PlatformManifestBinaryIDAttribute = v31;
      if ( v31 < 0 )
        goto LABEL_16;
LABEL_66:
      PlatformManifestBinaryIDAttribute = MinCryptVerifySignedHash2(v48, v29, v30, (int)v16 + 272, v59 + 176, 0);
      SigningTime = PlatformManifestBinaryIDAttribute;
      if ( PlatformManifestBinaryIDAttribute < 0 )
        goto LABEL_16;
      v33 = v41;
      v34 = v44;
      if ( !v41 && !(_DWORD)v49 && !v44 && !a8 )
        goto LABEL_104;
      v41 = 0;
      v46 = 0;
      SigningTime = I_MinCryptGetSigningTime(v16, v47, v40, (unsigned int)&v50, (__int64)&v46, (__int64)&v41);
      if ( SigningTime < 0
        || v46 > 0
        && (v46 < (__int64)v52
         || v46 > *((__int64 *)&v52 + 1)
         || v46 < *(_QWORD *)(a6 + 32)
         || v46 > *(_QWORD *)(a6 + 40)) )
      {
        v46 = 0;
      }
      if ( v33 )
      {
        if ( !v46 )
          *(_DWORD *)(a6 + 8) |= 0x4000000u;
        PlatformManifestBinaryIDAttribute = MincryptIsTimestampBeforeRevocation(a6, &v46, &v50);
        SigningTime = PlatformManifestBinaryIDAttribute;
        if ( PlatformManifestBinaryIDAttribute < 0 )
          goto LABEL_104;
        *(_DWORD *)(a6 + 8) &= ~0x200000u;
      }
      if ( !a5 || (*(_DWORD *)(a5 + 4) & 0x10) == 0 )
      {
        if ( (_DWORD)v49 )
        {
          PlatformManifestBinaryIDAttribute = I_MinCryptCheckCertHashWeakCrypto(0x400000, a6, &v46, 0);
          SigningTime = PlatformManifestBinaryIDAttribute;
          if ( PlatformManifestBinaryIDAttribute < 0 )
            goto LABEL_104;
        }
        if ( v34 && (_QWORD)v51 )
        {
          LOBYTE(v35) = 1;
          PlatformManifestBinaryIDAttribute = I_MinCryptCheckCertHashWeakCrypto(0x4000000, &v50, &v46, v35);
          SigningTime = PlatformManifestBinaryIDAttribute;
          if ( PlatformManifestBinaryIDAttribute < 0 )
          {
            *(_DWORD *)(a6 + 8) |= 0x40000u;
            goto LABEL_104;
          }
          v49 = 0;
          if ( !(unsigned __int8)I_MinCryptIsHashAlgPossiblyWeak(0x4000, v41, &v49) || v46 && v46 <= v49 )
            v11 = 0;
          v41 = v11;
          SigningTime = v11;
          if ( v11 < 0 )
          {
            *(_DWORD *)(a6 + 8) |= 0x40000u;
            local_unwind_0(v60, &loc_180015D29);
            return v41;
          }
        }
      }
      PlatformManifestBinaryIDAttribute = 0;
      SigningTime = 0;
      if ( a8 )
        *a8 = v46;
      if ( a9 )
      {
        *a9 = v50;
        a9[1] = v51;
        a9[2] = v52;
        v50 = 0;
        v52 = 0;
        v51 = 0;
      }
      goto LABEL_104;
    }
    PlatformManifestBinaryIDAttribute = -1073741801;
    SigningTime = -1073741801;
LABEL_104:
    v14 = v40;
    goto LABEL_105;
  }
  PlatformManifestBinaryIDAttribute = -1073741801;
  SigningTime = -1073741801;
LABEL_105:
  if ( PlatformManifestBinaryIDAttribute < 0 )
    PlatformManifestBinaryIDAttribute = I_MinCryptBuildErrorPolicy(
                                          (unsigned int)PlatformManifestBinaryIDAttribute,
                                          a6,
                                          v12);
  if ( (_DWORD)v50 )
  {
    SIPolicyFree(v51);
    v50 = 0;
    v51 = 0;
    v52 = 0;
  }
  if ( v55 )
    SkFreePool(1, v55);
  if ( v14 )
    SkFreePool(1, v14);
  return (unsigned int)PlatformManifestBinaryIDAttribute;
}

```

## disassembly

```asm
0x180015624  mov     r11, rsp
0x180015627  mov     [r11+8], rbx
0x18001562b  mov     [r11+10h], rsi
0x18001562f  mov     [r11+20h], r9d
0x180015633  mov     [r11+18h], r8
0x180015637  push    rdi
0x180015638  push    r12
0x18001563a  push    r13
0x18001563c  push    r14
0x18001563e  push    r15
0x180015640  sub     rsp, 0E0h
0x180015647  mov     [rsp+108h+var_30], rsp
0x18001564f  mov     r12d, edx
0x180015652  mov     r13, rcx
0x180015655  mov     r15, [r11+30h]
0x180015659  mov     esi, 0C0000428h
0x18001565e  mov     [rsp+108h+var_D8], esi
0x180015662  xor     eax, eax
0x180015664  mov     [rsp+108h+var_D0], rax
0x180015669  mov     [rsp+108h+var_C0], eax
0x18001566d  mov     [r11-60h], rax
0x180015671  mov     edi, eax
0x180015673  mov     [rsp+108h+var_D4], eax
0x180015677  xorps   xmm0, xmm0
0x18001567a  movups  xmmword ptr [r11-58h], xmm0
0x18001567f  mov     [rsp+108h+var_B8], eax
0x180015683  mov     [rsp+108h+var_C8], eax
0x180015687  mov     [rsp+108h+var_B0], rax
0x18001568c  movups  [rsp+108h+var_98], xmm0
0x180015691  movups  [rsp+108h+var_88], xmm0
0x180015699  movups  xmmword ptr [r11-78h], xmm0
0x18001569e  mov     dword ptr [rsp+108h+var_A0], eax
0x1800156a2  mov     [rsp+108h+var_BC], eax
0x1800156a6  mov     [rsp+108h+var_A8], 0Ah
0x1800156ae  xor     edx, edx; Val
0x1800156b0  lea     r8d, [rax+50h]; Size
0x1800156b4  mov     rbx, [rsp+108h+arg_30]
0x1800156bc  mov     rcx, rbx; void *
0x1800156bf  call    memset_0
0x1800156c4  mov     edx, 0AD0h
0x1800156c9  mov     ecx, 1
0x1800156ce  mov     r8d, 72634943h
0x1800156d4  call    cs:__imp_SkAllocatePool
0x1800156db  nop     dword ptr [rax+rax+00h]
0x1800156e0  mov     r14, rax
0x1800156e3  mov     [rsp+108h+var_D0], rax
0x1800156e8  test    rax, rax
0x1800156eb  jnz     short loc_1800156FB
0x1800156ed  mov     ebx, 0C0000017h
0x1800156f2  mov     [rsp+108h+var_D8], ebx
0x1800156f6  jmp     loc_180015DCA
0x1800156fb  add     r14, 960h
0x180015702  mov     r8, r14
0x180015705  mov     edx, r12d
0x180015708  mov     rcx, r13
0x18001570b  call    MinAsn1ParseSignedData
0x180015710  test    eax, eax
0x180015712  jns     short loc_18001571E
0x180015714  mov     edi, 50000h
0x180015719  jmp     loc_180015DBB
0x18001571e  cmp     dword ptr [r14+20h], 9
0x180015723  jnz     loc_180015DB6
0x180015729  mov     r8d, 9; Length
0x18001572f  mov     rdx, [r14+28h]; Source2
0x180015733  lea     rcx, qword_180052018; Source1
0x18001573a  call    cs:__imp_RtlCompareMemory
0x180015741  nop     dword ptr [rax+rax+00h]
0x180015746  cmp     rax, 9
0x18001574a  jnz     loc_180015DB6
0x180015750  mov     eax, [rsp+108h+arg_18]
0x180015757  test    eax, eax
0x180015759  jz      short loc_180015781
0x18001575b  mov     rcx, [rsp+108h+arg_10]
0x180015763  test    rcx, rcx
0x180015766  jz      short loc_180015781
0x180015768  cmp     dword ptr [r14+50h], 0
0x18001576d  jz      short loc_180015778
0x18001576f  movups  xmm0, xmmword ptr [r14+50h]
0x180015774  movdqu  xmmword ptr [rbx], xmm0
0x180015778  mov     [rbx+18h], rcx
0x18001577c  mov     [rbx+10h], eax
0x18001577f  jmp     short loc_1800157C0
0x180015781  cmp     dword ptr [r14+50h], 0
0x180015786  jz      short loc_180015714
0x180015788  cmp     dword ptr [r14+60h], 0
0x18001578d  jz      short loc_180015714
0x18001578f  movups  xmm0, xmmword ptr [r14+50h]
0x180015794  movdqu  xmmword ptr [rbx], xmm0
0x180015798  lea     rdx, [rbx+10h]
0x18001579c  mov     rcx, r14
0x18001579f  call    MinAsn1SignedDataGetContent
0x1800157a4  test    eax, eax
0x1800157a6  jg      short loc_1800157B8
0x1800157a8  mov     ebx, esi
0x1800157aa  mov     [rsp+108h+var_D8], ebx
0x1800157ae  mov     edi, 40000h
0x1800157b3  jmp     loc_180015DC1
0x1800157b8  mov     [rsp+108h+var_B8], 1
0x1800157c0  cmp     dword ptr [r14+0A0h], 0
0x1800157c8  jz      loc_180015714
0x1800157ce  lea     rcx, [r14+70h]
0x1800157d2  mov     r13, [rsp+108h+var_D0]
0x1800157d7  mov     r8, r13
0x1800157da  lea     rdx, [rsp+108h+var_A8]
0x1800157df  call    MinAsn1ParseSignedDataCertificatesEx
0x1800157e4  test    eax, eax
0x1800157e6  js      short loc_180015816
0x1800157e8  mov     eax, [rsp+108h+var_A8]
0x1800157ec  test    eax, eax
0x1800157ee  jz      short loc_180015816
0x1800157f0  lea     rdx, [r14+0D0h]
0x1800157f7  lea     rcx, [r14+0C0h]
0x1800157fe  mov     r9, r13
0x180015801  mov     r8d, eax
0x180015804  call    I_MinCryptFindSignerCertificateByIssuerAndSerialNumber
0x180015809  mov     [rsp+108h+var_38], rax
0x180015811  test    rax, rax
0x180015814  jnz     short loc_180015820
0x180015816  mov     edi, 60000h
0x18001581b  jmp     loc_180015DBB
0x180015820  movups  xmm0, xmmword ptr [rax+10h]
0x180015824  movdqu  xmmword ptr [rbx+20h], xmm0
0x180015829  lea     r12, [r14+0F0h]
0x180015830  movups  xmm0, xmmword ptr [r12]
0x180015835  movdqu  xmmword ptr [rbx+30h], xmm0
0x18001583a  movups  xmm1, xmmword ptr [r14+120h]
0x180015842  movdqu  xmmword ptr [rbx+40h], xmm1
0x180015847  mov     [rsp+108h+var_E0], r12
0x18001584c  mov     [rsp+108h+var_E8], r15
0x180015851  mov     r13, [rsp+108h+arg_20]
0x180015859  mov     r9, r13
0x18001585c  mov     r8, [rsp+108h+var_D0]
0x180015861  mov     edx, [rsp+108h+var_A8]
0x180015865  mov     rcx, rax
0x180015868  call    MinCryptVerifyCertificateWithPolicy2
0x18001586d  mov     ebx, eax
0x18001586f  mov     [rsp+108h+var_D8], eax
0x180015873  test    eax, eax
0x180015875  jns     short loc_180015892
0x180015877  cmp     eax, 0C0000603h
0x18001587c  jnz     loc_180015DC5
0x180015882  mov     [rsp+108h+var_D8], 0
0x18001588a  mov     [rsp+108h+var_C8], 1
0x180015892  cmp     dword ptr [r12], 0
0x180015897  jz      short loc_1800158B2
0x180015899  mov     rdx, r15
0x18001589c  mov     rcx, r12
0x18001589f  call    I_MinCryptGetPlatformManifestBinaryIDAttribute
0x1800158a4  mov     ebx, eax
0x1800158a6  mov     [rsp+108h+var_D8], eax
0x1800158aa  test    eax, eax
0x1800158ac  js      loc_180015DC5
0x1800158b2  test    r13, r13
0x1800158b5  jz      short loc_1800158C9
0x1800158b7  mov     eax, [r13+4]
0x1800158bb  test    al, 10h
0x1800158bd  jz      short loc_1800158C9
0x1800158bf  mov     ebx, 1
0x1800158c4  jmp     loc_18001598E
0x1800158c9  cmp     qword ptr [r15+10h], 0
0x1800158ce  jz      short loc_18001592B
0x1800158d0  xor     ebx, ebx
0x1800158d2  mov     [rsp+108h+var_68], ebx
0x1800158d9  mov     rdx, [r15+10h]
0x1800158dd  cmp     ebx, [rdx+30h]
0x1800158e0  jnb     short loc_180015932
0x1800158e2  mov     eax, ebx
0x1800158e4  imul    r12, rax, 78h ; 'x'
0x1800158e8  mov     rdx, [rdx+28h]
0x1800158ec  xor     r8d, r8d
0x1800158ef  mov     edx, [rdx+r12]
0x1800158f3  mov     ecx, 400000h
0x1800158f8  call    I_MinCryptIsHashAlgPossiblyWeak
0x1800158fd  test    al, al
0x1800158ff  jz      short loc_180015927
0x180015901  mov     rax, [r15+10h]
0x180015905  mov     rcx, [rax+28h]
0x180015909  add     rcx, r12
0x18001590c  call    MincryptIsWeakCertHashAllowed
0x180015911  test    al, al
0x180015913  jnz     short loc_180015927
0x180015915  mov     ebx, 1
0x18001591a  mov     dword ptr [rsp+108h+var_A0], ebx
0x18001591e  mov     [rsp+108h+var_40], ebx
0x180015925  jmp     short loc_180015937
0x180015927  inc     ebx
0x180015929  jmp     short loc_1800158D2
0x18001592b  mov     ebx, 1
0x180015930  jmp     short loc_18001593E
0x180015932  mov     ebx, 1
0x180015937  lea     r12, [r14+0F0h]
0x18001593e  xor     r8b, r8b
0x180015941  mov     [rsp+108h+var_C4], r8b
0x180015946  mov     r9, cs:g_WeakCryptoPolicies
0x18001594d  test    r9, r9
0x180015950  jz      short loc_180015980
0x180015952  xor     edx, edx
0x180015954  mov     [rsp+108h+var_64], edx
0x18001595b  cmp     edx, [r9]
0x18001595e  jnb     short loc_180015980
0x180015960  lea     rcx, [rdx+rdx*2]
0x180015964  add     rcx, rcx
0x180015967  mov     rax, [r9+8]
0x18001596b  test    dword ptr [rax+rcx*8+4], 4014000h
0x180015973  jnz     short loc_180015979
0x180015975  add     edx, ebx
0x180015977  jmp     short loc_180015954
0x180015979  mov     r8b, bl
0x18001597c  mov     [rsp+108h+var_C4], bl
0x180015980  mov     eax, [rsp+108h+var_BC]
0x180015984  test    r8b, r8b
0x180015987  cmovnz  eax, ebx
0x18001598a  mov     [rsp+108h+var_BC], eax
0x18001598e  lea     rcx, [r14+0E0h]
0x180015995  call    MinCryptDecodeHashAlgorithmIdentifier
0x18001599a  mov     [rsp+108h+var_A4], eax
0x18001599e  test    eax, eax
0x1800159a0  jz      loc_1800157A8
0x1800159a6  lea     rcx, [r14+100h]
0x1800159ad  call    MinCryptDecodeHashAlgorithmIdentifier
0x1800159b2  mov     r13d, eax
0x1800159b5  cmp     [rsp+108h+var_B8], 0
0x1800159ba  jz      short loc_1800159E2
0x1800159bc  lea     r9, [rsp+108h+var_50]
0x1800159c4  lea     r8, [rsp+108h+var_58]
0x1800159cc  mov     edx, [r14+60h]
0x1800159d0  mov     rcx, [r14+68h]
0x1800159d4  call    MinAsn1ExtractContent
0x1800159d9  test    eax, eax
0x1800159db  jns     short loc_180015A02
0x1800159dd  jmp     loc_1800157A8
0x1800159e2  mov     r9d, [rsp+108h+arg_18]
0x1800159ea  mov     [rsp+108h+var_58], r9d
0x1800159f2  mov     rax, [rsp+108h+arg_10]
0x1800159fa  mov     [rsp+108h+var_50], rax
0x180015a02  mov     r12d, [r12]
0x180015a06  mov     [rsp+108h+var_B8], r12d
0x180015a0b  cmp     r13d, 8000h
0x180015a12  jnz     short loc_180015A36
0x180015a14  test    r12d, r12d
0x180015a17  jnz     short loc_180015A36
0x180015a19  mov     rcx, [rsp+108h+var_50]
0x180015a21  mov     [rsp+108h+var_48], rcx
0x180015a29  mov     r8d, [rsp+108h+var_58]
0x180015a31  jmp     loc_180015B33
0x180015a36  lea     rax, [rsp+108h+var_C0]
0x180015a3b  mov     [rsp+108h+var_E8], rax
0x180015a40  lea     r9, [r14+130h]
0x180015a47  lea     r8, [rsp+108h+var_58]
0x180015a4f  mov     edx, ebx
0x180015a51  mov     ecx, [rsp+108h+var_A4]
0x180015a55  call    HashpHashMemory
0x180015a5a  mov     ebx, eax
0x180015a5c  mov     [rsp+108h+var_D8], eax
0x180015a60  test    eax, eax
0x180015a62  js      loc_1800157AE
0x180015a68  lea     rcx, [r14+130h]
0x180015a6f  mov     [rsp+108h+var_48], rcx
0x180015a77  test    r12d, r12d
0x180015a7a  jz      loc_180015B2E
0x180015a80  cmp     r13d, 8000h
0x180015a87  jz      short loc_180015AB3
0x180015a89  lea     r9, [r14+0F0h]
0x180015a90  lea     r8, [rsp+108h+var_C0]
0x180015a95  mov     rdx, rcx
0x180015a98  mov     ecx, [rsp+108h+var_A4]
0x180015a9c  call    I_MinCryptVerifySignerAuthenticatedAttributes
0x180015aa1  mov     [rsp+108h+var_D8], eax
0x180015aa5  mov     r8d, [rsp+108h+var_C0]
0x180015aaa  lea     rcx, [r14+130h]
0x180015ab1  jmp     short loc_180015B23
0x180015ab3  mov     rdx, r12
0x180015ab6  mov     ecx, 1
0x180015abb  mov     r8d, 72634943h
0x180015ac1  call    cs:__imp_SkAllocatePool
0x180015ac8  nop     dword ptr [rax+rax+00h]
0x180015acd  mov     r12, rax
0x180015ad0  mov     [rsp+108h+var_60], rax
0x180015ad8  test    rax, rax
0x180015adb  jnz     short loc_180015AEB
0x180015add  mov     ebx, 0C0000017h
0x180015ae2  mov     [rsp+108h+var_D8], ebx
0x180015ae6  jmp     loc_180015DC5
0x180015aeb  lea     rax, [r14+0F0h]
0x180015af2  mov     [rsp+108h+var_E8], rax
0x180015af7  lea     r9, [rsp+108h+var_B8]
0x180015afc  mov     r8, r12
0x180015aff  mov     edx, [rsp+108h+var_C0]
0x180015b03  lea     rcx, [r14+130h]
0x180015b0a  call    I_MinCryptVerifyReturnSignerAuthenticatedAttributes
0x180015b0f  mov     [rsp+108h+var_D8], eax
0x180015b13  mov     rcx, r12
0x180015b16  mov     [rsp+108h+var_48], rcx
0x180015b1e  mov     r8d, [rsp+108h+var_B8]
0x180015b23  mov     ebx, eax
0x180015b25  test    eax, eax
0x180015b27  jns     short loc_180015B33
0x180015b29  jmp     loc_1800157AE
0x180015b2e  mov     r8d, [rsp+108h+var_C0]
0x180015b33  mov     rax, [rsp+108h+var_38]
  ... truncated ...
```
