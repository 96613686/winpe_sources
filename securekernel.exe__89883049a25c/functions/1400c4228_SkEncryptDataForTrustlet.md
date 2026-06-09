# SkEncryptDataForTrustlet

- ea: `0x1400c4228`
- end: `0x1400c46f0`
- name: `SkEncryptDataForTrustlet`
- size: `1224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400c30f0`

## callees

- `0x14007f5bc`
- `0x1400c2394`
- `0x1400c4228`
- `0x1400f3620`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400c44c8`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400c44c8`
- `cng!BCryptGenRandom` at `0x1400c43e7`
- `cng!BCryptGenRandom` at `0x1400c43e7`
- `cng!BCryptGenerateSymmetricKey` at `0x1400c453e`
- `cng!BCryptGenerateSymmetricKey` at `0x1400c453e`
- `cng!BCryptEncrypt` at `0x1400c4470`
- `cng!BCryptEncrypt` at `0x1400c45f1`
- `cng!BCryptEncrypt` at `0x1400c4470`
- `cng!BCryptEncrypt` at `0x1400c45f1`
- `cng!BCryptDestroyKey` at `0x1400c4651`
- `cng!BCryptDestroyKey` at `0x1400c467f`
- `cng!BCryptDestroyKey` at `0x1400c4651`
- `cng!BCryptDestroyKey` at `0x1400c467f`
- `cng!BCryptSetProperty` at `0x1400c44ff`
- `cng!BCryptSetProperty` at `0x1400c44ff`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c4669`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c4697`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c4669`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400c4697`

## pseudocode

```c
__int64 __fastcall SkEncryptDataForTrustlet(
        UCHAR *a1,
        ULONGLONG a2,
        __int64 a3,
        _BYTE *a4,
        unsigned __int64 ullOperand,
        __int64 *a6)
{
  _QWORD *StackBase; // rax
  _DWORD *v11; // rax
  int inited; // ebx
  ULONG v14; // r13d
  ULONG v15; // eax
  ULONG v16; // eax
  __int64 v17; // r14
  ULONG v18; // esi
  ULONG v19; // eax
  __int64 i; // rax
  ULONG pcbResult; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v22; // [rsp+54h] [rbp-ACh] BYREF
  ULONG pulResult; // [rsp+58h] [rbp-A8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-A0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-98h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp-88h] BYREF
  PUCHAR pbInput; // [rsp+80h] [rbp-80h]
  _QWORD pPaddingInfo[3]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v30[2]; // [rsp+A0h] [rbp-60h] BYREF
  PUCHAR pbIV; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  int v34; // [rsp+C0h] [rbp-40h]
  _BYTE *v35; // [rsp+C8h] [rbp-38h]
  int v36; // [rsp+D0h] [rbp-30h]
  UCHAR pbBuffer[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v38; // [rsp+110h] [rbp+10h]

  pbInput = a1;
  pulResult = 0;
  v22 = 0;
  hAlgorithm = 0;
  phAlgorithm = 0;
  hKey = 0;
  phKey = 0;
  pPaddingInfo[0] = L"SHA256";
  *(_OWORD *)pbBuffer = 0;
  pPaddingInfo[1] = 0;
  v38 = 0;
  pPaddingInfo[2] = 0;
  pcbResult = 0;
  memset_0(v30, 0, 0x58u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v11 = (_DWORD *)StackBase[10];
    if ( v11 )
    {
      if ( (*v11 & 0x200) != 0 )
      {
        if ( !a1 && a4 || !a6 )
          return 3221225485LL;
        inited = RtlULongLongToULong(a2, &pulResult);
        if ( inited < 0 )
          return (unsigned int)inited;
        inited = RtlULongLongToULong(ullOperand, &v22);
        if ( inited < 0 )
          return (unsigned int)inited;
        v14 = pulResult;
        v15 = pulResult + 402;
        if ( pulResult >= 0xFFFFFE6E )
          return (unsigned int)-1073741675;
        *a6 = v15;
        if ( !a4 || ullOperand < v15 )
          return (unsigned int)-1073741789;
        if ( !a3 )
          return (unsigned int)-1073741811;
        *(_DWORD *)a4 = v15;
        *((_DWORD *)a4 + 1) = 33619969;
        *((_WORD *)a4 + 4) = 514;
        *(_OWORD *)(a4 + 10) = *(_OWORD *)a3;
        *(_OWORD *)(a4 + 26) = *(_OWORD *)(a3 + 16);
        *(_OWORD *)(a4 + 42) = *(_OWORD *)(a3 + 32);
        *(_QWORD *)(a4 + 58) = *(_QWORD *)(a3 + 48);
        *(_QWORD *)(a4 + 74) = 0;
        inited = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
        if ( inited < 0 || (inited = SkpInitIdkEncryption(IumIdkHandle, &hAlgorithm, &hKey), inited < 0) )
        {
LABEL_32:
          if ( phKey )
            BCryptDestroyKey(phKey);
          if ( phAlgorithm )
            BCryptCloseAlgorithmProvider(phAlgorithm, 0);
          if ( hKey )
            BCryptDestroyKey(hKey);
          if ( hAlgorithm )
            BCryptCloseAlgorithmProvider(hAlgorithm, 0);
          return (unsigned int)inited;
        }
        pcbResult = 0;
        inited = BCryptEncrypt(hKey, pbBuffer, 0x20u, pPaddingInfo, 0, 0, a4 + 98, v22 - 98, &pcbResult, 4u);
        if ( inited < 0 )
          goto LABEL_30;
        v16 = pcbResult + 98;
        if ( pcbResult < 0xFFFFFF9E )
        {
          v17 = pcbResult + 16;
          if ( (unsigned int)v17 >= pcbResult )
          {
            v18 = pcbResult + 146;
            *(_DWORD *)(a4 + 82) = v17;
            *(_DWORD *)(a4 + 66) = v17;
            if ( v16 + 48 < v16 )
            {
LABEL_29:
              inited = -1073741675;
              goto LABEL_30;
            }
            inited = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
            if ( inited >= 0 )
            {
              inited = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
              if ( inited >= 0 )
              {
                inited = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbBuffer, 0x20u, 0);
                if ( inited >= 0 )
                {
                  memset_0(v30, 0, 0x58u);
                  v32 = 12;
                  v35 = &a4[v17 + 98];
                  pbIV = &a4[v17 + 114];
                  v30[0] = 88;
                  v30[1] = 1;
                  v33 = a3;
                  v34 = 56;
                  v36 = 16;
                  pcbResult = 0;
                  inited = BCryptEncrypt(phKey, pbInput, v14, v30, pbIV, 0xCu, &a4[v17 + 130], v22 - v18, &pcbResult, 0);
                  if ( inited >= 0 )
                  {
                    if ( v18 + pcbResult >= v18 )
                    {
                      v19 = pcbResult + 48;
                      if ( pcbResult + 48 >= pcbResult )
                      {
                        *(_DWORD *)&a4[v17 + 82] = v19;
                        inited = 0;
                        *(_DWORD *)(a4 + 70) = v19;
                        goto LABEL_32;
                      }
                      *(_DWORD *)&a4[v17 + 82] = -1;
                    }
                    goto LABEL_29;
                  }
                }
              }
            }
LABEL_30:
            for ( i = *a6; i; --i )
              *a4++ = 0;
            goto LABEL_32;
          }
          *(_DWORD *)(a4 + 82) = -1;
        }
        inited = -1073741675;
        goto LABEL_30;
      }
    }
  }
  return 3221225659LL;
}

```

## disassembly

```asm
0x1400c4228  mov     [rsp-8+arg_8], rbx
0x1400c422d  push    rbp
0x1400c422e  push    rsi
0x1400c422f  push    rdi
0x1400c4230  push    r12
0x1400c4232  push    r13
0x1400c4234  push    r14
0x1400c4236  push    r15
0x1400c4238  lea     rbp, [rsp-30h]
0x1400c423d  sub     rsp, 130h
0x1400c4244  mov     rax, cs:__security_cookie
0x1400c424b  xor     rax, rsp
0x1400c424e  mov     [rbp+60h+var_40], rax
0x1400c4252  mov     r15, [rbp+60h+arg_28]
0x1400c4259  lea     rax, pszAlgId; "SHA256"
0x1400c4260  xorps   xmm0, xmm0
0x1400c4263  mov     [rbp+60h+pbInput], rcx
0x1400c4267  mov     rbx, rdx
0x1400c426a  mov     [rsp+160h+pulResult], 0
0x1400c4272  xor     edx, edx; Val
0x1400c4274  mov     [rsp+160h+var_10C], 0
0x1400c427c  mov     r12, r8
0x1400c427f  mov     [rsp+160h+hAlgorithm], 0
0x1400c4288  mov     rsi, rcx
0x1400c428b  mov     [rsp+160h+phAlgorithm], 0
0x1400c4294  lea     rcx, [rbp+60h+var_C0]; void *
0x1400c4298  mov     [rsp+160h+hKey], 0
0x1400c42a1  lea     r8d, [rdx+58h]; Size
0x1400c42a5  mov     [rsp+160h+phKey], 0
0x1400c42ae  mov     rdi, r9
0x1400c42b1  mov     [rbp+60h+pPaddingInfo], rax
0x1400c42b5  movups  xmmword ptr [rbp+60h+pbBuffer], xmm0
0x1400c42b9  mov     [rbp+60h+var_D0], 0
0x1400c42c1  movups  [rbp+60h+var_50], xmm0
0x1400c42c5  mov     [rbp+60h+var_C8], 0
0x1400c42cd  mov     [rsp+160h+var_110], 0
0x1400c42d5  call    memset_0
0x1400c42da  mov     rax, gs:8
0x1400c42e3  test    rax, rax
0x1400c42e6  jz      loc_1400C46C3
0x1400c42ec  mov     rax, [rax+50h]
0x1400c42f0  test    rax, rax
0x1400c42f3  jz      loc_1400C46C3
0x1400c42f9  test    dword ptr [rax], 200h
0x1400c42ff  jz      loc_1400C46C3
0x1400c4305  test    rsi, rsi
0x1400c4308  jnz     short loc_1400C430F
0x1400c430a  test    rdi, rdi
0x1400c430d  jnz     short loc_1400C4314
0x1400c430f  test    r15, r15
0x1400c4312  jnz     short loc_1400C431E
0x1400c4314  mov     eax, 0C000000Dh
0x1400c4319  jmp     loc_1400C46C8
0x1400c431e  lea     rdx, [rsp+160h+pulResult]; pulResult
0x1400c4323  mov     rcx, rbx; ullOperand
0x1400c4326  call    RtlULongLongToULong
0x1400c432b  mov     ebx, eax
0x1400c432d  test    eax, eax
0x1400c432f  js      loc_1400C46BF
0x1400c4335  mov     rcx, [rbp+60h+ullOperand]; ullOperand
0x1400c433c  lea     rdx, [rsp+160h+var_10C]; pulResult
0x1400c4341  call    RtlULongLongToULong
0x1400c4346  mov     ebx, eax
0x1400c4348  test    eax, eax
0x1400c434a  js      loc_1400C46BF
0x1400c4350  mov     r13d, [rsp+160h+pulResult]
0x1400c4355  lea     eax, [r13+192h]
0x1400c435c  cmp     eax, 192h
0x1400c4361  jb      loc_1400C46BA
0x1400c4367  mov     ecx, eax
0x1400c4369  mov     [r15], rcx
0x1400c436c  test    rdi, rdi
0x1400c436f  jz      loc_1400C46B3
0x1400c4375  cmp     [rbp+60h+ullOperand], rcx
0x1400c437c  jb      loc_1400C46B3
0x1400c4382  test    r12, r12
0x1400c4385  jnz     short loc_1400C4391
0x1400c4387  mov     ebx, 0C000000Dh
0x1400c438c  jmp     loc_1400C46BF
0x1400c4391  mov     [rdi], eax
0x1400c4393  lea     rdx, [rbp+60h+pbBuffer]; pbBuffer
0x1400c4397  mov     dword ptr [rdi+4], 2010001h
0x1400c439e  mov     esi, 1
0x1400c43a3  mov     word ptr [rdi+8], 202h
0x1400c43a9  xor     ecx, ecx; hAlgorithm
0x1400c43ab  movups  xmm0, xmmword ptr [r12]
0x1400c43b0  lea     r14d, [rsi+1Fh]
0x1400c43b4  movups  xmmword ptr [rdi+0Ah], xmm0
0x1400c43b8  lea     r9d, [rsi+1]; dwFlags
0x1400c43bc  mov     r8d, r14d; cbBuffer
0x1400c43bf  movups  xmm1, xmmword ptr [r12+10h]
0x1400c43c5  movups  xmmword ptr [rdi+1Ah], xmm1
0x1400c43c9  movups  xmm0, xmmword ptr [r12+20h]
0x1400c43cf  movups  xmmword ptr [rdi+2Ah], xmm0
0x1400c43d3  movsd   xmm1, qword ptr [r12+30h]
0x1400c43da  movsd   qword ptr [rdi+3Ah], xmm1
0x1400c43df  mov     qword ptr [rdi+4Ah], 0
0x1400c43e7  call    cs:__imp_BCryptGenRandom
0x1400c43ee  nop     dword ptr [rax+rax+00h]
0x1400c43f3  mov     ebx, eax
0x1400c43f5  test    eax, eax
0x1400c43f7  js      loc_1400C4647
0x1400c43fd  mov     rcx, cs:IumIdkHandle
0x1400c4404  lea     r8, [rsp+160h+hKey]
0x1400c4409  lea     rdx, [rsp+160h+hAlgorithm]
0x1400c440e  call    SkpInitIdkEncryption
0x1400c4413  mov     ebx, eax
0x1400c4415  test    eax, eax
0x1400c4417  js      loc_1400C4647
0x1400c441d  mov     eax, [rsp+160h+var_10C]
0x1400c4421  lea     rdx, [rsp+160h+var_110]
0x1400c4426  mov     [rsp+160h+dwFlags], 4; dwFlags
0x1400c442e  lea     rcx, [rdi+62h]
0x1400c4432  mov     [rsp+160h+pcbResult], rdx; pcbResult
0x1400c4437  lea     r9, [rbp+60h+pPaddingInfo]; pPaddingInfo
0x1400c443b  mov     [rsp+160h+var_10C], eax
0x1400c443f  lea     rdx, [rbp+60h+pbBuffer]; pbInput
0x1400c4443  add     eax, 0FFFFFF9Eh
0x1400c4446  mov     [rsp+160h+var_110], 0
0x1400c444e  mov     [rsp+160h+cbOutput], eax; cbOutput
0x1400c4452  mov     r8d, r14d; cbInput
0x1400c4455  mov     [rsp+160h+pbOutput], rcx; pbOutput
0x1400c445a  mov     rcx, [rsp+160h+hKey]; hKey
0x1400c445f  mov     [rsp+160h+cbIV], 0; cbIV
0x1400c4467  mov     [rsp+160h+pbIV], 0; pbIV
0x1400c4470  call    cs:__imp_BCryptEncrypt
0x1400c4477  nop     dword ptr [rax+rax+00h]
0x1400c447c  mov     ebx, eax
0x1400c447e  test    eax, eax
0x1400c4480  js      loc_1400C4634
0x1400c4486  mov     ecx, [rsp+160h+var_110]
0x1400c448a  lea     eax, [rcx+62h]
0x1400c448d  cmp     eax, 62h ; 'b'
0x1400c4490  jb      loc_1400C46AC
0x1400c4496  lea     r14d, [rcx+10h]
0x1400c449a  cmp     r14d, ecx
0x1400c449d  jb      loc_1400C46A5
0x1400c44a3  lea     esi, [rax+30h]
0x1400c44a6  mov     [rdi+52h], r14d
0x1400c44aa  mov     [rdi+42h], r14d
0x1400c44ae  cmp     esi, eax
0x1400c44b0  jb      loc_1400C462A
0x1400c44b6  xor     r9d, r9d; dwFlags
0x1400c44b9  lea     rdx, aAes; "AES"
0x1400c44c0  xor     r8d, r8d; pszImplementation
0x1400c44c3  lea     rcx, [rsp+160h+phAlgorithm]; phAlgorithm
0x1400c44c8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400c44cf  nop     dword ptr [rax+rax+00h]
0x1400c44d4  mov     ebx, eax
0x1400c44d6  test    eax, eax
0x1400c44d8  js      loc_1400C462F
0x1400c44de  mov     rcx, [rsp+160h+phAlgorithm]; hObject
0x1400c44e3  lea     r8, pbInput; "ChainingModeGCM"
0x1400c44ea  mov     r9d, 20h ; ' '; cbInput
0x1400c44f0  mov     dword ptr [rsp+160h+pbIV], 0; dwFlags
0x1400c44f8  lea     rdx, aChainingmode; "ChainingMode"
0x1400c44ff  call    cs:__imp_BCryptSetProperty
0x1400c4506  nop     dword ptr [rax+rax+00h]
0x1400c450b  mov     ebx, eax
0x1400c450d  test    eax, eax
0x1400c450f  js      loc_1400C462F
0x1400c4515  mov     rcx, [rsp+160h+phAlgorithm]; hAlgorithm
0x1400c451a  lea     rax, [rbp+60h+pbBuffer]
0x1400c451e  mov     dword ptr [rsp+160h+pbOutput], 0; dwFlags
0x1400c4526  lea     rdx, [rsp+160h+phKey]; phKey
0x1400c452b  mov     [rsp+160h+cbIV], 20h ; ' '; cbSecret
0x1400c4533  xor     r9d, r9d; cbKeyObject
0x1400c4536  xor     r8d, r8d; pbKeyObject
0x1400c4539  mov     [rsp+160h+pbIV], rax; pbSecret
0x1400c453e  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400c4545  nop     dword ptr [rax+rax+00h]
0x1400c454a  mov     ebx, eax
0x1400c454c  test    eax, eax
0x1400c454e  js      loc_1400C462F
0x1400c4554  mov     ebx, 58h ; 'X'
0x1400c4559  lea     rcx, [rbp+60h+var_C0]; void *
0x1400c455d  mov     r8d, ebx; Size
0x1400c4560  xor     edx, edx; Val
0x1400c4562  call    memset_0
0x1400c4567  mov     r8d, [rsp+160h+var_10C]
0x1400c456c  lea     r9d, [rbx-4Ch]
0x1400c4570  mov     [rsp+160h+dwFlags], 0; dwFlags
0x1400c4578  lea     rdx, [rsp+160h+var_110]
0x1400c457d  mov     [rsp+160h+pcbResult], rdx; pcbResult
0x1400c4582  lea     rax, [rdi+62h]
0x1400c4586  mov     rdx, [rbp+60h+pbInput]; pbInput
0x1400c458a  lea     rcx, [rdi+72h]
0x1400c458e  add     rax, r14
0x1400c4591  mov     [rbp+60h+var_B0], r9d
0x1400c4595  add     rcx, r14
0x1400c4598  mov     [rbp+60h+var_98], rax
0x1400c459c  sub     r8d, esi
0x1400c459f  mov     [rbp+60h+var_B8], rcx
0x1400c45a3  mov     [rsp+160h+cbOutput], r8d; cbOutput
0x1400c45a8  lea     rax, [rdi+82h]
0x1400c45af  add     rax, r14
0x1400c45b2  mov     [rbp+60h+var_C0], ebx
0x1400c45b5  mov     [rsp+160h+pbOutput], rax; pbOutput
0x1400c45ba  mov     r8d, r13d; cbInput
0x1400c45bd  mov     [rsp+160h+cbIV], r9d; cbIV
0x1400c45c2  lea     r9, [rbp+60h+var_C0]; pPaddingInfo
0x1400c45c6  mov     [rsp+160h+pbIV], rcx; pbIV
0x1400c45cb  mov     rcx, [rsp+160h+phKey]; hKey
0x1400c45d0  mov     [rbp+60h+var_BC], 1
0x1400c45d7  mov     [rbp+60h+var_A8], r12
0x1400c45db  mov     [rbp+60h+var_A0], 38h ; '8'
0x1400c45e2  mov     [rbp+60h+var_90], 10h
0x1400c45e9  mov     [rsp+160h+var_110], 0
0x1400c45f1  call    cs:__imp_BCryptEncrypt
0x1400c45f8  nop     dword ptr [rax+rax+00h]
0x1400c45fd  mov     ebx, eax
0x1400c45ff  test    eax, eax
0x1400c4601  js      short loc_1400C462F
0x1400c4603  mov     ecx, [rsp+160h+var_110]
0x1400c4607  lea     eax, [rsi+rcx]
0x1400c460a  cmp     eax, esi
0x1400c460c  jb      short loc_1400C462A
0x1400c460e  lea     eax, [rcx+30h]
0x1400c4611  cmp     eax, ecx
0x1400c4613  jb      short loc_1400C4621
0x1400c4615  mov     [r14+rdi+52h], eax
0x1400c461a  xor     ebx, ebx
0x1400c461c  mov     [rdi+46h], eax
0x1400c461f  jmp     short loc_1400C4647
0x1400c4621  mov     dword ptr [r14+rdi+52h], 0FFFFFFFFh
0x1400c462a  mov     ebx, 0C0000095h
0x1400c462f  mov     esi, 1
0x1400c4634  mov     rax, [r15]
0x1400c4637  test    rax, rax
0x1400c463a  jz      short loc_1400C4647
0x1400c463c  mov     byte ptr [rdi], 0
0x1400c463f  add     rdi, rsi
0x1400c4642  sub     rax, rsi
0x1400c4645  jnz     short loc_1400C463C
0x1400c4647  mov     rcx, [rsp+160h+phKey]; hKey
0x1400c464c  test    rcx, rcx
0x1400c464f  jz      short loc_1400C465D
0x1400c4651  call    cs:__imp_BCryptDestroyKey
0x1400c4658  nop     dword ptr [rax+rax+00h]
0x1400c465d  mov     rcx, [rsp+160h+phAlgorithm]; hAlgorithm
0x1400c4662  test    rcx, rcx
0x1400c4665  jz      short loc_1400C4675
0x1400c4667  xor     edx, edx; dwFlags
0x1400c4669  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c4670  nop     dword ptr [rax+rax+00h]
0x1400c4675  mov     rcx, [rsp+160h+hKey]; hKey
0x1400c467a  test    rcx, rcx
0x1400c467d  jz      short loc_1400C468B
0x1400c467f  call    cs:__imp_BCryptDestroyKey
0x1400c4686  nop     dword ptr [rax+rax+00h]
0x1400c468b  mov     rcx, [rsp+160h+hAlgorithm]; hAlgorithm
0x1400c4690  test    rcx, rcx
0x1400c4693  jz      short loc_1400C46BF
0x1400c4695  xor     edx, edx; dwFlags
0x1400c4697  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400c469e  nop     dword ptr [rax+rax+00h]
0x1400c46a3  jmp     short loc_1400C46BF
0x1400c46a5  mov     dword ptr [rdi+52h], 0FFFFFFFFh
0x1400c46ac  mov     ebx, 0C0000095h
0x1400c46b1  jmp     short loc_1400C4634
0x1400c46b3  mov     ebx, 0C0000023h
0x1400c46b8  jmp     short loc_1400C46BF
0x1400c46ba  mov     ebx, 0C0000095h
0x1400c46bf  mov     eax, ebx
0x1400c46c1  jmp     short loc_1400C46C8
0x1400c46c3  mov     eax, 0C00000BBh
0x1400c46c8  mov     rcx, [rbp+60h+var_40]
0x1400c46cc  xor     rcx, rsp; StackCookie
0x1400c46cf  call    __security_check_cookie
0x1400c46d4  mov     rbx, [rsp+160h+arg_8]
0x1400c46dc  add     rsp, 130h
0x1400c46e3  pop     r15
0x1400c46e5  pop     r14
0x1400c46e7  pop     r13
0x1400c46e9  pop     r12
0x1400c46eb  pop     rdi
0x1400c46ec  pop     rsi
0x1400c46ed  pop     rbp
0x1400c46ee  retn
```
