# CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180013c90`
- end: `0x180013d2b`
- name: `?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `155`
- prototype: `void __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD dwOptions, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002aaf8`
- `0x18002acb0`
- `0x18002ad8c`
- `0x18002b0ec`
- `0x18002b2d8`

## callees

- `0x180013c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013cb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013cb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013d23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013d23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013ce9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013ce9`

## pseudocode

```c
void __fastcall CRegistry::Open(_DWORD *phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD dwOptions)
{
  HKEY v6; // rcx
  LSTATUS Key; // eax

  v6 = *(HKEY *)phkResult;
  if ( v6 )
  {
    RegCloseKey(v6);
    *(_QWORD *)phkResult = 0;
  }
  phkResult[10] = 1010;
  phkResult[8] = 0;
  if ( dwOptions == -32 )
  {
    Key = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, (PHKEY)phkResult);
    phkResult[2] = 2;
  }
  else
  {
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, (LPWSTR)&Class, dwOptions, samDesired, 0, (PHKEY)phkResult, phkResult + 2);
  }
  phkResult[10] = Key;
}

```

## disassembly

```asm
0x180013c90  push    rbx
0x180013c92  push    rbp
0x180013c93  push    rsi
0x180013c94  push    rdi
0x180013c95  push    r14
0x180013c97  push    r15
0x180013c99  sub     rsp, 58h
0x180013c9d  mov     rbx, rcx
0x180013ca0  xor     r15d, r15d
0x180013ca3  mov     rcx, [rcx]; hKey
0x180013ca6  mov     esi, r9d
0x180013ca9  mov     rbp, r8
0x180013cac  mov     r14, rdx
0x180013caf  test    rcx, rcx
0x180013cb2  jz      short loc_180013CBD
0x180013cb4  call    cs:__imp_RegCloseKey
0x180013cba  mov     [rbx], r15
0x180013cbd  mov     eax, [rsp+88h+dwOptions]
0x180013cc4  lea     rdi, [rbx+8]
0x180013cc8  xor     r8d, r8d; Reserved
0x180013ccb  mov     dword ptr [rbx+28h], 3F2h
0x180013cd2  mov     [rbx+20h], r15d
0x180013cd6  mov     rdx, rbp; lpSubKey
0x180013cd9  mov     rcx, r14; hKey
0x180013cdc  cmp     eax, 0FFFFFFE0h
0x180013cdf  jnz     short loc_180013D05
0x180013ce1  mov     r9d, esi; samDesired
0x180013ce4  mov     [rsp+88h+phkResult], rbx; phkResult
0x180013ce9  call    cs:__imp_RegOpenKeyExW
0x180013cef  mov     dword ptr [rdi], 2
0x180013cf5  mov     [rbx+28h], eax
0x180013cf8  add     rsp, 58h
0x180013cfc  pop     r15
0x180013cfe  pop     r14
0x180013d00  pop     rdi
0x180013d01  pop     rsi
0x180013d02  pop     rbp
0x180013d03  pop     rbx
0x180013d04  retn
0x180013d05  mov     [rsp+88h+lpdwDisposition], rdi; lpdwDisposition
0x180013d0a  lea     r9, Class; lpClass
0x180013d11  mov     [rsp+88h+var_50], rbx; phkResult
0x180013d16  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180013d1b  mov     [rsp+88h+samDesired], esi; samDesired
0x180013d1f  mov     dword ptr [rsp+88h+phkResult], eax; dwOptions
0x180013d23  call    cs:__imp_RegCreateKeyExW
0x180013d29  jmp     short loc_180013CF5
```
