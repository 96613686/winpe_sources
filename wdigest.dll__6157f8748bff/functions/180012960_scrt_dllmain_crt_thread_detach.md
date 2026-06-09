# __scrt_dllmain_crt_thread_detach

- ea: `0x180012960`
- end: `0x180012975`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180012510`

## callees

- `0x180013c20`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x180012960  sub     rsp, 28h
0x180012964  call    __scrt_stub_for_acrt_uninitialize_critical
0x180012969  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001296e  mov     al, 1
0x180012970  add     rsp, 28h
0x180012974  retn
```
