# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180006c70`
- end: `0x180006cc1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007478`
- `0x1800078b0`

## callees

- `0x1800045c4`
- `0x180006c70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c9b`

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
0x180006c70  push    rbx
0x180006c72  sub     rsp, 40h
0x180006c76  mov     rbx, rcx
0x180006c79  mov     [rsp+48h+var_18], 0
0x180006c82  mov     rax, r8
0x180006c85  lea     rcx, [rsp+48h+var_18]
0x180006c8a  mov     r10, rdx
0x180006c8d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180006c92  mov     rcx, r10; hKey
0x180006c95  xor     r8d, r8d; ulOptions
0x180006c98  mov     rdx, rax; lpSubKey
0x180006c9b  call    cs:__imp_RegOpenKeyExW
0x180006ca1  mov     edx, eax
0x180006ca3  test    eax, eax
0x180006ca5  jnz     short loc_180006CB9
0x180006ca7  mov     rcx, rbx; this
0x180006caa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006caf  mov     edx, eax
0x180006cb1  mov     rax, [rsp+48h+var_18]
0x180006cb6  mov     [rbx], rax
0x180006cb9  mov     eax, edx
0x180006cbb  add     rsp, 40h
0x180006cbf  pop     rbx
0x180006cc0  retn
```
