# std::_Task_async_state<void>::_Get_value(bool)

- ea: `0x14001a190`
- end: `0x14001a1f5`
- name: `?_Get_value@?$_Task_async_state@X@std@@UEAAAEAH_N@Z`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140006ec8`
- `0x14001a190`
- `0x14001a2b0`
- `0x14001a310`
- `0x1400288dc`

## string_xrefs

- `0x14001a1ac`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::_Get_value(__int64 a1, char a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v4 = *(_QWORD *)(a1 + 272);
  if ( !v4 )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "This function cannot be called on a default constructed task");
    pExceptionObject[0] = &std::range_error::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  Concurrency::details::_Task_impl_base::_Wait(v4);
  LOBYTE(v5) = a2;
  return std::_Associated_state<int>::_Get_value(a1, v5);
}

```

## disassembly

```asm
0x14001a190  mov     [rsp+arg_0], rbx
0x14001a195  push    rdi
0x14001a196  sub     rsp, 40h
0x14001a19a  mov     rbx, rcx
0x14001a19d  mov     dil, dl
0x14001a1a0  mov     rcx, [rcx+110h]
0x14001a1a7  test    rcx, rcx
0x14001a1aa  jnz     short loc_14001A1DB
0x14001a1ac  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x14001a1b3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14001a1b8  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x14001a1bd  lea     rax, ??_7range_error@std@@6B@; const std::range_error::`vftable'
0x14001a1c4  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x14001a1cb  mov     [rsp+48h+pExceptionObject], rax
0x14001a1d0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14001a1d5  call    _CxxThrowException
0x14001a1db  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x14001a1e0  mov     dl, dil
0x14001a1e3  mov     rcx, rbx
0x14001a1e6  mov     rbx, [rsp+48h+arg_0]
0x14001a1eb  add     rsp, 40h
0x14001a1ef  pop     rdi
0x14001a1f0  jmp     ?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z; std::_Associated_state<int>::_Get_value(bool)
```
