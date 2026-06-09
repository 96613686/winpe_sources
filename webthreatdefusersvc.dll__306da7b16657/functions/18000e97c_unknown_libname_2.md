# unknown_libname_2

- ea: `0x18000e97c`
- end: `0x18000e9a3`
- name: `unknown_libname_2`
- size: `39`
- prototype: `void __noreturn()`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074bc`
- `0x18000e4a0`
- `0x18000f5f0`

## callees

- `0x180004234`
- `0x180006d50`

## string_xrefs

- `0x18000e980`: `This function cannot be called on a default constructed task`

## pseudocode

```c
// Microsoft VisualC v7/14 64bit runtime
void __noreturn unknown_libname_2()
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180006D50(pExceptionObject, "This function cannot be called on a default constructed task");
  throw (Concurrency::invalid_operation *)pExceptionObject;
}

```

## disassembly

```asm
0x18000e97c  sub     rsp, 48h
0x18000e980  lea     rdx, aThisFunctionCa
0x18000e987  lea     rcx, [rsp+48h+pExceptionObject]
0x18000e98c  call    sub_180006D50
0x18000e991  lea     rdx, __TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18000e998  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e99d  call    _CxxThrowException
```
