# __acrt_update_thread_multibyte_data

- ea: `0x10042fdf8`
- end: `0x10042fe14`
- name: `__acrt_update_thread_multibyte_data`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1004319d0`
- `0x100431a08`

## callees

- `0x10042dd4c`
- `0x10042fccc`

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
0x10042fdf8  sub     rsp, 28h
0x10042fdfc  call    __acrt_getptd
0x10042fe01  lea     rdx, __acrt_current_multibyte_data
0x10042fe08  mov     rcx, rax
0x10042fe0b  add     rsp, 28h
0x10042fe0f  jmp     update_thread_multibyte_data_internal
```
