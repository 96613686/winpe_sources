# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000b618`
- end: `0x18000b669`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800090b0`
- `0x18000ba18`
- `0x18000bf80`

## callees

- `0x1800096c4`
- `0x18000b618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b643`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x18000b618  push    rbx
0x18000b61a  sub     rsp, 40h
0x18000b61e  mov     rbx, rcx
0x18000b621  mov     [rsp+48h+var_18], 0
0x18000b62a  mov     rax, r8
0x18000b62d  lea     rcx, [rsp+48h+var_18]
0x18000b632  mov     r10, rdx
0x18000b635  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000b63a  mov     rcx, r10; hKey
0x18000b63d  xor     r8d, r8d; ulOptions
0x18000b640  mov     rdx, rax; lpSubKey
0x18000b643  call    cs:__imp_RegOpenKeyExW
0x18000b649  mov     edx, eax
0x18000b64b  test    eax, eax
0x18000b64d  jnz     short loc_18000B661
0x18000b64f  mov     rcx, rbx; this
0x18000b652  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b657  mov     edx, eax
0x18000b659  mov     rax, [rsp+48h+var_18]
0x18000b65e  mov     [rbx], rax
0x18000b661  mov     eax, edx
0x18000b663  add     rsp, 40h
0x18000b667  pop     rbx
0x18000b668  retn
```
