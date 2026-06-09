# CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)

- ea: `0x18002e004`
- end: `0x18002e05e`
- name: `?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z`
- size: `90`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002e6a4`

## callees

- `0x18002e004`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e042`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e042`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e01d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e01d`

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
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, phkResult);
  if ( result )
    *phkResult = 0;
  return result;
}

```

## disassembly

```asm
0x18002e004  mov     [rsp+arg_0], rbx
0x18002e009  push    rdi
0x18002e00a  sub     rsp, 30h
0x18002e00e  lea     rbx, [rcx+18h]
0x18002e012  mov     rdi, r8
0x18002e015  mov     rcx, [rbx]; hKey
0x18002e018  test    rcx, rcx
0x18002e01b  jz      short loc_18002E02A
0x18002e01d  call    cs:__imp_RegCloseKey
0x18002e023  mov     qword ptr [rbx], 0
0x18002e02a  mov     r9d, 20019h; samDesired
0x18002e030  mov     [rsp+38h+phkResult], rbx; phkResult
0x18002e035  xor     r8d, r8d; ulOptions
0x18002e038  mov     rdx, rdi; lpSubKey
0x18002e03b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e042  call    cs:__imp_RegOpenKeyExW
0x18002e048  test    eax, eax
0x18002e04a  jz      short loc_18002E053
0x18002e04c  mov     qword ptr [rbx], 0
0x18002e053  mov     rbx, [rsp+38h+arg_0]
0x18002e058  add     rsp, 30h
0x18002e05c  pop     rdi
0x18002e05d  retn
```
