# CWpnIdleTaskHandlerFactory::`scalar deleting destructor'(uint)

- ea: `0x180006010`
- end: `0x180006042`
- name: `??_GCWpnIdleTaskHandlerFactory@@EEAAPEAXI@Z`
- size: `50`
- prototype: `void *__fastcall(CWpnIdleTaskHandlerFactory *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001534`
- `0x180006010`

## pseudocode

```c
CWpnIdleTaskHandlerFactory *__fastcall CWpnIdleTaskHandlerFactory::`scalar deleting destructor'(
        CWpnIdleTaskHandlerFactory *this,
        char a2)
{
  *(_QWORD *)this = &CWpnIdleTaskHandlerFactory::`vftable';
  _InterlockedDecrement(&g_Count);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006010  push    rbx
0x180006012  sub     rsp, 20h
0x180006016  lea     rax, ??_7CWpnIdleTaskHandlerFactory@@6B@; const CWpnIdleTaskHandlerFactory::`vftable'
0x18000601d  mov     rbx, rcx
0x180006020  mov     [rcx], rax
0x180006023  lock dec cs:?g_Count@@3JA; long g_Count
0x18000602a  test    dl, 1
0x18000602d  jz      short loc_180006039
0x18000602f  mov     edx, 10h; unsigned __int64
0x180006034  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006039  mov     rax, rbx
0x18000603c  add     rsp, 20h
0x180006040  pop     rbx
0x180006041  retn
```
