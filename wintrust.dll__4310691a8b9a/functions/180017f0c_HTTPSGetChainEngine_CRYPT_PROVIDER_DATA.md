# HTTPSGetChainEngine(_CRYPT_PROVIDER_DATA *)

- ea: `0x180017f0c`
- end: `0x180017ff3`
- name: `?HTTPSGetChainEngine@@YAPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `231`
- prototype: `void *__fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017c20`

## callees

- `0x180017f0c`
- `0x18004de6a`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180017fe0`
- `CRYPT32!CertCloseStore` at `0x180017fe0`
- `CRYPT32!CertOpenStore` at `0x180017f86`
- `CRYPT32!CertOpenStore` at `0x180017f86`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180017fc5`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180017fc5`

## pseudocode

```c
HCERTCHAINENGINE __fastcall HTTPSGetChainEngine(struct _CRYPT_PROVIDER_DATA *a1)
{
  WINTRUST_DATA *pWintrustData; // rax
  struct WINTRUST_FILE_INFO_ *pFile; // rax
  HCERTSTORE v5; // rax
  void *v6; // rbx
  HCERTSTORE hRestrictedRoot; // rcx
  bool v8; // zf
  _CERT_CHAIN_ENGINE_CONFIG pConfig; // [rsp+30h] [rbp-68h] BYREF
  HCERTCHAINENGINE phChainEngine; // [rsp+A0h] [rbp+8h] BYREF

  memset_0(&pConfig, 0, 0x58u);
  pWintrustData = a1->pWintrustData;
  phChainEngine = 0;
  if ( !pWintrustData )
    return 0;
  if ( pWintrustData->dwUnionChoice != 5 )
    return 0;
  pFile = pWintrustData->pFile;
  if ( pFile->cbStruct <= 0x28 || ((__int64)pFile[1].pcwszFilePath & 3) == 0 )
    return 0;
  pConfig.cbSize = 88;
  v5 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_10;
  hRestrictedRoot = pConfig.hRestrictedRoot;
  v8 = ((__int64)a1->pWintrustData->pFile[1].pcwszFilePath & 1) == 0;
  pConfig.hRestrictedTrust = v5;
  if ( !v8 )
    hRestrictedRoot = v5;
  pConfig.hRestrictedOther = v5;
  pConfig.hRestrictedRoot = hRestrictedRoot;
  if ( !CertCreateCertificateChainEngine(&pConfig, &phChainEngine) )
LABEL_10:
    phChainEngine = 0;
  CertCloseStore(v6, 0);
  return phChainEngine;
}

```

## disassembly

```asm
0x180017f0c  mov     [rsp+arg_8], rbx
0x180017f11  push    rdi
0x180017f12  sub     rsp, 90h
0x180017f19  mov     rdi, rcx
0x180017f1c  mov     ebx, 58h ; 'X'
0x180017f21  mov     r8d, ebx; Size
0x180017f24  lea     rcx, [rsp+98h+pConfig]; void *
0x180017f29  xor     edx, edx; Val
0x180017f2b  call    memset_0
0x180017f30  mov     rax, [rdi+8]
0x180017f34  mov     [rsp+98h+phChainEngine], 0
0x180017f40  test    rax, rax
0x180017f43  jz      short loc_180017F5B
0x180017f45  cmp     dword ptr [rax+20h], 5
0x180017f49  jnz     short loc_180017F5B
0x180017f4b  mov     rax, [rax+28h]
0x180017f4f  cmp     dword ptr [rax], 28h ; '('
0x180017f52  jbe     short loc_180017F5B
0x180017f54  mov     eax, [rax+28h]
0x180017f57  test    al, 3
0x180017f59  jnz     short loc_180017F6E
0x180017f5b  xor     eax, eax
0x180017f5d  mov     rbx, [rsp+98h+arg_8]
0x180017f65  add     rsp, 90h
0x180017f6c  pop     rdi
0x180017f6d  retn
0x180017f6e  xor     edx, edx; dwEncodingType
0x180017f70  mov     [rsp+98h+pConfig.cbSize], ebx
0x180017f74  xor     r9d, r9d; dwFlags
0x180017f77  mov     [rsp+98h+pvPara], 0; pvPara
0x180017f80  xor     r8d, r8d; hCryptProv
0x180017f83  lea     ecx, [rdx+2]; lpszStoreProvider
0x180017f86  call    cs:__imp_CertOpenStore
0x180017f8c  mov     rbx, rax
0x180017f8f  test    rax, rax
0x180017f92  jz      short loc_180017FCF
0x180017f94  mov     rcx, [rdi+8]
0x180017f98  mov     rdx, [rcx+28h]
0x180017f9c  mov     rcx, [rsp+98h+pConfig.hRestrictedRoot]
0x180017fa1  test    byte ptr [rdx+28h], 1
0x180017fa5  lea     rdx, [rsp+98h+phChainEngine]; phChainEngine
0x180017fad  mov     [rsp+98h+pConfig.hRestrictedTrust], rax
0x180017fb2  cmovnz  rcx, rax
0x180017fb6  mov     [rsp+98h+pConfig.hRestrictedOther], rax
0x180017fbb  mov     [rsp+98h+pConfig.hRestrictedRoot], rcx
0x180017fc0  lea     rcx, [rsp+98h+pConfig]; pConfig
0x180017fc5  call    cs:__imp_CertCreateCertificateChainEngine
0x180017fcb  test    eax, eax
0x180017fcd  jnz     short loc_180017FDB
0x180017fcf  mov     [rsp+98h+phChainEngine], 0
0x180017fdb  xor     edx, edx; dwFlags
0x180017fdd  mov     rcx, rbx; hCertStore
0x180017fe0  call    cs:__imp_CertCloseStore
0x180017fe6  mov     rax, [rsp+98h+phChainEngine]
0x180017fee  jmp     loc_180017F5D
```
