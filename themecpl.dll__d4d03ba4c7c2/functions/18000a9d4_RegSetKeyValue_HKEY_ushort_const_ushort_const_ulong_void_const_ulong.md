# _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x18000a9d4`
- end: `0x18000aa9f`
- name: `?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `203`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009a98`
- `0x180022950`
- `0x180023984`

## callees

- `0x18000a9d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa7b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aa63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000aa63`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000aa24`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000aa24`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v8; // rbx
  unsigned int v9; // edi
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v8 = a1;
  if ( a2 && *a2 )
  {
    v9 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18000a9d4  mov     r11, rsp
0x18000a9d7  mov     [r11+8], rbx
0x18000a9db  mov     [r11+18h], rbp
0x18000a9df  push    rsi
0x18000a9e0  push    rdi
0x18000a9e1  push    r14
0x18000a9e3  sub     rsp, 50h
0x18000a9e7  xor     r14d, r14d
0x18000a9ea  mov     esi, r9d
0x18000a9ed  mov     [r11+10h], r14
0x18000a9f1  mov     rbp, r8
0x18000a9f4  mov     rbx, rcx
0x18000a9f7  test    rdx, rdx
0x18000a9fa  jz      short loc_18000AA3D
0x18000a9fc  cmp     [rdx], r14w
0x18000aa00  jz      short loc_18000AA3D
0x18000aa02  mov     [r11-28h], r14
0x18000aa06  lea     rax, [r11+10h]
0x18000aa0a  mov     [r11-30h], rax
0x18000aa0e  xor     r9d, r9d; lpClass
0x18000aa11  mov     [r11-38h], r14
0x18000aa15  xor     r8d, r8d; Reserved
0x18000aa18  mov     [rsp+68h+samDesired], 2; samDesired
0x18000aa20  mov     [r11-48h], r14d
0x18000aa24  call    cs:__imp_RegCreateKeyExW
0x18000aa2b  nop     dword ptr [rax+rax+00h]
0x18000aa30  mov     edi, eax
0x18000aa32  test    eax, eax
0x18000aa34  jnz     short loc_18000AA87
0x18000aa36  mov     rcx, [rsp+68h+hKey]; hKey
0x18000aa3b  jmp     short loc_18000AA42
0x18000aa3d  mov     [rsp+68h+hKey], rbx
0x18000aa42  mov     eax, [rsp+68h+cbData]
0x18000aa49  mov     r9d, esi; dwType
0x18000aa4c  mov     [rsp+68h+samDesired], eax; cbData
0x18000aa50  xor     r8d, r8d; Reserved
0x18000aa53  mov     rax, [rsp+68h+arg_20]
0x18000aa5b  mov     rdx, rbp; lpValueName
0x18000aa5e  mov     [rsp+68h+lpData], rax; lpData
0x18000aa63  call    cs:__imp_RegSetValueExW
0x18000aa6a  nop     dword ptr [rax+rax+00h]
0x18000aa6f  mov     rcx, [rsp+68h+hKey]; hKey
0x18000aa74  mov     edi, eax
0x18000aa76  cmp     rcx, rbx
0x18000aa79  jz      short loc_18000AA87
0x18000aa7b  call    cs:__imp_RegCloseKey
0x18000aa82  nop     dword ptr [rax+rax+00h]
0x18000aa87  lea     r11, [rsp+68h+var_18]
0x18000aa8c  mov     eax, edi
0x18000aa8e  mov     rbx, [r11+20h]
0x18000aa92  mov     rbp, [r11+30h]
0x18000aa96  mov     rsp, r11
0x18000aa99  pop     r14
0x18000aa9b  pop     rdi
0x18000aa9c  pop     rsi
0x18000aa9d  retn
```
