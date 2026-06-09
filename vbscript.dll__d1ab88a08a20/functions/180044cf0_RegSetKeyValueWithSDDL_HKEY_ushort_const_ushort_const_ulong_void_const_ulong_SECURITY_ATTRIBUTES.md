# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180044cf0`
- end: `0x180044dab`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `187`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078ed0`

## callees

- `0x180044cf0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180044d7a`
- `ADVAPI32!RegSetValueExW` at `0x180044d7a`
- `ADVAPI32!RegCloseKey` at `0x180044d96`
- `ADVAPI32!RegCloseKey` at `0x180044d96`
- `ADVAPI32!RegCreateKeyExW` at `0x180044d40`
- `ADVAPI32!RegCreateKeyExW` at `0x180044d40`

## string_xrefs

- `0x180044d0c`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180044d63`: `LastUnsafeExtensionReportTime`

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
         L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v5 )
  {
    v5 = RegSetValueExW(hKey, L"LastUnsafeExtensionReportTime", 0, 3u, lpData, 8u);
    if ( hKey != HKEY_CURRENT_USER )
      RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x180044cf0  mov     r11, rsp
0x180044cf3  mov     [r11+18h], r8
0x180044cf7  push    rbx
0x180044cf8  sub     rsp, 50h
0x180044cfc  mov     qword ptr [r11-18h], 0
0x180044d04  lea     rax, [r11+18h]
0x180044d08  mov     [r11-20h], rax
0x180044d0c  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x180044d13  mov     qword ptr [r11-28h], 0
0x180044d1b  xor     r9d, r9d; lpClass
0x180044d1e  mov     [rsp+58h+samDesired], 2; samDesired
0x180044d26  xor     r8d, r8d; Reserved
0x180044d29  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180044d30  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180044d38  mov     qword ptr [r11+18h], 0
0x180044d40  call    cs:__imp_RegCreateKeyExW
0x180044d47  nop     dword ptr [rax+rax+00h]
0x180044d4c  mov     ebx, eax
0x180044d4e  test    eax, eax
0x180044d50  jnz     short loc_180044DA2
0x180044d52  mov     rax, [rsp+58h+lpData]
0x180044d5a  lea     r9d, [rbx+3]; dwType
0x180044d5e  mov     rcx, [rsp+58h+hKey]; hKey
0x180044d63  lea     rdx, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x180044d6a  mov     [rsp+58h+samDesired], 8; cbData
0x180044d72  xor     r8d, r8d; Reserved
0x180044d75  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180044d7a  call    cs:__imp_RegSetValueExW
0x180044d81  nop     dword ptr [rax+rax+00h]
0x180044d86  mov     rcx, [rsp+58h+hKey]; hKey
0x180044d8b  mov     ebx, eax
0x180044d8d  cmp     rcx, 0FFFFFFFF80000001h
0x180044d94  jz      short loc_180044DA2
0x180044d96  call    cs:__imp_RegCloseKey
0x180044d9d  nop     dword ptr [rax+rax+00h]
0x180044da2  mov     eax, ebx
0x180044da4  add     rsp, 50h
0x180044da8  pop     rbx
0x180044da9  retn
```
