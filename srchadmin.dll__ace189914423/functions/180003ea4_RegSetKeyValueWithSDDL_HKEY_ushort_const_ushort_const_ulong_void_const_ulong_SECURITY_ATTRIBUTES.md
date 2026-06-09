# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180003ea4`
- end: `0x180003f49`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `165`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eed0`

## callees

- `0x180003ea4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003f25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ef4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003ef4`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  unsigned int v5; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, L"ReindexedProfile", 0, 4u, lpData, 4u);
    if ( hKey != HKEY_CURRENT_USER )
      RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180003ea4  mov     r11, rsp
0x180003ea7  mov     [r11+18h], r8
0x180003eab  push    rbx
0x180003eac  sub     rsp, 50h
0x180003eb0  mov     qword ptr [r11-18h], 0
0x180003eb8  lea     rax, [r11+18h]
0x180003ebc  mov     [r11-20h], rax
0x180003ec0  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180003ec7  mov     qword ptr [r11-28h], 0
0x180003ecf  xor     r9d, r9d; lpClass
0x180003ed2  mov     [rsp+58h+samDesired], 2; samDesired
0x180003eda  xor     r8d, r8d; Reserved
0x180003edd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180003ee4  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180003eec  mov     qword ptr [r11+18h], 0
0x180003ef4  call    cs:__imp_RegCreateKeyExW
0x180003efa  mov     ebx, eax
0x180003efc  test    eax, eax
0x180003efe  jnz     short loc_180003F41
0x180003f00  mov     rcx, [rsp+58h+hKey]; hKey
0x180003f05  lea     r9d, [rax+4]; dwType
0x180003f09  mov     rax, [rsp+58h+lpData]
0x180003f11  lea     rdx, aReindexedprofi; "ReindexedProfile"
0x180003f18  mov     [rsp+58h+samDesired], r9d; cbData
0x180003f1d  xor     r8d, r8d; Reserved
0x180003f20  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180003f25  call    cs:__imp_RegSetValueExW
0x180003f2b  mov     rcx, [rsp+58h+hKey]; hKey
0x180003f30  mov     ebx, eax
0x180003f32  cmp     rcx, 0FFFFFFFF80000001h
0x180003f39  jz      short loc_180003F41
0x180003f3b  call    cs:__imp_RegCloseKey
0x180003f41  mov     eax, ebx
0x180003f43  add     rsp, 50h
0x180003f47  pop     rbx
0x180003f48  retn
```
