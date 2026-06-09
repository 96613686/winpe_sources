# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001d510`
- end: `0x18001d561`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001df08`
- `0x18001e340`

## callees

- `0x18001ba14`
- `0x18001d510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d53b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d53b`

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
0x18001d510  push    rbx
0x18001d512  sub     rsp, 40h
0x18001d516  mov     rbx, rcx
0x18001d519  mov     [rsp+48h+var_18], 0
0x18001d522  mov     rax, r8
0x18001d525  lea     rcx, [rsp+48h+var_18]
0x18001d52a  mov     r10, rdx
0x18001d52d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001d532  mov     rcx, r10; hKey
0x18001d535  xor     r8d, r8d; ulOptions
0x18001d538  mov     rdx, rax; lpSubKey
0x18001d53b  call    cs:__imp_RegOpenKeyExW
0x18001d541  mov     edx, eax
0x18001d543  test    eax, eax
0x18001d545  jnz     short loc_18001D559
0x18001d547  mov     rcx, rbx; this
0x18001d54a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001d54f  mov     edx, eax
0x18001d551  mov     rax, [rsp+48h+var_18]
0x18001d556  mov     [rbx], rax
0x18001d559  mov     eax, edx
0x18001d55b  add     rsp, 40h
0x18001d55f  pop     rbx
0x18001d560  retn
```
