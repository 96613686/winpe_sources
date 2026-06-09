# RegistryFunctions::RegDeleteTreeW(HKEY__ *,ushort const *)

- ea: `0x180010030`
- end: `0x18001003d`
- name: `?RegDeleteTreeW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG@Z`
- size: `13`
- prototype: `LSTATUS __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180010036`

## pseudocode

```c
LSTATUS __fastcall RegistryFunctions::RegDeleteTreeW(RegistryFunctions *this, HKEY a2, const unsigned __int16 *a3)
{
  return RegDeleteTreeW(a2, a3);
}

```

## disassembly

```asm
0x180010030  mov     rcx, rdx
0x180010033  mov     rdx, r8
0x180010036  jmp     cs:__imp_RegDeleteTreeW
```
