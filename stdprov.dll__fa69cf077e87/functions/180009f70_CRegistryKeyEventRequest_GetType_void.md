# CRegistryKeyEventRequest::GetType(void)

- ea: `0x180009f70`
- end: `0x180009f76`
- name: `?GetType@CRegistryKeyEventRequest@@UEAAHXZ`
- size: `6`
- prototype: `__int64 __fastcall(CRegistryKeyEventRequest *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CRegistryKeyEventRequest::GetType(CRegistryKeyEventRequest *this)
{
  return 1;
}

```

## disassembly

```asm
0x180009f70  mov     eax, 1
0x180009f75  retn
```
