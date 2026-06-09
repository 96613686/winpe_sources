# META_SCRIPT_MAP_ENTRY::GetAllowPathInfoForScriptMappings(void)

- ea: `0x180005cc0`
- end: `0x180005cc7`
- name: `?GetAllowPathInfoForScriptMappings@META_SCRIPT_MAP_ENTRY@@UEBAHXZ`
- size: `7`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP_ENTRY::GetAllowPathInfoForScriptMappings(META_SCRIPT_MAP_ENTRY *this)
{
  return *((unsigned int *)this + 93);
}

```

## disassembly

```asm
0x180005cc0  mov     eax, [rcx+174h]
0x180005cc6  retn
```
