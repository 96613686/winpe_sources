# std::_Ref_count_obj2<mi::object_element<mi::MiInstance>>::_Delete_this(void)

- ea: `0x180012d10`
- end: `0x180012d2f`
- name: `?_Delete_this@?$_Ref_count_obj2@V?$object_element@VMiInstance@mi@@@mi@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012d10`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<mi::object_element<mi::MiInstance>>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180012d10  sub     rsp, 28h
0x180012d14  test    rcx, rcx
0x180012d17  jz      short loc_180012D2A
0x180012d19  mov     rax, [rcx]
0x180012d1c  mov     edx, 1
0x180012d21  mov     rax, [rax+10h]
0x180012d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d2a  add     rsp, 28h
0x180012d2e  retn
```
