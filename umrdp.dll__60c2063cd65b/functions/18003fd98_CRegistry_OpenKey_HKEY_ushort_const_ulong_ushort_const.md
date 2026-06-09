# CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)

- ea: `0x18003fd98`
- end: `0x18003fdf2`
- name: `?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z`
- size: `90`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002c0bc`

## callees

- `0x18003fd98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fdd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003fdd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fdb1`

## pseudocode

```c
LSTATUS __fastcall CRegistry::OpenKey(CRegistry *this, HKEY a2, const unsigned __int16 *a3)
{
  HKEY *phkResult; // rbx
  HKEY v5; // rcx
  LSTATUS result; // eax

  phkResult = (HKEY *)((char *)this + 24);
  v5 = (HKEY)*((_QWORD *)this + 3);
  if ( v5 )
  {
    RegCloseKey(v5);
    *phkResult = 0;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0xF003Fu, phkResult);
  if ( result )
    *phkResult = 0;
  return result;
}

```

## disassembly

```asm
0x18003fd98  mov     [rsp+arg_0], rbx
0x18003fd9d  push    rdi
0x18003fd9e  sub     rsp, 30h
0x18003fda2  lea     rbx, [rcx+18h]
0x18003fda6  mov     rdi, r8
0x18003fda9  mov     rcx, [rbx]; hKey
0x18003fdac  test    rcx, rcx
0x18003fdaf  jz      short loc_18003FDBE
0x18003fdb1  call    cs:__imp_RegCloseKey
0x18003fdb7  mov     qword ptr [rbx], 0
0x18003fdbe  mov     r9d, 0F003Fh; samDesired
0x18003fdc4  mov     [rsp+38h+phkResult], rbx; phkResult
0x18003fdc9  xor     r8d, r8d; ulOptions
0x18003fdcc  mov     rdx, rdi; lpSubKey
0x18003fdcf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003fdd6  call    cs:__imp_RegOpenKeyExW
0x18003fddc  test    eax, eax
0x18003fdde  jz      short loc_18003FDE7
0x18003fde0  mov     qword ptr [rbx], 0
0x18003fde7  mov     rbx, [rsp+38h+arg_0]
0x18003fdec  add     rsp, 30h
0x18003fdf0  pop     rdi
0x18003fdf1  retn
```
