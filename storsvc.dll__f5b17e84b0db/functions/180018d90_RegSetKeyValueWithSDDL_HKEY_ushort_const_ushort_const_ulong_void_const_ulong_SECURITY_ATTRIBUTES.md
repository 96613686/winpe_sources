# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180018d90`
- end: `0x180018e52`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `194`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018cc0`
- `0x180018cfc`

## callees

- `0x180018d90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018de1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018de1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018e27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018e40`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v8; // edi
  HKEY v9; // rcx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v8 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v8 )
      return v8;
    v9 = hKey;
  }
  else
  {
    v9 = HKEY_CURRENT_USER;
    hKey = HKEY_CURRENT_USER;
  }
  v8 = RegSetValueExW(v9, a3, 0, a4, lpData, cbData);
  if ( hKey != HKEY_CURRENT_USER )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180018d90  mov     r11, rsp
0x180018d93  mov     [r11+8], rcx
0x180018d97  push    rbp
0x180018d98  push    rsi
0x180018d99  push    rdi
0x180018d9a  push    r14
0x180018d9c  sub     rsp, 58h
0x180018da0  xor     r14d, r14d
0x180018da3  mov     esi, r9d
0x180018da6  mov     [r11+8], r14
0x180018daa  mov     rbp, r8
0x180018dad  test    rdx, rdx
0x180018db0  jz      short loc_180018DF7
0x180018db2  cmp     [rdx], r14w
0x180018db6  jz      short loc_180018DF7
0x180018db8  mov     [r11-38h], r14
0x180018dbc  lea     rax, [r11+8]
0x180018dc0  mov     [r11-40h], rax
0x180018dc4  xor     r9d, r9d; lpClass
0x180018dc7  mov     [r11-48h], r14
0x180018dcb  xor     r8d, r8d; Reserved
0x180018dce  mov     [rsp+78h+samDesired], 2; samDesired
0x180018dd6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180018ddd  mov     [r11-58h], r14d
0x180018de1  call    cs:__imp_RegCreateKeyExW
0x180018de7  mov     edi, eax
0x180018de9  test    eax, eax
0x180018deb  jnz     short loc_180018E46
0x180018ded  mov     rcx, [rsp+78h+hKey]
0x180018df5  jmp     short loc_180018E06
0x180018df7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180018dfe  mov     [rsp+78h+hKey], rcx
0x180018e06  mov     eax, [rsp+78h+cbData]
0x180018e0d  mov     r9d, esi; dwType
0x180018e10  mov     [rsp+78h+samDesired], eax; cbData
0x180018e14  xor     r8d, r8d; Reserved
0x180018e17  mov     rax, [rsp+78h+arg_20]
0x180018e1f  mov     rdx, rbp; lpValueName
0x180018e22  mov     [rsp+78h+lpData], rax; lpData
0x180018e27  call    cs:__imp_RegSetValueExW
0x180018e2d  mov     rcx, [rsp+78h+hKey]; hKey
0x180018e35  mov     edi, eax
0x180018e37  cmp     rcx, 0FFFFFFFF80000001h
0x180018e3e  jz      short loc_180018E46
0x180018e40  call    cs:__imp_RegCloseKey
0x180018e46  mov     eax, edi
0x180018e48  add     rsp, 58h
0x180018e4c  pop     r14
0x180018e4e  pop     rdi
0x180018e4f  pop     rsi
0x180018e50  pop     rbp
0x180018e51  retn
```
