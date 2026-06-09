# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000c5ac`
- end: `0x18000c5cc`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e90`
- `0x180003a84`
- `0x18000e22c`
- `0x18000e47c`
- `0x18000e5bc`
- `0x18000f7dc`
- `0x1800169b8`

## callees

- `0x1800028c0`
- `0x180003e9c`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x18000c5ac  sub     rsp, 48h
0x18000c5b0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000c5b5  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000c5ba  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000c5c1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c5c6  call    _CxxThrowException_0
```
