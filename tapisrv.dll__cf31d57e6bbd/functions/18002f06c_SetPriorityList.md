# SetPriorityList

- ea: `0x18002f06c`
- end: `0x18002f0ce`
- name: `SetPriorityList`
- size: `98`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, LPCWSTR lpString)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027ec0`
- `0x18002f0d4`

## callees

- `0x18002f06c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f089`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f089`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f0b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f0b8`
- `KERNEL32!lstrlenW` at `0x18002f094`
- `KERNEL32!lstrlenW` at `0x18002f094`

## pseudocode

```c
LSTATUS __fastcall SetPriorityList(HKEY hKey, LPCWSTR lpValueName, LPCWSTR lpString)
{
  int v7; // eax

  if ( !lpString )
    return RegDeleteValueW(hKey, lpValueName);
  v7 = lstrlenW(lpString);
  return RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)lpString + 2, 2 * v7);
}

```

## disassembly

```asm
0x18002f06c  mov     [rsp+arg_0], rbx
0x18002f071  mov     [rsp+arg_8], rsi
0x18002f076  push    rdi
0x18002f077  sub     rsp, 30h
0x18002f07b  mov     rbx, r8
0x18002f07e  mov     rdi, rdx
0x18002f081  mov     rsi, rcx
0x18002f084  test    r8, r8
0x18002f087  jnz     short loc_18002F091
0x18002f089  call    cs:__imp_RegDeleteValueW
0x18002f08f  jmp     short loc_18002F0BE
0x18002f091  mov     rcx, rbx; lpString
0x18002f094  call    cs:__imp_lstrlenW
0x18002f09a  lea     rcx, [rbx+2]
0x18002f09e  mov     r9d, 1; dwType
0x18002f0a4  add     eax, eax
0x18002f0a6  xor     r8d, r8d; Reserved
0x18002f0a9  mov     [rsp+38h+cbData], eax; cbData
0x18002f0ad  mov     rdx, rdi; lpValueName
0x18002f0b0  mov     [rsp+38h+lpData], rcx; lpData
0x18002f0b5  mov     rcx, rsi; hKey
0x18002f0b8  call    cs:__imp_RegSetValueExW
0x18002f0be  mov     rbx, [rsp+38h+arg_0]
0x18002f0c3  mov     rsi, [rsp+38h+arg_8]
0x18002f0c8  add     rsp, 30h
0x18002f0cc  pop     rdi
0x18002f0cd  retn
```
