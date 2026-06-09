# std::unique_ptr<KEY_MAPS_MEM,std::default_delete<KEY_MAPS_MEM>>::~unique_ptr<KEY_MAPS_MEM,std::default_delete<KEY_MAPS_MEM>>(void)

- ea: `0x18000dc38`
- end: `0x18000dc53`
- name: `??1?$unique_ptr@UKEY_MAPS_MEM@@U?$default_delete@UKEY_MAPS_MEM@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001001c`
- `0x180016324`
- `0x18003575c`

## callees

- `0x180002360`
- `0x18000dc38`

## pseudocode

```c
void __fastcall std::unique_ptr<KEY_MAPS_MEM>::~unique_ptr<KEY_MAPS_MEM>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000dc38  sub     rsp, 28h
0x18000dc3c  mov     rcx, [rcx]; Block
0x18000dc3f  test    rcx, rcx
0x18000dc42  jz      short loc_18000DC4E
0x18000dc44  mov     edx, 0B24h
0x18000dc49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc4e  add     rsp, 28h
0x18000dc52  retn
```
