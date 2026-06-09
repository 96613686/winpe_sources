# __scrt_dllmain_uninitialize_c

- ea: `0x18003a7d4`
- end: `0x18003a804`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a368`

## callees

- `0x180032600`
- `0x18003a7d4`
- `0x18003adb8`
- `0x18003ae5a`
- `0x18003ae7e`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18003a7d4  sub     rsp, 28h
0x18003a7d8  call    __scrt_is_ucrt_dll_in_use
0x18003a7dd  test    eax, eax
0x18003a7df  jz      short loc_18003A7F1
0x18003a7e1  lea     rcx, Table; Table
0x18003a7e8  add     rsp, 28h
0x18003a7ec  jmp     _execute_onexit_table
0x18003a7f1  call    __scrt_stub_for_is_c_termination_complete
0x18003a7f6  test    eax, eax
0x18003a7f8  jnz     short loc_18003A7FF
0x18003a7fa  call    _o__cexit_0
0x18003a7ff  add     rsp, 28h
0x18003a803  retn
```
