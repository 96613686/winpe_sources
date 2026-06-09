# GenericChainGetAdditionalStore(_CRYPT_PROVIDER_DATA *)

- ea: `0x18001a03c`
- end: `0x18001a0ca`
- name: `?GenericChainGetAdditionalStore@@YAPEAXPEAU_CRYPT_PROVIDER_DATA@@@Z`
- size: `142`
- prototype: `void *__fastcall(struct _CRYPT_PROVIDER_DATA *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019f14`

## callees

- `0x18001a03c`

## import_xrefs

- `CRYPT32!CertAddStoreToCollection` at `0x18001a0bb`
- `CRYPT32!CertAddStoreToCollection` at `0x18001a0bb`
- `CRYPT32!CertOpenStore` at `0x18001a08b`
- `CRYPT32!CertOpenStore` at `0x18001a08b`
- `CRYPT32!CertDuplicateStore` at `0x18001a061`
- `CRYPT32!CertDuplicateStore` at `0x18001a061`

## pseudocode

```c
HCERTSTORE __fastcall GenericChainGetAdditionalStore(struct _CRYPT_PROVIDER_DATA *a1)
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
0x18001a03c  mov     [rsp+arg_0], rbx
0x18001a041  mov     [rsp+arg_8], rsi
0x18001a046  push    rdi
0x18001a047  sub     rsp, 30h
0x18001a04b  cmp     dword ptr [rcx+58h], 0
0x18001a04f  mov     rbx, rcx
0x18001a052  jz      short loc_18001A09E
0x18001a054  cmp     dword ptr [rcx+58h], 1
0x18001a058  ja      short loc_18001A077
0x18001a05a  mov     rcx, [rcx+60h]
0x18001a05e  mov     rcx, [rcx]; hCertStore
0x18001a061  call    cs:__imp_CertDuplicateStore
0x18001a067  mov     rbx, [rsp+38h+arg_0]
0x18001a06c  mov     rsi, [rsp+38h+arg_8]
0x18001a071  add     rsp, 30h
0x18001a075  pop     rdi
0x18001a076  retn
0x18001a077  xor     edx, edx; dwEncodingType
0x18001a079  mov     [rsp+38h+pvPara], 0; pvPara
0x18001a082  xor     r9d, r9d; dwFlags
0x18001a085  xor     r8d, r8d; hCryptProv
0x18001a088  lea     ecx, [rdx+0Bh]; lpszStoreProvider
0x18001a08b  call    cs:__imp_CertOpenStore
0x18001a091  mov     rdi, rax
0x18001a094  test    rax, rax
0x18001a097  jnz     short loc_18001A0A2
0x18001a099  mov     rax, rdi
0x18001a09c  jmp     short loc_18001A067
0x18001a09e  xor     eax, eax
0x18001a0a0  jmp     short loc_18001A067
0x18001a0a2  xor     esi, esi
0x18001a0a4  cmp     [rbx+58h], esi
0x18001a0a7  jbe     short loc_18001A099
0x18001a0a9  mov     rdx, [rbx+60h]
0x18001a0ad  xor     r9d, r9d; dwPriority
0x18001a0b0  mov     rcx, rdi; hCollectionStore
0x18001a0b3  mov     rdx, [rdx+rsi*8]; hSiblingStore
0x18001a0b7  lea     r8d, [r9+1]; dwUpdateFlags
0x18001a0bb  call    cs:__imp_CertAddStoreToCollection
0x18001a0c1  inc     esi
0x18001a0c3  cmp     esi, [rbx+58h]
0x18001a0c6  jb      short loc_18001A0A9
0x18001a0c8  jmp     short loc_18001A099
```
