# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180043ae0`
- end: `0x180043b88`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `168`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007622c`

## callees

- `0x180043ae0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180043b64`
- `ADVAPI32!RegSetValueExW` at `0x180043b64`
- `ADVAPI32!RegCloseKey` at `0x180043b7a`
- `ADVAPI32!RegCloseKey` at `0x180043b7a`
- `ADVAPI32!RegCreateKeyExW` at `0x180043b30`
- `ADVAPI32!RegCreateKeyExW` at `0x180043b30`

## string_xrefs

- `0x180043afc`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180043b4d`: `LastUnsafeExtensionReportTime`

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
0x180043ae0  mov     r11, rsp
0x180043ae3  mov     [r11+18h], r8
0x180043ae7  push    rbx
0x180043ae8  sub     rsp, 50h
0x180043aec  mov     qword ptr [r11-18h], 0
0x180043af4  lea     rax, [r11+18h]
0x180043af8  mov     [r11-20h], rax
0x180043afc  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Internet Explorer"...
0x180043b03  mov     qword ptr [r11-28h], 0
0x180043b0b  xor     r9d, r9d; lpClass
0x180043b0e  mov     [rsp+58h+samDesired], 2; samDesired
0x180043b16  xor     r8d, r8d; Reserved
0x180043b19  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180043b20  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180043b28  mov     qword ptr [r11+18h], 0
0x180043b30  call    cs:__imp_RegCreateKeyExW
0x180043b36  mov     ebx, eax
0x180043b38  test    eax, eax
0x180043b3a  jnz     short loc_180043B80
0x180043b3c  mov     rax, [rsp+58h+lpData]
0x180043b44  lea     r9d, [rbx+3]; dwType
0x180043b48  mov     rcx, [rsp+58h+hKey]; hKey
0x180043b4d  lea     rdx, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x180043b54  mov     [rsp+58h+samDesired], 8; cbData
0x180043b5c  xor     r8d, r8d; Reserved
0x180043b5f  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180043b64  call    cs:__imp_RegSetValueExW
0x180043b6a  mov     rcx, [rsp+58h+hKey]; hKey
0x180043b6f  mov     ebx, eax
0x180043b71  cmp     rcx, 0FFFFFFFF80000001h
0x180043b78  jz      short loc_180043B80
0x180043b7a  call    cs:__imp_RegCloseKey
0x180043b80  mov     eax, ebx
0x180043b82  add     rsp, 50h
0x180043b86  pop     rbx
0x180043b87  retn
```
