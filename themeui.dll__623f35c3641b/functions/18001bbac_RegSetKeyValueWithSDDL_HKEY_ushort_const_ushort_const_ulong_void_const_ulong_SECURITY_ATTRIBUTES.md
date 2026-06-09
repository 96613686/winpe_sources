# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18001bbac`
- end: `0x18001bc6c`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `192`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033524`
- `0x18004cc7c`

## callees

- `0x18001bbac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bc56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001bc56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bc0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bc0c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bbfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001bbfa`

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
0x18001bbac  mov     [rsp+arg_0], rbx
0x18001bbb1  mov     [rsp+arg_10], rbp
0x18001bbb6  push    rsi
0x18001bbb7  push    rdi
0x18001bbb8  push    r14
0x18001bbba  sub     rsp, 50h
0x18001bbbe  xor     r14d, r14d
0x18001bbc1  mov     esi, r9d
0x18001bbc4  mov     [rsp+68h+hKey], r14
0x18001bbc9  mov     rbp, r8
0x18001bbcc  mov     rbx, rcx
0x18001bbcf  test    rdx, rdx
0x18001bbd2  jnz     short loc_18001BC29
0x18001bbd4  mov     [rsp+68h+hKey], rbx
0x18001bbd9  mov     eax, [rsp+68h+arg_28]
0x18001bbe0  mov     r9d, esi; dwType
0x18001bbe3  mov     [rsp+68h+cbData], eax; cbData
0x18001bbe7  xor     r8d, r8d; Reserved
0x18001bbea  mov     rax, [rsp+68h+arg_20]
0x18001bbf2  mov     rdx, rbp; lpValueName
0x18001bbf5  mov     [rsp+68h+lpData], rax; lpData
0x18001bbfa  call    cs:__imp_RegSetValueExW
0x18001bc00  mov     rcx, [rsp+68h+hKey]; hKey
0x18001bc05  mov     edi, eax
0x18001bc07  cmp     rcx, rbx
0x18001bc0a  jz      short loc_18001BC12
0x18001bc0c  call    cs:__imp_RegCloseKey
0x18001bc12  lea     r11, [rsp+68h+var_18]
0x18001bc17  mov     eax, edi
0x18001bc19  mov     rbx, [r11+20h]
0x18001bc1d  mov     rbp, [r11+30h]
0x18001bc21  mov     rsp, r11
0x18001bc24  pop     r14
0x18001bc26  pop     rdi
0x18001bc27  pop     rsi
0x18001bc28  retn
0x18001bc29  cmp     [rdx], r14w
0x18001bc2d  jz      short loc_18001BBD4
0x18001bc2f  mov     [rsp+68h+lpdwDisposition], r14; lpdwDisposition
0x18001bc34  lea     rax, [rsp+68h+hKey]
0x18001bc39  mov     [rsp+68h+phkResult], rax; phkResult
0x18001bc3e  xor     r9d, r9d; lpClass
0x18001bc41  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001bc46  xor     r8d, r8d; Reserved
0x18001bc49  mov     [rsp+68h+cbData], 2; samDesired
0x18001bc51  mov     dword ptr [rsp+68h+lpData], r14d; dwOptions
0x18001bc56  call    cs:__imp_RegCreateKeyExW
0x18001bc5c  mov     edi, eax
0x18001bc5e  test    eax, eax
0x18001bc60  jnz     short loc_18001BC12
0x18001bc62  mov     rcx, [rsp+68h+hKey]
0x18001bc67  jmp     loc_18001BBD9
```
