# std::_Ref_count_obj2<mi::object_element<mi::MiInstance>>::_Delete_this(void)

- ea: `0x180012be0`
- end: `0x180012c00`
- name: `?_Delete_this@?$_Ref_count_obj2@V?$object_element@VMiInstance@mi@@@mi@@@std@@EEAAXXZ`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012be0`
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
0x180012be0  sub     rsp, 28h
0x180012be4  test    rcx, rcx
0x180012be7  jz      short loc_180012BFA
0x180012be9  mov     rax, [rcx]
0x180012bec  mov     edx, 1
0x180012bf1  mov     rax, [rax+10h]
0x180012bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bfa  add     rsp, 28h
0x180012bfe  retn
```
