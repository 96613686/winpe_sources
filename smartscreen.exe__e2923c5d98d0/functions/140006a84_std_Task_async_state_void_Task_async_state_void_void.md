# std::_Task_async_state<void>::~_Task_async_state<void>(void)

- ea: `0x140006a84`
- end: `0x140006b28`
- name: `??1?$_Task_async_state@X@std@@UEAA@XZ`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140007330`

## callees

- `0x140006a00`
- `0x140006a84`
- `0x140006b30`
- `0x1400195c0`
- `0x14001cafc`
- `0x14002771c`
- `0x140068010`

## string_xrefs

- `0x140006af9`: `This function cannot be called on a default constructed task`

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
0x140006a84  mov     [rsp+arg_0], rbx
0x140006a89  push    rdi
0x140006a8a  sub     rsp, 40h
0x140006a8e  mov     rbx, rcx
0x140006a91  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x140006a98  mov     [rcx], rax
0x140006a9b  mov     rcx, [rcx+110h]
0x140006aa2  test    rcx, rcx
0x140006aa5  jz      short loc_140006AF9
0x140006aa7  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x140006aac  mov     rcx, [rbx+118h]; this
0x140006ab3  test    rcx, rcx
0x140006ab6  jz      short loc_140006ABD
0x140006ab8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140006abd  lea     rdi, [rbx+0D0h]
0x140006ac4  mov     rcx, [rdi+38h]
0x140006ac8  test    rcx, rcx
0x140006acb  jz      short loc_140006AE7
0x140006acd  mov     rax, [rcx]
0x140006ad0  cmp     rcx, rdi
0x140006ad3  setnz   dl
0x140006ad6  mov     rax, [rax+20h]
0x140006ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006adf  mov     qword ptr [rdi+38h], 0
0x140006ae7  mov     rcx, rbx
0x140006aea  mov     rbx, [rsp+48h+arg_0]
0x140006aef  add     rsp, 40h
0x140006af3  pop     rdi
0x140006af4  jmp     ??1?$_Associated_state@H@std@@UEAA@XZ; std::_Associated_state<int>::~_Associated_state<int>(void)
0x140006af9  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x140006b00  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140006b05  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x140006b0a  lea     rax, ??_7range_error@std@@6B@; const std::range_error::`vftable'
0x140006b11  mov     [rsp+48h+pExceptionObject], rax
0x140006b16  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x140006b1d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140006b22  call    _CxxThrowException
```
