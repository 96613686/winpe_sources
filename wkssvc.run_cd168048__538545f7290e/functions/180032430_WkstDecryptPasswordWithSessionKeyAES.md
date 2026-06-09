# WkstDecryptPasswordWithSessionKeyAES

- ea: `0x180032430`
- end: `0x18003273f`
- name: `WkstDecryptPasswordWithSessionKeyAES`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800282dc`

## callees

- `0x180007cd4`
- `0x18001fbd0`
- `0x1800321b4`
- `0x180032430`
- `0x180032748`
- `0x180032944`
- `0x180036185`
- `0x180036191`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032709`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800326fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032709`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003250f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003250f`

## pseudocode

```c
__int64 __fastcall WkstDecryptPasswordWithSessionKeyAES(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v4; // r12
  void *v5; // r15
  void *v6; // r14
  __int64 v7; // rsi
  NTSTATUS HMACWithSHA512; // edi
  __int64 v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  size_t v14; // rbx
  void *v15; // rax
  _QWORD *v16; // r13
  _BYTE *v17; // rax
  __int64 v18; // rcx
  ULONG cbInput; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+44h] [rbp-BCh] BYREF
  ULONG cbSecret[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  void *Buf1; // [rsp+70h] [rbp-90h] BYREF
  void *v27; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v29; // [rsp+90h] [rbp-70h]
  char v30[56]; // [rsp+98h] [rbp-68h] BYREF
  char v31[64]; // [rsp+D0h] [rbp-30h] BYREF

  v29 = a3;
  strcpy(v31, "Microsoft WKST encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  phAlgorithm = 0;
  hMem[0] = 0;
  v21 = 0;
  v4 = 0;
  v27 = 0;
  v5 = 0;
  cbInput = 0;
  v6 = 0;
  Buf1 = 0;
  v7 = 0;
  strcpy(v30, "Microsoft WKST MAC key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v25 = 0;
  cbSecret[0] = 0;
  v24 = 0;
  cbSecret[1] = 0;
  HMACWithSHA512 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 8u);
  if ( HMACWithSHA512 >= 0 )
  {
    HMACWithSHA512 = WkstGenerateHMACWithSHA512(phAlgorithm, 0x37u, (__int64)hMem, (__int64)&v21);
    if ( HMACWithSHA512 >= 0 )
    {
      v10 = WkstWriteAuthInfoDataToHMAC(a2 + 64, v9, *(_QWORD *)(a2 + 88), *(unsigned int *)(a2 + 80), &v27, &cbInput);
      v4 = v27;
      HMACWithSHA512 = v10;
      if ( v10 >= 0 )
      {
        v11 = WkstGenerateHMACWithSHA512(phAlgorithm, cbInput, (__int64)&Buf1, (__int64)&v21 + 4);
        v5 = Buf1;
        HMACWithSHA512 = v11;
        if ( v11 >= 0 )
        {
          if ( memcmp_0(Buf1, (const void *)a2, HIDWORD(v21)) )
          {
LABEL_6:
            HMACWithSHA512 = -1073741811;
            goto LABEL_14;
          }
          v12 = WkstGenerateHMACWithSHA512(phAlgorithm, 0x3Eu, (__int64)&v25, (__int64)cbSecret);
          v6 = (void *)v25;
          HMACWithSHA512 = v12;
          if ( v12 >= 0 )
          {
            v13 = WkstDecryptDataWithAES(
                    *(PUCHAR *)(a2 + 88),
                    *(_DWORD *)(a2 + 80),
                    (PUCHAR)(a2 + 64),
                    v25,
                    cbSecret[0],
                    (__int64)&v24,
                    (__int64)&cbSecret[1]);
            v7 = v24;
            HMACWithSHA512 = v13;
            if ( v13 >= 0 )
            {
              v14 = *(unsigned int *)v24;
              if ( (v14 & 1) != 0 )
                goto LABEL_6;
              v15 = (void *)NetpMemoryAllocate((unsigned int)(v14 + 2));
              v16 = v29;
              *v29 = v15;
              if ( v15 )
              {
                memcpy_0(v15, (const void *)(v7 + 4), v14);
                *(_WORD *)(*v16 + 2 * (v14 >> 1)) = 0;
                v17 = (_BYTE *)v7;
                v18 = cbSecret[1];
                if ( cbSecret[1] )
                {
                  do
                  {
                    *v17++ = 0;
                    --v18;
                  }
                  while ( v18 );
                }
              }
              else
              {
                HMACWithSHA512 = 8;
              }
            }
          }
        }
      }
    }
  }
LABEL_14:
  LocalFree(hMem[0]);
  LocalFree(v6);
  LocalFree(v5);
  LocalFree(v4);
  LocalFree((HLOCAL)v7);
  return (unsigned int)HMACWithSHA512;
}

```

## disassembly

```asm
0x180032430  mov     [rsp-8+arg_18], rbx
0x180032435  push    rbp
0x180032436  push    rsi
0x180032437  push    rdi
0x180032438  push    r12
0x18003243a  push    r13
0x18003243c  push    r14
0x18003243e  push    r15
0x180032440  lea     rbp, [rsp-20h]
0x180032445  sub     rsp, 120h
0x18003244c  mov     rax, cs:__security_cookie
0x180032453  xor     rax, rsp
0x180032456  mov     [rbp+50h+var_40], rax
0x18003245a  movups  xmm0, xmmword ptr cs:aMicrosoftWkstE; "Microsoft WKST encryption key AEAD-AES-"...
0x180032461  xor     eax, eax
0x180032463  mov     [rbp+50h+var_C0], r8
0x180032467  movups  xmm1, xmmword ptr cs:aMicrosoftWkstE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x18003246e  mov     rbx, rdx
0x180032471  mov     r13, rcx
0x180032474  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x180032478  lea     r9d, [rax+8]; dwFlags
0x18003247c  xor     r8d, r8d; pszImplementation
0x18003247f  movups  xmm0, xmmword ptr cs:aMicrosoftWkstE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x180032486  lea     rdx, aSha512; "SHA512"
0x18003248d  mov     [rsp+150h+phAlgorithm], rax
0x180032492  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x180032496  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x18003249b  mov     [rbp+50h+hMem], rax
0x18003249f  movups  xmm1, xmmword ptr cs:aMicrosoftWkstE+2Eh; "-HMAC-SHA512 16"
0x1800324a6  mov     dword ptr [rsp+150h+var_10C], eax
0x1800324aa  mov     r12d, eax
0x1800324ad  movups  xmmword ptr [rbp+50h+var_80+20h], xmm0
0x1800324b1  mov     [rsp+150h+var_D8], rax
0x1800324b6  mov     r15d, eax
0x1800324b9  movups  xmm0, xmmword ptr cs:aMicrosoftWkstM; "Microsoft WKST MAC key AEAD-AES-256-CBC"...
0x1800324c0  mov     [rsp+150h+var_110], eax
0x1800324c4  mov     r14d, eax
0x1800324c7  movups  xmmword ptr [rbp+50h+var_80+2Eh], xmm1
0x1800324cb  mov     [rsp+150h+Buf1], rax
0x1800324d0  mov     esi, eax
0x1800324d2  movups  xmm1, xmmword ptr cs:aMicrosoftWkstM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x1800324d9  mov     dword ptr [rsp+150h+var_10C+4], eax
0x1800324dd  movups  xmmword ptr [rbp+50h+var_B8], xmm0
0x1800324e1  mov     [rsp+150h+var_E8], rax
0x1800324e6  movups  xmm0, xmmword ptr cs:aMicrosoftWkstM+20h; "256-CBC-HMAC-SHA512 16"
0x1800324ed  mov     [rsp+150h+var_104], eax
0x1800324f1  movups  xmmword ptr [rbp+50h+var_B8+10h], xmm1
0x1800324f5  mov     [rsp+150h+var_F0], rax
0x1800324fa  movsd   xmm1, qword ptr cs:aMicrosoftWkstM+2Fh; "A512 16"
0x180032502  movups  xmmword ptr [rbp+50h+var_B8+20h], xmm0
0x180032506  mov     [rsp+150h+var_104+4], eax
0x18003250a  movsd   qword ptr [rbp+50h+var_B8+2Fh], xmm1
0x18003250f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180032516  nop     dword ptr [rax+rax+00h]
0x18003251b  mov     edi, eax
0x18003251d  test    eax, eax
0x18003251f  js      loc_1800326C9
0x180032525  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18003252a  lea     rax, [rsp+150h+var_10C]
0x18003252f  mov     [rsp+150h+var_120], rax; __int64
0x180032534  lea     r9, [rbp+50h+var_B8]
0x180032538  lea     rax, [rbp+50h+hMem]
0x18003253c  mov     rdx, r13
0x18003253f  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x180032544  lea     r8d, [rsi+10h]
0x180032548  mov     [rsp+150h+cbInput], 37h ; '7'; cbInput
0x180032550  call    WkstGenerateHMACWithSHA512
0x180032555  mov     edi, eax
0x180032557  test    eax, eax
0x180032559  js      loc_1800326C9
0x18003255f  mov     r9d, [rbx+50h]
0x180032563  lea     rax, [rsp+150h+var_110]
0x180032568  mov     r8, [rbx+58h]
0x18003256c  lea     rcx, [rbx+40h]
0x180032570  mov     qword ptr [rsp+150h+cbSecret], rax
0x180032575  lea     rax, [rsp+150h+var_D8]
0x18003257a  mov     qword ptr [rsp+150h+cbInput], rax
0x18003257f  call    WkstWriteAuthInfoDataToHMAC
0x180032584  mov     r12, [rsp+150h+var_D8]
0x180032589  mov     edi, eax
0x18003258b  test    eax, eax
0x18003258d  js      loc_1800326C9
0x180032593  mov     r8d, dword ptr [rsp+150h+var_10C]
0x180032598  lea     rax, [rsp+150h+var_10C+4]
0x18003259d  mov     rdx, [rbp+50h+hMem]
0x1800325a1  mov     r9, r12
0x1800325a4  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x1800325a9  mov     [rsp+150h+var_120], rax; __int64
0x1800325ae  lea     rax, [rsp+150h+Buf1]
0x1800325b3  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x1800325b8  mov     eax, [rsp+150h+var_110]
0x1800325bc  mov     [rsp+150h+cbInput], eax; cbInput
0x1800325c0  call    WkstGenerateHMACWithSHA512
0x1800325c5  mov     r15, [rsp+150h+Buf1]
0x1800325ca  mov     edi, eax
0x1800325cc  test    eax, eax
0x1800325ce  js      loc_1800326C9
0x1800325d4  mov     r8d, dword ptr [rsp+150h+var_10C+4]; Size
0x1800325d9  mov     rdx, rbx; Buf2
0x1800325dc  mov     rcx, r15; Buf1
0x1800325df  call    memcmp_0
0x1800325e4  test    eax, eax
0x1800325e6  jz      short loc_1800325F2
0x1800325e8  mov     edi, 0C000000Dh
0x1800325ed  jmp     loc_1800326C9
0x1800325f2  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x1800325f7  lea     rax, [rsp+150h+var_104]
0x1800325fc  mov     [rsp+150h+var_120], rax; __int64
0x180032601  lea     r9, [rbp+50h+var_80]
0x180032605  lea     rax, [rsp+150h+var_E8]
0x18003260a  mov     r8d, 10h
0x180032610  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x180032615  mov     rdx, r13
0x180032618  mov     [rsp+150h+cbInput], 3Eh ; '>'; cbInput
0x180032620  call    WkstGenerateHMACWithSHA512
0x180032625  mov     r14, [rsp+150h+var_E8]
0x18003262a  mov     edi, eax
0x18003262c  test    eax, eax
0x18003262e  js      loc_1800326C9
0x180032634  mov     edx, [rbx+50h]; cbInput
0x180032637  lea     rax, [rsp+150h+var_104+4]
0x18003263c  mov     rcx, [rbx+58h]; pbInput
0x180032640  lea     r8, [rbx+40h]; pbIV
0x180032644  mov     [rsp+150h+var_118], rax; __int64
0x180032649  lea     rax, [rsp+150h+var_F0]
0x18003264e  mov     [rsp+150h+var_120], rax; __int64
0x180032653  mov     eax, [rsp+150h+var_104]
0x180032657  mov     [rsp+150h+cbSecret], eax; cbSecret
0x18003265b  mov     qword ptr [rsp+150h+cbInput], r14; __int64
0x180032660  call    WkstDecryptDataWithAES
0x180032665  mov     rsi, [rsp+150h+var_F0]
0x18003266a  mov     edi, eax
0x18003266c  test    eax, eax
0x18003266e  js      short loc_1800326C9
0x180032670  mov     ebx, [rsi]
0x180032672  test    bl, 1
0x180032675  jnz     loc_1800325E8
0x18003267b  lea     ecx, [rbx+2]
0x18003267e  call    NetpMemoryAllocate
0x180032683  mov     r13, [rbp+50h+var_C0]
0x180032687  mov     [r13+0], rax
0x18003268b  test    rax, rax
0x18003268e  jnz     short loc_180032695
0x180032690  lea     edi, [rax+8]
0x180032693  jmp     short loc_1800326C9
0x180032695  lea     rdx, [rsi+4]; Src
0x180032699  mov     r8, rbx; Size
0x18003269c  mov     rcx, rax; void *
0x18003269f  call    memcpy_0
0x1800326a4  mov     rcx, [r13+0]
0x1800326a8  xor     eax, eax
0x1800326aa  shr     rbx, 1
0x1800326ad  mov     [rcx+rbx*2], ax
0x1800326b1  mov     rax, rsi
0x1800326b4  mov     ecx, [rsp+150h+var_104+4]
0x1800326b8  test    rcx, rcx
0x1800326bb  jz      short loc_1800326C9
0x1800326bd  mov     byte ptr [rax], 0
0x1800326c0  inc     rax
0x1800326c3  sub     rcx, 1
0x1800326c7  jnz     short loc_1800326BD
0x1800326c9  mov     rcx, [rbp+50h+hMem]; hMem
0x1800326cd  call    cs:__imp_LocalFree
0x1800326d4  nop     dword ptr [rax+rax+00h]
0x1800326d9  mov     rcx, r14; hMem
0x1800326dc  call    cs:__imp_LocalFree
0x1800326e3  nop     dword ptr [rax+rax+00h]
0x1800326e8  mov     rcx, r15; hMem
0x1800326eb  call    cs:__imp_LocalFree
0x1800326f2  nop     dword ptr [rax+rax+00h]
0x1800326f7  mov     rcx, r12; hMem
0x1800326fa  call    cs:__imp_LocalFree
0x180032701  nop     dword ptr [rax+rax+00h]
0x180032706  mov     rcx, rsi; hMem
0x180032709  call    cs:__imp_LocalFree
0x180032710  nop     dword ptr [rax+rax+00h]
0x180032715  mov     eax, edi
0x180032717  mov     rcx, [rbp+50h+var_40]
0x18003271b  xor     rcx, rsp; StackCookie
0x18003271e  call    __security_check_cookie
0x180032723  mov     rbx, [rsp+150h+arg_18]
0x18003272b  add     rsp, 120h
0x180032732  pop     r15
0x180032734  pop     r14
0x180032736  pop     r13
0x180032738  pop     r12
0x18003273a  pop     rdi
0x18003273b  pop     rsi
0x18003273c  pop     rbp
0x18003273d  retn
```
