# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800303dc`
- end: `0x18003042d`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180030698`
- `0x180030acc`

## callees

- `0x18002fe54`
- `0x1800303dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030407`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030407`

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
0x1800303dc  push    rbx
0x1800303de  sub     rsp, 40h
0x1800303e2  mov     rbx, rcx
0x1800303e5  mov     [rsp+48h+var_18], 0
0x1800303ee  mov     rax, r8
0x1800303f1  lea     rcx, [rsp+48h+var_18]
0x1800303f6  mov     r10, rdx
0x1800303f9  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800303fe  mov     rcx, r10; hKey
0x180030401  xor     r8d, r8d; ulOptions
0x180030404  mov     rdx, rax; lpSubKey
0x180030407  call    cs:__imp_RegOpenKeyExW
0x18003040d  mov     edx, eax
0x18003040f  test    eax, eax
0x180030411  jnz     short loc_180030425
0x180030413  mov     rcx, rbx; this
0x180030416  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003041b  mov     edx, eax
0x18003041d  mov     rax, [rsp+48h+var_18]
0x180030422  mov     [rbx], rax
0x180030425  mov     eax, edx
0x180030427  add     rsp, 40h
0x18003042b  pop     rbx
0x18003042c  retn
```
