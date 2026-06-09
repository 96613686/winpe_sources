# GetChainEngine(_CRYPT_PROVIDER_DATA *)

- ea: `0x180018660`
- end: `0x180018773`
- name: `?GetChainEngine@@YAPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `275`
- prototype: `void *__fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018090`

## callees

- `0x180018660`
- `0x18004de6a`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180018764`
- `CRYPT32!CertCloseStore` at `0x180018764`
- `CRYPT32!CertOpenStore` at `0x1800186ff`
- `CRYPT32!CertOpenStore` at `0x1800186ff`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18001874d`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x18001874d`

## pseudocode

```c
HCERTCHAINENGINE __fastcall GetChainEngine(struct _CRYPT_PROVIDER_DATA *a1)
{
  WINTRUST_DATA *pWintrustData; // rdx
  struct WINTRUST_FILE_INFO_ *pFile; // rax
  HCERTSTORE v5; // rax
  void *v6; // rbx
  HCERTSTORE hRestrictedRoot; // rcx
  struct _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+30h] [rbp-9h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+A0h] [rbp+67h] BYREF

  memset_0(&pConfig, 0, 0x58u);
  pWintrustData = a1->pWintrustData;
  phChainEngine = 0;
  if ( !pWintrustData )
    return 0;
  if ( pWintrustData->dwUnionChoice != 5 )
    return (HCERTCHAINENGINE)((pWintrustData->dwProvFlags >> 3) & 1);
  pFile = pWintrustData->pFile;
  if ( pFile->cbStruct <= 0x28 )
    return (HCERTCHAINENGINE)((pWintrustData->dwProvFlags >> 3) & 1);
  if ( ((__int64)pFile[1].pcwszFilePath & 7) == 0 && (pWintrustData->dwProvFlags & 8) == 0 )
    return 0;
  pConfig.cbSize = 88;
  if ( ((__int64)pWintrustData->pFile[1].pcwszFilePath & 3) == 0 )
  {
    v6 = 0;
    goto LABEL_14;
  }
  v5 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  v6 = v5;
  if ( v5 )
  {
    pWintrustData = a1->pWintrustData;
    hRestrictedRoot = pConfig.hRestrictedRoot;
    if ( ((__int64)pWintrustData->pFile[1].pcwszFilePath & 1) != 0 )
      hRestrictedRoot = v5;
    pConfig.hRestrictedTrust = v5;
    pConfig.hRestrictedRoot = hRestrictedRoot;
    pConfig.hRestrictedOther = v5;
LABEL_14:
    if ( (pWintrustData->dwProvFlags & 8) != 0 || ((__int64)pWintrustData->pFile[1].pcwszFilePath & 4) != 0 )
      pConfig.dwFlags |= 8u;
    if ( CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
      goto LABEL_19;
  }
  phChainEngine = 0;
LABEL_19:
  CertCloseStore(v6, 0);
  return phChainEngine;
}

```

## disassembly

```asm
0x180018660  mov     [rsp-8+arg_8], rbx
0x180018665  mov     [rsp-8+arg_10], rdi
0x18001866a  push    rbp
0x18001866b  lea     rbp, [rsp-57h]
0x180018670  sub     rsp, 90h
0x180018677  mov     rdi, rcx
0x18001867a  mov     ebx, 58h ; 'X'
0x18001867f  mov     r8d, ebx; Size
0x180018682  lea     rcx, [rbp+57h+pConfig]; void *
0x180018686  xor     edx, edx; Val
0x180018688  call    memset_0
0x18001868d  mov     rdx, [rdi+8]
0x180018691  mov     [rbp+57h+phChainEngine], 0
0x180018699  test    rdx, rdx
0x18001869c  jz      short loc_1800186C3
0x18001869e  cmp     dword ptr [rdx+20h], 5
0x1800186a2  jz      short loc_1800186C7
0x1800186a4  mov     eax, [rdx+48h]
0x1800186a7  shr     rax, 3
0x1800186ab  and     eax, 1
0x1800186ae  lea     r11, [rsp+90h+var_s0]
0x1800186b6  mov     rbx, [r11+18h]
0x1800186ba  mov     rdi, [r11+20h]
0x1800186be  mov     rsp, r11
0x1800186c1  pop     rbp
0x1800186c2  retn
0x1800186c3  xor     eax, eax
0x1800186c5  jmp     short loc_1800186AE
0x1800186c7  mov     rax, [rdx+28h]
0x1800186cb  cmp     dword ptr [rax], 28h ; '('
0x1800186ce  jbe     short loc_1800186A4
0x1800186d0  mov     eax, [rax+28h]
0x1800186d3  test    al, 7
0x1800186d5  jnz     short loc_1800186DE
0x1800186d7  mov     eax, [rdx+48h]
0x1800186da  test    al, 8
0x1800186dc  jz      short loc_1800186C3
0x1800186de  mov     [rbp+57h+pConfig.cbSize], ebx
0x1800186e1  mov     rax, [rdx+28h]
0x1800186e5  test    byte ptr [rax+28h], 3
0x1800186e9  jz      short loc_18001872F
0x1800186eb  xor     edx, edx; dwEncodingType
0x1800186ed  mov     [rsp+90h+pvPara], 0; pvPara
0x1800186f6  xor     r9d, r9d; dwFlags
0x1800186f9  xor     r8d, r8d; hCryptProv
0x1800186fc  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800186ff  call    cs:__imp_CertOpenStore
0x180018705  mov     rbx, rax
0x180018708  test    rax, rax
0x18001870b  jz      short loc_180018757
0x18001870d  mov     rdx, [rdi+8]
0x180018711  mov     rcx, [rdx+28h]
0x180018715  test    byte ptr [rcx+28h], 1
0x180018719  mov     rcx, [rbp+57h+pConfig.hRestrictedRoot]
0x18001871d  cmovnz  rcx, rax
0x180018721  mov     [rbp+57h+pConfig.hRestrictedTrust], rax
0x180018725  mov     [rbp+57h+pConfig.hRestrictedRoot], rcx
0x180018729  mov     [rbp+57h+pConfig.hRestrictedOther], rax
0x18001872d  jmp     short loc_180018731
0x18001872f  xor     ebx, ebx
0x180018731  test    byte ptr [rdx+48h], 8
0x180018735  jnz     short loc_180018741
0x180018737  mov     rax, [rdx+28h]
0x18001873b  test    byte ptr [rax+28h], 4
0x18001873f  jz      short loc_180018745
0x180018741  or      [rbp+57h+pConfig.dwFlags], 8
0x180018745  lea     rdx, [rbp+57h+phChainEngine]; phChainEngine
0x180018749  lea     rcx, [rbp+57h+pConfig]; pConfig
0x18001874d  call    cs:__imp_CertCreateCertificateChainEngine
0x180018753  test    eax, eax
0x180018755  jnz     short loc_18001875F
0x180018757  mov     [rbp+57h+phChainEngine], 0
0x18001875f  xor     edx, edx; dwFlags
0x180018761  mov     rcx, rbx; hCertStore
0x180018764  call    cs:__imp_CertCloseStore
0x18001876a  mov     rax, [rbp+57h+phChainEngine]
0x18001876e  jmp     loc_1800186AE
```
