# std::_Task_async_state<void>::~_Task_async_state<void>(void)

- ea: `0x140006e1c`
- end: `0x140006ec0`
- name: `??1?$_Task_async_state@X@std@@UEAA@XZ`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1400077a0`

## callees

- `0x140006d90`
- `0x140006e1c`
- `0x140006ec8`
- `0x14001a2b0`
- `0x14001da68`
- `0x1400288dc`
- `0x14006a010`

## string_xrefs

- `0x140006e91`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::~_Task_async_state<void>(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdx
  std::_Ref_count_base *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  *a1 = &std::_Task_async_state<void>::`vftable';
  v2 = a1[34];
  if ( !v2 )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "This function cannot be called on a default constructed task");
    pExceptionObject[0] = &std::range_error::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  Concurrency::details::_Task_impl_base::_Wait(v2);
  v4 = (std::_Ref_count_base *)a1[35];
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (_QWORD *)a1[33];
  if ( v5 )
  {
    LOBYTE(v3) = v5 != a1 + 26;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 32LL))(v5, v3);
    a1[33] = 0;
  }
  return std::_Associated_state<int>::~_Associated_state<int>(a1);
}

```

## disassembly

```asm
0x140006e1c  mov     [rsp+arg_0], rbx
0x140006e21  push    rdi
0x140006e22  sub     rsp, 40h
0x140006e26  mov     rbx, rcx
0x140006e29  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x140006e30  mov     [rcx], rax
0x140006e33  mov     rcx, [rcx+110h]
0x140006e3a  test    rcx, rcx
0x140006e3d  jz      short loc_140006E91
0x140006e3f  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x140006e44  mov     rcx, [rbx+118h]; this
0x140006e4b  test    rcx, rcx
0x140006e4e  jz      short loc_140006E55
0x140006e50  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140006e55  lea     rdi, [rbx+0D0h]
0x140006e5c  mov     rcx, [rdi+38h]
0x140006e60  test    rcx, rcx
0x140006e63  jz      short loc_140006E7F
0x140006e65  mov     rax, [rcx]
0x140006e68  cmp     rcx, rdi
0x140006e6b  setnz   dl
0x140006e6e  mov     rax, [rax+20h]
0x140006e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e77  mov     qword ptr [rdi+38h], 0
0x140006e7f  mov     rcx, rbx
0x140006e82  mov     rbx, [rsp+48h+arg_0]
0x140006e87  add     rsp, 40h
0x140006e8b  pop     rdi
0x140006e8c  jmp     ??1?$_Associated_state@H@std@@UEAA@XZ; std::_Associated_state<int>::~_Associated_state<int>(void)
0x140006e91  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x140006e98  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140006e9d  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x140006ea2  lea     rax, ??_7range_error@std@@6B@; const std::range_error::`vftable'
0x140006ea9  mov     [rsp+48h+pExceptionObject], rax
0x140006eae  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x140006eb5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140006eba  call    _CxxThrowException
```
