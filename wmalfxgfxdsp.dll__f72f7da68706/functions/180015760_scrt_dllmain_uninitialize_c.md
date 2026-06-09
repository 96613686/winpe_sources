# __scrt_dllmain_uninitialize_c

- ea: `0x180015760`
- end: `0x180015790`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180015318`

## callees

- `0x180014ac0`
- `0x180015760`
- `0x180015d20`
- `0x180015d7e`
- `0x180015da2`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  const unsigned __int16 *v0; // rdx
  CCorrAPO *v1; // rcx
  unsigned int v2; // r8d
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CCorrAPO::OnDeviceStateChanged(v1, v0, v2);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180015760  sub     rsp, 28h
0x180015764  call    __scrt_is_ucrt_dll_in_use
0x180015769  test    eax, eax
0x18001576b  jz      short loc_18001577D
0x18001576d  lea     rcx, Table; Table
0x180015774  add     rsp, 28h
0x180015778  jmp     _execute_onexit_table
0x18001577d  call    ?OnDeviceStateChanged@CCorrAPO@@UEAAJPEBGK@Z; CCorrAPO::OnDeviceStateChanged(ushort const *,ulong)
0x180015782  test    eax, eax
0x180015784  jnz     short loc_18001578B
0x180015786  call    _o__cexit_0
0x18001578b  add     rsp, 28h
0x18001578f  retn
```
