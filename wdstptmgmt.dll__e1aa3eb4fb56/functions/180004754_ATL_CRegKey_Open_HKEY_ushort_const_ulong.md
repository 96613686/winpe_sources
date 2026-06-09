# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180004754`
- end: `0x1800047a9`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `85`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800039fc`
- `0x180004a08`
- `0x180004f1c`

## callees

- `0x1800041b0`
- `0x180004754`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000477c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000477c`

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
0x180004754  push    rbx
0x180004756  sub     rsp, 40h
0x18000475a  and     [rsp+48h+var_18], 0
0x180004760  mov     rbx, rcx
0x180004763  mov     rax, r8
0x180004766  lea     rcx, [rsp+48h+var_18]
0x18000476b  mov     r10, rdx
0x18000476e  mov     [rsp+48h+phkResult], rcx; phkResult
0x180004773  mov     rcx, r10; hKey
0x180004776  xor     r8d, r8d; ulOptions
0x180004779  mov     rdx, rax; lpSubKey
0x18000477c  call    cs:__imp_RegOpenKeyExW
0x180004783  nop     dword ptr [rax+rax+00h]
0x180004788  mov     edx, eax
0x18000478a  test    eax, eax
0x18000478c  jnz     short loc_1800047A0
0x18000478e  mov     rcx, rbx; this
0x180004791  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180004796  mov     edx, eax
0x180004798  mov     rax, [rsp+48h+var_18]
0x18000479d  mov     [rbx], rax
0x1800047a0  mov     eax, edx
0x1800047a2  add     rsp, 40h
0x1800047a6  pop     rbx
0x1800047a7  retn
```
