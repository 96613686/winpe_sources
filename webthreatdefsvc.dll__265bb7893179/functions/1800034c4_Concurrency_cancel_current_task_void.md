# Concurrency::cancel_current_task(void)

- ea: `0x1800034c4`
- end: `0x1800034e4`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180002d10`

## callees

- `0x18000349c`
- `0x180003640`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_18000349C(pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x1800034c4  sub     rsp, 48h
0x1800034c8  lea     rcx, [rsp+48h+pExceptionObject]
0x1800034cd  call    sub_18000349C
0x1800034d2  lea     rdx, __TI2?AVbad_alloc@std@@; pThrowInfo
0x1800034d9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800034de  call    _CxxThrowException
```
