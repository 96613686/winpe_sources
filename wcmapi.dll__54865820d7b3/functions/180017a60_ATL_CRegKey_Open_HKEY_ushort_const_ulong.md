# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180017a60`
- end: `0x180017ad4`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `116`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006750`
- `0x180006f30`
- `0x180007db0`
- `0x180008010`
- `0x1800176c0`
- `0x180017b50`
- `0x18001aa44`
- `0x18001acac`

## callees

- `0x1800075e8`
- `0x180008a90`
- `0x180017a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a9a`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // ecx
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
0x180017a60  push    rbx
0x180017a62  sub     rsp, 40h
0x180017a66  mov     rax, cs:__security_cookie
0x180017a6d  xor     rax, rsp
0x180017a70  mov     [rsp+48h+var_10], rax
0x180017a75  mov     rbx, rcx
0x180017a78  mov     [rsp+48h+var_18], 0
0x180017a81  mov     r10, r8
0x180017a84  lea     rcx, [rsp+48h+var_18]
0x180017a89  mov     rax, rdx
0x180017a8c  mov     [rsp+48h+phkResult], rcx; phkResult
0x180017a91  mov     rcx, rax; hKey
0x180017a94  xor     r8d, r8d; ulOptions
0x180017a97  mov     rdx, r10; lpSubKey
0x180017a9a  call    cs:__imp_RegOpenKeyExW
0x180017aa1  nop     dword ptr [rax+rax+00h]
0x180017aa6  mov     ecx, eax
0x180017aa8  test    eax, eax
0x180017aaa  jnz     short loc_180017ABE
0x180017aac  mov     rcx, rbx; this
0x180017aaf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180017ab4  mov     ecx, eax
0x180017ab6  mov     rax, [rsp+48h+var_18]
0x180017abb  mov     [rbx], rax
0x180017abe  mov     eax, ecx
0x180017ac0  mov     rcx, [rsp+48h+var_10]
0x180017ac5  xor     rcx, rsp; StackCookie
0x180017ac8  call    __security_check_cookie
0x180017acd  add     rsp, 40h
0x180017ad1  pop     rbx
0x180017ad2  retn
```
