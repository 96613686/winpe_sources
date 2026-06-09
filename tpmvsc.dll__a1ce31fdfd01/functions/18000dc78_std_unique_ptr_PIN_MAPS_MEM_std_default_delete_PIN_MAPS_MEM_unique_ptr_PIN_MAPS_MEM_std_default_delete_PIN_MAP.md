# std::unique_ptr<PIN_MAPS_MEM,std::default_delete<PIN_MAPS_MEM>>::~unique_ptr<PIN_MAPS_MEM,std::default_delete<PIN_MAPS_MEM>>(void)

- ea: `0x18000dc78`
- end: `0x18000dc8e`
- name: `??1?$unique_ptr@UPIN_MAPS_MEM@@U?$default_delete@UPIN_MAPS_MEM@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012990`
- `0x180016324`
- `0x1800359bf`

## callees

- `0x18000dc78`
- `0x18000f3a4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<PIN_MAPS_MEM>::~unique_ptr<PIN_MAPS_MEM>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<PIN_MAPS_MEM>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000dc78  sub     rsp, 28h
0x18000dc7c  mov     rdx, [rcx]
0x18000dc7f  test    rdx, rdx
0x18000dc82  jz      short loc_18000DC89
0x18000dc84  call    ??R?$default_delete@UPIN_MAPS_MEM@@@std@@QEBAXPEAUPIN_MAPS_MEM@@@Z; std::default_delete<PIN_MAPS_MEM>::operator()(PIN_MAPS_MEM *)
0x18000dc89  add     rsp, 28h
0x18000dc8d  retn
```
