# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180039bfc`
- end: `0x180039c4d`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180039fc8`
- `0x18003a3fc`
- `0x1800550f4`
- `0x18005b5b0`

## callees

- `0x18000d554`
- `0x180039bfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039c27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039c27`

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
0x180039bfc  push    rbx
0x180039bfe  sub     rsp, 40h
0x180039c02  mov     rbx, rcx
0x180039c05  mov     [rsp+48h+var_18], 0
0x180039c0e  mov     rax, r8
0x180039c11  lea     rcx, [rsp+48h+var_18]
0x180039c16  mov     r10, rdx
0x180039c19  mov     [rsp+48h+phkResult], rcx; phkResult
0x180039c1e  mov     rcx, r10; hKey
0x180039c21  xor     r8d, r8d; ulOptions
0x180039c24  mov     rdx, rax; lpSubKey
0x180039c27  call    cs:__imp_RegOpenKeyExW
0x180039c2d  mov     edx, eax
0x180039c2f  test    eax, eax
0x180039c31  jnz     short loc_180039C45
0x180039c33  mov     rcx, rbx; this
0x180039c36  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180039c3b  mov     edx, eax
0x180039c3d  mov     rax, [rsp+48h+var_18]
0x180039c42  mov     [rbx], rax
0x180039c45  mov     eax, edx
0x180039c47  add     rsp, 40h
0x180039c4b  pop     rbx
0x180039c4c  retn
```
