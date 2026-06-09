# SHDeleteValueW

- ea: `0x18004c200`
- end: `0x18004c278`
- name: `SHDeleteValueW`
- size: `120`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18004d37c`

## callees

- `0x18004c200`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c258`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c237`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004c24b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004c24b`

## pseudocode

```c
LSTATUS __stdcall SHDeleteValueW(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue)
{
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(hkey, pszSubKey, 0, 2u, &hKey);
  if ( !v4 )
  {
    v4 = RegDeleteValueW(hKey, pszValue);
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x18004c200  mov     r11, rsp
0x18004c203  mov     [r11+20h], rbx
0x18004c207  push    rdi
0x18004c208  sub     rsp, 40h
0x18004c20c  mov     rax, cs:__security_cookie
0x18004c213  xor     rax, rsp
0x18004c216  mov     [rsp+48h+var_10], rax
0x18004c21b  mov     rdi, r8
0x18004c21e  mov     qword ptr [r11-18h], 0
0x18004c226  lea     rax, [r11-18h]
0x18004c22a  xor     r8d, r8d; ulOptions
0x18004c22d  mov     r9d, 2; samDesired
0x18004c233  mov     [r11-28h], rax
0x18004c237  call    cs:__imp_RegOpenKeyExW
0x18004c23d  mov     ebx, eax
0x18004c23f  test    eax, eax
0x18004c241  jnz     short loc_18004C25E
0x18004c243  mov     rcx, [rsp+48h+hKey]; hKey
0x18004c248  mov     rdx, rdi; lpValueName
0x18004c24b  call    cs:__imp_RegDeleteValueW
0x18004c251  mov     rcx, [rsp+48h+hKey]; hKey
0x18004c256  mov     ebx, eax
0x18004c258  call    cs:__imp_RegCloseKey
0x18004c25e  mov     eax, ebx
0x18004c260  mov     rcx, [rsp+48h+var_10]
0x18004c265  xor     rcx, rsp; StackCookie
0x18004c268  call    __security_check_cookie
0x18004c26d  mov     rbx, [rsp+48h+arg_18]
0x18004c272  add     rsp, 40h
0x18004c276  pop     rdi
0x18004c277  retn
```
