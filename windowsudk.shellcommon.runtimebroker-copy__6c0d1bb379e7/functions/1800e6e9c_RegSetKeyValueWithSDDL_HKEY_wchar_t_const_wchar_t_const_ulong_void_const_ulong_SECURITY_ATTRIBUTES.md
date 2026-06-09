# _RegSetKeyValueWithSDDL(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800e6e9c`
- end: `0x1800e6f54`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEB_W1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const wchar_t *, const wchar_t *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e6d88`
- `0x1800e6dcc`
- `0x1800e6f5c`

## callees

- `0x1800e6e9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6f37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6f37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e6f25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800e6f25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e6eec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800e6eec`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const wchar_t *a2,
        const wchar_t *a3,
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
0x1800e6e9c  mov     r11, rsp
0x1800e6e9f  mov     [r11+8], rbx
0x1800e6ea3  mov     [r11+18h], rbp
0x1800e6ea7  push    rsi
0x1800e6ea8  push    rdi
0x1800e6ea9  push    r14
0x1800e6eab  sub     rsp, 50h
0x1800e6eaf  xor     r14d, r14d
0x1800e6eb2  mov     esi, r9d
0x1800e6eb5  mov     [r11+10h], r14
0x1800e6eb9  mov     rbp, r8
0x1800e6ebc  mov     rbx, rcx
0x1800e6ebf  test    rdx, rdx
0x1800e6ec2  jz      short loc_1800E6EFF
0x1800e6ec4  cmp     [rdx], r14w
0x1800e6ec8  jz      short loc_1800E6EFF
0x1800e6eca  mov     [r11-28h], r14
0x1800e6ece  lea     rax, [r11+10h]
0x1800e6ed2  mov     [r11-30h], rax
0x1800e6ed6  xor     r9d, r9d; lpClass
0x1800e6ed9  mov     [r11-38h], r14
0x1800e6edd  xor     r8d, r8d; Reserved
0x1800e6ee0  mov     [rsp+68h+samDesired], 2; samDesired
0x1800e6ee8  mov     [r11-48h], r14d
0x1800e6eec  call    cs:__imp_RegCreateKeyExW
0x1800e6ef2  mov     edi, eax
0x1800e6ef4  test    eax, eax
0x1800e6ef6  jnz     short loc_1800E6F3D
0x1800e6ef8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800e6efd  jmp     short loc_1800E6F04
0x1800e6eff  mov     [rsp+68h+hKey], rbx
0x1800e6f04  mov     eax, [rsp+68h+cbData]
0x1800e6f0b  mov     r9d, esi; dwType
0x1800e6f0e  mov     [rsp+68h+samDesired], eax; cbData
0x1800e6f12  xor     r8d, r8d; Reserved
0x1800e6f15  mov     rax, [rsp+68h+arg_20]
0x1800e6f1d  mov     rdx, rbp; lpValueName
0x1800e6f20  mov     [rsp+68h+lpData], rax; lpData
0x1800e6f25  call    cs:__imp_RegSetValueExW
0x1800e6f2b  mov     rcx, [rsp+68h+hKey]; hKey
0x1800e6f30  mov     edi, eax
0x1800e6f32  cmp     rcx, rbx
0x1800e6f35  jz      short loc_1800E6F3D
0x1800e6f37  call    cs:__imp_RegCloseKey
0x1800e6f3d  lea     r11, [rsp+68h+var_18]
0x1800e6f42  mov     eax, edi
0x1800e6f44  mov     rbx, [r11+20h]
0x1800e6f48  mov     rbp, [r11+30h]
0x1800e6f4c  mov     rsp, r11
0x1800e6f4f  pop     r14
0x1800e6f51  pop     rdi
0x1800e6f52  pop     rsi
0x1800e6f53  retn
```
