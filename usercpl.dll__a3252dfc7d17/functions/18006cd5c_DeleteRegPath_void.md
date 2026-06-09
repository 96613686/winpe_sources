# DeleteRegPath(void)

- ea: `0x18006cd5c`
- end: `0x18006ce2a`
- name: `?DeleteRegPath@@YAKXZ`
- size: `206`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cbe0`

## callees

- `0x18006a608`
- `0x18006cd5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006cd8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ce1c`
- `ADVAPI32!RegDeleteValueW` at `0x18006cdb7`
- `ADVAPI32!RegDeleteValueW` at `0x18006cdb7`

## string_xrefs

- `0x18006cdc8`: `RegDeleteValue`
- `0x18006cdf3`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x18006cdb0`: `ThirdPartyEncryptionProviderPath`
- `0x18006cd9d`: `RegOpenKeyEx(SYSTEM\CurrentControlSet\Control\EAS)`
- `0x18006cddb`: `RegDeleteValue(ThirdPartyEncryptionProviderPath)`

## pseudocode

```c
__int64 DeleteRegPath(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // ecx
  const wchar_t *v2; // rdx
  int v3; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\EAS", 0, 3u, &hKey);
  if ( v0 )
  {
    v1 = 1;
    v2 = L"RegOpenKeyEx(SYSTEM\\CurrentControlSet\\Control\\EAS)";
    v3 = 158;
  }
  else
  {
    v0 = RegDeleteValueW(hKey, L"ThirdPartyEncryptionProviderPath");
    if ( v0 )
    {
      v1 = 1;
      v2 = L"RegDeleteValue";
      v3 = 164;
    }
    else
    {
      v1 = 4;
      v2 = L"RegDeleteValue(ThirdPartyEncryptionProviderPath)";
      v3 = 166;
    }
  }
  LODWORD(phkResult) = v3;
  DbgPrintfW(
    v1,
    L"(0x%08x) %ws:%u : %ws:%ws\n",
    v0,
    L"onecore\\ds\\security\\eas\\policyengine\\utilregs.cxx",
    phkResult,
    v2,
    &Class);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18006cd5c  push    rbx
0x18006cd5e  sub     rsp, 40h
0x18006cd62  lea     rax, [rsp+48h+hKey]
0x18006cd67  mov     [rsp+48h+hKey], 0
0x18006cd70  mov     r9d, 3; samDesired
0x18006cd76  mov     [rsp+48h+phkResult], rax; phkResult
0x18006cd7b  xor     r8d, r8d; ulOptions
0x18006cd7e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x18006cd85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006cd8c  call    cs:__imp_RegOpenKeyExW
0x18006cd92  mov     ebx, eax
0x18006cd94  test    eax, eax
0x18006cd96  jz      short loc_18006CDAB
0x18006cd98  mov     ecx, 1
0x18006cd9d  lea     rdx, aRegopenkeyexSy; "RegOpenKeyEx(SYSTEM\\CurrentControlSet"...
0x18006cda4  mov     eax, 9Eh
0x18006cda9  jmp     short loc_18006CDE7
0x18006cdab  mov     rcx, [rsp+48h+hKey]; hKey
0x18006cdb0  lea     rdx, aThirdpartyencr; "ThirdPartyEncryptionProviderPath"
0x18006cdb7  call    cs:__imp_RegDeleteValueW
0x18006cdbd  mov     ebx, eax
0x18006cdbf  test    eax, eax
0x18006cdc1  jz      short loc_18006CDD6
0x18006cdc3  mov     ecx, 1
0x18006cdc8  lea     rdx, aRegdeletevalue_0; "RegDeleteValue"
0x18006cdcf  mov     eax, 0A4h
0x18006cdd4  jmp     short loc_18006CDE7
0x18006cdd6  mov     ecx, 4; unsigned int
0x18006cddb  lea     rdx, aRegdeletevalue; "RegDeleteValue(ThirdPartyEncryptionProv"...
0x18006cde2  mov     eax, 0A6h
0x18006cde7  lea     r8, Class
0x18006cdee  mov     [rsp+48h+var_18], r8
0x18006cdf3  lea     r9, aOnecoreDsSecur_4; "onecore\\ds\\security\\eas\\policyengin"...
0x18006cdfa  mov     [rsp+48h+var_20], rdx
0x18006cdff  mov     r8d, ebx
0x18006ce02  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18006ce09  mov     dword ptr [rsp+48h+phkResult], eax
0x18006ce0d  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x18006ce12  mov     rcx, [rsp+48h+hKey]; hKey
0x18006ce17  test    rcx, rcx
0x18006ce1a  jz      short loc_18006CE22
0x18006ce1c  call    cs:__imp_RegCloseKey
0x18006ce22  mov     eax, ebx
0x18006ce24  add     rsp, 40h
0x18006ce28  pop     rbx
0x18006ce29  retn
```
