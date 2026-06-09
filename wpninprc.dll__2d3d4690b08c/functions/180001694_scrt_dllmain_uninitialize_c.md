# __scrt_dllmain_uninitialize_c

- ea: `0x180001694`
- end: `0x1800016c4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800012f8`

## callees

- `0x180001694`
- `0x180001da4`
- `0x180002002`
- `0x180002026`
- `0x180002118`

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
0x180001694  sub     rsp, 28h
0x180001698  call    __scrt_is_ucrt_dll_in_use
0x18000169d  test    eax, eax
0x18000169f  jz      short loc_1800016B1
0x1800016a1  lea     rcx, Table; Table
0x1800016a8  add     rsp, 28h
0x1800016ac  jmp     _execute_onexit_table
0x1800016b1  call    __scrt_stub_for_is_c_termination_complete
0x1800016b6  test    eax, eax
0x1800016b8  jnz     short loc_1800016BF
0x1800016ba  call    _o__cexit_0
0x1800016bf  add     rsp, 28h
0x1800016c3  retn
```
