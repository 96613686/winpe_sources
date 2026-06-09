# HTTP2Channel::PrepareForSyncSend(ulong,uchar *,HTTP2SendContext *)

- ea: `0x180010ccc`
- end: `0x180010d2b`
- name: `?PrepareForSyncSend@HTTP2Channel@@QEAAXKPEAEPEAVHTTP2SendContext@@@Z`
- size: `95`
- prototype: `void __fastcall(HTTP2Channel *__hidden this, unsigned int, unsigned __int8 *, struct HTTP2SendContext *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a000`
- `0x18001a0b0`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180010cf0`
- `KERNEL32!ResetEvent` at `0x180010cf0`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180010ce3`
- `RPCRT4!I_RpcTransGetThreadEvent` at `0x180010ce3`

## pseudocode

```c
void __fastcall HTTP2Channel::PrepareForSyncSend(
        HTTP2Channel *this,
        int a2,
        unsigned __int8 *a3,
        struct HTTP2SendContext *a4)
{
  void *ThreadEvent; // rax

  ThreadEvent = (void *)I_RpcTransGetThreadEvent(this);
  *((_QWORD *)a4 + 8) = ThreadEvent;
  ResetEvent(ThreadEvent);
  *((_DWORD *)a4 + 14) = a2;
  *((_QWORD *)a4 + 6) = a3;
  *((_QWORD *)a4 + 1) = 259;
  *((_DWORD *)a4 + 22) = 2;
  *((_DWORD *)a4 + 7) = 0;
  *(_QWORD *)((char *)a4 + 92) = 64;
}

```

## disassembly

```asm
0x180010ccc  mov     [rsp+arg_0], rbx
0x180010cd1  mov     [rsp+arg_8], rsi
0x180010cd6  push    rdi
0x180010cd7  sub     rsp, 20h
0x180010cdb  mov     rsi, r9
0x180010cde  mov     rdi, r8
0x180010ce1  mov     ebx, edx
0x180010ce3  call    cs:__imp_I_RpcTransGetThreadEvent
0x180010ce9  mov     rcx, rax; hEvent
0x180010cec  mov     [rsi+40h], rax
0x180010cf0  call    cs:__imp_ResetEvent
0x180010cf6  mov     [rsi+38h], ebx
0x180010cf9  mov     rbx, [rsp+28h+arg_0]
0x180010cfe  mov     [rsi+30h], rdi
0x180010d02  mov     qword ptr [rsi+8], 103h
0x180010d0a  mov     dword ptr [rsi+58h], 2
0x180010d11  mov     dword ptr [rsi+1Ch], 0
0x180010d18  mov     qword ptr [rsi+5Ch], 40h ; '@'
0x180010d20  mov     rsi, [rsp+28h+arg_8]
0x180010d25  add     rsp, 20h
0x180010d29  pop     rdi
0x180010d2a  retn
```
