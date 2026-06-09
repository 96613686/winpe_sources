# ReadDWordValue(ushort const *,ushort const *,ulong *)

- ea: `0x180041ed4`
- end: `0x180041fae`
- name: `?ReadDWordValue@@YAKPEBG0PEAK@Z`
- size: `218`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180041d5c`
- `0x1800426bc`

## callees

- `0x180041ed4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041f95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041f95`

## pseudocode

```c
__int64 __fastcall ReadDWordValue(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int *a3)
{
  unsigned int ValueW; // ebx
  unsigned int pvData; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD pdwType; // [rsp+88h] [rbp+38h] BYREF

  *a3 = 0;
  pdwType = 0;
  pcbData = 0;
  hKey = 0;
  pvData = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
  if ( !ValueW )
  {
    pdwType = 4;
    pcbData = 4;
    ValueW = RegGetValueW(hKey, 0, lpValue, 0x18u, &pdwType, &pvData, &pcbData);
    if ( !ValueW )
      *a3 = pvData;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return ValueW;
}

```

## disassembly

```asm
0x180041ed4  mov     [rsp-18h+arg_0], rbx
0x180041ed9  push    rbp
0x180041eda  push    rsi
0x180041edb  push    rdi
0x180041edc  mov     rbp, rsp
0x180041edf  sub     rsp, 50h
0x180041ee3  mov     rsi, rdx
0x180041ee6  mov     dword ptr [r8], 0
0x180041eed  mov     rdx, rcx; lpSubKey
0x180041ef0  mov     [rbp+pdwType], 0
0x180041ef7  mov     rdi, r8
0x180041efa  mov     [rbp+arg_10], 0
0x180041f01  lea     rax, [rbp+hKey]
0x180041f05  mov     [rbp+hKey], 0
0x180041f0d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041f14  mov     [rbp+var_10], 0
0x180041f1b  mov     r9d, 20119h; samDesired
0x180041f21  mov     [rsp+50h+phkResult], rax; phkResult
0x180041f26  xor     r8d, r8d; ulOptions
0x180041f29  call    cs:__imp_RegOpenKeyExW
0x180041f30  nop     dword ptr [rax+rax+00h]
0x180041f35  mov     ebx, eax
0x180041f37  test    eax, eax
0x180041f39  jz      short loc_180041F60
0x180041f3b  mov     rcx, [rbp+hKey]; hKey
0x180041f3f  test    rcx, rcx
0x180041f42  jz      short loc_180041F50
0x180041f44  call    cs:__imp_RegCloseKey
0x180041f4b  nop     dword ptr [rax+rax+00h]
0x180041f50  mov     eax, ebx
0x180041f52  mov     rbx, [rsp+50h+arg_0]
0x180041f57  add     rsp, 50h
0x180041f5b  pop     rdi
0x180041f5c  pop     rsi
0x180041f5d  pop     rbp
0x180041f5e  retn
0x180041f60  mov     rcx, [rbp+hKey]; hkey
0x180041f64  mov     eax, 4
0x180041f69  mov     [rbp+pdwType], eax
0x180041f6c  mov     r9d, 18h; dwFlags
0x180041f72  mov     [rbp+arg_10], eax
0x180041f75  mov     r8, rsi; lpValue
0x180041f78  lea     rax, [rbp+arg_10]
0x180041f7c  xor     edx, edx; lpSubKey
0x180041f7e  mov     [rsp+50h+pcbData], rax; pcbData
0x180041f83  lea     rax, [rbp+var_10]
0x180041f87  mov     [rsp+50h+pvData], rax; pvData
0x180041f8c  lea     rax, [rbp+pdwType]
0x180041f90  mov     [rsp+50h+phkResult], rax; pdwType
0x180041f95  call    cs:__imp_RegGetValueW
0x180041f9c  nop     dword ptr [rax+rax+00h]
0x180041fa1  mov     ebx, eax
0x180041fa3  test    eax, eax
0x180041fa5  jnz     short loc_180041F3B
0x180041fa7  mov     eax, [rbp+var_10]
0x180041faa  mov     [rdi], eax
0x180041fac  jmp     short loc_180041F3B
```
