# _register_thread_local_exe_atexit_callback_0

- ea: `0x1400020e0`
- end: `0x1400020e6`
- name: `_register_thread_local_exe_atexit_callback_0`
- size: `6`
- prototype: `void __cdecl(_tls_callback_type Callback)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400013f0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_register_thread_local_exe_atexit_callback` at `0x1400020e0`

## pseudocode

```c
// attributes: thunk
void __cdecl register_thread_local_exe_atexit_callback_0(_tls_callback_type Callback)
{
  _register_thread_local_exe_atexit_callback(Callback);
}

```

## disassembly

```asm
0x1400020e0  jmp     cs:__imp__register_thread_local_exe_atexit_callback
```
