# Concurrency::cancel_current_task(void)

- ea: `0x180004084`
- end: `0x1800040a4`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003b90`

## callees

- `0x18000405c`
- `0x180004234`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_18000405C(pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180004084  sub     rsp, 48h
0x180004088  lea     rcx, [rsp+48h+pExceptionObject]
0x18000408d  call    sub_18000405C
0x180004092  lea     rdx, __TI2?AVbad_alloc@std@@; pThrowInfo
0x180004099  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000409e  call    _CxxThrowException
```
