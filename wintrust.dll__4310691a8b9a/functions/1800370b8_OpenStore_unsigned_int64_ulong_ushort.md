# _OpenStore(unsigned __int64,ulong,ushort *)

- ea: `0x1800370b8`
- end: `0x18003711d`
- name: `?_OpenStore@@YAPEAX_KKPEAG@Z`
- size: `101`
- prototype: `void *__fastcall(HCRYPTPROV_LEGACY hCryptProv, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000da18`

## callees

- `0x1800370b8`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x1800370e6`
- `CRYPT32!CertOpenStore` at `0x180037107`
- `CRYPT32!CertOpenStore` at `0x1800370e6`
- `CRYPT32!CertOpenStore` at `0x180037107`

## pseudocode

```c
HCERTSTORE __fastcall _OpenStore(HCRYPTPROV_LEGACY hCryptProv, int a2, unsigned __int16 *pvPara)
{
  HCERTSTORE result; // rax

  result = CertOpenStore((LPCSTR)0xA, 0, hCryptProv, a2 | 0x4001u, pvPara);
  if ( !result )
    return CertOpenStore((LPCSTR)0xA, 0, hCryptProv, a2 | 0x8001u, pvPara);
  return result;
}

```

## disassembly

```asm
0x1800370b8  mov     [rsp+arg_0], rbx
0x1800370bd  mov     [rsp+arg_8], rsi
0x1800370c2  push    rdi
0x1800370c3  sub     rsp, 30h
0x1800370c7  mov     r9d, edx
0x1800370ca  mov     [rsp+38h+pvPara], r8; pvPara
0x1800370cf  mov     ebx, edx
0x1800370d1  mov     rdi, r8
0x1800370d4  xor     edx, edx; dwEncodingType
0x1800370d6  mov     rsi, rcx
0x1800370d9  mov     r8, rcx; hCryptProv
0x1800370dc  or      r9d, 4001h; dwFlags
0x1800370e3  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800370e6  call    cs:__imp_CertOpenStore
0x1800370ec  test    rax, rax
0x1800370ef  jnz     short loc_18003710D
0x1800370f1  or      ebx, 8001h
0x1800370f7  mov     [rsp+38h+pvPara], rdi; pvPara
0x1800370fc  mov     r9d, ebx; dwFlags
0x1800370ff  lea     ecx, [rax+0Ah]; lpszStoreProvider
0x180037102  mov     r8, rsi; hCryptProv
0x180037105  xor     edx, edx; dwEncodingType
0x180037107  call    cs:__imp_CertOpenStore
0x18003710d  mov     rbx, [rsp+38h+arg_0]
0x180037112  mov     rsi, [rsp+38h+arg_8]
0x180037117  add     rsp, 30h
0x18003711b  pop     rdi
0x18003711c  retn
```
