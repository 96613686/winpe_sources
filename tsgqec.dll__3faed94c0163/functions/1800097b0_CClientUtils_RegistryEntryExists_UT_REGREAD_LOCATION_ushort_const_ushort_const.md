# CClientUtils::RegistryEntryExists(UT_REGREAD_LOCATION,ushort const *,ushort const *)

- ea: `0x1800097b0`
- end: `0x1800097cd`
- name: `?RegistryEntryExists@CClientUtils@@UEAAHW4UT_REGREAD_LOCATION@@PEBG1@Z`
- size: `29`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800095c8`

## pseudocode

```c
__int64 __fastcall CClientUtils::RegistryEntryExists(__int64 a1, int a2, const unsigned __int16 *a3, char *a4)
{
  return CClientUtils::RegistryEntryExists((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, a4);
}

```

## disassembly

```asm
0x1800097b0  neg     edx
0x1800097b2  mov     rax, r8
0x1800097b5  mov     r8, r9; unsigned __int16 *
0x1800097b8  mov     rdx, rax; unsigned __int16 *
0x1800097bb  sbb     rcx, rcx
0x1800097be  neg     rcx
0x1800097c1  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800097c8  jmp     ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
```
