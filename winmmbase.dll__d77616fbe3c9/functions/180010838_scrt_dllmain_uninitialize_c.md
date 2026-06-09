# __scrt_dllmain_uninitialize_c

- ea: `0x180010838`
- end: `0x180010868`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800104a8`

## callees

- `0x180010838`
- `0x180010f34`
- `0x180010f8e`
- `0x180010fb2`
- `0x18001c110`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  const unsigned __int16 *v0; // rdx
  CWinmmNotificationClient *v1; // rcx
  struct _tagpropertykey *v2; // r8
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CWinmmNotificationClient::OnPropertyValueChanged(v1, v0, v2);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180010838  sub     rsp, 28h
0x18001083c  call    __scrt_is_ucrt_dll_in_use
0x180010841  test    eax, eax
0x180010843  jz      short loc_180010855
0x180010845  lea     rcx, Table; Table
0x18001084c  add     rsp, 28h
0x180010850  jmp     _execute_onexit_table
0x180010855  call    ?OnPropertyValueChanged@CWinmmNotificationClient@@UEAAJPEBGU_tagpropertykey@@@Z; CWinmmNotificationClient::OnPropertyValueChanged(ushort const *,_tagpropertykey)
0x18001085a  test    eax, eax
0x18001085c  jnz     short loc_180010863
0x18001085e  call    _o__cexit_0
0x180010863  add     rsp, 28h
0x180010867  retn
```
