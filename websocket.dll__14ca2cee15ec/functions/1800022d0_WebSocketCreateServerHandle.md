# WebSocketCreateServerHandle

- ea: `0x1800022d0`
- end: `0x1800022e0`
- name: `WebSocketCreateServerHandle`
- size: `16`
- prototype: `__int64 __fastcall(struct _WEB_SOCKET_PROPERTY *, unsigned int, struct WebSocket **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800045c0`

## pseudocode

```c
__int64 __fastcall WebSocketCreateServerHandle(struct _WEB_SOCKET_PROPERTY *a1, unsigned int a2, struct WebSocket **a3)
{
  return WebSocket::Create(0, a1, a2, a3);
}

```

## disassembly

```asm
0x1800022d0  mov     r9, r8; struct WebSocket **
0x1800022d3  mov     r8d, edx; unsigned int
0x1800022d6  mov     rdx, rcx; struct _WEB_SOCKET_PROPERTY *
0x1800022d9  xor     ecx, ecx; int
0x1800022db  jmp     ?Create@WebSocket@@SAJHQEAU_WEB_SOCKET_PROPERTY@@KPEAPEAV1@@Z; WebSocket::Create(int,_WEB_SOCKET_PROPERTY * const,ulong,WebSocket * *)
```
