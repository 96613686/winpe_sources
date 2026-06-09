# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000e234`
- end: `0x18000e285`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016d08`
- `0x180019be8`
- `0x18001a0e0`
- `0x1800216b0`
- `0x18002177c`
- `0x18002bb04`
- `0x18002bbb8`
- `0x18002bc6c`
- `0x18002bd2c`
- `0x18002be4c`
- `0x18002bed4`
- `0x18002cab4`

## callees

- `0x18000e234`
- `0x1800173a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e25f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e25f`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x18000e234  push    rbx
0x18000e236  sub     rsp, 40h
0x18000e23a  mov     rbx, rcx
0x18000e23d  mov     [rsp+48h+var_18], 0
0x18000e246  mov     rax, r8
0x18000e249  lea     rcx, [rsp+48h+var_18]
0x18000e24e  mov     r10, rdx
0x18000e251  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000e256  mov     rcx, r10; hKey
0x18000e259  xor     r8d, r8d; ulOptions
0x18000e25c  mov     rdx, rax; lpSubKey
0x18000e25f  call    cs:__imp_RegOpenKeyExW
0x18000e265  mov     edx, eax
0x18000e267  test    eax, eax
0x18000e269  jnz     short loc_18000E27D
0x18000e26b  mov     rcx, rbx; this
0x18000e26e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e273  mov     edx, eax
0x18000e275  mov     rax, [rsp+48h+var_18]
0x18000e27a  mov     [rbx], rax
0x18000e27d  mov     eax, edx
0x18000e27f  add     rsp, 40h
0x18000e283  pop     rbx
0x18000e284  retn
```
