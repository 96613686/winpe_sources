# SkpgAllocateContext

- ea: `0x1400a2260`
- end: `0x1400a2989`
- name: `SkpgAllocateContext`
- size: `1833`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400a3234`

## callees

- `0x14000f0f0`
- `0x140037e68`
- `0x14004f5d4`
- `0x1400a2260`
- `0x1400a2990`
- `0x1400a3650`
- `0x1400a40d8`
- `0x1400a623c`
- `0x1400aa580`
- `0x1400f3620`
- `0x1400f9780`
- `0x1400f9a80`

## import_xrefs

- `cng!BCryptOpenAlgorithmProvider` at `0x1400a23b8`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400a23b8`
- `cng!BCryptCreateHash` at `0x1400a24e6`
- `cng!BCryptCreateHash` at `0x1400a24e6`
- `cng!BCryptGenRandom` at `0x1400a2462`
- `cng!BCryptGenRandom` at `0x1400a267a`
- `cng!BCryptGenRandom` at `0x1400a2462`
- `cng!BCryptGenRandom` at `0x1400a267a`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400a286c`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400a2900`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400a286c`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400a2900`
- `cng!BCryptDestroyHash` at `0x1400a2851`
- `cng!BCryptDestroyHash` at `0x1400a28de`
- `cng!BCryptDestroyHash` at `0x1400a2851`
- `cng!BCryptDestroyHash` at `0x1400a28de`
- `cng!BCryptGetProperty` at `0x1400a23f4`
- `cng!BCryptGetProperty` at `0x1400a2522`
- `cng!BCryptGetProperty` at `0x1400a23f4`
- `cng!BCryptGetProperty` at `0x1400a2522`

## pseudocode

```c
unsigned int *__fastcall SkpgAllocateContext(unsigned __int64 a1, unsigned int a2, __int64 a3)
{
  unsigned __int64 v5; // r15
  unsigned int v6; // esi
  __int64 v7; // r12
  unsigned int v8; // edi
  void *Pool; // rax
  unsigned int v10; // eax
  void *v11; // rax
  __int64 i; // rax
  ULONG v13; // ecx
  UCHAR *v14; // rax
  unsigned int v15; // eax
  ULONG v16; // r14d
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  size_t v21; // rbx
  unsigned int *v22; // rax
  unsigned int *v23; // rdi
  unsigned int v24; // ecx
  __int64 v25; // rdx
  unsigned int v26; // ecx
  __int64 v27; // rdx
  __int64 IndependentPages; // rax
  unsigned int v29; // r11d
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // r11
  __int64 v32; // rcx
  unsigned __int64 v33; // r10
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rsi
  __int64 v37; // rax
  unsigned __int64 v38; // rbx
  BCRYPT_HANDLE v39; // rcx
  BCRYPT_HANDLE v40; // rcx
  BCRYPT_HANDLE v41; // rdx
  BCRYPT_HANDLE v42; // rdx
  __int64 v44; // rdi
  unsigned __int64 v45; // rbx
  BCRYPT_HANDLE v46; // rdx
  BCRYPT_HANDLE v47; // rdx
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49[3]; // [rsp+44h] [rbp-BCh] BYREF
  LPCWSTR pszAlgId; // [rsp+50h] [rbp-B0h] BYREF
  int v51; // [rsp+58h] [rbp-A8h]
  ULONG cbBuffer; // [rsp+5Ch] [rbp-A4h]
  BCRYPT_HANDLE hObject[6]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG cbHashObject[4]; // [rsp+90h] [rbp-70h] BYREF
  int v55; // [rsp+A0h] [rbp-60h]
  const wchar_t *v56; // [rsp+A8h] [rbp-58h]
  char v57[80]; // [rsp+B0h] [rbp-50h] BYREF
  const WCHAR *v58; // [rsp+100h] [rbp+0h]
  char v59[88]; // [rsp+108h] [rbp+8h] BYREF

  v49[0] = a2;
  pszAlgId = L"AES-GMAC";
  v51 = 12;
  cbBuffer = 16;
  memset_0(hObject, 0, 0x48u);
  v56 = L"SHA512";
  memset_0(v57, 0, sizeof(v57));
  v58 = L"SHA256";
  memset_0(v59, 0, 0x50u);
  pcbResult = 0;
  if ( a1 + 15 < a1 )
    goto LABEL_66;
  if ( a1 + 39 < a1 + 15 )
    goto LABEL_66;
  if ( a1 + 54 < a1 + 39 )
    goto LABEL_66;
  if ( a1 + 310 < a1 + 54 )
    goto LABEL_66;
  if ( a1 + 325 < a1 + 310 )
    goto LABEL_66;
  if ( a1 + 453 < a1 + 325 )
    goto LABEL_66;
  v5 = a1 + 468;
  if ( a1 + 468 < a1 + 453 )
    goto LABEL_66;
  v6 = 0;
  if ( SkpgNtInvalidPtesHard && SkpgNtSmtPresent )
    v55 = 1;
  if ( SkpKeepsNoSecrets )
    v55 = 1;
  v7 = *(_QWORD *)(a3 + 8);
  v8 = 0;
  while ( v8 < 3 )
  {
    if ( BCryptOpenAlgorithmProvider(&hObject[11 * v8], (&pszAlgId)[11 * v8], 0, 0x21u) < 0 )
      goto LABEL_66;
    if ( BCryptGetProperty(hObject[11 * v8], L"ObjectLength", (PUCHAR)&cbHashObject[22 * v8], 4u, &pcbResult, 0) < 0 )
      goto LABEL_66;
    Pool = (void *)SkAllocatePool(512, cbHashObject[22 * v8]);
    hObject[11 * v8 + 2] = Pool;
    if ( !Pool )
      goto LABEL_66;
    v10 = *(&cbBuffer + 22 * v8);
    if ( v10 )
    {
      v11 = (void *)SkAllocatePool(512, v10);
      hObject[11 * v8 + 3] = v11;
      if ( !v11 || BCryptGenRandom(0, (PUCHAR)v11, *(&cbBuffer + 22 * v8), 2u) < 0 )
        goto LABEL_66;
      if ( (*(_DWORD *)a3 & 2) != 0 )
      {
        for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
        {
          if ( v8 == *(_DWORD *)(v7 + 4 * i + 144) )
          {
            memmove(hObject[11 * v8 + 3], *(const void **)(v7 + 8 * i + 208), *(unsigned int *)(v7 + 4 * i + 224));
            break;
          }
        }
      }
    }
    v13 = *(&cbBuffer + 22 * v8);
    v14 = v13 ? (UCHAR *)hObject[11 * v8 + 3] : 0LL;
    if ( BCryptCreateHash(
           hObject[11 * v8],
           &hObject[11 * v8 + 1],
           (PUCHAR)hObject[11 * v8 + 2],
           cbHashObject[22 * v8],
           v14,
           v13,
           0x20u) < 0
      || BCryptGetProperty(hObject[11 * v8], L"HashDigestLength", (PUCHAR)&cbHashObject[22 * v8 + 1], 4u, &pcbResult, 0) < 0 )
    {
      goto LABEL_66;
    }
    v15 = *(&v51 + 22 * v8++);
    if ( v6 > v15 )
      v15 = v6;
    v6 = v15;
  }
  v16 = 2 * v6;
  v17 = v5 + 2 * v6;
  if ( v17 < v5 )
    goto LABEL_66;
  v18 = v17 + 15;
  if ( v17 + 15 < v17 )
    goto LABEL_66;
  v19 = v17 + 31;
  if ( v18 + 16 < v18 )
    goto LABEL_66;
  v20 = v18 + 31;
  if ( v19 + 15 < v19 )
    goto LABEL_66;
  if ( v19 + 4383 < v19 + 15 )
    goto LABEL_66;
  v21 = v19 + 4398;
  if ( v19 + 4398 < v19 + 4383 )
    goto LABEL_66;
  v22 = (unsigned int *)SkAllocatePool(512, v20 + 4383);
  v23 = v22;
  if ( !v22 )
    goto LABEL_66;
  memset_0(v22, 0, v21);
  v23[10] = v49[0];
  *((_QWORD *)v23 + 37) = v21;
  v24 = ((((_DWORD)v23 + 903) & 0xFFFFFFF0) + 39) & 0xFFFFFFF0;
  v23[25] = (((_DWORD)v23 + 903) & 0xFFFFFFF0) - (_DWORD)v23;
  v23[22] = v24 - (_DWORD)v23;
  v23[16] = v24 + 256 - (_DWORD)v23;
  v25 = 0;
  do
  {
    v23[v25 + 70] = v24 + 384 + v25 * v6 - (_DWORD)v23;
    v25 = (unsigned int)(v25 + 1);
  }
  while ( (unsigned int)v25 < 2 );
  v26 = (v16 + v24 + 399) & 0xFFFFFFF0;
  v23[29] = v26 - (_DWORD)v23;
  v27 = v26 + 16 - (unsigned int)v23;
  v23[28] = v27;
  v23[11] = ((v26 + 4399) & 0xFFFFFFF0) - (_DWORD)v23;
  *((_QWORD *)v23 + 38) = v27 + 8;
  if ( v6 )
  {
    if ( BCryptGenRandom(0, (PUCHAR)v23 + v23[70], v16, 2u) < 0 )
    {
LABEL_65:
      SkpgFreeContext(v23);
LABEL_66:
      v44 = 0;
      v45 = 0;
      do
      {
        if ( cbHashObject[v45 / 4 + 3] )
        {
          BCryptDestroyHash(hObject[v45 / 8 + 1]);
          cbHashObject[v45 / 4 + 3] = 0;
        }
        if ( cbHashObject[v45 / 4 + 2] )
        {
          BCryptCloseAlgorithmProvider(hObject[v45 / 8], 0);
          cbHashObject[v45 / 4 + 2] = 0;
        }
        v46 = hObject[v45 / 8 + 2];
        if ( v46 )
        {
          SkFreePool(512, v46);
          hObject[v45 / 8 + 2] = 0;
        }
        v47 = hObject[v45 / 8 + 3];
        if ( v47 )
        {
          SkFreePool(512, v47);
          hObject[v45 / 8 + 3] = 0;
        }
        ++v44;
        v45 += 88LL;
      }
      while ( v44 != 3 );
      return 0;
    }
    if ( (*(_DWORD *)a3 & 2) != 0 )
      memmove((char *)v23 + v23[70], (const void *)(v7 + *(unsigned int *)(v7 + 280)), v6);
  }
  v23[18] = 327680;
  v23[19] = 163840;
  if ( (*(_DWORD *)a3 & 2) != 0 )
  {
    v23[18] = 0x7FFFFFFF;
    v23[19] = 0x3FFFFFFF;
  }
  v23[26] = 1;
  IndependentPages = SkmmAllocateIndependentPages(4096);
  *((_QWORD *)v23 + 17) = IndependentPages;
  if ( !IndependentPages )
    goto LABEL_65;
  v29 = v23[10];
  *(_QWORD *)(v23 + 23) = 16;
  if ( v29 )
  {
    v30 = SkpgRandomValue();
    v23[12] = v30 % v31;
  }
  v23[61] = v23[61] & 0xFFBFFFFF | ((*(_DWORD *)a3 & 4) << 20);
  if ( (int)SkpgxInitializeContextArchSpecific(v23, v49) < 0 )
    goto LABEL_65;
  if ( (*(_DWORD *)a3 & 2) != 0 )
    SkpgCopyHashAlgorithms(v32, v7, &pszAlgId);
  else
    SkpgCalibrateHashAlgorithms(v32, &pszAlgId);
  memset_0(v23 + 140, 0, 0x48u);
  v33 = SkmiNtPteBase;
  *((_QWORD *)v23 + 76) = SkpgHyperguardTimerRoutine;
  v34 = (v33 >> 39) & 0x1FF;
  *((_QWORD *)v23 + 79) = SkpgHyperguardRuntime;
  v35 = 0;
  *((_QWORD *)v23 + 82) = 0;
  v23[166] = -1;
  do
  {
    *(_QWORD *)&v23[2 * v35 + 92] = v33;
    *(_QWORD *)&v23[2 * v35 + 100] = v33 + (1LL << (39 - 9 * (unsigned __int8)v35)) - 1;
    v35 = (unsigned int)(v35 + 1);
    v33 |= v34 << (39 - 9 * (unsigned __int8)v35);
  }
  while ( (unsigned int)v35 < 4 );
  v36 = 0;
  v37 = (*((_QWORD *)v23 + 49) >> 9) & 0x7FFFFFFFF8LL;
  v23[110] = v34;
  *((_QWORD *)v23 + 54) = *((_QWORD *)v23 + 46) + v37;
  v38 = 0;
  v23[113] = -2;
  do
  {
    v39 = hObject[v38 / 8 + 1];
    if ( v39 != *((BCRYPT_HANDLE *)v23 + 21) )
    {
      BCryptDestroyHash(v39);
      v40 = hObject[v38 / 8];
      cbHashObject[v38 / 4 + 3] = 0;
      BCryptCloseAlgorithmProvider(v40, 0);
      v41 = hObject[v38 / 8 + 2];
      cbHashObject[v38 / 4 + 2] = 0;
      SkFreePool(512, v41);
      v42 = hObject[v38 / 8 + 3];
      hObject[v38 / 8 + 2] = 0;
      if ( v42 )
      {
        SkFreePool(512, v42);
        hObject[v38 / 8 + 3] = 0;
      }
    }
    ++v36;
    v38 += 88LL;
  }
  while ( v36 != 2 );
  return v23;
}

```

## disassembly

```asm
0x1400a2260  mov     [rsp-8+arg_8], rbx
0x1400a2265  push    rbp
0x1400a2266  push    rsi
0x1400a2267  push    rdi
0x1400a2268  push    r12
0x1400a226a  push    r13
0x1400a226c  push    r14
0x1400a226e  push    r15
0x1400a2270  lea     rbp, [rsp-70h]
0x1400a2275  sub     rsp, 170h
0x1400a227c  mov     rax, cs:__security_cookie
0x1400a2283  xor     rax, rsp
0x1400a2286  mov     [rbp+0A0h+var_40], rax
0x1400a228a  mov     [rsp+1A0h+var_15C], edx
0x1400a228e  lea     rax, aAesGmac; "AES-GMAC"
0x1400a2295  xor     edx, edx; Val
0x1400a2297  mov     [rsp+1A0h+pszAlgId], rax
0x1400a229c  mov     r13, r8
0x1400a229f  mov     [rsp+1A0h+var_148], 0Ch
0x1400a22a7  mov     rbx, rcx
0x1400a22aa  mov     [rsp+1A0h+cbBuffer], 10h
0x1400a22b2  lea     rcx, [rsp+1A0h+hObject]; void *
0x1400a22b7  lea     r8d, [rdx+48h]; Size
0x1400a22bb  call    memset_0
0x1400a22c0  lea     rax, aSha512; "SHA512"
0x1400a22c7  mov     edi, 50h ; 'P'
0x1400a22cc  mov     r8d, edi; Size
0x1400a22cf  mov     [rbp+0A0h+var_F8], rax
0x1400a22d3  xor     edx, edx; Val
0x1400a22d5  lea     rcx, [rbp+0A0h+var_F0]; void *
0x1400a22d9  call    memset_0
0x1400a22de  lea     rax, pszAlgId; "SHA256"
0x1400a22e5  mov     r8d, edi; Size
0x1400a22e8  xor     edx, edx; Val
0x1400a22ea  mov     [rbp+0A0h+var_A0], rax
0x1400a22ee  lea     rcx, [rbp+0A0h+var_98]; void *
0x1400a22f2  call    memset_0
0x1400a22f7  lea     rcx, [rbx+0Fh]
0x1400a22fb  mov     [rsp+1A0h+var_160], 0
0x1400a2303  cmp     rcx, rbx
0x1400a2306  jb      loc_1400A28CE
0x1400a230c  lea     rax, [rcx+18h]
0x1400a2310  cmp     rax, rcx
0x1400a2313  jb      loc_1400A28CE
0x1400a2319  lea     rcx, [rax+0Fh]
0x1400a231d  cmp     rcx, rax
0x1400a2320  jb      loc_1400A28CE
0x1400a2326  lea     rax, [rcx+100h]
0x1400a232d  cmp     rax, rcx
0x1400a2330  jb      loc_1400A28CE
0x1400a2336  lea     rcx, [rax+0Fh]
0x1400a233a  cmp     rcx, rax
0x1400a233d  jb      loc_1400A28CE
0x1400a2343  lea     rax, [rcx+80h]
0x1400a234a  cmp     rax, rcx
0x1400a234d  jb      loc_1400A28CE
0x1400a2353  lea     r15, [rax+0Fh]
0x1400a2357  cmp     r15, rax
0x1400a235a  jb      loc_1400A28CE
0x1400a2360  xor     esi, esi
0x1400a2362  cmp     cs:SkpgNtInvalidPtesHard, esi
0x1400a2368  jz      short loc_1400A2379
0x1400a236a  cmp     cs:SkpgNtSmtPresent, esi
0x1400a2370  jz      short loc_1400A2379
0x1400a2372  mov     [rbp+0A0h+var_100], 1
0x1400a2379  cmp     cs:SkpKeepsNoSecrets, sil
0x1400a2380  jz      short loc_1400A2389
0x1400a2382  mov     [rbp+0A0h+var_100], 1
0x1400a2389  mov     r12, [r13+8]
0x1400a238d  xor     edi, edi
0x1400a238f  lea     r14d, [rdi+4]
0x1400a2393  cmp     edi, 3
0x1400a2396  jnb     loc_1400A2548
0x1400a239c  mov     eax, edi
0x1400a239e  lea     rcx, [rsp+1A0h+hObject]
0x1400a23a3  imul    rbx, rax, 58h ; 'X'
0x1400a23a7  mov     r9d, 21h ; '!'; dwFlags
0x1400a23ad  xor     r8d, r8d; pszImplementation
0x1400a23b0  add     rcx, rbx; phAlgorithm
0x1400a23b3  mov     rdx, [rsp+rbx+1A0h+pszAlgId]; pszAlgId
0x1400a23b8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400a23bf  nop     dword ptr [rax+rax+00h]
0x1400a23c4  test    eax, eax
0x1400a23c6  js      loc_1400A28CE
0x1400a23cc  mov     rcx, [rsp+rbx+1A0h+hObject]; hObject
0x1400a23d1  lea     rax, [rsp+1A0h+var_160]
0x1400a23d6  lea     r8, [rbp+0A0h+cbHashObject]
0x1400a23da  mov     [rsp+1A0h+dwFlags], 0; dwFlags
0x1400a23e2  add     r8, rbx; pbOutput
0x1400a23e5  mov     [rsp+1A0h+pcbResult], rax; pcbResult
0x1400a23ea  mov     r9d, r14d; cbOutput
0x1400a23ed  lea     rdx, pszProperty; "ObjectLength"
0x1400a23f4  call    cs:__imp_BCryptGetProperty
0x1400a23fb  nop     dword ptr [rax+rax+00h]
0x1400a2400  test    eax, eax
0x1400a2402  js      loc_1400A28CE
0x1400a2408  mov     edx, [rbp+rbx+0A0h+cbHashObject]
0x1400a240c  mov     ecx, 200h
0x1400a2411  mov     r8d, 4F486750h
0x1400a2417  call    SkAllocatePool
0x1400a241c  mov     [rsp+rbx+1A0h+pbHashObject], rax
0x1400a2421  test    rax, rax
0x1400a2424  jz      loc_1400A28CE
0x1400a242a  mov     eax, [rsp+rbx+1A0h+cbBuffer]
0x1400a242e  test    eax, eax
0x1400a2430  jz      short loc_1400A24AD
0x1400a2432  mov     edx, eax
0x1400a2434  mov     ecx, 200h
0x1400a2439  mov     r8d, 43426750h
0x1400a243f  call    SkAllocatePool
0x1400a2444  mov     [rsp+rbx+1A0h+pbSecret], rax
0x1400a2449  test    rax, rax
0x1400a244c  jz      loc_1400A28CE
0x1400a2452  mov     r8d, [rsp+rbx+1A0h+cbBuffer]; cbBuffer
0x1400a2457  mov     r9d, 2; dwFlags
0x1400a245d  mov     rdx, rax; pbBuffer
0x1400a2460  xor     ecx, ecx; hAlgorithm
0x1400a2462  call    cs:__imp_BCryptGenRandom
0x1400a2469  nop     dword ptr [rax+rax+00h]
0x1400a246e  test    eax, eax
0x1400a2470  js      loc_1400A28CE
0x1400a2476  mov     eax, [r13+0]
0x1400a247a  test    al, 2
0x1400a247c  jz      short loc_1400A24AD
0x1400a247e  xor     eax, eax
0x1400a2480  cmp     eax, 2
0x1400a2483  jnb     short loc_1400A24AD
0x1400a2485  cmp     edi, [r12+rax*4+90h]
0x1400a248d  jz      short loc_1400A2493
0x1400a248f  inc     eax
0x1400a2491  jmp     short loc_1400A2480
0x1400a2493  mov     r8d, [r12+rax*4+0E0h]; Size
0x1400a249b  mov     rdx, [r12+rax*8+0D0h]; Src
0x1400a24a3  mov     rcx, [rsp+rbx+1A0h+pbSecret]; void *
0x1400a24a8  call    memmove
0x1400a24ad  mov     ecx, [rsp+rbx+1A0h+cbBuffer]
0x1400a24b1  test    ecx, ecx
0x1400a24b3  jz      short loc_1400A24BC
0x1400a24b5  mov     rax, [rsp+rbx+1A0h+pbSecret]
0x1400a24ba  jmp     short loc_1400A24BE
0x1400a24bc  xor     eax, eax
0x1400a24be  mov     r9d, [rbp+rbx+0A0h+cbHashObject]; cbHashObject
0x1400a24c3  lea     rdx, [rsp+1A0h+hHash]
0x1400a24c8  mov     r8, [rsp+rbx+1A0h+pbHashObject]; pbHashObject
0x1400a24cd  add     rdx, rbx; phHash
0x1400a24d0  mov     [rsp+1A0h+var_170], 20h ; ' '; dwFlags
0x1400a24d8  mov     [rsp+1A0h+dwFlags], ecx; cbSecret
0x1400a24dc  mov     rcx, [rsp+rbx+1A0h+hObject]; hAlgorithm
0x1400a24e1  mov     [rsp+1A0h+pcbResult], rax; pbSecret
0x1400a24e6  call    cs:__imp_BCryptCreateHash
0x1400a24ed  nop     dword ptr [rax+rax+00h]
0x1400a24f2  test    eax, eax
0x1400a24f4  js      loc_1400A28CE
0x1400a24fa  mov     rcx, [rsp+rbx+1A0h+hObject]; hObject
0x1400a24ff  lea     rax, [rsp+1A0h+var_160]
0x1400a2504  lea     r8, [rbp+0A0h+var_10C]
0x1400a2508  mov     [rsp+1A0h+dwFlags], 0; dwFlags
0x1400a2510  add     r8, rbx; pbOutput
0x1400a2513  mov     [rsp+1A0h+pcbResult], rax; pcbResult
0x1400a2518  mov     r9d, r14d; cbOutput
0x1400a251b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400a2522  call    cs:__imp_BCryptGetProperty
0x1400a2529  nop     dword ptr [rax+rax+00h]
0x1400a252e  test    eax, eax
0x1400a2530  js      loc_1400A28CE
0x1400a2536  mov     eax, [rsp+rbx+1A0h+var_148]
0x1400a253a  inc     edi
0x1400a253c  cmp     esi, eax
0x1400a253e  cmova   eax, esi
0x1400a2541  mov     esi, eax
0x1400a2543  jmp     loc_1400A2393
0x1400a2548  lea     r14d, [rsi+rsi]
0x1400a254c  mov     ecx, r14d
0x1400a254f  add     rcx, r15
0x1400a2552  cmp     rcx, r15
0x1400a2555  jb      loc_1400A28CE
0x1400a255b  lea     rax, [rcx+0Fh]
0x1400a255f  cmp     rax, rcx
0x1400a2562  jb      loc_1400A28CE
0x1400a2568  lea     rcx, [rax+10h]
0x1400a256c  cmp     rcx, rax
0x1400a256f  jb      loc_1400A28CE
0x1400a2575  lea     rax, [rcx+0Fh]
0x1400a2579  cmp     rax, rcx
0x1400a257c  jb      loc_1400A28CE
0x1400a2582  lea     rcx, [rax+1110h]
0x1400a2589  cmp     rcx, rax
0x1400a258c  jb      loc_1400A28CE
0x1400a2592  lea     rbx, [rcx+0Fh]
0x1400a2596  cmp     rbx, rcx
0x1400a2599  jb      loc_1400A28CE
0x1400a259f  mov     r15d, 200h
0x1400a25a5  mov     r8d, 78436750h
0x1400a25ab  mov     ecx, r15d
0x1400a25ae  mov     rdx, rbx
0x1400a25b1  call    SkAllocatePool
0x1400a25b6  mov     rdi, rax
0x1400a25b9  test    rax, rax
0x1400a25bc  jz      loc_1400A28CE
0x1400a25c2  mov     r8, rbx; Size
0x1400a25c5  xor     edx, edx; Val
0x1400a25c7  mov     rcx, rax; void *
0x1400a25ca  call    memset_0
0x1400a25cf  mov     eax, [rsp+1A0h+var_15C]
0x1400a25d3  lea     rcx, [rdi+387h]
0x1400a25da  mov     [rdi+28h], eax
0x1400a25dd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400a25e1  mov     eax, ecx
0x1400a25e3  mov     [rdi+128h], rbx
0x1400a25ea  sub     eax, edi
0x1400a25ec  add     rcx, 27h ; '''
0x1400a25f0  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400a25f4  mov     [rdi+64h], eax
0x1400a25f7  mov     eax, ecx
0x1400a25f9  sub     eax, edi
0x1400a25fb  mov     [rdi+58h], eax
0x1400a25fe  lea     eax, [rcx+100h]
0x1400a2604  sub     eax, edi
0x1400a2606  lea     r8d, [rcx+180h]
0x1400a260d  mov     [rdi+40h], eax
0x1400a2610  xor     edx, edx
0x1400a2612  mov     ecx, esi
0x1400a2614  imul    ecx, edx
0x1400a2617  sub     ecx, edi
0x1400a2619  add     ecx, r8d
0x1400a261c  mov     [rdi+rdx*4+118h], ecx
0x1400a2623  inc     edx
0x1400a2625  cmp     edx, 2
0x1400a2628  jb      short loc_1400A2612
0x1400a262a  lea     ecx, [r8+0Fh]
0x1400a262e  mov     r8d, 0FFFFFFF0h
0x1400a2634  add     ecx, r14d
0x1400a2637  and     ecx, r8d
0x1400a263a  mov     eax, ecx
0x1400a263c  sub     eax, edi
0x1400a263e  mov     [rdi+74h], eax
0x1400a2641  lea     edx, [rcx+10h]
0x1400a2644  sub     edx, edi
0x1400a2646  lea     eax, [rcx+112Fh]
0x1400a264c  and     eax, r8d
0x1400a264f  mov     [rdi+70h], edx
0x1400a2652  sub     eax, edi
0x1400a2654  add     rdx, 8
0x1400a2658  mov     [rdi+2Ch], eax
0x1400a265b  mov     [rdi+130h], rdx
0x1400a2662  test    esi, esi
0x1400a2664  jz      short loc_1400A26B2
0x1400a2666  mov     edx, [rdi+118h]
0x1400a266c  mov     r9d, 2; dwFlags
0x1400a2672  add     rdx, rdi; pbBuffer
0x1400a2675  mov     r8d, r14d; cbBuffer
0x1400a2678  xor     ecx, ecx; hAlgorithm
0x1400a267a  call    cs:__imp_BCryptGenRandom
0x1400a2681  nop     dword ptr [rax+rax+00h]
0x1400a2686  test    eax, eax
0x1400a2688  js      loc_1400A28C6
0x1400a268e  mov     eax, [r13+0]
0x1400a2692  test    al, 2
0x1400a2694  jz      short loc_1400A26B2
0x1400a2696  mov     edx, [r12+118h]
0x1400a269e  mov     ecx, [rdi+118h]
0x1400a26a4  add     rdx, r12; Src
0x1400a26a7  add     rcx, rdi; void *
0x1400a26aa  mov     r8d, esi; Size
0x1400a26ad  call    memmove
0x1400a26b2  mov     dword ptr [rdi+48h], 50000h
0x1400a26b9  mov     dword ptr [rdi+4Ch], 28000h
0x1400a26c0  mov     eax, [r13+0]
0x1400a26c4  test    al, 2
0x1400a26c6  jz      short loc_1400A26D6
0x1400a26c8  mov     dword ptr [rdi+48h], 7FFFFFFFh
0x1400a26cf  mov     dword ptr [rdi+4Ch], 3FFFFFFFh
0x1400a26d6  mov     ecx, 1000h
0x1400a26db  mov     dword ptr [rdi+68h], 1
0x1400a26e2  call    SkmmAllocateIndependentPages
0x1400a26e7  mov     [rdi+88h], rax
0x1400a26ee  test    rax, rax
0x1400a26f1  jz      loc_1400A28C6
0x1400a26f7  mov     r11d, [rdi+28h]
0x1400a26fb  mov     qword ptr [rdi+5Ch], 10h
0x1400a2703  test    r11d, r11d
0x1400a2706  jz      short loc_1400A2715
0x1400a2708  call    SkpgRandomValue
0x1400a270d  xor     edx, edx
0x1400a270f  div     r11
0x1400a2712  mov     [rdi+30h], edx
0x1400a2715  mov     ecx, [r13+0]
0x1400a2719  lea     rdx, [rsp+1A0h+var_15C]
0x1400a271e  mov     eax, [rdi+0F4h]
0x1400a2724  and     ecx, 4
0x1400a2727  shl     ecx, 14h
0x1400a272a  btr     eax, 16h
0x1400a272e  or      ecx, eax
0x1400a2730  mov     [rdi+0F4h], ecx
0x1400a2736  mov     rcx, rdi
0x1400a2739  call    SkpgxInitializeContextArchSpecific
0x1400a273e  test    eax, eax
0x1400a2740  js      loc_1400A28C6
0x1400a2746  mov     eax, [r13+0]
0x1400a274a  test    al, 2
  ... truncated ...
```
