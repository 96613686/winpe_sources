# std::_Task_async_state<void>::_Get_value(bool)

- ea: `0x1400194a0`
- end: `0x140019505`
- name: `?_Get_value@?$_Task_async_state@X@std@@UEAAAEAH_N@Z`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140006b30`
- `0x1400194a0`
- `0x1400195c0`
- `0x140019610`
- `0x14002771c`

## string_xrefs

- `0x1400194bc`: `This function cannot be called on a default constructed task`

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
0x1400194a0  mov     [rsp+arg_0], rbx
0x1400194a5  push    rdi
0x1400194a6  sub     rsp, 40h
0x1400194aa  mov     rbx, rcx
0x1400194ad  mov     dil, dl
0x1400194b0  mov     rcx, [rcx+110h]
0x1400194b7  test    rcx, rcx
0x1400194ba  jnz     short loc_1400194EB
0x1400194bc  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x1400194c3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400194c8  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1400194cd  lea     rax, ??_7range_error@std@@6B@; const std::range_error::`vftable'
0x1400194d4  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x1400194db  mov     [rsp+48h+pExceptionObject], rax
0x1400194e0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400194e5  call    _CxxThrowException
0x1400194eb  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1400194f0  mov     dl, dil
0x1400194f3  mov     rcx, rbx
0x1400194f6  mov     rbx, [rsp+48h+arg_0]
0x1400194fb  add     rsp, 40h
0x1400194ff  pop     rdi
0x140019500  jmp     ?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z; std::_Associated_state<int>::_Get_value(bool)
```
