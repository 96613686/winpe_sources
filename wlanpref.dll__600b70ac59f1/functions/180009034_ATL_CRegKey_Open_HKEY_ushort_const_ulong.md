# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180009034`
- end: `0x180009085`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004fc8`
- `0x18000a8e8`
- `0x18000af10`

## callees

- `0x180005814`
- `0x180009034`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000905f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000905f`

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
0x180009034  push    rbx
0x180009036  sub     rsp, 40h
0x18000903a  mov     rbx, rcx
0x18000903d  mov     [rsp+48h+var_18], 0
0x180009046  mov     rax, r8
0x180009049  lea     rcx, [rsp+48h+var_18]
0x18000904e  mov     r10, rdx
0x180009051  mov     [rsp+48h+phkResult], rcx; phkResult
0x180009056  mov     rcx, r10; hKey
0x180009059  xor     r8d, r8d; ulOptions
0x18000905c  mov     rdx, rax; lpSubKey
0x18000905f  call    cs:__imp_RegOpenKeyExW
0x180009065  mov     edx, eax
0x180009067  test    eax, eax
0x180009069  jnz     short loc_18000907D
0x18000906b  mov     rcx, rbx; this
0x18000906e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009073  mov     edx, eax
0x180009075  mov     rax, [rsp+48h+var_18]
0x18000907a  mov     [rbx], rax
0x18000907d  mov     eax, edx
0x18000907f  add     rsp, 40h
0x180009083  pop     rbx
0x180009084  retn
```
