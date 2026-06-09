# CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)

- ea: `0x1800309ec`
- end: `0x180030a53`
- name: `?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z`
- size: `103`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180031130`

## callees

- `0x1800309ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030a30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030a30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030a05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030a05`

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
0x1800309ec  mov     [rsp+arg_0], rbx
0x1800309f1  push    rdi
0x1800309f2  sub     rsp, 30h
0x1800309f6  lea     rbx, [rcx+18h]
0x1800309fa  mov     rdi, r8
0x1800309fd  mov     rcx, [rbx]; hKey
0x180030a00  test    rcx, rcx
0x180030a03  jz      short loc_180030A18
0x180030a05  call    cs:__imp_RegCloseKey
0x180030a0c  nop     dword ptr [rax+rax+00h]
0x180030a11  mov     qword ptr [rbx], 0
0x180030a18  mov     r9d, 20019h; samDesired
0x180030a1e  mov     [rsp+38h+phkResult], rbx; phkResult
0x180030a23  xor     r8d, r8d; ulOptions
0x180030a26  mov     rdx, rdi; lpSubKey
0x180030a29  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180030a30  call    cs:__imp_RegOpenKeyExW
0x180030a37  nop     dword ptr [rax+rax+00h]
0x180030a3c  test    eax, eax
0x180030a3e  jz      short loc_180030A47
0x180030a40  mov     qword ptr [rbx], 0
0x180030a47  mov     rbx, [rsp+38h+arg_0]
0x180030a4c  add     rsp, 30h
0x180030a50  pop     rdi
0x180030a51  retn
```
