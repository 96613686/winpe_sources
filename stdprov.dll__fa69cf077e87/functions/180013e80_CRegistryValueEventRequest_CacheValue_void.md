# CRegistryValueEventRequest::CacheValue(void)

- ea: `0x180013e80`
- end: `0x180013e93`
- name: `?CacheValue@CRegistryValueEventRequest@@UEAAXXZ`
- size: `19`
- prototype: `void __fastcall(CRegistryValueEventRequest *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180017010`

## pseudocode

```c
void __fastcall CRegistryValueEventRequest::CacheValue(CRegistryValueEventRequest *this)
{
  (*(void (__fastcall **)(CRegistryValueEventRequest *, char *))(*(_QWORD *)this + 40LL))(this, (char *)this + 160);
}

```

## disassembly

```asm
0x180013e80  mov     rax, [rcx]
0x180013e83  lea     rdx, [rcx+0A0h]
0x180013e8a  mov     rax, [rax+28h]
0x180013e8e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
