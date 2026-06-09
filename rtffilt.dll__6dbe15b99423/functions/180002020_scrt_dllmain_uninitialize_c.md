# __scrt_dllmain_uninitialize_c

- ea: `0x180002020`
- end: `0x180002050`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001c18`

## callees

- `0x180002020`
- `0x18000276c`
- `0x1800027fe`
- `0x180002822`
- `0x1800150b0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int v0; // edx
  CRtfITextHost *v1; // rcx
  int v2; // r8d
  int v3; // r9d
  int result; // eax
  int v5; // [rsp+20h] [rbp-8h]

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CRtfITextHost::TxSetScrollRange(v1, v0, v2, v3, v5);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180002020  sub     rsp, 28h
0x180002024  call    __scrt_is_ucrt_dll_in_use
0x180002029  test    eax, eax
0x18000202b  jz      short loc_18000203D
0x18000202d  lea     rcx, Table; Table
0x180002034  add     rsp, 28h
0x180002038  jmp     _execute_onexit_table
0x18000203d  call    ?TxSetScrollRange@CRtfITextHost@@UEAAHHJHH@Z; CRtfITextHost::TxSetScrollRange(int,long,int,int)
0x180002042  test    eax, eax
0x180002044  jnz     short loc_18000204B
0x180002046  call    _o__cexit_0
0x18000204b  add     rsp, 28h
0x18000204f  retn
```
