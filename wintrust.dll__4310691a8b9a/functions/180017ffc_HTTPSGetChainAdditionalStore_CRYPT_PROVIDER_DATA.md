# HTTPSGetChainAdditionalStore(_CRYPT_PROVIDER_DATA *)

- ea: `0x180017ffc`
- end: `0x180018088`
- name: `?HTTPSGetChainAdditionalStore@@YAPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `140`
- prototype: `void *__fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017c20`

## callees

- `0x180017ffc`

## import_xrefs

- `CRYPT32!CertAddStoreToCollection` at `0x180018076`
- `CRYPT32!CertAddStoreToCollection` at `0x180018076`
- `CRYPT32!CertOpenStore` at `0x18001804f`
- `CRYPT32!CertOpenStore` at `0x18001804f`
- `CRYPT32!CertDuplicateStore` at `0x180018021`
- `CRYPT32!CertDuplicateStore` at `0x180018021`

## pseudocode

```c
HCERTSTORE __fastcall HTTPSGetChainAdditionalStore(struct _CRYPT_PROVIDER_DATA *a1)
{
  HCERTSTORE v3; // rdi
  __int64 i; // rsi

  if ( !a1->chStores )
    return 0;
  if ( a1->chStores <= 1 )
    return CertDuplicateStore(*a1->pahStores);
  v3 = CertOpenStore((LPCSTR)0xB, 0, 0, 0, 0);
  if ( v3 )
  {
    for ( i = 0; (unsigned int)i < a1->chStores; i = (unsigned int)(i + 1) )
      CertAddStoreToCollection(v3, a1->pahStores[i], 1u, 0);
  }
  return v3;
}

```

## disassembly

```asm
0x180017ffc  mov     [rsp+arg_0], rbx
0x180018001  mov     [rsp+arg_8], rsi
0x180018006  push    rdi
0x180018007  sub     rsp, 30h
0x18001800b  cmp     dword ptr [rcx+58h], 0
0x18001800f  mov     rbx, rcx
0x180018012  jz      short loc_180018037
0x180018014  cmp     dword ptr [rcx+58h], 1
0x180018018  ja      short loc_18001803B
0x18001801a  mov     rcx, [rcx+60h]
0x18001801e  mov     rcx, [rcx]; hCertStore
0x180018021  call    cs:__imp_CertDuplicateStore
0x180018027  mov     rbx, [rsp+38h+arg_0]
0x18001802c  mov     rsi, [rsp+38h+arg_8]
0x180018031  add     rsp, 30h
0x180018035  pop     rdi
0x180018036  retn
0x180018037  xor     eax, eax
0x180018039  jmp     short loc_180018027
0x18001803b  xor     edx, edx; dwEncodingType
0x18001803d  mov     [rsp+38h+pvPara], 0; pvPara
0x180018046  xor     r9d, r9d; dwFlags
0x180018049  xor     r8d, r8d; hCryptProv
0x18001804c  lea     ecx, [rdx+0Bh]; lpszStoreProvider
0x18001804f  call    cs:__imp_CertOpenStore
0x180018055  mov     rdi, rax
0x180018058  test    rax, rax
0x18001805b  jz      short loc_180018083
0x18001805d  xor     esi, esi
0x18001805f  cmp     [rbx+58h], esi
0x180018062  jbe     short loc_180018083
0x180018064  mov     rdx, [rbx+60h]
0x180018068  xor     r9d, r9d; dwPriority
0x18001806b  mov     rcx, rdi; hCollectionStore
0x18001806e  mov     rdx, [rdx+rsi*8]; hSiblingStore
0x180018072  lea     r8d, [r9+1]; dwUpdateFlags
0x180018076  call    cs:__imp_CertAddStoreToCollection
0x18001807c  inc     esi
0x18001807e  cmp     esi, [rbx+58h]
0x180018081  jb      short loc_180018064
0x180018083  mov     rax, rdi
0x180018086  jmp     short loc_180018027
```
