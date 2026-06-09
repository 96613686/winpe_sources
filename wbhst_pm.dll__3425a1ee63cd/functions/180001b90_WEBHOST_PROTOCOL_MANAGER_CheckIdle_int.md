# WEBHOST_PROTOCOL_MANAGER::CheckIdle(int *)

- ea: `0x180001b90`
- end: `0x180001ba0`
- name: `?CheckIdle@WEBHOST_PROTOCOL_MANAGER@@UEAAJPEAH@Z`
- size: `16`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005010`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::CheckIdle(WEBHOST_PROTOCOL_MANAGER *this, int *a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 9) + 24LL))(*((_QWORD *)this + 9), a2);
}

```

## disassembly

```asm
0x180001b90  mov     rcx, [rcx+48h]
0x180001b94  mov     rax, [rcx]
0x180001b97  mov     rax, [rax+18h]
0x180001b9b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
