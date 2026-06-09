# WebSocketDeleteHandle

- ea: `0x1800022f0`
- end: `0x180002315`
- name: `WebSocketDeleteHandle`
- size: `37`
- prototype: `void __fastcall(WebSocket *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001750`
- `0x1800022f0`
- `0x180003cf8`

## pseudocode

```c
void __fastcall WebSocketDeleteHandle(WebSocket *Block)
{
  if ( Block )
  {
    WebSocket::~WebSocket(Block);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x1800022f0  test    rcx, rcx
0x1800022f3  jz      short locret_180002314
0x1800022f5  push    rbx
0x1800022f6  sub     rsp, 20h
0x1800022fa  mov     rbx, rcx
0x1800022fd  call    ??1WebSocket@@QEAA@XZ; WebSocket::~WebSocket(void)
0x180002302  mov     edx, 28h ; '('
0x180002307  mov     rcx, rbx; Block
0x18000230a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000230f  add     rsp, 20h
0x180002313  pop     rbx
0x180002314  retn
```
