# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800042b4`
- end: `0x18000430b`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003ae0`

## callees

- `0x180004080`
- `0x1800042b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042e5`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x1800042b4  push    rbx
0x1800042b6  sub     rsp, 40h
0x1800042ba  mov     rbx, rcx
0x1800042bd  mov     [rsp+48h+var_18], 0
0x1800042c6  mov     rax, r8
0x1800042c9  lea     rcx, [rsp+48h+var_18]
0x1800042ce  mov     r10, rdx
0x1800042d1  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800042d6  mov     rcx, r10; hKey
0x1800042d9  mov     r9d, 20019h; samDesired
0x1800042df  xor     r8d, r8d; ulOptions
0x1800042e2  mov     rdx, rax; lpSubKey
0x1800042e5  call    cs:__imp_RegOpenKeyExW
0x1800042eb  mov     edx, eax
0x1800042ed  test    eax, eax
0x1800042ef  jnz     short loc_180004303
0x1800042f1  mov     rcx, rbx; this
0x1800042f4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800042f9  mov     edx, eax
0x1800042fb  mov     rax, [rsp+48h+var_18]
0x180004300  mov     [rbx], rax
0x180004303  mov     eax, edx
0x180004305  add     rsp, 40h
0x180004309  pop     rbx
0x18000430a  retn
```
