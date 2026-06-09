# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180004cc0`
- end: `0x180004d11`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005168`
- `0x1800055a0`

## callees

- `0x180003de4`
- `0x180004cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ceb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004ceb`

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
0x180004cc0  push    rbx
0x180004cc2  sub     rsp, 40h
0x180004cc6  mov     rbx, rcx
0x180004cc9  mov     [rsp+48h+var_18], 0
0x180004cd2  mov     rax, r8
0x180004cd5  lea     rcx, [rsp+48h+var_18]
0x180004cda  mov     r10, rdx
0x180004cdd  mov     [rsp+48h+phkResult], rcx; phkResult
0x180004ce2  mov     rcx, r10; hKey
0x180004ce5  xor     r8d, r8d; ulOptions
0x180004ce8  mov     rdx, rax; lpSubKey
0x180004ceb  call    cs:__imp_RegOpenKeyExW
0x180004cf1  mov     edx, eax
0x180004cf3  test    eax, eax
0x180004cf5  jnz     short loc_180004D09
0x180004cf7  mov     rcx, rbx; this
0x180004cfa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004cff  mov     edx, eax
0x180004d01  mov     rax, [rsp+48h+var_18]
0x180004d06  mov     [rbx], rax
0x180004d09  mov     eax, edx
0x180004d0b  add     rsp, 40h
0x180004d0f  pop     rbx
0x180004d10  retn
```
