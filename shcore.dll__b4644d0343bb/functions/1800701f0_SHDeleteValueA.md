# SHDeleteValueA

- ea: `0x1800701f0`
- end: `0x180070268`
- name: `SHDeleteValueA`
- size: `120`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCSTR pszSubKey, LPCSTR pszValue)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180066910`
- `0x1800701f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18007023b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18007023b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180070227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180070227`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070248`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070248`

## pseudocode

```c
LSTATUS __stdcall SHDeleteValueA(HKEY hkey, LPCSTR pszSubKey, LPCSTR pszValue)
{
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExA(hkey, pszSubKey, 0, 2u, &hKey);
  if ( !v4 )
  {
    v4 = RegDeleteValueA(hKey, pszValue);
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800701f0  mov     r11, rsp
0x1800701f3  mov     [r11+20h], rbx
0x1800701f7  push    rdi
0x1800701f8  sub     rsp, 40h
0x1800701fc  mov     rax, cs:__security_cookie
0x180070203  xor     rax, rsp
0x180070206  mov     [rsp+48h+var_10], rax
0x18007020b  mov     rdi, r8
0x18007020e  mov     qword ptr [r11-18h], 0
0x180070216  lea     rax, [r11-18h]
0x18007021a  xor     r8d, r8d; ulOptions
0x18007021d  mov     r9d, 2; samDesired
0x180070223  mov     [r11-28h], rax
0x180070227  call    cs:__imp_RegOpenKeyExA
0x18007022d  mov     ebx, eax
0x18007022f  test    eax, eax
0x180070231  jnz     short loc_18007024E
0x180070233  mov     rcx, [rsp+48h+hKey]; hKey
0x180070238  mov     rdx, rdi; lpValueName
0x18007023b  call    cs:__imp_RegDeleteValueA
0x180070241  mov     rcx, [rsp+48h+hKey]; hKey
0x180070246  mov     ebx, eax
0x180070248  call    cs:__imp_RegCloseKey
0x18007024e  mov     eax, ebx
0x180070250  mov     rcx, [rsp+48h+var_10]
0x180070255  xor     rcx, rsp; StackCookie
0x180070258  call    __security_check_cookie
0x18007025d  mov     rbx, [rsp+48h+arg_18]
0x180070262  add     rsp, 40h
0x180070266  pop     rdi
0x180070267  retn
```
