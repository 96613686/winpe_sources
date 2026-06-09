# std::_Uninitialized_move<mi::MiInstance *,std::allocator<mi::MiInstance>>(mi::MiInstance * const,mi::MiInstance * const,mi::MiInstance *,std::allocator<mi::MiInstance> &)

- ea: `0x180026550`
- end: `0x18002658d`
- name: `??$_Uninitialized_move@PEAVMiInstance@mi@@V?$allocator@VMiInstance@mi@@@std@@@std@@YAPEAVMiInstance@mi@@QEAV12@0PEAV12@AEAV?$allocator@VMiInstance@mi@@@0@@Z`
- size: `61`
- prototype: `mi::MiInstance *__fastcall(__int64, __int64, mi::MiInstance *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800263bc`

## callees

- `0x18001ce94`
- `0x180026550`
- `0x1800267e8`

## pseudocode

```c
mi::MiInstance *__fastcall std::_Uninitialized_move<mi::MiInstance *>(__int64 a1, __int64 a2, mi::MiInstance *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r9

  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      mi::MiInstance::MiInstance(a3, v5);
      a3 = (mi::MiInstance *)((char *)a3 + 56);
      v5 = v6 + 56;
    }
    while ( v5 != v7 );
  }
  std::_Destroy_range<std::allocator<mi::MiInstance>>(a3);
  return a3;
}

```

## disassembly

```asm
0x180026550  push    rbx
0x180026552  sub     rsp, 20h
0x180026556  mov     r9, rdx
0x180026559  mov     rbx, r8
0x18002655c  mov     rdx, rcx
0x18002655f  cmp     rcx, r9
0x180026562  jz      short loc_180026579
0x180026564  mov     rcx, rbx
0x180026567  call    ??0MiInstance@mi@@QEAA@$$QEAV01@@Z; mi::MiInstance::MiInstance(mi::MiInstance &&)
0x18002656c  add     rbx, 38h ; '8'
0x180026570  add     rdx, 38h ; '8'
0x180026574  cmp     rdx, r9
0x180026577  jnz     short loc_180026564
0x180026579  mov     rdx, rbx
0x18002657c  mov     rcx, rbx; this
0x18002657f  call    ??$_Destroy_range@V?$allocator@VMiInstance@mi@@@std@@@std@@YAXPEAVMiInstance@mi@@QEAV12@AEAV?$allocator@VMiInstance@mi@@@0@@Z; std::_Destroy_range<std::allocator<mi::MiInstance>>(mi::MiInstance *,mi::MiInstance * const,std::allocator<mi::MiInstance> &)
0x180026584  mov     rax, rbx
0x180026587  add     rsp, 20h
0x18002658b  pop     rbx
0x18002658c  retn
```
