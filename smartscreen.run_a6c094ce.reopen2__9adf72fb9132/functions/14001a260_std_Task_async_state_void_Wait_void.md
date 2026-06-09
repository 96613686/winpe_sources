# std::_Task_async_state<void>::_Wait(void)

- ea: `0x14001a260`
- end: `0x14001a2a8`
- name: `?_Wait@?$_Task_async_state@X@std@@UEAAXXZ`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x140006ec8`
- `0x14001a260`
- `0x14001a2b0`
- `0x1400288dc`

## string_xrefs

- `0x14001a270`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::_Wait(__int64 a1)
{
  __int64 v1; // rcx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 272);
  if ( !v1 )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "This function cannot be called on a default constructed task");
    pExceptionObject[0] = &std::range_error::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  return Concurrency::details::_Task_impl_base::_Wait(v1);
}

```

## disassembly

```asm
0x14001a260  sub     rsp, 48h
0x14001a264  mov     rcx, [rcx+110h]
0x14001a26b  test    rcx, rcx
0x14001a26e  jnz     short loc_14001A29F
0x14001a270  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x14001a277  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001a27c  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x14001a281  lea     rax, ??_7range_error@std@@6B@; const std::range_error::`vftable'
0x14001a288  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x14001a28f  mov     [rsp+48h+pExceptionObject], rax
0x14001a294  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001a299  call    _CxxThrowException
0x14001a29f  add     rsp, 48h
0x14001a2a3  jmp     ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
```
