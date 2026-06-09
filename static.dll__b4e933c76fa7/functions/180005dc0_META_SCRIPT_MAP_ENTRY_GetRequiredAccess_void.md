# META_SCRIPT_MAP_ENTRY::GetRequiredAccess(void)

- ea: `0x180005dc0`
- end: `0x180005dc7`
- name: `?GetRequiredAccess@META_SCRIPT_MAP_ENTRY@@UEBAKXZ`
- size: `7`
- prototype: `unsigned int __fastcall(META_SCRIPT_MAP_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP_ENTRY::GetRequiredAccess(META_SCRIPT_MAP_ENTRY *this)
{
  return *((unsigned int *)this + 91);
}

```

## disassembly

```asm
0x180005dc0  mov     eax, [rcx+16Ch]
0x180005dc6  retn
```
