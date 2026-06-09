# CheckKeyProvInfo

- ea: `0x1800444ac`
- end: `0x18004466d`
- name: `CheckKeyProvInfo`
- size: `449`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, DWORD dwKeySpec)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180044eb0`

## callees

- `0x180044464`
- `0x180044490`
- `0x1800444ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004462b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004462b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044615`
- `CRYPTSP!CryptAcquireContextW` at `0x180044557`
- `CRYPTSP!CryptAcquireContextW` at `0x180044557`
- `CRYPTSP!CryptSetProvParam` at `0x18004458c`
- `CRYPTSP!CryptSetProvParam` at `0x18004458c`
- `CRYPTSP!CryptReleaseContext` at `0x180044623`
- `CRYPTSP!CryptReleaseContext` at `0x180044623`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800445b8`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800445ea`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800445b8`
- `CRYPT32!CryptExportPublicKeyInfo` at `0x1800445ea`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800444ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180044530`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800444ef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180044530`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180044601`
- `CRYPT32!CertComparePublicKeyInfo` at `0x180044601`

## pseudocode

```c
__int64 __fastcall CheckKeyProvInfo(PCCERT_CONTEXT pCertContext, DWORD dwKeySpec, DWORD *a3)
{
  unsigned int v3; // r14d
  unsigned int v7; // r15d
  LPCWSTR *v8; // rdi
  struct _CERT_PUBLIC_KEY_INFO *v9; // rsi
  LPCWSTR *v10; // rax
  DWORD dwCertEncodingType; // r8d
  DWORD LastError; // ebx
  HCRYPTPROV phProv[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+50h] BYREF
  DWORD pcbInfo; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  phProv[0] = 0;
  pcbInfo = 0;
  pcbData = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData);
  if ( pcbData )
  {
    if ( dwKeySpec )
    {
      v10 = (LPCWSTR *)ACAlloc(pcbData);
      v8 = v10;
      if ( v10 && CertGetCertificateContextProperty(pCertContext, 2u, v10, &pcbData) )
      {
        if ( !CryptAcquireContextW(phProv, *v8, v8[1], *((_DWORD *)v8 + 4), *((_DWORD *)v8 + 5) & 0xFFFFFFFE) )
        {
          phProv[0] = 0;
LABEL_18:
          ACFree(v8);
          goto LABEL_19;
        }
        while ( v3 < *((_DWORD *)v8 + 6) )
        {
          if ( !CryptSetProvParam(
                  phProv[0],
                  *(_DWORD *)&v8[4][12 * v3],
                  *(const BYTE **)&v8[4][12 * v3 + 4],
                  *(_DWORD *)&v8[4][12 * v3 + 10]) )
            goto LABEL_15;
          ++v3;
        }
        dwCertEncodingType = pCertContext->dwCertEncodingType;
        pcbInfo = 0;
        CryptExportPublicKeyInfo(phProv[0], dwKeySpec, dwCertEncodingType, 0, &pcbInfo);
        if ( pcbInfo )
        {
          v9 = (struct _CERT_PUBLIC_KEY_INFO *)ACAlloc(pcbInfo);
          if ( v9 )
          {
            if ( CryptExportPublicKeyInfo(phProv[0], dwKeySpec, pCertContext->dwCertEncodingType, v9, &pcbInfo) )
              v7 = CertComparePublicKeyInfo(
                     pCertContext->dwCertEncodingType,
                     &pCertContext->pCertInfo->SubjectPublicKeyInfo,
                     v9);
          }
        }
      }
    }
    else
    {
      v7 = 1;
    }
  }
LABEL_15:
  if ( phProv[0] )
  {
    LastError = GetLastError();
    CryptReleaseContext(phProv[0], 0);
    SetLastError(LastError);
  }
  if ( v8 )
    goto LABEL_18;
LABEL_19:
  if ( v9 )
    ACFree(v9);
  *a3 = pcbData;
  return v7;
}

```

## disassembly

```asm
0x1800444ac  mov     [rsp-38h+arg_0], rbx
0x1800444b1  push    rbp
0x1800444b2  push    rsi
0x1800444b3  push    rdi
0x1800444b4  push    r12
0x1800444b6  push    r13
0x1800444b8  push    r14
0x1800444ba  push    r15
0x1800444bc  mov     rbp, rsp
0x1800444bf  sub     rsp, 40h
0x1800444c3  xor     r14d, r14d
0x1800444c6  lea     r9, [rbp+pcbData]; pcbData
0x1800444ca  mov     r13, r8
0x1800444cd  mov     [rbp+phProv], r14
0x1800444d1  mov     r12d, edx
0x1800444d4  mov     [rbp+pcbInfo], r14d
0x1800444d8  xor     r8d, r8d; pvData
0x1800444db  mov     [rbp+pcbData], r14d
0x1800444df  lea     edx, [r14+2]; dwPropId
0x1800444e3  mov     rbx, rcx
0x1800444e6  mov     r15d, r14d
0x1800444e9  mov     edi, r14d
0x1800444ec  mov     esi, r14d
0x1800444ef  call    cs:__imp_CertGetCertificateContextProperty
0x1800444f5  cmp     [rbp+pcbData], r14d
0x1800444f9  jz      loc_18004460F
0x1800444ff  test    r12d, r12d
0x180044502  jnz     short loc_18004450D
0x180044504  lea     r15d, [r14+1]
0x180044508  jmp     loc_18004460F
0x18004450d  mov     ecx, [rbp+pcbData]
0x180044510  call    ACAlloc
0x180044515  mov     rdi, rax
0x180044518  test    rax, rax
0x18004451b  jz      loc_18004460F
0x180044521  lea     r9, [rbp+pcbData]; pcbData
0x180044525  mov     r8, rax; pvData
0x180044528  mov     edx, 2; dwPropId
0x18004452d  mov     rcx, rbx; pCertContext
0x180044530  call    cs:__imp_CertGetCertificateContextProperty
0x180044536  test    eax, eax
0x180044538  jz      loc_18004460F
0x18004453e  mov     eax, [rdi+14h]
0x180044541  lea     rcx, [rbp+phProv]; phProv
0x180044545  mov     r9d, [rdi+10h]; dwProvType
0x180044549  and     eax, 0FFFFFFFEh
0x18004454c  mov     r8, [rdi+8]; szProvider
0x180044550  mov     rdx, [rdi]; szContainer
0x180044553  mov     [rsp+40h+dwFlags], eax; dwFlags
0x180044557  call    cs:__imp_CryptAcquireContextW
0x18004455d  test    eax, eax
0x18004455f  jnz     short loc_18004456A
0x180044561  mov     [rbp+phProv], r14
0x180044565  jmp     loc_180044636
0x18004456a  cmp     r14d, [rdi+18h]
0x18004456e  jnb     short loc_18004459B
0x180044570  mov     rdx, [rdi+20h]
0x180044574  mov     eax, r14d
0x180044577  lea     rcx, [rax+rax*2]
0x18004457b  mov     r9d, [rdx+rcx*8+14h]; dwFlags
0x180044580  mov     r8, [rdx+rcx*8+8]; pbData
0x180044585  mov     edx, [rdx+rcx*8]; dwParam
0x180044588  mov     rcx, [rbp+phProv]; hProv
0x18004458c  call    cs:__imp_CryptSetProvParam
0x180044592  test    eax, eax
0x180044594  jz      short loc_18004460C
0x180044596  inc     r14d
0x180044599  jmp     short loc_18004456A
0x18004459b  mov     r8d, [rbx]; dwCertEncodingType
0x18004459e  lea     rax, [rbp+pcbInfo]
0x1800445a2  mov     rcx, [rbp+phProv]; hCryptProvOrNCryptKey
0x1800445a6  xor     r14d, r14d
0x1800445a9  xor     r9d, r9d; pInfo
0x1800445ac  mov     [rbp+pcbInfo], r14d
0x1800445b0  mov     edx, r12d; dwKeySpec
0x1800445b3  mov     qword ptr [rsp+40h+dwFlags], rax; pcbInfo
0x1800445b8  call    cs:__imp_CryptExportPublicKeyInfo
0x1800445be  mov     eax, [rbp+pcbInfo]
0x1800445c1  test    eax, eax
0x1800445c3  jz      short loc_18004460F
0x1800445c5  mov     ecx, eax
0x1800445c7  call    ACAlloc
0x1800445cc  mov     rsi, rax
0x1800445cf  test    rax, rax
0x1800445d2  jz      short loc_18004460F
0x1800445d4  mov     r8d, [rbx]; dwCertEncodingType
0x1800445d7  lea     rax, [rbp+pcbInfo]
0x1800445db  mov     rcx, [rbp+phProv]; hCryptProvOrNCryptKey
0x1800445df  mov     r9, rsi; pInfo
0x1800445e2  mov     edx, r12d; dwKeySpec
0x1800445e5  mov     qword ptr [rsp+40h+dwFlags], rax; pcbInfo
0x1800445ea  call    cs:__imp_CryptExportPublicKeyInfo
0x1800445f0  test    eax, eax
0x1800445f2  jz      short loc_18004460F
0x1800445f4  mov     rdx, [rbx+18h]
0x1800445f8  mov     r8, rsi; pPublicKey2
0x1800445fb  mov     ecx, [rbx]; dwCertEncodingType
0x1800445fd  add     rdx, 60h ; '`'; pPublicKey1
0x180044601  call    cs:__imp_CertComparePublicKeyInfo
0x180044607  mov     r15d, eax
0x18004460a  jmp     short loc_18004460F
0x18004460c  xor     r14d, r14d
0x18004460f  cmp     [rbp+phProv], r14
0x180044613  jz      short loc_180044631
0x180044615  call    cs:__imp_GetLastError
0x18004461b  mov     rcx, [rbp+phProv]; hProv
0x18004461f  xor     edx, edx; dwFlags
0x180044621  mov     ebx, eax
0x180044623  call    cs:__imp_CryptReleaseContext
0x180044629  mov     ecx, ebx; dwErrCode
0x18004462b  call    cs:__imp_SetLastError
0x180044631  test    rdi, rdi
0x180044634  jz      short loc_18004463E
0x180044636  mov     rcx, rdi
0x180044639  call    ACFree
0x18004463e  test    rsi, rsi
0x180044641  jz      short loc_18004464B
0x180044643  mov     rcx, rsi
0x180044646  call    ACFree
0x18004464b  mov     eax, [rbp+pcbData]
0x18004464e  mov     rbx, [rsp+40h+arg_0]
0x180044656  mov     [r13+0], eax
0x18004465a  mov     eax, r15d
0x18004465d  add     rsp, 40h
0x180044661  pop     r15
0x180044663  pop     r14
0x180044665  pop     r13
0x180044667  pop     r12
0x180044669  pop     rdi
0x18004466a  pop     rsi
0x18004466b  pop     rbp
0x18004466c  retn
```
