# SHDeleteEmptyKeyW

- ea: `0x180070350`
- end: `0x180070460`
- name: `SHDeleteEmptyKeyW`
- size: `272`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004d37c`

## callees

- `0x180066910`
- `0x180070350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180070422`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180070422`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180070400`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180070400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070436`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070436`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070391`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180070391`

## pseudocode

```c
LSTATUS __stdcall SHDeleteEmptyKeyW(HKEY hkey, LPCWSTR pszSubKey)
{
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+60h] [rbp-28h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-1Ch] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(hkey, pszSubKey, 0, 0x2001Bu, &hKey);
  if ( !v4 )
  {
    cSubKeys = 0;
    cValues = 0;
    if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) || cValues || cSubKeys )
      v4 = 145;
    else
      v4 = RegDeleteKeyExW(hkey, pszSubKey, 0, 0);
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180070350  mov     r11, rsp
0x180070353  mov     [r11+18h], rbx
0x180070357  mov     [r11+20h], rsi
0x18007035b  push    rdi
0x18007035c  sub     rsp, 80h
0x180070363  mov     rax, cs:__security_cookie
0x18007036a  xor     rax, rsp
0x18007036d  mov     [rsp+88h+var_18], rax
0x180070372  lea     rax, [r11-28h]
0x180070376  mov     qword ptr [r11-28h], 0
0x18007037e  mov     r9d, 2001Bh; samDesired
0x180070384  mov     [r11-68h], rax
0x180070388  xor     r8d, r8d; ulOptions
0x18007038b  mov     rsi, rdx
0x18007038e  mov     rdi, rcx
0x180070391  call    cs:__imp_RegOpenKeyExW
0x180070397  mov     ebx, eax
0x180070399  test    eax, eax
0x18007039b  jnz     loc_18007043C
0x1800703a1  mov     rcx, [rsp+88h+hKey]; hKey
0x1800703a6  xor     r9d, r9d; lpReserved
0x1800703a9  mov     [rsp+88h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800703b2  xor     r8d, r8d; lpcchClass
0x1800703b5  mov     [rsp+88h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800703be  xor     edx, edx; lpClass
0x1800703c0  mov     [rsp+88h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800703c9  mov     [rsp+88h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800703d2  mov     [rsp+88h+cSubKeys], eax
0x1800703d6  mov     [rsp+88h+cValues], eax
0x1800703da  lea     rax, [rsp+88h+cValues]
0x1800703df  mov     [rsp+88h+lpcValues], rax; lpcValues
0x1800703e4  lea     rax, [rsp+88h+cSubKeys]
0x1800703e9  mov     [rsp+88h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800703f2  mov     [rsp+88h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800703fb  mov     [rsp+88h+lpcSubKeys], rax; lpcSubKeys
0x180070400  call    cs:__imp_RegQueryInfoKeyW
0x180070406  test    eax, eax
0x180070408  jnz     short loc_18007042C
0x18007040a  cmp     [rsp+88h+cValues], eax
0x18007040e  jnz     short loc_18007042C
0x180070410  cmp     [rsp+88h+cSubKeys], eax
0x180070414  jnz     short loc_18007042C
0x180070416  xor     r9d, r9d; Reserved
0x180070419  xor     r8d, r8d; samDesired
0x18007041c  mov     rdx, rsi; lpSubKey
0x18007041f  mov     rcx, rdi; hKey
0x180070422  call    cs:__imp_RegDeleteKeyExW
0x180070428  mov     ebx, eax
0x18007042a  jmp     short loc_180070431
0x18007042c  mov     ebx, 91h
0x180070431  mov     rcx, [rsp+88h+hKey]; hKey
0x180070436  call    cs:__imp_RegCloseKey
0x18007043c  mov     eax, ebx
0x18007043e  mov     rcx, [rsp+88h+var_18]
0x180070443  xor     rcx, rsp; StackCookie
0x180070446  call    __security_check_cookie
0x18007044b  lea     r11, [rsp+88h+var_8]
0x180070453  mov     rbx, [r11+20h]
0x180070457  mov     rsi, [r11+28h]
0x18007045b  mov     rsp, r11
0x18007045e  pop     rdi
0x18007045f  retn
```
