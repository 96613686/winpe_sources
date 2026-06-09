# std::_Uninitialized_move<mi::MiInstance *,std::allocator<mi::MiInstance>>(mi::MiInstance * const,mi::MiInstance * const,mi::MiInstance *,std::allocator<mi::MiInstance> &)

- ea: `0x180026894`
- end: `0x1800268d2`
- name: `??$_Uninitialized_move@PEAVMiInstance@mi@@V?$allocator@VMiInstance@mi@@@std@@@std@@YAPEAVMiInstance@mi@@QEAV12@0PEAV12@AEAV?$allocator@VMiInstance@mi@@@0@@Z`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180026700`

## callees

- `0x18001cfb0`
- `0x180026894`
- `0x180026b2c`

## pseudocode

```c
mi::MiInstance *__fastcall std::_Uninitialized_move<mi::MiInstance *>(__int64 a1, __int64 a2, mi::MiInstance *a3)
{
  __int64 v4; // rdx
  __int64 v5; // r9

  if ( a1 != a2 )
  {
    do
    {
      mi::MiInstance::MiInstance(a3);
      a3 = (mi::MiInstance *)((char *)a3 + 56);
    }
    while ( v4 + 56 != v5 );
  }
  std::_Destroy_range<std::allocator<mi::MiInstance>>(a3);
  return a3;
}

```

## disassembly

```asm
0x180026894  push    rbx
0x180026896  sub     rsp, 20h
0x18002689a  mov     r9, rdx
0x18002689d  mov     rbx, r8
0x1800268a0  mov     rdx, rcx
0x1800268a3  cmp     rcx, r9
0x1800268a6  jz      short loc_1800268BD
0x1800268a8  mov     rcx, rbx
0x1800268ab  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x1800268b0  add     rbx, 38h ; '8'
0x1800268b4  add     rdx, 38h ; '8'
0x1800268b8  cmp     rdx, r9
0x1800268bb  jnz     short loc_1800268A8
0x1800268bd  mov     rdx, rbx
0x1800268c0  mov     rcx, rbx; this
0x1800268c3  call    ??$_Destroy_range@V?$allocator@VMiInstance@mi@@@std@@@std@@YAXPEAVMiInstance@mi@@QEAV12@AEAV?$allocator@VMiInstance@mi@@@0@@Z; std::_Destroy_range<std::allocator<mi::MiInstance>>(mi::MiInstance *,mi::MiInstance * const,std::allocator<mi::MiInstance> &)
0x1800268c8  mov     rax, rbx
0x1800268cb  add     rsp, 20h
0x1800268cf  pop     rbx
0x1800268d0  retn
```
