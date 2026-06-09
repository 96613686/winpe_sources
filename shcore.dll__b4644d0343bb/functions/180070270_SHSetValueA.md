# SHSetValueA

- ea: `0x180070270`
- end: `0x180070340`
- name: `SHSetValueA`
- size: `208`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCSTR pszSubKey, LPCSTR pszValue, DWORD dwType, LPCVOID pvData, DWORD cbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180070b20`

## callees

- `0x180066910`
- `0x180070270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18007030e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18007030e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070320`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180070320`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800702dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800702dd`

## pseudocode

```c
LSTATUS __stdcall SHSetValueA(HKEY hkey, LPCSTR pszSubKey, LPCSTR pszValue, DWORD dwType, LPCVOID pvData, DWORD cbData)
{
  HKEY v8; // rdi
  LSTATUS v9; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  hKey = 0;
  v8 = hkey;
  if ( pszSubKey && *pszSubKey )
  {
    v9 = RegCreateKeyExA(hkey, pszSubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    hkey = hKey;
  }
  else
  {
    hKey = hkey;
  }
  v9 = RegSetValueExA(hkey, pszValue, 0, dwType, (const BYTE *)pvData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180070270  mov     r11, rsp
0x180070273  push    rbx
0x180070274  push    rbp
0x180070275  push    rsi
0x180070276  push    rdi
0x180070277  push    r14
0x180070279  sub     rsp, 60h
0x18007027d  mov     rax, cs:__security_cookie
0x180070284  xor     rax, rsp
0x180070287  mov     [rsp+88h+var_30], rax
0x18007028c  mov     r14, [rsp+88h+pvData]
0x180070294  mov     ebp, r9d
0x180070297  mov     qword ptr [r11-38h], 0
0x18007029f  mov     rsi, r8
0x1800702a2  mov     rdi, rcx
0x1800702a5  test    rdx, rdx
0x1800702a8  jz      short loc_1800702F0
0x1800702aa  cmp     byte ptr [rdx], 0
0x1800702ad  jz      short loc_1800702F0
0x1800702af  mov     qword ptr [r11-48h], 0
0x1800702b7  lea     rax, [r11-38h]
0x1800702bb  mov     [r11-50h], rax
0x1800702bf  xor     r9d, r9d; lpClass
0x1800702c2  mov     qword ptr [r11-58h], 0
0x1800702ca  xor     r8d, r8d; Reserved
0x1800702cd  mov     [rsp+88h+samDesired], 2; samDesired
0x1800702d5  mov     [rsp+88h+dwOptions], 0; dwOptions
0x1800702dd  call    cs:__imp_RegCreateKeyExA
0x1800702e3  mov     ebx, eax
0x1800702e5  test    eax, eax
0x1800702e7  jnz     short loc_180070326
0x1800702e9  mov     rcx, [rsp+88h+hKey]; hKey
0x1800702ee  jmp     short loc_1800702F5
0x1800702f0  mov     [rsp+88h+hKey], rcx
0x1800702f5  mov     eax, [rsp+88h+cbData]
0x1800702fc  mov     r9d, ebp; dwType
0x1800702ff  mov     [rsp+88h+samDesired], eax; cbData
0x180070303  xor     r8d, r8d; Reserved
0x180070306  mov     rdx, rsi; lpValueName
0x180070309  mov     qword ptr [rsp+88h+dwOptions], r14; lpData
0x18007030e  call    cs:__imp_RegSetValueExA
0x180070314  mov     rcx, [rsp+88h+hKey]; hKey
0x180070319  mov     ebx, eax
0x18007031b  cmp     rcx, rdi
0x18007031e  jz      short loc_180070326
0x180070320  call    cs:__imp_RegCloseKey
0x180070326  mov     eax, ebx
0x180070328  mov     rcx, [rsp+88h+var_30]
0x18007032d  xor     rcx, rsp; StackCookie
0x180070330  call    __security_check_cookie
0x180070335  add     rsp, 60h
0x180070339  pop     r14
0x18007033b  pop     rdi
0x18007033c  pop     rsi
0x18007033d  pop     rbp
0x18007033e  pop     rbx
0x18007033f  retn
```
