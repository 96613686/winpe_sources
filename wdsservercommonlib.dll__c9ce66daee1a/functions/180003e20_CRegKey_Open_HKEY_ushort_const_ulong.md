# CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180003e20`
- end: `0x180003e8f`
- name: `?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z`
- size: `111`
- prototype: `unsigned int __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003e20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003e48`
- `ADVAPI32!RegCloseKey` at `0x180003e48`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e6d`
- `ADVAPI32!RegOpenKeyExW` at `0x180003e6d`

## pseudocode

```c
LSTATUS __fastcall CRegKey::Open(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, int a4)
{
  HKEY v6; // rcx

  v6 = *phkResult;
  if ( v6 )
  {
    RegCloseKey(v6);
    *phkResult = 0;
  }
  return RegOpenKeyExW(hKey, lpSubKey, 0, a4 | 0x100, phkResult);
}

```

## disassembly

```asm
0x180003e20  mov     [rsp+arg_0], rbx
0x180003e25  mov     [rsp+arg_8], rbp
0x180003e2a  mov     [rsp+arg_10], rsi
0x180003e2f  push    rdi
0x180003e30  sub     rsp, 30h
0x180003e34  mov     rbx, rcx
0x180003e37  mov     edi, r9d
0x180003e3a  mov     rcx, [rcx]; hKey
0x180003e3d  mov     rsi, r8
0x180003e40  mov     rbp, rdx
0x180003e43  test    rcx, rcx
0x180003e46  jz      short loc_180003E58
0x180003e48  call    cs:__imp_RegCloseKey
0x180003e4f  nop     dword ptr [rax+rax+00h]
0x180003e54  and     qword ptr [rbx], 0
0x180003e58  bts     edi, 8
0x180003e5c  mov     [rsp+38h+phkResult], rbx; phkResult
0x180003e61  mov     r9d, edi; samDesired
0x180003e64  xor     r8d, r8d; ulOptions
0x180003e67  mov     rdx, rsi; lpSubKey
0x180003e6a  mov     rcx, rbp; hKey
0x180003e6d  call    cs:__imp_RegOpenKeyExW
0x180003e74  nop     dword ptr [rax+rax+00h]
0x180003e79  mov     rbx, [rsp+38h+arg_0]
0x180003e7e  mov     rbp, [rsp+38h+arg_8]
0x180003e83  mov     rsi, [rsp+38h+arg_10]
0x180003e88  add     rsp, 30h
0x180003e8c  pop     rdi
0x180003e8d  retn
```
