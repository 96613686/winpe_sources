# DavSetPinOnCNGProvider

- ea: `0x180014410`
- end: `0x180014559`
- name: `DavSetPinOnCNGProvider`
- size: `329`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011da8`

## callees

- `0x180014410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001447a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001447a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014510`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014470`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180014470`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180014506`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180014506`
- `ncrypt!NCryptOpenStorageProvider` at `0x180014452`
- `ncrypt!NCryptOpenStorageProvider` at `0x180014452`
- `ncrypt!NCryptOpenKey` at `0x1800144b5`
- `ncrypt!NCryptOpenKey` at `0x1800144b5`
- `ncrypt!NCryptFreeObject` at `0x180014529`
- `ncrypt!NCryptFreeObject` at `0x180014538`
- `ncrypt!NCryptFreeObject` at `0x180014529`
- `ncrypt!NCryptFreeObject` at `0x180014538`
- `ncrypt!NCryptSetProperty` at `0x1800144ed`
- `ncrypt!NCryptSetProperty` at `0x1800144ed`

## pseudocode

```c
__int64 __fastcall DavSetPinOnCNGProvider(PCCERT_CONTEXT pCertContext, LPCWSTR *a2, BYTE *a3)
{
  int v6; // edi
  DWORD LastError; // ebx
  NCRYPT_HANDLE v8; // rcx
  __int64 v9; // r9
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF
  const void *pvData; // [rsp+88h] [rbp+48h] BYREF

  pcbData = 8;
  phProvider[0] = 0;
  pvData = 0;
  v6 = 0;
  LastError = NCryptOpenStorageProvider(phProvider, a2[1], 0);
  if ( !LastError )
  {
    if ( CertGetCertificateContextProperty(pCertContext, 0x4Eu, &pvData, &pcbData) )
    {
      v8 = (NCRYPT_HANDLE)pvData;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != -2146885628 )
        goto LABEL_14;
      v8 = 0;
      pvData = 0;
    }
    if ( !v8 )
    {
      LastError = NCryptOpenKey(phProvider[0], (NCRYPT_KEY_HANDLE *)&pvData, *a2, 0, 0x40u);
      if ( LastError )
        goto LABEL_15;
      v8 = (NCRYPT_HANDLE)pvData;
      v6 = 1;
    }
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&a3[2 * v9] );
    LastError = NCryptSetProperty(v8, L"SmartCardPin", a3, 2 * v9 + 2, 0);
    if ( !LastError )
    {
      if ( CertSetCertificateContextProperty(pCertContext, 0x4Eu, 0, pvData) )
        goto LABEL_18;
      LastError = GetLastError();
LABEL_14:
      if ( !LastError )
        goto LABEL_18;
    }
  }
LABEL_15:
  if ( pvData && v6 )
    NCryptFreeObject((NCRYPT_HANDLE)pvData);
LABEL_18:
  if ( phProvider[0] )
    NCryptFreeObject(phProvider[0]);
  return LastError;
}

```

## disassembly

```asm
0x180014410  mov     [rsp-28h+arg_0], rbx
0x180014415  mov     [rsp-28h+arg_10], rsi
0x18001441a  push    rbp
0x18001441b  push    rdi
0x18001441c  push    r12
0x18001441e  push    r14
0x180014420  push    r15
0x180014422  mov     rbp, rsp
0x180014425  sub     rsp, 40h
0x180014429  xor     r12d, r12d
0x18001442c  mov     [rbp+pcbData], 8
0x180014433  mov     r15, r8
0x180014436  mov     [rbp+phProvider], r12
0x18001443a  mov     rsi, rdx
0x18001443d  mov     [rbp+pvData], r12
0x180014441  mov     rdx, [rdx+8]; pszProviderName
0x180014445  mov     r14, rcx
0x180014448  xor     r8d, r8d; dwFlags
0x18001444b  lea     rcx, [rbp+phProvider]; phProvider
0x18001444f  mov     edi, r12d
0x180014452  call    cs:__imp_NCryptOpenStorageProvider
0x180014458  mov     ebx, eax
0x18001445a  test    eax, eax
0x18001445c  jnz     loc_18001451C
0x180014462  lea     r9, [rbp+pcbData]; pcbData
0x180014466  mov     rcx, r14; pCertContext
0x180014469  lea     r8, [rbp+pvData]; pvData
0x18001446d  lea     edx, [rax+4Eh]; dwPropId
0x180014470  call    cs:__imp_CertGetCertificateContextProperty
0x180014476  test    eax, eax
0x180014478  jnz     short loc_180014496
0x18001447a  call    cs:__imp_GetLastError
0x180014480  mov     ebx, eax
0x180014482  cmp     eax, 80092004h
0x180014487  jnz     loc_180014518
0x18001448d  mov     ecx, r12d
0x180014490  mov     [rbp+pvData], rcx
0x180014494  jmp     short loc_18001449A
0x180014496  mov     rcx, [rbp+pvData]
0x18001449a  test    rcx, rcx
0x18001449d  jnz     short loc_1800144C8
0x18001449f  mov     r8, [rsi]; pszKeyName
0x1800144a2  lea     rdx, [rbp+pvData]; phKey
0x1800144a6  mov     rcx, [rbp+phProvider]; hProvider
0x1800144aa  xor     r9d, r9d; dwLegacyKeySpec
0x1800144ad  mov     [rsp+40h+dwFlags], 40h ; '@'; dwFlags
0x1800144b5  call    cs:__imp_NCryptOpenKey
0x1800144bb  mov     ebx, eax
0x1800144bd  test    eax, eax
0x1800144bf  jnz     short loc_18001451C
0x1800144c1  mov     rcx, [rbp+pvData]; hObject
0x1800144c5  lea     edi, [rax+1]
0x1800144c8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800144cc  inc     r9
0x1800144cf  cmp     [r15+r9*2], r12w
0x1800144d4  jnz     short loc_1800144CC
0x1800144d6  lea     r9d, ds:2[r9*2]; cbInput
0x1800144de  mov     [rsp+40h+dwFlags], r12d; dwFlags
0x1800144e3  mov     r8, r15; pbInput
0x1800144e6  lea     rdx, pszProperty; "SmartCardPin"
0x1800144ed  call    cs:__imp_NCryptSetProperty
0x1800144f3  mov     ebx, eax
0x1800144f5  test    eax, eax
0x1800144f7  jnz     short loc_18001451C
0x1800144f9  mov     r9, [rbp+pvData]; pvData
0x1800144fd  lea     edx, [rax+4Eh]; dwPropId
0x180014500  xor     r8d, r8d; dwFlags
0x180014503  mov     rcx, r14; pCertContext
0x180014506  call    cs:__imp_CertSetCertificateContextProperty
0x18001450c  test    eax, eax
0x18001450e  jnz     short loc_18001452F
0x180014510  call    cs:__imp_GetLastError
0x180014516  mov     ebx, eax
0x180014518  test    ebx, ebx
0x18001451a  jz      short loc_18001452F
0x18001451c  mov     rcx, [rbp+pvData]; hObject
0x180014520  test    rcx, rcx
0x180014523  jz      short loc_18001452F
0x180014525  test    edi, edi
0x180014527  jz      short loc_18001452F
0x180014529  call    cs:__imp_NCryptFreeObject
0x18001452f  mov     rcx, [rbp+phProvider]; hObject
0x180014533  test    rcx, rcx
0x180014536  jz      short loc_18001453E
0x180014538  call    cs:__imp_NCryptFreeObject
0x18001453e  lea     r11, [rsp+40h+var_s0]
0x180014543  mov     eax, ebx
0x180014545  mov     rbx, [r11+30h]
0x180014549  mov     rsi, [r11+40h]
0x18001454d  mov     rsp, r11
0x180014550  pop     r15
0x180014552  pop     r14
0x180014554  pop     r12
0x180014556  pop     rdi
0x180014557  pop     rbp
0x180014558  retn
```
