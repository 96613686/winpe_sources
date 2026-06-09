# ReadDwordRegistrySetting

- ea: `0x18002685c`
- end: `0x1800268ed`
- name: `ReadDwordRegistrySetting`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180026698`

## callees

- `0x18002685c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800268a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800268a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800268d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800268d7`

## pseudocode

```c
LSTATUS __fastcall ReadDwordRegistrySetting(__int64 a1, HKEY a2, const WCHAR *a3, BYTE *lpData, LSTATUS a5)
{
  LSTATUS result; // eax
  DWORD v9[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v10; // [rsp+50h] [rbp+8h] BYREF
  int v11; // [rsp+54h] [rbp+Ch]

  v11 = HIDWORD(a1);
  v9[0] = 0;
  v10 = 4;
  result = RegQueryValueExW(g_hkBase, a3, 0, v9, lpData, &v10);
  if ( result )
  {
    result = a5;
    *(_DWORD *)lpData = a5;
    if ( a2 )
      return RegSetValueExW(a2, a3, 0, 4u, lpData, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x18002685c  mov     r11, rsp
0x18002685f  mov     [r11+10h], rbx
0x180026863  mov     [r11+18h], rsi
0x180026867  mov     [r11+8], rcx
0x18002686b  push    rdi
0x18002686c  sub     rsp, 40h
0x180026870  mov     rcx, cs:?g_hkBase@@3PEAUHKEY__@@EA; hKey
0x180026877  lea     rax, [r11+8]
0x18002687b  mov     rsi, r8
0x18002687e  mov     [r11-20h], rax
0x180026882  mov     rbx, r9
0x180026885  mov     [rsp+48h+var_18], 0
0x18002688d  mov     rdi, rdx
0x180026890  mov     [r11-28h], rbx
0x180026894  mov     rdx, rsi; lpValueName
0x180026897  mov     [rsp+48h+arg_0], 4
0x18002689f  lea     r9, [r11-18h]; lpType
0x1800268a3  xor     r8d, r8d; lpReserved
0x1800268a6  call    cs:__imp_RegQueryValueExW
0x1800268ac  test    eax, eax
0x1800268ae  jz      short loc_1800268DD
0x1800268b0  mov     eax, [rsp+48h+arg_20]
0x1800268b4  mov     [rbx], eax
0x1800268b6  test    rdi, rdi
0x1800268b9  jz      short loc_1800268DD
0x1800268bb  mov     [rsp+48h+cbData], 4; cbData
0x1800268c3  mov     r9d, 4; dwType
0x1800268c9  xor     r8d, r8d; Reserved
0x1800268cc  mov     [rsp+48h+lpData], rbx; lpData
0x1800268d1  mov     rdx, rsi; lpValueName
0x1800268d4  mov     rcx, rdi; hKey
0x1800268d7  call    cs:__imp_RegSetValueExW
0x1800268dd  mov     rbx, [rsp+48h+arg_8]
0x1800268e2  mov     rsi, [rsp+48h+arg_10]
0x1800268e7  add     rsp, 40h
0x1800268eb  pop     rdi
0x1800268ec  retn
```
