# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180011a80`
- end: `0x180011ad7`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000cb80`
- `0x18001eb18`
- `0x18001ef4c`
- `0x180039a30`

## callees

- `0x180011a80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011abf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011abf`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(a2, a3, 0, a4, &phkResult);
  if ( !v5 )
  {
    if ( *this )
      v5 = RegCloseKey(*this);
    *this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x180011a80  push    rbx
0x180011a82  sub     rsp, 40h
0x180011a86  mov     rbx, rcx
0x180011a89  mov     [rsp+48h+var_18], 0
0x180011a92  mov     rax, r8
0x180011a95  lea     rcx, [rsp+48h+var_18]
0x180011a9a  mov     r10, rdx
0x180011a9d  mov     [rsp+48h+phkResult], rcx; phkResult
0x180011aa2  mov     rcx, r10; hKey
0x180011aa5  xor     r8d, r8d; ulOptions
0x180011aa8  mov     rdx, rax; lpSubKey
0x180011aab  call    cs:__imp_RegOpenKeyExW
0x180011ab1  mov     edx, eax
0x180011ab3  test    eax, eax
0x180011ab5  jnz     short loc_180011ACF
0x180011ab7  mov     rcx, [rbx]; hKey
0x180011aba  test    rcx, rcx
0x180011abd  jz      short loc_180011AC7
0x180011abf  call    cs:__imp_RegCloseKey
0x180011ac5  mov     edx, eax
0x180011ac7  mov     rax, [rsp+48h+var_18]
0x180011acc  mov     [rbx], rax
0x180011acf  mov     eax, edx
0x180011ad1  add     rsp, 40h
0x180011ad5  pop     rbx
0x180011ad6  retn
```
