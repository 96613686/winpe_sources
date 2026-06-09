# CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180006a58`
- end: `0x180006a9d`
- name: `?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z`
- size: `69`
- prototype: `unsigned int __fastcall(PHKEY phkResult, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007b18`
- `0x180008f9c`
- `0x18000c69c`

## callees

- `0x180002918`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180006a85`
- `ADVAPI32!RegOpenKeyExW` at `0x180006a85`

## pseudocode

```c
LSTATUS __fastcall CRegKey::Open(CRegKey *phkResult, HKEY a2, const unsigned __int16 *a3)
{
  CRegKey::Close(phkResult);
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20119u, (PHKEY)phkResult);
}

```

## disassembly

```asm
0x180006a58  mov     [rsp+arg_0], rbx
0x180006a5d  push    rdi
0x180006a5e  sub     rsp, 30h
0x180006a62  mov     rdi, r8
0x180006a65  mov     rbx, rcx
0x180006a68  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x180006a6d  mov     r9d, 20119h; samDesired
0x180006a73  mov     [rsp+38h+phkResult], rbx; phkResult
0x180006a78  xor     r8d, r8d; ulOptions
0x180006a7b  mov     rdx, rdi; lpSubKey
0x180006a7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006a85  call    cs:__imp_RegOpenKeyExW
0x180006a8c  nop     dword ptr [rax+rax+00h]
0x180006a91  mov     rbx, [rsp+38h+arg_0]
0x180006a96  add     rsp, 30h
0x180006a9a  pop     rdi
0x180006a9b  retn
```
