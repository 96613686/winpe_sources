# _guard_dispatch_icall_nop

- ea: `0x18000af10`
- end: `0x18000af12`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180001ce0`
- `0x180001f54`
- `0x1800021cc`
- `0x18000aee0`
- `0x18000af40`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x18000af10  jmp     rax
```
