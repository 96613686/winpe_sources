# RegistryFunctions::RegDeleteKeyW(HKEY__ *,ushort const *)

- ea: `0x180010010`
- end: `0x180010026`
- name: `?RegDeleteKeyW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG@Z`
- size: `22`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001001f`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegDeleteKeyW(RegistryFunctions *this, HKEY a2, const unsigned __int16 *a3)
{
  return RegDeleteKeyExW(a2, a3, 0, 0);
}

```

## disassembly

```asm
0x180010010  mov     rax, r8
0x180010013  mov     rcx, rdx
0x180010016  mov     rdx, rax
0x180010019  xor     r9d, r9d
0x18001001c  xor     r8d, r8d
0x18001001f  jmp     cs:__imp_RegDeleteKeyExW
```
