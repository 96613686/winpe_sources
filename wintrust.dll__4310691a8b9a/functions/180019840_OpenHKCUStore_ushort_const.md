# _OpenHKCUStore(ushort const *)

- ea: `0x180019840`
- end: `0x180019882`
- name: `?_OpenHKCUStore@@YAPEAXPEBG@Z`
- size: `66`
- prototype: `void *__fastcall(const unsigned __int16 *pvPara)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018c30`
- `0x18002daac`

## callees

- `0x180019840`

## import_xrefs

- `CRYPT32!CertOpenStore` at `0x180019859`
- `CRYPT32!CertOpenStore` at `0x180019859`
- `CRYPT32!CertControlStore` at `0x180019873`
- `CRYPT32!CertControlStore` at `0x180019873`

## pseudocode

```c
HCERTSTORE __fastcall _OpenHKCUStore(const unsigned __int16 *pvPara)
{
  HCERTSTORE v1; // rax
  HCERTSTORE v2; // rbx

  v1 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x11080u, pvPara);
  v2 = v1;
  if ( v1 )
    CertControlStore(v1, 0, 4u, 0);
  return v2;
}

```

## disassembly

```asm
0x180019840  push    rbx
0x180019842  sub     rsp, 30h
0x180019846  xor     edx, edx; dwEncodingType
0x180019848  mov     [rsp+38h+pvPara], rcx; pvPara
0x18001984d  mov     r9d, 11080h; dwFlags
0x180019853  xor     r8d, r8d; hCryptProv
0x180019856  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180019859  call    cs:__imp_CertOpenStore
0x18001985f  mov     rbx, rax
0x180019862  test    rax, rax
0x180019865  jz      short loc_180019879
0x180019867  xor     r9d, r9d; pvCtrlPara
0x18001986a  xor     edx, edx; dwFlags
0x18001986c  mov     rcx, rax; hCertStore
0x18001986f  lea     r8d, [r9+4]; dwCtrlType
0x180019873  call    cs:__imp_CertControlStore
0x180019879  mov     rax, rbx
0x18001987c  add     rsp, 30h
0x180019880  pop     rbx
0x180019881  retn
```
