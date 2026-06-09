# STATIC_URI_STORED_CONTEXT::CleanupStoredContext(void)

- ea: `0x180002db0`
- end: `0x180002dd0`
- name: `?CleanupStoredContext@STATIC_URI_STORED_CONTEXT@@UEAAXXZ`
- size: `32`
- prototype: `void __fastcall(STATIC_URI_STORED_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001398`
- `0x180002cf0`
- `0x180002db0`

## pseudocode

```c
void __fastcall STATIC_URI_STORED_CONTEXT::CleanupStoredContext(STATIC_URI_STORED_CONTEXT *this)
{
  if ( this )
  {
    STATIC_URI_STORED_CONTEXT::~STATIC_URI_STORED_CONTEXT(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180002db0  test    rcx, rcx
0x180002db3  jz      short locret_180002DCF
0x180002db5  push    rbx
0x180002db6  sub     rsp, 20h
0x180002dba  mov     rbx, rcx
0x180002dbd  call    ??1STATIC_URI_STORED_CONTEXT@@QEAA@XZ
0x180002dc2  mov     rcx, rbx; Block
0x180002dc5  call    ??3@YAXPEAX@Z
0x180002dca  add     rsp, 20h
0x180002dce  pop     rbx
0x180002dcf  retn
```
