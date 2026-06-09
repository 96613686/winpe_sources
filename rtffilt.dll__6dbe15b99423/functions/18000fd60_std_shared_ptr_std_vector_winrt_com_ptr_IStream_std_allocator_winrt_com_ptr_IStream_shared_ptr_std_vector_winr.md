# std::shared_ptr<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>::~shared_ptr<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>(void)

- ea: `0x18000fd60`
- end: `0x18000fdac`
- name: `??1?$shared_ptr@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@QEAA@XZ`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a6eb`
- `0x18001a721`

## callees

- `0x18000fd60`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<std::vector<winrt::com_ptr<IStream>>>::~shared_ptr<std::vector<winrt::com_ptr<IStream>>>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax

  v1 = *(volatile signed __int32 **)(a1 + 8);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
      result = (unsigned int)_InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fd60  push    rbx
0x18000fd62  sub     rsp, 20h
0x18000fd66  mov     rbx, [rcx+8]
0x18000fd6a  test    rbx, rbx
0x18000fd6d  jz      short loc_18000FDA6
0x18000fd6f  or      eax, 0FFFFFFFFh
0x18000fd72  lock xadd [rbx+8], eax
0x18000fd77  cmp     eax, 1
0x18000fd7a  jnz     short loc_18000FDA6
0x18000fd7c  mov     rax, [rbx]
0x18000fd7f  mov     rcx, rbx
0x18000fd82  mov     rax, [rax]
0x18000fd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8a  or      eax, 0FFFFFFFFh
0x18000fd8d  lock xadd [rbx+0Ch], eax
0x18000fd92  cmp     eax, 1
0x18000fd95  jnz     short loc_18000FDA6
0x18000fd97  mov     rax, [rbx]
0x18000fd9a  mov     rcx, rbx
0x18000fd9d  mov     rax, [rax+8]
0x18000fda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda6  add     rsp, 20h
0x18000fdaa  pop     rbx
0x18000fdab  retn
```
