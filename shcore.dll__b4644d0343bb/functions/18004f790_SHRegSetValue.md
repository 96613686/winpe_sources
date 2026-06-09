# SHRegSetValue

- ea: `0x18004f790`
- end: `0x18004f834`
- name: `SHRegSetValue`
- size: `164`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue, SRRF srrfFlags, DWORD dwType, LPCVOID pvData, DWORD cbData)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18004f790`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f7d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f7d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f823`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f811`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004f811`

## pseudocode

```c
LSTATUS __stdcall SHRegSetValue(
        HKEY hkey,
        LPCWSTR pszSubKey,
        LPCWSTR pszValue,
        SRRF srrfFlags,
        DWORD dwType,
        LPCVOID pvData,
        DWORD cbData)
{
  HKEY v8; // rbx
  LSTATUS v9; // edi
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  hKey = 0;
  v8 = hkey;
  if ( pszSubKey && *pszSubKey )
  {
    v9 = RegCreateKeyExW(hkey, pszSubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    hkey = hKey;
  }
  else
  {
    hKey = hkey;
  }
  v9 = RegSetValueExW(hkey, pszValue, 0, dwType, (const BYTE *)pvData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18004f790  mov     r11, rsp
0x18004f793  push    rbx
0x18004f794  push    rbp
0x18004f795  push    rsi
0x18004f796  push    rdi
0x18004f797  sub     rsp, 68h
0x18004f79b  xor     ebp, ebp
0x18004f79d  mov     rsi, r8
0x18004f7a0  mov     [r11-38h], rbp
0x18004f7a4  mov     rbx, rcx
0x18004f7a7  test    rdx, rdx
0x18004f7aa  jz      short loc_18004F7E6
0x18004f7ac  cmp     [rdx], bp
0x18004f7af  jz      short loc_18004F7E6
0x18004f7b1  mov     [r11-48h], rbp
0x18004f7b5  lea     rax, [r11-38h]
0x18004f7b9  mov     [r11-50h], rax
0x18004f7bd  xor     r9d, r9d; lpClass
0x18004f7c0  mov     [r11-58h], rbp
0x18004f7c4  xor     r8d, r8d; Reserved
0x18004f7c7  mov     [rsp+88h+samDesired], 2; samDesired
0x18004f7cf  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x18004f7d3  call    cs:__imp_RegCreateKeyExW
0x18004f7d9  mov     edi, eax
0x18004f7db  test    eax, eax
0x18004f7dd  jnz     short loc_18004F829
0x18004f7df  mov     rcx, [rsp+88h+hKey]; hKey
0x18004f7e4  jmp     short loc_18004F7EB
0x18004f7e6  mov     [rsp+88h+hKey], rbx
0x18004f7eb  mov     eax, [rsp+88h+cbData]
0x18004f7f2  xor     r8d, r8d; Reserved
0x18004f7f5  mov     r9d, [rsp+88h+dwType]; dwType
0x18004f7fd  mov     rdx, rsi; lpValueName
0x18004f800  mov     [rsp+88h+samDesired], eax; cbData
0x18004f804  mov     rax, [rsp+88h+pvData]
0x18004f80c  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x18004f811  call    cs:__imp_RegSetValueExW
0x18004f817  mov     rcx, [rsp+88h+hKey]; hKey
0x18004f81c  mov     edi, eax
0x18004f81e  cmp     rcx, rbx
0x18004f821  jz      short loc_18004F829
0x18004f823  call    cs:__imp_RegCloseKey
0x18004f829  mov     eax, edi
0x18004f82b  add     rsp, 68h
0x18004f82f  pop     rdi
0x18004f830  pop     rsi
0x18004f831  pop     rbp
0x18004f832  pop     rbx
0x18004f833  retn
```
