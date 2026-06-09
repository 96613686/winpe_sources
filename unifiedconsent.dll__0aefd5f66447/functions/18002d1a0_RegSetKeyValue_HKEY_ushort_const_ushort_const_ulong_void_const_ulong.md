# _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x18002d1a0`
- end: `0x18002d262`
- name: `?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `194`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180029504`
- `0x18002aae0`
- `0x18002be40`

## callees

- `0x18002d1a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d237`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002d237`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d1f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d1f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d250`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d250`

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
0x18002d1a0  mov     r11, rsp
0x18002d1a3  mov     [r11+8], rcx
0x18002d1a7  push    rbp
0x18002d1a8  push    rsi
0x18002d1a9  push    rdi
0x18002d1aa  push    r14
0x18002d1ac  sub     rsp, 58h
0x18002d1b0  xor     r14d, r14d
0x18002d1b3  mov     esi, r9d
0x18002d1b6  mov     [r11+8], r14
0x18002d1ba  mov     rbp, r8
0x18002d1bd  test    rdx, rdx
0x18002d1c0  jz      short loc_18002D207
0x18002d1c2  cmp     [rdx], r14w
0x18002d1c6  jz      short loc_18002D207
0x18002d1c8  mov     [r11-38h], r14
0x18002d1cc  lea     rax, [r11+8]
0x18002d1d0  mov     [r11-40h], rax
0x18002d1d4  xor     r9d, r9d; lpClass
0x18002d1d7  mov     [r11-48h], r14
0x18002d1db  xor     r8d, r8d; Reserved
0x18002d1de  mov     [rsp+78h+samDesired], 2; samDesired
0x18002d1e6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002d1ed  mov     [r11-58h], r14d
0x18002d1f1  call    cs:__imp_RegCreateKeyExW
0x18002d1f7  mov     edi, eax
0x18002d1f9  test    eax, eax
0x18002d1fb  jnz     short loc_18002D256
0x18002d1fd  mov     rcx, [rsp+78h+hKey]
0x18002d205  jmp     short loc_18002D216
0x18002d207  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002d20e  mov     [rsp+78h+hKey], rcx
0x18002d216  mov     eax, [rsp+78h+cbData]
0x18002d21d  mov     r9d, esi; dwType
0x18002d220  mov     [rsp+78h+samDesired], eax; cbData
0x18002d224  xor     r8d, r8d; Reserved
0x18002d227  mov     rax, [rsp+78h+arg_20]
0x18002d22f  mov     rdx, rbp; lpValueName
0x18002d232  mov     [rsp+78h+lpData], rax; lpData
0x18002d237  call    cs:__imp_RegSetValueExW
0x18002d23d  mov     rcx, [rsp+78h+hKey]; hKey
0x18002d245  mov     edi, eax
0x18002d247  cmp     rcx, 0FFFFFFFF80000001h
0x18002d24e  jz      short loc_18002D256
0x18002d250  call    cs:__imp_RegCloseKey
0x18002d256  mov     eax, edi
0x18002d258  add     rsp, 58h
0x18002d25c  pop     r14
0x18002d25e  pop     rdi
0x18002d25f  pop     rsi
0x18002d260  pop     rbp
0x18002d261  retn
```
