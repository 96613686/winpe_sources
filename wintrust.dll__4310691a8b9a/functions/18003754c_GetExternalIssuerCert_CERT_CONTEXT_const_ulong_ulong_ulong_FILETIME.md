# _GetExternalIssuerCert(_CERT_CONTEXT const *,ulong,ulong *,ulong *,_FILETIME *)

- ea: `0x18003754c`
- end: `0x1800377f2`
- name: `?_GetExternalIssuerCert@@YAPEBU_CERT_CONTEXT@@PEBU1@KPEAK1PEAU_FILETIME@@@Z`
- size: `678`
- prototype: `PCCERT_CONTEXT __fastcall(const struct _CERT_CONTEXT *, DWORD, unsigned int *, unsigned int *, struct _FILETIME *pTimeToVerify)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800378c0`

## callees

- `0x18002e5d0`
- `0x18002e5dc`
- `0x18003754c`
- `0x1800377f8`
- `0x18004de6a`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800375d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800377ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800377ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037639`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003759c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003759c`
- `CRYPT32!CertCompareCertificateName` at `0x180037701`
- `CRYPT32!CertCompareCertificateName` at `0x180037701`
- `CRYPT32!CertFreeCertificateContext` at `0x18003769b`
- `CRYPT32!CertFreeCertificateContext` at `0x180037771`
- `CRYPT32!CertFreeCertificateContext` at `0x1800377a2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800377c1`
- `CRYPT32!CertFreeCertificateContext` at `0x18003769b`
- `CRYPT32!CertFreeCertificateContext` at `0x180037771`
- `CRYPT32!CertFreeCertificateContext` at `0x1800377a2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800377c1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003777e`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18003777e`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180037721`
- `CRYPT32!CertVerifySubjectCertificateContext` at `0x180037721`

## string_xrefs

- `0x180037576`: `cryptnet.dll`

## pseudocode

```c
PCCERT_CONTEXT __fastcall _GetExternalIssuerCert(
        const struct _CERT_CONTEXT *a1,
        DWORD a2,
        unsigned int *a3,
        unsigned int *a4,
        struct _FILETIME *pTimeToVerify)
{
  unsigned int v5; // r14d
  PCCERT_CONTEXT v7; // rbx
  _QWORD *v8; // rdi
  unsigned int v9; // r12d
  unsigned int *v10; // rsi
  HMODULE LibraryA; // rax
  HMODULE v12; // r15
  FARPROC ProcAddress; // rsi
  _QWORD *v14; // rax
  unsigned int v15; // esi
  PCCERT_CONTEXT result; // rax
  DWORD pdwFlags; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v18; // [rsp+54h] [rbp-1Ch] BYREF
  unsigned int v19; // [rsp+58h] [rbp-18h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-10h]
  FARPROC v21; // [rsp+68h] [rbp-8h]
  unsigned int Size; // [rsp+C0h] [rbp+50h] BYREF
  int Size_4; // [rsp+C4h] [rbp+54h]
  unsigned int *v25; // [rsp+C8h] [rbp+58h]

  v25 = a4;
  Size_4 = HIDWORD(a3);
  v5 = 0;
  *a4 = 0;
  v19 = 0;
  v7 = 0;
  pdwFlags = 0;
  v8 = 0;
  pCertContext = 0;
  v9 = 0;
  Size = 0;
  v10 = a4;
  LibraryA = LoadLibraryA("cryptnet.dll");
  v12 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "CryptGetObjectUrl");
    if ( ProcAddress )
    {
      v21 = GetProcAddress(v12, "CryptRetrieveObjectByUrlW");
      if ( v21 )
      {
        if ( ((unsigned int (__fastcall *)(__int64, const struct _CERT_CONTEXT *, _QWORD, _QWORD, unsigned int *, _QWORD, _QWORD, _QWORD))ProcAddress)(
               1,
               a1,
               0,
               0,
               &Size,
               0,
               0,
               0)
          && Size )
        {
          v14 = operator new[](Size);
          v8 = v14;
          if ( v14 )
          {
            memset_0(v14, 0, Size);
            if ( ((unsigned int (__fastcall *)(__int64, const struct _CERT_CONTEXT *, _QWORD, _QWORD *, unsigned int *, _QWORD, _QWORD, _QWORD))ProcAddress)(
                   1,
                   a1,
                   0,
                   v8,
                   &Size,
                   0,
                   0,
                   0) )
            {
              while ( v5 < *(_DWORD *)v8 )
              {
                if ( pCertContext )
                {
                  CertFreeCertificateContext(pCertContext);
                  pCertContext = 0;
                }
                if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD))v21)(*(_QWORD *)(v8[1] + 8LL * v5), 1, 0) )
                {
                  if ( CertCompareCertificateName(1u, &a1->pCertInfo->Issuer, &pCertContext->pCertInfo->Subject) )
                  {
                    pdwFlags = 1;
                    if ( CertVerifySubjectCertificateContext(a1, pCertContext, &pdwFlags) )
                    {
                      v18 = 0;
                      _SetConfidenceOnIssuer(a2, a1, pCertContext, pdwFlags, pTimeToVerify, &v19, &v18);
                      if ( !v18 )
                      {
                        v15 = v19;
                        if ( v19 > v9 )
                        {
                          if ( v7 )
                            CertFreeCertificateContext(v7);
                          v9 = v15;
                          v7 = CertDuplicateCertificateContext(pCertContext);
                        }
                        if ( v15 >= 0x11111000 )
                          goto LABEL_24;
                      }
                    }
                  }
                }
                ++v5;
              }
              if ( v7 )
              {
                CertFreeCertificateContext(v7);
                v7 = 0;
              }
            }
          }
          else
          {
            SetLastError(8u);
          }
        }
      }
    }
LABEL_24:
    FreeLibrary(v12);
    v10 = v25;
  }
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v8 )
    operator delete(v8);
  result = v7;
  *v10 = v9;
  return result;
}

```

## disassembly

```asm
0x18003754c  mov     rax, rsp
0x18003754f  mov     [rax+8], rbx
0x180037553  mov     [rax+20h], r9
0x180037557  mov     [rax+18h], r8
0x18003755b  mov     [rax+10h], edx
0x18003755e  push    rbp
0x18003755f  push    rsi
0x180037560  push    rdi
0x180037561  push    r12
0x180037563  push    r13
0x180037565  push    r14
0x180037567  push    r15
0x180037569  mov     rbp, rsp
0x18003756c  sub     rsp, 70h
0x180037570  xor     r14d, r14d
0x180037573  mov     r13, rcx
0x180037576  lea     rcx, aCryptnetDll; "cryptnet.dll"
0x18003757d  mov     [r9], r14d
0x180037580  mov     [rbp+var_18], r14d
0x180037584  mov     ebx, r14d
0x180037587  mov     [rbp+pdwFlags], r14d
0x18003758b  mov     edi, r14d
0x18003758e  mov     [rbp+pCertContext], r14
0x180037592  mov     r12d, r14d
0x180037595  mov     dword ptr [rbp+Size], r14d
0x180037599  mov     rsi, r9
0x18003759c  call    cs:__imp_LoadLibraryA
0x1800375a2  mov     r15, rax
0x1800375a5  test    rax, rax
0x1800375a8  jz      loc_1800377B8
0x1800375ae  lea     rdx, aCryptgetobject; "CryptGetObjectUrl"
0x1800375b5  mov     rcx, rax; hModule
0x1800375b8  call    cs:__imp_GetProcAddress
0x1800375be  mov     rsi, rax
0x1800375c1  test    rax, rax
0x1800375c4  jz      loc_1800377AB
0x1800375ca  lea     rdx, aCryptretrieveo; "CryptRetrieveObjectByUrlW"
0x1800375d1  mov     rcx, r15; hModule
0x1800375d4  call    cs:__imp_GetProcAddress
0x1800375da  mov     [rbp+var_8], rax
0x1800375de  test    rax, rax
0x1800375e1  jz      loc_1800377AB
0x1800375e7  mov     [rsp+70h+var_38], r14
0x1800375ec  lea     rax, [rbp+Size]
0x1800375f0  mov     [rsp+70h+var_40], r14
0x1800375f5  lea     ecx, [r14+1]
0x1800375f9  mov     [rsp+70h+var_48], r14
0x1800375fe  xor     r9d, r9d
0x180037601  mov     [rsp+70h+pTimeToVerify], rax
0x180037606  xor     r8d, r8d
0x180037609  mov     rax, rsi
0x18003760c  mov     rdx, r13
0x18003760f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037614  test    eax, eax
0x180037616  jz      loc_1800377AB
0x18003761c  cmp     dword ptr [rbp+Size], 1
0x180037620  jb      loc_1800377AB
0x180037626  mov     ecx, dword ptr [rbp+Size]; unsigned __int64
0x180037629  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003762e  mov     rdi, rax
0x180037631  test    rax, rax
0x180037634  jnz     short loc_180037644
0x180037636  lea     ecx, [rax+8]; dwErrCode
0x180037639  call    cs:__imp_SetLastError
0x18003763f  jmp     loc_1800377AB
0x180037644  mov     r8d, dword ptr [rbp+Size]; Size
0x180037648  xor     edx, edx; Val
0x18003764a  mov     rcx, rdi; void *
0x18003764d  call    memset_0
0x180037652  mov     [rsp+70h+var_38], r14
0x180037657  lea     rax, [rbp+Size]
0x18003765b  xor     r8d, r8d
0x18003765e  mov     [rsp+70h+var_40], r14
0x180037663  mov     [rsp+70h+var_48], r14
0x180037668  mov     r9, rdi
0x18003766b  mov     [rsp+70h+pTimeToVerify], rax
0x180037670  mov     rdx, r13
0x180037673  mov     rax, rsi
0x180037676  lea     ecx, [r8+1]
0x18003767a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003767f  test    eax, eax
0x180037681  jz      loc_1800377AB
0x180037687  cmp     r14d, [rdi]
0x18003768a  jnb     loc_180037797
0x180037690  mov     rcx, [rbp+pCertContext]; pCertContext
0x180037694  xor     esi, esi
0x180037696  test    rcx, rcx
0x180037699  jz      short loc_1800376A5
0x18003769b  call    cs:__imp_CertFreeCertificateContext
0x1800376a1  mov     [rbp+pCertContext], rsi
0x1800376a5  mov     rcx, [rdi+8]
0x1800376a9  lea     rdx, [rbp+pCertContext]
0x1800376ad  mov     [rsp+70h+var_30], rsi
0x1800376b2  xor     r9d, r9d
0x1800376b5  mov     [rsp+70h+var_38], rsi
0x1800376ba  xor     r8d, r8d
0x1800376bd  mov     eax, r14d
0x1800376c0  mov     [rsp+70h+var_40], rsi
0x1800376c5  mov     [rsp+70h+var_48], rsi
0x1800376ca  mov     [rsp+70h+pTimeToVerify], rdx
0x1800376cf  lea     edx, [r9+1]
0x1800376d3  mov     rcx, [rcx+rax*8]
0x1800376d7  mov     rax, [rbp+var_8]
0x1800376db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376e0  test    eax, eax
0x1800376e2  jz      loc_18003778F
0x1800376e8  mov     rax, [rbp+pCertContext]
0x1800376ec  mov     ecx, 1; dwCertEncodingType
0x1800376f1  mov     rdx, [r13+18h]
0x1800376f5  add     rdx, 30h ; '0'; pCertName1
0x1800376f9  mov     r8, [rax+18h]
0x1800376fd  add     r8, 50h ; 'P'; pCertName2
0x180037701  call    cs:__imp_CertCompareCertificateName
0x180037707  test    eax, eax
0x180037709  jz      loc_18003778F
0x18003770f  mov     rdx, [rbp+pCertContext]; pIssuer
0x180037713  lea     r8, [rbp+pdwFlags]; pdwFlags
0x180037717  mov     rcx, r13; pSubject
0x18003771a  mov     [rbp+pdwFlags], 1
0x180037721  call    cs:__imp_CertVerifySubjectCertificateContext
0x180037727  test    eax, eax
0x180037729  jz      short loc_18003778F
0x18003772b  mov     r9d, [rbp+pdwFlags]; unsigned int
0x18003772f  lea     rax, [rbp+var_1C]
0x180037733  mov     r8, [rbp+pCertContext]; struct _CERT_CONTEXT *
0x180037737  mov     rdx, r13; struct _CERT_CONTEXT *
0x18003773a  mov     ecx, [rbp+dwCertEncodingType]; dwCertEncodingType
0x18003773d  mov     [rsp+70h+var_40], rax; unsigned int *
0x180037742  lea     rax, [rbp+var_18]
0x180037746  mov     [rsp+70h+var_48], rax; unsigned int *
0x18003774b  mov     rax, [rbp+arg_20]
0x18003774f  mov     [rsp+70h+pTimeToVerify], rax; pTimeToVerify
0x180037754  mov     [rbp+var_1C], esi
0x180037757  call    ?_SetConfidenceOnIssuer@@YAXKPEBU_CERT_CONTEXT@@0KPEAU_FILETIME@@PEAK2@Z; _SetConfidenceOnIssuer(ulong,_CERT_CONTEXT const *,_CERT_CONTEXT const *,ulong,_FILETIME *,ulong *,ulong *)
0x18003775c  cmp     [rbp+var_1C], esi
0x18003775f  jnz     short loc_18003778F
0x180037761  mov     esi, [rbp+var_18]
0x180037764  cmp     esi, r12d
0x180037767  jbe     short loc_180037787
0x180037769  test    rbx, rbx
0x18003776c  jz      short loc_180037777
0x18003776e  mov     rcx, rbx; pCertContext
0x180037771  call    cs:__imp_CertFreeCertificateContext
0x180037777  mov     rcx, [rbp+pCertContext]; pCertContext
0x18003777b  mov     r12d, esi
0x18003777e  call    cs:__imp_CertDuplicateCertificateContext
0x180037784  mov     rbx, rax
0x180037787  cmp     esi, 11111000h
0x18003778d  jnb     short loc_1800377AB
0x18003778f  inc     r14d
0x180037792  jmp     loc_180037687
0x180037797  xor     r14d, r14d
0x18003779a  test    rbx, rbx
0x18003779d  jz      short loc_1800377AB
0x18003779f  mov     rcx, rbx; pCertContext
0x1800377a2  call    cs:__imp_CertFreeCertificateContext
0x1800377a8  mov     ebx, r14d
0x1800377ab  mov     rcx, r15; hLibModule
0x1800377ae  call    cs:__imp_FreeLibrary
0x1800377b4  mov     rsi, [rbp+arg_18]
0x1800377b8  mov     rcx, [rbp+pCertContext]; pCertContext
0x1800377bc  test    rcx, rcx
0x1800377bf  jz      short loc_1800377C7
0x1800377c1  call    cs:__imp_CertFreeCertificateContext
0x1800377c7  test    rdi, rdi
0x1800377ca  jz      short loc_1800377D4
0x1800377cc  mov     rcx, rdi; Block
0x1800377cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800377d4  mov     rax, rbx
0x1800377d7  mov     [rsi], r12d
0x1800377da  mov     rbx, [rsp+70h+arg_0]
0x1800377e2  add     rsp, 70h
0x1800377e6  pop     r15
0x1800377e8  pop     r14
0x1800377ea  pop     r13
0x1800377ec  pop     r12
0x1800377ee  pop     rdi
0x1800377ef  pop     rsi
0x1800377f0  pop     rbp
0x1800377f1  retn
```
