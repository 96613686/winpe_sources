# WxpDeleteLocalKey

- ea: `0x180016e30`
- end: `0x180016eac`
- name: `WxpDeleteLocalKey`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016eb4`

## callees

- `0x18001672c`
- `0x180016e30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e69`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x180016e95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016e9e`

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
0x180016e30  push    rbx
0x180016e32  sub     rsp, 20h
0x180016e36  call    OpenLsaKey
0x180016e3b  mov     rbx, rax
0x180016e3e  test    rax, rax
0x180016e41  jz      short loc_180016EA6
0x180016e43  xor     r9d, r9d; Reserved
0x180016e46  lea     rdx, aData; "Data"
0x180016e4d  xor     r8d, r8d; samDesired
0x180016e50  mov     rcx, rbx; hKey
0x180016e53  call    cs:__imp_RegDeleteKeyExA
0x180016e59  xor     r9d, r9d; Reserved
0x180016e5c  lea     rdx, aSkew1; "Skew1"
0x180016e63  xor     r8d, r8d; samDesired
0x180016e66  mov     rcx, rbx; hKey
0x180016e69  call    cs:__imp_RegDeleteKeyExA
0x180016e6f  xor     r9d, r9d; Reserved
0x180016e72  lea     rdx, aGbg; "GBG"
0x180016e79  xor     r8d, r8d; samDesired
0x180016e7c  mov     rcx, rbx; hKey
0x180016e7f  call    cs:__imp_RegDeleteKeyExA
0x180016e85  xor     r9d, r9d; Reserved
0x180016e88  lea     rdx, aJd; "JD"
0x180016e8f  xor     r8d, r8d; samDesired
0x180016e92  mov     rcx, rbx; hKey
0x180016e95  call    cs:__imp_RegDeleteKeyExA
0x180016e9b  mov     rcx, rbx; hKey
0x180016e9e  call    cs:__imp_RegCloseKey
0x180016ea4  mov     al, 1
0x180016ea6  add     rsp, 20h
0x180016eaa  pop     rbx
0x180016eab  retn
```
