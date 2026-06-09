# SHDeleteEmptyKeyA

- ea: `0x1800700d0`
- end: `0x1800701e0`
- name: `SHDeleteEmptyKeyA`
- size: `272`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCSTR pszSubKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180066910`
- `0x1800700d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180070111`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180070111`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180070180`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180070180`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800701a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExA` at `0x1800701a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800701b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800701b6`

## pseudocode

```c
LSTATUS __stdcall SHDeleteEmptyKeyA(HKEY hkey, LPCSTR pszSubKey)
{
  LSTATUS v4; // ebx
  HKEY hKey; // [rsp+60h] [rbp-28h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-20h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-1Ch] BYREF

  hKey = 0;
  v4 = RegOpenKeyExA(hkey, pszSubKey, 0, 0x2001Bu, &hKey);
  if ( !v4 )
  {
    cSubKeys = 0;
    cValues = 0;
    if ( RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) || cValues || cSubKeys )
      v4 = 145;
    else
      v4 = RegDeleteKeyExA(hkey, pszSubKey, 0, 0);
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800700d0  mov     r11, rsp
0x1800700d3  mov     [r11+18h], rbx
0x1800700d7  mov     [r11+20h], rsi
0x1800700db  push    rdi
0x1800700dc  sub     rsp, 80h
0x1800700e3  mov     rax, cs:__security_cookie
0x1800700ea  xor     rax, rsp
0x1800700ed  mov     [rsp+88h+var_18], rax
0x1800700f2  lea     rax, [r11-28h]
0x1800700f6  mov     qword ptr [r11-28h], 0
0x1800700fe  mov     r9d, 2001Bh; samDesired
0x180070104  mov     [r11-68h], rax
0x180070108  xor     r8d, r8d; ulOptions
0x18007010b  mov     rsi, rdx
0x18007010e  mov     rdi, rcx
0x180070111  call    cs:__imp_RegOpenKeyExA
0x180070117  mov     ebx, eax
0x180070119  test    eax, eax
0x18007011b  jnz     loc_1800701BC
0x180070121  mov     rcx, [rsp+88h+hKey]; hKey
0x180070126  xor     r9d, r9d; lpReserved
0x180070129  mov     [rsp+88h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180070132  xor     r8d, r8d; lpcchClass
0x180070135  mov     [rsp+88h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18007013e  xor     edx, edx; lpClass
0x180070140  mov     [rsp+88h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180070149  mov     [rsp+88h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180070152  mov     [rsp+88h+cSubKeys], eax
0x180070156  mov     [rsp+88h+cValues], eax
0x18007015a  lea     rax, [rsp+88h+cValues]
0x18007015f  mov     [rsp+88h+lpcValues], rax; lpcValues
0x180070164  lea     rax, [rsp+88h+cSubKeys]
0x180070169  mov     [rsp+88h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180070172  mov     [rsp+88h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x18007017b  mov     [rsp+88h+lpcSubKeys], rax; lpcSubKeys
0x180070180  call    cs:__imp_RegQueryInfoKeyA
0x180070186  test    eax, eax
0x180070188  jnz     short loc_1800701AC
0x18007018a  cmp     [rsp+88h+cValues], eax
0x18007018e  jnz     short loc_1800701AC
0x180070190  cmp     [rsp+88h+cSubKeys], eax
0x180070194  jnz     short loc_1800701AC
0x180070196  xor     r9d, r9d; Reserved
0x180070199  xor     r8d, r8d; samDesired
0x18007019c  mov     rdx, rsi; lpSubKey
0x18007019f  mov     rcx, rdi; hKey
0x1800701a2  call    cs:__imp_RegDeleteKeyExA
0x1800701a8  mov     ebx, eax
0x1800701aa  jmp     short loc_1800701B1
0x1800701ac  mov     ebx, 91h
0x1800701b1  mov     rcx, [rsp+88h+hKey]; hKey
0x1800701b6  call    cs:__imp_RegCloseKey
0x1800701bc  mov     eax, ebx
0x1800701be  mov     rcx, [rsp+88h+var_18]
0x1800701c3  xor     rcx, rsp; StackCookie
0x1800701c6  call    __security_check_cookie
0x1800701cb  lea     r11, [rsp+88h+var_8]
0x1800701d3  mov     rbx, [r11+20h]
0x1800701d7  mov     rsi, [r11+28h]
0x1800701db  mov     rsp, r11
0x1800701de  pop     rdi
0x1800701df  retn
```
