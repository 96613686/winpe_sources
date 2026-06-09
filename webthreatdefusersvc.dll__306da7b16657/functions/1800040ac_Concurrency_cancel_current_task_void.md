# Concurrency::cancel_current_task(void)

- ea: `0x1800040ac`
- end: `0x1800040cc`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003b90`

## callees

- `0x180004234`
- `0x180022c8c`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180022C8C(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x1800040ac  sub     rsp, 48h
0x1800040b0  lea     rcx, [rsp+48h+pExceptionObject]
0x1800040b5  call    sub_180022C8C
0x1800040ba  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800040c1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800040c6  call    _CxxThrowException
```
