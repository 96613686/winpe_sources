# CXMLPropStoreSaxParser::_AddEntryForContent(HKEY__ *,ushort const *)

- ea: `0x18002fe7c`
- end: `0x18002ff09`
- name: `?_AddEntryForContent@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `141`
- prototype: `__int64 __fastcall(CXMLPropStoreSaxParser *__hidden this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001142c`

## callees

- `0x180012550`
- `0x18002d334`
- `0x18002fe7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fee9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002febd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002febd`

## pseudocode

```c
__int64 __fastcall CXMLPropStoreSaxParser::_AddEntryForContent(
        CXMLPropStoreSaxParser *this,
        HKEY hKey,
        LPCWSTR lpSubKey)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  HKEY hKeya; // [rsp+30h] [rbp-18h] BYREF

  v4 = 0;
  hKeya = 0;
  if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya) )
    v4 = CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7f34dda4c3a21f63818194a7724a5899_>(this, hKeya);
  v5 = hKeya;
  hKeya = 0;
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x18002fe7c  mov     r11, rsp
0x18002fe7f  mov     [r11+20h], rbx
0x18002fe83  push    rdi
0x18002fe84  sub     rsp, 40h
0x18002fe88  mov     rax, cs:__security_cookie
0x18002fe8f  xor     rax, rsp
0x18002fe92  mov     [rsp+48h+var_10], rax
0x18002fe97  mov     rdi, rcx
0x18002fe9a  mov     r10, r8
0x18002fe9d  lea     rcx, [r11-18h]
0x18002fea1  mov     rax, rdx
0x18002fea4  mov     [r11-28h], rcx
0x18002fea8  xor     ebx, ebx
0x18002feaa  mov     rcx, rax; hKey
0x18002fead  mov     [r11-18h], rbx
0x18002feb1  mov     r9d, 20019h; samDesired
0x18002feb7  xor     r8d, r8d; ulOptions
0x18002feba  mov     rdx, r10; lpSubKey
0x18002febd  call    cs:__imp_RegOpenKeyExW
0x18002fec3  test    eax, eax
0x18002fec5  jnz     short loc_18002FED6
0x18002fec7  mov     rdx, [rsp+48h+hKey]; HKEY
0x18002fecc  mov     rcx, rdi; this
0x18002fecf  call    ??$_ExecuteForAllSubkeys@V_lambda_7f34dda4c3a21f63818194a7724a5899_@@@CXMLPropStoreSaxParser@@AEAAJPEAUHKEY__@@AEBV_lambda_7f34dda4c3a21f63818194a7724a5899_@@@Z; CXMLPropStoreSaxParser::_ExecuteForAllSubkeys<_lambda_7f34dda4c3a21f63818194a7724a5899_>(HKEY__ *,_lambda_7f34dda4c3a21f63818194a7724a5899_ const &)
0x18002fed4  mov     ebx, eax
0x18002fed6  mov     rcx, [rsp+48h+hKey]; hKey
0x18002fedb  mov     [rsp+48h+hKey], 0
0x18002fee4  test    rcx, rcx
0x18002fee7  jz      short loc_18002FEEF
0x18002fee9  call    cs:__imp_RegCloseKey
0x18002feef  mov     eax, ebx
0x18002fef1  mov     rcx, [rsp+48h+var_10]
0x18002fef6  xor     rcx, rsp; StackCookie
0x18002fef9  call    __security_check_cookie
0x18002fefe  mov     rbx, [rsp+48h+arg_18]
0x18002ff03  add     rsp, 40h
0x18002ff07  pop     rdi
0x18002ff08  retn
```
