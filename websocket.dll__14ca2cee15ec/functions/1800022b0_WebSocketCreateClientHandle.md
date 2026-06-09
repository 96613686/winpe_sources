# WebSocketCreateClientHandle

- ea: `0x1800022b0`
- end: `0x1800022c3`
- name: `WebSocketCreateClientHandle`
- size: `19`
- prototype: `__int64 __fastcall(struct _WEB_SOCKET_PROPERTY *, unsigned int, struct WebSocket **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800045c0`

## pseudocode

```c
__int64 __fastcall WebSocketCreateClientHandle(struct _WEB_SOCKET_PROPERTY *a1, unsigned int a2, struct WebSocket **a3)
{
  return WebSocket::Create(1, a1, a2, a3);
}

```

## disassembly

```asm
0x1800022b0  mov     r9, r8; struct WebSocket **
0x1800022b3  mov     r8d, edx; unsigned int
0x1800022b6  mov     rdx, rcx; struct _WEB_SOCKET_PROPERTY *
0x1800022b9  mov     ecx, 1; int
0x1800022be  jmp     ?Create@WebSocket@@SAJHQEAU_WEB_SOCKET_PROPERTY@@KPEAPEAV1@@Z; WebSocket::Create(int,_WEB_SOCKET_PROPERTY * const,ulong,WebSocket * *)
```
