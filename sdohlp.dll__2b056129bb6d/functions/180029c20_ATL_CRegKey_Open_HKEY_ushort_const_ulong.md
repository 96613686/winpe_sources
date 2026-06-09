# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180029c20`
- end: `0x180029c71`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002637c`
- `0x18002a148`
- `0x18002a62c`
- `0x180047458`

## callees

- `0x180026a40`
- `0x180029c20`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180029c4b`
- `ADVAPI32!RegOpenKeyExW` at `0x180029c4b`

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
0x180029c20  push    rbx
0x180029c22  sub     rsp, 40h
0x180029c26  mov     rbx, rcx
0x180029c29  mov     [rsp+48h+var_18], 0
0x180029c32  mov     rax, r8
0x180029c35  lea     rcx, [rsp+48h+var_18]
0x180029c3a  mov     r10, rdx
0x180029c3d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180029c42  mov     rcx, r10; hKey
0x180029c45  xor     r8d, r8d; ulOptions
0x180029c48  mov     rdx, rax; lpSubKey
0x180029c4b  call    cs:__imp_RegOpenKeyExW
0x180029c51  mov     edx, eax
0x180029c53  test    eax, eax
0x180029c55  jnz     short loc_180029C69
0x180029c57  mov     rcx, rbx; this
0x180029c5a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029c5f  mov     edx, eax
0x180029c61  mov     rax, [rsp+48h+var_18]
0x180029c66  mov     [rbx], rax
0x180029c69  mov     eax, edx
0x180029c6b  add     rsp, 40h
0x180029c6f  pop     rbx
0x180029c70  retn
```
