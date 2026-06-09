# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000a1d8`
- end: `0x14000a1f8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400023fc`
- `0x140007000`
- `0x140007078`
- `0x140007498`
- `0x14000780c`
- `0x140007980`
- `0x140007bf8`
- `0x140007d60`

## callees

- `0x140002c68`
- `0x14000830c`

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
0x14000a1d8  sub     rsp, 48h
0x14000a1dc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000a1e1  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000a1e6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000a1ed  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000a1f2  call    _CxxThrowException_0
```
