# VelocityGetRegDword(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x1800343b8`
- end: `0x180034443`
- name: `?VelocityGetRegDword@@YAHPEAUHKEY__@@PEBG1PEAK@Z`
- size: `139`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180034860`
- `0x1800348d0`

## callees

- `0x1800343b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003442b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003442b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034411`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034411`
- `ADVAPI32!RegOpenKeyW` at `0x1800343ea`
- `ADVAPI32!RegOpenKeyW` at `0x1800343ea`

## pseudocode

```c
_BOOL8 __fastcall VelocityGetRegDword(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, BYTE *a4)
{
  BOOL v5; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]

  v10 = HIDWORD(a1);
  cbData = 4;
  v5 = 0;
  hKey = 0;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, a2, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, a3, 0, 0, a4, &cbData) )
      v5 = cbData == 4;
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x1800343b8  mov     rax, rsp
0x1800343bb  mov     [rax+10h], rbx
0x1800343bf  mov     [rax+18h], rsi
0x1800343c3  mov     [rax+8], rcx
0x1800343c7  push    rdi
0x1800343c8  sub     rsp, 40h
0x1800343cc  mov     rsi, r8
0x1800343cf  mov     dword ptr [rax+8], 4
0x1800343d6  xor     ebx, ebx
0x1800343d8  lea     r8, [rax-18h]; phkResult
0x1800343dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800343e3  mov     [rax-18h], rbx
0x1800343e7  mov     rdi, r9
0x1800343ea  call    cs:__imp_RegOpenKeyW
0x1800343f0  test    eax, eax
0x1800343f2  jnz     short loc_180034431
0x1800343f4  mov     rcx, [rsp+48h+hKey]; hKey
0x1800343f9  lea     rax, [rsp+48h+cbData]
0x1800343fe  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180034403  xor     r9d, r9d; lpType
0x180034406  xor     r8d, r8d; lpReserved
0x180034409  mov     [rsp+48h+lpData], rdi; lpData
0x18003440e  mov     rdx, rsi; lpValueName
0x180034411  call    cs:__imp_RegQueryValueExW
0x180034417  test    eax, eax
0x180034419  jnz     short loc_180034426
0x18003441b  cmp     [rsp+48h+cbData], 4
0x180034420  lea     eax, [rbx+1]
0x180034423  cmovz   ebx, eax
0x180034426  mov     rcx, [rsp+48h+hKey]; hKey
0x18003442b  call    cs:__imp_RegCloseKey
0x180034431  mov     rsi, [rsp+48h+arg_10]
0x180034436  mov     eax, ebx
0x180034438  mov     rbx, [rsp+48h+arg_8]
0x18003443d  add     rsp, 40h
0x180034441  pop     rdi
0x180034442  retn
```
