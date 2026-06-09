# CWshEnvRegistry::get_length(long *)

- ea: `0x18000c5c0`
- end: `0x18000c5cc`
- name: `?get_length@CWshEnvRegistry@@UEAAJPEAJ@Z`
- size: `12`
- prototype: `__int64 __fastcall(CWshEnvRegistry *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWshEnvRegistry::get_length(CWshEnvRegistry *this, int *a2)
{
  return (*(__int64 (__fastcall **)(CWshEnvRegistry *, int *))(*(_QWORD *)this + 72LL))(this, a2);
}

```

## disassembly

```asm
0x18000c5c0  mov     rax, [rcx]
0x18000c5c3  mov     rax, [rax+48h]
0x18000c5c7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
