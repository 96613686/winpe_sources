# std::_Destroy_range<std::allocator<_bstr_t>>(_bstr_t *,_bstr_t * const,std::allocator<_bstr_t> &)

- ea: `0x180004094`
- end: `0x1800040c5`
- name: `??$_Destroy_range@V?$allocator@V_bstr_t@@@std@@@std@@YAXPEAV_bstr_t@@QEAV1@AEAV?$allocator@V_bstr_t@@@0@@Z`
- size: `49`
- prototype: `void __fastcall(_bstr_t *this, _bstr_t *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180004164`
- `0x180004240`
- `0x1800072b4`
- `0x180008730`
- `0x180009260`
- `0x180009fb0`
- `0x18000a130`
- `0x18000a3b0`
- `0x18000a48c`
- `0x18000b5c8`

## callees

- `0x180003fec`
- `0x180004094`

## pseudocode

```c
void __fastcall std::_Destroy_range<std::allocator<_bstr_t>>(_bstr_t *this, _bstr_t *a2)
{
  _bstr_t *v3; // rbx

  if ( this != a2 )
  {
    v3 = this;
    do
    {
      _bstr_t::_Free(v3);
      v3 = (_bstr_t *)((char *)v3 + 8);
    }
    while ( v3 != a2 );
  }
}

```

## disassembly

```asm
0x180004094  cmp     rcx, rdx
0x180004097  jz      short locret_1800040C4
0x180004099  mov     [rsp+arg_0], rbx
0x18000409e  push    rdi
0x18000409f  sub     rsp, 20h
0x1800040a3  mov     rdi, rdx
0x1800040a6  mov     rbx, rcx
0x1800040a9  mov     rcx, rbx; this
0x1800040ac  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800040b1  add     rbx, 8
0x1800040b5  cmp     rbx, rdi
0x1800040b8  jnz     short loc_1800040A9
0x1800040ba  mov     rbx, [rsp+28h+arg_0]
0x1800040bf  add     rsp, 20h
0x1800040c3  pop     rdi
0x1800040c4  retn
```
