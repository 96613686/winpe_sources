# std::default_delete<CDevNode>::operator()(CDevNode *)

- ea: `0x180003cc4`
- end: `0x180003ced`
- name: `??R?$default_delete@VCDevNode@@@std@@QEBAXPEAVCDevNode@@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003c6c`
- `0x180008290`
- `0x18000ab84`

## callees

- `0x180002434`
- `0x180003cc4`
- `0x180003fec`

## pseudocode

```c
void __fastcall std::default_delete<CDevNode>::operator()(__int64 a1, __int64 a2)
{
  if ( a2 )
  {
    _bstr_t::_Free((_bstr_t *)(a2 + 96));
    operator delete((void *)a2);
  }
}

```

## disassembly

```asm
0x180003cc4  test    rdx, rdx
0x180003cc7  jz      short locret_180003CEC
0x180003cc9  push    rbx
0x180003cca  sub     rsp, 20h
0x180003cce  lea     rcx, [rdx+60h]; this
0x180003cd2  mov     rbx, rdx
0x180003cd5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180003cda  mov     edx, 68h ; 'h'
0x180003cdf  mov     rcx, rbx; Block
0x180003ce2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003ce7  add     rsp, 20h
0x180003ceb  pop     rbx
0x180003cec  retn
```
