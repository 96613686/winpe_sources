# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800070c8`
- end: `0x180007119`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006598`
- `0x1800073c8`
- `0x1800078ec`

## callees

- `0x180006ad4`
- `0x1800070c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800070f3`

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
0x1800070c8  push    rbx
0x1800070ca  sub     rsp, 40h
0x1800070ce  mov     rbx, rcx
0x1800070d1  mov     [rsp+48h+var_18], 0
0x1800070da  mov     rax, r8
0x1800070dd  lea     rcx, [rsp+48h+var_18]
0x1800070e2  mov     r10, rdx
0x1800070e5  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800070ea  mov     rcx, r10; hKey
0x1800070ed  xor     r8d, r8d; ulOptions
0x1800070f0  mov     rdx, rax; lpSubKey
0x1800070f3  call    cs:__imp_RegOpenKeyExW
0x1800070f9  mov     edx, eax
0x1800070fb  test    eax, eax
0x1800070fd  jnz     short loc_180007111
0x1800070ff  mov     rcx, rbx; this
0x180007102  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007107  mov     edx, eax
0x180007109  mov     rax, [rsp+48h+var_18]
0x18000710e  mov     [rbx], rax
0x180007111  mov     eax, edx
0x180007113  add     rsp, 40h
0x180007117  pop     rbx
0x180007118  retn
```
