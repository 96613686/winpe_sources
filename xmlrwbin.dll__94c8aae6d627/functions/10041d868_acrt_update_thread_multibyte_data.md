# __acrt_update_thread_multibyte_data

- ea: `0x10041d868`
- end: `0x10041d884`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10041f264`
- `0x10041f29c`

## callees

- `0x10041b7bc`
- `0x10041d73c`

## pseudocode

```c
volatile signed __int32 *_acrt_update_thread_multibyte_data()
{
  __int64 v0; // rax

  v0 = _acrt_getptd();
  return update_thread_multibyte_data_internal(v0, (volatile signed __int32 **)&_acrt_current_multibyte_data);
}

```

## disassembly

```asm
0x10041d868  sub     rsp, 28h
0x10041d86c  call    __acrt_getptd
0x10041d871  lea     rdx, __acrt_current_multibyte_data
0x10041d878  mov     rcx, rax
0x10041d87b  add     rsp, 28h
0x10041d87f  jmp     update_thread_multibyte_data_internal
```
