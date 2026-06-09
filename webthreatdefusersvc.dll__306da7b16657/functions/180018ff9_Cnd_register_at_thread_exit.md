# _Cnd_register_at_thread_exit

- ea: `0x180018ff9`
- end: `0x180018fff`
- name: `_Cnd_register_at_thread_exit`
- size: `6`
- prototype: `void __cdecl(_Cnd_t, _Mtx_t, int *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000da90`

## import_xrefs

- `msvcp_win!_Cnd_register_at_thread_exit` at `0x180018ff9`

## pseudocode

```c
// attributes: thunk
void __cdecl Cnd_register_at_thread_exit(_Cnd_t a1, _Mtx_t a2, int *a3)
{
  _Cnd_register_at_thread_exit(a1, a2, a3);
}

```

## disassembly

```asm
0x180018ff9  jmp     cs:__imp__Cnd_register_at_thread_exit
```
