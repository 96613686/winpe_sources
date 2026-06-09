# _Cnd_unregister_at_thread_exit

- ea: `0x180019005`
- end: `0x18001900b`
- name: `_Cnd_unregister_at_thread_exit`
- size: `6`
- prototype: `void __cdecl(_Mtx_t)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800073ec`
- `0x180008610`

## import_xrefs

- `msvcp_win!_Cnd_unregister_at_thread_exit` at `0x180019005`

## pseudocode

```c
// attributes: thunk
void __cdecl Cnd_unregister_at_thread_exit(_Mtx_t a1)
{
  _Cnd_unregister_at_thread_exit(a1);
}

```

## disassembly

```asm
0x180019005  jmp     cs:__imp__Cnd_unregister_at_thread_exit
```
