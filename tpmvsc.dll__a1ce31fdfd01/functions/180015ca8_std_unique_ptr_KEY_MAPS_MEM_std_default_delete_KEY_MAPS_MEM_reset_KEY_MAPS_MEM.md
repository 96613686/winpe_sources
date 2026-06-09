# std::unique_ptr<KEY_MAPS_MEM,std::default_delete<KEY_MAPS_MEM>>::reset(KEY_MAPS_MEM *)

- ea: `0x180015ca8`
- end: `0x180015cc9`
- name: `?reset@?$unique_ptr@UKEY_MAPS_MEM@@U?$default_delete@UKEY_MAPS_MEM@@@std@@@std@@QEAAXPEAUKEY_MAPS_MEM@@@Z`
- size: `33`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c7bc`
- `0x180016954`
- `0x180029000`

## callees

- `0x180002360`
- `0x180015ca8`

## pseudocode

```c
void __fastcall std::unique_ptr<KEY_MAPS_MEM>::reset(void **a1, void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    operator delete(v2);
}

```

## disassembly

```asm
0x180015ca8  sub     rsp, 28h
0x180015cac  mov     rax, [rcx]
0x180015caf  mov     [rcx], rdx
0x180015cb2  test    rax, rax
0x180015cb5  jz      short loc_180015CC4
0x180015cb7  mov     edx, 0B24h
0x180015cbc  mov     rcx, rax; Block
0x180015cbf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015cc4  add     rsp, 28h
0x180015cc8  retn
```
