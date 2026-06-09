# IsHashInSignatureList

- ea: `0x180023718`
- end: `0x1800239a6`
- name: `IsHashInSignatureList`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180023cd0`

## callees

- `0x180023718`
- `0x180023ab8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002388b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002388b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023774`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023919`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18002390f`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x18002390f`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800237f8`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x1800237f8`
- `CRYPT32!CertFreeCertificateContext` at `0x18002393b`
- `CRYPT32!CertFreeCertificateContext` at `0x180023955`
- `CRYPT32!CertFreeCertificateContext` at `0x18002393b`
- `CRYPT32!CertFreeCertificateContext` at `0x180023955`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180023901`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180023901`
- `CRYPT32!CertCloseStore` at `0x18002398e`
- `CRYPT32!CertCloseStore` at `0x18002398e`
- `CRYPT32!CertFindCertificateInStore` at `0x180023839`
- `CRYPT32!CertFindCertificateInStore` at `0x180023839`
- `CRYPT32!CertGetNameStringW` at `0x180023878`
- `CRYPT32!CertGetNameStringW` at `0x1800238ba`
- `CRYPT32!CertGetNameStringW` at `0x180023878`
- `CRYPT32!CertGetNameStringW` at `0x1800238ba`
- `CRYPT32!CertOpenStore` at `0x180023766`
- `CRYPT32!CertOpenStore` at `0x180023766`

## pseudocode

```c
__int64 __fastcall IsHashInSignatureList(_QWORD *a1, __int64 a2, int a3, int *a4)
{
  __int64 v5; // rbx
  _QWORD *v6; // r14
  unsigned __int64 v7; // rsi
  HCERTSTORE v8; // r15
  signed int v9; // eax
  signed int v10; // ebx
  const CERT_CONTEXT *v11; // rdi
  unsigned __int64 v12; // rax
  unsigned int v13; // r12d
  int v14; // ecx
  unsigned int i; // ebx
  const CERT_CONTEXT *CertificateInStore; // rax
  __int64 v17; // rsi
  DWORD NameStringW; // r14d
  WCHAR *v19; // rax
  WCHAR *v20; // rbx
  int v21; // edx
  int v22; // ecx
  const wchar_t *v23; // r8
  const CERT_CONTEXT *v24; // rax
  signed int LastError; // eax
  __int64 v27; // [rsp+30h] [rbp-58h]
  __int64 v28; // [rsp+40h] [rbp-48h]
  int v29; // [rsp+48h] [rbp-40h]
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+10h] BYREF
  int v32; // [rsp+A0h] [rbp+18h]
  int *v33; // [rsp+A8h] [rbp+20h]

  v33 = a4;
  v32 = a3;
  v5 = *(unsigned int *)(a2 + 16);
  v6 = a1;
  v7 = *(unsigned int *)(a2 + 24);
  v28 = *a1;
  v27 = a1[1];
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  if ( v8 )
  {
    v32 = 0;
    v11 = 0;
    v12 = (v5 - 28) / v7;
    v13 = 0;
    v29 = v12;
    while ( v13 < (unsigned int)v12 )
    {
      v14 = *(_DWORD *)(a2 + 24);
      pCertContext = 0;
      if ( !CertAddEncodedCertificateToStore(v8, 1u, (const BYTE *)(a2 + v13 * v14 + 44LL), v14 - 16, 4u, &pCertContext) )
        goto LABEL_22;
      for ( i = 0; i < *((_DWORD *)v6 + 8); ++i )
      {
        CertificateInStore = CertFindCertificateInStore(v8, 0, 0, 0x10000u, (const void *)(v28 + 16LL * i), 0);
        v11 = CertificateInStore;
        if ( CertificateInStore )
        {
          v17 = *(_QWORD *)(v28 + 16LL * i + 8);
          v32 = 1;
          NameStringW = CertGetNameStringW(CertificateInStore, 4u, 0, 0, 0, 0);
          v19 = (WCHAR *)LocalAlloc(0x40u, 2LL * NameStringW);
          v20 = v19;
          if ( !v19 )
          {
            v10 = -2147024882;
            goto LABEL_24;
          }
          if ( CertGetNameStringW(v11, 4u, 0, 0, v19, NameStringW) )
          {
            if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 2) != 0 )
            {
              LODWORD(v23) = (_DWORD)v20;
              goto LABEL_18;
            }
          }
          else if ( (Microsoft_Windows_VerifyHardwareSecurityEnableBits & 2) != 0 )
          {
            v23 = L"CERT_NAME_UNKNOWN";
LABEL_18:
            McTemplateU0zzb20_EventWriteTransfer(v22, v21, (_DWORD)v23, v27, v17);
          }
          LocalFree(v20);
          break;
        }
      }
      v10 = 0;
      v24 = CertEnumCertificatesInStore(v8, 0);
      if ( v24 )
      {
        if ( !CertDeleteCertificateFromStore(v24) )
        {
LABEL_22:
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
        }
      }
LABEL_24:
      if ( pCertContext )
      {
        CertFreeCertificateContext(pCertContext);
        pCertContext = 0;
      }
      if ( v11 )
      {
        CertFreeCertificateContext(v11);
        v11 = 0;
      }
      if ( v10 < 0 )
        goto LABEL_31;
      v6 = a1;
      ++v13;
      LODWORD(v12) = v29;
    }
    v10 = 0;
    *v33 = v32;
LABEL_31:
    CertCloseStore(v8, 0);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180023718  mov     r11, rsp
0x18002371b  mov     [r11+20h], r9
0x18002371f  mov     [r11+18h], r8d
0x180023723  mov     [r11+8], rcx
0x180023727  push    rbx
0x180023728  push    rsi
0x180023729  push    rdi
0x18002372a  push    r12
0x18002372c  push    r13
0x18002372e  push    r14
0x180023730  push    r15
0x180023732  sub     rsp, 50h
0x180023736  mov     rax, [rcx]
0x180023739  mov     r13, rdx
0x18002373c  mov     ebx, [rdx+10h]
0x18002373f  mov     r14, rcx
0x180023742  mov     esi, [rdx+18h]
0x180023745  xor     r9d, r9d; dwFlags
0x180023748  xor     edx, edx; dwEncodingType
0x18002374a  mov     [rsp+88h+var_48], rax
0x18002374f  mov     rax, [rcx+8]
0x180023753  xor     r8d, r8d; hCryptProv
0x180023756  mov     [rsp+88h+var_58], rax
0x18002375b  mov     qword ptr [r11-68h], 0
0x180023763  lea     ecx, [rdx+2]; lpszStoreProvider
0x180023766  call    cs:__imp_CertOpenStore
0x18002376c  mov     r15, rax
0x18002376f  test    rax, rax
0x180023772  jnz     short loc_180023792
0x180023774  call    cs:__imp_GetLastError
0x18002377a  mov     ebx, eax
0x18002377c  test    eax, eax
0x18002377e  jle     loc_180023994
0x180023784  movzx   ebx, ax
0x180023787  or      ebx, 80070000h
0x18002378d  jmp     loc_180023994
0x180023792  xor     edx, edx
0x180023794  mov     [rsp+88h+arg_10], 0
0x18002379f  lea     rax, [rbx-1Ch]
0x1800237a3  xor     edi, edi
0x1800237a5  div     rsi
0x1800237a8  xor     r12d, r12d
0x1800237ab  mov     qword ptr [rsp+88h+var_40], rax
0x1800237b0  cmp     r12d, eax
0x1800237b3  jnb     loc_180023976
0x1800237b9  mov     ecx, [r13+18h]
0x1800237bd  lea     rax, [rsp+88h+pCertContext]
0x1800237c5  mov     [rsp+88h+ppCertContext], rax; ppCertContext
0x1800237ca  mov     edx, 1; dwCertEncodingType
0x1800237cf  mov     [rsp+88h+pCertContext], 0
0x1800237db  mov     [rsp+88h+dwAddDisposition], 4; dwAddDisposition
0x1800237e3  lea     r9d, [rcx-10h]; cbCertEncoded
0x1800237e7  imul    ecx, r12d
0x1800237eb  mov     r8d, ecx
0x1800237ee  mov     rcx, r15; hCertStore
0x1800237f1  add     r8, 2Ch ; ','
0x1800237f5  add     r8, r13; pbCertEncoded
0x1800237f8  call    cs:__imp_CertAddEncodedCertificateToStore
0x1800237fe  test    eax, eax
0x180023800  jz      loc_180023919
0x180023806  xor     ebx, ebx
0x180023808  cmp     ebx, [r14+20h]
0x18002380c  jnb     loc_1800238FA
0x180023812  mov     esi, ebx
0x180023814  mov     r9d, 10000h; dwFindType
0x18002381a  shl     rsi, 4
0x18002381e  xor     r8d, r8d; dwFindFlags
0x180023821  add     rsi, [rsp+88h+var_48]
0x180023826  xor     edx, edx; dwCertEncodingType
0x180023828  mov     [rsp+88h+ppCertContext], 0; pPrevCertContext
0x180023831  mov     rcx, r15; hCertStore
0x180023834  mov     qword ptr [rsp+88h+dwAddDisposition], rsi; pvFindPara
0x180023839  call    cs:__imp_CertFindCertificateInStore
0x18002383f  mov     rdi, rax
0x180023842  test    rax, rax
0x180023845  jnz     short loc_18002384B
0x180023847  inc     ebx
0x180023849  jmp     short loc_180023808
0x18002384b  mov     rsi, [rsi+8]
0x18002384f  xor     r9d, r9d; pvTypePara
0x180023852  mov     dword ptr [rsp+88h+ppCertContext], 0; cchNameString
0x18002385a  xor     r8d, r8d; dwFlags
0x18002385d  mov     rcx, rdi; pCertContext
0x180023860  mov     [rsp+88h+arg_10], 1
0x18002386b  mov     qword ptr [rsp+88h+dwAddDisposition], 0; pszNameString
0x180023874  lea     edx, [r9+4]; dwType
0x180023878  call    cs:__imp_CertGetNameStringW
0x18002387e  mov     edx, eax
0x180023880  mov     ecx, 40h ; '@'; uFlags
0x180023885  add     rdx, rdx; uBytes
0x180023888  mov     r14d, eax
0x18002388b  call    cs:__imp_LocalAlloc
0x180023891  mov     rbx, rax
0x180023894  test    rax, rax
0x180023897  jnz     short loc_1800238A3
0x180023899  mov     ebx, 8007000Eh
0x18002389e  jmp     loc_18002392E
0x1800238a3  xor     r9d, r9d; pvTypePara
0x1800238a6  mov     dword ptr [rsp+88h+ppCertContext], r14d; cchNameString
0x1800238ab  xor     r8d, r8d; dwFlags
0x1800238ae  mov     qword ptr [rsp+88h+dwAddDisposition], rbx; pszNameString
0x1800238b3  mov     rcx, rdi; pCertContext
0x1800238b6  lea     edx, [r9+4]; dwType
0x1800238ba  call    cs:__imp_CertGetNameStringW
0x1800238c0  test    eax, eax
0x1800238c2  jz      short loc_1800238D2
0x1800238c4  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 2
0x1800238cb  jz      short loc_1800238F1
0x1800238cd  mov     r8, rbx
0x1800238d0  jmp     short loc_1800238E2
0x1800238d2  test    cs:Microsoft_Windows_VerifyHardwareSecurityEnableBits, 2
0x1800238d9  jz      short loc_1800238F1
0x1800238db  lea     r8, aCertNameUnknow; "CERT_NAME_UNKNOWN"
0x1800238e2  mov     r9, [rsp+88h+var_58]
0x1800238e7  mov     qword ptr [rsp+88h+dwAddDisposition], rsi
0x1800238ec  call    McTemplateU0zzb20_EventWriteTransfer
0x1800238f1  mov     rcx, rbx; hMem
0x1800238f4  call    cs:__imp_LocalFree
0x1800238fa  xor     edx, edx; pPrevCertContext
0x1800238fc  mov     rcx, r15; hCertStore
0x1800238ff  xor     ebx, ebx
0x180023901  call    cs:__imp_CertEnumCertificatesInStore
0x180023907  test    rax, rax
0x18002390a  jz      short loc_18002392E
0x18002390c  mov     rcx, rax; pCertContext
0x18002390f  call    cs:__imp_CertDeleteCertificateFromStore
0x180023915  test    eax, eax
0x180023917  jnz     short loc_18002392E
0x180023919  call    cs:__imp_GetLastError
0x18002391f  mov     ebx, eax
0x180023921  test    eax, eax
0x180023923  jle     short loc_18002392E
0x180023925  movzx   ebx, ax
0x180023928  or      ebx, 80070000h
0x18002392e  mov     rcx, [rsp+88h+pCertContext]; pCertContext
0x180023936  test    rcx, rcx
0x180023939  jz      short loc_18002394D
0x18002393b  call    cs:__imp_CertFreeCertificateContext
0x180023941  mov     [rsp+88h+pCertContext], 0
0x18002394d  test    rdi, rdi
0x180023950  jz      short loc_18002395D
0x180023952  mov     rcx, rdi; pCertContext
0x180023955  call    cs:__imp_CertFreeCertificateContext
0x18002395b  xor     edi, edi
0x18002395d  test    ebx, ebx
0x18002395f  js      short loc_180023989
0x180023961  mov     r14, [rsp+88h+arg_0]
0x180023969  inc     r12d
0x18002396c  mov     rax, qword ptr [rsp+88h+var_40]
0x180023971  jmp     loc_1800237B0
0x180023976  mov     rcx, [rsp+88h+arg_18]
0x18002397e  xor     ebx, ebx
0x180023980  mov     eax, [rsp+88h+arg_10]
0x180023987  mov     [rcx], eax
0x180023989  xor     edx, edx; dwFlags
0x18002398b  mov     rcx, r15; hCertStore
0x18002398e  call    cs:__imp_CertCloseStore
0x180023994  mov     eax, ebx
0x180023996  add     rsp, 50h
0x18002399a  pop     r15
0x18002399c  pop     r14
0x18002399e  pop     r13
0x1800239a0  pop     r12
0x1800239a2  pop     rdi
0x1800239a3  pop     rsi
0x1800239a4  pop     rbx
0x1800239a5  retn
```
