# ClearPersistentHandlerValue(HKEY__ *)

- ea: `0x18000df50`
- end: `0x18000df6d`
- name: `?ClearPersistentHandlerValue@@YAJPEAUHKEY__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(HKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e938`

## callees

- `0x18000df50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000df56`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000df56`

## pseudocode

```c
LSTATUS __fastcall ClearPersistentHandlerValue(HKEY a1)
{
  LSTATUS result; // eax

  result = RegDeleteValueW(a1, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000df50  sub     rsp, 28h
0x18000df54  xor     edx, edx; lpValueName
0x18000df56  call    cs:__imp_RegDeleteValueW
0x18000df5c  test    eax, eax
0x18000df5e  jle     short loc_18000DF68
0x18000df60  movzx   eax, ax
0x18000df63  or      eax, 80070000h
0x18000df68  add     rsp, 28h
0x18000df6c  retn
```
