# CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800048c0`
- end: `0x18000492f`
- name: `?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z`
- size: `111`
- prototype: `unsigned int __fastcall(PHKEY phkResult, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800048c0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800048e8`
- `ADVAPI32!RegCloseKey` at `0x1800048e8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000490d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000490d`

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
0x1800048c0  mov     [rsp+arg_0], rbx
0x1800048c5  mov     [rsp+arg_8], rbp
0x1800048ca  mov     [rsp+arg_10], rsi
0x1800048cf  push    rdi
0x1800048d0  sub     rsp, 30h
0x1800048d4  mov     rbx, rcx
0x1800048d7  mov     edi, r9d
0x1800048da  mov     rcx, [rcx]; hKey
0x1800048dd  mov     rsi, r8
0x1800048e0  mov     rbp, rdx
0x1800048e3  test    rcx, rcx
0x1800048e6  jz      short loc_1800048F8
0x1800048e8  call    cs:__imp_RegCloseKey
0x1800048ef  nop     dword ptr [rax+rax+00h]
0x1800048f4  and     qword ptr [rbx], 0
0x1800048f8  bts     edi, 8
0x1800048fc  mov     [rsp+38h+phkResult], rbx; phkResult
0x180004901  mov     r9d, edi; samDesired
0x180004904  xor     r8d, r8d; ulOptions
0x180004907  mov     rdx, rsi; lpSubKey
0x18000490a  mov     rcx, rbp; hKey
0x18000490d  call    cs:__imp_RegOpenKeyExW
0x180004914  nop     dword ptr [rax+rax+00h]
0x180004919  mov     rbx, [rsp+38h+arg_0]
0x18000491e  mov     rbp, [rsp+38h+arg_8]
0x180004923  mov     rsi, [rsp+38h+arg_10]
0x180004928  add     rsp, 30h
0x18000492c  pop     rdi
0x18000492d  retn
```
