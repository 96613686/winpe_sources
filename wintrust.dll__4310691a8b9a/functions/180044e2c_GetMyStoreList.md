# GetMyStoreList

- ea: `0x180044e2c`
- end: `0x180044eaa`
- name: `GetMyStoreList`
- size: `126`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180044eb0`

## callees

- `0x180044464`
- `0x180044490`
- `0x180044e2c`

## import_xrefs

- `CRYPT32!CertOpenSystemStoreA` at `0x180044e6a`
- `CRYPT32!CertOpenSystemStoreA` at `0x180044e6a`
- `CRYPT32!CertCloseStore` at `0x180044e87`
- `CRYPT32!CertCloseStore` at `0x180044e87`

## pseudocode

```c
HCERTSTORE *GetMyStoreList()
{
  HCERTSTORE *result; // rax
  HCERTSTORE *v1; // rdi
  int v2; // esi
  HCERTSTORE v3; // rax

  result = (HCERTSTORE *)ACAlloc(16);
  v1 = result;
  if ( result )
  {
    v2 = 0;
    *(_OWORD *)result = 0;
    while ( !v2 )
    {
      v3 = CertOpenSystemStoreA(0, "My");
      *v1 = v3;
      if ( !v3 )
      {
        if ( *v1 )
          CertCloseStore(*v1, 0);
        ACFree(v1);
        return 0;
      }
      v2 = 1;
    }
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180044e2c  mov     [rsp+arg_0], rbx
0x180044e31  mov     [rsp+arg_8], rsi
0x180044e36  push    rdi
0x180044e37  sub     rsp, 20h
0x180044e3b  mov     ecx, 10h
0x180044e40  call    ACAlloc
0x180044e45  mov     rdi, rax
0x180044e48  test    rax, rax
0x180044e4b  jz      short loc_180044E9A
0x180044e4d  xorps   xmm0, xmm0
0x180044e50  xor     esi, esi
0x180044e52  movups  xmmword ptr [rax], xmm0
0x180044e55  cmp     esi, 1
0x180044e58  jnb     short loc_180044E97
0x180044e5a  movsxd  rbx, esi
0x180044e5d  lea     rdx, off_180052F30; "My"
0x180044e64  xor     ecx, ecx; hProv
0x180044e66  mov     rdx, [rdx+rbx*8]; szSubsystemProtocol
0x180044e6a  call    cs:__imp_CertOpenSystemStoreA
0x180044e70  mov     [rdi+rbx*8], rax
0x180044e74  test    rax, rax
0x180044e77  jz      short loc_180044E7D
0x180044e79  inc     esi
0x180044e7b  jmp     short loc_180044E55
0x180044e7d  mov     rcx, [rdi]; hCertStore
0x180044e80  test    rcx, rcx
0x180044e83  jz      short loc_180044E8D
0x180044e85  xor     edx, edx; dwFlags
0x180044e87  call    cs:__imp_CertCloseStore
0x180044e8d  mov     rcx, rdi
0x180044e90  call    ACFree
0x180044e95  xor     edi, edi
0x180044e97  mov     rax, rdi
0x180044e9a  mov     rbx, [rsp+28h+arg_0]
0x180044e9f  mov     rsi, [rsp+28h+arg_8]
0x180044ea4  add     rsp, 20h
0x180044ea8  pop     rdi
0x180044ea9  retn
```
