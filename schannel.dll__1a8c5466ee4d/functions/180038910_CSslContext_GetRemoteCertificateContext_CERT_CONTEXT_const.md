# CSslContext::GetRemoteCertificateContext(_CERT_CONTEXT const * *)

- ea: `0x180038910`
- end: `0x180038c4a`
- name: `?GetRemoteCertificateContext@CSslContext@@UEAAKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `826`
- prototype: `unsigned int __fastcall(CSslContext *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180021da8`
- `0x180038910`
- `0x180057c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038bf1`
- `ntdll!RtlReleaseResource` at `0x180038990`
- `ntdll!RtlReleaseResource` at `0x180038990`
- `ntdll!RtlAcquireResourceShared` at `0x18003894b`
- `ntdll!RtlAcquireResourceShared` at `0x18003894b`
- `CRYPT32!CertOpenStore` at `0x1800389ee`
- `CRYPT32!CertOpenStore` at `0x1800389ee`
- `CRYPT32!CertCloseStore` at `0x180038b37`
- `CRYPT32!CertCloseStore` at `0x180038b9d`
- `CRYPT32!CertCloseStore` at `0x180038bc3`
- `CRYPT32!CertCloseStore` at `0x180038b37`
- `CRYPT32!CertCloseStore` at `0x180038b9d`
- `CRYPT32!CertCloseStore` at `0x180038bc3`
- `CRYPT32!CertFreeCertificateContext` at `0x180038af6`
- `CRYPT32!CertFreeCertificateContext` at `0x180038bda`
- `CRYPT32!CertFreeCertificateContext` at `0x180038be6`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ea44`
- `CRYPT32!CertFreeCertificateContext` at `0x180038af6`
- `CRYPT32!CertFreeCertificateContext` at `0x180038bda`
- `CRYPT32!CertFreeCertificateContext` at `0x180038be6`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ea44`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038aa5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038aa5`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180038a76`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180038a76`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180038ad5`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180038ad5`

## pseudocode

```c
__int64 __fastcall CSslContext::GetRemoteCertificateContext(CSslContext *this, const struct _CERT_CONTEXT **a2)
{
  __int64 v4; // rcx
  const BYTE *v5; // rsi
  DWORD LastError; // esi
  unsigned int v8; // r14d
  const CERT_CONTEXT *v9; // rcx
  HCERTSTORE v10; // r12
  int v11; // r13d
  __int64 v12; // r15
  unsigned int v13; // r14d
  DWORD v14; // eax
  unsigned int *v15; // [rsp+30h] [rbp-58h]
  _QWORD pvData[3]; // [rsp+38h] [rbp-50h] BYREF
  int v17; // [rsp+98h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+18h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a2 || *a2 )
    return 87;
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL), 1u);
  v4 = *(_QWORD *)(*((_QWORD *)this + 14) + 40LL);
  v5 = *(const BYTE **)(v4 + 16);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_66f36298ed2a3a88f0a812f41a45625f_Traceguids);
    LastError = -2146893042;
    goto LABEL_8;
  }
  v8 = *(_DWORD *)(v4 + 24);
  v9 = *a2;
  pCertContext = 0;
  if ( v9 )
    CertFreeCertificateContext(v9);
  *a2 = 0;
  v10 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  if ( !v10 )
  {
    LastError = GetLastError();
    goto LABEL_27;
  }
  pvData[1] = &v17;
  v11 = 1;
  v17 = 0;
  pvData[0] = 4;
  while ( 1 )
  {
    if ( v8 < 4 || (v12 = *(unsigned int *)v5, v13 = v8 - 4, (unsigned int)v12 > v13) )
    {
      LastError = -2146893052;
      CertCloseStore(v10, 0);
      goto LABEL_35;
    }
    v15 = (unsigned int *)(v5 + 4);
    if ( !CertAddEncodedCertificateToStore(v10, 1u, v5 + 4, v12, 2u, &pCertContext) )
    {
LABEL_25:
      LastError = GetLastError();
      goto LABEL_26;
    }
    LastError = 0;
    pcbData = 0;
    if ( !CertGetCertificateContextProperty(pCertContext, 0xE697u, 0, &pcbData) )
      break;
LABEL_20:
    v8 = v13 - v12;
    if ( v11 )
    {
      v11 = 0;
      *a2 = pCertContext;
    }
    else
    {
      CertFreeCertificateContext(pCertContext);
    }
    pCertContext = 0;
    if ( !v8 )
    {
      CertCloseStore(v10, 0);
      goto LABEL_27;
    }
    v5 = (const BYTE *)v15 + v12;
  }
  if ( GetLastError() == -2146885628 )
  {
    if ( !CertSetCertificateContextProperty(pCertContext, 0xE697u, 0, pvData) )
      goto LABEL_25;
    ++v17;
    goto LABEL_20;
  }
  v14 = GetLastError();
  LastError = v14;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids, v14);
LABEL_26:
  CertCloseStore(v10, 0);
  if ( !LastError )
    goto LABEL_27;
LABEL_35:
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( *a2 )
  {
    CertFreeCertificateContext(*a2);
    *a2 = 0;
  }
LABEL_27:
  if ( LastError
    && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_66f36298ed2a3a88f0a812f41a45625f_Traceguids, LastError);
  }
LABEL_8:
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(*((_QWORD *)this + 14) + 40LL) + 80LL));
  return LastError;
}

```

## disassembly

```asm
0x180038910  push    rbx
0x180038912  push    rdi
0x180038913  sub     rsp, 78h
0x180038917  mov     rdi, rdx
0x18003891a  mov     rbx, rcx
0x18003891d  test    rdx, rdx
0x180038920  jz      loc_180038BAF
0x180038926  cmp     qword ptr [rdx], 0
0x18003892a  jnz     loc_180038BAF
0x180038930  mov     rax, [rcx+70h]
0x180038934  mov     dl, 1; Wait
0x180038936  mov     [rsp+88h+var_18], rsi
0x18003893b  mov     [rsp+88h+arg_0], rbp
0x180038943  mov     rcx, [rax+28h]
0x180038947  add     rcx, 50h ; 'P'; Resource
0x18003894b  call    cs:__imp_RtlAcquireResourceShared
0x180038951  mov     rax, [rbx+70h]
0x180038955  mov     rcx, [rax+28h]
0x180038959  mov     rsi, [rcx+10h]
0x18003895d  test    rsi, rsi
0x180038960  jnz     short loc_1800389AC
0x180038962  mov     rcx, cs:WPP_GLOBAL_Control
0x180038969  lea     rbp, WPP_GLOBAL_Control
0x180038970  cmp     rcx, rbp
0x180038973  jz      short loc_18003897F
0x180038975  test    byte ptr [rcx+1Ch], 4
0x180038979  jnz     loc_180038C30
0x18003897f  mov     esi, 8009030Eh
0x180038984  mov     rcx, [rbx+70h]
0x180038988  mov     rcx, [rcx+28h]
0x18003898c  add     rcx, 50h ; 'P'; Resource
0x180038990  call    cs:__imp_RtlReleaseResource
0x180038996  mov     rbp, [rsp+88h+arg_0]
0x18003899e  mov     eax, esi
0x1800389a0  mov     rsi, [rsp+88h+var_18]
0x1800389a5  add     rsp, 78h
0x1800389a9  pop     rdi
0x1800389aa  pop     rbx
0x1800389ab  retn
0x1800389ac  mov     [rsp+88h+var_20], r12
0x1800389b1  mov     [rsp+88h+var_30], r14
0x1800389b6  mov     r14d, [rcx+18h]
0x1800389ba  mov     rcx, [rdi]; pCertContext
0x1800389bd  mov     [rsp+88h+var_38], r15
0x1800389c2  xor     r15d, r15d
0x1800389c5  mov     [rsp+88h+pCertContext], r15
0x1800389cd  test    rcx, rcx
0x1800389d0  jnz     loc_180038BE6
0x1800389d6  mov     r9d, 4; dwFlags
0x1800389dc  mov     [rdi], r15
0x1800389df  xor     r8d, r8d; hCryptProv
0x1800389e2  mov     [rsp+88h+pvPara], r15; pvPara
0x1800389e7  xor     edx, edx; dwEncodingType
0x1800389e9  mov     ecx, 2; lpszStoreProvider
0x1800389ee  call    cs:__imp_CertOpenStore
0x1800389f4  lea     rbp, WPP_GLOBAL_Control
0x1800389fb  mov     r12, rax
0x1800389fe  test    rax, rax
0x180038a01  jz      loc_180038BA5
0x180038a07  lea     rax, [rsp+88h+arg_8]
0x180038a0f  mov     [rsp+88h+var_28], r13
0x180038a14  mov     [rsp+88h+var_48], rax
0x180038a19  mov     r13d, 1
0x180038a1f  mov     [rsp+88h+arg_8], r15d
0x180038a27  mov     [rsp+88h+pvData], 4
0x180038a30  cmp     r14d, 4
0x180038a34  jb      loc_180038BB9
0x180038a3a  mov     r15d, [rsi]
0x180038a3d  add     r14d, 0FFFFFFFCh
0x180038a41  cmp     r15d, r14d
0x180038a44  ja      loc_180038BB9
0x180038a4a  lea     rax, [rsi+4]
0x180038a4e  mov     r9d, r15d; cbCertEncoded
0x180038a51  lea     rcx, [rsp+88h+pCertContext]
0x180038a59  mov     [rsp+88h+var_58], rax
0x180038a5e  mov     [rsp+88h+ppCertContext], rcx; ppCertContext
0x180038a63  mov     r8, rax; pbCertEncoded
0x180038a66  mov     rcx, r12; hCertStore
0x180038a69  mov     dword ptr [rsp+88h+pvPara], 2; dwAddDisposition
0x180038a71  mov     edx, 1; dwCertEncodingType
0x180038a76  call    cs:__imp_CertAddEncodedCertificateToStore
0x180038a7c  test    eax, eax
0x180038a7e  jz      loc_180038B2A
0x180038a84  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180038a8c  lea     r9, [rsp+88h+pcbData]; pcbData
0x180038a94  xor     esi, esi
0x180038a96  xor     r8d, r8d; pvData
0x180038a99  mov     edx, 0E697h; dwPropId
0x180038a9e  mov     [rsp+88h+pcbData], esi
0x180038aa5  call    cs:__imp_CertGetCertificateContextProperty
0x180038aab  test    eax, eax
0x180038aad  jnz     short loc_180038AE6
0x180038aaf  call    cs:__imp_GetLastError
0x180038ab5  cmp     eax, 80092004h
0x180038aba  jnz     loc_180038BF1
0x180038ac0  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180038ac8  lea     r9, [rsp+88h+pvData]; pvData
0x180038acd  xor     r8d, r8d; dwFlags
0x180038ad0  mov     edx, 0E697h; dwPropId
0x180038ad5  call    cs:__imp_CertSetCertificateContextProperty
0x180038adb  test    eax, eax
0x180038add  jz      short loc_180038B2A
0x180038adf  inc     [rsp+88h+arg_8]
0x180038ae6  sub     r14d, r15d
0x180038ae9  test    r13d, r13d
0x180038aec  jnz     short loc_180038B1A
0x180038aee  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180038af6  call    cs:__imp_CertFreeCertificateContext
0x180038afc  mov     [rsp+88h+pCertContext], rsi
0x180038b04  test    r14d, r14d
0x180038b07  jz      loc_180038B98
0x180038b0d  mov     rsi, r15
0x180038b10  add     rsi, [rsp+88h+var_58]
0x180038b15  jmp     loc_180038A30
0x180038b1a  mov     rax, [rsp+88h+pCertContext]
0x180038b22  mov     r13d, esi
0x180038b25  mov     [rdi], rax
0x180038b28  jmp     short loc_180038AFC
0x180038b2a  call    cs:__imp_GetLastError
0x180038b30  mov     esi, eax
0x180038b32  xor     edx, edx; dwFlags
0x180038b34  mov     rcx, r12; hCertStore
0x180038b37  call    cs:__imp_CertCloseStore
0x180038b3d  test    esi, esi
0x180038b3f  jnz     loc_180038BC9
0x180038b45  mov     r13, [rsp+88h+var_28]
0x180038b4a  mov     r15, [rsp+88h+var_38]
0x180038b4f  mov     r14, [rsp+88h+var_30]
0x180038b54  mov     r12, [rsp+88h+var_20]
0x180038b59  test    esi, esi
0x180038b5b  jz      loc_180038984
0x180038b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b68  cmp     rcx, rbp
0x180038b6b  jz      loc_180038984
0x180038b71  test    byte ptr [rcx+1Ch], 1
0x180038b75  jz      loc_180038984
0x180038b7b  mov     rcx, [rcx+10h]
0x180038b7f  lea     r8, WPP_66f36298ed2a3a88f0a812f41a45625f_Traceguids
0x180038b86  mov     edx, 0Eh
0x180038b8b  mov     r9d, esi
0x180038b8e  call    WPP_SF_d
0x180038b93  jmp     loc_180038984
0x180038b98  xor     edx, edx; dwFlags
0x180038b9a  mov     rcx, r12; hCertStore
0x180038b9d  call    cs:__imp_CertCloseStore
0x180038ba3  jmp     short loc_180038B45
0x180038ba5  call    cs:__imp_GetLastError
0x180038bab  mov     esi, eax
0x180038bad  jmp     short loc_180038B4A
0x180038baf  mov     eax, 57h ; 'W'
0x180038bb4  jmp     loc_1800389A5
0x180038bb9  xor     edx, edx; dwFlags
0x180038bbb  mov     rcx, r12; hCertStore
0x180038bbe  mov     esi, 80090304h
0x180038bc3  call    cs:__imp_CertCloseStore
0x180038bc9  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180038bd1  test    rcx, rcx
0x180038bd4  jz      loc_18008EA38
0x180038bda  call    cs:__imp_CertFreeCertificateContext
0x180038be0  nop
0x180038be1  jmp     loc_18008EA38
0x180038be6  call    cs:__imp_CertFreeCertificateContext
0x180038bec  jmp     loc_1800389D6
0x180038bf1  call    cs:__imp_GetLastError
0x180038bf7  mov     esi, eax
0x180038bf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c00  cmp     rcx, rbp
0x180038c03  jz      loc_180038B32
0x180038c09  test    byte ptr [rcx+1Ch], 1
0x180038c0d  jz      loc_180038B32
0x180038c13  mov     rcx, [rcx+10h]
0x180038c17  lea     r8, WPP_97ce1caa02e33ff6a1f9fe6c11ed93b7_Traceguids
0x180038c1e  mov     edx, 0Ah
0x180038c23  mov     r9d, eax
0x180038c26  call    WPP_SF_d
0x180038c2b  jmp     loc_180038B32
0x180038c30  mov     rcx, [rcx+10h]
0x180038c34  lea     r8, WPP_66f36298ed2a3a88f0a812f41a45625f_Traceguids
0x180038c3b  mov     edx, 0Fh
0x180038c40  call    WPP_SF_
0x180038c45  jmp     loc_18003897F
0x18008ea38  mov     rcx, [rdi]; pCertContext
0x18008ea3b  test    rcx, rcx
0x18008ea3e  jz      loc_180038B45
0x18008ea44  call    cs:__imp_CertFreeCertificateContext
0x18008ea4a  mov     qword ptr [rdi], 0
0x18008ea51  jmp     loc_180038B45
```
