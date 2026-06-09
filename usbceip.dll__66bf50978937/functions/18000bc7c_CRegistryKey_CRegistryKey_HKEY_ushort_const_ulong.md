# CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)

- ea: `0x18000bc7c`
- end: `0x18000bcc7`
- name: `??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z`
- size: `75`
- prototype: `CRegistryKey *__fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *)`
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005e94`
- `0x180006430`
- `0x1800064b0`
- `0x1800066a8`
- `0x180007754`
- `0x1800078e0`
- `0x180008b6c`
- `0x180008bf0`
- `0x180008f48`
- `0x1800090d4`
- `0x180009424`
- `0x180009748`
- `0x180009c50`
- `0x180009d50`
- `0x180009e50`

## callees

- `0x1800040cc`
- `0x180008020`
- `0x18000bc7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bca7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bca7`

## pseudocode

```c
CRegistryKey *__fastcall CRegistryKey::CRegistryKey(PHKEY phkResult, HKEY a2, const unsigned __int16 *a3)
{
  REGSAM v4; // r9d
  LPCWSTR v5; // r10
  HKEY v6; // r11
  unsigned int v7; // eax

  std::vector<_bstr_t>::vector<_bstr_t>(phkResult + 1);
  v7 = RegOpenKeyExW(v6, v5, 0, v4, phkResult);
  if ( v7 )
    CException::ThrowException(v7, 0, 0);
  return (CRegistryKey *)phkResult;
}

```

## disassembly

```asm
0x18000bc7c  mov     [rsp+arg_0], rcx
0x18000bc81  push    rbx
0x18000bc82  sub     rsp, 30h
0x18000bc86  mov     r10, r8
0x18000bc89  mov     r11, rdx
0x18000bc8c  mov     rbx, rcx
0x18000bc8f  add     rcx, 8
0x18000bc93  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000bc98  nop
0x18000bc99  mov     [rsp+38h+phkResult], rbx; phkResult
0x18000bc9e  xor     r8d, r8d; ulOptions
0x18000bca1  mov     rdx, r10; lpSubKey
0x18000bca4  mov     rcx, r11; hKey
0x18000bca7  call    cs:__imp_RegOpenKeyExW
0x18000bcad  test    eax, eax
0x18000bcaf  jz      short loc_18000BCBE
0x18000bcb1  xor     r8d, r8d
0x18000bcb4  xor     edx, edx
0x18000bcb6  mov     ecx, eax
0x18000bcb8  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000bcbe  mov     rax, rbx
0x18000bcc1  add     rsp, 30h
0x18000bcc5  pop     rbx
0x18000bcc6  retn
```
