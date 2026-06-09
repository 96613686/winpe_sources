# TSGetCertificateByHash(uchar *,ulong,ushort *,int,_CERT_CONTEXT const * *)

- ea: `0x180018fb0`
- end: `0x1800190b6`
- name: `?TSGetCertificateByHash@@YAJPEAEKPEAGHPEAPEBU_CERT_CONTEXT@@@Z`
- size: `262`
- prototype: `int(unsigned __int8 *, unsigned int, unsigned __int16 *, int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005520`

## callees

- `0x180018fb0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800190a3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800190a3`
- `CRYPT32!CertFreeCertificateContext` at `0x18001908e`
- `CRYPT32!CertFreeCertificateContext` at `0x18001908e`
- `CRYPT32!CertOpenStore` at `0x18001900e`
- `CRYPT32!CertOpenStore` at `0x18001900e`
- `CRYPT32!CertFindCertificateInStore` at `0x180019053`
- `CRYPT32!CertFindCertificateInStore` at `0x180019053`
- `CRYPT32!CertCloseStore` at `0x180019099`
- `CRYPT32!CertCloseStore` at `0x180019099`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001906b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001906b`

## pseudocode

```c
__int64 __fastcall TSGetCertificateByHash(
        unsigned __int8 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        int a4,
        const struct _CERT_CONTEXT **a5)
{
  int v7; // esi
  DWORD v8; // r9d
  int v9; // ebx
  HCERTSTORE v10; // rbp
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v12; // rdi
  const struct _CERT_CONTEXT *v13; // rcx
  __int128 pvFindPara; // [rsp+30h] [rbp-38h] BYREF

  pvFindPara = 0;
  if ( a4 )
  {
    v7 = 0;
    v8 = 0x20000;
    v9 = 0;
  }
  else
  {
    v9 = TSGlobalLsaFunctions->ImpersonateClient();
    if ( v9 < 0 )
      return (unsigned int)v9;
    v7 = 1;
    v8 = 0x10000;
  }
  v10 = CertOpenStore((LPCSTR)0xA, 1u, 0, v8, a3);
  if ( v10 )
  {
    LODWORD(pvFindPara) = 20;
    *((_QWORD *)&pvFindPara + 1) = a1;
    CertificateInStore = CertFindCertificateInStore(v10, 1u, 0, 0x10000u, &pvFindPara, 0);
    v12 = CertificateInStore;
    if ( CertificateInStore )
    {
      v13 = CertDuplicateCertificateContext(CertificateInStore);
      if ( v13 )
        *a5 = v13;
      else
        v9 = -1073741670;
      CertFreeCertificateContext(v12);
    }
    else
    {
      v9 = -2146893042;
    }
    CertCloseStore(v10, 0);
  }
  else
  {
    v9 = -1073741670;
  }
  if ( v7 )
    RevertToSelf();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180018fb0  push    rbx
0x180018fb2  push    rbp
0x180018fb3  push    rsi
0x180018fb4  push    rdi
0x180018fb5  push    r14
0x180018fb7  sub     rsp, 40h
0x180018fbb  xorps   xmm0, xmm0
0x180018fbe  mov     rdi, r8
0x180018fc1  mov     r14, rcx
0x180018fc4  movups  [rsp+68h+pvFindPara], xmm0
0x180018fc9  test    r9d, r9d
0x180018fcc  jz      short loc_180018FDA
0x180018fce  xor     esi, esi
0x180018fd0  mov     r9d, 20000h
0x180018fd6  xor     ebx, ebx
0x180018fd8  jmp     short loc_180018FFF
0x180018fda  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180018fe1  mov     rax, [rax+58h]
0x180018fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fea  mov     ebx, eax
0x180018fec  test    eax, eax
0x180018fee  js      loc_1800190A9
0x180018ff4  mov     esi, 1
0x180018ff9  mov     r9d, 10000h; dwFlags
0x180018fff  xor     r8d, r8d; hCryptProv
0x180019002  mov     [rsp+68h+pvPara], rdi; pvPara
0x180019007  lea     edx, [r8+1]; dwEncodingType
0x18001900b  lea     ecx, [rdx+9]; lpszStoreProvider
0x18001900e  call    cs:__imp_CertOpenStore
0x180019014  mov     rbp, rax
0x180019017  test    rax, rax
0x18001901a  jnz     short loc_180019023
0x18001901c  mov     ebx, 0C000009Ah
0x180019021  jmp     short loc_18001909F
0x180019023  xor     r8d, r8d; dwFindFlags
0x180019026  mov     [rsp+68h+pPrevCertContext], 0; pPrevCertContext
0x18001902f  lea     rax, [rsp+68h+pvFindPara]
0x180019034  mov     dword ptr [rsp+68h+pvFindPara], 14h
0x18001903c  mov     r9d, 10000h; dwFindType
0x180019042  mov     qword ptr [rsp+68h+pvFindPara+8], r14
0x180019047  mov     rcx, rbp; hCertStore
0x18001904a  mov     [rsp+68h+pvPara], rax; pvFindPara
0x18001904f  lea     edx, [r8+1]; dwCertEncodingType
0x180019053  call    cs:__imp_CertFindCertificateInStore
0x180019059  mov     rdi, rax
0x18001905c  test    rax, rax
0x18001905f  jnz     short loc_180019068
0x180019061  mov     ebx, 8009030Eh
0x180019066  jmp     short loc_180019094
0x180019068  mov     rcx, rdi; pCertContext
0x18001906b  call    cs:__imp_CertDuplicateCertificateContext
0x180019071  mov     rcx, rax
0x180019074  test    rax, rax
0x180019077  jnz     short loc_180019080
0x180019079  mov     ebx, 0C000009Ah
0x18001907e  jmp     short loc_18001908B
0x180019080  mov     rax, [rsp+68h+arg_20]
0x180019088  mov     [rax], rcx
0x18001908b  mov     rcx, rdi; pCertContext
0x18001908e  call    cs:__imp_CertFreeCertificateContext
0x180019094  xor     edx, edx; dwFlags
0x180019096  mov     rcx, rbp; hCertStore
0x180019099  call    cs:__imp_CertCloseStore
0x18001909f  test    esi, esi
0x1800190a1  jz      short loc_1800190A9
0x1800190a3  call    cs:__imp_RevertToSelf
0x1800190a9  mov     eax, ebx
0x1800190ab  add     rsp, 40h
0x1800190af  pop     r14
0x1800190b1  pop     rdi
0x1800190b2  pop     rsi
0x1800190b3  pop     rbp
0x1800190b4  pop     rbx
0x1800190b5  retn
```
