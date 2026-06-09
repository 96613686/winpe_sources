# std::_Uninitialized_move<_bstr_t *,std::allocator<_bstr_t>>(_bstr_t * const,_bstr_t * const,_bstr_t *,std::allocator<_bstr_t> &)

- ea: `0x18000a3b0`
- end: `0x18000a3ed`
- name: `??$_Uninitialized_move@PEAV_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@YAPEAV_bstr_t@@QEAV1@0PEAV1@AEAV?$allocator@V_bstr_t@@@0@@Z`
- size: `61`
- prototype: `_bstr_t *__fastcall(__int64, __int64, _bstr_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a130`

## callees

- `0x180004094`
- `0x18000a3b0`
- `0x18000a3f4`

## pseudocode

```c
_bstr_t *__fastcall std::_Uninitialized_move<_bstr_t *>(__int64 a1, __int64 a2, _bstr_t *a3)
{
  __int64 v4; // r8
  __int64 i; // r9
  __int64 v6; // r8

  v4 = a1;
  for ( i = a2; v4 != i; v4 = v6 + 8 )
  {
    std::_Default_allocator_traits<std::allocator<_bstr_t>>::construct<_bstr_t,_bstr_t>(a1, a3, v4, i);
    a3 = (_bstr_t *)((char *)a3 + 8);
  }
  std::_Destroy_range<std::allocator<_bstr_t>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18000a3b0  push    rbx
0x18000a3b2  sub     rsp, 20h
0x18000a3b6  mov     rbx, r8
0x18000a3b9  mov     r8, rcx
0x18000a3bc  mov     r9, rdx
0x18000a3bf  cmp     rcx, rdx
0x18000a3c2  jz      short loc_18000A3D9
0x18000a3c4  mov     rdx, rbx
0x18000a3c7  call    ??$construct@V_bstr_t@@V1@@?$_Default_allocator_traits@V?$allocator@V_bstr_t@@@std@@@std@@SAXAEAV?$allocator@V_bstr_t@@@1@QEAV_bstr_t@@$$QEAV3@@Z; std::_Default_allocator_traits<std::allocator<_bstr_t>>::construct<_bstr_t,_bstr_t>(std::allocator<_bstr_t> &,_bstr_t * const,_bstr_t &&)
0x18000a3cc  add     rbx, 8
0x18000a3d0  add     r8, 8
0x18000a3d4  cmp     r8, r9
0x18000a3d7  jnz     short loc_18000A3C4
0x18000a3d9  mov     rdx, rbx
0x18000a3dc  mov     rcx, rbx; this
0x18000a3df  call    ??$_Destroy_range@V?$allocator@V_bstr_t@@@std@@@std@@YAXPEAV_bstr_t@@QEAV1@AEAV?$allocator@V_bstr_t@@@0@@Z; std::_Destroy_range<std::allocator<_bstr_t>>(_bstr_t *,_bstr_t * const,std::allocator<_bstr_t> &)
0x18000a3e4  mov     rax, rbx
0x18000a3e7  add     rsp, 20h
0x18000a3eb  pop     rbx
0x18000a3ec  retn
```
