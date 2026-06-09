# WTHelperIsChainedToMicrosoftFromStateData

- ea: `0x180039380`
- end: `0x180039435`
- name: `WTHelperIsChainedToMicrosoftFromStateData`
- size: `181`
- prototype: `__int64 __fastcall(CRYPT_PROVIDER_DATA *pProvData, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001e4e0`
- `0x180039200`
- `0x180039380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003939c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003939c`
- `CRYPT32!CertCloseStore` at `0x180039419`
- `CRYPT32!CertCloseStore` at `0x180039419`
- `CRYPT32!CertOpenStore` at `0x1800393e1`
- `CRYPT32!CertOpenStore` at `0x1800393e1`

## pseudocode

```c
__int64 __fastcall WTHelperIsChainedToMicrosoftFromStateData(CRYPT_PROVIDER_DATA *pProvData, int a2)
{
  CRYPT_PROVIDER_DATA *v3; // rbx
  DWORD *padwTrustStepErrors; // rax
  HCERTSTORE v5; // rdi
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax

  v3 = pProvData;
  if ( pProvData )
  {
    padwTrustStepErrors = pProvData->padwTrustStepErrors;
    if ( !padwTrustStepErrors
      || padwTrustStepErrors[30]
      || padwTrustStepErrors[31]
      || padwTrustStepErrors[32]
      || padwTrustStepErrors[33]
      || (v5 = CertOpenStore((LPCSTR)1, pProvData->dwEncoding, 0, 0, pProvData->hMsg)) == 0 )
    {
      LODWORD(v3) = 0;
    }
    else
    {
      ProvSignerFromChain = WTHelperGetProvSignerFromChain(v3, 0, 0, 0);
      LODWORD(v3) = WTHelperIsChainedToMicrosoft(ProvSignerFromChain->pasCertChain->pCert, v5, a2);
      CertCloseStore(v5, 0);
    }
  }
  else
  {
    SetLastError(0x57u);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180039380  mov     [rsp+arg_0], rbx
0x180039385  mov     [rsp+arg_8], rsi
0x18003938a  push    rdi
0x18003938b  sub     rsp, 30h
0x18003938f  mov     esi, edx
0x180039391  mov     rbx, rcx
0x180039394  test    rcx, rcx
0x180039397  jnz     short loc_1800393A4
0x180039399  lea     ecx, [rbx+57h]; dwErrCode
0x18003939c  call    cs:__imp_SetLastError
0x1800393a2  jmp     short loc_180039423
0x1800393a4  mov     rax, [rcx+50h]
0x1800393a8  test    rax, rax
0x1800393ab  jz      short loc_180039421
0x1800393ad  cmp     dword ptr [rax+78h], 0
0x1800393b1  jnz     short loc_180039421
0x1800393b3  cmp     dword ptr [rax+7Ch], 0
0x1800393b7  jnz     short loc_180039421
0x1800393b9  cmp     dword ptr [rax+80h], 0
0x1800393c0  jnz     short loc_180039421
0x1800393c2  cmp     dword ptr [rax+84h], 0
0x1800393c9  jnz     short loc_180039421
0x1800393cb  mov     rax, [rcx+70h]
0x1800393cf  xor     r9d, r9d; dwFlags
0x1800393d2  mov     edx, [rcx+68h]; dwEncodingType
0x1800393d5  xor     r8d, r8d; hCryptProv
0x1800393d8  mov     [rsp+38h+pvPara], rax; pvPara
0x1800393dd  lea     ecx, [r9+1]; lpszStoreProvider
0x1800393e1  call    cs:__imp_CertOpenStore
0x1800393e7  mov     rdi, rax
0x1800393ea  test    rax, rax
0x1800393ed  jz      short loc_180039421
0x1800393ef  xor     r9d, r9d; idxCounterSigner
0x1800393f2  xor     r8d, r8d; fCounterSigner
0x1800393f5  xor     edx, edx; idxSigner
0x1800393f7  mov     rcx, rbx; pProvData
0x1800393fa  call    WTHelperGetProvSignerFromChain
0x1800393ff  mov     r8d, esi
0x180039402  mov     rdx, rdi; hSiblingStore
0x180039405  mov     rcx, [rax+10h]
0x180039409  mov     rcx, [rcx+8]; pCertContext
0x18003940d  call    WTHelperIsChainedToMicrosoft
0x180039412  xor     edx, edx; dwFlags
0x180039414  mov     rcx, rdi; hCertStore
0x180039417  mov     ebx, eax
0x180039419  call    cs:__imp_CertCloseStore
0x18003941f  jmp     short loc_180039423
0x180039421  xor     ebx, ebx
0x180039423  mov     rsi, [rsp+38h+arg_8]
0x180039428  mov     eax, ebx
0x18003942a  mov     rbx, [rsp+38h+arg_0]
0x18003942f  add     rsp, 30h
0x180039433  pop     rdi
0x180039434  retn
```
