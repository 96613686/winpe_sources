# Concurrency::cancel_current_task(void)

- ea: `0x1800034ec`
- end: `0x18000350c`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002d10`

## callees

- `0x180003640`
- `0x180012894`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180012894(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x1800034ec  sub     rsp, 48h
0x1800034f0  lea     rcx, [rsp+48h+pExceptionObject]
0x1800034f5  call    sub_180012894
0x1800034fa  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180003501  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180003506  call    _CxxThrowException
```
