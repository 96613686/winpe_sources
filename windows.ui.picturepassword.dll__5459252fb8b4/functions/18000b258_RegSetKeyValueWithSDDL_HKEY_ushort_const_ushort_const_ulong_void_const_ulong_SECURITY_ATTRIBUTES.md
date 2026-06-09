# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18000b258`
- end: `0x18000b310`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009520`
- `0x180019bc0`

## callees

- `0x18000b258`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b2a8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b2a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b2f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b2e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b2e1`

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
0x18000b258  mov     r11, rsp
0x18000b25b  mov     [r11+8], rbx
0x18000b25f  mov     [r11+18h], rbp
0x18000b263  push    rsi
0x18000b264  push    rdi
0x18000b265  push    r14
0x18000b267  sub     rsp, 50h
0x18000b26b  xor     r14d, r14d
0x18000b26e  mov     esi, r9d
0x18000b271  mov     [r11+10h], r14
0x18000b275  mov     rbp, r8
0x18000b278  mov     rbx, rcx
0x18000b27b  test    rdx, rdx
0x18000b27e  jz      short loc_18000B2BB
0x18000b280  cmp     [rdx], r14w
0x18000b284  jz      short loc_18000B2BB
0x18000b286  mov     [r11-28h], r14
0x18000b28a  lea     rax, [r11+10h]
0x18000b28e  mov     [r11-30h], rax
0x18000b292  xor     r9d, r9d; lpClass
0x18000b295  mov     [r11-38h], r14
0x18000b299  xor     r8d, r8d; Reserved
0x18000b29c  mov     [rsp+68h+samDesired], 2; samDesired
0x18000b2a4  mov     [r11-48h], r14d
0x18000b2a8  call    cs:__imp_RegCreateKeyExW
0x18000b2ae  mov     edi, eax
0x18000b2b0  test    eax, eax
0x18000b2b2  jnz     short loc_18000B2F9
0x18000b2b4  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b2b9  jmp     short loc_18000B2C0
0x18000b2bb  mov     [rsp+68h+hKey], rbx
0x18000b2c0  mov     eax, [rsp+68h+cbData]
0x18000b2c7  mov     r9d, esi; dwType
0x18000b2ca  mov     [rsp+68h+samDesired], eax; cbData
0x18000b2ce  xor     r8d, r8d; Reserved
0x18000b2d1  mov     rax, [rsp+68h+arg_20]
0x18000b2d9  mov     rdx, rbp; lpValueName
0x18000b2dc  mov     [rsp+68h+lpData], rax; lpData
0x18000b2e1  call    cs:__imp_RegSetValueExW
0x18000b2e7  mov     rcx, [rsp+68h+hKey]; hKey
0x18000b2ec  mov     edi, eax
0x18000b2ee  cmp     rcx, rbx
0x18000b2f1  jz      short loc_18000B2F9
0x18000b2f3  call    cs:__imp_RegCloseKey
0x18000b2f9  lea     r11, [rsp+68h+var_18]
0x18000b2fe  mov     eax, edi
0x18000b300  mov     rbx, [r11+20h]
0x18000b304  mov     rbp, [r11+30h]
0x18000b308  mov     rsp, r11
0x18000b30b  pop     r14
0x18000b30d  pop     rdi
0x18000b30e  pop     rsi
0x18000b30f  retn
```
