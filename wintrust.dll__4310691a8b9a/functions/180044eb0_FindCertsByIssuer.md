# FindCertsByIssuer

- ea: `0x180044eb0`
- end: `0x18004526b`
- name: `FindCertsByIssuer`
- size: `955`
- prototype: `HRESULT __stdcall(PCERT_CHAIN pCertChains, DWORD *pcbCertChains, DWORD *pcCertChains, BYTE *pbEncodedIssuerName, DWORD cbEncodedIssuerName, LPCWSTR pwszPurpose, DWORD dwKeySpec)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180044490`
- `0x1800444ac`
- `0x180044674`
- `0x1800447c4`
- `0x180044d30`
- `0x180044e2c`
- `0x180044eb0`
- `0x18004de52`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004519e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004519e`
- `CRYPT32!CertOpenSystemStoreA` at `0x180044ee6`
- `CRYPT32!CertOpenSystemStoreA` at `0x180044ee6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180044f56`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180044fe6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180044f56`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180044fe6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800450d6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800450d6`
- `CRYPT32!CertCloseStore` at `0x180044f01`
- `CRYPT32!CertCloseStore` at `0x180045210`
- `CRYPT32!CertCloseStore` at `0x18004523e`
- `CRYPT32!CertCloseStore` at `0x180044f01`
- `CRYPT32!CertCloseStore` at `0x180045210`
- `CRYPT32!CertCloseStore` at `0x18004523e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800451df`
- `CRYPT32!CertFreeCertificateContext` at `0x1800451df`

## pseudocode

```c
HRESULT __stdcall FindCertsByIssuer(
        PCERT_CHAIN pCertChains,
        DWORD *pcbCertChains,
        DWORD *pcCertChains,
        BYTE *pbEncodedIssuerName,
        DWORD cbEncodedIssuerName,
        LPCWSTR pwszPurpose,
        DWORD dwKeySpec)
{
  DWORD *v7; // r15
  PCERT_CHAIN v8; // r12
  void **CaStoreList; // rbp
  __int64 v10; // rsi
  HCERTSTORE v11; // rax
  void *v12; // rbx
  void **MyStoreList; // r14
  void *v14; // rdi
  void **v15; // r13
  DWORD v16; // r8d
  int v17; // edx
  DWORD v18; // ebx
  int v19; // r12d
  const CERT_CONTEXT *v20; // r15
  DWORD v21; // r13d
  __int64 ChainInfo; // rax
  DWORD v23; // edx
  DWORD v24; // ecx
  HRESULT v25; // ebx
  DWORD v26; // ecx
  DWORD v27; // eax
  __int64 v28; // rdi
  struct _CRYPTOAPI_BLOB *v29; // r15
  struct _CRYPTOAPI_BLOB *v30; // rbx
  DWORD v31; // r13d
  const CERT_CONTEXT *v32; // rcx
  void **v33; // rdx
  DWORD v34; // ecx
  signed int LastError; // eax
  int v36; // edi
  __int64 v37; // r15
  void *v38; // rax
  void **v39; // rdi
  void *v40; // rax
  void **v41; // rdi
  int v43; // [rsp+30h] [rbp-58h]
  int v44; // [rsp+30h] [rbp-58h]
  DWORD pcbData; // [rsp+34h] [rbp-54h] BYREF
  void **v46; // [rsp+38h] [rbp-50h]

  v7 = pcbCertChains;
  v8 = pCertChains;
  CaStoreList = 0;
  v10 = 0;
  v11 = CertOpenSystemStoreA(0, "My");
  v12 = v11;
  if ( v11 )
  {
    GetAndIe30ClientAuthCertificates(v11);
    CertCloseStore(v12, 0);
  }
  MyStoreList = (void **)GetMyStoreList();
  if ( MyStoreList && (CaStoreList = (void **)GetCaStoreList()) != 0 )
  {
    v14 = *MyStoreList;
    v15 = MyStoreList + 1;
    v16 = 0;
    v46 = MyStoreList + 1;
    v17 = 0;
    pcbData = 0;
    v18 = 0;
    v43 = 0;
    if ( v14 )
    {
      v19 = 0;
      do
      {
        v20 = CertEnumCertificatesInStore(v14, 0);
        if ( v20 )
        {
          v21 = pcbData;
          do
          {
            pcbData = 0;
            if ( (unsigned int)CheckKeyProvInfo(v20, dwKeySpec) )
            {
              ChainInfo = CreateChainInfo(v20, pbEncodedIssuerName, (__int64)MyStoreList);
              if ( ChainInfo )
              {
                v23 = pcbData + 7;
                *(_QWORD *)(ChainInfo + 144) = v10;
                v23 &= 0xFFFFFFF8;
                ++v18;
                v10 = ChainInfo;
                v24 = v23 + *(_DWORD *)(ChainInfo + 140);
                *(_DWORD *)(ChainInfo + 136) = v23;
                v19 += v24;
                v21 += *(_DWORD *)ChainInfo;
              }
            }
            v20 = CertEnumCertificatesInStore(v14, v20);
          }
          while ( v20 );
          pcbData = v21;
          v15 = v46;
          v43 = v19;
        }
        v14 = *v15++;
        v46 = v15;
      }
      while ( v14 );
      v8 = pCertChains;
      v17 = v43;
      v16 = pcbData;
      v7 = pcbCertChains;
    }
    if ( v18 )
    {
      v26 = v17 + 16 * (v16 + 4 * v18);
      if ( !v8 )
        *v7 = 0;
      v27 = *v7;
      *pcCertChains = v18;
      *v7 = v26;
      if ( v27 )
      {
        if ( v27 < v26 )
        {
          v25 = -2147024872;
          goto LABEL_43;
        }
        v28 = v10;
        v29 = (struct _CRYPTOAPI_BLOB *)&v8[(unsigned __int64)v18];
        v30 = &v29[v16];
        while ( v28 )
        {
          v31 = *(_DWORD *)v28;
          v8->cCerts = *(_DWORD *)v28;
          v8->certs = v29;
          v44 = v17 - *(_DWORD *)(v28 + 136);
          pcbData = *(_DWORD *)(v28 + 136);
          if ( v44 < 0
            || (v32 = *(const CERT_CONTEXT **)(v28 + 8),
                v46 = (void **)(v28 + 8),
                !CertGetCertificateContextProperty(v32, 2u, v30, &pcbData)) )
          {
LABEL_33:
            v25 = -2147418113;
            goto LABEL_38;
          }
          v33 = v46;
          *(struct _CRYPTOAPI_BLOB *)&v8->keyLocatorInfo.pwszContainerName = *v30;
          *(struct _CRYPTOAPI_BLOB *)&v8->keyLocatorInfo.dwProvType = v30[1];
          *(struct _CRYPTOAPI_BLOB *)&v8->keyLocatorInfo.rgProvParam = v30[2];
          v30 = (struct _CRYPTOAPI_BLOB *)((char *)v30 + *(unsigned int *)(v28 + 136));
          while ( v31 )
          {
            v34 = *((_DWORD *)*v33 + 4);
            pcbData = v34;
            v44 -= (v34 + 7) & 0xFFFFFFF8;
            if ( v44 < 0 )
              goto LABEL_33;
            v29->cbData = v34;
            v29->pbData = (BYTE *)v30;
            memcpy_0(v30, *((const void **)*v33 + 1), v34);
            v33 = v46 + 1;
            v30 = (struct _CRYPTOAPI_BLOB *)((char *)v30 + ((pcbData + 7) & 0xFFFFFFF8));
            ++v46;
            --v31;
            ++v29;
          }
          v28 = *(_QWORD *)(v28 + 144);
          ++v8;
          v17 = v44;
        }
      }
      v25 = 0;
      goto LABEL_43;
    }
    v25 = -2146885628;
  }
  else if ( GetLastError() <= 0xFFFF )
  {
    LastError = GetLastError();
    v25 = LastError;
    if ( LastError > 0 )
      v25 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v25 = GetLastError();
  }
LABEL_38:
  *pcbCertChains = 0;
  *pcCertChains = 0;
LABEL_43:
  while ( v10 )
  {
    v36 = *(_DWORD *)v10;
    v37 = v10;
    while ( v36 )
      CertFreeCertificateContext(*(PCCERT_CONTEXT *)(v10 + 8LL * (unsigned int)--v36 + 8));
    v10 = *(_QWORD *)(v10 + 144);
    ACFree(v37);
  }
  if ( MyStoreList )
  {
    v38 = *MyStoreList;
    v39 = MyStoreList + 1;
    while ( v38 )
    {
      CertCloseStore(v38, 0);
      v38 = *v39++;
    }
    ACFree(MyStoreList);
  }
  if ( CaStoreList )
  {
    v40 = *CaStoreList;
    v41 = CaStoreList + 1;
    while ( v40 )
    {
      CertCloseStore(v40, 0);
      v40 = *v41++;
    }
    ACFree(CaStoreList);
  }
  return v25;
}

```

## disassembly

```asm
0x180044eb0  mov     rax, rsp
0x180044eb3  mov     [rax+20h], r9
0x180044eb7  mov     [rax+18h], r8
0x180044ebb  mov     [rax+10h], rdx
0x180044ebf  mov     [rax+8], rcx
0x180044ec3  push    rbx
0x180044ec4  push    rbp
0x180044ec5  push    rsi
0x180044ec6  push    rdi
0x180044ec7  push    r12
0x180044ec9  push    r13
0x180044ecb  push    r14
0x180044ecd  push    r15
0x180044ecf  sub     rsp, 48h
0x180044ed3  mov     r15, rdx
0x180044ed6  mov     r12, rcx
0x180044ed9  lea     rdx, szSubsystemProtocol; "My"
0x180044ee0  xor     ecx, ecx; hProv
0x180044ee2  xor     ebp, ebp
0x180044ee4  xor     esi, esi
0x180044ee6  call    cs:__imp_CertOpenSystemStoreA
0x180044eec  mov     rbx, rax
0x180044eef  test    rax, rax
0x180044ef2  jz      short loc_180044F07
0x180044ef4  mov     rcx, rax
0x180044ef7  call    GetAndIe30ClientAuthCertificates
0x180044efc  xor     edx, edx; dwFlags
0x180044efe  mov     rcx, rbx; hCertStore
0x180044f01  call    cs:__imp_CertCloseStore
0x180044f07  call    GetMyStoreList
0x180044f0c  mov     r14, rax
0x180044f0f  test    rax, rax
0x180044f12  jz      loc_180045187
0x180044f18  call    GetCaStoreList
0x180044f1d  mov     rbp, rax
0x180044f20  test    rax, rax
0x180044f23  jz      loc_180045187
0x180044f29  mov     rdi, [r14]
0x180044f2c  lea     r13, [r14+8]
0x180044f30  xor     r8d, r8d
0x180044f33  mov     [rsp+88h+var_50], r13
0x180044f38  xor     edx, edx
0x180044f3a  mov     [rsp+88h+pcbData], r8d
0x180044f3f  xor     ebx, ebx
0x180044f41  mov     [rsp+88h+var_58], edx
0x180044f45  test    rdi, rdi
0x180044f48  jz      loc_180045036
0x180044f4e  mov     r12d, edx
0x180044f51  xor     edx, edx; pPrevCertContext
0x180044f53  mov     rcx, rdi; hCertStore
0x180044f56  call    cs:__imp_CertEnumCertificatesInStore
0x180044f5c  mov     r15, rax
0x180044f5f  test    rax, rax
0x180044f62  jz      loc_180045007
0x180044f68  mov     r13d, [rsp+88h+pcbData]
0x180044f6d  mov     edx, [rsp+88h+dwKeySpec]; dwKeySpec
0x180044f74  lea     r8, [rsp+88h+pcbData]
0x180044f79  mov     rcx, r15; pCertContext
0x180044f7c  mov     [rsp+88h+pcbData], 0
0x180044f84  call    CheckKeyProvInfo
0x180044f89  test    eax, eax
0x180044f8b  jz      short loc_180044FE0
0x180044f8d  mov     r8d, [rsp+88h+cbEncodedIssuerName]
0x180044f95  mov     r9, rbp
0x180044f98  mov     rdx, [rsp+88h+Buf1]; Buf1
0x180044fa0  mov     rcx, r15; pSubjectContext
0x180044fa3  mov     [rsp+88h+var_68], r14; __int64
0x180044fa8  call    CreateChainInfo
0x180044fad  test    rax, rax
0x180044fb0  jz      short loc_180044FE0
0x180044fb2  mov     edx, [rsp+88h+pcbData]
0x180044fb6  mov     ecx, 0FFFFFFF8h
0x180044fbb  add     edx, 7
0x180044fbe  mov     [rax+90h], rsi
0x180044fc5  and     edx, ecx
0x180044fc7  inc     ebx
0x180044fc9  mov     ecx, [rax+8Ch]
0x180044fcf  mov     rsi, rax
0x180044fd2  add     ecx, edx
0x180044fd4  mov     [rax+88h], edx
0x180044fda  add     r12d, ecx
0x180044fdd  add     r13d, [rax]
0x180044fe0  mov     rdx, r15; pPrevCertContext
0x180044fe3  mov     rcx, rdi; hCertStore
0x180044fe6  call    cs:__imp_CertEnumCertificatesInStore
0x180044fec  mov     r15, rax
0x180044fef  test    rax, rax
0x180044ff2  jnz     loc_180044F6D
0x180044ff8  mov     [rsp+88h+pcbData], r13d
0x180044ffd  mov     r13, [rsp+88h+var_50]
0x180045002  mov     [rsp+88h+var_58], r12d
0x180045007  mov     rdi, [r13+0]
0x18004500b  add     r13, 8
0x18004500f  mov     [rsp+88h+var_50], r13
0x180045014  test    rdi, rdi
0x180045017  jnz     loc_180044F51
0x18004501d  mov     r12, [rsp+88h+arg_0]
0x180045025  mov     edx, [rsp+88h+var_58]
0x180045029  mov     r8d, [rsp+88h+pcbData]
0x18004502e  mov     r15, [rsp+88h+arg_8]
0x180045036  test    ebx, ebx
0x180045038  jnz     short loc_180045044
0x18004503a  mov     ebx, 80092004h
0x18004503f  jmp     loc_1800451B3
0x180045044  lea     ecx, [r8+rbx*4]
0x180045048  shl     ecx, 4
0x18004504b  add     ecx, edx
0x18004504d  test    r12, r12
0x180045050  jnz     short loc_180045055
0x180045052  mov     [r15], r12d
0x180045055  mov     eax, [r15]
0x180045058  mov     r9, [rsp+88h+arg_10]
0x180045060  mov     [r9], ebx
0x180045063  mov     [r15], ecx
0x180045066  test    eax, eax
0x180045068  jnz     short loc_180045071
0x18004506a  xor     ebx, ebx
0x18004506c  jmp     loc_1800451F8
0x180045071  cmp     eax, ecx
0x180045073  jnb     short loc_18004507F
0x180045075  mov     ebx, 80070018h
0x18004507a  jmp     loc_1800451F8
0x18004507f  mov     r15d, ebx
0x180045082  mov     rdi, rsi
0x180045085  shl     r15, 6
0x180045089  mov     ebx, r8d
0x18004508c  add     r15, r12
0x18004508f  shl     rbx, 4
0x180045093  add     rbx, r15
0x180045096  test    rdi, rdi
0x180045099  jz      short loc_18004506A
0x18004509b  mov     r13d, [rdi]
0x18004509e  mov     [r12], r13d
0x1800450a2  mov     [r12+8], r15
0x1800450a7  mov     eax, [rdi+88h]
0x1800450ad  sub     edx, eax
0x1800450af  mov     [rsp+88h+var_58], edx
0x1800450b3  mov     [rsp+88h+pcbData], eax
0x1800450b7  js      loc_180045180
0x1800450bd  lea     rax, [rdi+8]
0x1800450c1  mov     r8, rbx; pvData
0x1800450c4  mov     rcx, [rax]; pCertContext
0x1800450c7  lea     r9, [rsp+88h+pcbData]; pcbData
0x1800450cc  mov     edx, 2; dwPropId
0x1800450d1  mov     [rsp+88h+var_50], rax
0x1800450d6  call    cs:__imp_CertGetCertificateContextProperty
0x1800450dc  test    eax, eax
0x1800450de  jz      loc_180045180
0x1800450e4  movups  xmm0, xmmword ptr [rbx]
0x1800450e7  mov     rdx, [rsp+88h+var_50]
0x1800450ec  movups  xmmword ptr [r12+10h], xmm0
0x1800450f2  movups  xmm1, xmmword ptr [rbx+10h]
0x1800450f6  movups  xmmword ptr [r12+20h], xmm1
0x1800450fc  movups  xmm0, xmmword ptr [rbx+20h]
0x180045100  movups  xmmword ptr [r12+30h], xmm0
0x180045106  mov     eax, [rdi+88h]
0x18004510c  add     rbx, rax
0x18004510f  test    r13d, r13d
0x180045112  jz      short loc_18004516C
0x180045114  mov     rax, [rdx]
0x180045117  mov     ecx, [rax+10h]
0x18004511a  mov     [rsp+88h+pcbData], ecx
0x18004511e  lea     eax, [rcx+7]
0x180045121  and     eax, 0FFFFFFF8h
0x180045124  sub     [rsp+88h+var_58], eax
0x180045128  js      short loc_180045180
0x18004512a  mov     [r15], ecx
0x18004512d  mov     r8d, ecx; Size
0x180045130  mov     [r15+8], rbx
0x180045134  mov     rcx, rbx; void *
0x180045137  mov     rdx, [rdx]
0x18004513a  mov     rdx, [rdx+8]; Src
0x18004513e  call    memcpy_0
0x180045143  mov     eax, [rsp+88h+pcbData]
0x180045147  mov     ecx, 0FFFFFFF8h
0x18004514c  mov     rdx, [rsp+88h+var_50]
0x180045151  add     eax, 7
0x180045154  and     rax, rcx
0x180045157  add     rdx, 8
0x18004515b  add     rbx, rax
0x18004515e  mov     [rsp+88h+var_50], rdx
0x180045163  dec     r13d
0x180045166  add     r15, 10h
0x18004516a  jmp     short loc_18004510F
0x18004516c  mov     rdi, [rdi+90h]
0x180045173  add     r12, 40h ; '@'
0x180045177  mov     edx, [rsp+88h+var_58]
0x18004517b  jmp     loc_180045096
0x180045180  mov     ebx, 8000FFFFh
0x180045185  jmp     short loc_1800451B3
0x180045187  call    cs:__imp_GetLastError
0x18004518d  cmp     eax, 0FFFFh
0x180045192  jbe     short loc_18004519E
0x180045194  call    cs:__imp_GetLastError
0x18004519a  mov     ebx, eax
0x18004519c  jmp     short loc_1800451B3
0x18004519e  call    cs:__imp_GetLastError
0x1800451a4  mov     ebx, eax
0x1800451a6  test    eax, eax
0x1800451a8  jle     short loc_1800451B3
0x1800451aa  movzx   ebx, ax
0x1800451ad  or      ebx, 80070000h
0x1800451b3  mov     rax, [rsp+88h+arg_8]
0x1800451bb  mov     dword ptr [rax], 0
0x1800451c1  mov     rax, [rsp+88h+arg_10]
0x1800451c9  mov     dword ptr [rax], 0
0x1800451cf  jmp     short loc_1800451F8
0x1800451d1  mov     edi, [rsi]
0x1800451d3  mov     r15, rsi
0x1800451d6  jmp     short loc_1800451E5
0x1800451d8  dec     edi
0x1800451da  mov     rcx, [rsi+rdi*8+8]; pCertContext
0x1800451df  call    cs:__imp_CertFreeCertificateContext
0x1800451e5  test    edi, edi
0x1800451e7  jnz     short loc_1800451D8
0x1800451e9  mov     rsi, [rsi+90h]
0x1800451f0  mov     rcx, r15
0x1800451f3  call    ACFree
0x1800451f8  test    rsi, rsi
0x1800451fb  jnz     short loc_1800451D1
0x1800451fd  test    r14, r14
0x180045200  jz      short loc_18004522A
0x180045202  mov     rax, [r14]
0x180045205  lea     rdi, [r14+8]
0x180045209  jmp     short loc_18004521D
0x18004520b  xor     edx, edx; dwFlags
0x18004520d  mov     rcx, rax; hCertStore
0x180045210  call    cs:__imp_CertCloseStore
0x180045216  mov     rax, [rdi]
0x180045219  lea     rdi, [rdi+8]
0x18004521d  test    rax, rax
0x180045220  jnz     short loc_18004520B
0x180045222  mov     rcx, r14
0x180045225  call    ACFree
0x18004522a  test    rbp, rbp
0x18004522d  jz      short loc_180045258
0x18004522f  mov     rax, [rbp+0]
0x180045233  lea     rdi, [rbp+8]
0x180045237  jmp     short loc_18004524B
0x180045239  xor     edx, edx; dwFlags
0x18004523b  mov     rcx, rax; hCertStore
0x18004523e  call    cs:__imp_CertCloseStore
0x180045244  mov     rax, [rdi]
0x180045247  lea     rdi, [rdi+8]
0x18004524b  test    rax, rax
0x18004524e  jnz     short loc_180045239
0x180045250  mov     rcx, rbp
0x180045253  call    ACFree
0x180045258  mov     eax, ebx
0x18004525a  add     rsp, 48h
0x18004525e  pop     r15
0x180045260  pop     r14
0x180045262  pop     r13
0x180045264  pop     r12
0x180045266  pop     rdi
0x180045267  pop     rsi
0x180045268  pop     rbp
0x180045269  pop     rbx
0x18004526a  retn
```
