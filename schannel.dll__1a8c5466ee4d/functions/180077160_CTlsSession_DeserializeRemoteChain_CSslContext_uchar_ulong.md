# CTlsSession::DeserializeRemoteChain(CSslContext *,uchar *,ulong)

- ea: `0x180077160`
- end: `0x1800772a7`
- name: `?DeserializeRemoteChain@CTlsSession@@AEAAKPEAVCSslContext@@PEAEK@Z`
- size: `327`
- prototype: `unsigned int(CTlsSession *__hidden this, struct CSslContext *, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180077000`

## callees

- `0x180014240`
- `0x180021eb0`
- `0x180053df8`
- `0x180057c8c`
- `0x180077160`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077220`
- `CRYPT32!CertFreeCertificateContext` at `0x18007726c`
- `CRYPT32!CertFreeCertificateContext` at `0x18007726c`
- `CRYPT32!CertCreateCertificateContext` at `0x180077212`
- `CRYPT32!CertCreateCertificateContext` at `0x180077212`

## pseudocode

```c
DWORD __fastcall CTlsSession::DeserializeRemoteChain(
        CTlsSession *this,
        struct CSslContext *a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  size_t v5; // rdi
  unsigned __int64 v8; // r8
  const struct _CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v10; // rbp
  unsigned int PublicKeyFromCert; // esi
  void *v12; // rax
  struct _PUBLICKEY *v13; // [rsp+60h] [rbp+8h] BYREF

  v5 = a4;
  if ( !*((_QWORD *)this + 2) && !*((_DWORD *)this + 6) && !*((_QWORD *)this + 4) && !*((_QWORD *)this + 5) )
  {
    if ( a2 )
    {
      if ( !a4 )
      {
        if ( (*((_DWORD *)a2 + 464) & 0x100LL) != 0 )
        {
          if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_760271da25583b4008385e155c125333_Traceguids);
          }
          return 87;
        }
        return 0;
      }
      if ( a3 )
      {
        if ( a4 > 4 )
        {
          v8 = *(unsigned int *)a3;
          if ( (unsigned __int64)a4 - 4 >= v8 )
          {
            CertificateContext = CertCreateCertificateContext(1u, a3 + 4, v8);
            v10 = CertificateContext;
            if ( !CertificateContext )
              return GetLastError();
            v13 = 0;
            PublicKeyFromCert = GetPublicKeyFromCert(CertificateContext, &v13, 0);
            if ( !PublicKeyFromCert )
            {
              v12 = SPExternalAlloc((unsigned int)v5);
              *((_QWORD *)this + 2) = v12;
              if ( v12 )
              {
                *((_QWORD *)this + 4) = v13;
                *((_QWORD *)this + 5) = v10;
                memcpy_0(v12, a3, v5);
                *((_DWORD *)this + 6) = v5;
                return 0;
              }
              SPExternalFree(v13);
              PublicKeyFromCert = 14;
            }
            CertFreeCertificateContext(v10);
            return PublicKeyFromCert;
          }
        }
      }
    }
    return 87;
  }
  return 1359;
}

```

## disassembly

```asm
0x180077160  push    rbx
0x180077162  push    rbp
0x180077163  push    rsi
0x180077164  push    rdi
0x180077165  push    r14
0x180077167  push    r15
0x180077169  sub     rsp, 28h
0x18007716d  cmp     qword ptr [rcx+10h], 0
0x180077172  mov     r14, r8
0x180077175  mov     edi, r9d
0x180077178  mov     rbx, rcx
0x18007717b  jnz     loc_180077295
0x180077181  cmp     dword ptr [rcx+18h], 0
0x180077185  jnz     loc_180077295
0x18007718b  cmp     qword ptr [rcx+20h], 0
0x180077190  jnz     loc_180077295
0x180077196  cmp     qword ptr [rcx+28h], 0
0x18007719b  jnz     loc_180077295
0x1800771a1  test    rdx, rdx
0x1800771a4  jz      short loc_1800771E9
0x1800771a6  test    r9d, r9d
0x1800771a9  jnz     short loc_1800771F3
0x1800771ab  mov     eax, [rdx+740h]
0x1800771b1  bt      rax, 8
0x1800771b6  jnb     loc_180077291
0x1800771bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800771c3  lea     rax, WPP_GLOBAL_Control
0x1800771ca  cmp     rcx, rax
0x1800771cd  jz      short loc_1800771E9
0x1800771cf  test    byte ptr [rcx+1Ch], 2
0x1800771d3  jz      short loc_1800771E9
0x1800771d5  mov     rcx, [rcx+10h]
0x1800771d9  lea     edx, [r9+11h]
0x1800771dd  lea     r8, WPP_760271da25583b4008385e155c125333_Traceguids
0x1800771e4  call    WPP_SF_
0x1800771e9  mov     eax, 57h ; 'W'
0x1800771ee  jmp     loc_18007729A
0x1800771f3  test    r14, r14
0x1800771f6  jz      short loc_1800771E9
0x1800771f8  cmp     edi, 4
0x1800771fb  jbe     short loc_1800771E9
0x1800771fd  mov     r8d, [r8]; cbCertEncoded
0x180077200  lea     rax, [rdi-4]
0x180077204  cmp     rax, r8
0x180077207  jb      short loc_1800771E9
0x180077209  lea     rdx, [r14+4]; pbCertEncoded
0x18007720d  mov     ecx, 1; dwCertEncodingType
0x180077212  call    cs:__imp_CertCreateCertificateContext
0x180077218  mov     rbp, rax
0x18007721b  test    rax, rax
0x18007721e  jnz     short loc_180077228
0x180077220  call    cs:__imp_GetLastError
0x180077226  jmp     short loc_18007729A
0x180077228  xor     r8d, r8d; enum _eTlsSignatureAlgorithm *
0x18007722b  mov     [rsp+58h+arg_0], 0
0x180077234  lea     rdx, [rsp+58h+arg_0]; struct _PUBLICKEY **
0x180077239  mov     rcx, rbp; struct _CERT_CONTEXT *
0x18007723c  call    ?GetPublicKeyFromCert@@YAKPEBU_CERT_CONTEXT@@PEAPEAU_PUBLICKEY@@PEAW4_eTlsSignatureAlgorithm@@@Z; GetPublicKeyFromCert(_CERT_CONTEXT const *,_PUBLICKEY * *,_eTlsSignatureAlgorithm *)
0x180077241  mov     esi, eax
0x180077243  test    eax, eax
0x180077245  jnz     short loc_180077269
0x180077247  mov     ecx, edi; uBytes
0x180077249  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18007724e  mov     [rbx+10h], rax
0x180077252  mov     rcx, rax; void *
0x180077255  test    rax, rax
0x180077258  jnz     short loc_180077276
0x18007725a  mov     rcx, [rsp+58h+arg_0]; void *
0x18007725f  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180077264  mov     esi, 0Eh
0x180077269  mov     rcx, rbp; pCertContext
0x18007726c  call    cs:__imp_CertFreeCertificateContext
0x180077272  mov     eax, esi
0x180077274  jmp     short loc_18007729A
0x180077276  mov     rax, [rsp+58h+arg_0]
0x18007727b  mov     r8, rdi; Size
0x18007727e  mov     rdx, r14; Src
0x180077281  mov     [rbx+20h], rax
0x180077285  mov     [rbx+28h], rbp
0x180077289  call    memcpy_0
0x18007728e  mov     [rbx+18h], edi
0x180077291  xor     eax, eax
0x180077293  jmp     short loc_18007729A
0x180077295  mov     eax, 54Fh
0x18007729a  add     rsp, 28h
0x18007729e  pop     r15
0x1800772a0  pop     r14
0x1800772a2  pop     rdi
0x1800772a3  pop     rsi
0x1800772a4  pop     rbp
0x1800772a5  pop     rbx
0x1800772a6  retn
```
