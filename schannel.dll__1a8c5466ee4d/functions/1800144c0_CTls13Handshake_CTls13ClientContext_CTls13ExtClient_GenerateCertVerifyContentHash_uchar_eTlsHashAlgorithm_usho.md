# CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::GenerateCertVerifyContentHash(uchar,_eTlsHashAlgorithm,ushort const *,uchar *,ulong,ulong *)

- ea: `0x1800144c0`
- end: `0x180014893`
- name: `?GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z`
- size: `979`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800148a0`
- `0x18007db7c`
- `0x180080f44`

## callees

- `0x1800144c0`
- `0x180088a54`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800144ea`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800144ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014844`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014823`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014823`
- `ncrypt!SslComputeSessionHash` at `0x1800145ad`
- `ncrypt!SslComputeSessionHash` at `0x1800145ad`
- `bcrypt!BCryptGetProperty` at `0x180014687`
- `bcrypt!BCryptGetProperty` at `0x180014687`
- `bcrypt!BCryptCreateHash` at `0x1800146de`
- `bcrypt!BCryptCreateHash` at `0x1800146de`
- `bcrypt!BCryptHashData` at `0x180014702`
- `bcrypt!BCryptHashData` at `0x180014730`
- `bcrypt!BCryptHashData` at `0x180014750`
- `bcrypt!BCryptHashData` at `0x18001476a`
- `bcrypt!BCryptHashData` at `0x180014702`
- `bcrypt!BCryptHashData` at `0x180014730`
- `bcrypt!BCryptHashData` at `0x180014750`
- `bcrypt!BCryptHashData` at `0x18001476a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008aee6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18008aee6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008aeb6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18008aeb6`
- `bcrypt!BCryptFinishHash` at `0x180014783`
- `bcrypt!BCryptFinishHash` at `0x180014783`
- `bcrypt!BCryptDestroyHash` at `0x18001479c`
- `bcrypt!BCryptDestroyHash` at `0x18001479c`

## pseudocode

```c
NTSTATUS __fastcall CTls13Handshake<CTls13ClientContext,CTls13ExtClient>::GenerateCertVerifyContentHash(
        __int64 a1,
        char a2,
        int a3,
        const wchar_t *a4,
        PUCHAR pbInput,
        unsigned int a6,
        unsigned int *a7)
{
  unsigned __int8 v10; // al
  unsigned int *v11; // r12
  PUCHAR v12; // r13
  unsigned int v13; // r14d
  unsigned int v14; // ecx
  unsigned __int16 *v15; // rcx
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rcx
  NTSTATUS result; // eax
  int v21; // esi
  unsigned int i; // eax
  __int64 v23; // rdx
  BCRYPT_ALG_HANDLE v24; // rax
  __int64 v25; // rcx
  BCRYPT_HANDLE v26; // rbx
  ULONG v27; // edi
  UCHAR *v28; // rax
  UCHAR *v29; // rsi
  NTSTATUS v30; // ebx
  UCHAR *v31; // rdx
  __int64 v32; // rbx
  ULONG cbInput; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-28h] BYREF
  ULONG pbOutput; // [rsp+B8h] [rbp+40h] BYREF

  if ( a4 )
    v10 = wcsnlen(a4, 0x40u);
  else
    v10 = 0;
  if ( v10 >= 0x40u )
    return 87;
  v11 = a7;
  if ( !a7 )
    return 87;
  if ( v10 )
    v10 = 2 * (v10 + 1);
  v12 = pbInput;
  v13 = v10;
  v14 = v10 + 64;
  *a7 = v14;
  if ( !v12 || a6 < v14 )
    return 122;
  *v11 = 0;
  if ( a4 )
  {
    v32 = v10;
    memcpy_0(v12, a4, v10);
    v12 += v32;
    *v11 = v13;
  }
  v15 = *(unsigned __int16 **)(a1 + 8);
  cbInput = 0;
  v16 = v15[17];
  v17 = (*(__int64 (__fastcall **)(unsigned __int16 *, _QWORD))(*(_QWORD *)v15 + 576LL))(v15, 0);
  v18 = *(__int64 **)(*(_QWORD *)(a1 + 8) + 8LL);
  if ( v18 )
    v19 = *v18;
  else
    v19 = 0;
  result = SslComputeSessionHash(v19, v17, v16, v12, 64, &cbInput, 0);
  if ( !result )
  {
    v21 = g_dwHashInfoTotalCount;
    hObject = 0;
    for ( i = 0; i < g_dwHashInfoTotalCount; ++i )
    {
      v23 = g_pHashInfo[i];
      if ( v23 && *(_DWORD *)(v23 + 20) == a3 )
      {
        v21 = i;
        break;
      }
    }
    if ( v21 < 0 || v21 >= g_dwHashInfoTotalCount )
    {
      v21 = 0;
    }
    else
    {
      if ( v21 == 1 )
      {
        v24 = g_hMD5Provider;
        goto LABEL_25;
      }
      if ( v21 == 2 )
      {
        v24 = g_hSHAProvider;
        goto LABEL_25;
      }
    }
    v24 = (BCRYPT_ALG_HANDLE)qword_1800AE610[v21];
LABEL_25:
    hObject = v24;
    if ( v21 >= (unsigned int)g_dwHashInfoTotalCount )
      return 1168;
    _mm_lfence();
    v25 = g_pHashInfo[v21];
    if ( !v25 )
      return 1168;
    v26 = hObject;
    v27 = *(_DWORD *)(v25 + 8);
    if ( !hObject )
    {
      if ( !*(_QWORD *)v25 )
        return 1359;
      result = BCryptOpenAlgorithmProvider(&hObject, *(LPCWSTR *)v25, 0, 0);
      if ( result )
        return result;
      v26 = (BCRYPT_HANDLE)_InterlockedCompareExchange64(
                             (volatile signed __int64 *)&_ImageBase[4 * v21 + 357128],
                             (signed __int64)hObject,
                             0);
      if ( v26 )
      {
        BCryptCloseAlgorithmProvider(hObject, 0);
        hObject = v26;
      }
      else
      {
        v26 = hObject;
      }
    }
    if ( v27 <= 0x40 )
    {
      pbOutput = 0;
      pcbResult = 0;
      result = BCryptGetProperty(v26, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
      if ( !result )
      {
        if ( LsaTable )
          v28 = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(LsaTable + 40))(pbOutput);
        else
          v28 = (UCHAR *)LocalAlloc(0x40u, pbOutput);
        v29 = v28;
        if ( v28 )
        {
          phHash = 0;
          v30 = BCryptCreateHash(v26, &phHash, v28, pbOutput, 0, 0, 0);
          if ( !v30 )
          {
            v30 = BCryptHashData(
                    phHash,
                    (PUCHAR)"                                                                TLS 1.3, ",
                    0x49u,
                    0);
            if ( !v30 )
            {
              v31 = a2 ? (UCHAR *)"server" : (UCHAR *)"client";
              v30 = BCryptHashData(phHash, v31, 6u, 0);
              if ( !v30 )
              {
                v30 = BCryptHashData(phHash, (PUCHAR)" CertificateVerify", 0x13u, 0);
                if ( !v30 )
                {
                  v30 = BCryptHashData(phHash, v12, cbInput, 0);
                  if ( !v30 )
                  {
                    v30 = BCryptFinishHash(phHash, v12, v27, 0);
                    if ( !v30 )
                      *v11 += v27;
                  }
                }
              }
            }
          }
          if ( phHash )
            BCryptDestroyHash(phHash);
          if ( LsaTable )
            (*(void (__fastcall **)(UCHAR *))(LsaTable + 48))(v29);
          else
            LocalFree(v29);
          return v30;
        }
        else
        {
          return 14;
        }
      }
      return result;
    }
    return 1359;
  }
  return result;
}

```

## disassembly

```asm
0x1800144c0  mov     [rsp-20h+arg_8], dl
0x1800144c4  push    rbp
0x1800144c5  push    rsi
0x1800144c6  push    rdi
0x1800144c7  push    r15
0x1800144c9  mov     rbp, rsp
0x1800144cc  sub     rsp, 78h
0x1800144d0  mov     rsi, r9
0x1800144d3  mov     edi, r8d
0x1800144d6  mov     r15, rcx
0x1800144d9  test    r9, r9
0x1800144dc  jz      loc_1800147ED
0x1800144e2  mov     edx, 40h ; '@'; MaxCount
0x1800144e7  mov     rcx, r9; Source
0x1800144ea  call    cs:__imp_wcsnlen
0x1800144f0  mov     [rsp+78h+var_8], r12
0x1800144f5  cmp     al, 40h ; '@'
0x1800144f7  jnb     loc_180014807
0x1800144fd  mov     r12, [rbp+arg_30]
0x180014501  test    r12, r12
0x180014504  jz      loc_180014807
0x18001450a  mov     [rsp+78h+var_10], r13
0x18001450f  mov     [rsp+78h+var_18], r14
0x180014514  test    al, al
0x180014516  jnz     loc_18001484F
0x18001451c  mov     r13, [rbp+pbInput]
0x180014520  movzx   r14d, al
0x180014524  lea     ecx, [r14+40h]
0x180014528  mov     [r12], ecx
0x18001452c  test    r13, r13
0x18001452f  jz      loc_18001482E
0x180014535  cmp     [rbp+arg_28], ecx
0x180014538  jb      loc_18001482E
0x18001453e  mov     [rsp+78h+arg_0], rbx
0x180014546  mov     dword ptr [r12], 0
0x18001454e  test    rsi, rsi
0x180014551  jnz     loc_180014858
0x180014557  mov     rcx, [r15+8]
0x18001455b  xor     edx, edx
0x18001455d  mov     [rbp+cbInput], 0
0x180014564  mov     rax, [rcx]
0x180014567  movzx   ebx, word ptr [rcx+22h]
0x18001456b  mov     rax, [rax+240h]
0x180014572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014577  mov     rcx, [r15+8]
0x18001457b  xor     r15d, r15d
0x18001457e  mov     rcx, [rcx+8]
0x180014582  test    rcx, rcx
0x180014585  jz      loc_18001483C
0x18001458b  mov     rcx, [rcx]
0x18001458e  lea     rdx, [rbp+cbInput]
0x180014592  mov     [rsp+78h+var_48], r15d
0x180014597  mov     qword ptr [rsp+78h+dwFlags], rdx
0x18001459c  mov     r9, r13
0x18001459f  mov     rdx, rax
0x1800145a2  mov     dword ptr [rsp+78h+pcbResult], 40h ; '@'
0x1800145aa  mov     r8d, ebx
0x1800145ad  call    cs:__imp_SslComputeSessionHash
0x1800145b3  test    eax, eax
0x1800145b5  jnz     loc_1800147C0
0x1800145bb  mov     r8d, cs:g_dwHashInfoTotalCount
0x1800145c2  lea     r14, __ImageBase
0x1800145c9  mov     esi, r8d
0x1800145cc  mov     [rbp+hObject], r15
0x1800145d0  mov     eax, r15d
0x1800145d3  cmp     eax, r8d
0x1800145d6  jnb     short loc_1800145F2
0x1800145d8  mov     ecx, eax
0x1800145da  mov     rdx, rva g_pHashInfo[r14+rcx*8]
0x1800145e2  test    rdx, rdx
0x1800145e5  jz      short loc_1800145EC
0x1800145e7  cmp     [rdx+14h], edi
0x1800145ea  jz      short loc_1800145F0
0x1800145ec  inc     eax
0x1800145ee  jmp     short loc_1800145D3
0x1800145f0  mov     esi, eax
0x1800145f2  test    esi, esi
0x1800145f4  js      loc_180014881
0x1800145fa  cmp     esi, r8d
0x1800145fd  jge     loc_180014881
0x180014603  mov     ecx, esi
0x180014605  sub     ecx, 1
0x180014608  jz      loc_1800147E1
0x18001460e  cmp     ecx, 1
0x180014611  jz      loc_180014875
0x180014617  mov     eax, esi
0x180014619  mov     rax, rva qword_1800AE610[r14+rax*8]
0x180014621  mov     [rbp+hObject], rax
0x180014625  cmp     esi, r8d
0x180014628  jnb     loc_180014835
0x18001462e  lfence
0x180014631  mov     eax, esi
0x180014633  mov     rcx, rva g_pHashInfo[r14+rax*8]
0x18001463b  test    rcx, rcx
0x18001463e  jz      loc_180014835
0x180014644  mov     rbx, [rbp+hObject]
0x180014648  mov     edi, [rcx+8]
0x18001464b  test    rbx, rbx
0x18001464e  jz      loc_18008AEA0
0x180014654  cmp     edi, 40h ; '@'
0x180014657  ja      loc_180014889
0x18001465d  lea     rax, [rbp+var_34]
0x180014661  mov     [rsp+78h+dwFlags], r15d; dwFlags
0x180014666  mov     r9d, 4; cbOutput
0x18001466c  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180014671  lea     r8, [rbp+pbOutput]; pbOutput
0x180014675  mov     [rbp+pbOutput], r15d
0x180014679  lea     rdx, pszProperty; "ObjectLength"
0x180014680  mov     [rbp+var_34], r15d
0x180014684  mov     rcx, rbx; hObject
0x180014687  call    cs:__imp_BCryptGetProperty
0x18001468d  test    eax, eax
0x18001468f  jnz     loc_1800147C0
0x180014695  mov     rax, cs:LsaTable
0x18001469c  mov     ecx, [rbp+pbOutput]
0x18001469f  test    rax, rax
0x1800146a2  jz      loc_18001481B
0x1800146a8  mov     rax, [rax+28h]
0x1800146ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146b1  mov     rsi, rax
0x1800146b4  test    rax, rax
0x1800146b7  jz      loc_180014800
0x1800146bd  mov     r9d, [rbp+pbOutput]; cbHashObject
0x1800146c1  lea     rdx, [rbp+phHash]; phHash
0x1800146c5  mov     [rsp+78h+var_48], r15d; dwFlags
0x1800146ca  mov     r8, rax; pbHashObject
0x1800146cd  mov     [rsp+78h+dwFlags], r15d; cbSecret
0x1800146d2  mov     rcx, rbx; hAlgorithm
0x1800146d5  mov     [rsp+78h+pcbResult], r15; pbSecret
0x1800146da  mov     [rbp+phHash], r15
0x1800146de  call    cs:__imp_BCryptCreateHash
0x1800146e4  mov     ebx, eax
0x1800146e6  test    eax, eax
0x1800146e8  jnz     loc_180014793
0x1800146ee  mov     rcx, [rbp+phHash]; hHash
0x1800146f2  lea     rdx, ?LabelPrefix@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "                                       "...
0x1800146f9  xor     r9d, r9d; dwFlags
0x1800146fc  mov     r8d, 49h ; 'I'; cbInput
0x180014702  call    cs:__imp_BCryptHashData
0x180014708  mov     ebx, eax
0x18001470a  test    eax, eax
0x18001470c  jnz     loc_180014793
0x180014712  mov     rcx, [rbp+phHash]; hHash
0x180014716  xor     r9d, r9d; dwFlags
0x180014719  mov     r8d, 6; cbInput
0x18001471f  cmp     [rbp+arg_8], r9b
0x180014723  jz      loc_1800147F4
0x180014729  lea     rdx, ?LabelServer@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "server"
0x180014730  call    cs:__imp_BCryptHashData
0x180014736  mov     ebx, eax
0x180014738  test    eax, eax
0x18001473a  jnz     short loc_180014793
0x18001473c  mov     rcx, [rbp+phHash]; hHash
0x180014740  lea     rdx, ?LabelSuffix@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; " CertificateVerify"
0x180014747  xor     r9d, r9d; dwFlags
0x18001474a  mov     r8d, 13h; cbInput
0x180014750  call    cs:__imp_BCryptHashData
0x180014756  mov     ebx, eax
0x180014758  test    eax, eax
0x18001475a  jnz     short loc_180014793
0x18001475c  mov     r8d, [rbp+cbInput]; cbInput
0x180014760  xor     r9d, r9d; dwFlags
0x180014763  mov     rcx, [rbp+phHash]; hHash
0x180014767  mov     rdx, r13; pbInput
0x18001476a  call    cs:__imp_BCryptHashData
0x180014770  mov     ebx, eax
0x180014772  test    eax, eax
0x180014774  jnz     short loc_180014793
0x180014776  mov     rcx, [rbp+phHash]; hHash
0x18001477a  xor     r9d, r9d; dwFlags
0x18001477d  mov     r8d, edi; cbOutput
0x180014780  mov     rdx, r13; pbOutput
0x180014783  call    cs:__imp_BCryptFinishHash
0x180014789  mov     ebx, eax
0x18001478b  test    eax, eax
0x18001478d  jnz     short loc_180014793
0x18001478f  add     [r12], edi
0x180014793  mov     rcx, [rbp+phHash]; hHash
0x180014797  test    rcx, rcx
0x18001479a  jz      short loc_1800147A2
0x18001479c  call    cs:__imp_BCryptDestroyHash
0x1800147a2  mov     rax, cs:LsaTable
0x1800147a9  mov     rcx, rsi; hMem
0x1800147ac  test    rax, rax
0x1800147af  jz      loc_180014844
0x1800147b5  mov     rax, [rax+30h]
0x1800147b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147be  mov     eax, ebx
0x1800147c0  mov     rbx, [rsp+78h+arg_0]
0x1800147c8  mov     r13, [rsp+78h+var_10]
0x1800147cd  mov     r14, [rsp+78h+var_18]
0x1800147d2  mov     r12, [rsp+78h+var_8]
0x1800147d7  add     rsp, 78h
0x1800147db  pop     r15
0x1800147dd  pop     rdi
0x1800147de  pop     rsi
0x1800147df  pop     rbp
0x1800147e0  retn
0x1800147e1  mov     rax, cs:?g_hMD5Provider@@3PEAXEA; void * g_hMD5Provider
0x1800147e8  jmp     loc_180014621
0x1800147ed  xor     eax, eax
0x1800147ef  jmp     loc_1800144F0
0x1800147f4  lea     rdx, ?LabelClient@?1??GenerateCertVerifyContentHash@?$CTls13Handshake@VCTls13ClientContext@@VCTls13ExtClient@@@@QEAAKEW4_eTlsHashAlgorithm@@PEBGPEAEKPEAK@Z@4QBEB; "client"
0x1800147fb  jmp     loc_180014730
0x180014800  mov     eax, 0Eh
0x180014805  jmp     short loc_1800147C0
0x180014807  mov     r12, [rsp+78h+var_8]
0x18001480c  mov     eax, 57h ; 'W'
0x180014811  add     rsp, 78h
0x180014815  pop     r15
0x180014817  pop     rdi
0x180014818  pop     rsi
0x180014819  pop     rbp
0x18001481a  retn
0x18001481b  mov     rdx, rcx; uBytes
0x18001481e  mov     ecx, 40h ; '@'; uFlags
0x180014823  call    cs:__imp_LocalAlloc
0x180014829  jmp     loc_1800146B1
0x18001482e  mov     eax, 7Ah ; 'z'
0x180014833  jmp     short loc_1800147C8
0x180014835  mov     eax, 490h
0x18001483a  jmp     short loc_1800147C0
0x18001483c  mov     rcx, r15
0x18001483f  jmp     loc_18001458E
0x180014844  call    cs:__imp_LocalFree
0x18001484a  jmp     loc_1800147BE
0x18001484f  inc     al
0x180014851  add     al, al
0x180014853  jmp     loc_18001451C
0x180014858  movzx   ebx, al
0x18001485b  mov     rdx, rsi; Src
0x18001485e  mov     r8d, ebx; Size
0x180014861  mov     rcx, r13; void *
0x180014864  call    memcpy_0
0x180014869  add     r13, rbx
0x18001486c  mov     [r12], r14d
0x180014870  jmp     loc_180014557
0x180014875  mov     rax, cs:?g_hSHAProvider@@3PEAXEA; void * g_hSHAProvider
0x18001487c  jmp     loc_180014621
0x180014881  mov     esi, r15d
0x180014884  jmp     loc_180014617
0x180014889  mov     eax, 54Fh
0x18001488e  jmp     loc_1800147C0
0x18008aea0  mov     rdx, [rcx]; pszAlgId
0x18008aea3  test    rdx, rdx
0x18008aea6  jz      loc_180014889
0x18008aeac  xor     r9d, r9d; dwFlags
0x18008aeaf  lea     rcx, [rbp+hObject]; phAlgorithm
0x18008aeb3  xor     r8d, r8d; pszImplementation
0x18008aeb6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18008aebc  test    eax, eax
0x18008aebe  jnz     loc_1800147C0
0x18008aec4  mov     rcx, [rbp+hObject]
0x18008aec8  movsxd  rax, esi
0x18008aecb  lea     rdx, ds:0AE610h[rax*8]
0x18008aed3  xor     eax, eax
0x18008aed5  lock cmpxchg [rdx+r14], rcx
0x18008aedb  mov     rbx, rax
0x18008aede  jz      short loc_18008AEF5
0x18008aee0  mov     rcx, [rbp+hObject]; hAlgorithm
0x18008aee4  xor     edx, edx; dwFlags
0x18008aee6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18008aeec  mov     [rbp+hObject], rbx
0x18008aef0  jmp     loc_180014654
0x18008aef5  mov     rbx, [rbp+hObject]
0x18008aef9  jmp     loc_180014654
```
