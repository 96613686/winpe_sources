# std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::~unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>(void)

- ea: `0x1800338f4`
- end: `0x180033917`
- name: `??1?$unique_ptr@U_SEC_CHANNEL_BINDINGS_EX@@Uupgraded_channel_bindings_deleter@@@std@@QEAA@XZ`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180033f78`
- `0x180034398`
- `0x180034434`

## callees

- `0x180012c50`
- `0x1800338f4`

## pseudocode

```c
void __fastcall std::unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>::~unique_ptr<_SEC_CHANNEL_BINDINGS_EX,upgraded_channel_bindings_deleter>(
        __int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    if ( *(_BYTE *)a1 )
      operator delete(*(void **)(a1 + 8));
  }
}

```

## disassembly

```asm
0x1800338f4  sub     rsp, 28h
0x1800338f8  cmp     qword ptr [rcx+8], 0
0x1800338fd  jz      short loc_180033912
0x1800338ff  cmp     byte ptr [rcx], 0
0x180033902  jz      short loc_180033912
0x180033904  mov     rcx, [rcx+8]; void *
0x180033908  mov     edx, 30h ; '0'; unsigned __int64
0x18003390d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180033912  add     rsp, 28h
0x180033916  retn
```
