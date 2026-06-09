# _RegSetKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)

- ea: `0x180007594`
- end: `0x180007647`
- name: `?_RegSetKeyValue@@YAKPEAUHKEY__@@PEBG1KPEBXK@Z`
- size: `179`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006730`

## callees

- `0x180007594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800075dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800075dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007634`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007634`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000761e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000761e`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  unsigned int v5; // edi
  HKEY v6; // rcx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v5 = RegCreateKeyExW(HKEY_USERS, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v5 )
      return v5;
    v6 = hKey;
  }
  else
  {
    v6 = HKEY_USERS;
    hKey = HKEY_USERS;
  }
  v5 = RegSetValueExW(v6, L"DelayLockInterval", 0, 4u, lpData, 4u);
  if ( hKey != HKEY_USERS )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180007594  mov     r11, rsp
0x180007597  mov     [r11+8], rsi
0x18000759b  mov     [r11+18h], r8
0x18000759f  push    rdi
0x1800075a0  sub     rsp, 50h
0x1800075a4  xor     esi, esi
0x1800075a6  mov     [r11+18h], rsi
0x1800075aa  test    rdx, rdx
0x1800075ad  jz      short loc_1800075F0
0x1800075af  cmp     [rdx], si
0x1800075b2  jz      short loc_1800075F0
0x1800075b4  mov     [r11-18h], rsi
0x1800075b8  lea     rax, [r11+18h]
0x1800075bc  mov     [r11-20h], rax
0x1800075c0  xor     r9d, r9d; lpClass
0x1800075c3  mov     [r11-28h], rsi
0x1800075c7  xor     r8d, r8d; Reserved
0x1800075ca  mov     [rsp+58h+samDesired], 2; samDesired
0x1800075d2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800075d9  mov     [rsp+58h+dwOptions], esi; dwOptions
0x1800075dd  call    cs:__imp_RegCreateKeyExW
0x1800075e3  mov     edi, eax
0x1800075e5  test    eax, eax
0x1800075e7  jnz     short loc_18000763A
0x1800075e9  mov     rcx, [rsp+58h+hKey]
0x1800075ee  jmp     short loc_1800075FC
0x1800075f0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800075f7  mov     [rsp+58h+hKey], rcx
0x1800075fc  mov     rax, [rsp+58h+lpData]
0x180007604  lea     rdx, ValueName; "DelayLockInterval"
0x18000760b  mov     r9d, 4; dwType
0x180007611  xor     r8d, r8d; Reserved
0x180007614  mov     [rsp+58h+samDesired], r9d; cbData
0x180007619  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000761e  call    cs:__imp_RegSetValueExW
0x180007624  mov     rcx, [rsp+58h+hKey]; hKey
0x180007629  mov     edi, eax
0x18000762b  cmp     rcx, 0FFFFFFFF80000003h
0x180007632  jz      short loc_18000763A
0x180007634  call    cs:__imp_RegCloseKey
0x18000763a  mov     rsi, [rsp+58h+arg_0]
0x18000763f  mov     eax, edi
0x180007641  add     rsp, 50h
0x180007645  pop     rdi
0x180007646  retn
```
