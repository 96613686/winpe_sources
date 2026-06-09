# DeleteRegPath(void)

- ea: `0x140098e64`
- end: `0x140098f32`
- name: `?DeleteRegPath@@YAKXZ`
- size: `206`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140098d9c`

## callees

- `0x140038250`
- `0x140098e64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140098ebf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140098ebf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140098e94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140098e94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140098f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140098f24`

## string_xrefs

- `0x140098ed0`: `RegDeleteValue`
- `0x140098eb8`: `ThirdPartyEncryptionProviderPath`
- `0x140098ea5`: `RegOpenKeyEx(SYSTEM\CurrentControlSet\Control\EAS)`
- `0x140098efb`: `onecore\ds\security\eas\policyengine\utilregs.cxx`
- `0x140098ee3`: `RegDeleteValue(ThirdPartyEncryptionProviderPath)`

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
    &pPassword);
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x140098e64  push    rbx
0x140098e66  sub     rsp, 40h
0x140098e6a  lea     rax, [rsp+48h+hKey]
0x140098e6f  mov     [rsp+48h+hKey], 0
0x140098e78  mov     r9d, 3; samDesired
0x140098e7e  mov     [rsp+48h+phkResult], rax; phkResult
0x140098e83  xor     r8d, r8d; ulOptions
0x140098e86  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\EAS"
0x140098e8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140098e94  call    cs:__imp_RegOpenKeyExW
0x140098e9a  mov     ebx, eax
0x140098e9c  test    eax, eax
0x140098e9e  jz      short loc_140098EB3
0x140098ea0  mov     ecx, 1
0x140098ea5  lea     rdx, aRegopenkeyexSy; "RegOpenKeyEx(SYSTEM\\CurrentControlSet"...
0x140098eac  mov     eax, 9Eh
0x140098eb1  jmp     short loc_140098EEF
0x140098eb3  mov     rcx, [rsp+48h+hKey]; hKey
0x140098eb8  lea     rdx, aThirdpartyencr; "ThirdPartyEncryptionProviderPath"
0x140098ebf  call    cs:__imp_RegDeleteValueW
0x140098ec5  mov     ebx, eax
0x140098ec7  test    eax, eax
0x140098ec9  jz      short loc_140098EDE
0x140098ecb  mov     ecx, 1
0x140098ed0  lea     rdx, aRegdeletevalue_0; "RegDeleteValue"
0x140098ed7  mov     eax, 0A4h
0x140098edc  jmp     short loc_140098EEF
0x140098ede  mov     ecx, 4; unsigned int
0x140098ee3  lea     rdx, aRegdeletevalue; "RegDeleteValue(ThirdPartyEncryptionProv"...
0x140098eea  mov     eax, 0A6h
0x140098eef  lea     r8, pPassword
0x140098ef6  mov     [rsp+48h+var_18], r8
0x140098efb  lea     r9, aOnecoreDsSecur_5; "onecore\\ds\\security\\eas\\policyengin"...
0x140098f02  mov     [rsp+48h+var_20], rdx
0x140098f07  mov     r8d, ebx
0x140098f0a  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x140098f11  mov     dword ptr [rsp+48h+phkResult], eax
0x140098f15  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x140098f1a  mov     rcx, [rsp+48h+hKey]; hKey
0x140098f1f  test    rcx, rcx
0x140098f22  jz      short loc_140098F2A
0x140098f24  call    cs:__imp_RegCloseKey
0x140098f2a  mov     eax, ebx
0x140098f2c  add     rsp, 40h
0x140098f30  pop     rbx
0x140098f31  retn
```
