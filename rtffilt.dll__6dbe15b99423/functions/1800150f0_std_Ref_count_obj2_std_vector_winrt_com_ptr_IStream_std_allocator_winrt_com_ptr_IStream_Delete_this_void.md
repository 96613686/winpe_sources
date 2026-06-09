# std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>,std::allocator<winrt::com_ptr<IStream>>>>::_Delete_this(void)

- ea: `0x1800150f0`
- end: `0x18001510f`
- name: `?_Delete_this@?$_Ref_count_obj2@V?$vector@U?$com_ptr@UIStream@@@winrt@@V?$allocator@U?$com_ptr@UIStream@@@winrt@@@std@@@std@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800150f0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<std::vector<winrt::com_ptr<IStream>>>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x1800150f0  sub     rsp, 28h
0x1800150f4  test    rcx, rcx
0x1800150f7  jz      short loc_18001510A
0x1800150f9  mov     rax, [rcx]
0x1800150fc  mov     edx, 1
0x180015101  mov     rax, [rax+10h]
0x180015105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001510a  add     rsp, 28h
0x18001510e  retn
```
