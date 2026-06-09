# WkstDecryptPasswordWithSessionKeyAES

- ea: `0x18002f730`
- end: `0x18002fa1a`
- name: `WkstDecryptPasswordWithSessionKeyAES`
- size: `746`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180026300`

## callees

- `0x180007710`
- `0x18001e420`
- `0x18002f4f8`
- `0x18002f730`
- `0x18002fa20`
- `0x18002fbe0`
- `0x18003314d`
- `0x180033159`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9eb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f80f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002f80f`

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
0x18002f730  mov     [rsp-8+arg_18], rbx
0x18002f735  push    rbp
0x18002f736  push    rsi
0x18002f737  push    rdi
0x18002f738  push    r12
0x18002f73a  push    r13
0x18002f73c  push    r14
0x18002f73e  push    r15
0x18002f740  lea     rbp, [rsp-20h]
0x18002f745  sub     rsp, 120h
0x18002f74c  mov     rax, cs:__security_cookie
0x18002f753  xor     rax, rsp
0x18002f756  mov     [rbp+50h+var_40], rax
0x18002f75a  movups  xmm0, xmmword ptr cs:aMicrosoftWkstE; "Microsoft WKST encryption key AEAD-AES-"...
0x18002f761  xor     eax, eax
0x18002f763  mov     [rbp+50h+var_C0], r8
0x18002f767  movups  xmm1, xmmword ptr cs:aMicrosoftWkstE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x18002f76e  mov     rbx, rdx
0x18002f771  mov     r13, rcx
0x18002f774  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x18002f778  lea     r9d, [rax+8]; dwFlags
0x18002f77c  xor     r8d, r8d; pszImplementation
0x18002f77f  movups  xmm0, xmmword ptr cs:aMicrosoftWkstE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x18002f786  lea     rdx, aSha512; "SHA512"
0x18002f78d  mov     [rsp+150h+phAlgorithm], rax
0x18002f792  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x18002f796  lea     rcx, [rsp+150h+phAlgorithm]; phAlgorithm
0x18002f79b  mov     [rbp+50h+hMem], rax
0x18002f79f  movups  xmm1, xmmword ptr cs:aMicrosoftWkstE+2Eh; "-HMAC-SHA512 16"
0x18002f7a6  mov     dword ptr [rsp+150h+var_10C], eax
0x18002f7aa  mov     r12d, eax
0x18002f7ad  movups  xmmword ptr [rbp+50h+var_80+20h], xmm0
0x18002f7b1  mov     [rsp+150h+var_D8], rax
0x18002f7b6  mov     r15d, eax
0x18002f7b9  movups  xmm0, xmmword ptr cs:aMicrosoftWkstM; "Microsoft WKST MAC key AEAD-AES-256-CBC"...
0x18002f7c0  mov     [rsp+150h+var_110], eax
0x18002f7c4  mov     r14d, eax
0x18002f7c7  movups  xmmword ptr [rbp+50h+var_80+2Eh], xmm1
0x18002f7cb  mov     [rsp+150h+Buf1], rax
0x18002f7d0  mov     esi, eax
0x18002f7d2  movups  xmm1, xmmword ptr cs:aMicrosoftWkstM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x18002f7d9  mov     dword ptr [rsp+150h+var_10C+4], eax
0x18002f7dd  movups  xmmword ptr [rbp+50h+var_B8], xmm0
0x18002f7e1  mov     [rsp+150h+var_E8], rax
0x18002f7e6  movups  xmm0, xmmword ptr cs:aMicrosoftWkstM+20h; "256-CBC-HMAC-SHA512 16"
0x18002f7ed  mov     [rsp+150h+var_104], eax
0x18002f7f1  movups  xmmword ptr [rbp+50h+var_B8+10h], xmm1
0x18002f7f5  mov     [rsp+150h+var_F0], rax
0x18002f7fa  movsd   xmm1, qword ptr cs:aMicrosoftWkstM+2Fh; "A512 16"
0x18002f802  movups  xmmword ptr [rbp+50h+var_B8+20h], xmm0
0x18002f806  mov     [rsp+150h+var_104+4], eax
0x18002f80a  movsd   qword ptr [rbp+50h+var_B8+2Fh], xmm1
0x18002f80f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002f815  mov     edi, eax
0x18002f817  test    eax, eax
0x18002f819  js      loc_18002F9C3
0x18002f81f  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18002f824  lea     rax, [rsp+150h+var_10C]
0x18002f829  mov     [rsp+150h+var_120], rax; __int64
0x18002f82e  lea     r9, [rbp+50h+var_B8]
0x18002f832  lea     rax, [rbp+50h+hMem]
0x18002f836  mov     rdx, r13
0x18002f839  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18002f83e  lea     r8d, [rsi+10h]
0x18002f842  mov     [rsp+150h+cbInput], 37h ; '7'; cbInput
0x18002f84a  call    WkstGenerateHMACWithSHA512
0x18002f84f  mov     edi, eax
0x18002f851  test    eax, eax
0x18002f853  js      loc_18002F9C3
0x18002f859  mov     r9d, [rbx+50h]
0x18002f85d  lea     rax, [rsp+150h+var_110]
0x18002f862  mov     r8, [rbx+58h]
0x18002f866  lea     rcx, [rbx+40h]
0x18002f86a  mov     qword ptr [rsp+150h+cbSecret], rax
0x18002f86f  lea     rax, [rsp+150h+var_D8]
0x18002f874  mov     qword ptr [rsp+150h+cbInput], rax
0x18002f879  call    WkstWriteAuthInfoDataToHMAC
0x18002f87e  mov     r12, [rsp+150h+var_D8]
0x18002f883  mov     edi, eax
0x18002f885  test    eax, eax
0x18002f887  js      loc_18002F9C3
0x18002f88d  mov     r8d, dword ptr [rsp+150h+var_10C]
0x18002f892  lea     rax, [rsp+150h+var_10C+4]
0x18002f897  mov     rdx, [rbp+50h+hMem]
0x18002f89b  mov     r9, r12
0x18002f89e  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18002f8a3  mov     [rsp+150h+var_120], rax; __int64
0x18002f8a8  lea     rax, [rsp+150h+Buf1]
0x18002f8ad  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18002f8b2  mov     eax, [rsp+150h+var_110]
0x18002f8b6  mov     [rsp+150h+cbInput], eax; cbInput
0x18002f8ba  call    WkstGenerateHMACWithSHA512
0x18002f8bf  mov     r15, [rsp+150h+Buf1]
0x18002f8c4  mov     edi, eax
0x18002f8c6  test    eax, eax
0x18002f8c8  js      loc_18002F9C3
0x18002f8ce  mov     r8d, dword ptr [rsp+150h+var_10C+4]; Size
0x18002f8d3  mov     rdx, rbx; Buf2
0x18002f8d6  mov     rcx, r15; Buf1
0x18002f8d9  call    memcmp_0
0x18002f8de  test    eax, eax
0x18002f8e0  jz      short loc_18002F8EC
0x18002f8e2  mov     edi, 0C000000Dh
0x18002f8e7  jmp     loc_18002F9C3
0x18002f8ec  mov     rcx, [rsp+150h+phAlgorithm]; hAlgorithm
0x18002f8f1  lea     rax, [rsp+150h+var_104]
0x18002f8f6  mov     [rsp+150h+var_120], rax; __int64
0x18002f8fb  lea     r9, [rbp+50h+var_80]
0x18002f8ff  lea     rax, [rsp+150h+var_E8]
0x18002f904  mov     r8d, 10h
0x18002f90a  mov     qword ptr [rsp+150h+cbSecret], rax; __int64
0x18002f90f  mov     rdx, r13
0x18002f912  mov     [rsp+150h+cbInput], 3Eh ; '>'; cbInput
0x18002f91a  call    WkstGenerateHMACWithSHA512
0x18002f91f  mov     r14, [rsp+150h+var_E8]
0x18002f924  mov     edi, eax
0x18002f926  test    eax, eax
0x18002f928  js      loc_18002F9C3
0x18002f92e  mov     edx, [rbx+50h]; cbInput
0x18002f931  lea     rax, [rsp+150h+var_104+4]
0x18002f936  mov     rcx, [rbx+58h]; pbInput
0x18002f93a  lea     r8, [rbx+40h]; pbIV
0x18002f93e  mov     [rsp+150h+var_118], rax; __int64
0x18002f943  lea     rax, [rsp+150h+var_F0]
0x18002f948  mov     [rsp+150h+var_120], rax; __int64
0x18002f94d  mov     eax, [rsp+150h+var_104]
0x18002f951  mov     [rsp+150h+cbSecret], eax; cbSecret
0x18002f955  mov     qword ptr [rsp+150h+cbInput], r14; __int64
0x18002f95a  call    WkstDecryptDataWithAES
0x18002f95f  mov     rsi, [rsp+150h+var_F0]
0x18002f964  mov     edi, eax
0x18002f966  test    eax, eax
0x18002f968  js      short loc_18002F9C3
0x18002f96a  mov     ebx, [rsi]
0x18002f96c  test    bl, 1
0x18002f96f  jnz     loc_18002F8E2
0x18002f975  lea     ecx, [rbx+2]
0x18002f978  call    NetpMemoryAllocate
0x18002f97d  mov     r13, [rbp+50h+var_C0]
0x18002f981  mov     [r13+0], rax
0x18002f985  test    rax, rax
0x18002f988  jnz     short loc_18002F98F
0x18002f98a  lea     edi, [rax+8]
0x18002f98d  jmp     short loc_18002F9C3
0x18002f98f  lea     rdx, [rsi+4]; Src
0x18002f993  mov     r8, rbx; Size
0x18002f996  mov     rcx, rax; void *
0x18002f999  call    memcpy_0
0x18002f99e  mov     rcx, [r13+0]
0x18002f9a2  xor     eax, eax
0x18002f9a4  shr     rbx, 1
0x18002f9a7  mov     [rcx+rbx*2], ax
0x18002f9ab  mov     rax, rsi
0x18002f9ae  mov     ecx, [rsp+150h+var_104+4]
0x18002f9b2  test    rcx, rcx
0x18002f9b5  jz      short loc_18002F9C3
0x18002f9b7  mov     byte ptr [rax], 0
0x18002f9ba  inc     rax
0x18002f9bd  sub     rcx, 1
0x18002f9c1  jnz     short loc_18002F9B7
0x18002f9c3  mov     rcx, [rbp+50h+hMem]; hMem
0x18002f9c7  call    cs:__imp_LocalFree
0x18002f9cd  mov     rcx, r14; hMem
0x18002f9d0  call    cs:__imp_LocalFree
0x18002f9d6  mov     rcx, r15; hMem
0x18002f9d9  call    cs:__imp_LocalFree
0x18002f9df  mov     rcx, r12; hMem
0x18002f9e2  call    cs:__imp_LocalFree
0x18002f9e8  mov     rcx, rsi; hMem
0x18002f9eb  call    cs:__imp_LocalFree
0x18002f9f1  mov     eax, edi
0x18002f9f3  mov     rcx, [rbp+50h+var_40]
0x18002f9f7  xor     rcx, rsp; StackCookie
0x18002f9fa  call    __security_check_cookie
0x18002f9ff  mov     rbx, [rsp+150h+arg_18]
0x18002fa07  add     rsp, 120h
0x18002fa0e  pop     r15
0x18002fa10  pop     r14
0x18002fa12  pop     r13
0x18002fa14  pop     r12
0x18002fa16  pop     rdi
0x18002fa17  pop     rsi
0x18002fa18  pop     rbp
0x18002fa19  retn
```
