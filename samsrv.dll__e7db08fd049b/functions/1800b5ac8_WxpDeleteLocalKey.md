# WxpDeleteLocalKey

- ea: `0x1800b5ac8`
- end: `0x1800b5b44`
- name: `WxpDeleteLocalKey`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800b5b4c`

## callees

- `0x1800b53c4`
- `0x1800b5ac8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5aeb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b2d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5aeb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b01`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800b5b2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5b36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5b36`

## pseudocode

```c
char WxpDeleteLocalKey()
{
  HKEY v0; // rax
  HKEY v1; // rbx

  v0 = (HKEY)OpenLsaKey();
  v1 = v0;
  if ( v0 )
  {
    RegDeleteKeyExA(v0, "Data", 0, 0);
    RegDeleteKeyExA(v1, "Skew1", 0, 0);
    RegDeleteKeyExA(v1, "GBG", 0, 0);
    RegDeleteKeyExA(v1, "JD", 0, 0);
    RegCloseKey(v1);
    LOBYTE(v0) = 1;
  }
  return (char)v0;
}

```

## disassembly

```asm
0x1800b5ac8  push    rbx
0x1800b5aca  sub     rsp, 20h
0x1800b5ace  call    OpenLsaKey
0x1800b5ad3  mov     rbx, rax
0x1800b5ad6  test    rax, rax
0x1800b5ad9  jz      short loc_1800B5B3E
0x1800b5adb  xor     r9d, r9d; Reserved
0x1800b5ade  lea     rdx, aData; "Data"
0x1800b5ae5  xor     r8d, r8d; samDesired
0x1800b5ae8  mov     rcx, rbx; hKey
0x1800b5aeb  call    cs:__imp_RegDeleteKeyExA
0x1800b5af1  xor     r9d, r9d; Reserved
0x1800b5af4  lea     rdx, aSkew1; "Skew1"
0x1800b5afb  xor     r8d, r8d; samDesired
0x1800b5afe  mov     rcx, rbx; hKey
0x1800b5b01  call    cs:__imp_RegDeleteKeyExA
0x1800b5b07  xor     r9d, r9d; Reserved
0x1800b5b0a  lea     rdx, aGbg; "GBG"
0x1800b5b11  xor     r8d, r8d; samDesired
0x1800b5b14  mov     rcx, rbx; hKey
0x1800b5b17  call    cs:__imp_RegDeleteKeyExA
0x1800b5b1d  xor     r9d, r9d; Reserved
0x1800b5b20  lea     rdx, aJd; "JD"
0x1800b5b27  xor     r8d, r8d; samDesired
0x1800b5b2a  mov     rcx, rbx; hKey
0x1800b5b2d  call    cs:__imp_RegDeleteKeyExA
0x1800b5b33  mov     rcx, rbx; hKey
0x1800b5b36  call    cs:__imp_RegCloseKey
0x1800b5b3c  mov     al, 1
0x1800b5b3e  add     rsp, 20h
0x1800b5b42  pop     rbx
0x1800b5b43  retn
```
